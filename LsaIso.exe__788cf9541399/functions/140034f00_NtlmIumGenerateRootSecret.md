# NtlmIumGenerateRootSecret

- ea: `0x140034f00`
- end: `0x140035050`
- name: `NtlmIumGenerateRootSecret`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140006720`
- `0x140034f00`
- `0x140038d10`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034f35`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034f35`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140034f8c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140034f8c`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140034fb8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140034fb8`
- `bcrypt!BCryptGenRandom` at `0x140034fa9`
- `bcrypt!BCryptGenRandom` at `0x140034fa9`

## pseudocode

```c
__int64 __fastcall NtlmIumGenerateRootSecret(__int64 a1, _DWORD *a2, void **a3)
{
  NTSTATUS v6; // edi
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-38h] BYREF
  UCHAR pbBuffer[16]; // [rsp+58h] [rbp-30h] BYREF
  __int128 v9; // [rsp+68h] [rbp-20h]

  if ( qword_140052C50 == a1 )
  {
    phAlgorithm = 0;
    *(_OWORD *)pbBuffer = 0;
    v9 = 0;
    if ( a2 && a3 )
    {
      *a3 = 0;
      *a2 = 0;
      v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
      if ( v6 < 0
        || (v6 = BCryptGenRandom(phAlgorithm, pbBuffer, 0x20u, 0), BCryptCloseAlgorithmProvider(phAlgorithm, 0), v6 < 0)
        || (v6 = IumpLsaIsoFunctions(
                   "NtlmRootSecret",
                   pbBuffer,
                   32,
                   MIDL_user_allocate,
                   SafeAllocaFreeToHeap,
                   1,
                   a3,
                   a2),
            v6 < 0) )
      {
        *a2 = 0;
        if ( *a3 )
        {
          SafeAllocaFreeToHeap(*a3);
          *a3 = 0;
        }
      }
      return (unsigned int)v6;
    }
    else
    {
      return 3221225485LL;
    }
  }
  else
  {
    Sleep(5u);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x140034f00  mov     [rsp+arg_0], rbx
0x140034f05  mov     [rsp+arg_18], rsi
0x140034f0a  push    rdi
0x140034f0b  sub     rsp, 80h
0x140034f12  mov     rax, cs:__security_cookie
0x140034f19  xor     rax, rsp
0x140034f1c  mov     [rsp+88h+var_10], rax
0x140034f21  cmp     cs:qword_140052C50, rcx
0x140034f28  mov     rbx, r8
0x140034f2b  mov     rsi, rdx
0x140034f2e  jz      short loc_140034F45
0x140034f30  mov     ecx, 5; dwMilliseconds
0x140034f35  call    cs:__imp_Sleep
0x140034f3b  mov     eax, 0C0000022h
0x140034f40  jmp     loc_14003502E
0x140034f45  mov     [rsp+88h+phAlgorithm], 0
0x140034f4e  xorps   xmm0, xmm0
0x140034f51  movups  xmmword ptr [rsp+88h+pbBuffer], xmm0
0x140034f56  movups  [rsp+88h+var_20], xmm0
0x140034f5b  test    rsi, rsi
0x140034f5e  jz      loc_140035029
0x140034f64  test    rbx, rbx
0x140034f67  jz      loc_140035029
0x140034f6d  mov     qword ptr [r8], 0
0x140034f74  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x140034f79  mov     dword ptr [rdx], 0
0x140034f7f  xor     r9d, r9d; dwFlags
0x140034f82  lea     rdx, aRng; "RNG"
0x140034f89  xor     r8d, r8d; pszImplementation
0x140034f8c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140034f92  mov     edi, eax
0x140034f94  test    eax, eax
0x140034f96  js      short loc_14003500B
0x140034f98  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x140034f9d  lea     rdx, [rsp+88h+pbBuffer]; pbBuffer
0x140034fa2  xor     r9d, r9d; dwFlags
0x140034fa5  lea     r8d, [r9+20h]; cbBuffer
0x140034fa9  call    cs:__imp_BCryptGenRandom
0x140034faf  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x140034fb4  xor     edx, edx; dwFlags
0x140034fb6  mov     edi, eax
0x140034fb8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140034fbe  test    edi, edi
0x140034fc0  js      short loc_14003500B
0x140034fc2  mov     [rsp+88h+var_50], rsi
0x140034fc7  lea     rax, SafeAllocaFreeToHeap
0x140034fce  mov     [rsp+88h+var_58], rbx
0x140034fd3  lea     r9, MIDL_user_allocate
0x140034fda  mov     [rsp+88h+var_60], 1
0x140034fe2  lea     rdx, [rsp+88h+pbBuffer]
0x140034fe7  mov     [rsp+88h+var_68], rax
0x140034fec  lea     rcx, aNtlmrootsecret; "NtlmRootSecret"
0x140034ff3  mov     rax, qword ptr cs:?IumpLsaIsoFunctions@@3U_LsaIsoSupportFunctions@@A; _LsaIsoSupportFunctions IumpLsaIsoFunctions
0x140034ffa  mov     r8d, 20h ; ' '
0x140035000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140035005  mov     edi, eax
0x140035007  test    eax, eax
0x140035009  jns     short loc_140035025
0x14003500b  mov     dword ptr [rsi], 0
0x140035011  mov     rcx, [rbx]; void *
0x140035014  test    rcx, rcx
0x140035017  jz      short loc_140035025
0x140035019  call    SafeAllocaFreeToHeap
0x14003501e  mov     qword ptr [rbx], 0
0x140035025  mov     eax, edi
0x140035027  jmp     short loc_14003502E
0x140035029  mov     eax, 0C000000Dh
0x14003502e  mov     rcx, [rsp+88h+var_10]
0x140035033  xor     rcx, rsp; StackCookie
0x140035036  call    __security_check_cookie
0x14003503b  lea     r11, [rsp+88h+var_8]
0x140035043  mov     rbx, [r11+10h]
0x140035047  mov     rsi, [r11+28h]
0x14003504b  mov     rsp, r11
0x14003504e  pop     rdi
0x14003504f  retn
```
