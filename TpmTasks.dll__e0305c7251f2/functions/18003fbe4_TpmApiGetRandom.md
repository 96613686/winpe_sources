# TpmApiGetRandom

- ea: `0x18003fbe4`
- end: `0x18003fc68`
- name: `TpmApiGetRandom`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800166dc`

## callees

- `0x18003fbc0`
- `0x18003fbe4`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18003fc3a`
- `bcrypt!BCryptGenRandom` at `0x18003fc3a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003fc55`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003fc55`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003fc18`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003fc18`

## pseudocode

```c
__int64 __fastcall TpmApiGetRandom(__int64 a1, UCHAR *a2)
{
  int v3; // ebx
  NTSTATUS v4; // eax
  NTSTATUS v5; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  phAlgorithm = 0;
  if ( a2 )
  {
    v4 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
    v3 = FromNtStatus(v4);
    if ( v3 >= 0 )
    {
      v5 = BCryptGenRandom(phAlgorithm, a2, 0xAu, 0);
      v3 = FromNtStatus(v5);
    }
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  else
  {
    return (unsigned int)-2144796413;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003fbe4  mov     [rsp+arg_0], rbx
0x18003fbe9  push    rdi
0x18003fbea  sub     rsp, 20h
0x18003fbee  mov     [rsp+28h+phAlgorithm], 0
0x18003fbf7  mov     rdi, rdx
0x18003fbfa  test    rdx, rdx
0x18003fbfd  jnz     short loc_18003FC06
0x18003fbff  mov     ebx, 80290103h
0x18003fc04  jmp     short loc_18003FC5B
0x18003fc06  xor     r9d, r9d; dwFlags
0x18003fc09  lea     rdx, aRng; "RNG"
0x18003fc10  xor     r8d, r8d; pszImplementation
0x18003fc13  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x18003fc18  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003fc1e  mov     ecx, eax; int
0x18003fc20  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18003fc25  mov     ebx, eax
0x18003fc27  test    eax, eax
0x18003fc29  js      short loc_18003FC49
0x18003fc2b  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18003fc30  xor     r9d, r9d; dwFlags
0x18003fc33  mov     rdx, rdi; pbBuffer
0x18003fc36  lea     r8d, [r9+0Ah]; cbBuffer
0x18003fc3a  call    cs:__imp_BCryptGenRandom
0x18003fc40  mov     ecx, eax; int
0x18003fc42  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18003fc47  mov     ebx, eax
0x18003fc49  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18003fc4e  test    rcx, rcx
0x18003fc51  jz      short loc_18003FC5B
0x18003fc53  xor     edx, edx; dwFlags
0x18003fc55  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003fc5b  mov     eax, ebx
0x18003fc5d  mov     rbx, [rsp+28h+arg_0]
0x18003fc62  add     rsp, 20h
0x18003fc66  pop     rdi
0x18003fc67  retn
```
