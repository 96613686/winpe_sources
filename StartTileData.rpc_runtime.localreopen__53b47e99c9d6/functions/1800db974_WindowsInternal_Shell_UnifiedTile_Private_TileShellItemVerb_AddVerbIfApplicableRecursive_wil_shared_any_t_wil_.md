# WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::AddVerbIfApplicableRecursive(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>> const &,IContextMenu *,HMENU__ *,int,tagMENUITEMINFOW const &,WindowsInternal::Shell::UnifiedTile::VerbEnumerationOptions,WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IVector<WindowsInternal::Shell::UnifiedTile::TileVerb *> *)

- ea: `0x1800db974`
- end: `0x1800dbf27`
- name: `?AddVerbIfApplicableRecursive@TileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@CAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAUIContextMenu@@PEAUHMENU__@@HAEBUtagMENUITEMINFOW@@W4VerbEnumerationOptions@345@PEAUIVerbEnumerationArgsPrivate@2345@PEAUHSTRING__@@6PEAU?$IVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@Z`
- size: `1459`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800db7c8`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18004ffc0`
- `0x1800db7c8`
- `0x1800db974`
- `0x1800dbf30`
- `0x1800dc1cc`
- `0x1800dc4e0`
- `0x180161204`
- `0x18019a4b8`
- `0x180201e50`
- `0x1802dac70`
- `0x1802dad54`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dba43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbacb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbc2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbcd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbd10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbde9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbe02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbe0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dba43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbacb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbc2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbcd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbd10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbde9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbe02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dbe0c`

## string_xrefs

- `0x1800dba1c`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dba6f`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbaab`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbafa`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbba0`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbbdf`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbc5d`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbcb6`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbdbc`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbe71`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1800dbede`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::AddVerbIfApplicableRecursive(
        __int64 a1,
        struct IContextMenu *a2,
        HMENU a3,
        int a4,
        struct tagMENUITEMINFOW *a5,
        unsigned int a6,
        __int64 a7,
        __int64 a8,
        HSTRING a9,
        __int64 a10)
{
  bool v11; // r14
  UINT fType; // eax
  UINT wID; // ebx
  unsigned int v14; // ebx
  int VerbCanonicalName; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rcx
  int VerbDisplayName; // eax
  HSTRING v23; // rbx
  int v24; // r14d
  __int64 v25; // rdx
  HRESULT (__stdcall *QueryInterface)(IContextMenu *, const IID *const, void **); // rbx
  int v27; // eax
  __int64 (__fastcall *v28)(__int64, __int64, _BYTE *); // rbx
  int v29; // eax
  int v30; // eax
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-B9h]
  int v33; // [rsp+20h] [rbp-B9h]
  _BYTE v34[8]; // [rsp+50h] [rbp-89h] BYREF
  HSTRING string; // [rsp+58h] [rbp-81h] BYREF
  HSTRING v36; // [rsp+60h] [rbp-79h] BYREF
  __int64 v37; // [rsp+68h] [rbp-71h] BYREF
  HSTRING v38; // [rsp+70h] [rbp-69h] BYREF
  HMENU v39; // [rsp+78h] [rbp-61h] BYREF
  HSTRING v40; // [rsp+80h] [rbp-59h] BYREF
  __int64 v41; // [rsp+88h] [rbp-51h] BYREF
  HSTRING v42; // [rsp+90h] [rbp-49h] BYREF
  HMENU v43; // [rsp+98h] [rbp-41h] BYREF
  HSTRING v44; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-31h]
  __int64 v46; // [rsp+B0h] [rbp-29h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+3Fh]

  LODWORD(v37) = a4;
  v43 = a3;
  v45 = a1;
  v42 = (HSTRING)a2;
  v39 = a3;
  v46 = a8;
  v41 = a8;
  v44 = a9;
  v40 = a9;
  v11 = 0;
  v34[0] = 0;
  fType = a5->fType;
  if ( !fType )
  {
    if ( a5->hSubMenu )
    {
      v11 = 1;
      if ( (a6 & 4) == 0 )
        return 0;
    }
    wID = a5->wID;
    if ( wID - 1 > 0x7FFE )
    {
      v14 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x149,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
        (const char *)0x8000FFFFLL,
        v32);
      return v14;
    }
    LODWORD(v36) = wID - 1;
    WindowsDeleteString(0);
    v38 = 0;
    VerbCanonicalName = WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::GetVerbCanonicalName(
                          a2,
                          wID - 1,
                          v11,
                          &v38);
    v14 = VerbCanonicalName;
    if ( VerbCanonicalName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
        (const char *)(unsigned int)VerbCanonicalName,
        v32);
LABEL_38:
      WindowsDeleteString(v38);
      return v14;
    }
    v17 = (*(__int64 (__fastcall **)(__int64, HSTRING, _BYTE *))(*(_QWORD *)a7 + 64LL))(a7, v38, v34);
    if ( v17 >= 0 )
    {
      if ( v34[0] )
      {
        if ( v11 )
        {
          if ( (a6 & 1) == 0 )
          {
            WindowsDeleteString(0);
            string = 0;
            VerbDisplayName = WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::GetVerbDisplayName(
                                a5,
                                v43,
                                &string,
                                0,
                                0);
            if ( VerbDisplayName < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x16B,
                (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
                (const char *)(unsigned int)VerbDisplayName,
                v33);
            v39 = 0;
            v23 = string;
            v43 = (HMENU)string;
            v42 = v38;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
            v24 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileVerbGroup,WindowsInternal::Shell::UnifiedTile::ITileVerb,HSTRING__ * &,HSTRING__ * &,HSTRING__ *,HSTRING__ *>(
                    (unsigned int)&v39,
                    (unsigned int)&v41,
                    (unsigned int)&v40,
                    (unsigned int)&v42,
                    (__int64)&v43);
            if ( v24 >= 0 )
            {
              v24 = (*(__int64 (__fastcall **)(__int64, HMENU))(*(_QWORD *)a10 + 104LL))(a10, v39);
              if ( v24 >= 0 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                WindowsDeleteString(v23);
                goto LABEL_12;
              }
              v25 = 372;
            }
            else
            {
              v25 = 371;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v25,
              (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
              (const char *)(unsigned int)v24,
              v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
            WindowsDeleteString(v23);
            v14 = v24;
            goto LABEL_38;
          }
LABEL_12:
          v36 = 0;
          WindowsDeleteString(0);
          v36 = 0;
          v18 = WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::ConcatGroupPath(v44, v38, &v36);
          v14 = v18;
          if ( v18 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x17D,
              (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
              (const char *)(unsigned int)v18,
              v32);
LABEL_37:
            WindowsDeleteString(v36);
            v36 = 0;
            goto LABEL_38;
          }
          string = 0;
          QueryInterface = a2->lpVtbl->QueryInterface;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          if ( ((int (__fastcall *)(struct IContextMenu *, GUID *, HSTRING *))QueryInterface)(
                 a2,
                 &GUID_bcfce0a0_ec17_11d0_8d10_00a0c90f2719,
                 &string) >= 0 )
          {
            v44 = 0;
            (*(void (__fastcall **)(HSTRING, __int64, HMENU, __int64, HSTRING *))(*(_QWORD *)string + 56LL))(
              string,
              279,
              a5->hSubMenu,
              (unsigned __int16)v37 | 0x10000LL,
              &v44);
          }
          v27 = WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::EnumerateMenuRecursive(
                  v45,
                  a2,
                  a5->hSubMenu,
                  a6);
          v14 = v27;
          if ( v27 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x195,
              (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
              (const char *)(unsigned int)v27,
              a7);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
            goto LABEL_37;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          WindowsDeleteString(v36);
          goto LABEL_40;
        }
        if ( (a5->fState & 3) == 0 || (a6 & 1) == 0 )
        {
          v37 = 0;
          string = v38;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
          v19 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb,WindowsInternal::Shell::UnifiedTile::ITileVerb,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>> const &,IContextMenu * &,unsigned int const &,tagMENUITEMINFOW const &,HMENU__ * &,enum WindowsInternal::Shell::UnifiedTile::VerbEnumerationOptions &,HSTRING__ * &,HSTRING__ * &,HSTRING__ *>(
                  &v37,
                  v45,
                  &v42,
                  &v36);
          v14 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x164,
              (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
              (const char *)(unsigned int)v19,
              (int)a5);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
            goto LABEL_38;
          }
          v20 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a10 + 104LL))(a10, v37);
          v14 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x165,
              (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
              (const char *)(unsigned int)v20,
              (int)a5);
            v21 = v37;
            if ( v37 )
            {
              v37 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            }
            goto LABEL_38;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        }
LABEL_40:
        WindowsDeleteString(v38);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x14F,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
        (const char *)(unsigned int)v17,
        v32);
    }
    if ( v11 )
      goto LABEL_12;
    goto LABEL_40;
  }
  if ( fType != 2048 || (a6 & 1) != 0 )
    return 0;
  v28 = *(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)a7 + 64LL);
  v48 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"<separator>", 0xCu, 0xBu);
  v29 = v28(a7, v48, v34);
  if ( v29 >= 0 )
  {
    if ( v34[0] )
    {
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      v30 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileVerbSeparator,WindowsInternal::Shell::UnifiedTile::ITileVerb,HSTRING__ * &,HSTRING__ * &>(
              &string,
              &v41,
              &v40);
      v14 = v30;
      if ( v30 >= 0 )
      {
        v30 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)a10 + 104LL))(a10, string);
        v14 = v30;
        if ( v30 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
          return 0;
        }
        v31 = 416;
      }
      else
      {
        v31 = 415;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
        (const char *)(unsigned int)v30,
        v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      return v14;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v29,
      v32);
  }
  return 0;
}

```

## disassembly

```asm
0x1800db974  push    rbp
0x1800db976  push    rbx
0x1800db977  push    rsi
0x1800db978  push    rdi
0x1800db979  push    r12
0x1800db97b  push    r13
0x1800db97d  push    r14
0x1800db97f  lea     rbp, [rsp-7]
0x1800db984  sub     rsp, 0E0h
0x1800db98b  mov     rax, cs:__security_cookie
0x1800db992  xor     rax, rsp
0x1800db995  mov     [rbp+37h+var_38], rax
0x1800db999  mov     dword ptr [rbp+37h+var_A8], r9d
0x1800db99d  mov     rax, r8
0x1800db9a0  mov     [rbp+37h+var_78], rax
0x1800db9a4  mov     r12, rdx
0x1800db9a7  mov     [rbp+37h+var_68], rcx
0x1800db9ab  mov     [rbp+37h+var_80], rdx
0x1800db9af  mov     [rbp+37h+var_98], rax
0x1800db9b3  mov     rdi, [rbp+37h+arg_20]
0x1800db9b7  mov     r13, [rbp+37h+arg_30]
0x1800db9bb  mov     rax, [rbp+37h+arg_38]
0x1800db9bf  mov     [rbp+37h+var_60], rax
0x1800db9c3  mov     [rbp+37h+var_88], rax
0x1800db9c7  mov     rax, [rbp+37h+arg_40]
0x1800db9ce  mov     [rbp+37h+var_70], rax
0x1800db9d2  mov     [rbp+37h+var_90], rax
0x1800db9d6  mov     rsi, [rbp+37h+arg_48]
0x1800db9dd  xor     r14d, r14d
0x1800db9e0  mov     [rsp+110h+var_C0], r14b
0x1800db9e5  mov     eax, [rdi+8]
0x1800db9e8  test    eax, eax
0x1800db9ea  jnz     loc_1800DBE17
0x1800db9f0  cmp     [rdi+18h], r14
0x1800db9f4  jz      short loc_1800DBA03
0x1800db9f6  mov     r14b, 1
0x1800db9f9  test    byte ptr [rbp+37h+arg_28], 4
0x1800db9fd  jz      loc_1800DBF07
0x1800dba03  mov     ebx, [rdi+10h]
0x1800dba06  lea     eax, [rbx-1]
0x1800dba09  cmp     eax, 7FFEh
0x1800dba0e  jbe     short loc_1800DBA34
0x1800dba10  mov     rcx, [rbp+3Fh]; this
0x1800dba14  mov     ebx, 8000FFFFh
0x1800dba19  mov     r9d, ebx; char *
0x1800dba1c  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dba23  mov     edx, 149h; void *
0x1800dba28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dba2d  mov     eax, ebx
0x1800dba2f  jmp     loc_1800DBF09
0x1800dba34  dec     ebx
0x1800dba36  mov     dword ptr [rbp+37h+var_B0], ebx
0x1800dba39  mov     [rbp+37h+var_A0], 0
0x1800dba41  xor     ecx, ecx; string
0x1800dba43  call    cs:__imp_WindowsDeleteString
0x1800dba49  mov     [rbp+37h+var_A0], 0
0x1800dba51  lea     r9, [rbp+37h+var_A0]; HSTRING *
0x1800dba55  mov     r8b, r14b; bool
0x1800dba58  mov     edx, ebx; unsigned int
0x1800dba5a  mov     rcx, r12; struct IContextMenu *
0x1800dba5d  call    ?GetVerbCanonicalName@TileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@CAJPEAUIContextMenu@@I_NPEAPEAUHSTRING__@@@Z; WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::GetVerbCanonicalName(IContextMenu *,uint,bool,HSTRING__ * *)
0x1800dba62  mov     ebx, eax
0x1800dba64  test    eax, eax
0x1800dba66  jns     short loc_1800DBA85
0x1800dba68  mov     rcx, [rbp+3Fh]; this
0x1800dba6c  mov     r9d, eax; char *
0x1800dba6f  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dba76  mov     edx, 14Dh; void *
0x1800dba7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dba80  jmp     loc_1800DBDE5
0x1800dba85  mov     rax, [r13+0]
0x1800dba89  lea     r8, [rsp+110h+var_C0]
0x1800dba8e  mov     rdx, [rbp+37h+var_A0]
0x1800dba92  mov     rcx, r13
0x1800dba95  mov     rax, [rax+40h]
0x1800dba99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dba9e  mov     rcx, [rbp+3Fh]; this
0x1800dbaa2  xor     ebx, ebx
0x1800dbaa4  test    eax, eax
0x1800dbaa6  jns     short loc_1800DBB10
0x1800dbaa8  mov     r9d, eax; char *
0x1800dbaab  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dbab2  mov     edx, 14Fh; void *
0x1800dbab7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dbabc  test    r14b, r14b
0x1800dbabf  jz      loc_1800DBE08
0x1800dbac5  mov     [rbp+37h+var_B0], rbx
0x1800dbac9  xor     ecx, ecx; string
0x1800dbacb  call    cs:__imp_WindowsDeleteString
0x1800dbad1  mov     [rbp+37h+var_B0], rbx
0x1800dbad5  lea     r8, [rbp+37h+var_B0]; HSTRING *
0x1800dbad9  mov     rdx, [rbp+37h+var_A0]; HSTRING
0x1800dbadd  mov     rcx, [rbp+37h+var_70]; HSTRING
0x1800dbae1  call    ?ConcatGroupPath@TileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@CAJPEAUHSTRING__@@0PEAPEAU6@@Z; WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::ConcatGroupPath(HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x1800dbae6  mov     ebx, eax
0x1800dbae8  xor     r14d, r14d
0x1800dbaeb  test    eax, eax
0x1800dbaed  jns     loc_1800DBD1D
0x1800dbaf3  mov     rcx, [rbp+3Fh]; this
0x1800dbaf7  mov     r9d, eax; char *
0x1800dbafa  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dbb01  mov     edx, 17Dh; void *
0x1800dbb06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbb0b  jmp     loc_1800DBDD7
0x1800dbb10  cmp     [rsp+110h+var_C0], bl
0x1800dbb14  jz      short loc_1800DBABC
0x1800dbb16  test    r14b, r14b
0x1800dbb19  jnz     loc_1800DBC22
0x1800dbb1f  test    byte ptr [rdi+0Ch], 3
0x1800dbb23  setnz   cl
0x1800dbb26  test    byte ptr [rbp+37h+arg_28], 1
0x1800dbb2a  setnz   al
0x1800dbb2d  test    al, cl
0x1800dbb2f  jnz     loc_1800DBE08
0x1800dbb35  mov     [rbp+37h+var_A8], rbx
0x1800dbb39  mov     rax, [rbp+37h+var_A0]
0x1800dbb3d  mov     [rsp+110h+string], rax
0x1800dbb42  lea     rcx, [rbp+37h+var_A8]
0x1800dbb46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbb4b  lea     rax, [rsp+110h+string]
0x1800dbb50  mov     [rsp+110h+var_C8], rax
0x1800dbb55  lea     rax, [rbp+37h+var_90]
0x1800dbb59  mov     [rsp+110h+var_D0], rax
0x1800dbb5e  lea     rax, [rbp+37h+var_88]
0x1800dbb62  mov     [rsp+110h+var_D8], rax
0x1800dbb67  lea     rax, [rbp+37h+arg_28]
0x1800dbb6b  mov     [rsp+110h+var_E0], rax
0x1800dbb70  lea     rax, [rbp+37h+var_98]
0x1800dbb74  mov     [rsp+110h+var_E8], rax
0x1800dbb79  mov     [rsp+110h+var_F0], rdi; int
0x1800dbb7e  lea     r9, [rbp+37h+var_B0]
0x1800dbb82  lea     r8, [rbp+37h+var_80]
0x1800dbb86  mov     rdx, [rbp+37h+var_68]
0x1800dbb8a  lea     rcx, [rbp+37h+var_A8]
0x1800dbb8e  call    ??$MakeAndInitialize@VTileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@UITileVerb@345@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEAPEAUIContextMenu@@AEBIAEBUtagMENUITEMINFOW@@AEAPEAUHMENU__@@AEAW4VerbEnumerationOptions@345@AEAPEAUHSTRING__@@AEAPEAUHSTRING__@@PEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAUITileVerb@UnifiedTile@Shell@WindowsInternal@@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEAPEAUIContextMenu@@AEBIAEBUtagMENUITEMINFOW@@AEAPEAUHMENU__@@AEAW4VerbEnumerationOptions@456@AEAPEAUHSTRING__@@7$$QEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb,WindowsInternal::Shell::UnifiedTile::ITileVerb,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>> const &,IContextMenu * &,uint const &,tagMENUITEMINFOW const &,HMENU__ * &,WindowsInternal::Shell::UnifiedTile::VerbEnumerationOptions &,HSTRING__ * &,HSTRING__ * &,HSTRING__ *>(WindowsInternal::Shell::UnifiedTile::ITileVerb * *,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>> const &,IContextMenu * &,uint const &,tagMENUITEMINFOW const &,HMENU__ * &,WindowsInternal::Shell::UnifiedTile::VerbEnumerationOptions &,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &&)
0x1800dbb93  mov     ebx, eax
0x1800dbb95  test    eax, eax
0x1800dbb97  jns     short loc_1800DBBBF
0x1800dbb99  mov     rcx, [rbp+3Fh]; this
0x1800dbb9d  mov     r9d, eax; char *
0x1800dbba0  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dbba7  mov     edx, 164h; void *
0x1800dbbac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbbb1  lea     rcx, [rbp+37h+var_A8]
0x1800dbbb5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbbba  jmp     loc_1800DBDE5
0x1800dbbbf  mov     rax, [rsi]
0x1800dbbc2  mov     rdx, [rbp+37h+var_A8]
0x1800dbbc6  mov     rcx, rsi
0x1800dbbc9  mov     rax, [rax+68h]
0x1800dbbcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbbd2  mov     ebx, eax
0x1800dbbd4  test    eax, eax
0x1800dbbd6  jns     short loc_1800DBC14
0x1800dbbd8  mov     rcx, [rbp+3Fh]; this
0x1800dbbdc  mov     r9d, eax; char *
0x1800dbbdf  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dbbe6  mov     edx, 165h; void *
0x1800dbbeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbbf0  nop
0x1800dbbf1  mov     rcx, [rbp+37h+var_A8]
0x1800dbbf5  test    rcx, rcx
0x1800dbbf8  jz      short loc_1800DBC0F
0x1800dbbfa  mov     [rbp+37h+var_A8], 0
0x1800dbc02  mov     rax, [rcx]
0x1800dbc05  mov     rax, [rax+10h]
0x1800dbc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbc0e  nop
0x1800dbc0f  jmp     loc_1800DBDE5
0x1800dbc14  lea     rcx, [rbp+37h+var_A8]
0x1800dbc18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbc1d  jmp     loc_1800DBE08
0x1800dbc22  test    byte ptr [rbp+37h+arg_28], 1
0x1800dbc26  jnz     loc_1800DBAC5
0x1800dbc2c  xor     ecx, ecx; string
0x1800dbc2e  call    cs:__imp_WindowsDeleteString
0x1800dbc34  mov     [rsp+110h+string], rbx
0x1800dbc39  mov     [rsp+110h+var_F0], rbx; int
0x1800dbc3e  xor     r9d, r9d; HSTRING *
0x1800dbc41  lea     r8, [rsp+110h+string]; HSTRING *
0x1800dbc46  mov     rdx, [rbp+37h+var_78]; HMENU
0x1800dbc4a  mov     rcx, rdi; struct tagMENUITEMINFOW *
0x1800dbc4d  call    ?GetVerbDisplayName@TileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@CAJAEBUtagMENUITEMINFOW@@PEAUHMENU__@@PEAPEAUHSTRING__@@22@Z; WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::GetVerbDisplayName(tagMENUITEMINFOW const &,HMENU__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *)
0x1800dbc52  test    eax, eax
0x1800dbc54  jns     short loc_1800DBC6E
0x1800dbc56  mov     rcx, [rbp+3Fh]; this
0x1800dbc5a  mov     r9d, eax; char *
0x1800dbc5d  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dbc64  mov     edx, 16Bh; void *
0x1800dbc69  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dbc6e  mov     [rbp+37h+var_98], rbx
0x1800dbc72  mov     rbx, [rsp+110h+string]
0x1800dbc77  mov     [rbp+37h+var_78], rbx
0x1800dbc7b  mov     rax, [rbp+37h+var_A0]
0x1800dbc7f  mov     [rbp+37h+var_80], rax
0x1800dbc83  lea     rcx, [rbp+37h+var_98]
0x1800dbc87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbc8c  lea     rax, [rbp+37h+var_78]
0x1800dbc90  mov     [rsp+110h+var_F0], rax; int
0x1800dbc95  lea     r9, [rbp+37h+var_80]
0x1800dbc99  lea     r8, [rbp+37h+var_90]
0x1800dbc9d  lea     rdx, [rbp+37h+var_88]
0x1800dbca1  lea     rcx, [rbp+37h+var_98]
0x1800dbca5  call    ??$MakeAndInitialize@VTileVerbGroup@Private@UnifiedTile@Shell@WindowsInternal@@UITileVerb@345@AEAPEAUHSTRING__@@AEAPEAU7@PEAU7@PEAU7@@Details@WRL@Microsoft@@YAJPEAPEAUITileVerb@UnifiedTile@Shell@WindowsInternal@@AEAPEAUHSTRING__@@1$$QEAPEAU7@2@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Private::TileVerbGroup,WindowsInternal::Shell::UnifiedTile::ITileVerb,HSTRING__ * &,HSTRING__ * &,HSTRING__ *,HSTRING__ *>(WindowsInternal::Shell::UnifiedTile::ITileVerb * *,HSTRING__ * &,HSTRING__ * &,HSTRING__ * &&,HSTRING__ * &&)
0x1800dbcaa  mov     r14d, eax
0x1800dbcad  test    eax, eax
0x1800dbcaf  jns     short loc_1800DBCE3
0x1800dbcb1  mov     edx, 173h; void *
0x1800dbcb6  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dbcbd  mov     r9d, r14d; char *
0x1800dbcc0  mov     rcx, [rbp+3Fh]; this
0x1800dbcc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbcc9  lea     rcx, [rbp+37h+var_98]
0x1800dbccd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbcd2  mov     rcx, rbx; string
0x1800dbcd5  call    cs:__imp_WindowsDeleteString
0x1800dbcdb  mov     ebx, r14d
0x1800dbcde  jmp     loc_1800DBDE5
0x1800dbce3  mov     rax, [rsi]
0x1800dbce6  mov     rdx, [rbp+37h+var_98]
0x1800dbcea  mov     rcx, rsi
0x1800dbced  mov     rax, [rax+68h]
0x1800dbcf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbcf6  mov     r14d, eax
0x1800dbcf9  test    eax, eax
0x1800dbcfb  jns     short loc_1800DBD04
0x1800dbcfd  mov     edx, 174h
0x1800dbd02  jmp     short loc_1800DBCB6
0x1800dbd04  lea     rcx, [rbp+37h+var_98]
0x1800dbd08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbd0d  mov     rcx, rbx; string
0x1800dbd10  call    cs:__imp_WindowsDeleteString
0x1800dbd16  xor     ebx, ebx
0x1800dbd18  jmp     loc_1800DBAC5
0x1800dbd1d  mov     [rsp+110h+string], r14
0x1800dbd22  mov     rax, [r12]
0x1800dbd26  mov     rbx, [rax]
0x1800dbd29  lea     rcx, [rsp+110h+string]
0x1800dbd2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbd33  lea     r8, [rsp+110h+string]
0x1800dbd38  lea     rdx, _GUID_bcfce0a0_ec17_11d0_8d10_00a0c90f2719
0x1800dbd3f  mov     rcx, r12
0x1800dbd42  mov     rax, rbx
0x1800dbd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbd4a  test    eax, eax
0x1800dbd4c  js      short loc_1800DBD7F
0x1800dbd4e  mov     [rbp+37h+var_70], r14
0x1800dbd52  mov     rcx, [rsp+110h+string]
0x1800dbd57  mov     rax, [rcx]
0x1800dbd5a  movzx   r9d, word ptr [rbp+37h+var_A8]
0x1800dbd5f  bts     r9, 10h
0x1800dbd64  lea     rdx, [rbp+37h+var_70]
0x1800dbd68  mov     [rsp+110h+var_F0], rdx
0x1800dbd6d  mov     r8, [rdi+18h]
0x1800dbd71  mov     edx, 117h
0x1800dbd76  mov     rax, [rax+38h]
0x1800dbd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbd7f  mov     rax, [rbp+37h+var_B0]
0x1800dbd83  mov     [rsp+110h+var_D8], rsi
0x1800dbd88  mov     [rsp+110h+var_E0], rax
0x1800dbd8d  mov     rax, [rbp+37h+var_60]
0x1800dbd91  mov     [rsp+110h+var_E8], rax
0x1800dbd96  mov     [rsp+110h+var_F0], r13; int
0x1800dbd9b  mov     r9d, [rbp+37h+arg_28]
0x1800dbd9f  mov     r8, [rdi+18h]
0x1800dbda3  mov     rdx, r12
0x1800dbda6  mov     rcx, [rbp+37h+var_68]
0x1800dbdaa  call    ?EnumerateMenuRecursive@TileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@CAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAUIContextMenu@@PEAUHMENU__@@W4VerbEnumerationOptions@345@PEAUIVerbEnumerationArgsPrivate@2345@PEAUHSTRING__@@5PEAU?$IVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@Z; WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::EnumerateMenuRecursive(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>> const &,IContextMenu *,HMENU__ *,WindowsInternal::Shell::UnifiedTile::VerbEnumerationOptions,WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IVector<WindowsInternal::Shell::UnifiedTile::TileVerb *> *)
0x1800dbdaf  mov     ebx, eax
0x1800dbdb1  test    eax, eax
0x1800dbdb3  jns     short loc_1800DBDF4
0x1800dbdb5  mov     rcx, [rbp+3Fh]; this
0x1800dbdb9  mov     r9d, eax; char *
0x1800dbdbc  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1800dbdc3  mov     edx, 195h; void *
0x1800dbdc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dbdcd  lea     rcx, [rsp+110h+string]
0x1800dbdd2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbdd7  mov     rcx, [rbp+37h+var_B0]; string
0x1800dbddb  call    cs:__imp_WindowsDeleteString
0x1800dbde1  mov     [rbp+37h+var_B0], r14
0x1800dbde5  mov     rcx, [rbp+37h+var_A0]; string
0x1800dbde9  call    cs:__imp_WindowsDeleteString
0x1800dbdef  jmp     loc_1800DBA2D
0x1800dbdf4  lea     rcx, [rsp+110h+string]
0x1800dbdf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800dbdfe  mov     rcx, [rbp+37h+var_B0]; string
0x1800dbe02  call    cs:__imp_WindowsDeleteString
0x1800dbe08  mov     rcx, [rbp+37h+var_A0]; string
0x1800dbe0c  call    cs:__imp_WindowsDeleteString
0x1800dbe12  jmp     loc_1800DBF07
0x1800dbe17  cmp     eax, 800h
0x1800dbe1c  jnz     loc_1800DBF07
0x1800dbe22  test    byte ptr [rbp+37h+arg_28], 1
0x1800dbe26  jnz     loc_1800DBF07
0x1800dbe2c  mov     rax, [r13+0]
0x1800dbe30  mov     rbx, [rax+40h]
0x1800dbe34  mov     [rbp+37h+var_40], r14
0x1800dbe38  mov     r9d, 0Bh; unsigned int
0x1800dbe3e  lea     r8d, [r9+1]; unsigned int
  ... truncated ...
```
