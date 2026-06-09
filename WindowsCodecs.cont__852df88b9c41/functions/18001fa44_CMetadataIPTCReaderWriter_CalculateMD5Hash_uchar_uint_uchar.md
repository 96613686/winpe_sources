# CMetadataIPTCReaderWriter::CalculateMD5Hash(uchar *,uint,uchar *)

- ea: `0x18001fa44`
- end: `0x18001fb20`
- name: `?CalculateMD5Hash@CMetadataIPTCReaderWriter@@CAXPEAEI0@Z`
- size: `220`
- prototype: `void __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020740`

## callees

- `0x18001fa44`
- `0x1800e2f90`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18001fad7`
- `bcrypt!BCryptDestroyHash` at `0x18001fad7`
- `bcrypt!BCryptCreateHash` at `0x18001fa90`
- `bcrypt!BCryptCreateHash` at `0x18001fa90`
- `bcrypt!BCryptFinishHash` at `0x18001fac8`
- `bcrypt!BCryptFinishHash` at `0x18001fac8`
- `bcrypt!BCryptHashData` at `0x18001faad`
- `bcrypt!BCryptHashData` at `0x18001faad`

## pseudocode

```c
void __fastcall CMetadataIPTCReaderWriter::CalculateMD5Hash(PUCHAR pbInput, ULONG cbInput, unsigned __int8 *a3)
{
  BCRYPT_HASH_HANDLE hHash[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v7; // [rsp+50h] [rbp-28h]

  *(_OWORD *)hHash = 0;
  v7 = 0;
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, hHash, 0, 0, 0, 0, 0) < 0 )
    __fastfail(7u);
  if ( BCryptHashData(hHash[0], pbInput, cbInput, 0) < 0 )
    __fastfail(7u);
  if ( BCryptFinishHash(hHash[0], (PUCHAR)&hHash[1], 0x10u, 0) < 0 )
    __fastfail(7u);
  BCryptDestroyHash(hHash[0]);
  *(BCRYPT_HASH_HANDLE *)a3 = hHash[1];
  *((_QWORD *)a3 + 1) = v7;
}

```

## disassembly

```asm
0x18001fa44  mov     r11, rsp
0x18001fa47  mov     [r11+20h], rbx
0x18001fa4b  push    rbp
0x18001fa4c  push    rsi
0x18001fa4d  push    rdi
0x18001fa4e  sub     rsp, 60h
0x18001fa52  mov     rax, cs:__security_cookie
0x18001fa59  xor     rax, rsp
0x18001fa5c  mov     [rsp+78h+var_20], rax
0x18001fa61  xor     eax, eax
0x18001fa63  xorps   xmm0, xmm0
0x18001fa66  mov     [rsp+78h+dwFlags], eax; dwFlags
0x18001fa6a  mov     rbx, r8
0x18001fa6d  mov     esi, edx
0x18001fa6f  mov     [rsp+78h+cbSecret], eax; cbSecret
0x18001fa73  mov     rdi, rcx
0x18001fa76  mov     [r11-58h], rax
0x18001fa7a  movups  xmmword ptr [rsp+78h+hHash], xmm0
0x18001fa7f  lea     ecx, [rax+21h]; hAlgorithm
0x18001fa82  mov     [r11-28h], rax
0x18001fa86  xor     r9d, r9d; cbHashObject
0x18001fa89  lea     rdx, [r11-38h]; phHash
0x18001fa8d  xor     r8d, r8d; pbHashObject
0x18001fa90  call    cs:__imp_BCryptCreateHash
0x18001fa96  mov     ebp, 7
0x18001fa9b  test    eax, eax
0x18001fa9d  js      short loc_18001FB0B
0x18001fa9f  mov     rcx, [rsp+78h+hHash]; hHash
0x18001faa4  xor     r9d, r9d; dwFlags
0x18001faa7  mov     r8d, esi; cbInput
0x18001faaa  mov     rdx, rdi; pbInput
0x18001faad  call    cs:__imp_BCryptHashData
0x18001fab3  test    eax, eax
0x18001fab5  js      short loc_18001FB12
0x18001fab7  mov     rcx, [rsp+78h+hHash]; hHash
0x18001fabc  lea     rdx, [rsp+78h+hHash+8]; pbOutput
0x18001fac1  xor     r9d, r9d; dwFlags
0x18001fac4  lea     r8d, [r9+10h]; cbOutput
0x18001fac8  call    cs:__imp_BCryptFinishHash
0x18001face  test    eax, eax
0x18001fad0  js      short loc_18001FB19
0x18001fad2  mov     rcx, [rsp+78h+hHash]; hHash
0x18001fad7  call    cs:__imp_BCryptDestroyHash
0x18001fadd  mov     rax, [rsp+78h+hHash+8]
0x18001fae2  mov     [rbx], rax
0x18001fae5  mov     rax, [rsp+78h+var_28]
0x18001faea  mov     [rbx+8], rax
0x18001faee  mov     rcx, [rsp+78h+var_20]
0x18001faf3  xor     rcx, rsp; StackCookie
0x18001faf6  call    __security_check_cookie
0x18001fafb  mov     rbx, [rsp+78h+arg_18]
0x18001fb03  add     rsp, 60h
0x18001fb07  pop     rdi
0x18001fb08  pop     rsi
0x18001fb09  pop     rbp
0x18001fb0a  retn
0x18001fb0b  mov     rcx, rbp
0x18001fb0e  int     29h; Win8: RtlFailFast(ecx)
0x18001fb10  jmp     short loc_18001FA9F
0x18001fb12  mov     rcx, rbp
0x18001fb15  int     29h; Win8: RtlFailFast(ecx)
0x18001fb17  jmp     short loc_18001FAB7
0x18001fb19  mov     rcx, rbp
0x18001fb1c  int     29h; Win8: RtlFailFast(ecx)
0x18001fb1e  jmp     short loc_18001FAD2
```
