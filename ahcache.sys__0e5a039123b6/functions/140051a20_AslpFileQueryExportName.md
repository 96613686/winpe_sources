# AslpFileQueryExportName

- ea: `0x140051a20`
- end: `0x140051d4f`
- name: `AslpFileQueryExportName`
- size: `815`
- prototype: `__int64 __fastcall(char *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x140051954`

## callees

- `0x140001fc8`
- `0x140004445`
- `0x1400045b0`
- `0x140006c90`
- `0x140006cd8`
- `0x1400272d0`
- `0x1400273b8`
- `0x1400273f4`
- `0x140027430`
- `0x1400274cc`
- `0x140036568`
- `0x14003e364`
- `0x140051a20`
- `0x140051e8c`

## string_xrefs

- `0x140051aa1`: `AslpFileGetImageNtHeader failed [%x]`
- `0x140051bc5`: `Export directory invalid or invalid image format`
- `0x140051cd0`: `RtlStringCchCopyA failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileQueryExportName(char *a1, __int64 a2)
{
  __int64 v4; // rdx
  int ImageNtHeader; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rbx
  char IsUserAddress_0; // si
  unsigned __int16 UShortFromUser; // ax
  __int64 v12; // rax
  unsigned int *v13; // r15
  __int64 ULongFromUser; // r15
  __int64 v15; // r11
  void *v16; // r14
  const char *v17; // r9
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // rax
  size_t v21; // rbx
  char *v22; // rsi
  __int64 v24; // [rsp+40h] [rbp-78h] BYREF
  __int64 v25; // [rsp+48h] [rbp-70h]
  __int64 v26; // [rsp+50h] [rbp-68h] BYREF
  __int64 v27; // [rsp+58h] [rbp-60h]
  __int128 v28; // [rsp+60h] [rbp-58h] BYREF
  void *v29; // [rsp+70h] [rbp-48h] BYREF
  __int64 v30; // [rsp+78h] [rbp-40h]
  __int64 v31; // [rsp+C0h] [rbp+8h] BYREF

  v28 = 0;
  v31 = 0;
  AslpMemorySpanInitViewFromFileMapping(&v28, a2);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  *a1 = 0;
  ImageNtHeader = AslpFileGetImageNtHeader(&v31, v4);
  v6 = ImageNtHeader;
  if ( ImageNtHeader >= 0 )
  {
    v9 = v31;
    v24 = v31;
    v25 = 264;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v24, &v28) )
    {
      AslLogCallPrintf(1, "AslpFileQueryExportName", 4351, "Image too small to be a valid PE");
      return (unsigned int)-1073741701;
    }
    IsUserAddress_0 = MmIsUserAddress_0(v9);
    if ( IsUserAddress_0 )
      UShortFromUser = RtlReadUShortFromUser(v9 + 24);
    else
      UShortFromUser = *(_WORD *)(v9 + 24);
    if ( UShortFromUser == 267 )
    {
      v12 = v9 + 120;
    }
    else
    {
      if ( UShortFromUser != 523 )
      {
        AslLogCallPrintf(
          2,
          "AslpFileQueryExportName",
          4383,
          "Unknown image optional header magic value %x",
          UShortFromUser);
        return (unsigned int)-1073741637;
      }
      v12 = v9 + 136;
    }
    v13 = (unsigned int *)(v12 + 4);
    if ( IsUserAddress_0 )
    {
      RtlReadULongFromUser(v12);
      ULongFromUser = (unsigned int)RtlReadULongFromUser(v13);
    }
    else
    {
      ULongFromUser = *v13;
    }
    v26 = AslpImageRvaToVa(v9, a2);
    v27 = ULongFromUser;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v26, &v28) )
    {
      if ( !ULongFromUser && !v15 )
        return (unsigned int)-1073741275;
      AslLogCallPrintf(2, "AslpFileQueryExportName", 4405, "Export directory invalid or invalid image format");
      return (unsigned int)-1073741701;
    }
    if ( IsUserAddress_0 )
      RtlReadULongFromUser(v15 + 12);
    v16 = (void *)AslpImageRvaToVa(v9, a2);
    v29 = v16;
    v30 = 256;
    if ( !(unsigned __int8)AslpMemorySpanCheckBounds(&v29, &v28) )
    {
      v6 = -1073741701;
      v17 = "Export name pointer out of bounds or invalid image format";
      v18 = 4431;
      v19 = 2;
LABEL_26:
      AslLogCallPrintf(v19, "AslpFileQueryExportName", v18, v17);
      return v6;
    }
    if ( IsUserAddress_0 )
    {
      v20 = RtlStringLengthFromUser(v16);
      v21 = v20;
      if ( (unsigned __int64)(v20 + 1) > 0x100 )
      {
        v6 = -2147483643;
        v17 = "Export name too long";
        v18 = 4440;
        v19 = 1;
        goto LABEL_26;
      }
      v22 = &a1[v20];
      if ( (unsigned __int8)MmIsUserAddress_0(a1) )
      {
        RtlCopyToUserFromUser(a1, v16, v21);
        RtlWriteUCharToUser(v22, 0);
      }
      else
      {
        RtlCopyFromUser(a1, v16, v21);
        *v22 = 0;
      }
    }
    else
    {
      ImageNtHeader = RtlStringCchCopyA(a1, 0x100u, (NTSTRSAFE_PCSTR)v16);
      v6 = ImageNtHeader;
      if ( ImageNtHeader < 0 )
      {
        v7 = "RtlStringCchCopyA failed [%x]";
        v8 = 4457;
        goto LABEL_3;
      }
    }
    return 0;
  }
  v7 = "AslpFileGetImageNtHeader failed [%x]";
  v8 = 4340;
LABEL_3:
  AslLogCallPrintf(1, "AslpFileQueryExportName", v8, v7, ImageNtHeader);
  return v6;
}

```

## disassembly

```asm
0x140051a20  mov     rax, rsp
0x140051a23  push    rbx
0x140051a24  push    rsi
0x140051a25  push    rdi
0x140051a26  push    r12
0x140051a28  push    r14
0x140051a2a  push    r15
0x140051a2c  sub     rsp, 88h
0x140051a33  mov     r14, rdx
0x140051a36  mov     rdi, rcx
0x140051a39  xorps   xmm0, xmm0
0x140051a3c  movups  xmmword ptr [rax-58h], xmm0
0x140051a40  mov     qword ptr [rax+8], 0
0x140051a48  lea     rcx, [rax-58h]
0x140051a4c  call    AslpMemorySpanInitViewFromFileMapping
0x140051a51  mov     [rsp+0B8h+var_78], 0
0x140051a5a  mov     [rsp+0B8h+var_70], 0
0x140051a63  mov     [rsp+0B8h+var_68], 0
0x140051a6c  mov     [rsp+0B8h+var_60], 0
0x140051a75  mov     [rsp+0B8h+var_48], 0
0x140051a7e  mov     [rsp+0B8h+var_40], 0
0x140051a87  mov     byte ptr [rdi], 0
0x140051a8a  lea     rcx, [rsp+0B8h+arg_0]
0x140051a92  call    AslpFileGetImageNtHeader
0x140051a97  mov     ebx, eax
0x140051a99  mov     [rsp+0B8h+var_88], eax
0x140051a9d  test    eax, eax
0x140051a9f  jns     short loc_140051AC8
0x140051aa1  lea     r9, aAslpfilegetima_1; "AslpFileGetImageNtHeader failed [%x]"
0x140051aa8  mov     r8d, 10F4h
0x140051aae  mov     [rsp+0B8h+var_98], eax
0x140051ab2  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x140051ab9  mov     ecx, 1
0x140051abe  call    AslLogCallPrintf
0x140051ac3  jmp     loc_140051D10
0x140051ac8  mov     rbx, [rsp+0B8h+arg_0]
0x140051ad0  mov     [rsp+0B8h+var_78], rbx
0x140051ad5  mov     [rsp+0B8h+var_70], 108h
0x140051ade  lea     rdx, [rsp+0B8h+var_58]
0x140051ae3  lea     rcx, [rsp+0B8h+var_78]
0x140051ae8  call    AslpMemorySpanCheckBounds
0x140051aed  test    al, al
0x140051aef  jnz     short loc_140051B19
0x140051af1  lea     r9, aImageTooSmallT; "Image too small to be a valid PE"
0x140051af8  mov     r8d, 10FFh
0x140051afe  mov     ecx, 1
0x140051b03  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x140051b0a  call    AslLogCallPrintf
0x140051b0f  mov     ebx, 0C000007Bh
0x140051b14  jmp     loc_140051D0C
0x140051b19  mov     rcx, rbx
0x140051b1c  call    MmIsUserAddress_0
0x140051b21  mov     sil, al
0x140051b24  test    al, al
0x140051b26  jz      short loc_140051B33
0x140051b28  lea     rcx, [rbx+18h]
0x140051b2c  call    RtlReadUShortFromUser
0x140051b31  jmp     short loc_140051B37
0x140051b33  movzx   eax, word ptr [rbx+18h]
0x140051b37  mov     ecx, 10Bh
0x140051b3c  cmp     ax, cx
0x140051b3f  jnz     short loc_140051B47
0x140051b41  lea     rax, [rbx+78h]
0x140051b45  jmp     short loc_140051B5C
0x140051b47  mov     ecx, 20Bh
0x140051b4c  cmp     ax, cx
0x140051b4f  jnz     loc_140051CE2
0x140051b55  lea     rax, [rbx+88h]
0x140051b5c  lea     r15, [rax+4]
0x140051b60  test    sil, sil
0x140051b63  jz      short loc_140051B7D
0x140051b65  mov     rcx, rax
0x140051b68  call    RtlReadULongFromUser
0x140051b6d  mov     r12d, eax
0x140051b70  mov     rcx, r15
0x140051b73  call    RtlReadULongFromUser
0x140051b78  mov     r15d, eax
0x140051b7b  jmp     short loc_140051B83
0x140051b7d  mov     r12d, [rax]
0x140051b80  mov     r15d, [r15]
0x140051b83  mov     r8d, r12d
0x140051b86  mov     rdx, r14
0x140051b89  mov     rcx, rbx
0x140051b8c  call    AslpImageRvaToVa
0x140051b91  mov     r11, rax
0x140051b94  mov     [rsp+0B8h+var_68], rax
0x140051b99  mov     [rsp+0B8h+var_60], r15
0x140051b9e  lea     rdx, [rsp+0B8h+var_58]
0x140051ba3  lea     rcx, [rsp+0B8h+var_68]
0x140051ba8  call    AslpMemorySpanCheckBounds
0x140051bad  test    al, al
0x140051baf  jnz     short loc_140051BDC
0x140051bb1  test    r15, r15
0x140051bb4  jnz     short loc_140051BC5
0x140051bb6  test    r11, r11
0x140051bb9  jnz     short loc_140051BC5
0x140051bbb  mov     ebx, 0C0000225h
0x140051bc0  jmp     loc_140051D0C
0x140051bc5  lea     r9, aExportDirector; "Export directory invalid or invalid ima"...
0x140051bcc  mov     r8d, 1135h
0x140051bd2  mov     ecx, 2
0x140051bd7  jmp     loc_140051B03
0x140051bdc  test    sil, sil
0x140051bdf  jz      short loc_140051BEC
0x140051be1  lea     rcx, [r11+0Ch]
0x140051be5  call    RtlReadULongFromUser
0x140051bea  jmp     short loc_140051BF0
0x140051bec  mov     eax, [r11+0Ch]
0x140051bf0  mov     r8d, eax
0x140051bf3  mov     rdx, r14
0x140051bf6  mov     rcx, rbx
0x140051bf9  call    AslpImageRvaToVa
0x140051bfe  mov     r14, rax
0x140051c01  mov     [rsp+0B8h+var_48], rax
0x140051c06  mov     r15d, 100h
0x140051c0c  mov     [rsp+0B8h+var_40], r15
0x140051c11  lea     rdx, [rsp+0B8h+var_58]
0x140051c16  lea     rcx, [rsp+0B8h+var_48]
0x140051c1b  call    AslpMemorySpanCheckBounds
0x140051c20  test    al, al
0x140051c22  jnz     short loc_140051C50
0x140051c24  mov     ebx, 0C000007Bh
0x140051c29  lea     r9, aExportNamePoin; "Export name pointer out of bounds or in"...
0x140051c30  mov     r8d, 114Fh
0x140051c36  mov     ecx, 2
0x140051c3b  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x140051c42  mov     [rsp+0B8h+var_88], ebx
0x140051c46  call    AslLogCallPrintf
0x140051c4b  jmp     loc_140051D10
0x140051c50  test    sil, sil
0x140051c53  jz      short loc_140051CB8
0x140051c55  mov     rcx, r14
0x140051c58  call    RtlStringLengthFromUser
0x140051c5d  mov     rbx, rax
0x140051c60  lea     rcx, [rax+1]
0x140051c64  cmp     rcx, r15
0x140051c67  jbe     short loc_140051C82
0x140051c69  mov     ebx, 80000005h
0x140051c6e  lea     r9, aExportNameTooL; "Export name too long"
0x140051c75  mov     r8d, 1158h
0x140051c7b  mov     ecx, 1
0x140051c80  jmp     short loc_140051C3B
0x140051c82  lea     rsi, [rax+rdi]
0x140051c86  mov     rcx, rdi
0x140051c89  call    MmIsUserAddress_0
0x140051c8e  mov     r8, rbx; Size
0x140051c91  mov     rdx, r14; Src
0x140051c94  mov     rcx, rdi; void *
0x140051c97  test    al, al
0x140051c99  jz      short loc_140051CAE
0x140051c9b  call    RtlCopyToUserFromUser
0x140051ca0  xor     edx, edx
0x140051ca2  mov     rcx, rsi
0x140051ca5  call    RtlWriteUCharToUser
0x140051caa  xor     ebx, ebx
0x140051cac  jmp     short loc_140051D0C
0x140051cae  call    RtlCopyFromUser
0x140051cb3  mov     byte ptr [rsi], 0
0x140051cb6  jmp     short loc_140051CAA
0x140051cb8  mov     r8, r14; pszSrc
0x140051cbb  mov     rdx, r15; cchDest
0x140051cbe  mov     rcx, rdi; pszDest
0x140051cc1  call    RtlStringCchCopyA
0x140051cc6  mov     ebx, eax
0x140051cc8  mov     [rsp+0B8h+var_88], eax
0x140051ccc  test    eax, eax
0x140051cce  jns     short loc_140051CAA
0x140051cd0  lea     r9, aRtlstringcchco_1; "RtlStringCchCopyA failed [%x]"
0x140051cd7  mov     r8d, 1169h
0x140051cdd  jmp     loc_140051AAE
0x140051ce2  movzx   eax, ax
0x140051ce5  mov     [rsp+0B8h+var_98], eax
0x140051ce9  lea     r9, aUnknownImageOp; "Unknown image optional header magic val"...
0x140051cf0  mov     r8d, 111Fh
0x140051cf6  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x140051cfd  mov     ecx, 2
0x140051d02  call    AslLogCallPrintf
0x140051d07  mov     ebx, 0C00000BBh
0x140051d0c  mov     [rsp+0B8h+var_88], ebx
0x140051d10  jmp     short loc_140051D3B
0x140051d12  mov     ebx, eax
0x140051d14  mov     [rsp+0B8h+var_88], eax
0x140051d18  mov     [rsp+0B8h+var_98], eax
0x140051d1c  lea     r9, aExceptionEncou_0; "Exception encountered [%x]"
0x140051d23  mov     r8d, 1172h
0x140051d29  lea     rdx, aAslpfilequerye_0; "AslpFileQueryExportName"
0x140051d30  mov     ecx, 1
0x140051d35  call    AslLogCallPrintf
0x140051d3a  nop
0x140051d3b  mov     eax, ebx
0x140051d3d  add     rsp, 88h
0x140051d44  pop     r15
0x140051d46  pop     r14
0x140051d48  pop     r12
0x140051d4a  pop     rdi
0x140051d4b  pop     rsi
0x140051d4c  pop     rbx
0x140051d4d  retn
0x14005bf1a  push    rbp
0x14005bf1c  sub     rsp, 30h
0x14005bf20  mov     rbp, rdx
0x14005bf23  mov     eax, 1
0x14005bf28  add     rsp, 30h
0x14005bf2c  pop     rbp
0x14005bf2d  retn
```
