# WinPlatformGetRandom(uchar *,uint)

- ea: `0x18004ba80`
- end: `0x18004bb2c`
- name: `?WinPlatformGetRandom@@YAJPEAEI@Z`
- size: `172`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18004ba80`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004bafc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004bafc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004bac2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004bac2`
- `bcrypt!BCryptGenRandom` at `0x18004bae2`
- `bcrypt!BCryptGenRandom` at `0x18004bae2`

## pseudocode

```c
__int64 __fastcall WinPlatformGetRandom(PUCHAR pbBuffer, ULONG cbBuffer)
{
  NTSTATUS v4; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( cbBuffer && !pbBuffer )
    return 3221225485LL;
  v4 = 0;
  if ( cbBuffer )
  {
    v4 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", L"Microsoft Primitive Provider", 0);
    if ( v4 >= 0 )
      v4 = BCryptGenRandom(phAlgorithm, pbBuffer, cbBuffer, 0);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004ba80  mov     [rsp+arg_8], rsi
0x18004ba85  push    rdi
0x18004ba86  sub     rsp, 20h
0x18004ba8a  mov     [rsp+28h+phAlgorithm], 0
0x18004ba93  mov     edi, edx
0x18004ba95  mov     rsi, rcx
0x18004ba98  test    edx, edx
0x18004ba9a  jz      short loc_18004BAA1
0x18004ba9c  test    rcx, rcx
0x18004ba9f  jz      short loc_18004BB1B
0x18004baa1  mov     [rsp+28h+arg_0], rbx
0x18004baa6  xor     ebx, ebx
0x18004baa8  test    edi, edi
0x18004baaa  jz      short loc_18004BB08
0x18004baac  xor     r9d, r9d; dwFlags
0x18004baaf  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18004bab6  lea     rdx, aRng; "RNG"
0x18004babd  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x18004bac2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004bac9  nop     dword ptr [rax+rax+00h]
0x18004bace  mov     ebx, eax
0x18004bad0  test    eax, eax
0x18004bad2  js      short loc_18004BAF0
0x18004bad4  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18004bad9  xor     r9d, r9d; dwFlags
0x18004badc  mov     r8d, edi; cbBuffer
0x18004badf  mov     rdx, rsi; pbBuffer
0x18004bae2  call    cs:__imp_BCryptGenRandom
0x18004bae9  nop     dword ptr [rax+rax+00h]
0x18004baee  mov     ebx, eax
0x18004baf0  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18004baf5  test    rcx, rcx
0x18004baf8  jz      short loc_18004BB08
0x18004bafa  xor     edx, edx; dwFlags
0x18004bafc  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004bb03  nop     dword ptr [rax+rax+00h]
0x18004bb08  mov     eax, ebx
0x18004bb0a  mov     rbx, [rsp+28h+arg_0]
0x18004bb0f  mov     rsi, [rsp+28h+arg_8]
0x18004bb14  add     rsp, 20h
0x18004bb18  pop     rdi
0x18004bb19  retn
0x18004bb1b  mov     rsi, [rsp+28h+arg_8]
0x18004bb20  mov     eax, 0C000000Dh
0x18004bb25  add     rsp, 20h
0x18004bb29  pop     rdi
0x18004bb2a  retn
```
