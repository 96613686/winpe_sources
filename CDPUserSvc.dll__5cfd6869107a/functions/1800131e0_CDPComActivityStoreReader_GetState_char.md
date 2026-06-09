# CDPComActivityStoreReader::GetState(char * *)

- ea: `0x1800131e0`
- end: `0x180013338`
- name: `?GetState@CDPComActivityStoreReader@@UEAAJPEAPEAD@Z`
- size: `344`
- prototype: `__int64 __fastcall(CDPComActivityStoreReader *__hidden this, char **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800131e0`
- `0x1800250a4`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18001329d`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18001329d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800132ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013330`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800132ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180013330`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013208`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180013208`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013286`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013286`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDPComActivityStoreReader::GetState(RTL_SRWLOCK *this, char **a2)
{
  RTL_SRWLOCK *v4; // rdi
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // rax
  const char *v10; // rbx
  __int64 v11; // rcx
  rsize_t v12; // r15
  char *v13; // rax
  char *v14; // rsi
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+38h] [rbp-8h] BYREF
  int v20; // [rsp+3Ch] [rbp-4h] BYREF

  v18 = 0;
  v4 = this + 9;
  AcquireSRWLockShared(this + 9);
  v5 = (*(__int64 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)this[7].Ptr + 32LL))(this[7].Ptr, &v18);
  if ( v5 < 0 )
  {
    v19 = v5;
    v20 = 128;
    Log<long &,char const (&)[33],int>(v7, v6, &v19, v8, &v20);
    if ( v4 )
      ReleaseSRWLockShared(v4);
    v17 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v19;
  }
  else
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 24LL))(v18);
    v10 = (const char *)v9;
    if ( a2 )
    {
      *a2 = 0;
      if ( v9 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_BYTE *)(v9 + v11) );
        v12 = v11 + 1;
        v13 = (char *)CoTaskMemAlloc(v11 + 1);
        v14 = v13;
        if ( v13 )
        {
          strcpy_s(v13, v12, v10);
          *a2 = v14;
        }
      }
    }
    if ( v4 )
      ReleaseSRWLockShared(v4);
    v15 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800131e0  mov     [rsp-28h+arg_10], rbx
0x1800131e5  push    rbp
0x1800131e6  push    rsi
0x1800131e7  push    rdi
0x1800131e8  push    r14
0x1800131ea  push    r15
0x1800131ec  mov     rbp, rsp
0x1800131ef  sub     rsp, 40h
0x1800131f3  mov     r14, rdx
0x1800131f6  mov     rbx, rcx
0x1800131f9  mov     [rbp+var_10], 0
0x180013201  lea     rdi, [rcx+48h]
0x180013205  mov     rcx, rdi; SRWLock
0x180013208  call    cs:__imp_AcquireSRWLockShared
0x18001320e  mov     rbx, [rbx+38h]
0x180013212  mov     rax, [rbx]
0x180013215  mov     rsi, [rax+20h]
0x180013219  mov     rcx, [rbp+var_10]
0x18001321d  test    rcx, rcx
0x180013220  jz      short loc_180013237
0x180013222  mov     [rbp+var_10], 0
0x18001322a  mov     rax, [rcx]
0x18001322d  mov     rax, [rax+10h]
0x180013231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013236  nop
0x180013237  lea     rdx, [rbp+var_10]
0x18001323b  mov     rcx, rbx
0x18001323e  mov     rax, rsi
0x180013241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013246  test    eax, eax
0x180013248  js      loc_1800132E9
0x18001324e  mov     rcx, [rbp+var_10]
0x180013252  mov     rax, [rcx]
0x180013255  mov     rax, [rax+18h]
0x180013259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001325e  mov     rbx, rax
0x180013261  test    r14, r14
0x180013264  jz      short loc_1800132A6
0x180013266  mov     qword ptr [r14], 0
0x18001326d  test    rax, rax
0x180013270  jz      short loc_1800132A6
0x180013272  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180013276  inc     rcx
0x180013279  cmp     byte ptr [rax+rcx], 0
0x18001327d  jnz     short loc_180013276
0x18001327f  lea     r15, [rcx+1]
0x180013283  mov     rcx, r15; cb
0x180013286  call    cs:__imp_CoTaskMemAlloc
0x18001328c  mov     rsi, rax
0x18001328f  test    rax, rax
0x180013292  jz      short loc_1800132A6
0x180013294  mov     r8, rbx; Source
0x180013297  mov     rdx, r15; SizeInBytes
0x18001329a  mov     rcx, rax; Destination
0x18001329d  call    cs:__imp_strcpy_s
0x1800132a3  mov     [r14], rsi
0x1800132a6  test    rdi, rdi
0x1800132a9  jz      short loc_1800132B5
0x1800132ab  mov     rcx, rdi; SRWLock
0x1800132ae  call    cs:__imp_ReleaseSRWLockShared
0x1800132b4  nop
0x1800132b5  mov     rcx, [rbp+var_10]
0x1800132b9  test    rcx, rcx
0x1800132bc  jz      short loc_1800132D3
0x1800132be  mov     [rbp+var_10], 0
0x1800132c6  mov     rax, [rcx]
0x1800132c9  mov     rax, [rax+10h]
0x1800132cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132d2  nop
0x1800132d3  xor     eax, eax
0x1800132d5  mov     rbx, [rsp+40h+arg_10]
0x1800132dd  add     rsp, 40h
0x1800132e1  pop     r15
0x1800132e3  pop     r14
0x1800132e5  pop     rdi
0x1800132e6  pop     rsi
0x1800132e7  pop     rbp
0x1800132e8  retn
0x1800132e9  mov     [rbp+var_8], eax
0x1800132ec  mov     [rbp+var_4], 80h
0x1800132f3  lea     rax, [rbp+var_4]
0x1800132f7  mov     [rsp+40h+var_20], rax
0x1800132fc  lea     r8, [rbp+var_8]
0x180013300  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x180013305  test    rdi, rdi
0x180013308  jnz     short loc_18001332D
0x18001330a  mov     rcx, [rbp+var_10]
0x18001330e  test    rcx, rcx
0x180013311  jz      short loc_180013328
0x180013313  mov     [rbp+var_10], 0
0x18001331b  mov     rdx, [rcx]
0x18001331e  mov     rax, [rdx+10h]
0x180013322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013327  nop
0x180013328  mov     eax, [rbp+var_8]
0x18001332b  jmp     short loc_1800132D5
0x18001332d  mov     rcx, rdi; SRWLock
0x180013330  call    cs:__imp_ReleaseSRWLockShared
0x180013336  jmp     short loc_18001330A
```
