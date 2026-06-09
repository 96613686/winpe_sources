# WinPlatformGetRandom(uchar *,uint)

- ea: `0x180040150`
- end: `0x1800401df`
- name: `?WinPlatformGetRandom@@YAJPEAEI@Z`
- size: `143`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180040150`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800401b3`
- `bcrypt!BCryptGenRandom` at `0x1800401b3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800401c7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800401c7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180040199`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180040199`

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
0x180040150  mov     [rsp+arg_0], rbx
0x180040155  mov     [rsp+arg_8], rsi
0x18004015a  push    rdi
0x18004015b  sub     rsp, 20h
0x18004015f  mov     [rsp+28h+phAlgorithm], 0
0x180040168  mov     edi, edx
0x18004016a  mov     rsi, rcx
0x18004016d  test    edx, edx
0x18004016f  jz      short loc_18004017D
0x180040171  test    rcx, rcx
0x180040174  jnz     short loc_18004017D
0x180040176  mov     eax, 0C000000Dh
0x18004017b  jmp     short loc_1800401CF
0x18004017d  xor     ebx, ebx
0x18004017f  test    edi, edi
0x180040181  jz      short loc_1800401CD
0x180040183  xor     r9d, r9d; dwFlags
0x180040186  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18004018d  lea     rdx, aRng; "RNG"
0x180040194  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x180040199  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004019f  mov     ebx, eax
0x1800401a1  test    eax, eax
0x1800401a3  js      short loc_1800401BB
0x1800401a5  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1800401aa  xor     r9d, r9d; dwFlags
0x1800401ad  mov     r8d, edi; cbBuffer
0x1800401b0  mov     rdx, rsi; pbBuffer
0x1800401b3  call    cs:__imp_BCryptGenRandom
0x1800401b9  mov     ebx, eax
0x1800401bb  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1800401c0  test    rcx, rcx
0x1800401c3  jz      short loc_1800401CD
0x1800401c5  xor     edx, edx; dwFlags
0x1800401c7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800401cd  mov     eax, ebx
0x1800401cf  mov     rbx, [rsp+28h+arg_0]
0x1800401d4  mov     rsi, [rsp+28h+arg_8]
0x1800401d9  add     rsp, 20h
0x1800401dd  pop     rdi
0x1800401de  retn
```
