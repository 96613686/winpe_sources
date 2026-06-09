# CPersistSession::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x180020f40`
- end: `0x180021059`
- name: `?GetProperties@CPersistSession@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `281`
- prototype: `int(CPersistSession *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180015fb4`
- `0x180020f40`
- `0x18002c3dc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180020f88`
- `KERNEL32!GetCurrentThreadId` at `0x180020f88`
- `KERNEL32!LeaveCriticalSection` at `0x180021036`
- `KERNEL32!LeaveCriticalSection` at `0x180021036`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020fa7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180020fa7`
- `MSDART!UMSEnterCSWraper` at `0x180020f74`
- `MSDART!UMSEnterCSWraper` at `0x180020f74`

## pseudocode

```c
__int64 __fastcall CPersistSession::GetProperties(
        GUID *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  GUID *v9; // r14
  unsigned __int8 *v10; // rdi
  int Properties; // eax
  unsigned int v12; // r15d
  __int64 v14; // rcx

  v9 = this + 2;
  UMSEnterCSWraper(&this[2]);
  v10 = &this[2].Data4[4];
  if ( !*(_DWORD *)&this[2].Data4[4] )
    *(_DWORD *)this[2].Data4 = GetCurrentThreadId();
  ++*(_DWORD *)v10;
  ++this[3].Data1;
  SetErrorInfo(0, 0);
  this[5] = IID_ISessionProperties;
  *(_DWORD *)&this[262].Data2 = 0;
  Properties = CUtlProps::utlGetProperties(
                 (CUtlProps *)this[283].Data4,
                 a2,
                 a3,
                 a4,
                 a5,
                 (const struct CBidGenericBase *)this[282].Data4);
  v12 = Exit(Properties, 0xBB9u);
  --this[3].Data1;
  if ( (*(_DWORD *)v10)-- == 1 )
    *(_DWORD *)this[2].Data4 = -1;
  v14 = *(_QWORD *)&v9->Data1;
  --*(_DWORD *)(v14 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
  return v12;
}

```

## disassembly

```asm
0x180020f40  mov     [rsp+arg_8], rbx
0x180020f45  mov     [rsp+arg_10], rsi
0x180020f4a  mov     [rsp+arg_0], rcx
0x180020f4f  push    rdi
0x180020f50  push    r12
0x180020f52  push    r13
0x180020f54  push    r14
0x180020f56  push    r15
0x180020f58  sub     rsp, 60h
0x180020f5c  mov     r15, r9
0x180020f5f  mov     r12, r8
0x180020f62  mov     r13d, edx
0x180020f65  mov     rbx, rcx
0x180020f68  lea     r14, [rcx+20h]
0x180020f6c  mov     [rsp+88h+var_50], r14
0x180020f71  mov     rcx, r14
0x180020f74  call    cs:__imp_UMSEnterCSWraper
0x180020f7a  lea     rdi, [rbx+2Ch]
0x180020f7e  mov     [rsp+88h+var_48], rdi
0x180020f83  cmp     dword ptr [rdi], 0
0x180020f86  jnz     short loc_180020F91
0x180020f88  call    cs:__imp_GetCurrentThreadId
0x180020f8e  mov     [rbx+28h], eax
0x180020f91  inc     dword ptr [rdi]
0x180020f93  lea     rsi, [rbx+30h]
0x180020f97  mov     [rsp+88h+var_40], rsi
0x180020f9c  inc     dword ptr [rsi]
0x180020f9e  mov     [rsp+88h+var_38], r14
0x180020fa3  xor     edx, edx; perrinfo
0x180020fa5  xor     ecx, ecx; dwReserved
0x180020fa7  call    cs:__imp_SetErrorInfo
0x180020fad  movups  xmm0, xmmword ptr cs:IID_ISessionProperties.Data1
0x180020fb4  movdqu  xmmword ptr [rbx+50h], xmm0
0x180020fb9  mov     dword ptr [rbx+1064h], 0
0x180020fc3  lea     rax, [rbx+11A8h]
0x180020fca  lea     rcx, [rbx+11B8h]; this
0x180020fd1  mov     [rsp+88h+var_60], rax; struct CBidGenericBase *
0x180020fd6  mov     rax, [rsp+88h+arg_20]
0x180020fde  mov     [rsp+88h+var_68], rax; struct tagDBPROPSET **
0x180020fe3  mov     r9, r15; unsigned int *
0x180020fe6  mov     r8, r12; struct tagDBPROPIDSET *
0x180020fe9  mov     edx, r13d; unsigned int
0x180020fec  call    ?utlGetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; CUtlProps::utlGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x180020ff1  nop
0x180020ff2  jmp     short loc_180021011
0x180020ff4  jmp     short $+2
0x180020ff6  mov     rsi, [rsp+88h+var_40]
0x180020ffb  mov     rdi, [rsp+88h+var_48]
0x180021000  mov     r14, [rsp+88h+var_50]
0x180021005  mov     eax, [rsp+88h+var_58]
0x180021009  mov     rbx, [rsp+88h+arg_0]
0x180021011  mov     edx, 0BB9h; unsigned int
0x180021016  mov     ecx, eax; int
0x180021018  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18002101d  mov     r15d, eax
0x180021020  or      eax, 0FFFFFFFFh
0x180021023  add     [rsi], eax
0x180021025  add     [rdi], eax
0x180021027  jnz     short loc_18002102C
0x180021029  mov     [rbx+28h], eax
0x18002102c  mov     rcx, [r14]
0x18002102f  dec     dword ptr [rcx+30h]
0x180021032  add     rcx, 8; lpCriticalSection
0x180021036  call    cs:__imp_LeaveCriticalSection
0x18002103c  mov     eax, r15d
0x18002103f  lea     r11, [rsp+88h+var_28]
0x180021044  mov     rbx, [r11+38h]
0x180021048  mov     rsi, [r11+40h]
0x18002104c  mov     rsp, r11
0x18002104f  pop     r15
0x180021051  pop     r14
0x180021053  pop     r13
0x180021055  pop     r12
0x180021057  pop     rdi
0x180021058  retn
```
