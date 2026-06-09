# I_CacheHashKeys

- ea: `0x1800028e0`
- end: `0x1800029c1`
- name: `I_CacheHashKeys`
- size: `225`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800027f4`
- `0x1800029c8`
- `0x18001859c`

## callees

- `0x1800028e0`
- `0x1800058ec`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180002950`
- `bcrypt!BCryptHashData` at `0x180002950`
- `bcrypt!BCryptDestroyHash` at `0x180002961`
- `bcrypt!BCryptDestroyHash` at `0x180002986`
- `bcrypt!BCryptDestroyHash` at `0x180002961`
- `bcrypt!BCryptDestroyHash` at `0x180002986`
- `bcrypt!BCryptFinishHash` at `0x180002979`
- `bcrypt!BCryptFinishHash` at `0x180002979`
- `bcrypt!BCryptCreateHash` at `0x180002916`
- `bcrypt!BCryptCreateHash` at `0x180002916`
- `ntdll!RtlNtStatusToDosError` at `0x1800029b1`
- `ntdll!RtlNtStatusToDosError` at `0x1800029b1`

## pseudocode

```c
ULONG __fastcall I_CacheHashKeys(__int64 a1, __int64 a2, UCHAR *a3)
{
  unsigned int v5; // eax
  unsigned int v6; // ebx
  unsigned int v7; // edi
  ULONG result; // eax
  int v9; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp+20h] BYREF

  phHash = 0;
  v5 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, &phHash, 0, 0, 0, 0, 0);
  if ( v5 )
    return WIN32_FROM_NTSTATUS(v5);
  v6 = 2;
  while ( v6 )
  {
    --v6;
    v7 = BCryptHashData(phHash, *(PUCHAR *)(a1 + 16LL * v6 + 8), *(_DWORD *)(a1 + 16LL * v6), 0);
    if ( v7 )
    {
      BCryptDestroyHash(phHash);
      return WIN32_FROM_NTSTATUS(v7);
    }
  }
  v9 = BCryptFinishHash(phHash, a3, 0x20u, 0);
  BCryptDestroyHash(phHash);
  if ( v9 >= 0 )
    return 0;
  result = RtlNtStatusToDosError(v9);
  if ( result == 317 )
    return v9;
  return result;
}

```

## disassembly

```asm
0x1800028e0  push    rbp
0x1800028e2  push    rsi
0x1800028e3  push    r14
0x1800028e5  sub     rsp, 40h
0x1800028e9  xor     r14d, r14d
0x1800028ec  lea     rdx, [rsp+58h+phHash]; phHash
0x1800028f1  mov     [rsp+58h+dwFlags], r14d; dwFlags
0x1800028f6  mov     rsi, r8
0x1800028f9  mov     rbp, rcx
0x1800028fc  mov     [rsp+58h+cbSecret], r14d; cbSecret
0x180002901  xor     r9d, r9d; cbHashObject
0x180002904  mov     [rsp+58h+pbSecret], r14; pbSecret
0x180002909  xor     r8d, r8d; pbHashObject
0x18000290c  mov     [rsp+58h+phHash], r14
0x180002911  mov     ecx, 41h ; 'A'; hAlgorithm
0x180002916  call    cs:__imp_BCryptCreateHash
0x18000291c  test    eax, eax
0x18000291e  jnz     loc_1800029A6
0x180002924  mov     [rsp+58h+arg_0], rbx
0x180002929  mov     ebx, 2
0x18000292e  mov     [rsp+58h+arg_8], rdi
0x180002933  mov     rcx, [rsp+58h+phHash]; hHash
0x180002938  xor     r9d, r9d; dwFlags
0x18000293b  test    ebx, ebx
0x18000293d  jz      short loc_180002970
0x18000293f  dec     ebx
0x180002941  mov     eax, ebx
0x180002943  add     rax, rax
0x180002946  mov     r8d, [rbp+rax*8+0]; cbInput
0x18000294b  mov     rdx, [rbp+rax*8+8]; pbInput
0x180002950  call    cs:__imp_BCryptHashData
0x180002956  mov     edi, eax
0x180002958  test    eax, eax
0x18000295a  jz      short loc_180002933
0x18000295c  mov     rcx, [rsp+58h+phHash]; hHash
0x180002961  call    cs:__imp_BCryptDestroyHash
0x180002967  mov     ecx, edi
0x180002969  call    WIN32_FROM_NTSTATUS
0x18000296e  jmp     short loc_180002993
0x180002970  mov     r8d, 20h ; ' '; cbOutput
0x180002976  mov     rdx, rsi; pbOutput
0x180002979  call    cs:__imp_BCryptFinishHash
0x18000297f  mov     rcx, [rsp+58h+phHash]; hHash
0x180002984  mov     ebx, eax
0x180002986  call    cs:__imp_BCryptDestroyHash
0x18000298c  test    ebx, ebx
0x18000298e  js      short loc_1800029AF
0x180002990  mov     eax, r14d
0x180002993  mov     rdi, [rsp+58h+arg_8]
0x180002998  mov     rbx, [rsp+58h+arg_0]
0x18000299d  add     rsp, 40h
0x1800029a1  pop     r14
0x1800029a3  pop     rsi
0x1800029a4  pop     rbp
0x1800029a5  retn
0x1800029a6  mov     ecx, eax
0x1800029a8  call    WIN32_FROM_NTSTATUS
0x1800029ad  jmp     short loc_18000299D
0x1800029af  mov     ecx, ebx; Status
0x1800029b1  call    cs:__imp_RtlNtStatusToDosError
0x1800029b7  cmp     eax, 13Dh
0x1800029bc  cmovz   eax, ebx
0x1800029bf  jmp     short loc_180002993
```
