# sub_14078BFCC

- ea: `0x14078bfcc`
- end: `0x14078ccbc`
- name: `sub_14078BFCC`
- size: `3312`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14078d2b0`

## callees

- `0x140021ab8`
- `0x1400279b0`
- `0x140045380`
- `0x140057bb0`
- `0x14006ee4c`
- `0x140141978`
- `0x140193970`
- `0x1402f35d4`
- `0x140328ef8`
- `0x1403e1680`
- `0x1405d3298`
- `0x14078bfcc`
- `0x1407b0e20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078c436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078c629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078c6fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078c8f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078cab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078c436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078c629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078c6fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078c8f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14078cab3`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14078c035`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x14078c035`

## pseudocode

```c
__int64 __fastcall sub_14078BFCC(__int64 a1, __int64 a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // rcx
  const WCHAR *v8; // rdx
  unsigned __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // edi
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rcx
  _BYTE v32[8]; // [rsp+30h] [rbp-288h] BYREF
  __int64 v33; // [rsp+38h] [rbp-280h] BYREF
  __int128 v34; // [rsp+40h] [rbp-278h] BYREF
  _BYTE v35[16]; // [rsp+50h] [rbp-268h] BYREF
  HSTRING string; // [rsp+60h] [rbp-258h] BYREF
  __int64 v37; // [rsp+68h] [rbp-250h] BYREF
  __int64 v38; // [rsp+70h] [rbp-248h] BYREF
  void **v39; // [rsp+78h] [rbp-240h] BYREF
  __int128 *v40; // [rsp+80h] [rbp-238h]
  _BYTE *v41; // [rsp+88h] [rbp-230h]
  __int64 v42; // [rsp+90h] [rbp-228h] BYREF
  _QWORD v43[9]; // [rsp+98h] [rbp-220h] BYREF
  void **v44; // [rsp+E0h] [rbp-1D8h] BYREF
  __int128 v45; // [rsp+E8h] [rbp-1D0h] BYREF
  __m128i si128; // [rsp+F8h] [rbp-1C0h]
  void **v47; // [rsp+110h] [rbp-1A8h] BYREF
  __int64 v48; // [rsp+118h] [rbp-1A0h] BYREF
  __int128 v49; // [rsp+120h] [rbp-198h]
  char v50; // [rsp+130h] [rbp-188h]
  __int128 v51; // [rsp+138h] [rbp-180h] BYREF
  __int64 v52; // [rsp+148h] [rbp-170h]
  __int64 v53; // [rsp+150h] [rbp-168h]
  HSTRING_HEADER hstringHeader; // [rsp+160h] [rbp-158h] BYREF
  __int64 v55; // [rsp+178h] [rbp-140h]

  v43[1] = a2;
  v33 = 0;
  v55 = 0;
  sub_14006EE4C(&hstringHeader, L"Windows.Management.Deployment.PackageManager");
  v4 = RoActivateInstance(v55, &v33);
  v55 = 0;
  if ( v4 < 0 )
  {
    sub_140021AB8((__int64)&hstringHeader, L"Failed to initialize Windows Runtime (WinRT).");
    v47 = &C2R::ContextData::`vftable';
    v48 = 0;
    v49 = 0;
    v50 = 7;
    v51 = 0;
    v52 = 0;
    v53 = 7;
    LOWORD(v51) = 0;
    v34 = 0;
    sub_140328EF8(&v48, &v34);
    v50 = 7;
    sub_1400279B0((char *)&v51, (char *)&hstringHeader, v5);
    v47 = &C2R::ContextData::`vftable';
    v44 = &C2R::CommonTelemetry::`vftable';
    v45 = 0;
    si128 = _mm_load_si128((const __m128i *)&xmmword_14082E430);
    LOWORD(v45) = 0;
    if ( sub_140057BB0(504647830, 0x3B0u, 0xAu, 0) )
    {
      *(_QWORD *)&v34 = &v44;
      *((_QWORD *)&v34 + 1) = &v47;
      v39 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v40 = &v34;
      v41 = v35;
      sub_140141978(
        504647830,
        944,
        10,
        0,
        (__int64)L"C2R::DeploymentOnline::RichInteraction::VersionCheck::CurrentVersion",
        (__int64)&v39);
    }
    sub_140045380(&v45);
    sub_140193970(&v47);
    sub_140045380(&hstringHeader);
    *(_BYTE *)(a2 + 40) = 0;
    v6 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return a2;
  }
  if ( !v33 )
  {
    sub_140021AB8((__int64)&hstringHeader, L"Failed to activate package manager instance.");
    v47 = &C2R::ContextData::`vftable';
    v48 = 0;
    v49 = 0;
    v50 = 7;
    v51 = 0;
    v52 = 0;
    v53 = 7;
    LOWORD(v51) = 0;
    v34 = 0;
    sub_140328EF8(&v48, &v34);
    v50 = 7;
    sub_1400279B0((char *)&v51, (char *)&hstringHeader, v30);
    v47 = &C2R::ContextData::`vftable';
    v44 = &C2R::CommonTelemetry::`vftable';
    v45 = 0;
    si128 = _mm_load_si128((const __m128i *)&xmmword_14082E430);
    LOWORD(v45) = 0;
    if ( sub_140057BB0(504647829, 0x3B0u, 0x32u, 0) )
    {
      *(_QWORD *)&v34 = &v44;
      *((_QWORD *)&v34 + 1) = &v47;
      v39 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v40 = &v34;
      v41 = v35;
      sub_140141978(
        504647829,
        944,
        50,
        0,
        (__int64)L"C2R::DeploymentOnline::RichInteraction::VersionCheck::CurrentVersion",
        (__int64)&v39);
    }
    sub_140045380(&v45);
    sub_140193970(&v47);
    sub_140045380(&hstringHeader);
    *(_BYTE *)(a2 + 40) = 0;
    v31 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    return a2;
  }
  string = 0;
  v8 = (const WCHAR *)(a1 + 88);
  if ( *(_QWORD *)(a1 + 112) > 7u )
    v8 = *(const WCHAR **)v8;
  if ( v8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    if ( v9 > 0xFFFFFFFF )
      goto LABEL_65;
  }
  else
  {
    v8 = &LocaleName;
    v9 = 0;
  }
  if ( (int)sub_1405D3298(&string, v8, v9) < 0 || !string )
  {
LABEL_65:
    sub_140021AB8((__int64)&hstringHeader, L"Failed to set package family name for search.");
    v47 = &C2R::ContextData::`vftable';
    v48 = 0;
    v49 = 0;
    v50 = 7;
    v51 = 0;
    v52 = 0;
    v53 = 7;
    LOWORD(v51) = 0;
    v34 = 0;
    sub_140328EF8(&v48, &v34);
    v50 = 7;
    sub_1400279B0((char *)&v51, (char *)&hstringHeader, v28);
    v47 = &C2R::ContextData::`vftable';
    v44 = &C2R::CommonTelemetry::`vftable';
    v45 = 0;
    si128 = _mm_load_si128((const __m128i *)&xmmword_14082E430);
    LOWORD(v45) = 0;
    if ( sub_140057BB0(504647828, 0x3B0u, 0xFu, 0) )
    {
      *(_QWORD *)&v34 = &v44;
      *((_QWORD *)&v34 + 1) = &v47;
      v39 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v40 = &v34;
      v41 = v35;
      sub_140141978(
        504647828,
        944,
        15,
        0,
        (__int64)L"C2R::DeploymentOnline::RichInteraction::VersionCheck::CurrentVersion",
        (__int64)&v39);
    }
    sub_140045380(&v45);
    sub_140193970(&v47);
    sub_140045380(&hstringHeader);
    *(_BYTE *)(a2 + 40) = 0;
    WindowsDeleteString(string);
    string = 0;
    v29 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    return a2;
  }
  v38 = 0;
  if ( (*(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v33 + 152LL))(v33, string, &v38) >= 0 )
  {
    v37 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v37) >= 0 && v37 )
    {
      v32[0] = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v37 + 56LL))(v37, v32);
      while ( v13 >= 0 && v32[0] )
      {
        v43[0] = 0;
        if ( (*(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v37 + 48LL))(v37, v43) >= 0 )
        {
          v42 = 0;
          if ( (*(int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v43[0] + 48LL))(v43[0], &v42) >= 0
            && (*(int (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v42 + 56LL))(v42, &v34) >= 0 )
          {
            LODWORD(v45) = 0;
            v44 = &OVersion::`vftable';
            DWORD2(v45) = (unsigned __int16)v34;
            HIDWORD(v45) = WORD1(v34);
            si128.m128i_i32[0] = WORD2(v34);
            *(__int64 *)((char *)si128.m128i_i64 + 4) = WORD3(v34) | 0xA000000000LL;
            sub_1402F35D4(a2, &v44);
            *(_BYTE *)(a2 + 40) = 1;
            v14 = v42;
            if ( v42 )
            {
              v42 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            }
            v15 = v43[0];
            if ( v43[0] )
            {
              v43[0] = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            }
            v16 = v37;
            if ( v37 )
            {
              v37 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            }
            v17 = v38;
            if ( v38 )
            {
              v38 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
            WindowsDeleteString(string);
            string = 0;
            v18 = v33;
            if ( v33 )
            {
              v33 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            }
            return a2;
          }
          v19 = v42;
          if ( v42 )
          {
            v42 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
        }
        v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v37 + 64LL))(v37, v32);
        v20 = v43[0];
        if ( v43[0] )
        {
          v43[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
      v21 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      WindowsDeleteString(string);
      string = 0;
      v23 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      }
      *(_BYTE *)(a2 + 40) = 0;
      return a2;
    }
    else
    {
      sub_140021AB8((__int64)&hstringHeader, L"Failed to get packages iterator.");
      v47 = &C2R::ContextData::`vftable';
      v48 = 0;
      v49 = 0;
      v50 = 7;
      v51 = 0;
      v52 = 0;
      v53 = 7;
      LOWORD(v51) = 0;
      v34 = 0;
      sub_140328EF8(&v48, &v34);
      v50 = 7;
      sub_1400279B0((char *)&v51, (char *)&hstringHeader, v24);
      v47 = &C2R::ContextData::`vftable';
      v44 = &C2R::CommonTelemetry::`vftable';
      v45 = 0;
      si128 = _mm_load_si128((const __m128i *)&xmmword_14082E430);
      LOWORD(v45) = 0;
      if ( sub_140057BB0(504647826, 0x3B0u, 0xFu, 0) )
      {
        *(_QWORD *)&v34 = &v44;
        *((_QWORD *)&v34 + 1) = &v47;
        v39 = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v40 = &v34;
        v41 = v35;
        sub_140141978(
          504647826,
          944,
          15,
          0,
          (__int64)L"C2R::DeploymentOnline::RichInteraction::VersionCheck::CurrentVersion",
          (__int64)&v39);
      }
      sub_140045380(&v45);
      sub_140193970(&v47);
      sub_140045380(&hstringHeader);
      *(_BYTE *)(a2 + 40) = 0;
      v25 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = v38;
      if ( v38 )
      {
        v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      WindowsDeleteString(string);
      string = 0;
      v27 = v33;
      if ( v33 )
      {
        v33 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      return a2;
    }
  }
  else
  {
    sub_140021AB8((__int64)&hstringHeader, L"Failed to find packages by package family name.");
    v47 = &C2R::ContextData::`vftable';
    v48 = 0;
    v49 = 0;
    v50 = 7;
    v51 = 0;
    v52 = 0;
    v53 = 7;
    LOWORD(v51) = 0;
    v34 = 0;
    sub_140328EF8(&v48, &v34);
    v50 = 7;
    sub_1400279B0((char *)&v51, (char *)&hstringHeader, v10);
    v47 = &C2R::ContextData::`vftable';
    v44 = &C2R::CommonTelemetry::`vftable';
    v45 = 0;
    si128 = _mm_load_si128((const __m128i *)&xmmword_14082E430);
    LOWORD(v45) = 0;
    if ( sub_140057BB0(504647827, 0x3B0u, 0xFu, 0) )
    {
      *(_QWORD *)&v34 = &v44;
      *((_QWORD *)&v34 + 1) = &v47;
      v39 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      v40 = &v34;
      v41 = v35;
      sub_140141978(
        504647827,
        944,
        15,
        0,
        (__int64)L"C2R::DeploymentOnline::RichInteraction::VersionCheck::CurrentVersion",
        (__int64)&v39);
    }
    sub_140045380(&v45);
    sub_140193970(&v47);
    sub_140045380(&hstringHeader);
    *(_BYTE *)(a2 + 40) = 0;
    v11 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    WindowsDeleteString(string);
    string = 0;
    v12 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return a2;
  }
}

```

## disassembly

```asm
0x14078bfcc  mov     [rsp+arg_10], rbx
0x14078bfd1  push    rsi
0x14078bfd2  push    rdi
0x14078bfd3  push    r14
0x14078bfd5  sub     rsp, 2A0h
0x14078bfdc  mov     rax, cs:__security_cookie
0x14078bfe3  xor     rax, rsp
0x14078bfe6  mov     [rsp+2B8h+var_28], rax
0x14078bfee  mov     rbx, rdx
0x14078bff1  mov     rdi, rcx
0x14078bff4  mov     [rsp+2B8h+var_218], rdx
0x14078bffc  xor     r14d, r14d
0x14078bfff  mov     [rsp+2B8h+var_280], r14
0x14078c004  mov     [rsp+2B8h+var_140], r14
0x14078c00c  lea     r9d, [r14+2Ch]
0x14078c010  lea     r8d, [r14+2Dh]
0x14078c014  lea     rdx, aWindowsManagem_3; "Windows.Management.Deployment.PackageMa"...
0x14078c01b  lea     rcx, [rsp+2B8h+hstringHeader]; hstringHeader
0x14078c023  call    sub_14006EE4C
0x14078c028  lea     rdx, [rsp+2B8h+var_280]
0x14078c02d  mov     rcx, [rsp+2B8h+var_140]
0x14078c035  call    cs:RoActivateInstance
0x14078c03b  mov     [rsp+2B8h+var_140], r14
0x14078c043  test    eax, eax
0x14078c045  jns     loc_14078C1F6
0x14078c04b  lea     rdx, aFailedToInitia_8; "Failed to initialize Windows Runtime (W"...
0x14078c052  lea     rcx, [rsp+2B8h+hstringHeader]
0x14078c05a  call    sub_140021AB8
0x14078c05f  lea     rsi, ??_7ContextData@C2R@@6B@; const C2R::ContextData::`vftable'
0x14078c066  mov     [rsp+2B8h+var_1A8], rsi
0x14078c06e  mov     [rsp+2B8h+var_1A0], r14
0x14078c076  xorps   xmm0, xmm0
0x14078c079  movdqa  [rsp+2B8h+var_198], xmm0
0x14078c082  lea     edi, [r14+7]
0x14078c086  mov     [rsp+2B8h+var_188], dil
0x14078c08e  movups  [rsp+2B8h+var_180], xmm0
0x14078c096  mov     [rsp+2B8h+var_170], r14
0x14078c09e  mov     [rsp+2B8h+var_168], rdi
0x14078c0a6  mov     word ptr [rsp+2B8h+var_180], r14w
0x14078c0af  movdqa  [rsp+2B8h+var_278], xmm0
0x14078c0b5  lea     rdx, [rsp+2B8h+var_278]
0x14078c0ba  lea     rcx, [rsp+2B8h+var_1A0]
0x14078c0c2  call    sub_140328EF8
0x14078c0c7  mov     [rsp+2B8h+var_188], dil
0x14078c0cf  lea     rdx, [rsp+2B8h+hstringHeader]
0x14078c0d7  lea     rcx, [rsp+2B8h+var_180]; void *
0x14078c0df  call    sub_1400279B0
0x14078c0e4  nop
0x14078c0e5  mov     [rsp+2B8h+var_1A8], rsi
0x14078c0ed  lea     rax, ??_7CommonTelemetry@C2R@@6B@; const C2R::CommonTelemetry::`vftable'
0x14078c0f4  mov     [rsp+2B8h+var_1D8], rax
0x14078c0fc  xorps   xmm0, xmm0
0x14078c0ff  movups  [rsp+2B8h+var_1D0], xmm0
0x14078c107  movdqa  xmm1, cs:xmmword_14082E430
0x14078c10f  movdqu  [rsp+2B8h+var_1C0], xmm1
0x14078c118  mov     word ptr [rsp+2B8h+var_1D0], r14w
0x14078c121  xor     r9d, r9d
0x14078c124  lea     esi, [rdi+3]
0x14078c127  mov     r8d, esi
0x14078c12a  mov     edi, 3B0h
0x14078c12f  mov     edx, edi
0x14078c131  mov     ecx, 1E145096h
0x14078c136  call    sub_140057BB0
0x14078c13b  test    al, al
0x14078c13d  jz      short loc_14078C1A7
0x14078c13f  lea     rax, [rsp+2B8h+var_1D8]
0x14078c147  mov     qword ptr [rsp+2B8h+var_278], rax
0x14078c14c  lea     rax, [rsp+2B8h+var_1A8]
0x14078c154  mov     qword ptr [rsp+2B8h+var_278+8], rax
0x14078c159  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x14078c160  mov     [rsp+2B8h+var_240], rax
0x14078c165  lea     rax, [rsp+2B8h+var_278]
0x14078c16a  mov     [rsp+2B8h+var_238], rax
0x14078c172  lea     rax, [rsp+2B8h+var_268]
0x14078c177  mov     [rsp+2B8h+var_230], rax
0x14078c17f  xor     r9d, r9d
0x14078c182  lea     rax, [rsp+2B8h+var_240]
0x14078c187  mov     [rsp+2B8h+var_290], rax
0x14078c18c  lea     rax, aC2rDeploymento_8; "C2R::DeploymentOnline::RichInteraction:"...
0x14078c193  mov     [rsp+2B8h+var_298], rax
0x14078c198  mov     r8d, esi
0x14078c19b  mov     edx, edi
0x14078c19d  mov     ecx, 1E145096h
0x14078c1a2  call    sub_140141978
0x14078c1a7  lea     rcx, [rsp+2B8h+var_1D0]; void *
0x14078c1af  call    sub_140045380
0x14078c1b4  lea     rcx, [rsp+2B8h+var_1A8]
0x14078c1bc  call    sub_140193970
0x14078c1c1  lea     rcx, [rsp+2B8h+hstringHeader]; void *
0x14078c1c9  call    sub_140045380
0x14078c1ce  mov     [rbx+28h], r14b
0x14078c1d2  mov     rcx, [rsp+2B8h+var_280]
0x14078c1d7  test    rcx, rcx
0x14078c1da  jz      short loc_14078C1EE
0x14078c1dc  mov     [rsp+2B8h+var_280], r14
0x14078c1e1  mov     rdx, [rcx]
0x14078c1e4  mov     rax, [rdx+10h]
0x14078c1e8  call    cs:__guard_dispatch_icall_fptr
0x14078c1ee  mov     rax, rbx
0x14078c1f1  jmp     loc_14078CC98
0x14078c1f6  cmp     [rsp+2B8h+var_280], r14
0x14078c1fb  jz      loc_14078CAE2
0x14078c201  mov     [rsp+2B8h+string], r14
0x14078c206  lea     rdx, [rdi+58h]
0x14078c20a  mov     edi, 7
0x14078c20f  cmp     [rdx+18h], rdi
0x14078c213  jbe     short loc_14078C218
0x14078c215  mov     rdx, [rdx]
0x14078c218  test    rdx, rdx
0x14078c21b  jz      short loc_14078C23B
0x14078c21d  or      r8, 0FFFFFFFFFFFFFFFFh
0x14078c221  inc     r8
0x14078c224  cmp     [rdx+r8*2], r14w
0x14078c229  jnz     short loc_14078C221
0x14078c22b  mov     eax, 0FFFFFFFFh
0x14078c230  cmp     r8, rax
0x14078c233  ja      loc_14078C927
0x14078c239  jmp     short loc_14078C245
0x14078c23b  lea     rdx, LocaleName
0x14078c242  mov     r8d, r14d
0x14078c245  lea     rcx, [rsp+2B8h+string]
0x14078c24a  call    sub_1405D3298
0x14078c24f  test    eax, eax
0x14078c251  js      loc_14078C927
0x14078c257  mov     rdx, [rsp+2B8h+string]
0x14078c25c  test    rdx, rdx
0x14078c25f  jz      loc_14078C927
0x14078c265  mov     [rsp+2B8h+var_248], r14
0x14078c26a  mov     rcx, [rsp+2B8h+var_280]
0x14078c26f  mov     rax, [rcx]
0x14078c272  lea     r8, [rsp+2B8h+var_248]
0x14078c277  mov     rax, [rax+98h]
0x14078c27e  call    cs:__guard_dispatch_icall_fptr
0x14078c284  test    eax, eax
0x14078c286  jns     loc_14078C465
0x14078c28c  lea     rdx, aFailedToFindPa; "Failed to find packages by package fami"...
0x14078c293  lea     rcx, [rsp+2B8h+hstringHeader]
0x14078c29b  call    sub_140021AB8
0x14078c2a0  nop
0x14078c2a1  lea     rsi, ??_7ContextData@C2R@@6B@; const C2R::ContextData::`vftable'
0x14078c2a8  mov     [rsp+2B8h+var_1A8], rsi
0x14078c2b0  mov     [rsp+2B8h+var_1A0], r14
0x14078c2b8  xorps   xmm0, xmm0
0x14078c2bb  movdqa  [rsp+2B8h+var_198], xmm0
0x14078c2c4  mov     [rsp+2B8h+var_188], dil
0x14078c2cc  xorps   xmm1, xmm1
0x14078c2cf  movups  [rsp+2B8h+var_180], xmm1
0x14078c2d7  mov     [rsp+2B8h+var_170], r14
0x14078c2df  mov     [rsp+2B8h+var_168], rdi
0x14078c2e7  mov     word ptr [rsp+2B8h+var_180], r14w
0x14078c2f0  movdqa  [rsp+2B8h+var_278], xmm0
0x14078c2f6  lea     rdx, [rsp+2B8h+var_278]
0x14078c2fb  lea     rcx, [rsp+2B8h+var_1A0]
0x14078c303  call    sub_140328EF8
0x14078c308  mov     [rsp+2B8h+var_188], dil
0x14078c310  lea     rdx, [rsp+2B8h+hstringHeader]
0x14078c318  lea     rcx, [rsp+2B8h+var_180]; void *
0x14078c320  call    sub_1400279B0
0x14078c325  nop
0x14078c326  mov     [rsp+2B8h+var_1A8], rsi
0x14078c32e  lea     rax, ??_7CommonTelemetry@C2R@@6B@; const C2R::CommonTelemetry::`vftable'
0x14078c335  mov     [rsp+2B8h+var_1D8], rax
0x14078c33d  xorps   xmm0, xmm0
0x14078c340  movups  [rsp+2B8h+var_1D0], xmm0
0x14078c348  movdqa  xmm1, cs:xmmword_14082E430
0x14078c350  movdqu  [rsp+2B8h+var_1C0], xmm1
0x14078c359  mov     word ptr [rsp+2B8h+var_1D0], r14w
0x14078c362  xor     r9d, r9d
0x14078c365  lea     esi, [r9+0Fh]
0x14078c369  mov     r8d, esi
0x14078c36c  mov     edi, 3B0h
0x14078c371  mov     edx, edi
0x14078c373  mov     ecx, 1E145093h
0x14078c378  call    sub_140057BB0
0x14078c37d  test    al, al
0x14078c37f  jz      short loc_14078C3E9
0x14078c381  lea     rax, [rsp+2B8h+var_1D8]
0x14078c389  mov     qword ptr [rsp+2B8h+var_278], rax
0x14078c38e  lea     rax, [rsp+2B8h+var_1A8]
0x14078c396  mov     qword ptr [rsp+2B8h+var_278+8], rax
0x14078c39b  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x14078c3a2  mov     [rsp+2B8h+var_240], rax
0x14078c3a7  lea     rax, [rsp+2B8h+var_278]
0x14078c3ac  mov     [rsp+2B8h+var_238], rax
0x14078c3b4  lea     rax, [rsp+2B8h+var_268]
0x14078c3b9  mov     [rsp+2B8h+var_230], rax
0x14078c3c1  xor     r9d, r9d
0x14078c3c4  lea     rax, [rsp+2B8h+var_240]
0x14078c3c9  mov     [rsp+2B8h+var_290], rax
0x14078c3ce  lea     rax, aC2rDeploymento_8; "C2R::DeploymentOnline::RichInteraction:"...
0x14078c3d5  mov     [rsp+2B8h+var_298], rax
0x14078c3da  mov     r8d, esi
0x14078c3dd  mov     edx, edi
0x14078c3df  mov     ecx, 1E145093h
0x14078c3e4  call    sub_140141978
0x14078c3e9  lea     rcx, [rsp+2B8h+var_1D0]; void *
0x14078c3f1  call    sub_140045380
0x14078c3f6  lea     rcx, [rsp+2B8h+var_1A8]
0x14078c3fe  call    sub_140193970
0x14078c403  lea     rcx, [rsp+2B8h+hstringHeader]; void *
0x14078c40b  call    sub_140045380
0x14078c410  mov     [rbx+28h], r14b
0x14078c414  mov     rcx, [rsp+2B8h+var_248]
0x14078c419  test    rcx, rcx
0x14078c41c  jz      short loc_14078C431
0x14078c41e  mov     [rsp+2B8h+var_248], r14
0x14078c423  mov     rax, [rcx]
0x14078c426  mov     rax, [rax+10h]
0x14078c42a  call    cs:__guard_dispatch_icall_fptr
0x14078c430  nop
0x14078c431  mov     rcx, [rsp+2B8h+string]; string
0x14078c436  call    cs:WindowsDeleteString
0x14078c43c  mov     [rsp+2B8h+string], r14
0x14078c441  mov     rcx, [rsp+2B8h+var_280]
0x14078c446  test    rcx, rcx
0x14078c449  jz      short loc_14078C45D
0x14078c44b  mov     [rsp+2B8h+var_280], r14
0x14078c450  mov     rax, [rcx]
0x14078c453  mov     rax, [rax+10h]
0x14078c457  call    cs:__guard_dispatch_icall_fptr
0x14078c45d  mov     rax, rbx
0x14078c460  jmp     loc_14078CC98
0x14078c465  mov     [rsp+2B8h+var_250], r14
0x14078c46a  mov     rcx, [rsp+2B8h+var_248]
0x14078c46f  mov     rax, [rcx]
0x14078c472  lea     rdx, [rsp+2B8h+var_250]
0x14078c477  mov     rax, [rax+30h]
0x14078c47b  call    cs:__guard_dispatch_icall_fptr
0x14078c481  test    eax, eax
0x14078c483  js      loc_14078C731
0x14078c489  mov     rcx, [rsp+2B8h+var_250]
0x14078c48e  test    rcx, rcx
0x14078c491  jz      loc_14078C731
0x14078c497  mov     [rsp+2B8h+var_288], r14b
0x14078c49c  mov     rax, [rcx]
0x14078c49f  lea     rdx, [rsp+2B8h+var_288]
0x14078c4a4  mov     rax, [rax+38h]
0x14078c4a8  call    cs:__guard_dispatch_icall_fptr
0x14078c4ae  mov     edi, eax
0x14078c4b0  test    edi, edi
0x14078c4b2  js      loc_14078C6BE
0x14078c4b8  cmp     [rsp+2B8h+var_288], r14b
0x14078c4bd  jz      loc_14078C6BE
0x14078c4c3  mov     [rsp+2B8h+var_220], r14
0x14078c4cb  mov     rcx, [rsp+2B8h+var_250]
0x14078c4d0  mov     rax, [rcx]
0x14078c4d3  lea     rdx, [rsp+2B8h+var_220]
0x14078c4db  mov     rax, [rax+30h]
0x14078c4df  call    cs:__guard_dispatch_icall_fptr
0x14078c4e5  test    eax, eax
0x14078c4e7  js      loc_14078C67A
0x14078c4ed  mov     [rsp+2B8h+var_228], r14
0x14078c4f5  mov     rcx, [rsp+2B8h+var_220]
0x14078c4fd  mov     rax, [rcx]
0x14078c500  lea     rdx, [rsp+2B8h+var_228]
0x14078c508  mov     rax, [rax+30h]
0x14078c50c  call    cs:__guard_dispatch_icall_fptr
0x14078c512  test    eax, eax
0x14078c514  js      loc_14078C658
0x14078c51a  mov     rcx, [rsp+2B8h+var_228]
0x14078c522  mov     rax, [rcx]
0x14078c525  lea     rdx, [rsp+2B8h+var_278]
0x14078c52a  mov     rax, [rax+38h]
0x14078c52e  call    cs:__guard_dispatch_icall_fptr
0x14078c534  test    eax, eax
0x14078c536  js      loc_14078C658
0x14078c53c  movzx   r8d, word ptr [rsp+2B8h+var_278+6]
0x14078c542  movzx   edx, word ptr [rsp+2B8h+var_278+4]
0x14078c547  movzx   ecx, word ptr [rsp+2B8h+var_278+2]
0x14078c54c  movzx   eax, word ptr [rsp+2B8h+var_278]
0x14078c551  mov     dword ptr [rsp+2B8h+var_1D0], r14d
0x14078c559  lea     r9, ??_7OVersion@@6B@; const OVersion::`vftable'
0x14078c560  mov     [rsp+2B8h+var_1D8], r9
0x14078c568  mov     dword ptr [rsp+2B8h+var_1C0+8], 0A0h
0x14078c573  mov     dword ptr [rsp+2B8h+var_1D0+8], eax
0x14078c57a  mov     dword ptr [rsp+2B8h+var_1D0+0Ch], ecx
0x14078c581  mov     dword ptr [rsp+2B8h+var_1C0], edx
0x14078c588  mov     dword ptr [rsp+2B8h+var_1C0+4], r8d
0x14078c590  lea     rdx, [rsp+2B8h+var_1D8]
0x14078c598  mov     rcx, rbx
0x14078c59b  call    sub_1402F35D4
0x14078c5a0  mov     byte ptr [rbx+28h], 1
0x14078c5a4  mov     rcx, [rsp+2B8h+var_228]
0x14078c5ac  test    rcx, rcx
0x14078c5af  jz      short loc_14078C5C7
0x14078c5b1  mov     [rsp+2B8h+var_228], r14
0x14078c5b9  mov     rax, [rcx]
0x14078c5bc  mov     rax, [rax+10h]
0x14078c5c0  call    cs:__guard_dispatch_icall_fptr
0x14078c5c6  nop
0x14078c5c7  mov     rcx, [rsp+2B8h+var_220]
0x14078c5cf  test    rcx, rcx
0x14078c5d2  jz      short loc_14078C5EA
0x14078c5d4  mov     [rsp+2B8h+var_220], r14
0x14078c5dc  mov     rax, [rcx]
0x14078c5df  mov     rax, [rax+10h]
0x14078c5e3  call    cs:__guard_dispatch_icall_fptr
0x14078c5e9  nop
0x14078c5ea  mov     rcx, [rsp+2B8h+var_250]
0x14078c5ef  test    rcx, rcx
  ... truncated ...
```
