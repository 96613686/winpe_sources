# GetCachedBCryptHandle(ushort const *,void * *,ulong,int *)

- ea: `0x180010f9c`
- end: `0x1800110da`
- name: `?GetCachedBCryptHandle@@YAJPEBGPEAPEAXKPEAH@Z`
- size: `318`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, void **, unsigned int, int *)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b758`
- `0x18000d6a0`
- `0x18000dc90`
- `0x18000dfc0`
- `0x18000e540`
- `0x1800173d8`
- `0x180017638`

## callees

- `0x180010dcc`
- `0x180010f30`
- `0x180010f9c`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010fe8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180010fe8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180010fcd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180010fcd`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001100c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001100c`
- `bcrypt!BCryptGetProperty` at `0x18001105d`
- `bcrypt!BCryptGetProperty` at `0x18001105d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800110c3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800110c3`

## string_xrefs

- `0x18001101e`: `onecore\ds\security\keyman\sidkeyprov\common\bcryptprovhandlecache.cxx`
- `0x18001107c`: `onecore\ds\security\keyman\sidkeyprov\common\bcryptprovhandlecache.cxx`

## pseudocode

```c
__int64 __fastcall GetCachedBCryptHandle(WCHAR *Src, void **a2, unsigned int a3, int *a4)
{
  unsigned int v4; // ebx
  __int64 v8; // rcx
  void *BCryptProvHandle; // rdi
  NTSTATUS Property; // edi
  unsigned int v11; // r9d
  UCHAR pbOutput[4]; // [rsp+30h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+34h] [rbp-Ch] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-8h] BYREF

  v4 = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  AcquireSRWLockShared(&SRWLock);
  BCryptProvHandle = (void *)FindBCryptProvHandle(v8, Src, a3);
  ReleaseSRWLockShared(&SRWLock);
  phAlgorithm = BCryptProvHandle;
  if ( BCryptProvHandle )
  {
    *a2 = BCryptProvHandle;
    return v4;
  }
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, Src, 0, 0);
  if ( Property < 0 )
  {
    v11 = 189;
LABEL_5:
    SidKeyDebugTraceError(
      Property,
      "ntStatus",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\bcryptprovhandlecache.cxx",
      v11);
    v4 = Property | 0x10000000;
    goto LABEL_11;
  }
  Property = BCryptGetProperty(phAlgorithm, L"PrimitiveType", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v11 = 203;
    goto LABEL_5;
  }
  if ( *(_DWORD *)pbOutput == a3 )
  {
    AddBCryptHandleCache(Src);
    *a2 = phAlgorithm;
    phAlgorithm = 0;
  }
  else
  {
    v4 = -2146893821;
    SidKeyDebugTraceError(
      0x80090003,
      "hr",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\bcryptprovhandlecache.cxx",
      0xD4u);
  }
LABEL_11:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v4;
}

```

## disassembly

```asm
0x180010f9c  push    rbp
0x180010f9e  push    rbx
0x180010f9f  push    rsi
0x180010fa0  push    rdi
0x180010fa1  push    r12
0x180010fa3  push    r14
0x180010fa5  push    r15
0x180010fa7  mov     rbp, rsp
0x180010faa  sub     rsp, 40h
0x180010fae  xor     ebx, ebx
0x180010fb0  mov     r15, rcx
0x180010fb3  lea     rcx, SRWLock; SRWLock
0x180010fba  mov     [rbp+phAlgorithm], rbx
0x180010fbe  mov     dword ptr [rbp+pbOutput], ebx
0x180010fc1  mov     r12, r9
0x180010fc4  mov     [rbp+var_C], ebx
0x180010fc7  mov     esi, r8d
0x180010fca  mov     r14, rdx
0x180010fcd  call    cs:__imp_AcquireSRWLockShared
0x180010fd3  mov     r8d, esi
0x180010fd6  mov     rdx, r15
0x180010fd9  call    FindBCryptProvHandle
0x180010fde  lea     rcx, SRWLock; SRWLock
0x180010fe5  mov     rdi, rax
0x180010fe8  call    cs:__imp_ReleaseSRWLockShared
0x180010fee  mov     [rbp+phAlgorithm], rdi
0x180010ff2  test    rdi, rdi
0x180010ff5  jz      short loc_180010FFF
0x180010ff7  mov     [r14], rdi
0x180010ffa  jmp     loc_1800110C9
0x180010fff  xor     r9d, r9d; dwFlags
0x180011002  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180011006  xor     r8d, r8d; pszImplementation
0x180011009  mov     rdx, r15; pszAlgId
0x18001100c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180011012  mov     edi, eax
0x180011014  test    eax, eax
0x180011016  jns     short loc_18001103B
0x180011018  mov     r9d, 0BDh; unsigned int
0x18001101e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180011025  mov     ecx, edi; unsigned int
0x180011027  lea     rdx, aNtstatus; "ntStatus"
0x18001102e  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180011033  mov     ebx, edi
0x180011035  bts     ebx, 1Ch
0x180011039  jmp     short loc_1800110B8
0x18001103b  mov     rcx, [rbp+phAlgorithm]; hObject
0x18001103f  lea     rax, [rbp+var_C]
0x180011043  mov     [rsp+40h+dwFlags], ebx; dwFlags
0x180011047  lea     r8, [rbp+pbOutput]; pbOutput
0x18001104b  mov     r9d, 4; cbOutput
0x180011051  mov     [rsp+40h+pcbResult], rax; pcbResult
0x180011056  lea     rdx, aPrimitivetype; "PrimitiveType"
0x18001105d  call    cs:__imp_BCryptGetProperty
0x180011063  mov     edi, eax
0x180011065  test    eax, eax
0x180011067  jns     short loc_180011071
0x180011069  mov     r9d, 0CBh
0x18001106f  jmp     short loc_18001101E
0x180011071  cmp     dword ptr [rbp+pbOutput], esi
0x180011074  jz      short loc_18001109B
0x180011076  mov     r9d, 0D4h; unsigned int
0x18001107c  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180011083  lea     rdx, aHr; "hr"
0x18001108a  mov     ecx, 80090003h; unsigned int
0x18001108f  mov     ebx, 80090003h
0x180011094  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180011099  jmp     short loc_1800110B8
0x18001109b  mov     rdx, [rbp+phAlgorithm]
0x18001109f  mov     r9, r12
0x1800110a2  mov     r8d, esi
0x1800110a5  mov     rcx, r15; Src
0x1800110a8  call    AddBCryptHandleCache
0x1800110ad  mov     rcx, [rbp+phAlgorithm]
0x1800110b1  mov     [r14], rcx
0x1800110b4  mov     [rbp+phAlgorithm], rbx
0x1800110b8  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800110bc  test    rcx, rcx
0x1800110bf  jz      short loc_1800110C9
0x1800110c1  xor     edx, edx; dwFlags
0x1800110c3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800110c9  mov     eax, ebx
0x1800110cb  add     rsp, 40h
0x1800110cf  pop     r15
0x1800110d1  pop     r14
0x1800110d3  pop     r12
0x1800110d5  pop     rdi
0x1800110d6  pop     rsi
0x1800110d7  pop     rbx
0x1800110d8  pop     rbp
0x1800110d9  retn
```
