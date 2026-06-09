# TpmApiOpenAlgorithmProvider(void * *,ushort const *)

- ea: `0x180076124`
- end: `0x1800761c2`
- name: `?TpmApiOpenAlgorithmProvider@@YAJPEAPEAXPEBG@Z`
- size: `158`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800764f4`

## callees

- `0x180074a48`
- `0x180076094`
- `0x180076124`
- `0x1800761c8`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180076164`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180076193`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180076164`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180076193`

## pseudocode

```c
__int64 __fastcall TpmApiOpenAlgorithmProvider(BCRYPT_ALG_HANDLE *phAlgorithm, LPCWSTR pszAlgId)
{
  NTSTATUS v4; // edi
  unsigned int v6; // [rsp+40h] [rbp+18h] BYREF
  LPCWSTR pszImplementation; // [rsp+48h] [rbp+20h] BYREF

  pszImplementation = 0;
  v6 = 0;
  TpmApiRegistryGetAlgorithmProvider((unsigned __int16 **)&pszImplementation, &v6);
  v4 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, pszImplementation, 0);
  if ( v4 < 0 && pszImplementation && TpmApiDefaultToExistingProviders() )
    v4 = BCryptOpenAlgorithmProvider(phAlgorithm, pszAlgId, 0, 0);
  TpmApiCallbackFree(0, 0, pszImplementation);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180076124  mov     rax, rsp
0x180076127  mov     [rax+8], rbp
0x18007612b  mov     [rax+10h], rsi
0x18007612f  push    rdi
0x180076130  sub     rsp, 20h
0x180076134  mov     rsi, rdx
0x180076137  mov     qword ptr [rax+20h], 0
0x18007613f  mov     rbp, rcx
0x180076142  mov     dword ptr [rax+18h], 0
0x180076149  lea     rdx, [rax+18h]; unsigned int *
0x18007614d  lea     rcx, [rax+20h]; unsigned __int16 **
0x180076151  call    ?TpmApiRegistryGetAlgorithmProvider@@YAJPEAPEAGPEAK@Z; TpmApiRegistryGetAlgorithmProvider(ushort * *,ulong *)
0x180076156  mov     r8, [rsp+28h+pszImplementation]; pszImplementation
0x18007615b  xor     r9d, r9d; dwFlags
0x18007615e  mov     rdx, rsi; pszAlgId
0x180076161  mov     rcx, rbp; phAlgorithm
0x180076164  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18007616b  nop     dword ptr [rax+rax+00h]
0x180076170  mov     edi, eax
0x180076172  test    eax, eax
0x180076174  jns     short loc_1800761A1
0x180076176  cmp     [rsp+28h+pszImplementation], 0
0x18007617c  jz      short loc_1800761A1
0x18007617e  call    ?TpmApiDefaultToExistingProviders@@YAEXZ; TpmApiDefaultToExistingProviders(void)
0x180076183  test    al, al
0x180076185  jz      short loc_1800761A1
0x180076187  xor     r9d, r9d; dwFlags
0x18007618a  xor     r8d, r8d; pszImplementation
0x18007618d  mov     rdx, rsi; pszAlgId
0x180076190  mov     rcx, rbp; phAlgorithm
0x180076193  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18007619a  nop     dword ptr [rax+rax+00h]
0x18007619f  mov     edi, eax
0x1800761a1  mov     r8, [rsp+28h+pszImplementation]
0x1800761a6  xor     edx, edx
0x1800761a8  xor     ecx, ecx
0x1800761aa  call    TpmApiCallbackFree
0x1800761af  mov     rbp, [rsp+28h+arg_0]
0x1800761b4  mov     eax, edi
0x1800761b6  mov     rsi, [rsp+28h+arg_8]
0x1800761bb  add     rsp, 20h
0x1800761bf  pop     rdi
0x1800761c0  retn
```
