# LuaCdfCreateFileNameForFile

- ea: `0x18000b490`
- end: `0x18000ba18`
- name: `LuaCdfCreateFileNameForFile`
- size: `1416`
- prototype: `__int64 __fastcall(PCWSTR DosPathName)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18000b1c0`

## callees

- `0x180004f20`
- `0x180009820`
- `0x18000a610`
- `0x18000b490`
- `0x18000bcd0`
- `0x18000bd10`
- `0x18000c478`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x180097e20`
- `0x1800981e0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000b9fd`
- `ntdll!RtlFreeUnicodeString` at `0x18000b9fd`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000b536`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18000b536`
- `ntdll!RtlCopyUnicodeString` at `0x18000b7ad`
- `ntdll!RtlCopyUnicodeString` at `0x18000b7ad`

## pseudocode

```c
__int64 __fastcall LuaCdfCreateFileNameForFile(
        PCWSTR DosPathName,
        PCWSTR *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  BOOLEAN v8; // al
  PCWSTR v9; // rcx
  PWSTR Buffer; // rax
  unsigned __int64 v11; // rax
  int v12; // ebx
  size_t v14; // rsi
  __int64 v15; // rdi
  _DWORD *v16; // rcx
  PWSTR v17; // rdx
  unsigned __int64 v18; // rcx
  WCHAR v19; // r8
  size_t v20; // rdi
  USHORT v21; // bx
  __int64 StringRoutine; // rax
  unsigned __int16 MaximumLength; // dx
  unsigned __int64 Length; // rbx
  PWSTR v25; // rcx
  const char *v26; // rax
  const char *v27; // rax
  __int128 v28; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+38h] [rbp-D0h]
  const char *Size; // [rsp+40h] [rbp-C8h]
  size_t Size_8[2]; // [rsp+48h] [rbp-C0h] BYREF
  void *Src; // [rsp+58h] [rbp-B0h]
  PCWSTR NtFileNamePart; // [rsp+60h] [rbp-A8h] BYREF
  int v34; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v35; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v36; // [rsp+80h] [rbp-88h]
  _BYTE v37[256]; // [rsp+88h] [rbp-80h] BYREF

  Src = 0;
  v29 = 0;
  v36 = 0;
  NtFileNamePart = 0;
  *(_OWORD *)Size_8 = 0;
  v28 = 0;
  v35 = 0;
  memset(v37, 0, 0xF8u);
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = RtlDosPathNameToNtPathName_U(DosPathName, a3, &NtFileNamePart, 0);
  v9 = NtFileNamePart;
  *a2 = NtFileNamePart;
  if ( !v8 )
  {
    v12 = -1073741801;
    goto LABEL_12;
  }
  if ( !v9 )
    goto LABEL_39;
  Buffer = a3->Buffer;
  if ( *Buffer != 92 || Buffer[1] != 63 || Buffer[2] != 63 || Buffer[3] != 92 )
  {
    RtlFreeUnicodeString(a3);
    *a3 = 0;
    *a2 = 0;
    goto LABEL_39;
  }
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(2 * v11 + 0x7FFE0030) );
  if ( v11 > 0x7FFFFFFFFFFFFFFELL )
  {
    v29 = 393;
    *(_QWORD *)&v28 = "onecore\\base\\lstring\\lunicode_string.cpp";
    *((_QWORD *)&v28 + 1) = "RtlInitLUnicodeStringFromNullTerminatedString";
    Size = "cch <= (((((SIZE_T)~((SIZE_T)0)) - (((SIZE_T)~((SIZE_T)0)) % sizeof(WCHAR))) / sizeof(WCHAR)) - 1)";
    RtlReportErrorOrigination(&v28, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221226539LL);
    v12 = -1073740757;
    goto LABEL_12;
  }
  v14 = 2 * v11;
  v15 = 2 * v11 + 8;
  if ( 2 * v11 >= 0xFFFFFFFFFFFFFFF8uLL )
    goto LABEL_11;
  if ( v36 )
    __debugbreak();
  if ( !(unsigned __int8)RtlIsLUnicodeStringValid(&v35) )
  {
    v29 = 1273;
    *(_QWORD *)&v28 = "onecore\\base\\lstring\\lunicode_string.cpp";
    *((_QWORD *)&v28 + 1) = "RtlReallocateLUnicodeString";
    v27 = "::RtlIsLUnicodeStringValid(String)";
    goto LABEL_48;
  }
  v12 = RtlReallocateLBlob(0, v15, &v35);
  if ( v12 >= 0 )
  {
    v16 = v36;
    *v36 = 4128860;
    v16[1] = 6029375;
    memmove(v16 + 2, (const void *)0x7FFE0030, v14);
    v17 = a3->Buffer;
    *(_QWORD *)&v35 = v15;
    v18 = 2 * (NtFileNamePart - v17);
    if ( v18 )
    {
      v19 = v17[(v18 >> 1) - 1];
      if ( v19 == 92 || v19 == 47 )
        v18 -= 2LL;
    }
    Size_8[0] = 0;
    v29 = (__int64)(v17 + 4);
    *(_QWORD *)&v28 = v18 - 8;
    Src = v37;
    *((_QWORD *)&v28 + 1) = v18 - 8;
    Size_8[1] = 248;
    v12 = ((__int64 (__fastcall *)(unsigned __int64, __int128 *, __int128 *, size_t *))LuaCdfGenerateFilemapFileName)(
            v18 - 8,
            &v28,
            &v35,
            Size_8);
    if ( v12 >= 0 )
    {
      v20 = Size_8[0];
      if ( Size_8[0] <= 0xFFFF )
      {
        v21 = LOWORD(Size_8[0]) + 56;
        if ( (unsigned __int16)(LOWORD(Size_8[0]) + 56) >= LOWORD(Size_8[0]) )
        {
          *(_DWORD *)&a4->Length = 0;
          a4->Buffer = 0;
          if ( (v21 & 1) == 0 )
          {
            if ( v21 )
            {
              StringRoutine = anonymous_namespace_::OurRtlAllocateStringRoutine((unsigned __int16)(v20 + 56));
              a4->Buffer = (PWSTR)StringRoutine;
              if ( !StringRoutine )
              {
                v29 = 61;
                *(_QWORD *)&v28 = "onecore\\base\\lstring\\lunicode_string.cpp";
                *((_QWORD *)&v28 + 1) = "RtlAllocateUnicodeString";
                Size = "String->Buffer = reinterpret_cast<PWSTR>((*RtlAllocateStringRoutine)(Bytes))";
                RtlReportErrorOrigination(&v28, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
                v12 = -1073741801;
                goto LABEL_12;
              }
              a4->MaximumLength = v21;
            }
            RtlCopyUnicodeString(a4, &SourceString);
            MaximumLength = a4->MaximumLength;
            Length = a4->Length;
            v34 = 0;
            if ( (((unsigned __int16)Length | MaximumLength) & 1) != 0
              || (unsigned __int16)Length > MaximumLength
              || (v25 = a4->Buffer) == 0 && (_WORD)Length )
            {
              v29 = 706;
              *(_QWORD *)&v28 = "onecore\\base\\lstring\\lunicode_string.cpp";
              *((_QWORD *)&v28 + 1) = "RtlAppendLUnicodeStringToUnicodeString";
              v26 = "::RtlIsUnicodeStringValid(Destination)";
            }
            else
            {
              if ( (v20 & 1) == 0 && (Size_8[1] & 1) == 0 && v20 <= Size_8[1] && (Src || !v20) )
              {
                if ( (unsigned __int16)(MaximumLength - Length) < v20 )
                {
                  v29 = 718;
                  *(_QWORD *)&v28 = "onecore\\base\\lstring\\lunicode_string.cpp";
                  Size = 0;
                  *((_QWORD *)&v28 + 1) = "RtlAppendLUnicodeStringToUnicodeString";
                  RtlReportErrorOrigination(&v28, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 2147483653LL);
                  v12 = -2147483643;
                  goto LABEL_12;
                }
                memmove(&v25[Length >> 1], Src, v20);
                a4->Length = Length + v20;
                goto LABEL_39;
              }
              v29 = 708;
              *(_QWORD *)&v28 = "onecore\\base\\lstring\\lunicode_string.cpp";
              *((_QWORD *)&v28 + 1) = "RtlAppendLUnicodeStringToUnicodeString";
              v26 = "::RtlIsLUnicodeStringValid(Source)";
            }
            Size = v26;
            v12 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                    &v34,
                    &v28);
            if ( v12 < 0 )
              goto LABEL_12;
LABEL_39:
            v12 = 0;
            goto LABEL_12;
          }
          v29 = 57;
          *(_QWORD *)&v28 = "onecore\\base\\lstring\\lunicode_string.cpp";
          *((_QWORD *)&v28 + 1) = "RtlAllocateUnicodeString";
          v27 = "(Bytes % sizeof(WCHAR)) == 0";
LABEL_48:
          Size = v27;
          RtlReportErrorOrigination(&v28, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
          v12 = -1073741811;
          goto LABEL_12;
        }
      }
LABEL_11:
      v12 = -1073741675;
    }
  }
LABEL_12:
  if ( v36 )
    RtlFreeLUtf8String(&v35);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b490  mov     r11, rsp
0x18000b493  push    rbp
0x18000b494  push    rbx
0x18000b495  lea     rbp, [r11-0D8h]
0x18000b49c  sub     rsp, 1C8h
0x18000b4a3  mov     rax, cs:__security_cookie
0x18000b4aa  xor     rax, rsp
0x18000b4ad  mov     [rbp+0D0h+var_50], rax
0x18000b4b4  mov     [r11-18h], rsi
0x18000b4b8  xor     eax, eax
0x18000b4ba  mov     [r11-20h], rdi
0x18000b4be  xorps   xmm0, xmm0
0x18000b4c1  mov     [r11-28h], r12
0x18000b4c5  mov     rdi, rdx
0x18000b4c8  mov     [r11-30h], r13
0x18000b4cc  mov     rbx, rcx
0x18000b4cf  mov     [r11-38h], r14
0x18000b4d3  lea     rcx, [rbp+0D0h+var_150]; void *
0x18000b4d7  mov     r14, r8
0x18000b4da  mov     [r11-40h], r15
0x18000b4de  xorps   xmm1, xmm1
0x18000b4e1  mov     [rsp+1D0h+Src], rax
0x18000b4e6  xor     r13d, r13d
0x18000b4e9  mov     [rsp+1D0h+var_1A0], rax
0x18000b4ee  mov     r8d, 0F8h; Size
0x18000b4f4  mov     [rsp+1D0h+var_158], rax
0x18000b4f9  xor     edx, edx; Val
0x18000b4fb  mov     [rsp+1D0h+NtFileNamePart], r13
0x18000b500  mov     r15, r9
0x18000b503  movups  xmmword ptr [rsp+1D0h+Size+8], xmm0
0x18000b508  movups  [rsp+1D0h+var_1B8+8], xmm1
0x18000b50d  movups  [rsp+1D0h+var_170+8], xmm0
0x18000b512  call    memset
0x18000b517  mov     [rdi], r13
0x18000b51a  lea     r8, [rsp+1D0h+NtFileNamePart]; NtFileNamePart
0x18000b51f  xorps   xmm0, xmm0
0x18000b522  xorps   xmm1, xmm1
0x18000b525  movups  xmmword ptr [r14], xmm0
0x18000b529  xor     r9d, r9d; DirectoryInfo
0x18000b52c  mov     rdx, r14; NtPathName
0x18000b52f  mov     rcx, rbx; DosPathName
0x18000b532  movups  xmmword ptr [r15], xmm1
0x18000b536  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18000b53d  nop     dword ptr [rax+rax+00h]
0x18000b542  mov     rcx, [rsp+1D0h+NtFileNamePart]
0x18000b547  mov     [rdi], rcx
0x18000b54a  test    al, al
0x18000b54c  jz      loc_18000B8DE
0x18000b552  test    rcx, rcx
0x18000b555  jz      loc_18000B83F
0x18000b55b  mov     rax, [r14+8]
0x18000b55f  cmp     word ptr [rax], 5Ch ; '\'
0x18000b563  jnz     loc_18000B9FA
0x18000b569  cmp     word ptr [rax+2], 3Fh ; '?'
0x18000b56e  jnz     loc_18000B9FA
0x18000b574  cmp     word ptr [rax+4], 3Fh ; '?'
0x18000b579  jnz     loc_18000B9FA
0x18000b57f  cmp     word ptr [rax+6], 5Ch ; '\'
0x18000b584  jnz     loc_18000B9FA
0x18000b58a  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000b591  mov     r12d, 7FFE0030h
0x18000b597  nop     word ptr [rax+rax+00000000h]
0x18000b5a0  inc     rax
0x18000b5a3  cmp     [r12+rax*2], r13w
0x18000b5a8  jnz     short loc_18000B5A0
0x18000b5aa  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18000b5b4  cmp     rax, rcx
0x18000b5b7  jbe     loc_18000B66D
0x18000b5bd  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000b5c4  mov     [rsp+1D0h+var_1A0], 189h
0x18000b5cd  mov     qword ptr [rsp+1D0h+var_1B8+8], rax
0x18000b5d2  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000b5d9  lea     rax, aRtlinitlunicod_1; "RtlInitLUnicodeStringFromNullTerminated"...
0x18000b5e0  mov     r8d, 0C000042Bh
0x18000b5e6  mov     [rsp+1D0h+var_1A8], rax
0x18000b5eb  lea     rcx, [rsp+1D0h+var_1B8+8]
0x18000b5f0  lea     rax, aCchSizeTSizeT0; "cch <= (((((SIZE_T)~((SIZE_T)0)) - (((S"...
0x18000b5f7  mov     [rsp+1D0h+Size], rax
0x18000b5fc  call    RtlReportErrorOrigination
0x18000b601  mov     ebx, 0C000042Bh
0x18000b606  jmp     short loc_18000B60D
0x18000b608  mov     ebx, 0C0000095h
0x18000b60d  cmp     [rsp+1D0h+var_158], 0
0x18000b613  mov     r15, [rsp+1D0h+var_38]
0x18000b61b  mov     r14, [rsp+1D0h+var_30]
0x18000b623  mov     r13, [rsp+1D0h+var_28]
0x18000b62b  mov     r12, [rsp+1D0h+var_20]
0x18000b633  mov     rdi, [rsp+1D0h+var_18]
0x18000b63b  mov     rsi, [rsp+1C0h]
0x18000b643  jnz     short loc_18000B661
0x18000b645  mov     eax, ebx
0x18000b647  mov     rcx, [rbp+0D0h+var_50]
0x18000b64e  xor     rcx, rsp; StackCookie
0x18000b651  call    __security_check_cookie
0x18000b656  add     rsp, 1C8h
0x18000b65d  pop     rbx
0x18000b65e  pop     rbp
0x18000b65f  retn
0x18000b661  lea     rcx, [rsp+1D0h+var_170+8]
0x18000b666  call    RtlFreeLUtf8String
0x18000b66b  jmp     short loc_18000B645
0x18000b66d  lea     rsi, [rax+rax]
0x18000b671  lea     rdi, [rsi+8]
0x18000b675  cmp     rdi, 8
0x18000b679  jb      short loc_18000B608
0x18000b67b  cmp     [rsp+1D0h+var_158], r13
0x18000b680  jnz     loc_18000B8E8
0x18000b686  lea     rcx, [rsp+1D0h+var_170+8]
0x18000b68b  call    RtlIsLUnicodeStringValid
0x18000b690  test    al, al
0x18000b692  jz      loc_18000B8EE
0x18000b698  lea     r8, [rsp+1D0h+var_170+8]
0x18000b69d  mov     rdx, rdi
0x18000b6a0  xor     ecx, ecx
0x18000b6a2  call    RtlReallocateLBlob
0x18000b6a7  mov     ebx, eax
0x18000b6a9  test    eax, eax
0x18000b6ab  js      loc_18000B60D
0x18000b6b1  mov     rcx, [rsp+1D0h+var_158]
0x18000b6b6  mov     r8, rsi; Size
0x18000b6b9  mov     rdx, r12; Src
0x18000b6bc  mov     dword ptr [rcx], 3F005Ch
0x18000b6c2  mov     dword ptr [rcx+4], 5C003Fh
0x18000b6c9  add     rcx, 8; void *
0x18000b6cd  call    memmove
0x18000b6d2  mov     rdx, [r14+8]
0x18000b6d6  mov     rax, [rsp+1D0h+NtFileNamePart]
0x18000b6db  sub     rax, rdx
0x18000b6de  mov     qword ptr [rsp+1D0h+var_170+8], rdi
0x18000b6e3  sar     rax, 1
0x18000b6e6  lea     rcx, [rax+rax]
0x18000b6ea  test    rcx, rcx
0x18000b6ed  jz      short loc_18000B70A
0x18000b6ef  mov     rax, rcx
0x18000b6f2  shr     rax, 1
0x18000b6f5  movzx   r8d, word ptr [rdx+rax*2-2]
0x18000b6fb  cmp     r8w, 5Ch ; '\'
0x18000b700  jnz     loc_18000B966
0x18000b706  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18000b70a  lea     rax, [rdx+8]
0x18000b70e  mov     [rsp+1D0h+Size+8], r13
0x18000b713  sub     rcx, 8
0x18000b717  mov     [rsp+1D0h+var_1A0], rax
0x18000b71c  lea     rax, [rbp+0D0h+var_150]
0x18000b720  mov     qword ptr [rsp+1D0h+var_1B8+8], rcx
0x18000b725  lea     r9, [rsp+1D0h+Size+8]
0x18000b72a  mov     [rsp+1D0h+Src], rax
0x18000b72f  lea     r8, [rsp+1D0h+var_170+8]
0x18000b734  mov     [rsp+1D0h+var_1A8], rcx
0x18000b739  lea     rdx, [rsp+1D0h+var_1B8+8]
0x18000b73e  mov     [rsp+1D0h+var_188], 0F8h
0x18000b747  call    LuaCdfGenerateFilemapFileName
0x18000b74c  mov     ebx, eax
0x18000b74e  test    eax, eax
0x18000b750  js      loc_18000B60D
0x18000b756  mov     rdi, [rsp+1D0h+Size+8]
0x18000b75b  cmp     rdi, 0FFFFh
0x18000b762  ja      loc_18000B608
0x18000b768  lea     ebx, [rdi+38h]
0x18000b76b  cmp     bx, di
0x18000b76e  jb      loc_18000B608
0x18000b774  mov     [r15], r13d
0x18000b777  mov     [r15+8], r13
0x18000b77b  test    bl, 1
0x18000b77e  jnz     loc_18000B918
0x18000b784  test    bx, bx
0x18000b787  jz      short loc_18000B7A3
0x18000b789  movzx   ecx, bx
0x18000b78c  call    _anonymous_namespace___OurRtlAllocateStringRoutine
0x18000b791  mov     [r15+8], rax
0x18000b795  test    rax, rax
0x18000b798  jz      loc_18000B976
0x18000b79e  mov     [r15+2], bx
0x18000b7a3  lea     rdx, SourceString; SourceString
0x18000b7aa  mov     rcx, r15; DestinationString
0x18000b7ad  call    cs:__imp_RtlCopyUnicodeString
0x18000b7b4  nop     dword ptr [rax+rax+00h]
0x18000b7b9  movzx   edx, word ptr [r15+2]
0x18000b7be  movzx   ebx, word ptr [r15]
0x18000b7c2  movzx   ecx, dx
0x18000b7c5  or      cx, bx
0x18000b7c8  mov     dword ptr [rsp+1D0h+var_170], r13d
0x18000b7cd  bt      cx, r13w
0x18000b7d2  jb      loc_18000B9CD
0x18000b7d8  cmp     bx, dx
0x18000b7db  ja      loc_18000B9CD
0x18000b7e1  mov     rcx, [r15+8]
0x18000b7e5  test    rcx, rcx
0x18000b7e8  jz      loc_18000B9C4
0x18000b7ee  test    dil, 1
0x18000b7f2  jnz     loc_18000B893
0x18000b7f8  mov     rax, [rsp+1D0h+var_188]
0x18000b7fd  test    al, 1
0x18000b7ff  jnz     loc_18000B893
0x18000b805  cmp     rdi, rax
0x18000b808  ja      loc_18000B893
0x18000b80e  mov     r9, [rsp+1D0h+Src]
0x18000b813  test    r9, r9
0x18000b816  jz      short loc_18000B88E
0x18000b818  sub     dx, bx
0x18000b81b  movzx   eax, dx
0x18000b81e  cmp     rax, rdi
0x18000b821  jb      short loc_18000B847
0x18000b823  mov     rax, rbx
0x18000b826  mov     r8, rdi; Size
0x18000b829  shr     rax, 1
0x18000b82c  mov     rdx, r9; Src
0x18000b82f  lea     rcx, [rcx+rax*2]; void *
0x18000b833  call    memmove
0x18000b838  add     di, bx
0x18000b83b  mov     [r15], di
0x18000b83f  mov     ebx, r13d
0x18000b842  jmp     loc_18000B60D
0x18000b847  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000b84e  mov     [rsp+1D0h+var_1A0], 2CEh
0x18000b857  mov     qword ptr [rsp+1D0h+var_1B8+8], rax
0x18000b85c  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000b863  lea     rax, aRtlappendlunic_1; "RtlAppendLUnicodeStringToUnicodeString"
0x18000b86a  mov     [rsp+1D0h+Size], r13
0x18000b86f  mov     r8d, 80000005h
0x18000b875  mov     [rsp+1D0h+var_1A8], rax
0x18000b87a  lea     rcx, [rsp+1D0h+var_1B8+8]
0x18000b87f  call    RtlReportErrorOrigination
0x18000b884  mov     ebx, 80000005h
0x18000b889  jmp     loc_18000B60D
0x18000b88e  test    rdi, rdi
0x18000b891  jz      short loc_18000B818
0x18000b893  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000b89a  mov     [rsp+1D0h+var_1A0], 2C4h
0x18000b8a3  mov     qword ptr [rsp+1D0h+var_1B8+8], rax
0x18000b8a8  lea     rax, aRtlappendlunic_1; "RtlAppendLUnicodeStringToUnicodeString"
0x18000b8af  mov     [rsp+1D0h+var_1A8], rax
0x18000b8b4  lea     rax, aRtlislunicodes_13; "::RtlIsLUnicodeStringValid(Source)"
0x18000b8bb  lea     rdx, [rsp+1D0h+var_1B8+8]
0x18000b8c0  mov     [rsp+1D0h+Size], rax
0x18000b8c5  lea     rcx, [rsp+1D0h+var_170]
0x18000b8ca  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18000b8cf  mov     ebx, eax
0x18000b8d1  test    eax, eax
0x18000b8d3  jns     loc_18000B83F
0x18000b8d9  jmp     loc_18000B60D
0x18000b8de  mov     ebx, 0C0000017h
0x18000b8e3  jmp     loc_18000B60D
0x18000b8e8  int     3; Trap to Debugger
0x18000b8e9  jmp     loc_18000B686
0x18000b8ee  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000b8f5  mov     [rsp+1D0h+var_1A0], 4F9h
0x18000b8fe  mov     qword ptr [rsp+1D0h+var_1B8+8], rax
0x18000b903  lea     rax, aRtlreallocatel_2; "RtlReallocateLUnicodeString"
0x18000b90a  mov     [rsp+1D0h+var_1A8], rax
0x18000b90f  lea     rax, aRtlislunicodes_14; "::RtlIsLUnicodeStringValid(String)"
0x18000b916  jmp     short loc_18000B940
0x18000b918  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000b91f  mov     [rsp+1D0h+var_1A0], 39h ; '9'
0x18000b928  mov     qword ptr [rsp+1D0h+var_1B8+8], rax
0x18000b92d  lea     rax, aRtlallocateuni_0; "RtlAllocateUnicodeString"
0x18000b934  mov     [rsp+1D0h+var_1A8], rax
0x18000b939  lea     rax, aBytesSizeofWch; "(Bytes % sizeof(WCHAR)) == 0"
0x18000b940  mov     r8d, 0C000000Dh
0x18000b946  mov     [rsp+1D0h+Size], rax
0x18000b94b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000b952  lea     rcx, [rsp+1D0h+var_1B8+8]
0x18000b957  call    RtlReportErrorOrigination
0x18000b95c  mov     ebx, 0C000000Dh
0x18000b961  jmp     loc_18000B60D
0x18000b966  cmp     r8w, 2Fh ; '/'
0x18000b96b  jnz     loc_18000B70A
0x18000b971  jmp     loc_18000B706
0x18000b976  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000b97d  mov     [rsp+1D0h+var_1A0], 3Dh ; '='
0x18000b986  mov     qword ptr [rsp+1D0h+var_1B8+8], rax
0x18000b98b  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18000b992  lea     rax, aRtlallocateuni_0; "RtlAllocateUnicodeString"
0x18000b999  mov     r8d, 0C0000017h
0x18000b99f  mov     [rsp+1D0h+var_1A8], rax
0x18000b9a4  lea     rcx, [rsp+1D0h+var_1B8+8]
0x18000b9a9  lea     rax, aStringBufferRe; "String->Buffer = reinterpret_cast<PWSTR"...
0x18000b9b0  mov     [rsp+1D0h+Size], rax
0x18000b9b5  call    RtlReportErrorOrigination
0x18000b9ba  mov     ebx, 0C0000017h
0x18000b9bf  jmp     loc_18000B60D
0x18000b9c4  test    bx, bx
0x18000b9c7  jz      loc_18000B7EE
0x18000b9cd  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000b9d4  mov     [rsp+1D0h+var_1A0], 2C2h
0x18000b9dd  mov     qword ptr [rsp+1D0h+var_1B8+8], rax
0x18000b9e2  lea     rax, aRtlappendlunic_1; "RtlAppendLUnicodeStringToUnicodeString"
0x18000b9e9  mov     [rsp+1D0h+var_1A8], rax
0x18000b9ee  lea     rax, aRtlisunicodest; "::RtlIsUnicodeStringValid(Destination)"
0x18000b9f5  jmp     loc_18000B8BB
0x18000b9fa  mov     rcx, r14; UnicodeString
0x18000b9fd  call    cs:__imp_RtlFreeUnicodeString
0x18000ba04  nop     dword ptr [rax+rax+00h]
0x18000ba09  xorps   xmm0, xmm0
0x18000ba0c  movups  xmmword ptr [r14], xmm0
0x18000ba10  mov     [rdi], r13
0x18000ba13  jmp     loc_18000B83F
```
