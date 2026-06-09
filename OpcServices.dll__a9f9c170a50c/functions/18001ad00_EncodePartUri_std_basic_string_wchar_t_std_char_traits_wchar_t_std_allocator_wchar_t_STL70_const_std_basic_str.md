# EncodePartUri(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &)

- ea: `0x18001ad00`
- end: `0x18001b684`
- name: `?EncodePartUri@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBV12@0@Z`
- size: `2436`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180019664`

## callees

- `0x180015a68`
- `0x180018c2c`
- `0x18001aaa0`
- `0x18001ad00`
- `0x18001b690`
- `0x18001b940`
- `0x18001c5d0`
- `0x18001ca9c`
- `0x18001cb40`
- `0x18001cbb0`
- `0x18001d200`
- `0x1800517a0`
- `0x18005c760`
- `0x180067a04`
- `0x18009c21c`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800cdb60`
- `0x1800cdbbc`
- `0x1800d04d8`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001af99`
- `msvcrt!memcpy_s` at `0x18001b067`
- `msvcrt!memcpy_s` at `0x18001b2db`
- `msvcrt!memcpy_s` at `0x18001af99`
- `msvcrt!memcpy_s` at `0x18001b067`
- `msvcrt!memcpy_s` at `0x18001b2db`

## string_xrefs

- `0x18001af4c`: `http://www.example.com`
- `0x18001b465`: `Call to CPercentDecodePartUri::GetEncodedLength failed with HResult 0x%X.`
- `0x18001b531`: `Call to CPercentDecodePartUri::Decode failed with HResult 0x%X.`
- `0x18001b4cb`: `Call to PercentEncodePartUri::Encode failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EncodePartUri(__int64 a1, _QWORD *a2, __int64 a3, unsigned __int16 **a4)
{
  __int64 v6; // rcx
  _QWORD *v7; // rax
  signed int v8; // ebx
  unsigned __int64 v9; // rax
  int v10; // edx
  void **v11; // rbx
  const char *v12; // r8
  unsigned int v13; // r9d
  volatile signed __int32 *v14; // rax
  unsigned __int16 **v15; // r9
  win_scope::counted_strong_weak_base *v16; // r14
  signed int v17; // edi
  unsigned __int16 **v18; // r9
  signed int v19; // edi
  unsigned __int64 v20; // r8
  unsigned int v21; // eax
  _WORD *v22; // rdx
  unsigned __int64 v23; // r11
  unsigned __int64 v24; // r10
  unsigned __int64 v25; // rdi
  char v26; // dl
  char v27; // r9
  unsigned __int64 i; // rcx
  __int16 v29; // ax
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // r10
  unsigned __int64 v32; // r11
  char v33; // dl
  unsigned __int64 j; // rcx
  __int16 v35; // ax
  void **v36; // rcx
  void **v37; // rcx
  unsigned __int64 v38; // r10
  unsigned __int64 v39; // rdi
  void **v40; // rax
  void **v41; // rcx
  unsigned __int64 v42; // rsi
  void **v43; // rax
  void **v44; // rcx
  __int16 v46; // r9
  void **v47; // rax
  void **v48; // rcx
  unsigned __int64 v49; // rdi
  void **v50; // rax
  void **v51; // rcx
  void **v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rdx
  void **v55; // rcx
  void **v56; // rax
  void **v57; // rax
  unsigned __int64 *v58; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v59; // [rsp+20h] [rbp-E0h]
  unsigned __int64 *v60; // [rsp+20h] [rbp-E0h]
  char v61; // [rsp+28h] [rbp-D8h]
  char v62; // [rsp+28h] [rbp-D8h]
  char v63; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v64; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v65[8]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v66[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v67[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v68; // [rsp+88h] [rbp-78h]
  __int64 v69; // [rsp+98h] [rbp-68h]
  char v70[8]; // [rsp+A0h] [rbp-60h] BYREF
  void *Destination[2]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v72; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v73; // [rsp+C0h] [rbp-40h]
  _BYTE pExceptionObject[160]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v75[512]; // [rsp+170h] [rbp+70h] BYREF

  v69 = -2;
  v68 = 0;
  v64 = 0;
  v6 = a2[3];
  v7 = a2 + 1;
  if ( a2[4] >= 8u )
    v7 = (_QWORD *)*v7;
  v67[1] = v7;
  v67[2] = v6;
  v67[0] = &win_dox::PercentEncodePartUri::`vftable';
  v8 = CPercentEncodeString::Encode((CPercentEncodeString *)v67, 0, &v64, a4, v58, v61);
  if ( v8 < 0 )
  {
    memset_0(v75, 0, sizeof(v75));
    StringCchPrintfW(
      v75,
      0x200u,
      L"Call to CPercentDecodePartUri::GetEncodedLength failed with HResult 0x%X.",
      (unsigned int)v8);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x485u,
      v8,
      (struct win_musl::TStringEllipseBase *)v75);
    throw (SplException::THResultException *)pExceptionObject;
  }
  ++v64;
  v9 = 2 * v64;
  if ( !is_mul_ok(v64, 2u) )
    v9 = -1;
  v11 = (void **)operator new(v9, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v10, v12, v13);
  v14 = (volatile signed __int32 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = (win_scope::counted_strong_weak_base *)v14;
  if ( !v14 )
  {
    operator delete(v11);
    win_scope::report_policy_throw::report_init_failure();
  }
  *((_QWORD *)v14 + 1) = 0;
  *(_QWORD *)v14 = &win_scope::counted_strong_weak<bool volatile *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
  *((_QWORD *)v14 + 2) = v11;
  if ( _InterlockedIncrement(v14 + 2) == 1 )
    _InterlockedIncrement(v14 + 3);
  *(_QWORD *)&v68 = v14;
  *((_QWORD *)&v68 + 1) = v11;
  v17 = CPercentEncodeString::Encode((CPercentEncodeString *)v67, (unsigned __int16 *)v11, &v64, v15, v59, v62);
  if ( v17 < 0 )
  {
    memset_0(v75, 0, sizeof(v75));
    StringCchPrintfW(v75, 0x200u, L"Call to PercentEncodePartUri::Encode failed with HResult 0x%X.", (unsigned int)v17);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x492u,
      v17,
      (struct win_musl::TStringEllipseBase *)v75);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v66[1] = v11;
  v66[2] = v64;
  v66[0] = &win_dox::PercentDecodePartUri::`vftable';
  ++v64;
  v19 = CPercentDecodeString::Decode((CPercentDecodeString *)v66, (unsigned __int16 *)v11, &v64, v18, v60, v63);
  if ( v19 < 0 )
  {
    memset_0(v75, 0, sizeof(v75));
    StringCchPrintfW(v75, 0x200u, L"Call to CPercentDecodePartUri::Decode failed with HResult 0x%X.", (unsigned int)v19);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x4A9u,
      v19,
      (struct win_musl::TStringEllipseBase *)v75);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v20 = v64 + 1;
  v21 = 0;
  if ( (_DWORD)v64 != -1 )
  {
    do
    {
      v22 = (_WORD *)v11 + v21;
      if ( !*v22 )
        break;
      if ( *v22 == 92 )
        *v22 = 47;
      ++v21;
    }
    while ( v21 < (unsigned int)v20 );
  }
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 1;
  for ( i = 0; i < v20; ++i )
  {
    v29 = *((_WORD *)v11 + i);
    if ( v29 == 47 || !v29 )
    {
      if ( v23 != i )
      {
        if ( !v26 || v27 )
        {
          if ( v24 == v23 )
          {
            v24 = i;
          }
          else
          {
            for ( ; v23 < i; ++v24 )
              *((_WORD *)v11 + v24) = *((_WORD *)v11 + v23++);
          }
        }
        else if ( v24 == v23 )
        {
          v24 = v25;
        }
        else
        {
          for ( ; v23 < v25; ++v24 )
            *((_WORD *)v11 + v24) = *((_WORD *)v11 + v23++);
        }
      }
      if ( !*((_WORD *)v11 + i) )
        *((_WORD *)v11 + v24) = 0;
      v23 = i;
      v27 = 1;
    }
    else
    {
      if ( v29 == 46 )
      {
        if ( !v26 )
        {
          v26 = 1;
          v25 = i;
        }
        continue;
      }
      v27 = 0;
    }
    v26 = 0;
  }
  v30 = v24 + 1;
  v31 = 0;
  v32 = 0;
  v33 = 1;
  for ( j = 0; j < v30; ++j )
  {
    v35 = *((_WORD *)v11 + j);
    if ( v35 == 47 || !v35 )
    {
      v46 = *((_WORD *)v11 + j);
      if ( v31 != j && (!v33 || j - v31 - 2 <= 1 || j - v31 == 1 && *((_WORD *)v11 + v31) == 46) )
      {
        if ( v32 == v31 )
        {
          v32 = j;
        }
        else if ( v31 < j )
        {
          do
            *((_WORD *)v11 + v32++) = *((_WORD *)v11 + v31++);
          while ( v31 < j );
          v46 = *((_WORD *)v11 + j);
        }
      }
      if ( !v46 )
        *((_WORD *)v11 + v32) = 0;
      v31 = j;
      v33 = 1;
    }
    else if ( v35 != 46 )
    {
      v33 = 0;
    }
  }
  v73 = 7;
  v72 = 0;
  LOWORD(Destination[0]) = 0;
  std::wstring::_Copy(v70, 22, 0);
  v36 = Destination;
  if ( v73 >= 8 )
    v36 = (void **)Destination[0];
  memcpy_s(v36, 2 * v73, L"http://www.example.com", 0x2Cu);
  v37 = Destination;
  if ( v73 >= 8 )
    v37 = (void **)Destination[0];
  v72 = 22;
  *((_WORD *)v37 + 22) = 0;
  if ( *(_WORD *)v11 == 47 )
    goto LABEL_35;
  if ( *(_QWORD *)(a3 + 24) )
  {
    std::wstring::append(v70, a3, 0, -1);
    if ( *(_WORD *)v11 != 63 && *(_WORD *)v11 != 35 )
    {
      v65[0] = 47;
      v53 = std::wstring::rfind(v70, v65, -1, 1);
      if ( v53 != -1 )
      {
        v54 = v53 + 1;
        if ( v53 + 1 > v72 )
          std::wstring::append(v70, v54 - v72, 0);
        else
          std::wstring::erase(v70, v54, -1);
      }
    }
    goto LABEL_35;
  }
  v47 = Destination;
  v38 = v73;
  if ( v73 >= 8 )
    v47 = (void **)Destination[0];
  if ( L"/" >= (const OLECHAR *)v47 )
  {
    v48 = Destination;
    if ( v73 >= 8 )
      v48 = (void **)Destination[0];
    if ( (char *)v48 + 2 * v72 > (char *)L"/" )
    {
      v56 = Destination;
      if ( v73 >= 8 )
        v56 = (void **)Destination[0];
      std::wstring::append(v70, v70, ((char *)L"/" - (char *)v56) >> 1, 1);
      goto LABEL_35;
    }
  }
  if ( -1LL - v72 <= 1 )
    std::_String_base::_Xlen();
  v49 = v72 + 1;
  if ( v72 + 1 > 0x7FFFFFFFFFFFFFFELL )
    std::_String_base::_Xlen();
  if ( v73 < v49 )
  {
    std::wstring::_Copy(v70, v72 + 1, v72);
    v38 = v73;
    if ( !v49 )
      goto LABEL_36;
  }
  else if ( v72 == -1 )
  {
    v55 = Destination;
    if ( v73 >= 8 )
      v55 = (void **)Destination[0];
    v72 = 0;
    *(_WORD *)v55 = 0;
    goto LABEL_35;
  }
  v50 = Destination;
  if ( v38 >= 8 )
    v50 = (void **)Destination[0];
  memcpy_s((char *)v50 + 2 * v72, 2 * (v38 - v72), L"/", 2u);
  v51 = Destination;
  if ( v73 >= 8 )
    v51 = (void **)Destination[0];
  v72 = v49;
  *((_WORD *)v51 + v49) = 0;
LABEL_35:
  v38 = v73;
LABEL_36:
  v39 = -1;
  do
    ++v39;
  while ( *((_WORD *)v11 + v39) );
  v40 = Destination;
  if ( v38 >= 8 )
    v40 = (void **)Destination[0];
  if ( v11 < v40 )
    goto LABEL_44;
  v41 = Destination;
  if ( v38 >= 8 )
    v41 = (void **)Destination[0];
  if ( (void **)((char *)v41 + 2 * v72) > v11 )
  {
    v57 = Destination;
    if ( v38 >= 8 )
      v57 = (void **)Destination[0];
    std::wstring::append(v70, v70, ((char *)v11 - (char *)v57) >> 1, v39);
  }
  else
  {
LABEL_44:
    if ( -1LL - v72 <= v39 )
      std::_String_base::_Xlen();
    if ( v39 )
    {
      v42 = v39 + v72;
      if ( v39 + v72 > 0x7FFFFFFFFFFFFFFELL )
        std::_String_base::_Xlen();
      if ( v38 < v42 )
      {
        std::wstring::_Copy(v70, v39 + v72, v72);
        v38 = v73;
        if ( !v42 )
          goto LABEL_54;
        goto LABEL_49;
      }
      if ( v42 )
      {
LABEL_49:
        v43 = Destination;
        if ( v38 >= 8 )
          v43 = (void **)Destination[0];
        memcpy_s((char *)v43 + 2 * v72, 2 * (v38 - v72), v11, 2 * v39);
        v44 = Destination;
        if ( v73 >= 8 )
          v44 = (void **)Destination[0];
        v72 = v42;
        *((_WORD *)v44 + v42) = 0;
        goto LABEL_54;
      }
      v52 = Destination;
      if ( v38 >= 8 )
        v52 = (void **)Destination[0];
      v72 = 0;
      *(_WORD *)v52 = 0;
    }
  }
LABEL_54:
  win_dox::Uri::CreateUri((__int64)&v64, (__int64)v70, 0x1100u);
  win_dox::Uri::GetPath(&v64, a1);
  if ( v64 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v73 >= 8 )
    operator delete(Destination[0]);
  v73 = 7;
  v72 = 0;
  LOWORD(Destination[0]) = 0;
  v66[0] = &CPercentDecodeString::`vftable';
  v67[0] = &CPercentEncodeString::`vftable';
  if ( v16 )
    win_scope::counted_strong_weak_base::Release(v16);
  return a1;
}

```

## disassembly

```asm
0x18001ad00  push    rbp
0x18001ad02  push    rsi
0x18001ad03  push    rdi
0x18001ad04  push    r12
0x18001ad06  push    r13
0x18001ad08  push    r14
0x18001ad0a  push    r15
0x18001ad0c  lea     rbp, [rsp-480h]
0x18001ad14  sub     rsp, 580h
0x18001ad1b  mov     [rbp+4B0h+var_518], 0FFFFFFFFFFFFFFFEh
0x18001ad23  mov     [rsp+5B0h+arg_8], rbx
0x18001ad2b  mov     rax, cs:__security_cookie
0x18001ad32  xor     rax, rsp
0x18001ad35  mov     [rbp+4B0h+var_40], rax
0x18001ad3c  mov     r13, r8
0x18001ad3f  mov     r12, rcx
0x18001ad42  mov     [rsp+5B0h+var_570], rcx
0x18001ad47  xor     esi, esi
0x18001ad49  xorps   xmm0, xmm0
0x18001ad4c  movdqu  [rbp+4B0h+var_528], xmm0
0x18001ad51  mov     [rsp+5B0h+var_570], rsi
0x18001ad56  mov     rcx, [rdx+18h]
0x18001ad5a  lea     rax, [rdx+8]
0x18001ad5e  cmp     qword ptr [rdx+20h], 8
0x18001ad63  jb      short loc_18001AD68
0x18001ad65  mov     rax, [rax]
0x18001ad68  mov     [rsp+5B0h+var_538], rax
0x18001ad6d  mov     [rbp+4B0h+var_530], rcx
0x18001ad71  lea     rax, ??_7PercentEncodePartUri@win_dox@@6B@; const win_dox::PercentEncodePartUri::`vftable'
0x18001ad78  mov     [rsp+5B0h+var_540], rax
0x18001ad7d  lea     r8, [rsp+5B0h+var_570]; unsigned __int64 *
0x18001ad82  xor     edx, edx; unsigned __int16 *
0x18001ad84  lea     rcx, [rsp+5B0h+var_540]; this
0x18001ad89  call    ?Encode@CPercentEncodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentEncodeString::Encode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x18001ad8e  mov     ebx, eax
0x18001ad90  test    eax, eax
0x18001ad92  js      loc_18001B451
0x18001ad98  mov     rcx, [rsp+5B0h+var_570]
0x18001ad9d  inc     rcx
0x18001ada0  mov     [rsp+5B0h+var_570], rcx
0x18001ada5  mov     eax, 2
0x18001adaa  mul     rcx
0x18001adad  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18001adb4  cmovb   rax, r15
0x18001adb8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001adbf  mov     rcx, rax; unsigned __int64
0x18001adc2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001adc7  mov     rbx, rax
0x18001adca  test    rax, rax
0x18001adcd  jz      loc_18001B2FE
0x18001add3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001adda  mov     ecx, 18h; unsigned __int64
0x18001addf  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ade4  mov     r14, rax
0x18001ade7  test    rax, rax
0x18001adea  jz      loc_18001B39E
0x18001adf0  mov     [rax+8], rsi
0x18001adf4  lea     rax, ??_7?$counted_strong_weak@PEC_NU?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<bool volatile *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x18001adfb  mov     [r14], rax
0x18001adfe  mov     [r14+10h], rbx
0x18001ae02  mov     eax, 1
0x18001ae07  lock xadd [r14+8], eax
0x18001ae0d  inc     eax
0x18001ae0f  cmp     eax, 1
0x18001ae12  jz      loc_18001B1B3
0x18001ae18  mov     qword ptr [rbp+4B0h+var_528], r14
0x18001ae1c  mov     qword ptr [rbp+4B0h+var_528+8], rbx
0x18001ae20  lea     r8, [rsp+5B0h+var_570]; unsigned __int64 *
0x18001ae25  mov     rdx, rbx; unsigned __int16 *
0x18001ae28  lea     rcx, [rsp+5B0h+var_540]; this
0x18001ae2d  call    ?Encode@CPercentEncodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentEncodeString::Encode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x18001ae32  mov     edi, eax
0x18001ae34  test    eax, eax
0x18001ae36  js      loc_18001B4B7
0x18001ae3c  mov     [rsp+5B0h+var_550], rbx
0x18001ae41  mov     rcx, [rsp+5B0h+var_570]
0x18001ae46  mov     dword ptr [rsp+5B0h+var_548], ecx
0x18001ae4a  mov     eax, dword ptr [rsp+5B0h+var_570+4]
0x18001ae4e  mov     dword ptr [rsp+5B0h+var_548+4], eax
0x18001ae52  lea     rax, ??_7PercentDecodePartUri@win_dox@@6B@; const win_dox::PercentDecodePartUri::`vftable'
0x18001ae59  mov     [rsp+5B0h+var_558], rax
0x18001ae5e  inc     rcx
0x18001ae61  mov     [rsp+5B0h+var_570], rcx
0x18001ae66  lea     r8, [rsp+5B0h+var_570]; unsigned __int64 *
0x18001ae6b  mov     rdx, rbx; unsigned __int16 *
0x18001ae6e  lea     rcx, [rsp+5B0h+var_558]; this
0x18001ae73  call    ?Decode@CPercentDecodeString@@QEAAJPEAGPEA_KPEAPEAG1K@Z; CPercentDecodeString::Decode(ushort *,unsigned __int64 *,ushort * *,unsigned __int64 *,ulong)
0x18001ae78  mov     edi, eax
0x18001ae7a  test    eax, eax
0x18001ae7c  js      loc_18001B51D
0x18001ae82  mov     r8, [rsp+5B0h+var_570]
0x18001ae87  inc     r8
0x18001ae8a  mov     eax, esi
0x18001ae8c  test    r8d, r8d
0x18001ae8f  jz      short loc_18001AEB0
0x18001ae91  mov     ecx, eax
0x18001ae93  lea     rdx, [rbx+rcx*2]
0x18001ae97  movzx   ecx, word ptr [rdx]
0x18001ae9a  test    cx, cx
0x18001ae9d  jz      short loc_18001AEB0
0x18001ae9f  cmp     cx, 5Ch ; '\'
0x18001aea3  jz      loc_18001B133
0x18001aea9  inc     eax
0x18001aeab  cmp     eax, r8d
0x18001aeae  jb      short loc_18001AE91
0x18001aeb0  mov     r11, rsi
0x18001aeb3  mov     r10, rsi
0x18001aeb6  mov     rdi, rsi
0x18001aeb9  xor     dl, dl
0x18001aebb  mov     r9b, 1
0x18001aebe  mov     rcx, rsi
0x18001aec1  test    r8, r8
0x18001aec4  jz      short loc_18001AEFE
0x18001aec6  nop     word ptr [rax+rax+00000000h]
0x18001aed0  movzx   eax, word ptr [rbx+rcx*2]
0x18001aed4  cmp     ax, 2Fh ; '/'
0x18001aed8  jz      loc_18001B13D
0x18001aede  test    ax, ax
0x18001aee1  jz      loc_18001B13D
0x18001aee7  cmp     ax, 2Eh ; '.'
0x18001aeeb  jz      loc_18001B16D
0x18001aef1  xor     r9b, r9b
0x18001aef4  xor     dl, dl
0x18001aef6  inc     rcx
0x18001aef9  cmp     rcx, r8
0x18001aefc  jb      short loc_18001AED0
0x18001aefe  lea     r8, [r10+1]
0x18001af02  mov     r10, rsi
0x18001af05  mov     r11, rsi
0x18001af08  mov     dl, 1
0x18001af0a  mov     rcx, rsi
0x18001af0d  test    r8, r8
0x18001af10  jz      short loc_18001AF39
0x18001af12  movzx   eax, word ptr [rbx+rcx*2]
0x18001af16  cmp     ax, 2Fh ; '/'
0x18001af1a  jz      loc_18001B17F
0x18001af20  test    ax, ax
0x18001af23  jz      loc_18001B17F
0x18001af29  cmp     ax, 2Eh ; '.'
0x18001af2d  jz      short loc_18001AF31
0x18001af2f  xor     dl, dl
0x18001af31  inc     rcx
0x18001af34  cmp     rcx, r8
0x18001af37  jb      short loc_18001AF12
0x18001af39  mov     [rbp+4B0h+var_4F0], 7
0x18001af41  mov     rcx, rsi
0x18001af44  mov     [rbp+4B0h+var_4F8], rcx
0x18001af48  mov     word ptr [rbp+4B0h+Destination], si
0x18001af4c  lea     rdi, ?g_sampleBaseUri@win_musl@@3QB_WB; "http://www.example.com"
0x18001af53  lea     rax, [rbp+4B0h+Destination]
0x18001af57  cmp     rdi, rax
0x18001af5a  jb      short loc_18001AF69
0x18001af5c  lea     rax, [rbp+4B0h+Destination]
0x18001af60  cmp     rax, rdi
0x18001af63  ja      loc_18001B1ED
0x18001af69  xor     r8d, r8d
0x18001af6c  mov     esi, 16h
0x18001af71  mov     edx, esi
0x18001af73  lea     rcx, [rbp+4B0h+var_510]
0x18001af77  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001af7c  mov     rdx, [rbp+4B0h+var_4F0]
0x18001af80  lea     rcx, [rbp+4B0h+Destination]
0x18001af84  cmp     rdx, 8
0x18001af88  cmovnb  rcx, [rbp+4B0h+Destination]; Destination
0x18001af8d  add     rdx, rdx; DestinationSize
0x18001af90  mov     r9d, 2Ch ; ','; SourceSize
0x18001af96  mov     r8, rdi; Source
0x18001af99  call    cs:__imp_memcpy_s
0x18001af9f  lea     rcx, [rbp+4B0h+Destination]
0x18001afa3  cmp     [rbp+4B0h+var_4F0], 8
0x18001afa8  cmovnb  rcx, [rbp+4B0h+Destination]
0x18001afad  mov     [rbp+4B0h+var_4F8], rsi
0x18001afb1  xor     eax, eax
0x18001afb3  mov     [rcx+2Ch], ax
0x18001afb7  cmp     word ptr [rbx], 2Fh ; '/'
0x18001afbb  jnz     loc_18001B22F
0x18001afc1  mov     r13, 7FFFFFFFFFFFFFFEh
0x18001afcb  mov     r10, [rbp+4B0h+var_4F0]
0x18001afcf  mov     rdi, r15
0x18001afd2  inc     rdi
0x18001afd5  cmp     word ptr [rbx+rdi*2], 0
0x18001afda  jnz     short loc_18001AFD2
0x18001afdc  lea     rax, [rbp+4B0h+Destination]
0x18001afe0  mov     rdx, [rbp+4B0h+Destination]
0x18001afe4  cmp     r10, 8
0x18001afe8  cmovnb  rax, rdx
0x18001afec  cmp     rbx, rax
0x18001afef  jb      short loc_18001B00E
0x18001aff1  lea     rcx, [rbp+4B0h+Destination]
0x18001aff5  cmp     r10, 8
0x18001aff9  cmovnb  rcx, rdx
0x18001affd  mov     rax, [rbp+4B0h+var_4F8]
0x18001b001  lea     rcx, [rcx+rax*2]
0x18001b005  cmp     rcx, rbx
0x18001b008  ja      loc_18001B63D
0x18001b00e  sub     r15, [rbp+4B0h+var_4F8]
0x18001b012  cmp     r15, rdi
0x18001b015  jbe     loc_18001B667
0x18001b01b  test    rdi, rdi
0x18001b01e  jz      short loc_18001B085
0x18001b020  mov     rsi, [rbp+4B0h+var_4F8]
0x18001b024  add     rsi, rdi
0x18001b027  cmp     rsi, r13
0x18001b02a  ja      loc_18001B675
0x18001b030  cmp     r10, rsi
0x18001b033  jb      loc_18001B1CB
0x18001b039  test    rsi, rsi
0x18001b03c  jz      loc_18001B309
0x18001b042  mov     rdx, r10
0x18001b045  mov     rcx, [rbp+4B0h+var_4F8]
0x18001b049  sub     rdx, rcx
0x18001b04c  lea     rax, [rbp+4B0h+Destination]
0x18001b050  cmp     r10, 8
0x18001b054  cmovnb  rax, [rbp+4B0h+Destination]
0x18001b059  lea     r9, [rdi+rdi]; SourceSize
0x18001b05d  add     rdx, rdx; DestinationSize
0x18001b060  lea     rcx, [rax+rcx*2]; Destination
0x18001b064  mov     r8, rbx; Source
0x18001b067  call    cs:__imp_memcpy_s
0x18001b06d  lea     rcx, [rbp+4B0h+Destination]
0x18001b071  cmp     [rbp+4B0h+var_4F0], 8
0x18001b076  cmovnb  rcx, [rbp+4B0h+Destination]
0x18001b07b  mov     [rbp+4B0h+var_4F8], rsi
0x18001b07f  xor     eax, eax
0x18001b081  mov     [rcx+rsi*2], ax
0x18001b085  mov     r8d, 1100h
0x18001b08b  lea     rdx, [rbp+4B0h+var_510]
0x18001b08f  lea     rcx, [rsp+5B0h+var_570]
0x18001b094  call    ?CreateUri@Uri@win_dox@@SA?AV12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@K@Z; win_dox::Uri::CreateUri(std::wstring const &,ulong)
0x18001b099  nop
0x18001b09a  mov     rdx, r12
0x18001b09d  lea     rcx, [rsp+5B0h+var_570]
0x18001b0a2  call    ?GetPath@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetPath(void)
0x18001b0a7  nop
0x18001b0a8  mov     rcx, [rsp+5B0h+var_570]
0x18001b0ad  test    rcx, rcx
0x18001b0b0  jz      short loc_18001B0BF
0x18001b0b2  mov     rax, [rcx]
0x18001b0b5  mov     rax, [rax+10h]
0x18001b0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0be  nop
0x18001b0bf  cmp     [rbp+4B0h+var_4F0], 8
0x18001b0c4  jnb     loc_18001B1BD
0x18001b0ca  mov     [rbp+4B0h+var_4F0], 7
0x18001b0d2  mov     [rbp+4B0h+var_4F8], 0
0x18001b0da  xor     eax, eax
0x18001b0dc  mov     word ptr [rbp+4B0h+Destination], ax
0x18001b0e0  lea     rax, ??_7CPercentDecodeString@@6B@; const CPercentDecodeString::`vftable'
0x18001b0e7  mov     [rsp+5B0h+var_558], rax
0x18001b0ec  lea     rax, ??_7CPercentEncodeString@@6B@; const CPercentEncodeString::`vftable'
0x18001b0f3  mov     [rsp+5B0h+var_540], rax
0x18001b0f8  test    r14, r14
0x18001b0fb  jz      short loc_18001B106
0x18001b0fd  mov     rcx, r14; this
0x18001b100  call    ?Release@counted_strong_weak_base@win_scope@@QEAAKXZ; win_scope::counted_strong_weak_base::Release(void)
0x18001b105  nop
0x18001b106  mov     rax, r12
0x18001b109  mov     rcx, [rbp+4B0h+var_40]
0x18001b110  xor     rcx, rsp; StackCookie
0x18001b113  call    __security_check_cookie
0x18001b118  mov     rbx, [rsp+5B0h+arg_8]
0x18001b120  add     rsp, 580h
0x18001b127  pop     r15
0x18001b129  pop     r14
0x18001b12b  pop     r13
0x18001b12d  pop     r12
0x18001b12f  pop     rdi
0x18001b130  pop     rsi
0x18001b131  pop     rbp
0x18001b132  retn
0x18001b133  mov     word ptr [rdx], 2Fh ; '/'
0x18001b138  jmp     loc_18001AEA9
0x18001b13d  cmp     r11, rcx
0x18001b140  jz      short loc_18001B156
0x18001b142  test    dl, dl
0x18001b144  jnz     loc_18001B3FD
0x18001b14a  cmp     r10, r11
0x18001b14d  jnz     loc_18001B58B
0x18001b153  mov     r10, rcx
0x18001b156  cmp     word ptr [rbx+rcx*2], 0
0x18001b15b  jnz     short loc_18001B162
0x18001b15d  mov     [rbx+r10*2], si
0x18001b162  mov     r11, rcx
0x18001b165  mov     r9b, 1
0x18001b168  jmp     loc_18001AEF4
0x18001b16d  test    dl, dl
0x18001b16f  jnz     loc_18001AEF6
0x18001b175  mov     dl, 1
0x18001b177  mov     rdi, rcx
0x18001b17a  jmp     loc_18001AEF6
0x18001b17f  movzx   r9d, ax
0x18001b183  cmp     r10, rcx
0x18001b186  jz      short loc_18001B19C
0x18001b188  test    dl, dl
0x18001b18a  jnz     loc_18001B3CE
0x18001b190  cmp     r11, r10
0x18001b193  jnz     loc_18001B5AE
0x18001b199  mov     r11, rcx
0x18001b19c  test    r9w, r9w
0x18001b1a0  jz      short loc_18001B1AC
  ... truncated ...
```
