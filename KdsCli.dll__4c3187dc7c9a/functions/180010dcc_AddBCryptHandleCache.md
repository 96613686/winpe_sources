# AddBCryptHandleCache

- ea: `0x180010dcc`
- end: `0x180010f27`
- name: `AddBCryptHandleCache`
- size: `347`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010f9c`

## callees

- `0x180010920`
- `0x180010950`
- `0x180010dcc`
- `0x180010f30`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010e07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180010e07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010ef0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180010ef0`

## string_xrefs

- `0x180010e51`: `onecore\ds\security\keyman\sidkeyprov\common\bcryptprovhandlecache.cxx`

## pseudocode

```c
__int64 __fastcall AddBCryptHandleCache(_WORD *Src, __int64 a2, unsigned int a3, int *a4)
{
  _QWORD *v4; // rdi
  int v6; // ebx
  _QWORD *v7; // rsi
  __int64 v8; // rbp
  int v11; // r15d
  __int64 v12; // rcx
  unsigned int v13; // r9d
  unsigned __int64 v14; // rbp
  void *v15; // rax
  __int64 v16; // rcx

  v4 = 0;
  v6 = 0;
  v7 = 0;
  v8 = -1;
  do
    ++v8;
  while ( Src[v8] );
  v11 = 0;
  AcquireSRWLockExclusive(&SRWLock);
  if ( !FindBCryptProvHandle(v12, Src, a3) )
  {
    v4 = SIDKeyProvAlloc(0x18u);
    if ( !v4 )
    {
      v6 = -2147024882;
      goto LABEL_14;
    }
    v7 = SIDKeyProvAlloc(0x18u);
    if ( !v7 )
    {
      v13 = 113;
LABEL_8:
      v6 = -2147024882;
      SidKeyDebugTraceError(
        0x8007000E,
        "hr",
        "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\bcryptprovhandlecache.cxx",
        v13);
      goto LABEL_14;
    }
    v14 = 2 * v8 + 2;
    *v4 = a2;
    v15 = SIDKeyProvAlloc(v14);
    v4[1] = v15;
    if ( !v15 )
    {
      v13 = 123;
      goto LABEL_8;
    }
    memcpy_0(v15, Src, v14);
    *v7 = v4;
    *((_DWORD *)v4 + 4) = a3;
    v16 = qword_180023530;
    if ( *(__int64 **)(qword_180023530 + 8) != &qword_180023530 )
      __fastfail(3u);
    v11 = 1;
    v7[1] = qword_180023530;
    v7[2] = &qword_180023530;
    *(_QWORD *)(v16 + 8) = v7 + 1;
    qword_180023530 = (__int64)(v7 + 1);
  }
LABEL_14:
  *a4 = v11;
  ReleaseSRWLockExclusive(&SRWLock);
  if ( v6 < 0 )
  {
    if ( v4 )
      SIDKeyProvFree(v4);
    if ( v7 )
      SIDKeyProvFree(v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010dcc  mov     [rsp+arg_18], r9
0x180010dd1  push    rbx
0x180010dd2  push    rbp
0x180010dd3  push    rsi
0x180010dd4  push    rdi
0x180010dd5  push    r12
0x180010dd7  push    r13
0x180010dd9  push    r14
0x180010ddb  push    r15
0x180010ddd  sub     rsp, 28h
0x180010de1  xor     edi, edi
0x180010de3  mov     r12d, r8d
0x180010de6  mov     ebx, edi
0x180010de8  mov     esi, edi
0x180010dea  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180010dee  mov     r13, rdx
0x180010df1  mov     r14, rcx
0x180010df4  inc     rbp
0x180010df7  cmp     [rcx+rbp*2], di
0x180010dfb  jnz     short loc_180010DF4
0x180010dfd  lea     rcx, SRWLock; SRWLock
0x180010e04  mov     r15d, edi
0x180010e07  call    cs:__imp_AcquireSRWLockExclusive
0x180010e0d  mov     r8d, r12d
0x180010e10  mov     rdx, r14
0x180010e13  call    FindBCryptProvHandle
0x180010e18  test    rax, rax
0x180010e1b  jnz     loc_180010EDE
0x180010e21  lea     ecx, [rax+18h]; unsigned __int64
0x180010e24  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180010e29  mov     rdi, rax
0x180010e2c  test    rax, rax
0x180010e2f  jnz     short loc_180010E3B
0x180010e31  mov     ebx, 8007000Eh
0x180010e36  jmp     loc_180010EDE
0x180010e3b  mov     ecx, 18h; unsigned __int64
0x180010e40  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180010e45  mov     rsi, rax
0x180010e48  test    rax, rax
0x180010e4b  jnz     short loc_180010E70
0x180010e4d  lea     r9d, [rax+71h]; unsigned int
0x180010e51  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010e58  mov     ecx, 8007000Eh; unsigned int
0x180010e5d  lea     rdx, aHr; "hr"
0x180010e64  mov     ebx, 8007000Eh
0x180010e69  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010e6e  jmp     short loc_180010EDE
0x180010e70  lea     rbp, ds:2[rbp*2]
0x180010e78  mov     [rdi], r13
0x180010e7b  mov     rcx, rbp; unsigned __int64
0x180010e7e  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180010e83  mov     [rdi+8], rax
0x180010e87  test    rax, rax
0x180010e8a  jnz     short loc_180010E92
0x180010e8c  lea     r9d, [rax+7Bh]
0x180010e90  jmp     short loc_180010E51
0x180010e92  mov     r8, rbp; Size
0x180010e95  mov     rdx, r14; Src
0x180010e98  mov     rcx, rax; void *
0x180010e9b  call    memcpy_0
0x180010ea0  mov     [rsi], rdi
0x180010ea3  lea     rdx, qword_180023530
0x180010eaa  mov     [rdi+10h], r12d
0x180010eae  mov     rcx, cs:qword_180023530
0x180010eb5  cmp     [rcx+8], rdx
0x180010eb9  jz      short loc_180010EC2
0x180010ebb  mov     ecx, 3
0x180010ec0  int     29h; Win8: RtlFailFast(ecx)
0x180010ec2  lea     rax, [rsi+8]
0x180010ec6  mov     r15d, 1
0x180010ecc  mov     [rax], rcx
0x180010ecf  mov     [rax+8], rdx
0x180010ed3  mov     [rcx+8], rax
0x180010ed7  mov     cs:qword_180023530, rax
0x180010ede  mov     rax, [rsp+68h+arg_18]
0x180010ee6  lea     rcx, SRWLock; SRWLock
0x180010eed  mov     [rax], r15d
0x180010ef0  call    cs:__imp_ReleaseSRWLockExclusive
0x180010ef6  test    ebx, ebx
0x180010ef8  jns     short loc_180010F14
0x180010efa  test    rdi, rdi
0x180010efd  jz      short loc_180010F07
0x180010eff  mov     rcx, rdi; lpMem
0x180010f02  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180010f07  test    rsi, rsi
0x180010f0a  jz      short loc_180010F14
0x180010f0c  mov     rcx, rsi; lpMem
0x180010f0f  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180010f14  mov     eax, ebx
0x180010f16  add     rsp, 28h
0x180010f1a  pop     r15
0x180010f1c  pop     r14
0x180010f1e  pop     r13
0x180010f20  pop     r12
0x180010f22  pop     rdi
0x180010f23  pop     rsi
0x180010f24  pop     rbp
0x180010f25  pop     rbx
0x180010f26  retn
```
