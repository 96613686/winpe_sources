# CMetadataIPTCReaderWriter::CalculateMD5Hash(uchar *,uint,uchar *)

- ea: `0x18004fe44`
- end: `0x18004ff3c`
- name: `?CalculateMD5Hash@CMetadataIPTCReaderWriter@@CAXPEAEI0@Z`
- size: `248`
- prototype: `void __fastcall(PUCHAR pbInput, ULONG cbInput, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004fb38`

## callees

- `0x18004fe44`
- `0x1800e5e60`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x18004fee9`
- `bcrypt!BCryptDestroyHash` at `0x18004fee9`
- `bcrypt!BCryptCreateHash` at `0x18004fe90`
- `bcrypt!BCryptCreateHash` at `0x18004fe90`
- `bcrypt!BCryptFinishHash` at `0x18004fed4`
- `bcrypt!BCryptFinishHash` at `0x18004fed4`
- `bcrypt!BCryptHashData` at `0x18004feb3`
- `bcrypt!BCryptHashData` at `0x18004feb3`

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
0x18004fe44  mov     r11, rsp
0x18004fe47  mov     [r11+20h], rbx
0x18004fe4b  push    rbp
0x18004fe4c  push    rsi
0x18004fe4d  push    rdi
0x18004fe4e  sub     rsp, 60h
0x18004fe52  mov     rax, cs:__security_cookie
0x18004fe59  xor     rax, rsp
0x18004fe5c  mov     [rsp+78h+var_20], rax
0x18004fe61  xor     eax, eax
0x18004fe63  xorps   xmm0, xmm0
0x18004fe66  mov     [rsp+78h+dwFlags], eax; dwFlags
0x18004fe6a  mov     rbx, r8
0x18004fe6d  mov     esi, edx
0x18004fe6f  mov     [rsp+78h+cbSecret], eax; cbSecret
0x18004fe73  mov     rdi, rcx
0x18004fe76  mov     [r11-58h], rax
0x18004fe7a  movups  xmmword ptr [rsp+78h+hHash], xmm0
0x18004fe7f  lea     ecx, [rax+21h]; hAlgorithm
0x18004fe82  mov     [r11-28h], rax
0x18004fe86  xor     r9d, r9d; cbHashObject
0x18004fe89  lea     rdx, [r11-38h]; phHash
0x18004fe8d  xor     r8d, r8d; pbHashObject
0x18004fe90  call    cs:__imp_BCryptCreateHash
0x18004fe97  nop     dword ptr [rax+rax+00h]
0x18004fe9c  mov     ebp, 7
0x18004fea1  test    eax, eax
0x18004fea3  js      short loc_18004FF24
0x18004fea5  mov     rcx, [rsp+78h+hHash]; hHash
0x18004feaa  xor     r9d, r9d; dwFlags
0x18004fead  mov     r8d, esi; cbInput
0x18004feb0  mov     rdx, rdi; pbInput
0x18004feb3  call    cs:__imp_BCryptHashData
0x18004feba  nop     dword ptr [rax+rax+00h]
0x18004febf  test    eax, eax
0x18004fec1  js      short loc_18004FF2E
0x18004fec3  mov     rcx, [rsp+78h+hHash]; hHash
0x18004fec8  lea     rdx, [rsp+78h+hHash+8]; pbOutput
0x18004fecd  xor     r9d, r9d; dwFlags
0x18004fed0  lea     r8d, [r9+10h]; cbOutput
0x18004fed4  call    cs:__imp_BCryptFinishHash
0x18004fedb  nop     dword ptr [rax+rax+00h]
0x18004fee0  test    eax, eax
0x18004fee2  js      short loc_18004FF35
0x18004fee4  mov     rcx, [rsp+78h+hHash]; hHash
0x18004fee9  call    cs:__imp_BCryptDestroyHash
0x18004fef0  nop     dword ptr [rax+rax+00h]
0x18004fef5  mov     rax, [rsp+78h+hHash+8]
0x18004fefa  mov     [rbx], rax
0x18004fefd  mov     rax, [rsp+78h+var_28]
0x18004ff02  mov     [rbx+8], rax
0x18004ff06  mov     rcx, [rsp+78h+var_20]
0x18004ff0b  xor     rcx, rsp; StackCookie
0x18004ff0e  call    __security_check_cookie
0x18004ff13  mov     rbx, [rsp+78h+arg_18]
0x18004ff1b  add     rsp, 60h
0x18004ff1f  pop     rdi
0x18004ff20  pop     rsi
0x18004ff21  pop     rbp
0x18004ff22  retn
0x18004ff24  mov     rcx, rbp
0x18004ff27  int     29h; Win8: RtlFailFast(ecx)
0x18004ff29  jmp     loc_18004FEA5
0x18004ff2e  mov     rcx, rbp
0x18004ff31  int     29h; Win8: RtlFailFast(ecx)
0x18004ff33  jmp     short loc_18004FEC3
0x18004ff35  mov     rcx, rbp
0x18004ff38  int     29h; Win8: RtlFailFast(ecx)
0x18004ff3a  jmp     short loc_18004FEE4
```
