# WinPlatformGetRandom(uchar *,uint)

- ea: `0x140055880`
- end: `0x14005590f`
- name: `?WinPlatformGetRandom@@YAJPEAEI@Z`
- size: `143`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140055880`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1400558e3`
- `bcrypt!BCryptGenRandom` at `0x1400558e3`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400558c9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1400558c9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1400558f7`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1400558f7`

## pseudocode

```c
__int64 __fastcall WinPlatformGetRandom(PUCHAR pbBuffer, ULONG cbBuffer)
{
  NTSTATUS v4; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( !cbBuffer || pbBuffer )
  {
    v4 = 0;
    if ( cbBuffer )
    {
      v4 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", L"Microsoft Primitive Provider", 0);
      if ( v4 >= 0 )
        v4 = BCryptGenRandom(phAlgorithm, pbBuffer, cbBuffer, 0);
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140055880  mov     [rsp+arg_0], rbx
0x140055885  mov     [rsp+arg_8], rsi
0x14005588a  push    rdi
0x14005588b  sub     rsp, 20h
0x14005588f  mov     [rsp+28h+phAlgorithm], 0
0x140055898  mov     edi, edx
0x14005589a  mov     rsi, rcx
0x14005589d  test    edx, edx
0x14005589f  jz      short loc_1400558AD
0x1400558a1  test    rcx, rcx
0x1400558a4  jnz     short loc_1400558AD
0x1400558a6  mov     ebx, 0C000000Dh
0x1400558ab  jmp     short loc_1400558FD
0x1400558ad  xor     ebx, ebx
0x1400558af  test    edi, edi
0x1400558b1  jz      short loc_1400558FD
0x1400558b3  xor     r9d, r9d; dwFlags
0x1400558b6  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1400558bd  lea     rdx, aRng; "RNG"
0x1400558c4  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x1400558c9  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400558cf  mov     ebx, eax
0x1400558d1  test    eax, eax
0x1400558d3  js      short loc_1400558EB
0x1400558d5  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1400558da  xor     r9d, r9d; dwFlags
0x1400558dd  mov     r8d, edi; cbBuffer
0x1400558e0  mov     rdx, rsi; pbBuffer
0x1400558e3  call    cs:__imp_BCryptGenRandom
0x1400558e9  mov     ebx, eax
0x1400558eb  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x1400558f0  test    rcx, rcx
0x1400558f3  jz      short loc_1400558FD
0x1400558f5  xor     edx, edx; dwFlags
0x1400558f7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400558fd  mov     rsi, [rsp+28h+arg_8]
0x140055902  mov     eax, ebx
0x140055904  mov     rbx, [rsp+28h+arg_0]
0x140055909  add     rsp, 20h
0x14005590d  pop     rdi
0x14005590e  retn
```
