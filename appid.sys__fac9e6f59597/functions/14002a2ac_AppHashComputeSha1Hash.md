# AppHashComputeSha1Hash

- ea: `0x14002a2ac`
- end: `0x14002a336`
- name: `AppHashComputeSha1Hash`
- size: `138`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140026afc`

## callees

- `0x14002a2ac`
- `0x14002a33c`
- `0x14002a3fc`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x14002a2ef`
- `ksecdd!BCryptHashData` at `0x14002a2ef`
- `ksecdd!BCryptFinishHash` at `0x14002a312`
- `ksecdd!BCryptFinishHash` at `0x14002a312`

## pseudocode

```c
__int64 __fastcall AppHashComputeSha1Hash(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)
{
  NTSTATUS inited; // ebx
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+20h] [rbp-48h] BYREF
  __int128 v9; // [rsp+30h] [rbp-38h]

  *(_OWORD *)hHash = 0;
  v9 = 0;
  inited = AppHashInitHash(AppHashAlgHandle, hHash);
  if ( inited >= 0 )
  {
    inited = BCryptHashData(hHash[0], pbInput, cbInput, 0);
    if ( inited >= 0 )
      inited = BCryptFinishHash(hHash[0], pbOutput, WORD2(v9), 0);
  }
  AppHashDestroyHash(hHash);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14002a2ac  push    rbx
0x14002a2ae  push    rbp
0x14002a2af  push    rsi
0x14002a2b0  push    rdi
0x14002a2b1  sub     rsp, 48h
0x14002a2b5  xorps   xmm0, xmm0
0x14002a2b8  mov     esi, edx
0x14002a2ba  mov     rbp, rcx
0x14002a2bd  lea     rdx, [rsp+68h+hHash]; phHash
0x14002a2c2  mov     rcx, qword ptr cs:AppHashAlgHandle; hAlgorithm
0x14002a2c9  mov     rdi, r8
0x14002a2cc  movups  xmmword ptr [rsp+68h+hHash], xmm0
0x14002a2d1  movups  [rsp+68h+var_38], xmm0
0x14002a2d6  call    AppHashInitHash
0x14002a2db  mov     ebx, eax
0x14002a2dd  test    eax, eax
0x14002a2df  js      short loc_14002A320
0x14002a2e1  mov     rcx, [rsp+68h+hHash]; hHash
0x14002a2e6  xor     r9d, r9d; dwFlags
0x14002a2e9  mov     r8d, esi; cbInput
0x14002a2ec  mov     rdx, rbp; pbInput
0x14002a2ef  call    cs:__imp_BCryptHashData
0x14002a2f6  nop     dword ptr [rax+rax+00h]
0x14002a2fb  mov     ebx, eax
0x14002a2fd  test    eax, eax
0x14002a2ff  js      short loc_14002A320
0x14002a301  movzx   r8d, word ptr [rsp+68h+var_38+4]; cbOutput
0x14002a307  xor     r9d, r9d; dwFlags
0x14002a30a  mov     rcx, [rsp+68h+hHash]; hHash
0x14002a30f  mov     rdx, rdi; pbOutput
0x14002a312  call    cs:__imp_BCryptFinishHash
0x14002a319  nop     dword ptr [rax+rax+00h]
0x14002a31e  mov     ebx, eax
0x14002a320  lea     rcx, [rsp+68h+hHash]
0x14002a325  call    AppHashDestroyHash
0x14002a32a  mov     eax, ebx
0x14002a32c  add     rsp, 48h
0x14002a330  pop     rdi
0x14002a331  pop     rsi
0x14002a332  pop     rbp
0x14002a333  pop     rbx
0x14002a334  retn
```
