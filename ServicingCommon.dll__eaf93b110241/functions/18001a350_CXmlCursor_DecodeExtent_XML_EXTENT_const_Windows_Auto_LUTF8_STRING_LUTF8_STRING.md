# CXmlCursor::DecodeExtent(_XML_EXTENT const &,Windows::Auto<_LUTF8_STRING> *,_LUTF8_STRING *)

- ea: `0x18001a350`
- end: `0x18001a52c`
- name: `?DecodeExtent@CXmlCursor@@QEAAJAEBU_XML_EXTENT@@PEAV?$Auto@U_LUTF8_STRING@@@Windows@@PEAU_LUTF8_STRING@@@Z`
- size: `476`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180010c40`
- `0x180015bf8`
- `0x1800164b0`
- `0x180017380`

## callees

- `0x1800031e0`
- `0x1800032b0`
- `0x1800033e0`
- `0x180003550`
- `0x180011214`
- `0x18001a350`
- `0x18001fd10`

## string_xrefs

- `0x18001a423`: `onecore\base\xml\udom_xmlcursor.cpp`
- `0x18001a4d8`: `onecore\base\xml\udom_xmlcursor.cpp`
- `0x18001a43d`: `CXmlCursor::DecodeExtent`
- `0x18001a4f2`: `CXmlCursor::DecodeExtent`
- `0x18001a44f`: `::RtlXmlExtentToUtf8String( 0, &m_State.ParseState.RawTokenState, &Src, TempString.GetMutablePointer(), &cRequired)`

## pseudocode

```c
__int64 __fastcall CXmlCursor::DecodeExtent(__int64 a1, __int64 *a2, _QWORD *a3, _QWORD *a4)
{
  int v6; // r14d
  int v7; // r15d
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 result; // rax
  bool v11; // zf
  int v12; // edi
  int v13; // ecx
  int v14; // edi
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // xmm1_8
  __int64 v19; // rcx
  unsigned __int64 v20; // [rsp+30h] [rbp-48h] BYREF
  __int128 v21; // [rsp+38h] [rbp-40h] BYREF
  __int64 v22; // [rsp+48h] [rbp-30h]
  const char *v23; // [rsp+50h] [rbp-28h] BYREF
  const char *v24; // [rsp+58h] [rbp-20h]
  __int64 v25; // [rsp+60h] [rbp-18h]
  const char *v26; // [rsp+68h] [rbp-10h]

  v6 = (int)a2;
  v7 = a1;
  if ( *(_BYTE *)(a1 + 9376) )
  {
    v8 = a2[1];
    v9 = *a2;
    a4[1] = v8;
    *a4 = v8;
    result = 0;
    a4[2] = v9;
    return result;
  }
  v11 = a3[2] == 0;
  v20 = 0;
  if ( !v11 || (result = RtlAllocateLBlob(a2[1], a3), (int)result >= 0) )
  {
    *a3 = 0;
    v12 = RtlXmlExtentToUtf8String(a1, v7, v6, (_DWORD)a3, (__int64)&v20);
    if ( v12 == -1073741789 )
    {
      v21 = 0;
      v22 = 0;
      v14 = RtlAllocateLBlob(v20, &v21);
      if ( v14 < 0 )
      {
LABEL_9:
        if ( v22 )
          RtlFreeLUtf8String(&v21);
        return (unsigned int)v14;
      }
      v15 = RtlXmlExtentToUtf8String(v13, v7, v6, (unsigned int)&v21, (__int64)&v20);
      v14 = v15;
      if ( v15 < 0 )
      {
        v25 = 119;
        v23 = "onecore\\base\\xml\\udom_xmlcursor.cpp";
        v24 = "CXmlCursor::DecodeExtent";
        v26 = "::RtlXmlExtentToUtf8String( 0, &m_State.ParseState.RawTokenState, &Src, TempString.GetMutablePointer(), &cRequired)";
        RtlReportErrorOrigination(&v23, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v15);
        goto LABEL_9;
      }
      if ( v20 <= *((_QWORD *)&v21 + 1) )
      {
        v18 = v22;
        v19 = a3[2];
        *(_OWORD *)a3 = v21;
        a3[2] = v18;
        if ( v19 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v19, v16, v17);
        goto LABEL_15;
      }
    }
    else
    {
      if ( !v12 )
      {
LABEL_15:
        result = 0;
        *(_OWORD *)a4 = *(_OWORD *)a3;
        a4[2] = a3[2];
        return result;
      }
      if ( v12 < 0 )
      {
        v25 = 126;
        v23 = "onecore\\base\\xml\\udom_xmlcursor.cpp";
        v26 = 0;
        v24 = "CXmlCursor::DecodeExtent";
        RtlReportErrorOrigination(&v23, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v12);
        return (unsigned int)v12;
      }
    }
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18001A52BLL);
  }
  return result;
}

```

## disassembly

```asm
0x18001a350  push    rbp
0x18001a352  push    rbx
0x18001a353  push    rsi
0x18001a354  push    rdi
0x18001a355  push    r14
0x18001a357  push    r15
0x18001a359  mov     rbp, rsp
0x18001a35c  sub     rsp, 78h
0x18001a360  cmp     byte ptr [rcx+24A0h], 0
0x18001a367  mov     rsi, r9
0x18001a36a  mov     rbx, r8
0x18001a36d  mov     r14, rdx
0x18001a370  mov     r15, rcx
0x18001a373  jz      short loc_18001A397
0x18001a375  mov     rax, [rdx+8]
0x18001a379  mov     rcx, [rdx]
0x18001a37c  mov     [r9+8], rax
0x18001a380  mov     [r9], rax
0x18001a383  xor     eax, eax
0x18001a385  mov     [r9+10h], rcx
0x18001a389  add     rsp, 78h
0x18001a38d  pop     r15
0x18001a38f  pop     r14
0x18001a391  pop     rdi
0x18001a392  pop     rsi
0x18001a393  pop     rbx
0x18001a394  pop     rbp
0x18001a395  retn
0x18001a397  cmp     qword ptr [r8+10h], 0
0x18001a39c  mov     [rbp+var_48], 0
0x18001a3a4  jnz     short loc_18001A3BA
0x18001a3a6  mov     rcx, [r14+8]
0x18001a3aa  mov     rdx, rbx
0x18001a3ad  call    RtlAllocateLBlob
0x18001a3b2  test    eax, eax
0x18001a3b4  js      loc_18001A4C4
0x18001a3ba  lea     rax, [rbp+var_48]
0x18001a3be  mov     qword ptr [rbx], 0
0x18001a3c5  mov     r9, rbx
0x18001a3c8  mov     [rsp+78h+var_58], rax
0x18001a3cd  mov     r8, r14
0x18001a3d0  mov     rdx, r15
0x18001a3d3  call    RtlXmlExtentToUtf8String
0x18001a3d8  mov     edi, eax
0x18001a3da  cmp     eax, 0C0000023h
0x18001a3df  jnz     loc_18001A4D2
0x18001a3e5  mov     rcx, [rbp+var_48]
0x18001a3e9  lea     rdx, [rbp+var_40]
0x18001a3ed  xorps   xmm0, xmm0
0x18001a3f0  xor     eax, eax
0x18001a3f2  movups  [rbp+var_40], xmm0
0x18001a3f6  mov     [rbp+var_30], rax
0x18001a3fa  call    RtlAllocateLBlob
0x18001a3ff  mov     edi, eax
0x18001a401  test    eax, eax
0x18001a403  js      short loc_18001A45F
0x18001a405  lea     rax, [rbp+var_48]
0x18001a409  mov     r8, r14
0x18001a40c  lea     r9, [rbp+var_40]
0x18001a410  mov     [rsp+78h+var_58], rax
0x18001a415  mov     rdx, r15
0x18001a418  call    RtlXmlExtentToUtf8String
0x18001a41d  mov     edi, eax
0x18001a41f  test    eax, eax
0x18001a421  jns     short loc_18001A47F
0x18001a423  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_xmlcursor.cpp"
0x18001a42a  mov     [rbp+var_18], 77h ; 'w'
0x18001a432  mov     [rbp+var_28], rax
0x18001a436  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a43d  lea     rax, aCxmlcursorDeco; "CXmlCursor::DecodeExtent"
0x18001a444  mov     r8d, edi
0x18001a447  mov     [rbp+var_20], rax
0x18001a44b  lea     rcx, [rbp+var_28]
0x18001a44f  lea     rax, aRtlxmlextentto_0; "::RtlXmlExtentToUtf8String( 0, &m_State"...
0x18001a456  mov     [rbp+var_10], rax
0x18001a45a  call    RtlReportErrorOrigination
0x18001a45f  cmp     [rbp+var_30], 0
0x18001a464  jz      short loc_18001A46F
0x18001a466  lea     rcx, [rbp+var_40]
0x18001a46a  call    RtlFreeLUtf8String
0x18001a46f  mov     eax, edi
0x18001a471  add     rsp, 78h
0x18001a475  pop     r15
0x18001a477  pop     r14
0x18001a479  pop     rdi
0x18001a47a  pop     rsi
0x18001a47b  pop     rbx
0x18001a47c  pop     rbp
0x18001a47d  retn
0x18001a47f  mov     rax, qword ptr [rbp+var_40+8]
0x18001a483  cmp     [rbp+var_48], rax
0x18001a487  ja      loc_18001A521
0x18001a48d  movsd   xmm2, qword ptr [rbx+10h]
0x18001a492  movups  xmm0, [rbp+var_40]
0x18001a496  movsd   xmm1, [rbp+var_30]
0x18001a49b  movq    rcx, xmm2
0x18001a4a0  movups  xmmword ptr [rbx], xmm0
0x18001a4a3  movsd   qword ptr [rbx+10h], xmm1
0x18001a4a8  test    rcx, rcx
0x18001a4ab  jz      short loc_18001A4B2
0x18001a4ad  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18001a4b2  movups  xmm0, xmmword ptr [rbx]
0x18001a4b5  xor     eax, eax
0x18001a4b7  movups  xmmword ptr [rsi], xmm0
0x18001a4ba  movsd   xmm1, qword ptr [rbx+10h]
0x18001a4bf  movsd   qword ptr [rsi+10h], xmm1
0x18001a4c4  add     rsp, 78h
0x18001a4c8  pop     r15
0x18001a4ca  pop     r14
0x18001a4cc  pop     rdi
0x18001a4cd  pop     rsi
0x18001a4ce  pop     rbx
0x18001a4cf  pop     rbp
0x18001a4d0  retn
0x18001a4d2  test    edi, edi
0x18001a4d4  jz      short loc_18001A4B2
0x18001a4d6  jns     short loc_18001A521
0x18001a4d8  lea     rax, aOnecoreBaseXml_5; "onecore\\base\\xml\\udom_xmlcursor.cpp"
0x18001a4df  mov     [rbp+var_18], 7Eh ; '~'
0x18001a4e7  mov     [rbp+var_28], rax
0x18001a4eb  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a4f2  lea     rax, aCxmlcursorDeco; "CXmlCursor::DecodeExtent"
0x18001a4f9  mov     [rbp+var_10], 0
0x18001a501  mov     r8d, edi
0x18001a504  mov     [rbp+var_20], rax
0x18001a508  lea     rcx, [rbp+var_28]
0x18001a50c  call    RtlReportErrorOrigination
0x18001a511  mov     eax, edi
0x18001a513  add     rsp, 78h
0x18001a517  pop     r15
0x18001a519  pop     r14
0x18001a51b  pop     rdi
0x18001a51c  pop     rsi
0x18001a51d  pop     rbx
0x18001a51e  pop     rbp
0x18001a51f  retn
0x18001a521  mov     ecx, 0C00000E5h; int
0x18001a526  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
