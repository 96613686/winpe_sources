# AddWapContent(IXMLDOMNode *,uchar *,ulong,ushort *)

- ea: `0x180028bc0`
- end: `0x1800293c4`
- name: `?AddWapContent@@YAJPEAUIXMLDOMNode@@PEAEKPEAG@Z`
- size: `2052`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, BYTE *pbBinary, DWORD cbBinary, unsigned __int16 *Src)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003056c`
- `0x180052b44`

## callees

- `0x180003650`
- `0x180003a60`
- `0x180003a90`
- `0x18000498c`
- `0x18000659c`
- `0x1800069f0`
- `0x180006c84`
- `0x18000ae8c`
- `0x18000d388`
- `0x18000df8c`
- `0x18000e05c`
- `0x18000e534`
- `0x1800127bc`
- `0x180012c48`
- `0x180013d40`
- `0x18002623c`
- `0x180028858`
- `0x1800288f4`
- `0x180028bc0`
- `0x18002ac18`
- `0x18003214c`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180028ca9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180029368`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180028ca9`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180029368`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002904f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029091`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002904f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180029091`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180028d59`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180028d59`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AddWapContent(struct IXMLDOMNode *a1, BYTE *pbBinary, DWORD cbBinary, unsigned __int16 *Src)
{
  int v8; // r15d
  _QWORD *v9; // rax
  int Base64String; // ebx
  const unsigned __int16 *v12; // r8
  wchar_t *v13; // rax
  __int64 v14; // r8
  wchar_t *v15; // r14
  unsigned __int64 v16; // rdx
  void **v17; // rdi
  __int64 v18; // rbx
  unsigned __int64 v19; // rdx
  void **v20; // rdi
  __int64 v21; // rbx
  void **v22; // r14
  char *v23; // rbx
  __int64 v24; // rax
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // r8
  void **v27; // rdx
  unsigned __int64 v28; // rdi
  unsigned __int64 v29; // r8
  void **v30; // rax
  _QWORD *v31; // r14
  __int64 v32; // r12
  __int64 inserted; // rdi
  __int64 v34; // rbx
  __int64 v35; // r8
  _OWORD *v36; // rdi
  __int128 *v37; // rdx
  __int64 v38; // r8
  __int128 *v39; // rdx
  __int64 v40; // r8
  unsigned __int16 **v41; // rdi
  char *v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rdx
  unsigned __int16 **v45; // rcx
  char *v46; // r10
  unsigned __int16 **v47; // rax
  char *v48; // rcx
  unsigned __int16 **v49; // rax
  __int64 v50; // rdx
  unsigned __int64 v51; // r10
  unsigned __int16 **v52; // rax
  __int64 v53; // rbx
  const unsigned __int16 *v54; // r8
  const unsigned __int16 *v55; // r8
  int v56; // esi
  _QWORD *v57; // rbx
  struct IXMLDOMNode *v58; // rdi
  const unsigned __int16 *v59; // r8
  const unsigned __int16 *v60; // rdx
  __int64 **v61; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  _QWORD *v64; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v65; // [rsp+28h] [rbp-D8h]
  struct IXMLDOMNode *v66; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v67; // [rsp+38h] [rbp-C8h]
  _QWORD **v68; // [rsp+40h] [rbp-C0h]
  _OWORD *v69; // [rsp+48h] [rbp-B8h]
  __int64 v70; // [rsp+50h] [rbp-B0h] BYREF
  int v71; // [rsp+58h] [rbp-A8h]
  int v72; // [rsp+5Ch] [rbp-A4h]
  char v73[24]; // [rsp+60h] [rbp-A0h] BYREF
  char v74[128]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v75[104]; // [rsp+F8h] [rbp-8h] BYREF
  void *v76[2]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v77; // [rsp+170h] [rbp+70h]
  unsigned __int64 v78; // [rsp+178h] [rbp+78h]
  unsigned __int16 *v79[2]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v80; // [rsp+190h] [rbp+90h]
  unsigned __int64 v81; // [rsp+198h] [rbp+98h]
  __int128 v82; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v83; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v84; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 *v85[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v86; // [rsp+1D0h] [rbp+D0h]
  unsigned __int64 v87; // [rsp+1D8h] [rbp+D8h]
  unsigned __int16 *v88[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v89; // [rsp+1F0h] [rbp+F0h]
  unsigned __int64 v90; // [rsp+1F8h] [rbp+F8h]

  v8 = 0;
  *(_OWORD *)v85 = 0;
  v86 = 0;
  v87 = 7;
  LOWORD(v85[0]) = 0;
  *(_OWORD *)v79 = 0;
  v80 = 0;
  v81 = 7;
  LOWORD(v79[0]) = 0;
  v65 = 0;
  v9 = operator new(0x60u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  v64 = v9;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v73);
  v66 = 0;
  if ( pbBinary && cbBinary )
  {
    Base64String = GetBase64String(pbBinary, cbBinary);
    if ( Base64String < 0 )
      goto LABEL_4;
    std::basic_stringbuf<unsigned short>::str(v74, v88);
    v12 = (const unsigned __int16 *)v88;
    if ( v90 > 7 )
      v12 = v88[0];
    Base64String = Windows::Sms::Common::CSmsUtil::AddElement(a1, L"Data", v12, 0);
    std::wstring::~wstring((char **)v88);
    if ( Base64String < 0 )
      goto LABEL_4;
  }
  *(_OWORD *)v76 = 0;
  v77 = 0;
  v78 = 7;
  LOWORD(v76[0]) = 0;
  while ( Src && *Src )
  {
    v13 = wcsstr(Src, L"\r\n");
    v15 = v13;
    if ( v13 )
    {
      v16 = v13 - Src;
      if ( v16 > v78 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)v76,
          v16,
          v14,
          Src);
      }
      else
      {
        v17 = v76;
        if ( v78 > 7 )
          v17 = (void **)v76[0];
        v77 = v13 - Src;
        v18 = 2 * v16;
        memmove_0(v17, Src, 2 * v16);
        *(_WORD *)((char *)v17 + v18) = 0;
      }
      Src = v15 + 2;
    }
    else
    {
      v19 = -1;
      do
        ++v19;
      while ( Src[v19] );
      if ( v19 > v78 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)v76,
          v19,
          v14,
          Src);
      }
      else
      {
        v20 = v76;
        if ( v78 > 7 )
          v20 = (void **)v76[0];
        v77 = v19;
        v21 = 2 * v19;
        memmove_0(v20, Src, 2 * v19);
        *(_WORD *)((char *)v20 + v21) = 0;
      }
      Src = 0;
    }
    v22 = v76;
    if ( v78 > 7 )
      v22 = (void **)v76[0];
    if ( !v77 || (v23 = (char *)v22 + 2 * v77, v24 = _std_search_2(v22, v23, L":", 1), (char *)v24 == v23) )
      v25 = -1;
    else
      v25 = (v24 - (__int64)v22) >> 1;
    if ( v25 != -1 )
    {
      v82 = 0;
      v83 = 0;
      v84 = 0;
      v26 = v77;
      if ( v77 >= v25 )
        v26 = v25;
      v27 = v76;
      if ( v78 > 7 )
        v27 = (void **)v76[0];
      std::wstring::_Construct<1,unsigned short const *>((char **)&v82, v27, v26);
      v28 = v25 + 1;
      *(_OWORD *)v88 = 0;
      v89 = 0;
      v90 = 0;
      if ( v77 < v28 )
        std::_String_val<std::_Simple_types<char>>::_Xran();
      v29 = -1;
      if ( v77 - v28 != -1 )
        v29 = v77 - v28;
      v30 = v76;
      if ( v78 > 7 )
        v30 = (void **)v76[0];
      std::wstring::_Construct<1,unsigned short const *>((char **)v88, (char *)v30 + 2 * v28, v29);
      TrimString(&v82);
      TrimString(v88);
      if ( v83 )
      {
        v31 = v64;
        v32 = v64[1];
        v67 = 0;
        inserted = (__int64)v64;
        v34 = v32;
        if ( !*(_BYTE *)(v32 + 25) )
        {
          do
          {
            v32 = v34;
            if ( (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)(v34 + 32), (const wchar_t *)&v82) )
            {
              v8 = 0;
              v34 = *(_QWORD *)(v34 + 16);
            }
            else
            {
              v8 = 1;
              inserted = v34;
              v34 = *(_QWORD *)v34;
            }
          }
          while ( !*(_BYTE *)(v34 + 25) );
          v31 = v64;
        }
        if ( *(_BYTE *)(inserted + 25) )
        {
LABEL_51:
          if ( v65 == 0x2AAAAAAAAAAAAAALL )
            std::_Throw_tree_length_error();
          v68 = &v64;
          v69 = 0;
          v36 = operator new(0x60u);
          v69 = v36;
          std::wstring::wstring((__int64)(v36 + 2), (__int64)&v82);
          v36[4] = 0;
          *((_QWORD *)v36 + 10) = 0;
          *((_QWORD *)v36 + 11) = 7;
          *((_WORD *)v36 + 32) = 0;
          *(_QWORD *)v36 = v31;
          *((_QWORD *)v36 + 1) = v31;
          *((_QWORD *)v36 + 2) = v31;
          *((_WORD *)v36 + 12) = 0;
          v69 = 0;
          v70 = v32;
          v71 = v8;
          v72 = v67;
          inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_GUID>>>::_Insert_node(
                       &v64,
                       (__int64)&v70,
                       (__int64)v36);
        }
        else if ( (unsigned __int8)std::operator<<unsigned short>(
                                     (const wchar_t *)&v82,
                                     (const wchar_t *)(inserted + 32)) )
        {
          v31 = v64;
          goto LABEL_51;
        }
        std::wstring::operator=(inserted + 64, v88, v35);
        v37 = &v82;
        if ( v84 > 7 )
          v37 = (__int128 *)v82;
        v8 = 0;
        if ( (unsigned int)_o__wcsicmp(L"X-Wap-Application-Id", v37) )
        {
          v39 = &v82;
          if ( v84 > 7 )
            v39 = (__int128 *)v82;
          if ( !(unsigned int)_o__wcsicmp(L"Content-Type", v39) )
          {
            std::wstring::operator=((__int64)v79, v88, v40);
            v41 = v79;
            if ( v81 > 7 )
              v41 = (unsigned __int16 **)v79[0];
            if ( v80 )
            {
              v42 = (char *)v41 + 2 * v80;
              v43 = _std_search_2(v41, v42, L";", 1);
              if ( (char *)v43 != v42 )
              {
                v44 = (v43 - (__int64)v41) >> 1;
                if ( v44 != -1 )
                {
                  v45 = v79;
                  if ( v81 > 7 )
                    v45 = (unsigned __int16 **)v79[0];
                  v46 = (char *)v45 + 2 * v80;
                  v47 = v79;
                  if ( v81 > 7 )
                    v47 = (unsigned __int16 **)v79[0];
                  v48 = (char *)v47 + 2 * v44;
                  v49 = v79;
                  if ( v81 > 7 )
                    v49 = (unsigned __int16 **)v79[0];
                  v50 = (v48 - (char *)v49) >> 1;
                  v51 = (v46 - v48) >> 1;
                  if ( v80 - v50 < v51 )
                    v51 = v80 - v50;
                  v52 = v79;
                  if ( v81 > 7 )
                    v52 = (unsigned __int16 **)v79[0];
                  v53 = v80 - v51;
                  memmove_0((char *)v52 + 2 * v50, (char *)v52 + 2 * v50 + 2 * v51, 2 * (v80 - v51 - v50) + 2);
                  v80 = v53;
                }
              }
            }
          }
        }
        else
        {
          std::wstring::operator=((__int64)v85, v88, v38);
        }
      }
      std::wstring::~wstring((char **)v88);
      std::wstring::~wstring((char **)&v82);
    }
  }
  if ( v86 )
  {
    v54 = (const unsigned __int16 *)v85;
    if ( v87 > 7 )
      v54 = v85[0];
    Base64String = Windows::Sms::Common::CSmsUtil::AddElement(a1, L"ApplicationId", v54, 0);
    if ( Base64String < 0 )
      goto LABEL_82;
  }
  if ( v80 )
  {
    v55 = (const unsigned __int16 *)v79;
    if ( v81 > 7 )
      v55 = v79[0];
    Base64String = Windows::Sms::Common::CSmsUtil::AddElement(a1, L"ContentType", v55, 0);
    if ( Base64String < 0 )
    {
LABEL_82:
      std::wstring::~wstring((char **)v76);
LABEL_4:
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v75);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v75);
      std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v64);
      std::wstring::~wstring((char **)v79);
      std::wstring::~wstring((char **)v85);
      return (unsigned int)Base64String;
    }
  }
  v56 = Windows::Sms::Common::CSmsUtil::AddElement(a1, L"WapHeaders", 0, &v66);
  if ( v56 >= 0 )
  {
    v57 = (_QWORD *)*v64;
    v58 = v66;
    while ( v57 != v64 )
    {
      v59 = (const unsigned __int16 *)(v57 + 8);
      if ( v57[11] > 7u )
        v59 = *(const unsigned __int16 **)v59;
      v60 = (const unsigned __int16 *)(v57 + 4);
      if ( v57[7] > 7u )
        v60 = *(const unsigned __int16 **)v60;
      v56 = Windows::Sms::Common::CSmsUtil::AddElement(v58, v60, v59, 0);
      if ( v56 < 0 )
      {
        std::wstring::~wstring((char **)v76);
        if ( v58 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v58->lpVtbl->Release)(v58);
        goto LABEL_112;
      }
      v61 = (__int64 **)v57[2];
      if ( *((_BYTE *)v61 + 25) )
      {
        for ( i = v57[1]; !*(_BYTE *)(i + 25) && v57 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
          v57 = (_QWORD *)i;
        v57 = (_QWORD *)i;
      }
      else
      {
        v57 = (_QWORD *)v57[2];
        for ( j = *v61; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v57 = j;
      }
    }
    std::wstring::~wstring((char **)v76);
    if ( v58 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v58->lpVtbl->Release)(v58);
  }
  else
  {
    std::wstring::~wstring((char **)v76);
    if ( v66 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v66->lpVtbl->Release)(v66);
  }
LABEL_112:
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v75);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v75);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v64);
  std::wstring::~wstring((char **)v79);
  std::wstring::~wstring((char **)v85);
  return (unsigned int)v56;
}

```

## disassembly

```asm
0x180028bc0  push    rbp
0x180028bc2  push    rbx
0x180028bc3  push    rsi
0x180028bc4  push    rdi
0x180028bc5  push    r12
0x180028bc7  push    r13
0x180028bc9  push    r14
0x180028bcb  push    r15
0x180028bcd  lea     rbp, [rsp-118h]
0x180028bd5  sub     rsp, 218h
0x180028bdc  mov     rax, cs:__security_cookie
0x180028be3  xor     rax, rsp
0x180028be6  mov     [rbp+150h+var_50], rax
0x180028bed  mov     rsi, r9
0x180028bf0  mov     ebx, r8d
0x180028bf3  mov     rdi, rdx
0x180028bf6  mov     r13, rcx
0x180028bf9  xor     r15d, r15d
0x180028bfc  xorps   xmm0, xmm0
0x180028bff  movups  xmmword ptr [rbp+150h+var_90], xmm0
0x180028c06  mov     [rbp+150h+var_80], r15
0x180028c0d  lea     r12d, [r15+7]
0x180028c11  mov     [rbp+150h+var_78], r12
0x180028c18  mov     word ptr [rbp+150h+var_90], r15w
0x180028c20  movups  xmmword ptr [rbp+150h+var_D0], xmm0
0x180028c27  mov     [rbp+150h+var_C0], r15
0x180028c2e  mov     [rbp+150h+var_B8], r12
0x180028c35  mov     word ptr [rbp+150h+var_D0], r15w
0x180028c3d  mov     [rsp+250h+var_230], r15
0x180028c42  mov     [rsp+250h+var_228], r15
0x180028c47  lea     ecx, [r15+60h]; Size
0x180028c4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028c50  mov     [rax], rax
0x180028c53  mov     [rax+8], rax
0x180028c57  mov     [rax+10h], rax
0x180028c5b  mov     word ptr [rax+18h], 101h
0x180028c61  mov     [rsp+250h+var_230], rax
0x180028c66  lea     rcx, [rsp+250h+var_1F0]
0x180028c6b  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180028c70  nop
0x180028c71  mov     [rsp+250h+var_220], r15
0x180028c76  test    rdi, rdi
0x180028c79  jz      loc_180028D2C
0x180028c7f  test    ebx, ebx
0x180028c81  jz      loc_180028D2C
0x180028c87  lea     r8, [rsp+250h+var_1F0]
0x180028c8c  mov     edx, ebx; cbBinary
0x180028c8e  mov     rcx, rdi; pbBinary
0x180028c91  call    ?GetBase64String@@YAJPEAEKAEAV?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetBase64String(uchar *,ulong,std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)
0x180028c96  mov     ebx, eax
0x180028c98  test    eax, eax
0x180028c9a  jns     short loc_180028CDB
0x180028c9c  lea     rcx, [rbp+150h+var_158]
0x180028ca0  call    ??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180028ca5  lea     rcx, [rbp+150h+var_158]
0x180028ca9  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180028caf  nop
0x180028cb0  lea     rcx, [rsp+250h+var_230]
0x180028cb5  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180028cba  nop
0x180028cbb  lea     rcx, [rbp+150h+var_D0]; void *
0x180028cc2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028cc7  nop
0x180028cc8  lea     rcx, [rbp+150h+var_90]; void *
0x180028ccf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028cd4  mov     eax, ebx
0x180028cd6  jmp     loc_180029395
0x180028cdb  lea     rdx, [rbp+150h+var_70]
0x180028ce2  lea     rcx, [rsp+250h+var_1D8]
0x180028ce7  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180028cec  nop
0x180028ced  lea     r8, [rbp+150h+var_70]
0x180028cf4  cmp     [rbp+150h+var_58], r12
0x180028cfb  cmova   r8, [rbp+150h+var_70]; unsigned __int16 *
0x180028d03  xor     r9d, r9d; struct IXMLDOMNode **
0x180028d06  lea     rdx, aData; "Data"
0x180028d0d  mov     rcx, r13; struct IXMLDOMNode *
0x180028d10  call    ?AddElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG1PEAPEAU5@@Z; Windows::Sms::Common::CSmsUtil::AddElement(IXMLDOMNode *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180028d15  mov     ebx, eax
0x180028d17  lea     rcx, [rbp+150h+var_70]; void *
0x180028d1e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028d23  test    ebx, ebx
0x180028d25  jns     short loc_180028D2C
0x180028d27  jmp     loc_180028C9C
0x180028d2c  xorps   xmm0, xmm0
0x180028d2f  movups  xmmword ptr [rbp+150h+var_F0], xmm0
0x180028d33  mov     [rbp+150h+var_E0], r15
0x180028d37  mov     [rbp+150h+var_D8], r12
0x180028d3b  mov     word ptr [rbp+150h+var_F0], r15w
0x180028d40  jmp     loc_1800291BB
0x180028d45  cmp     [rsi], r15w
0x180028d49  jz      loc_1800291C4
0x180028d4f  lea     rdx, SubStr; "\r\n"
0x180028d56  mov     rcx, rsi; Str
0x180028d59  call    cs:__imp_wcsstr
0x180028d5f  mov     r14, rax
0x180028d62  test    rax, rax
0x180028d65  jz      short loc_180028DB2
0x180028d67  mov     rdx, rax
0x180028d6a  sub     rdx, rsi
0x180028d6d  sar     rdx, 1
0x180028d70  cmp     rdx, [rbp+150h+var_D8]
0x180028d74  ja      short loc_180028DA0
0x180028d76  lea     rdi, [rbp+150h+var_F0]
0x180028d7a  cmp     [rbp+150h+var_D8], r12
0x180028d7e  cmova   rdi, [rbp+150h+var_F0]
0x180028d83  mov     [rbp+150h+var_E0], rdx
0x180028d87  lea     rbx, [rdx+rdx]
0x180028d8b  mov     r8, rbx; Size
0x180028d8e  mov     rdx, rsi; Src
0x180028d91  mov     rcx, rdi; void *
0x180028d94  call    memmove_0
0x180028d99  mov     [rbx+rdi], r15w
0x180028d9e  jmp     short loc_180028DAC
0x180028da0  mov     r9, rsi
0x180028da3  lea     rcx, [rbp+150h+var_F0]
0x180028da7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180028dac  lea     rsi, [r14+4]
0x180028db0  jmp     short loc_180028DFF
0x180028db2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180028db6  inc     rdx
0x180028db9  cmp     [rsi+rdx*2], r15w
0x180028dbe  jnz     short loc_180028DB6
0x180028dc0  cmp     rdx, [rbp+150h+var_D8]
0x180028dc4  ja      short loc_180028DF0
0x180028dc6  lea     rdi, [rbp+150h+var_F0]
0x180028dca  cmp     [rbp+150h+var_D8], r12
0x180028dce  cmova   rdi, [rbp+150h+var_F0]
0x180028dd3  mov     [rbp+150h+var_E0], rdx
0x180028dd7  lea     rbx, [rdx+rdx]
0x180028ddb  mov     r8, rbx; Size
0x180028dde  mov     rdx, rsi; Src
0x180028de1  mov     rcx, rdi; void *
0x180028de4  call    memmove_0
0x180028de9  mov     [rbx+rdi], r15w
0x180028dee  jmp     short loc_180028DFC
0x180028df0  mov     r9, rsi
0x180028df3  lea     rcx, [rbp+150h+var_F0]
0x180028df7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180028dfc  mov     rsi, r15
0x180028dff  mov     rax, [rbp+150h+var_E0]
0x180028e03  lea     r14, [rbp+150h+var_F0]
0x180028e07  cmp     [rbp+150h+var_D8], r12
0x180028e0b  cmova   r14, [rbp+150h+var_F0]
0x180028e10  cmp     rax, 1
0x180028e14  jb      short loc_180028E42
0x180028e16  lea     rbx, [r14+rax*2]
0x180028e1a  mov     r9d, 1
0x180028e20  lea     r8, asc_1800767A4; ":"
0x180028e27  mov     rdx, rbx
0x180028e2a  mov     rcx, r14
0x180028e2d  call    __std_search_2
0x180028e32  mov     rdi, rax
0x180028e35  cmp     rax, rbx
0x180028e38  jz      short loc_180028E42
0x180028e3a  sub     rdi, r14
0x180028e3d  sar     rdi, 1
0x180028e40  jmp     short loc_180028E46
0x180028e42  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180028e46  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180028e4a  jz      loc_1800291BB
0x180028e50  xorps   xmm0, xmm0
0x180028e53  movups  [rbp+150h+var_B0], xmm0
0x180028e5a  mov     [rbp+150h+var_A0], r15
0x180028e61  mov     [rbp+150h+var_98], r15
0x180028e68  mov     r8, [rbp+150h+var_E0]
0x180028e6c  cmp     r8, rdi
0x180028e6f  cmovnb  r8, rdi
0x180028e73  lea     rdx, [rbp+150h+var_F0]
0x180028e77  cmp     [rbp+150h+var_D8], r12
0x180028e7b  cmova   rdx, [rbp+150h+var_F0]
0x180028e80  lea     rcx, [rbp+150h+var_B0]
0x180028e87  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028e8c  nop
0x180028e8d  inc     rdi
0x180028e90  xorps   xmm0, xmm0
0x180028e93  movups  xmmword ptr [rbp+150h+var_70], xmm0
0x180028e9a  mov     [rbp+150h+var_60], r15
0x180028ea1  mov     [rbp+150h+var_58], r15
0x180028ea8  mov     rax, [rbp+150h+var_E0]
0x180028eac  cmp     rax, rdi
0x180028eaf  jb      loc_1800293B8
0x180028eb5  sub     rax, rdi
0x180028eb8  or      r8, 0FFFFFFFFFFFFFFFFh
0x180028ebc  cmp     rax, r8
0x180028ebf  cmovb   r8, rax
0x180028ec3  lea     rax, [rbp+150h+var_F0]
0x180028ec7  cmp     [rbp+150h+var_D8], r12
0x180028ecb  cmova   rax, [rbp+150h+var_F0]
0x180028ed0  lea     rdx, [rax+rdi*2]
0x180028ed4  lea     rcx, [rbp+150h+var_70]
0x180028edb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028ee0  nop
0x180028ee1  lea     rcx, [rbp+150h+var_B0]; void *
0x180028ee8  call    ?TrimString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrimString(std::wstring &)
0x180028eed  lea     rcx, [rbp+150h+var_70]; void *
0x180028ef4  call    ?TrimString@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrimString(std::wstring &)
0x180028ef9  cmp     [rbp+150h+var_A0], r15
0x180028f00  jz      loc_1800291A2
0x180028f06  mov     r14, [rsp+250h+var_230]
0x180028f0b  mov     r12, [r14+8]
0x180028f0f  xor     eax, eax
0x180028f11  mov     [rsp+250h+var_218], rax
0x180028f16  mov     rdi, r14
0x180028f19  mov     rbx, r12
0x180028f1c  cmp     [r12+19h], al
0x180028f21  jnz     short loc_180028F5A
0x180028f23  mov     r12, rbx
0x180028f26  lea     rcx, [rbx+20h]
0x180028f2a  lea     rdx, [rbp+150h+var_B0]
0x180028f31  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180028f36  test    al, al
0x180028f38  jz      short loc_180028F43
0x180028f3a  xor     r15d, r15d
0x180028f3d  mov     rbx, [rbx+10h]
0x180028f41  jmp     short loc_180028F4F
0x180028f43  mov     r15d, 1
0x180028f49  mov     rdi, rbx
0x180028f4c  mov     rbx, [rbx]
0x180028f4f  cmp     byte ptr [rbx+19h], 0
0x180028f53  jz      short loc_180028F23
0x180028f55  mov     r14, [rsp+250h+var_230]
0x180028f5a  cmp     byte ptr [rdi+19h], 0
0x180028f5e  jnz     short loc_180028F7D
0x180028f60  lea     rdx, [rdi+20h]
0x180028f64  lea     rcx, [rbp+150h+var_B0]
0x180028f6b  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180028f70  test    al, al
0x180028f72  jz      loc_18002901C
0x180028f78  mov     r14, [rsp+250h+var_230]
0x180028f7d  mov     rax, 2AAAAAAAAAAAAAAh
0x180028f87  cmp     [rsp+250h+var_228], rax
0x180028f8c  jz      loc_1800293BE
0x180028f92  lea     rax, [rsp+250h+var_230]
0x180028f97  mov     [rsp+250h+var_210], rax
0x180028f9c  mov     [rsp+250h+var_208], 0
0x180028fa5  mov     ecx, 60h ; '`'; Size
0x180028faa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028faf  mov     rdi, rax
0x180028fb2  mov     [rsp+250h+var_208], rax
0x180028fb7  lea     rdx, [rbp+150h+var_B0]
0x180028fbe  lea     rcx, [rax+20h]
0x180028fc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180028fc7  xorps   xmm0, xmm0
0x180028fca  movups  xmmword ptr [rdi+40h], xmm0
0x180028fce  xor     ecx, ecx
0x180028fd0  mov     [rdi+50h], rcx
0x180028fd4  mov     qword ptr [rdi+58h], 7
0x180028fdc  mov     [rdi+40h], cx
0x180028fe0  mov     [rdi], r14
0x180028fe3  mov     [rdi+8], r14
0x180028fe7  mov     [rdi+10h], r14
0x180028feb  mov     [rdi+18h], cx
0x180028fef  mov     [rsp+250h+var_208], rcx
0x180028ff4  mov     [rsp+250h+var_200], r12
0x180028ff9  mov     [rsp+250h+var_1F8], r15d
0x180028ffe  mov     rax, [rsp+250h+var_218]
0x180029003  mov     [rsp+250h+var_1F4], eax
0x180029007  mov     r8, rdi
0x18002900a  lea     rdx, [rsp+250h+var_200]
0x18002900f  lea     rcx, [rsp+250h+var_230]
0x180029014  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@U1@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@U1@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@U1@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,_GUID>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,_GUID>,void *> *>,std::_Tree_node<std::pair<_GUID const,_GUID>,void *> * const)
0x180029019  mov     rdi, rax
0x18002901c  lea     rcx, [rdi+40h]
0x180029020  lea     rdx, [rbp+150h+var_70]
0x180029027  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002902c  lea     rdx, [rbp+150h+var_B0]
0x180029033  mov     r12d, 7
0x180029039  cmp     [rbp+150h+var_98], r12
0x180029040  cmova   rdx, qword ptr [rbp+150h+var_B0]
0x180029048  lea     rcx, aXWapApplicatio; "X-Wap-Application-Id"
0x18002904f  call    cs:__imp__o__wcsicmp
0x180029055  xor     r15d, r15d
0x180029058  test    eax, eax
0x18002905a  jnz     short loc_180029074
0x18002905c  lea     rdx, [rbp+150h+var_70]
0x180029063  lea     rcx, [rbp+150h+var_90]
0x18002906a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002906f  jmp     loc_1800291A2
0x180029074  lea     rdx, [rbp+150h+var_B0]
0x18002907b  cmp     [rbp+150h+var_98], r12
0x180029082  cmova   rdx, qword ptr [rbp+150h+var_B0]
0x18002908a  lea     rcx, aContentType; "Content-Type"
0x180029091  call    cs:__imp__o__wcsicmp
0x180029097  test    eax, eax
0x180029099  jnz     loc_1800291A2
0x18002909f  lea     rdx, [rbp+150h+var_70]
0x1800290a6  lea     rcx, [rbp+150h+var_D0]
0x1800290ad  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800290b2  mov     rax, [rbp+150h+var_C0]
0x1800290b9  lea     rdi, [rbp+150h+var_D0]
0x1800290c0  cmp     [rbp+150h+var_B8], r12
0x1800290c7  cmova   rdi, [rbp+150h+var_D0]
0x1800290cf  cmp     rax, 1
0x1800290d3  jb      loc_1800291A2
0x1800290d9  lea     rbx, [rdi+rax*2]
0x1800290dd  mov     r9d, 1
0x1800290e3  lea     r8, asc_1800767BC; ";"
0x1800290ea  mov     rdx, rbx
0x1800290ed  mov     rcx, rdi
  ... truncated ...
```
