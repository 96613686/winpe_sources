# WOSCSettings::GetAllSettings(void)

- ea: `0x18003d614`
- end: `0x18003dc69`
- name: `?GetAllSettings@WOSCSettings@@QEAA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@XZ`
- size: `1621`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180042130`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x180008560`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800209fc`
- `0x18002127c`
- `0x18003d02c`
- `0x18003d0f4`
- `0x18003d614`
- `0x18003ea84`
- `0x18003ecb4`
- `0x180071010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003dbb8`
- `msvcp_win!_Mtx_unlock` at `0x18003dbb8`
- `msvcp_win!_Mtx_lock` at `0x18003d65b`
- `msvcp_win!_Mtx_lock` at `0x18003d65b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003d66a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003d685`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003d66a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003d685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d8c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003da94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dabb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d88e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d8c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003da94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003dabb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d8ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d935`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d8ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d935`

## string_xrefs

- `0x18003dbe8`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003dbfd`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003dc12`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003dc2d`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003dc42`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x18003dc57`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
_QWORD *__fastcall WOSCSettings::GetAllSettings(__int64 **a1, _QWORD *a2)
{
  __int64 **v4; // rbx
  __int64 *v5; // rcx
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  _QWORD *v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 **); // rsi
  __int64 *v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // r14d
  __int64 *v18; // rsi
  __int64 (__fastcall *v19)(__int64 *, HSTRING *); // rdi
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, _DWORD *); // rdi
  int v25; // eax
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, _DWORD *); // rdi
  PCWSTR StringRawBuffer; // rax
  __int64 v29; // r8
  PCWSTR v30; // rax
  __int64 v31; // r8
  __int64 inserted; // rdi
  __int64 v33; // r8
  __int64 v34; // rdi
  _OWORD *v35; // rax
  void **v36; // rcx
  unsigned __int64 v37; // rdx
  void **v38; // r9
  char *v39; // rsi
  __int64 v40; // rdi
  int v41; // eax
  __int64 v42; // rdi
  __int64 (__fastcall *v43)(__int64, __int64 **); // rsi
  __int64 *v44; // rcx
  int v45; // eax
  __int64 *v46; // rcx
  __int64 v47; // rcx
  int v49; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v50[3]; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v51; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v52; // [rsp+38h] [rbp-C8h] BYREF
  int *v53; // [rsp+40h] [rbp-C0h]
  int v54; // [rsp+48h] [rbp-B8h]
  int v55; // [rsp+50h] [rbp-B0h]
  __int64 v56; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v57; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v58; // [rsp+68h] [rbp-98h] BYREF
  UINT32 length; // [rsp+70h] [rbp-90h] BYREF
  __int64 v60; // [rsp+78h] [rbp-88h] BYREF
  __int128 v61; // [rsp+80h] [rbp-80h] BYREF
  __int64 v62; // [rsp+90h] [rbp-70h]
  _QWORD *v63; // [rsp+A0h] [rbp-60h]
  __int64 v64; // [rsp+A8h] [rbp-58h]
  _QWORD *v65; // [rsp+B0h] [rbp-50h]
  __int64 **v66; // [rsp+B8h] [rbp-48h]
  __int128 v67; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v68; // [rsp+D0h] [rbp-30h]
  void *Src[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v70; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v71; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v65 = a2;
  v55 = 0;
  v4 = a1 + 1;
  v66 = a1 + 1;
  if ( _Mtx_lock((_Mtx_t)(a1 + 1)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v4 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v4 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v58 = 0;
  v5 = *a1;
  v6 = **a1;
  v58 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 96))(v5, &v58);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
      (const char *)(unsigned int)v7,
      v49);
  v60 = 0;
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v58)(
         v58,
         &GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099,
         &v60);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
      (const char *)(unsigned int)v8,
      v49);
  v50[0] = 0;
  *a2 = 0;
  a2[1] = 0;
  v9 = operator new(0x60u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *a2 = v9;
  v55 = 1;
  v51 = 0;
  v52 = 0;
  v53 = v50;
  v54 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v60 + 48LL))(v60, &v51);
  *v53 = v10;
  if ( v10 >= 0 )
  {
    LOBYTE(v49) = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 56LL))(v51, &v49);
    *v53 = v11;
    if ( v11 < 0 || !(_BYTE)v49 )
      goto LABEL_13;
    v12 = v51;
    v13 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v51 + 48LL);
    v14 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
    }
    v15 = v13(v12, &v52);
    *v53 = v15;
    if ( v15 < 0 )
    {
LABEL_13:
      v16 = v51;
      if ( v51 )
      {
        v51 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
  }
  v55 = 3;
  v17 = (v51 != 0) - 1;
  while ( *v53 >= 0 && v17 != -1 )
  {
    v57 = 0;
    v18 = v52;
    v19 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v52 + 48);
    WindowsDeleteString(0);
    v57 = 0;
    v20 = v19(v18, &v57);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
        (const char *)(unsigned int)v20,
        v49);
    v56 = 0;
    v21 = *v52;
    v56 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v21 + 56))(v52, &v56);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
        (const char *)(unsigned int)v22,
        v49);
    *(_QWORD *)&v50[1] = 0;
    v23 = v56;
    v24 = *(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v56 + 64LL);
    WindowsDeleteString(0);
    *(_QWORD *)&v50[1] = 0;
    v25 = v24(v23, &v50[1]);
    v50[0] = v25;
    if ( v25 == -2147483634 )
    {
      v26 = v56;
      v27 = *(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v56 + 56LL);
      WindowsDeleteString(*(HSTRING *)&v50[1]);
      *(_QWORD *)&v50[1] = 0;
      v25 = v27(v26, &v50[1]);
      v50[0] = v25;
    }
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
        (const char *)(unsigned int)v25,
        v49);
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&v50[1], &length);
    *(_OWORD *)Src = 0;
    v70 = 0;
    v71 = 0;
    v29 = -1;
    do
      ++v29;
    while ( StringRawBuffer[v29] );
    std::wstring::_Construct<1,unsigned short const *>(Src, StringRawBuffer, v29);
    v30 = WindowsGetStringRawBuffer(v57, 0);
    v67 = 0;
    v68 = 0u;
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
    std::wstring::_Construct<1,unsigned short const *>(&v67, v30, v31);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
      a2,
      &v61,
      &v67);
    inserted = v62;
    if ( *(_BYTE *)(v62 + 25) || (unsigned __int8)std::operator<<unsigned short>(&v67, v62 + 32) )
    {
      if ( a2[1] == 0x2AAAAAAAAAAAAAALL )
        std::_Throw_tree_length_error();
      v34 = *a2;
      v63 = a2;
      v64 = 0;
      v35 = operator new(0x60u);
      v35[2] = v67;
      v35[3] = v68;
      *(_QWORD *)&v68 = 0;
      *((_QWORD *)&v68 + 1) = 7;
      LOWORD(v67) = 0;
      v35[4] = 0;
      *((_QWORD *)v35 + 10) = 0;
      *((_QWORD *)v35 + 11) = 7;
      *((_WORD *)v35 + 32) = 0;
      *(_QWORD *)v35 = v34;
      *((_QWORD *)v35 + 1) = v34;
      *((_QWORD *)v35 + 2) = v34;
      *((_WORD *)v35 + 12) = 0;
      v64 = 0;
      inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned int>>>::_Insert_node(
                   a2,
                   &v61,
                   v35);
    }
    v36 = (void **)(inserted + 64);
    if ( (void **)(inserted + 64) != Src )
    {
      v37 = v70;
      v38 = Src;
      if ( v71 > 7 )
        v38 = (void **)Src[0];
      if ( v70 > *(_QWORD *)(inserted + 88) )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v36,
          v70,
          v33,
          v38);
      }
      else
      {
        if ( *(_QWORD *)(inserted + 88) <= 7u )
          v39 = (char *)(inserted + 64);
        else
          v39 = (char *)*v36;
        *(_QWORD *)(inserted + 80) = v70;
        v40 = 2 * v37;
        memmove_0(v39, v38, 2 * v37);
        *(_WORD *)&v39[v40] = 0;
      }
    }
    std::wstring::_Tidy_deallocate(&v67);
    std::wstring::_Tidy_deallocate(Src);
    WindowsDeleteString(*(HSTRING *)&v50[1]);
    *(_QWORD *)&v50[1] = 0;
    if ( v56 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
    WindowsDeleteString(v57);
    LOBYTE(v49) = 0;
    v41 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 64LL))(v51, &v49);
    *v53 = v41;
    if ( v41 < 0 || !(_BYTE)v49 )
      goto LABEL_48;
    v42 = v51;
    v43 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v51 + 48LL);
    v44 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
    }
    v45 = v43(v42, &v52);
    *v53 = v45;
    if ( v45 >= 0 )
      ++v17;
    else
LABEL_48:
      v17 = -1;
  }
  v46 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64 *))(*v46 + 16))(v46);
  }
  v47 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  if ( v50[0] < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
      (const char *)v50[0],
      v49);
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  if ( v58 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
  _Mtx_unlock((_Mtx_t)v4);
  return a2;
}

```

## disassembly

```asm
0x18003d614  mov     [rsp-8+arg_10], rbx
0x18003d619  push    rbp
0x18003d61a  push    rsi
0x18003d61b  push    rdi
0x18003d61c  push    r12
0x18003d61e  push    r13
0x18003d620  push    r14
0x18003d622  push    r15
0x18003d624  lea     rbp, [rsp-10h]
0x18003d629  sub     rsp, 110h
0x18003d630  mov     rax, cs:__security_cookie
0x18003d637  xor     rax, rsp
0x18003d63a  mov     [rbp+40h+var_40], rax
0x18003d63e  mov     r15, rdx
0x18003d641  mov     rdi, rcx
0x18003d644  mov     [rbp+40h+var_90], rdx
0x18003d648  xor     r12d, r12d
0x18003d64b  mov     [rsp+140h+var_F0], r12d
0x18003d650  lea     rbx, [rcx+8]
0x18003d654  mov     [rbp+40h+var_88], rbx
0x18003d658  mov     rcx, rbx; _Mtx_t
0x18003d65b  call    cs:__imp__Mtx_lock
0x18003d661  test    eax, eax
0x18003d663  jz      short loc_18003D671
0x18003d665  lea     ecx, [r12+5]
0x18003d66a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003d670  int     3; Trap to Debugger
0x18003d671  mov     eax, [rbx+4Ch]
0x18003d674  cmp     eax, 7FFFFFFFh
0x18003d679  jnz     short loc_18003D68C
0x18003d67b  dec     eax
0x18003d67d  mov     [rbx+4Ch], eax
0x18003d680  mov     ecx, 6
0x18003d685  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003d68b  nop
0x18003d68c  mov     [rsp+140h+var_D8], r12
0x18003d691  mov     rcx, [rdi]
0x18003d694  mov     rax, [rcx]
0x18003d697  mov     [rsp+140h+var_D8], r12
0x18003d69c  lea     rdx, [rsp+140h+var_D8]
0x18003d6a1  mov     rax, [rax+60h]
0x18003d6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6aa  mov     rcx, [rbp+48h]; this
0x18003d6ae  test    eax, eax
0x18003d6b0  js      loc_18003DBFA
0x18003d6b6  mov     [rsp+140h+var_C8], r12
0x18003d6bb  mov     rcx, [rsp+140h+var_D8]
0x18003d6c0  mov     rax, [rcx]
0x18003d6c3  lea     r8, [rsp+140h+var_C8]
0x18003d6c8  lea     rdx, _GUID_dfabb6e1_0411_5a8f_aa87_354e7110f099
0x18003d6cf  mov     rax, [rax]
0x18003d6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6d7  mov     rcx, [rbp+48h]; this
0x18003d6db  test    eax, eax
0x18003d6dd  js      loc_18003DC0F
0x18003d6e3  mov     dword ptr [rsp+140h+var_11C], r12d
0x18003d6e8  mov     [r15], r12
0x18003d6eb  mov     [r15+8], r12
0x18003d6ef  mov     ecx, 60h ; '`'; Size
0x18003d6f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d6f9  mov     [rax], rax
0x18003d6fc  mov     [rax+8], rax
0x18003d700  mov     [rax+10h], rax
0x18003d704  mov     word ptr [rax+18h], 101h
0x18003d70a  mov     [r15], rax
0x18003d70d  mov     [rsp+140h+var_F0], 1
0x18003d715  mov     rcx, [rsp+140h+var_C8]
0x18003d71a  mov     [rsp+140h+var_110], r12
0x18003d71f  mov     [rsp+140h+var_108], r12
0x18003d724  lea     rax, [rsp+140h+var_11C]
0x18003d729  mov     [rsp+140h+var_100], rax
0x18003d72e  mov     [rsp+140h+var_F8], r12d
0x18003d733  mov     rax, [rcx]
0x18003d736  lea     rdx, [rsp+140h+var_110]
0x18003d73b  mov     rax, [rax+30h]
0x18003d73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d744  mov     rcx, [rsp+140h+var_100]
0x18003d749  mov     [rcx], eax
0x18003d74b  test    eax, eax
0x18003d74d  js      loc_18003D7E1
0x18003d753  mov     byte ptr [rsp+140h+var_120], r12b; int
0x18003d758  mov     rcx, [rsp+140h+var_110]
0x18003d75d  mov     rax, [rcx]
0x18003d760  lea     rdx, [rsp+140h+var_120]
0x18003d765  mov     rax, [rax+38h]
0x18003d769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d76e  mov     rcx, [rsp+140h+var_100]
0x18003d773  mov     [rcx], eax
0x18003d775  test    eax, eax
0x18003d777  js      short loc_18003D7C5
0x18003d779  cmp     byte ptr [rsp+140h+var_120], r12b
0x18003d77e  jz      short loc_18003D7C5
0x18003d780  mov     rdi, [rsp+140h+var_110]
0x18003d785  mov     rax, [rdi]
0x18003d788  mov     rsi, [rax+30h]
0x18003d78c  mov     rcx, [rsp+140h+var_108]
0x18003d791  test    rcx, rcx
0x18003d794  jz      short loc_18003D7A8
0x18003d796  mov     [rsp+140h+var_108], r12
0x18003d79b  mov     rdx, [rcx]
0x18003d79e  mov     rax, [rdx+10h]
0x18003d7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7a7  nop
0x18003d7a8  lea     rdx, [rsp+140h+var_108]
0x18003d7ad  mov     rcx, rdi
0x18003d7b0  mov     rax, rsi
0x18003d7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7b8  mov     rcx, [rsp+140h+var_100]
0x18003d7bd  mov     [rcx], eax
0x18003d7bf  test    eax, eax
0x18003d7c1  jns     short loc_18003D7E1
0x18003d7c3  jmp     short $+2
0x18003d7c5  mov     rcx, [rsp+140h+var_110]
0x18003d7ca  test    rcx, rcx
0x18003d7cd  jz      short loc_18003D7E1
0x18003d7cf  mov     [rsp+140h+var_110], r12
0x18003d7d4  mov     rax, [rcx]
0x18003d7d7  mov     rax, [rax+10h]
0x18003d7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7e0  nop
0x18003d7e1  mov     [rsp+140h+var_F0], 3
0x18003d7e9  mov     rax, [rsp+140h+var_110]
0x18003d7ee  neg     rax
0x18003d7f1  sbb     r14d, r14d
0x18003d7f4  neg     r14d
0x18003d7f7  dec     r14d
0x18003d7fa  or      r13, 0FFFFFFFFFFFFFFFFh
0x18003d7fe  mov     rax, [rsp+140h+var_100]
0x18003d803  cmp     [rax], r12d
0x18003d806  jl      loc_18003DB41
0x18003d80c  cmp     r14d, r13d
0x18003d80f  jz      loc_18003DB41
0x18003d815  mov     [rsp+140h+var_E0], r12
0x18003d81a  mov     rsi, [rsp+140h+var_108]
0x18003d81f  mov     rax, [rsi]
0x18003d822  mov     rdi, [rax+30h]
0x18003d826  xor     ecx, ecx; string
0x18003d828  call    cs:__imp_WindowsDeleteString
0x18003d82e  mov     [rsp+140h+var_E0], r12
0x18003d833  lea     rdx, [rsp+140h+var_E0]
0x18003d838  mov     rcx, rsi
0x18003d83b  mov     rax, rdi
0x18003d83e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d843  mov     rcx, [rbp+48h]; this
0x18003d847  test    eax, eax
0x18003d849  js      loc_18003DC54
0x18003d84f  mov     [rsp+140h+var_E8], r12
0x18003d854  mov     rcx, [rsp+140h+var_108]
0x18003d859  mov     rax, [rcx]
0x18003d85c  mov     [rsp+140h+var_E8], r12
0x18003d861  lea     rdx, [rsp+140h+var_E8]
0x18003d866  mov     rax, [rax+38h]
0x18003d86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d86f  mov     rcx, [rbp+48h]; this
0x18003d873  test    eax, eax
0x18003d875  js      loc_18003DC3F
0x18003d87b  mov     qword ptr [rsp+140h+var_11C+4], r12
0x18003d880  mov     rsi, [rsp+140h+var_E8]
0x18003d885  mov     rax, [rsi]
0x18003d888  mov     rdi, [rax+40h]
0x18003d88c  xor     ecx, ecx; string
0x18003d88e  call    cs:__imp_WindowsDeleteString
0x18003d894  mov     qword ptr [rsp+140h+var_11C+4], r12
0x18003d899  lea     rdx, [rsp+140h+var_11C+4]
0x18003d89e  mov     rcx, rsi
0x18003d8a1  mov     rax, rdi
0x18003d8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8a9  mov     dword ptr [rsp+140h+var_11C], eax
0x18003d8ad  cmp     eax, 8000000Eh
0x18003d8b2  jnz     short loc_18003D8E4
0x18003d8b4  mov     rsi, [rsp+140h+var_E8]
0x18003d8b9  mov     rax, [rsi]
0x18003d8bc  mov     rdi, [rax+38h]
0x18003d8c0  mov     rcx, qword ptr [rsp+140h+var_11C+4]; string
0x18003d8c5  call    cs:__imp_WindowsDeleteString
0x18003d8cb  mov     qword ptr [rsp+140h+var_11C+4], r12
0x18003d8d0  lea     rdx, [rsp+140h+var_11C+4]
0x18003d8d5  mov     rcx, rsi
0x18003d8d8  mov     rax, rdi
0x18003d8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8e0  mov     dword ptr [rsp+140h+var_11C], eax
0x18003d8e4  mov     rcx, [rbp+48h]; this
0x18003d8e8  test    eax, eax
0x18003d8ea  js      loc_18003DC2A
0x18003d8f0  mov     [rsp+140h+length], r12d
0x18003d8f5  lea     rdx, [rsp+140h+length]; length
0x18003d8fa  mov     rcx, qword ptr [rsp+140h+var_11C+4]; string
0x18003d8ff  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d905  xorps   xmm0, xmm0
0x18003d908  movups  xmmword ptr [rbp+40h+Src], xmm0
0x18003d90c  mov     [rbp+40h+var_50], r12
0x18003d910  mov     [rbp+40h+var_48], r12
0x18003d914  mov     r8, r13
0x18003d917  inc     r8
0x18003d91a  cmp     [rax+r8*2], r12w
0x18003d91f  jnz     short loc_18003D917
0x18003d921  mov     rdx, rax
0x18003d924  lea     rcx, [rbp+40h+Src]
0x18003d928  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003d92d  nop
0x18003d92e  xor     edx, edx; length
0x18003d930  mov     rcx, [rsp+140h+var_E0]; string
0x18003d935  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d93b  xorps   xmm0, xmm0
0x18003d93e  movups  [rbp+40h+var_80], xmm0
0x18003d942  mov     qword ptr [rbp+40h+var_70], r12
0x18003d946  mov     qword ptr [rbp+40h+var_70+8], r12
0x18003d94a  mov     r8, r13
0x18003d94d  inc     r8
0x18003d950  cmp     [rax+r8*2], r12w
0x18003d955  jnz     short loc_18003D94D
0x18003d957  mov     rdx, rax
0x18003d95a  lea     rcx, [rbp+40h+var_80]
0x18003d95e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003d963  nop
0x18003d964  lea     r8, [rbp+40h+var_80]
0x18003d968  lea     rdx, [rbp+40h+var_C0]
0x18003d96c  mov     rcx, r15
0x18003d96f  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18003d974  mov     rdi, [rbp+40h+var_B0]
0x18003d978  cmp     [rdi+19h], r12b
0x18003d97c  jnz     short loc_18003D993
0x18003d97e  lea     rdx, [rdi+20h]
0x18003d982  lea     rcx, [rbp+40h+var_80]
0x18003d986  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x18003d98b  test    al, al
0x18003d98d  jz      loc_18003DA24
0x18003d993  mov     rax, 2AAAAAAAAAAAAAAh
0x18003d99d  cmp     [r15+8], rax
0x18003d9a1  jz      loc_18003DC24
0x18003d9a7  mov     rdi, [r15]
0x18003d9aa  mov     [rbp+40h+var_A0], r15
0x18003d9ae  mov     [rbp+40h+var_98], r12
0x18003d9b2  mov     ecx, 60h ; '`'; Size
0x18003d9b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d9bc  mov     r8, rax
0x18003d9bf  movups  xmm0, [rbp+40h+var_80]
0x18003d9c3  movups  xmmword ptr [rax+20h], xmm0
0x18003d9c7  movups  xmm1, [rbp+40h+var_70]
0x18003d9cb  movups  xmmword ptr [rax+30h], xmm1
0x18003d9cf  mov     qword ptr [rbp+40h+var_70], r12
0x18003d9d3  mov     qword ptr [rbp+40h+var_70+8], 7
0x18003d9db  mov     word ptr [rbp+40h+var_80], r12w
0x18003d9e0  xorps   xmm0, xmm0
0x18003d9e3  movups  xmmword ptr [rax+40h], xmm0
0x18003d9e7  mov     [rax+50h], r12
0x18003d9eb  mov     qword ptr [rax+58h], 7
0x18003d9f3  mov     [rax+40h], r12w
0x18003d9f8  mov     [rax], rdi
0x18003d9fb  mov     [rax+8], rdi
0x18003d9ff  mov     [rax+10h], rdi
0x18003da03  mov     [rax+18h], r12w
0x18003da08  mov     [rbp+40h+var_98], r12
0x18003da0c  movups  xmm0, [rbp+40h+var_C0]
0x18003da10  movdqu  [rbp+40h+var_C0], xmm0
0x18003da15  lea     rdx, [rbp+40h+var_C0]
0x18003da19  mov     rcx, r15
0x18003da1c  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,uint>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,uint>,void *> *>,std::_Tree_node<std::pair<std::wstring const,uint>,void *> * const)
0x18003da21  mov     rdi, rax
0x18003da24  lea     rcx, [rdi+40h]
0x18003da28  lea     rax, [rbp+40h+Src]
0x18003da2c  cmp     rcx, rax
0x18003da2f  jz      short loc_18003DA7B
0x18003da31  mov     rdx, [rbp+40h+var_50]
0x18003da35  lea     r9, [rbp+40h+Src]
0x18003da39  cmp     [rbp+40h+var_48], 7
0x18003da3e  cmova   r9, [rbp+40h+Src]
0x18003da43  cmp     rdx, [rcx+18h]
0x18003da47  ja      short loc_18003DA75
0x18003da49  cmp     qword ptr [rcx+18h], 7
0x18003da4e  jbe     short loc_18003DA55
0x18003da50  mov     rsi, [rcx]
0x18003da53  jmp     short loc_18003DA58
0x18003da55  mov     rsi, rcx
0x18003da58  mov     [rcx+10h], rdx
0x18003da5c  lea     rdi, [rdx+rdx]
0x18003da60  mov     r8, rdi; Size
0x18003da63  mov     rdx, r9; Src
0x18003da66  mov     rcx, rsi; void *
0x18003da69  call    memmove_0
0x18003da6e  mov     [rdi+rsi], r12w
0x18003da73  jmp     short loc_18003DA7B
0x18003da75  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18003da7a  nop
0x18003da7b  lea     rcx, [rbp+40h+var_80]
0x18003da7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003da84  nop
0x18003da85  lea     rcx, [rbp+40h+Src]
0x18003da89  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003da8e  nop
0x18003da8f  mov     rcx, qword ptr [rsp+140h+var_11C+4]; string
0x18003da94  call    cs:__imp_WindowsDeleteString
0x18003da9a  mov     qword ptr [rsp+140h+var_11C+4], r12
0x18003da9f  mov     rcx, [rsp+140h+var_E8]
0x18003daa4  test    rcx, rcx
0x18003daa7  jz      short loc_18003DAB6
0x18003daa9  mov     rax, [rcx]
0x18003daac  mov     rax, [rax+10h]
0x18003dab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dab5  nop
  ... truncated ...
```
