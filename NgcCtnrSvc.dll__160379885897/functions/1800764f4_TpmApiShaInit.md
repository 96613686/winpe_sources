# TpmApiShaInit

- ea: `0x1800764f4`
- end: `0x1800765ad`
- name: `TpmApiShaInit`
- size: `185`
- prototype: `__int64 __fastcall(LPCWSTR pszAlgId, BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180076ab8`
- `0x180076c20`
- `0x180076e24`
- `0x180077084`

## callees

- `0x180076124`
- `0x1800764f4`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180076561`
- `bcrypt!BCryptCreateHash` at `0x180076561`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007659f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007659f`

## pseudocode

```c
__int64 __fastcall TpmApiShaInit(LPCWSTR pszAlgId, BCRYPT_HASH_HANDLE *phHash, volatile signed __int64 *a3)
{
  int v5; // ebx
  int v6; // eax
  NTSTATUS Hash; // eax
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+58h] [rbp+10h] BYREF

  if ( !phHash )
    return (unsigned int)-2144796412;
  v5 = 0;
  hAlgorithm = 0;
  if ( *a3 )
    goto LABEL_6;
  v6 = TpmApiOpenAlgorithmProvider(&hAlgorithm, pszAlgId);
  if ( v6 < 0 )
  {
    v5 = v6 | 0x10000000;
    goto LABEL_6;
  }
  if ( !_InterlockedCompareExchange64(a3, (signed __int64)hAlgorithm, 0) )
  {
LABEL_6:
    if ( v5 < 0 )
      return (unsigned int)v5;
    goto LABEL_7;
  }
  BCryptCloseAlgorithmProvider(hAlgorithm, 0);
LABEL_7:
  Hash = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)a3, phHash, 0, 0, 0, 0, 0);
  if ( Hash < 0 )
    return (unsigned int)(Hash | 0x10000000);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800764f4  mov     [rsp+arg_0], rbx
0x1800764f9  mov     [rsp+arg_10], rsi
0x1800764fe  push    rdi
0x1800764ff  sub     rsp, 40h
0x180076503  mov     rdi, r8
0x180076506  mov     rsi, rdx
0x180076509  test    rdx, rdx
0x18007650c  jnz     short loc_180076515
0x18007650e  mov     ebx, 80290104h
0x180076513  jmp     short loc_180076577
0x180076515  xor     ebx, ebx
0x180076517  mov     [rsp+48h+hAlgorithm], rbx
0x18007651c  cmp     [r8], rbx
0x18007651f  jnz     short loc_180076538
0x180076521  mov     rdx, rcx; pszAlgId
0x180076524  lea     rcx, [rsp+48h+hAlgorithm]; phAlgorithm
0x180076529  call    ?TpmApiOpenAlgorithmProvider@@YAJPEAPEAXPEBG@Z; TpmApiOpenAlgorithmProvider(void * *,ushort const *)
0x18007652e  test    eax, eax
0x180076530  jns     short loc_18007658A
0x180076532  mov     ebx, eax
0x180076534  bts     ebx, 1Ch
0x180076538  test    ebx, ebx
0x18007653a  js      short loc_180076577
0x18007653c  mov     rcx, [rdi]; hAlgorithm
0x18007653f  xor     r9d, r9d; cbHashObject
0x180076542  mov     [rsp+48h+dwFlags], 0; dwFlags
0x18007654a  xor     r8d, r8d; pbHashObject
0x18007654d  mov     [rsp+48h+cbSecret], 0; cbSecret
0x180076555  mov     rdx, rsi; phHash
0x180076558  mov     [rsp+48h+pbSecret], 0; pbSecret
0x180076561  call    cs:__imp_BCryptCreateHash
0x180076568  nop     dword ptr [rax+rax+00h]
0x18007656d  test    eax, eax
0x18007656f  jns     short loc_180076577
0x180076571  mov     ebx, eax
0x180076573  bts     ebx, 1Ch
0x180076577  mov     rsi, [rsp+48h+arg_10]
0x18007657c  mov     eax, ebx
0x18007657e  mov     rbx, [rsp+48h+arg_0]
0x180076583  add     rsp, 40h
0x180076587  pop     rdi
0x180076588  retn
0x18007658a  mov     rcx, [rsp+48h+hAlgorithm]
0x18007658f  xor     eax, eax
0x180076591  lock cmpxchg [rdi], rcx
0x180076596  jz      short loc_180076538
0x180076598  mov     rcx, [rsp+48h+hAlgorithm]; hAlgorithm
0x18007659d  xor     edx, edx; dwFlags
0x18007659f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800765a6  nop     dword ptr [rax+rax+00h]
0x1800765ab  jmp     short loc_18007653C
```
