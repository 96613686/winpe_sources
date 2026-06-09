# DoWizard(_WIZDATA *,SHSTOCKICONID,int,_WIZPAGE const *,int,ulong)

- ea: `0x180051e10`
- end: `0x180051fd6`
- name: `?DoWizard@@YAHPEAU_WIZDATA@@W4SHSTOCKICONID@@HPEBU_WIZPAGE@@HK@Z`
- size: `454`
- prototype: `__int64 __fastcall(struct _WIZDATA *, enum SHSTOCKICONID, int, const struct _WIZPAGE *, int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052dd0`

## callees

- `0x180051a18`
- `0x180051afc`
- `0x180051e10`
- `0x1800521a0`
- `0x180056720`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051f3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051f3a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180051fae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180051fae`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180051f20`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180051f20`
- `ole32!CoInitialize` at `0x180051e5e`
- `ole32!CoInitialize` at `0x180051e5e`
- `USER32!LoadIconW` at `0x180051efc`
- `USER32!LoadIconW` at `0x180051efc`
- `USER32!GetParent` at `0x180051ed3`
- `USER32!GetParent` at `0x180051ed3`
- `USER32!DestroyIcon` at `0x180051f98`
- `USER32!DestroyIcon` at `0x180051fa8`
- `USER32!DestroyIcon` at `0x180051f98`
- `USER32!DestroyIcon` at `0x180051fa8`
- `USER32!SendMessageW` at `0x180051f0d`
- `USER32!SendMessageW` at `0x180051f8a`
- `USER32!SendMessageW` at `0x180051f0d`
- `USER32!SendMessageW` at `0x180051f8a`
- `USER32!IsWindowVisible` at `0x180051ee1`
- `USER32!IsWindowVisible` at `0x180051ee1`

## string_xrefs

- `0x180051f19`: `comctl32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DoWizard(struct _WIZDATA *a1, enum SHSTOCKICONID a2, __int64 a3, const struct _WIZPAGE *a4)
{
  unsigned int v5; // edi
  enum SHSTOCKICONID v6; // r9d
  int v7; // r14d
  LRESULT v8; // r15
  __int64 v9; // rsi
  __int64 v10; // rdi
  HWND v11; // rbx
  HWND i; // rcx
  HWND Parent; // rax
  HICON IconW; // rax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v17; // eax
  HICON v18; // rax
  int v20; // [rsp+20h] [rbp-E0h]
  unsigned int v21; // [rsp+30h] [rbp-D0h]
  _DWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE v23; // [rsp+48h] [rbp-B8h] BYREF
  PROPSHEETHEADERW_V2 v24; // [rsp+50h] [rbp-B0h] BYREF
  struct _PSP *v25[16]; // [rsp+B0h] [rbp-50h] BYREF

  memset_0(v25, 0, 0x78u);
  memset_0(&v24, 0, sizeof(v24));
  v5 = -1;
  if ( CoInitialize(0) >= 0 )
  {
    v7 = 0;
    v8 = 0;
    InitWizHeaders(&v24, v25, a1, v6, v20);
    v9 = 0;
    v10 = 0;
    do
    {
      AddPage(
        &v24,
        qword_18005E0B0[v10],
        HIDWORD(qword_18005E0B0[v10 + 2]),
        (__int64 (*)(HWND, unsigned int, unsigned __int64, __int64))qword_18005E0B0[v10 + 1],
        a1,
        qword_18005E0B0[v10 + 2],
        v21);
      ++v9;
      v10 += 3;
    }
    while ( v9 != 3 );
    v11 = *(HWND *)a1;
    for ( i = v11; ; i = Parent )
    {
      Parent = GetParent(i);
      if ( !Parent )
        break;
      v11 = Parent;
    }
    if ( !IsWindowVisible(v11) )
    {
      IconW = LoadIconW(g_hinst, (LPCWSTR)0x5DC);
      v8 = SendMessageW(v11, 0x80u, 1u, (LPARAM)IconW);
      v7 = 1;
    }
    LibraryW = LoadLibraryW(L"comctl32.dll");
    v23 = LibraryW;
    if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "PropertySheetInternalW")) != 0 )
    {
      v22[0] = 8;
      v22[1] = 1;
      v17 = ((__int64 (__fastcall *)(PROPSHEETHEADERW_V2 *, _DWORD *))ProcAddress)(&v24, v22);
    }
    else
    {
      v17 = PropertySheetW(&v24);
    }
    v5 = v17;
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v23);
    if ( v7 )
    {
      v18 = (HICON)SendMessageW(v11, 0x80u, 1u, v8);
      if ( v18 )
        DestroyIcon(v18);
    }
    if ( v24.hIcon )
      DestroyIcon(v24.hIcon);
    CoUninitialize();
  }
  return v5;
}

```

## disassembly

```asm
0x180051e10  push    rbp
0x180051e12  push    rbx
0x180051e13  push    rsi
0x180051e14  push    rdi
0x180051e15  push    r12
0x180051e17  push    r13
0x180051e19  push    r14
0x180051e1b  push    r15
0x180051e1d  lea     rbp, [rsp-48h]
0x180051e22  sub     rsp, 148h
0x180051e29  mov     rax, cs:__security_cookie
0x180051e30  xor     rax, rsp
0x180051e33  mov     [rbp+80h+var_50], rax
0x180051e37  mov     rbx, rcx
0x180051e3a  xor     edx, edx; Val
0x180051e3c  lea     r8d, [rdx+78h]; Size
0x180051e40  lea     rcx, [rbp+80h+var_D0]; void *
0x180051e44  call    memset_0
0x180051e49  xor     edx, edx; Val
0x180051e4b  lea     r8d, [rdx+60h]; Size
0x180051e4f  lea     rcx, [rsp+180h+var_130]; void *
0x180051e54  call    memset_0
0x180051e59  or      edi, 0FFFFFFFFh
0x180051e5c  xor     ecx, ecx; pvReserved
0x180051e5e  call    cs:__imp_CoInitialize
0x180051e64  test    eax, eax
0x180051e66  js      loc_180051FB4
0x180051e6c  xor     r14d, r14d
0x180051e6f  xor     r15d, r15d
0x180051e72  mov     r8, rbx; struct _WIZDATA *
0x180051e75  lea     rdx, [rbp+80h+var_D0]; struct _PSP **
0x180051e79  lea     rcx, [rsp+180h+var_130]; struct _PROPSHEETHEADERW_V2 *
0x180051e7e  call    ?InitWizHeaders@@YAXPEAU_PROPSHEETHEADERW_V2@@PEAPEAU_PSP@@PEAU_WIZDATA@@W4SHSTOCKICONID@@H@Z; InitWizHeaders(_PROPSHEETHEADERW_V2 *,_PSP * *,_WIZDATA *,SHSTOCKICONID,int)
0x180051e83  xor     esi, esi
0x180051e85  xor     edi, edi
0x180051e87  lea     r13, qword_18005E0B0
0x180051e8e  lea     r12d, [r14+1]
0x180051e92  mov     eax, [rdi+r13+10h]
0x180051e97  mov     dword ptr [rsp+180h+var_158], eax; __int16
0x180051e9b  mov     [rsp+180h+var_160], rbx; struct _WIZDATA *
0x180051ea0  mov     r9, [rdi+r13+8]; __int64 (*)(HWND, unsigned int, unsigned __int64, __int64)
0x180051ea5  mov     r8d, [rdi+r13+14h]; unsigned int
0x180051eaa  mov     edx, [rdi+r13]; unsigned int
0x180051eae  lea     rcx, [rsp+180h+var_130]; struct _PROPSHEETHEADERW_V2 *
0x180051eb3  call    ?AddPage@@YAXPEAU_PROPSHEETHEADERW_V2@@IIP6A_JPEAUHWND__@@I_K_J@ZPEBU_WIZDATA@@HK@Z; AddPage(_PROPSHEETHEADERW_V2 *,uint,uint,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),_WIZDATA const *,int,ulong)
0x180051eb8  add     rsi, r12
0x180051ebb  lea     rdi, [rdi+18h]
0x180051ebf  cmp     rsi, 3
0x180051ec3  jnz     short loc_180051E92
0x180051ec5  mov     rbx, [rbx]
0x180051ec8  mov     rcx, rbx
0x180051ecb  jmp     short loc_180051ED3
0x180051ecd  mov     rbx, rax
0x180051ed0  mov     rcx, rax; hWnd
0x180051ed3  call    cs:__imp_GetParent
0x180051ed9  test    rax, rax
0x180051edc  jnz     short loc_180051ECD
0x180051ede  mov     rcx, rbx; hWnd
0x180051ee1  call    cs:__imp_IsWindowVisible
0x180051ee7  mov     esi, 80h
0x180051eec  test    eax, eax
0x180051eee  jnz     short loc_180051F19
0x180051ef0  mov     edx, 5DCh; lpIconName
0x180051ef5  mov     rcx, cs:g_hinst; hInstance
0x180051efc  call    cs:__imp_LoadIconW
0x180051f02  mov     r9, rax; lParam
0x180051f05  mov     r8, r12; wParam
0x180051f08  mov     edx, esi; Msg
0x180051f0a  mov     rcx, rbx; hWnd
0x180051f0d  call    cs:__imp_SendMessageW
0x180051f13  mov     r15, rax
0x180051f16  mov     r14d, r12d
0x180051f19  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180051f20  call    cs:__imp_LoadLibraryW
0x180051f26  mov     [rsp+180h+var_138], rax
0x180051f2b  test    rax, rax
0x180051f2e  jz      short loc_180051F63
0x180051f30  lea     rdx, aPropertysheeti; "PropertySheetInternalW"
0x180051f37  mov     rcx, rax; hModule
0x180051f3a  call    cs:__imp_GetProcAddress
0x180051f40  test    rax, rax
0x180051f43  jz      short loc_180051F63
0x180051f45  mov     [rsp+180h+var_140], 8
0x180051f4d  mov     [rsp+180h+var_13C], r12d
0x180051f52  lea     rdx, [rsp+180h+var_140]
0x180051f57  lea     rcx, [rsp+180h+var_130]
0x180051f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f61  jmp     short loc_180051F6D
0x180051f63  lea     rcx, [rsp+180h+var_130]; LPCPROPSHEETHEADERW
0x180051f68  call    PropertySheetW
0x180051f6d  mov     rdi, rax
0x180051f70  lea     rcx, [rsp+180h+var_138]
0x180051f75  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180051f7a  test    r14d, r14d
0x180051f7d  jz      short loc_180051F9E
0x180051f7f  mov     r9, r15; lParam
0x180051f82  mov     r8, r12; wParam
0x180051f85  mov     edx, esi; Msg
0x180051f87  mov     rcx, rbx; hWnd
0x180051f8a  call    cs:__imp_SendMessageW
0x180051f90  test    rax, rax
0x180051f93  jz      short loc_180051F9E
0x180051f95  mov     rcx, rax; hIcon
0x180051f98  call    cs:__imp_DestroyIcon
0x180051f9e  mov     rcx, qword ptr [rsp+180h+var_130.18h]; hIcon
0x180051fa3  test    rcx, rcx
0x180051fa6  jz      short loc_180051FAE
0x180051fa8  call    cs:__imp_DestroyIcon
0x180051fae  call    cs:__imp_CoUninitialize
0x180051fb4  mov     eax, edi
0x180051fb6  mov     rcx, [rbp+80h+var_50]
0x180051fba  xor     rcx, rsp; StackCookie
0x180051fbd  call    __security_check_cookie
0x180051fc2  add     rsp, 148h
0x180051fc9  pop     r15
0x180051fcb  pop     r14
0x180051fcd  pop     r13
0x180051fcf  pop     r12
0x180051fd1  pop     rdi
0x180051fd2  pop     rsi
0x180051fd3  pop     rbx
0x180051fd4  pop     rbp
0x180051fd5  retn
```
