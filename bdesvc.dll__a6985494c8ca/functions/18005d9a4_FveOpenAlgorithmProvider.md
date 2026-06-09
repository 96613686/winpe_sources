# FveOpenAlgorithmProvider

- ea: `0x18005d9a4`
- end: `0x18005da57`
- name: `FveOpenAlgorithmProvider`
- size: `179`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE *phAlgorithm)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18005dd18`

## callees

- `0x18005c864`
- `0x18005d920`
- `0x18005d9a4`
- `0x18005da60`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005d9ec`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005da22`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005d9ec`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005da22`

## pseudocode

```c
__int64 __fastcall FveOpenAlgorithmProvider(BCRYPT_ALG_HANDLE *phAlgorithm)
{
  NTSTATUS v2; // edi
  LPCWSTR pszImplementation; // [rsp+38h] [rbp+10h] BYREF
  unsigned int v5; // [rsp+40h] [rbp+18h] BYREF

  pszImplementation = 0;
  v5 = 0;
  FveRegistryGetAlgorithmProvider(&pszImplementation, &v5);
  v2 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA384", pszImplementation, 0x20u);
  if ( v2 < 0 )
  {
    if ( !pszImplementation )
      return (unsigned int)v2;
    if ( (unsigned __int8)FveDefaultToExistingProviders() )
      v2 = BCryptOpenAlgorithmProvider(phAlgorithm, L"SHA384", 0, 0x20u);
  }
  if ( pszImplementation )
    FveLibFreeWithTag(pszImplementation, v5, 0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005d9a4  mov     rax, rsp
0x18005d9a7  mov     [rax+8], rsi
0x18005d9ab  mov     [rax+18h], r8d
0x18005d9af  mov     [rax+10h], rdx
0x18005d9b3  push    rdi
0x18005d9b4  sub     rsp, 20h
0x18005d9b8  mov     rsi, rcx
0x18005d9bb  mov     qword ptr [rax+10h], 0
0x18005d9c3  lea     rcx, [rax+10h]
0x18005d9c7  mov     dword ptr [rax+18h], 0
0x18005d9ce  lea     rdx, [rax+18h]
0x18005d9d2  call    FveRegistryGetAlgorithmProvider
0x18005d9d7  mov     r8, [rsp+28h+pszImplementation]; pszImplementation
0x18005d9dc  lea     rdx, pszAlgId; "SHA384"
0x18005d9e3  mov     r9d, 20h ; ' '; dwFlags
0x18005d9e9  mov     rcx, rsi; phAlgorithm
0x18005d9ec  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18005d9f3  nop     dword ptr [rax+rax+00h]
0x18005d9f8  mov     edi, eax
0x18005d9fa  test    eax, eax
0x18005d9fc  jns     short loc_18005DA30
0x18005d9fe  cmp     [rsp+28h+pszImplementation], 0
0x18005da04  jz      short loc_18005DA49
0x18005da06  call    FveDefaultToExistingProviders
0x18005da0b  test    al, al
0x18005da0d  jz      short loc_18005DA30
0x18005da0f  mov     r9d, 20h ; ' '; dwFlags
0x18005da15  lea     rdx, pszAlgId; "SHA384"
0x18005da1c  xor     r8d, r8d; pszImplementation
0x18005da1f  mov     rcx, rsi; phAlgorithm
0x18005da22  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18005da29  nop     dword ptr [rax+rax+00h]
0x18005da2e  mov     edi, eax
0x18005da30  cmp     [rsp+28h+pszImplementation], 0
0x18005da36  jz      short loc_18005DA49
0x18005da38  mov     edx, [rsp+28h+arg_10]
0x18005da3c  xor     r8d, r8d
0x18005da3f  mov     rcx, [rsp+28h+pszImplementation]
0x18005da44  call    FveLibFreeWithTag
0x18005da49  mov     rsi, [rsp+28h+arg_0]
0x18005da4e  mov     eax, edi
0x18005da50  add     rsp, 20h
0x18005da54  pop     rdi
0x18005da55  retn
```
