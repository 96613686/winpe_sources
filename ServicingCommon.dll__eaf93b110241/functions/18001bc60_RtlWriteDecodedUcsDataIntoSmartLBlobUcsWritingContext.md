# RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext

- ea: `0x18001bc60`
- end: `0x18001bf39`
- name: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- size: `729`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x18001bf40`
- `0x1800635e0`
- `0x18006a4e0`
- `0x18006a5b0`

## callees

- `0x1800031e0`
- `0x18001afa0`
- `0x18001bc60`
- `0x18001fd10`
- `0x1800293a0`
- `0x1800a0020`

## string_xrefs

- `0x18001bca0`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x18001bcf1`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x18001bd39`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x18001bd67`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x18001bd95`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`
- `0x18001bf06`: `RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext`

## pseudocode

```c
__int64 __fastcall RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext(
        int a1,
        __int64 *a2,
        __int64 (__fastcall *a3)(),
        __int64 a4)
{
  const char *v6; // rax
  __int64 result; // rax
  __int64 v8; // rdi
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ecx
  __int64 *v12; // rbx
  __int64 (__fastcall *v13)(_BYTE *, __int64, __int64); // r12
  __int64 v14; // r14
  __int64 v15; // rax
  const char *v16; // [rsp+20h] [rbp-89h] BYREF
  const char *v17; // [rsp+28h] [rbp-81h]
  __int64 v18; // [rsp+30h] [rbp-79h]
  const char *v19; // [rsp+38h] [rbp-71h]
  _BYTE v20[128]; // [rsp+40h] [rbp-69h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+17h] BYREF

  if ( a1 )
  {
    v18 = 238;
    v16 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v17 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v6 = "Valid flags check failed: Flags";
LABEL_3:
    v19 = v6;
    RtlReportErrorOrigination(&v16, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v18 = 239;
    v16 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v17 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v6 = "Not-null check failed: Data";
    goto LABEL_3;
  }
  v8 = a2[2];
  if ( !v8 && *a2 || (v9 = *a2, *a2 > (unsigned __int64)a2[1]) )
  {
    v18 = 240;
    v16 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v17 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v6 = "::RtlIsLBlobValid(Data)";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v18 = 241;
    v16 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v17 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v6 = "Not-null check failed: Decoder";
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v18 = 242;
    v16 = "onecore\\base\\lstring\\lblob_encoders.cpp";
    v17 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
    v6 = "Not-null check failed: WritingContext";
    goto LABEL_3;
  }
  if ( a3 == RtlDecodeUtf16LE && *(__int64 (__fastcall **)())(a4 + 88) == RtlSmartUcsEncoder_Utf16LE )
  {
    v10 = RtlWriteDataIntoSmartLBlobWritingContext((__int64)a2, (char **)a4);
    v11 = 0;
    if ( v10 < 0 )
      return (unsigned int)v10;
    return v11;
  }
  else
  {
    v12 = (__int64 *)v20;
    v13 = *(__int64 (__fastcall **)(_BYTE *, __int64, __int64))(a4 + 96);
    v14 = v9 + v8;
    if ( v8 != v9 + v8 )
    {
      do
      {
        v15 = ((__int64 (__fastcall *)(const char **, __int64, __int64))a3)(&v16, v8, v14);
        v8 = *(_QWORD *)(v15 + 8);
        if ( *(_DWORD *)v15 == -1 )
        {
          if ( (int)v8 >= 0 )
          {
            INTERNAL_ERROR_ACTION(-1073741595);
            JUMPOUT(0x18001BF38LL);
          }
          v18 = 269;
          v16 = "onecore\\base\\lstring\\lblob_encoders.cpp";
          v17 = "RtlWriteDecodedUcsDataIntoSmartLBlobUcsWritingContext";
          v19 = "__rv.UcsCharacter != (0xffffffff)";
          RtlReportErrorOrigination(&v16, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v8);
          return (unsigned int)v8;
        }
        *(_DWORD *)v12 = *(_DWORD *)v15;
        v12 = (__int64 *)((char *)v12 + 4);
        if ( v12 == &v21 )
        {
          result = v13(v20, 32, a4);
          if ( (int)result < 0 )
            return result;
          v12 = (__int64 *)v20;
        }
      }
      while ( v8 != v14 );
      if ( v12 != (__int64 *)v20 )
      {
        result = v13(v20, ((char *)v12 - v20) >> 2, a4);
        if ( (int)result < 0 )
          return result;
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18001bc60  push    rbp
0x18001bc62  push    rsi
0x18001bc63  push    r15
0x18001bc65  lea     rbp, [rsp-47h]
0x18001bc6a  sub     rsp, 0F0h
0x18001bc71  mov     rax, cs:__security_cookie
0x18001bc78  xor     rax, rsp
0x18001bc7b  mov     [rbp+57h+var_40], rax
0x18001bc7f  mov     rsi, r9
0x18001bc82  mov     r15, r8
0x18001bc85  mov     rax, rdx
0x18001bc88  test    ecx, ecx
0x18001bc8a  jz      short loc_18001BCD8
0x18001bc8c  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x18001bc93  mov     [rbp+57h+var_D0], 0EEh
0x18001bc9b  mov     [rsp+100h+var_E0], rax
0x18001bca0  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x18001bca7  mov     [rsp+100h+var_D8], rax
0x18001bcac  lea     rax, aValidFlagsChec; "Valid flags check failed: Flags"
0x18001bcb3  mov     r8d, 0C000000Dh
0x18001bcb9  mov     [rbp+57h+var_C8], rax
0x18001bcbd  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001bcc4  lea     rcx, [rsp+100h+var_E0]
0x18001bcc9  call    RtlReportErrorOrigination
0x18001bcce  mov     eax, 0C000000Dh
0x18001bcd3  jmp     loc_18001BECE
0x18001bcd8  test    rax, rax
0x18001bcdb  jnz     short loc_18001BD06
0x18001bcdd  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x18001bce4  mov     [rbp+57h+var_D0], 0EFh
0x18001bcec  mov     [rsp+100h+var_E0], rax
0x18001bcf1  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x18001bcf8  mov     [rsp+100h+var_D8], rax
0x18001bcfd  lea     rax, aNotNullCheckFa_15; "Not-null check failed: Data"
0x18001bd04  jmp     short loc_18001BCB3
0x18001bd06  mov     [rsp+100h+var_20], rdi
0x18001bd0e  mov     rdi, [rdx+10h]
0x18001bd12  test    rdi, rdi
0x18001bd15  jnz     short loc_18001BD1C
0x18001bd17  cmp     [rdx], rdi
0x18001bd1a  jnz     short loc_18001BD25
0x18001bd1c  mov     rcx, [rdx]
0x18001bd1f  cmp     rcx, [rdx+8]
0x18001bd23  jbe     short loc_18001BD4E
0x18001bd25  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x18001bd2c  mov     [rbp+57h+var_D0], 0F0h
0x18001bd34  mov     [rsp+100h+var_E0], rax
0x18001bd39  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x18001bd40  mov     [rsp+100h+var_D8], rax
0x18001bd45  lea     rax, aRtlislblobvali_2; "::RtlIsLBlobValid(Data)"
0x18001bd4c  jmp     short loc_18001BDA8
0x18001bd4e  test    r15, r15
0x18001bd51  jnz     short loc_18001BD7C
0x18001bd53  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x18001bd5a  mov     [rbp+57h+var_D0], 0F1h
0x18001bd62  mov     [rsp+100h+var_E0], rax
0x18001bd67  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x18001bd6e  mov     [rsp+100h+var_D8], rax
0x18001bd73  lea     rax, aNotNullCheckFa_84; "Not-null check failed: Decoder"
0x18001bd7a  jmp     short loc_18001BDA8
0x18001bd7c  test    rsi, rsi
0x18001bd7f  jnz     short loc_18001BDCD
0x18001bd81  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x18001bd88  mov     [rbp+57h+var_D0], 0F2h
0x18001bd90  mov     [rsp+100h+var_E0], rax
0x18001bd95  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x18001bd9c  mov     [rsp+100h+var_D8], rax
0x18001bda1  lea     rax, aNotNullCheckFa_13; "Not-null check failed: WritingContext"
0x18001bda8  mov     r8d, 0C000000Dh
0x18001bdae  mov     [rbp+57h+var_C8], rax
0x18001bdb2  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001bdb9  lea     rcx, [rsp+100h+var_E0]
0x18001bdbe  call    RtlReportErrorOrigination
0x18001bdc3  mov     eax, 0C000000Dh
0x18001bdc8  jmp     loc_18001BEC6
0x18001bdcd  lea     rdx, RtlDecodeUtf16LE
0x18001bdd4  cmp     r15, rdx
0x18001bdd7  jnz     short loc_18001BDFF
0x18001bdd9  lea     rdx, RtlSmartUcsEncoder_Utf16LE
0x18001bde0  cmp     [r9+58h], rdx
0x18001bde4  jnz     short loc_18001BDFF
0x18001bde6  mov     rdx, rsi
0x18001bde9  mov     rcx, rax
0x18001bdec  call    RtlWriteDataIntoSmartLBlobWritingContext
0x18001bdf1  xor     ecx, ecx
0x18001bdf3  test    eax, eax
0x18001bdf5  cmovs   ecx, eax
0x18001bdf8  mov     eax, ecx
0x18001bdfa  jmp     loc_18001BEC6
0x18001bdff  mov     [rsp+100h+var_18], rbx
0x18001be07  lea     rbx, [rbp+57h+var_C0]
0x18001be0b  mov     [rsp+100h+var_28], r12
0x18001be13  mov     r12, [r9+60h]
0x18001be17  mov     [rsp+100h+var_30], r14
0x18001be1f  lea     r14, [rcx+rdi]
0x18001be23  cmp     rdi, r14
0x18001be26  jz      loc_18001BEAC
0x18001be2c  nop     dword ptr [rax+00h]
0x18001be30  mov     r8, r14
0x18001be33  lea     rcx, [rsp+100h+var_E0]
0x18001be38  mov     rdx, rdi
0x18001be3b  mov     rax, r15
0x18001be3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be43  mov     ecx, [rax]
0x18001be45  mov     rdi, [rax+8]
0x18001be49  cmp     ecx, 0FFFFFFFFh
0x18001be4c  jz      loc_18001BEE7
0x18001be52  mov     [rbx], ecx
0x18001be54  lea     rax, [rbp+57h+var_40]
0x18001be58  add     rbx, 4
0x18001be5c  cmp     rbx, rax
0x18001be5f  jnz     short loc_18001BE7D
0x18001be61  mov     r8, rsi
0x18001be64  lea     rcx, [rbp+57h+var_C0]
0x18001be68  mov     edx, 20h ; ' '
0x18001be6d  mov     rax, r12
0x18001be70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be75  test    eax, eax
0x18001be77  js      short loc_18001BEAE
0x18001be79  lea     rbx, [rbp+57h+var_C0]
0x18001be7d  cmp     rdi, r14
0x18001be80  jnz     short loc_18001BE30
0x18001be82  lea     rax, [rbp+57h+var_C0]
0x18001be86  cmp     rbx, rax
0x18001be89  jz      short loc_18001BEAC
0x18001be8b  lea     rax, [rbp+57h+var_C0]
0x18001be8f  mov     r8, rsi
0x18001be92  sub     rbx, rax
0x18001be95  lea     rcx, [rbp+57h+var_C0]
0x18001be99  sar     rbx, 2
0x18001be9d  mov     rax, r12
0x18001bea0  mov     rdx, rbx
0x18001bea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bea8  test    eax, eax
0x18001beaa  js      short loc_18001BEAE
0x18001beac  xor     eax, eax
0x18001beae  mov     r12, [rsp+100h+var_28]
0x18001beb6  mov     rbx, [rsp+100h+var_18]
0x18001bebe  mov     r14, [rsp+100h+var_30]
0x18001bec6  mov     rdi, [rsp+100h+var_20]
0x18001bece  mov     rcx, [rbp+57h+var_40]
0x18001bed2  xor     rcx, rsp; StackCookie
0x18001bed5  call    __security_check_cookie
0x18001beda  add     rsp, 0F0h
0x18001bee1  pop     r15
0x18001bee3  pop     rsi
0x18001bee4  pop     rbp
0x18001bee5  retn
0x18001bee7  test    edi, edi
0x18001bee9  jns     short loc_18001BF2E
0x18001beeb  lea     rax, aOnecoreBaseLst_5; "onecore\\base\\lstring\\lblob_encoders."...
0x18001bef2  mov     [rbp+57h+var_D0], 10Dh
0x18001befa  mov     [rsp+100h+var_E0], rax
0x18001beff  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001bf06  lea     rax, aRtlwritedecode_0; "RtlWriteDecodedUcsDataIntoSmartLBlobUcs"...
0x18001bf0d  mov     r8d, edi
0x18001bf10  mov     [rsp+100h+var_D8], rax
0x18001bf15  lea     rcx, [rsp+100h+var_E0]
0x18001bf1a  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x18001bf21  mov     [rbp+57h+var_C8], rax
0x18001bf25  call    RtlReportErrorOrigination
0x18001bf2a  mov     eax, edi
0x18001bf2c  jmp     short loc_18001BEAE
0x18001bf2e  mov     ecx, 0C00000E5h; int
0x18001bf33  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
