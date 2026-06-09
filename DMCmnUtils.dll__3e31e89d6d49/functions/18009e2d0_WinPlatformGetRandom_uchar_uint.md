# WinPlatformGetRandom(uchar *,uint)

- ea: `0x18009e2d0`
- end: `0x18009e372`
- name: `?WinPlatformGetRandom@@YAJPEAEI@Z`
- size: `162`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18009e2d0`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18009e339`
- `bcrypt!BCryptGenRandom` at `0x18009e339`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009e353`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009e353`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009e319`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009e319`

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
0x18009e2d0  mov     [rsp+arg_0], rbx
0x18009e2d5  mov     [rsp+arg_8], rsi
0x18009e2da  push    rdi
0x18009e2db  sub     rsp, 20h
0x18009e2df  mov     [rsp+28h+phAlgorithm], 0
0x18009e2e8  mov     edi, edx
0x18009e2ea  mov     rsi, rcx
0x18009e2ed  test    edx, edx
0x18009e2ef  jz      short loc_18009E2FD
0x18009e2f1  test    rcx, rcx
0x18009e2f4  jnz     short loc_18009E2FD
0x18009e2f6  mov     eax, 0C000000Dh
0x18009e2fb  jmp     short loc_18009E361
0x18009e2fd  xor     ebx, ebx
0x18009e2ff  test    edi, edi
0x18009e301  jz      short loc_18009E35F
0x18009e303  xor     r9d, r9d; dwFlags
0x18009e306  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009e30d  lea     rdx, aRng; "RNG"
0x18009e314  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x18009e319  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009e320  nop     dword ptr [rax+rax+00h]
0x18009e325  mov     ebx, eax
0x18009e327  test    eax, eax
0x18009e329  js      short loc_18009E347
0x18009e32b  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18009e330  xor     r9d, r9d; dwFlags
0x18009e333  mov     r8d, edi; cbBuffer
0x18009e336  mov     rdx, rsi; pbBuffer
0x18009e339  call    cs:__imp_BCryptGenRandom
0x18009e340  nop     dword ptr [rax+rax+00h]
0x18009e345  mov     ebx, eax
0x18009e347  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18009e34c  test    rcx, rcx
0x18009e34f  jz      short loc_18009E35F
0x18009e351  xor     edx, edx; dwFlags
0x18009e353  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009e35a  nop     dword ptr [rax+rax+00h]
0x18009e35f  mov     eax, ebx
0x18009e361  mov     rbx, [rsp+28h+arg_0]
0x18009e366  mov     rsi, [rsp+28h+arg_8]
0x18009e36b  add     rsp, 20h
0x18009e36f  pop     rdi
0x18009e370  retn
```
