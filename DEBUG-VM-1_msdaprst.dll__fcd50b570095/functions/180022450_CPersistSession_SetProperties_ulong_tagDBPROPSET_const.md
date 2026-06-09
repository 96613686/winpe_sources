# CPersistSession::SetProperties(ulong,tagDBPROPSET * const)

- ea: `0x180022450`
- end: `0x180022558`
- name: `?SetProperties@CPersistSession@@UEAAJKQEAUtagDBPROPSET@@@Z`
- size: `264`
- prototype: `int(CPersistSession *__hidden this, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180015fb4`
- `0x180022450`
- `0x18002ca58`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002248f`
- `KERNEL32!GetCurrentThreadId` at `0x18002248f`
- `KERNEL32!LeaveCriticalSection` at `0x18002253a`
- `KERNEL32!LeaveCriticalSection` at `0x18002253a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800224af`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800224af`
- `MSDART!UMSEnterCSWraper` at `0x18002247b`
- `MSDART!UMSEnterCSWraper` at `0x18002247b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistSession::SetProperties(
        CPersistSession *this,
        unsigned int a2,
        struct tagDBPROPSET *const a3)
{
  CPersistSession *v5; // rbx
  _QWORD *v6; // rsi
  _DWORD *v7; // rdi
  _DWORD *v8; // r14
  unsigned int v9; // edx
  int v10; // eax
  unsigned int v11; // r15d
  __int64 v13; // rcx
  int v15; // [rsp+30h] [rbp-58h] BYREF
  char *v16; // [rsp+38h] [rbp-50h]
  _DWORD *v17; // [rsp+40h] [rbp-48h]
  _DWORD *v18; // [rsp+48h] [rbp-40h]
  _QWORD *v19; // [rsp+50h] [rbp-38h]
  int v23; // [rsp+A8h] [rbp+20h]
  int v24; // [rsp+A8h] [rbp+20h]

  v5 = this;
  v6 = (_QWORD *)((char *)this + 32);
  v16 = (char *)this + 32;
  UMSEnterCSWraper((char *)this + 32);
  v7 = (_DWORD *)((char *)v5 + 44);
  v17 = (_DWORD *)((char *)v5 + 44);
  if ( !*((_DWORD *)v5 + 11) )
    *((_DWORD *)v5 + 10) = GetCurrentThreadId();
  ++*v7;
  v8 = (_DWORD *)((char *)v5 + 48);
  v18 = (_DWORD *)((char *)v5 + 48);
  ++*((_DWORD *)v5 + 12);
  v19 = v6;
  SetErrorInfo(0, 0);
  try
  {
    *((GUID *)v5 + 5) = IID_ISessionProperties;
    *((_DWORD *)v5 + 1049) = 0;
    v10 = CUtlProps::utlSetProperties(
            (CPersistSession *)((char *)v5 + 4536),
            v9,
            a2,
            a3,
            (CPersistSession *)((char *)v5 + 4520),
            0);
  }
  catch ( long v15 )
  {
    v23 = v15;
    v8 = v18;
    v7 = v17;
    v6 = v16;
    v10 = v23;
    v5 = this;
  }
  catch ( ... )
  {
    v24 = -2147467259;
    v8 = v18;
    v7 = v17;
    v6 = v16;
    v10 = v24;
    v5 = this;
  }
  v11 = Exit(v10, 0xBB8u);
  --*v8;
  if ( (*v7)-- == 1 )
    *((_DWORD *)v5 + 10) = -1;
  v13 = *v6;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v11;
}

```

## disassembly

```asm
0x180022450  mov     [rsp+arg_8], rbx
0x180022455  mov     [rsp+arg_0], rcx
0x18002245a  push    rsi
0x18002245b  push    rdi
0x18002245c  push    r12
0x18002245e  push    r14
0x180022460  push    r15
0x180022462  sub     rsp, 60h
0x180022466  mov     r15, r8
0x180022469  mov     r12d, edx
0x18002246c  mov     rbx, rcx
0x18002246f  lea     rsi, [rcx+20h]
0x180022473  mov     [rsp+88h+var_50], rsi
0x180022478  mov     rcx, rsi
0x18002247b  call    cs:__imp_UMSEnterCSWraper
0x180022481  lea     rdi, [rbx+2Ch]
0x180022485  mov     [rsp+88h+var_48], rdi
0x18002248a  cmp     dword ptr [rdi], 0
0x18002248d  jnz     short loc_180022498
0x18002248f  call    cs:__imp_GetCurrentThreadId
0x180022495  mov     [rbx+28h], eax
0x180022498  inc     dword ptr [rdi]
0x18002249a  lea     r14, [rbx+30h]
0x18002249e  mov     [rsp+88h+var_40], r14
0x1800224a3  inc     dword ptr [r14]
0x1800224a6  mov     [rsp+88h+var_38], rsi
0x1800224ab  xor     edx, edx; perrinfo
0x1800224ad  xor     ecx, ecx; dwReserved
0x1800224af  call    cs:__imp_SetErrorInfo
0x1800224b5  movups  xmm0, xmmword ptr cs:IID_ISessionProperties.Data1
0x1800224bc  movdqu  xmmword ptr [rbx+50h], xmm0
0x1800224c1  mov     dword ptr [rbx+1064h], 0
0x1800224cb  lea     rax, [rbx+11A8h]
0x1800224d2  lea     rcx, [rbx+11B8h]; this
0x1800224d9  mov     [rsp+88h+var_60], 0; int
0x1800224e1  mov     [rsp+88h+var_68], rax; struct CBidGenericBase *
0x1800224e6  mov     r9, r15; struct tagDBPROPSET *
0x1800224e9  mov     r8d, r12d; unsigned int
0x1800224ec  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x1800224f1  nop
0x1800224f2  jmp     short loc_180022514
0x1800224f4  jmp     short $+2
0x1800224f6  mov     r14, [rsp+88h+var_40]
0x1800224fb  mov     rdi, [rsp+88h+var_48]
0x180022500  mov     rsi, [rsp+88h+var_50]
0x180022505  mov     eax, [rsp+88h+arg_18]
0x18002250c  mov     rbx, [rsp+88h+arg_0]
0x180022514  mov     edx, 0BB8h; unsigned int
0x180022519  mov     ecx, eax; int
0x18002251b  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180022520  mov     r15d, eax
0x180022523  or      eax, 0FFFFFFFFh
0x180022526  add     [r14], eax
0x180022529  add     [rdi], eax
0x18002252b  jnz     short loc_180022530
0x18002252d  mov     [rbx+28h], eax
0x180022530  mov     rcx, [rsi]
0x180022533  dec     dword ptr [rcx+30h]
0x180022536  add     rcx, 8; lpCriticalSection
0x18002253a  call    cs:__imp_LeaveCriticalSection
0x180022540  mov     eax, r15d
0x180022543  mov     rbx, [rsp+88h+arg_8]
0x18002254b  add     rsp, 60h
0x18002254f  pop     r15
0x180022551  pop     r14
0x180022553  pop     r12
0x180022555  pop     rdi
0x180022556  pop     rsi
0x180022557  retn
```
