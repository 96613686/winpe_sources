# WinPlatformGetRandom(uchar *,uint)

- ea: `0x180063bc0`
- end: `0x180063c62`
- name: `?WinPlatformGetRandom@@YAJPEAEI@Z`
- size: `162`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180063bc0`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x180063c29`
- `bcrypt!BCryptGenRandom` at `0x180063c29`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063c09`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063c09`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180063c43`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180063c43`

## pseudocode

```c
__int64 __fastcall WinPlatformGetRandom(PUCHAR pbBuffer, ULONG cbBuffer)
{
  NTSTATUS v5; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( cbBuffer && !pbBuffer )
    return 3221225485LL;
  v5 = 0;
  if ( cbBuffer )
  {
    v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", L"Microsoft Primitive Provider", 0);
    if ( v5 >= 0 )
      v5 = BCryptGenRandom(phAlgorithm, pbBuffer, cbBuffer, 0);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180063bc0  mov     [rsp+arg_0], rbx
0x180063bc5  mov     [rsp+arg_8], rsi
0x180063bca  push    rdi
0x180063bcb  sub     rsp, 20h
0x180063bcf  mov     [rsp+28h+phAlgorithm], 0
0x180063bd8  mov     edi, edx
0x180063bda  mov     rsi, rcx
0x180063bdd  test    edx, edx
0x180063bdf  jz      short loc_180063BED
0x180063be1  test    rcx, rcx
0x180063be4  jnz     short loc_180063BED
0x180063be6  mov     eax, 0C000000Dh
0x180063beb  jmp     short loc_180063C51
0x180063bed  xor     ebx, ebx
0x180063bef  test    edi, edi
0x180063bf1  jz      short loc_180063C4F
0x180063bf3  xor     r9d, r9d; dwFlags
0x180063bf6  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180063bfd  lea     rdx, aRng; "RNG"
0x180063c04  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x180063c09  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180063c10  nop     dword ptr [rax+rax+00h]
0x180063c15  mov     ebx, eax
0x180063c17  test    eax, eax
0x180063c19  js      short loc_180063C37
0x180063c1b  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180063c20  xor     r9d, r9d; dwFlags
0x180063c23  mov     r8d, edi; cbBuffer
0x180063c26  mov     rdx, rsi; pbBuffer
0x180063c29  call    cs:__imp_BCryptGenRandom
0x180063c30  nop     dword ptr [rax+rax+00h]
0x180063c35  mov     ebx, eax
0x180063c37  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180063c3c  test    rcx, rcx
0x180063c3f  jz      short loc_180063C4F
0x180063c41  xor     edx, edx; dwFlags
0x180063c43  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180063c4a  nop     dword ptr [rax+rax+00h]
0x180063c4f  mov     eax, ebx
0x180063c51  mov     rbx, [rsp+28h+arg_0]
0x180063c56  mov     rsi, [rsp+28h+arg_8]
0x180063c5b  add     rsp, 20h
0x180063c5f  pop     rdi
0x180063c60  retn
```
