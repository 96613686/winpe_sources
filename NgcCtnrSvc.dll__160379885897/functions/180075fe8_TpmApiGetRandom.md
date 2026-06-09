# TpmApiGetRandom

- ea: `0x180075fe8`
- end: `0x18007608c`
- name: `TpmApiGetRandom`
- size: `164`
- prototype: `__int64 __fastcall(ULONG cbBuffer, PUCHAR pbBuffer)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180074f80`
- `0x180076bec`

## callees

- `0x180075fc0`
- `0x180075fe8`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x18007604c`
- `bcrypt!BCryptGenRandom` at `0x18007604c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180076025`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180076025`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007606d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007606d`

## pseudocode

```c
__int64 __fastcall TpmApiGetRandom(ULONG cbBuffer, PUCHAR pbBuffer)
{
  int v2; // ebx
  NTSTATUS v5; // eax
  NTSTATUS v6; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  v2 = 0;
  phAlgorithm = 0;
  if ( cbBuffer )
  {
    if ( pbBuffer )
    {
      v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
      v2 = FromNtStatus(v5);
      if ( v2 >= 0 )
      {
        v6 = BCryptGenRandom(phAlgorithm, pbBuffer, cbBuffer, 0);
        v2 = FromNtStatus(v6);
      }
      if ( phAlgorithm )
        BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    }
    else
    {
      return (unsigned int)-2144796413;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180075fe8  mov     [rsp+arg_0], rbx
0x180075fed  mov     [rsp+arg_8], rsi
0x180075ff2  push    rdi
0x180075ff3  sub     rsp, 20h
0x180075ff7  xor     ebx, ebx
0x180075ff9  mov     rdi, rdx
0x180075ffc  mov     [rsp+28h+phAlgorithm], rbx
0x180076001  mov     esi, ecx
0x180076003  test    ecx, ecx
0x180076005  jz      short loc_180076079
0x180076007  test    rdx, rdx
0x18007600a  jnz     short loc_180076013
0x18007600c  mov     ebx, 80290103h
0x180076011  jmp     short loc_180076079
0x180076013  xor     r9d, r9d; dwFlags
0x180076016  lea     rdx, aRng; "RNG"
0x18007601d  xor     r8d, r8d; pszImplementation
0x180076020  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x180076025  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18007602c  nop     dword ptr [rax+rax+00h]
0x180076031  mov     ecx, eax; int
0x180076033  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180076038  mov     ebx, eax
0x18007603a  test    eax, eax
0x18007603c  js      short loc_180076061
0x18007603e  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180076043  xor     r9d, r9d; dwFlags
0x180076046  mov     r8d, esi; cbBuffer
0x180076049  mov     rdx, rdi; pbBuffer
0x18007604c  call    cs:__imp_BCryptGenRandom
0x180076053  nop     dword ptr [rax+rax+00h]
0x180076058  mov     ecx, eax; int
0x18007605a  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18007605f  mov     ebx, eax
0x180076061  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x180076066  test    rcx, rcx
0x180076069  jz      short loc_180076079
0x18007606b  xor     edx, edx; dwFlags
0x18007606d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180076074  nop     dword ptr [rax+rax+00h]
0x180076079  mov     rsi, [rsp+28h+arg_8]
0x18007607e  mov     eax, ebx
0x180076080  mov     rbx, [rsp+28h+arg_0]
0x180076085  add     rsp, 20h
0x180076089  pop     rdi
0x18007608a  retn
```
