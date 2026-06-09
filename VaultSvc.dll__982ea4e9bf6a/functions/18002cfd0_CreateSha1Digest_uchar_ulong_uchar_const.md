# CreateSha1Digest(uchar *,ulong,uchar * const)

- ea: `0x18002cfd0`
- end: `0x18002d089`
- name: `?CreateSha1Digest@@YAXPEAEKQEAE@Z`
- size: `185`
- prototype: `void __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002f958`

## callees

- `0x18002cfd0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18002d031`
- `bcrypt!BCryptHashData` at `0x18002d031`
- `bcrypt!BCryptFinishHash` at `0x18002d052`
- `bcrypt!BCryptFinishHash` at `0x18002d052`
- `bcrypt!BCryptDestroyHash` at `0x18002d064`
- `bcrypt!BCryptDestroyHash` at `0x18002d064`
- `bcrypt!BCryptCreateHash` at `0x18002d010`
- `bcrypt!BCryptCreateHash` at `0x18002d010`

## pseudocode

```c
void __fastcall CreateSha1Digest(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)
{
  BCRYPT_HASH_HANDLE hHash; // [rsp+80h] [rbp+18h] BYREF

  hHash = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &hHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(hHash, pbInput, cbInput, 0) < 0 )
    __fastfail(7u);
  if ( pbOutput && BCryptFinishHash(hHash, pbOutput, 0x14u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(hHash);
}

```

## disassembly

```asm
0x18002cfd0  mov     rax, rsp
0x18002cfd3  push    rbx
0x18002cfd4  push    rsi
0x18002cfd5  push    rdi
0x18002cfd6  push    r14
0x18002cfd8  sub     rsp, 48h
0x18002cfdc  mov     dword ptr [rax-38h], 0
0x18002cfe3  xor     r9d, r9d; cbHashObject
0x18002cfe6  mov     rbx, r8
0x18002cfe9  mov     dword ptr [rax-40h], 0
0x18002cff0  mov     edi, edx
0x18002cff2  mov     qword ptr [rax+18h], 0
0x18002cffa  mov     rsi, rcx
0x18002cffd  mov     qword ptr [rax-48h], 0
0x18002d005  lea     ecx, [r9+31h]; hAlgorithm
0x18002d009  xor     r8d, r8d; pbHashObject
0x18002d00c  lea     rdx, [rax+18h]; phHash
0x18002d010  call    cs:__imp_BCryptCreateHash
0x18002d016  mov     r14d, 7
0x18002d01c  test    eax, eax
0x18002d01e  js      short loc_18002D074
0x18002d020  mov     rcx, [rsp+68h+hHash]; hHash
0x18002d028  xor     r9d, r9d; dwFlags
0x18002d02b  mov     r8d, edi; cbInput
0x18002d02e  mov     rdx, rsi; pbInput
0x18002d031  call    cs:__imp_BCryptHashData
0x18002d037  test    eax, eax
0x18002d039  js      short loc_18002D07B
0x18002d03b  test    rbx, rbx
0x18002d03e  jz      short loc_18002D05C
0x18002d040  mov     rcx, [rsp+68h+hHash]; hHash
0x18002d048  xor     r9d, r9d; dwFlags
0x18002d04b  mov     rdx, rbx; pbOutput
0x18002d04e  lea     r8d, [r9+14h]; cbOutput
0x18002d052  call    cs:__imp_BCryptFinishHash
0x18002d058  test    eax, eax
0x18002d05a  js      short loc_18002D082
0x18002d05c  mov     rcx, [rsp+68h+hHash]; hHash
0x18002d064  call    cs:__imp_BCryptDestroyHash
0x18002d06a  add     rsp, 48h
0x18002d06e  pop     r14
0x18002d070  pop     rdi
0x18002d071  pop     rsi
0x18002d072  pop     rbx
0x18002d073  retn
0x18002d074  mov     rcx, r14
0x18002d077  int     29h; Win8: RtlFailFast(ecx)
0x18002d079  jmp     short loc_18002D020
0x18002d07b  mov     rcx, r14
0x18002d07e  int     29h; Win8: RtlFailFast(ecx)
0x18002d080  jmp     short loc_18002D03B
0x18002d082  mov     rcx, r14
0x18002d085  int     29h; Win8: RtlFailFast(ecx)
0x18002d087  jmp     short loc_18002D05C
```
