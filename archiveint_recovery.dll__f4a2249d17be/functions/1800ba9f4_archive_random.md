# archive_random

- ea: `0x1800ba9f4`
- end: `0x1800baa68`
- name: `archive_random`
- size: `116`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18010f448`
- `0x180115c40`
- `0x180116488`
- `0x1801165c4`
- `0x180116778`

## callees

- `0x1800ba9f4`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800baa1f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800baa1f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800baa46`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800baa46`
- `bcrypt!BCryptGenRandom` at `0x1800baa37`
- `bcrypt!BCryptGenRandom` at `0x1800baa37`

## pseudocode

```c
__int64 __fastcall archive_random(PUCHAR pbBuffer, ULONG cbBuffer)
{
  NTSTATUS v4; // ebx
  __int64 result; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0) < 0 )
    return 4294967271LL;
  v4 = BCryptGenRandom(phAlgorithm, pbBuffer, cbBuffer, 0);
  BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  result = 0;
  if ( v4 < 0 )
    return 4294967271LL;
  return result;
}

```

## disassembly

```asm
0x1800ba9f4  mov     [rsp+arg_0], rbx
0x1800ba9f9  push    rdi
0x1800ba9fa  sub     rsp, 20h
0x1800ba9fe  mov     rbx, rdx
0x1800baa01  mov     [rsp+28h+phAlgorithm], 0
0x1800baa0a  mov     rdi, rcx
0x1800baa0d  lea     rdx, pszAlgId; "RNG"
0x1800baa14  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x1800baa19  xor     r9d, r9d; dwFlags
0x1800baa1c  xor     r8d, r8d; pszImplementation
0x1800baa1f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800baa25  test    eax, eax
0x1800baa27  js      short loc_1800BAA58
0x1800baa29  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1800baa2e  mov     r8d, ebx; cbBuffer
0x1800baa31  xor     r9d, r9d; dwFlags
0x1800baa34  mov     rdx, rdi; pbBuffer
0x1800baa37  call    cs:__imp_BCryptGenRandom
0x1800baa3d  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1800baa42  xor     edx, edx; dwFlags
0x1800baa44  mov     ebx, eax
0x1800baa46  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800baa4c  xor     eax, eax
0x1800baa4e  test    ebx, ebx
0x1800baa50  lea     ecx, [rax-19h]
0x1800baa53  cmovs   eax, ecx
0x1800baa56  jmp     short loc_1800BAA5D
0x1800baa58  mov     eax, 0FFFFFFE7h
0x1800baa5d  mov     rbx, [rsp+28h+arg_0]
0x1800baa62  add     rsp, 20h
0x1800baa66  pop     rdi
0x1800baa67  retn
```
