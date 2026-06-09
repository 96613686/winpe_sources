# AppHashInitHash

- ea: `0x14002a3fc`
- end: `0x14002a519`
- name: `AppHashInitHash`
- size: `285`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003598`
- `0x14002a2ac`

## callees

- `0x14002a33c`
- `0x14002a3fc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002a4a9`
- `ntoskrnl!ExAllocatePool2` at `0x14002a4a9`
- `ksecdd!BCryptGetProperty` at `0x14002a44b`
- `ksecdd!BCryptGetProperty` at `0x14002a488`
- `ksecdd!BCryptGetProperty` at `0x14002a44b`
- `ksecdd!BCryptGetProperty` at `0x14002a488`
- `ksecdd!BCryptCreateHash` at `0x14002a4ec`
- `ksecdd!BCryptCreateHash` at `0x14002a4ec`

## pseudocode

```c
__int64 __fastcall AppHashInitHash(BCRYPT_ALG_HANDLE hAlgorithm, BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS Property; // ebx
  void *Pool2; // rax
  ULONG pbOutput; // [rsp+58h] [rbp+10h] BYREF
  ULONG pcbResult; // [rsp+60h] [rbp+18h] BYREF

  *(_OWORD *)phHash = 0;
  pbOutput = 0;
  pcbResult = 0;
  *((_OWORD *)phHash + 1) = 0;
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", (PUCHAR)phHash + 20, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_6;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_6;
  Pool2 = (void *)ExAllocatePool2(258, pbOutput, 1215328321);
  phHash[1] = Pool2;
  if ( !Pool2 )
  {
    Property = -1073741801;
LABEL_6:
    AppHashDestroyHash(phHash);
    return (unsigned int)Property;
  }
  Property = BCryptCreateHash(hAlgorithm, phHash, (PUCHAR)Pool2, pbOutput, 0, 0, 0);
  if ( Property < 0 )
    goto LABEL_6;
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14002a3fc  mov     rax, rsp
0x14002a3ff  mov     [rax+8], rbx
0x14002a403  mov     [rax+20h], rsi
0x14002a407  push    rdi
0x14002a408  sub     rsp, 40h
0x14002a40c  xorps   xmm0, xmm0
0x14002a40f  mov     dword ptr [rax-20h], 0
0x14002a416  movups  xmmword ptr [rdx], xmm0
0x14002a419  mov     dword ptr [rax+10h], 0
0x14002a420  lea     r8, [rdx+14h]; pbOutput
0x14002a424  mov     dword ptr [rax+18h], 0
0x14002a42b  lea     rax, [rax+18h]
0x14002a42f  movups  xmmword ptr [rdx+10h], xmm0
0x14002a433  mov     rdi, rdx
0x14002a436  mov     [rsp+48h+pcbResult], rax; pcbResult
0x14002a43b  lea     rdx, pszProperty; "HashDigestLength"
0x14002a442  mov     r9d, 4; cbOutput
0x14002a448  mov     rsi, rcx
0x14002a44b  call    cs:__imp_BCryptGetProperty
0x14002a452  nop     dword ptr [rax+rax+00h]
0x14002a457  mov     ebx, eax
0x14002a459  test    eax, eax
0x14002a45b  js      loc_14002A4FE
0x14002a461  lea     rax, [rsp+48h+arg_10]
0x14002a466  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14002a46e  mov     r9d, 4; cbOutput
0x14002a474  mov     [rsp+48h+pcbResult], rax; pcbResult
0x14002a479  lea     r8, [rsp+48h+pbOutput]; pbOutput
0x14002a47e  mov     rcx, rsi; hObject
0x14002a481  lea     rdx, aObjectlength; "ObjectLength"
0x14002a488  call    cs:__imp_BCryptGetProperty
0x14002a48f  nop     dword ptr [rax+rax+00h]
0x14002a494  mov     ebx, eax
0x14002a496  test    eax, eax
0x14002a498  js      short loc_14002A4FE
0x14002a49a  mov     edx, [rsp+48h+pbOutput]
0x14002a49e  mov     ecx, 102h
0x14002a4a3  mov     r8d, 48707041h
0x14002a4a9  call    cs:__imp_ExAllocatePool2
0x14002a4b0  nop     dword ptr [rax+rax+00h]
0x14002a4b5  mov     [rdi+8], rax
0x14002a4b9  test    rax, rax
0x14002a4bc  jnz     short loc_14002A4C5
0x14002a4be  mov     ebx, 0C0000017h
0x14002a4c3  jmp     short loc_14002A4FE
0x14002a4c5  mov     r9d, [rsp+48h+pbOutput]; cbHashObject
0x14002a4ca  mov     r8, rax; pbHashObject
0x14002a4cd  mov     [rsp+48h+var_18], 0; dwFlags
0x14002a4d5  mov     rdx, rdi; phHash
0x14002a4d8  mov     [rsp+48h+dwFlags], 0; cbSecret
0x14002a4e0  mov     rcx, rsi; hAlgorithm
0x14002a4e3  mov     [rsp+48h+pcbResult], 0; pbSecret
0x14002a4ec  call    cs:__imp_BCryptCreateHash
0x14002a4f3  nop     dword ptr [rax+rax+00h]
0x14002a4f8  mov     ebx, eax
0x14002a4fa  test    eax, eax
0x14002a4fc  jns     short loc_14002A506
0x14002a4fe  mov     rcx, rdi
0x14002a501  call    AppHashDestroyHash
0x14002a506  mov     rsi, [rsp+48h+arg_18]
0x14002a50b  mov     eax, ebx
0x14002a50d  mov     rbx, [rsp+48h+arg_0]
0x14002a512  add     rsp, 40h
0x14002a516  pop     rdi
0x14002a517  retn
```
