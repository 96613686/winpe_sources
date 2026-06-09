# GenerateRandomSeed(uchar *,uint)

- ea: `0x18004141c`
- end: `0x1800414bc`
- name: `?GenerateRandomSeed@@YAJPEAEI@Z`
- size: `160`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800414c4`
- `0x180041728`

## callees

- `0x18004141c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180041451`
- `ntdll!RtlNtStatusToDosError` at `0x180041481`
- `ntdll!RtlNtStatusToDosError` at `0x180041451`
- `ntdll!RtlNtStatusToDosError` at `0x180041481`
- `bcrypt!BCryptGenRandom` at `0x180041479`
- `bcrypt!BCryptGenRandom` at `0x180041479`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800414a2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800414a2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180041449`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180041449`

## pseudocode

```c
__int64 __fastcall GenerateRandomSeed(PUCHAR pbBuffer)
{
  NTSTATUS v2; // eax
  signed int v3; // eax
  signed int v4; // ebx
  NTSTATUS v5; // eax
  signed int v6; // eax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+30h] [rbp+8h] BYREF

  phAlgorithm = 0;
  if ( pbBuffer )
  {
    v2 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"RNG", 0, 0);
    v3 = RtlNtStatusToDosError(v2);
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( v4 >= 0 )
    {
      v5 = BCryptGenRandom(phAlgorithm, pbBuffer, 0x20u, 0);
      v6 = RtlNtStatusToDosError(v5);
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004141c  mov     [rsp+arg_8], rbx
0x180041421  push    rdi
0x180041422  sub     rsp, 20h
0x180041426  mov     [rsp+28h+phAlgorithm], 0
0x18004142f  mov     rdi, rcx
0x180041432  test    rcx, rcx
0x180041435  jz      short loc_1800414AA
0x180041437  xor     r9d, r9d; dwFlags
0x18004143a  lea     rdx, aRng; "RNG"
0x180041441  xor     r8d, r8d; pszImplementation
0x180041444  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x180041449  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004144f  mov     ecx, eax; Status
0x180041451  call    cs:__imp_RtlNtStatusToDosError
0x180041457  mov     ebx, eax
0x180041459  test    eax, eax
0x18004145b  jle     short loc_180041466
0x18004145d  movzx   ebx, ax
0x180041460  or      ebx, 80070000h
0x180041466  test    ebx, ebx
0x180041468  js      short loc_180041496
0x18004146a  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18004146f  xor     r9d, r9d; dwFlags
0x180041472  mov     rdx, rdi; pbBuffer
0x180041475  lea     r8d, [r9+20h]; cbBuffer
0x180041479  call    cs:__imp_BCryptGenRandom
0x18004147f  mov     ecx, eax; Status
0x180041481  call    cs:__imp_RtlNtStatusToDosError
0x180041487  mov     ebx, eax
0x180041489  test    eax, eax
0x18004148b  jle     short loc_180041496
0x18004148d  movzx   ebx, ax
0x180041490  or      ebx, 80070000h
0x180041496  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18004149b  test    rcx, rcx
0x18004149e  jz      short loc_1800414AF
0x1800414a0  xor     edx, edx; dwFlags
0x1800414a2  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800414a8  jmp     short loc_1800414AF
0x1800414aa  mov     ebx, 80070057h
0x1800414af  mov     eax, ebx
0x1800414b1  mov     rbx, [rsp+28h+arg_8]
0x1800414b6  add     rsp, 20h
0x1800414ba  pop     rdi
0x1800414bb  retn
```
