# RtlCalculateShaOwfPassword

- ea: `0x1800069f8`
- end: `0x180006b18`
- name: `RtlCalculateShaOwfPassword`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800093e0`
- `0x1800094f0`

## callees

- `0x1800069f8`
- `0x180009664`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180006a7e`
- `bcrypt!BCryptHashData` at `0x180006a7e`
- `bcrypt!BCryptCreateHash` at `0x180006a3a`
- `bcrypt!BCryptCreateHash` at `0x180006a3a`
- `bcrypt!BCryptDestroyHash` at `0x180006b00`
- `bcrypt!BCryptDestroyHash` at `0x180006b00`
- `bcrypt!BCryptFinishHash` at `0x180006ab9`
- `bcrypt!BCryptFinishHash` at `0x180006ab9`

## pseudocode

```c
__int64 __fastcall RtlCalculateShaOwfPassword(PUCHAR *a1, UCHAR *a2)
{
  NTSTATUS v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  BCRYPT_HASH_HANDLE hHash; // [rsp+60h] [rbp+18h] BYREF

  hHash = 0;
  v4 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &hHash, 0, 0, 0, 0, 0);
  if ( v4 >= 0 )
  {
    v4 = BCryptHashData(hHash, a1[1], *(unsigned __int16 *)a1, 0);
    if ( v4 >= 0 )
    {
      v4 = BCryptFinishHash(hHash, a2, 0x14u, 0);
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v6 = 50;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v6 = 49;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v6 = 48;
LABEL_13:
      WPP_SF_D(v5[2], v6, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids, (unsigned int)v4);
    }
  }
  if ( hHash )
    BCryptDestroyHash(hHash);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800069f8  mov     rax, rsp
0x1800069fb  mov     [rax+8], rbx
0x1800069ff  mov     [rax+10h], rsi
0x180006a03  push    rdi
0x180006a04  sub     rsp, 40h
0x180006a08  mov     dword ptr [rax-18h], 0
0x180006a0f  xor     r9d, r9d; cbHashObject
0x180006a12  mov     rsi, rdx
0x180006a15  mov     dword ptr [rax-20h], 0
0x180006a1c  mov     rdi, rcx
0x180006a1f  mov     qword ptr [rax+18h], 0
0x180006a27  xor     r8d, r8d; pbHashObject
0x180006a2a  mov     qword ptr [rax-28h], 0
0x180006a32  lea     ecx, [r9+31h]; hAlgorithm
0x180006a36  lea     rdx, [rax+18h]; phHash
0x180006a3a  call    cs:__imp_BCryptCreateHash
0x180006a40  mov     ebx, eax
0x180006a42  test    eax, eax
0x180006a44  jns     short loc_180006A6E
0x180006a46  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a4d  lea     rax, WPP_GLOBAL_Control
0x180006a54  cmp     rcx, rax
0x180006a57  jz      loc_180006AF6
0x180006a5d  test    byte ptr [rcx+1Ch], 8
0x180006a61  jz      loc_180006AF6
0x180006a67  mov     edx, 30h ; '0'
0x180006a6c  jmp     short loc_180006AE3
0x180006a6e  movzx   r8d, word ptr [rdi]; cbInput
0x180006a72  xor     r9d, r9d; dwFlags
0x180006a75  mov     rdx, [rdi+8]; pbInput
0x180006a79  mov     rcx, [rsp+48h+hHash]; hHash
0x180006a7e  call    cs:__imp_BCryptHashData
0x180006a84  mov     ebx, eax
0x180006a86  test    eax, eax
0x180006a88  jns     short loc_180006AAA
0x180006a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a91  lea     rax, WPP_GLOBAL_Control
0x180006a98  cmp     rcx, rax
0x180006a9b  jz      short loc_180006AF6
0x180006a9d  test    byte ptr [rcx+1Ch], 8
0x180006aa1  jz      short loc_180006AF6
0x180006aa3  mov     edx, 31h ; '1'
0x180006aa8  jmp     short loc_180006AE3
0x180006aaa  mov     rcx, [rsp+48h+hHash]; hHash
0x180006aaf  xor     r9d, r9d; dwFlags
0x180006ab2  mov     rdx, rsi; pbOutput
0x180006ab5  lea     r8d, [r9+14h]; cbOutput
0x180006ab9  call    cs:__imp_BCryptFinishHash
0x180006abf  mov     ebx, eax
0x180006ac1  test    eax, eax
0x180006ac3  jns     short loc_180006AF6
0x180006ac5  mov     rcx, cs:WPP_GLOBAL_Control
0x180006acc  lea     rax, WPP_GLOBAL_Control
0x180006ad3  cmp     rcx, rax
0x180006ad6  jz      short loc_180006AF6
0x180006ad8  test    byte ptr [rcx+1Ch], 8
0x180006adc  jz      short loc_180006AF6
0x180006ade  mov     edx, 32h ; '2'
0x180006ae3  mov     rcx, [rcx+10h]
0x180006ae7  lea     r8, WPP_1719d4e6f7f6337b67c9ada63d044132_Traceguids
0x180006aee  mov     r9d, ebx
0x180006af1  call    WPP_SF_D
0x180006af6  mov     rcx, [rsp+48h+hHash]; hHash
0x180006afb  test    rcx, rcx
0x180006afe  jz      short loc_180006B06
0x180006b00  call    cs:__imp_BCryptDestroyHash
0x180006b06  mov     rsi, [rsp+48h+arg_8]
0x180006b0b  mov     eax, ebx
0x180006b0d  mov     rbx, [rsp+48h+arg_0]
0x180006b12  add     rsp, 40h
0x180006b16  pop     rdi
0x180006b17  retn
```
