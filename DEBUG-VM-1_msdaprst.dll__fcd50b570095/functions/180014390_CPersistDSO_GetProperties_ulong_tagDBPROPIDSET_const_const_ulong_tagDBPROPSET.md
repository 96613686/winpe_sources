# CPersistDSO::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)

- ea: `0x180014390`
- end: `0x1800144a9`
- name: `?GetProperties@CPersistDSO@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `281`
- prototype: `int(CPersistDSO *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180014390`
- `0x180015fb4`
- `0x18002c3dc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800143d8`
- `KERNEL32!GetCurrentThreadId` at `0x1800143d8`
- `KERNEL32!LeaveCriticalSection` at `0x180014486`
- `KERNEL32!LeaveCriticalSection` at `0x180014486`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800143f7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800143f7`
- `MSDART!UMSEnterCSWraper` at `0x1800143c4`
- `MSDART!UMSEnterCSWraper` at `0x1800143c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::GetProperties(
        CPersistDSO *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  CPersistDSO *v8; // rbx
  _QWORD *v9; // r14
  _DWORD *v10; // rdi
  _DWORD *v11; // rsi
  int Properties; // eax
  unsigned int v13; // r15d
  __int64 v15; // rcx
  int v18; // [rsp+30h] [rbp-58h]
  int v19; // [rsp+30h] [rbp-58h]
  int v20; // [rsp+34h] [rbp-54h] BYREF
  char *v21; // [rsp+38h] [rbp-50h]
  _DWORD *v22; // [rsp+40h] [rbp-48h]
  _DWORD *v23; // [rsp+48h] [rbp-40h]
  _QWORD *v24; // [rsp+50h] [rbp-38h]

  v8 = this;
  v9 = (_QWORD *)((char *)this + 48);
  v21 = (char *)this + 48;
  UMSEnterCSWraper((char *)this + 48);
  v10 = (_DWORD *)((char *)v8 + 60);
  v22 = (_DWORD *)((char *)v8 + 60);
  if ( !*((_DWORD *)v8 + 15) )
    *((_DWORD *)v8 + 14) = GetCurrentThreadId();
  ++*v10;
  v11 = (_DWORD *)((char *)v8 + 64);
  v23 = (_DWORD *)((char *)v8 + 64);
  ++*((_DWORD *)v8 + 16);
  v24 = v9;
  SetErrorInfo(0, 0);
  try
  {
    *((GUID *)v8 + 6) = IID_IDBProperties;
    *((_DWORD *)v8 + 1053) = 0;
    Properties = CUtlProps::utlGetProperties(
                   (CPersistDSO *)((char *)v8 + 4600),
                   a2,
                   a3,
                   a4,
                   a5,
                   (CPersistDSO *)((char *)v8 + 4584));
  }
  catch ( long v20 )
  {
    v18 = v20;
    v11 = v23;
    v10 = v22;
    v9 = v21;
    Properties = v18;
    v8 = this;
  }
  catch ( ... )
  {
    v19 = -2147467259;
    v11 = v23;
    v10 = v22;
    v9 = v21;
    Properties = v19;
    v8 = this;
  }
  v13 = Exit(Properties, 0xBB9u);
  --*v11;
  if ( (*v10)-- == 1 )
    *((_DWORD *)v8 + 14) = -1;
  v15 = *v9;
  --*(_DWORD *)(v15 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
  return v13;
}

```

## disassembly

```asm
0x180014390  mov     [rsp+arg_8], rbx
0x180014395  mov     [rsp+arg_10], rsi
0x18001439a  mov     [rsp+arg_0], rcx
0x18001439f  push    rdi
0x1800143a0  push    r12
0x1800143a2  push    r13
0x1800143a4  push    r14
0x1800143a6  push    r15
0x1800143a8  sub     rsp, 60h
0x1800143ac  mov     r15, r9
0x1800143af  mov     r12, r8
0x1800143b2  mov     r13d, edx
0x1800143b5  mov     rbx, rcx
0x1800143b8  lea     r14, [rcx+30h]
0x1800143bc  mov     [rsp+88h+var_50], r14
0x1800143c1  mov     rcx, r14
0x1800143c4  call    cs:__imp_UMSEnterCSWraper
0x1800143ca  lea     rdi, [rbx+3Ch]
0x1800143ce  mov     [rsp+88h+var_48], rdi
0x1800143d3  cmp     dword ptr [rdi], 0
0x1800143d6  jnz     short loc_1800143E1
0x1800143d8  call    cs:__imp_GetCurrentThreadId
0x1800143de  mov     [rbx+38h], eax
0x1800143e1  inc     dword ptr [rdi]
0x1800143e3  lea     rsi, [rbx+40h]
0x1800143e7  mov     [rsp+88h+var_40], rsi
0x1800143ec  inc     dword ptr [rsi]
0x1800143ee  mov     [rsp+88h+var_38], r14
0x1800143f3  xor     edx, edx; perrinfo
0x1800143f5  xor     ecx, ecx; dwReserved
0x1800143f7  call    cs:__imp_SetErrorInfo
0x1800143fd  movups  xmm0, xmmword ptr cs:IID_IDBProperties.Data1
0x180014404  movdqu  xmmword ptr [rbx+60h], xmm0
0x180014409  mov     dword ptr [rbx+1074h], 0
0x180014413  lea     rax, [rbx+11E8h]
0x18001441a  lea     rcx, [rbx+11F8h]; this
0x180014421  mov     [rsp+88h+var_60], rax; struct CBidGenericBase *
0x180014426  mov     rax, [rsp+88h+arg_20]
0x18001442e  mov     [rsp+88h+var_68], rax; struct tagDBPROPSET **
0x180014433  mov     r9, r15; unsigned int *
0x180014436  mov     r8, r12; struct tagDBPROPIDSET *
0x180014439  mov     edx, r13d; unsigned int
0x18001443c  call    ?utlGetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z; CUtlProps::utlGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)
0x180014441  nop
0x180014442  jmp     short loc_180014461
0x180014444  jmp     short $+2
0x180014446  mov     rsi, [rsp+88h+var_40]
0x18001444b  mov     rdi, [rsp+88h+var_48]
0x180014450  mov     r14, [rsp+88h+var_50]
0x180014455  mov     eax, [rsp+88h+var_58]
0x180014459  mov     rbx, [rsp+88h+arg_0]
0x180014461  mov     edx, 0BB9h; unsigned int
0x180014466  mov     ecx, eax; int
0x180014468  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001446d  mov     r15d, eax
0x180014470  or      eax, 0FFFFFFFFh
0x180014473  add     [rsi], eax
0x180014475  add     [rdi], eax
0x180014477  jnz     short loc_18001447C
0x180014479  mov     [rbx+38h], eax
0x18001447c  mov     rcx, [r14]
0x18001447f  dec     dword ptr [rcx+30h]
0x180014482  add     rcx, 8; lpCriticalSection
0x180014486  call    cs:__imp_LeaveCriticalSection
0x18001448c  mov     eax, r15d
0x18001448f  lea     r11, [rsp+88h+var_28]
0x180014494  mov     rbx, [r11+38h]
0x180014498  mov     rsi, [r11+40h]
0x18001449c  mov     rsp, r11
0x18001449f  pop     r15
0x1800144a1  pop     r14
0x1800144a3  pop     r13
0x1800144a5  pop     r12
0x1800144a7  pop     rdi
0x1800144a8  retn
```
