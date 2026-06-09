# OrphanFileFinder::GetTargetDirectoryFromShortcut(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004e308`
- end: `0x18004e6ac`
- name: `?GetTargetDirectoryFromShortcut@OrphanFileFinder@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `932`
- prototype: `void *__fastcall(void *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003caa8`

## callees

- `0x1800114a4`
- `0x1800150ac`
- `0x1800172bc`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x1800404c4`
- `0x18004e308`
- `0x18004e6b4`
- `0x18004e6e4`
- `0x180059920`
- `0x18005a8bc`
- `0x1800679f8`
- `0x180130010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18004e380`
- `ole32!CoCreateInstance` at `0x18004e380`
- `ole32!CoTaskMemFree` at `0x18004e65f`
- `ole32!CoTaskMemFree` at `0x18004e65f`
- `SHELL32!SHCreateItemFromIDList` at `0x18004e540`
- `SHELL32!SHCreateItemFromIDList` at `0x18004e540`

## string_xrefs

- `0x18004e42f`: `OrphanFileFinder::GetTargetDirectoryFromShortcut`
- `0x18004e394`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18004e3da`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18004e47d`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18004e4b3`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18004e50d`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18004e554`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`
- `0x18004e5d6`: `base\appcompat\inventory\software\inv2\lib\orphanfilefinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void *__fastcall OrphanFileFinder::GetTargetDirectoryFromShortcut(void *a1, _QWORD *a2)
{
  HRESULT v4; // eax
  __int64 (__fastcall **v5)(LPVOID, GUID *, __int64 *); // rax
  int v6; // eax
  _QWORD *v7; // rdx
  __int64 (__fastcall **v8)(LPVOID, GUID *, __int64 *); // rax
  int v9; // eax
  int v10; // eax
  __int64 (__fastcall **v11)(LPVOID, GUID *, __int64 *); // rax
  int v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  _QWORD *DirectoryFromPath; // rax
  ITEMIDLIST *v16; // rcx
  int v18; // [rsp+28h] [rbp-E0h]
  LPVOID ppv; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+48h] [rbp-C0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+58h] [rbp-B0h] BYREF
  int v24; // [rsp+60h] [rbp-A8h]
  int v25; // [rsp+64h] [rbp-A4h] BYREF
  void *v26[3]; // [rsp+68h] [rbp-A0h] BYREF
  LPCITEMIDLIST *p_pidl; // [rsp+80h] [rbp-88h] BYREF
  __int64 v28; // [rsp+88h] [rbp-80h] BYREF
  __int64 v29; // [rsp+90h] [rbp-78h]
  _BYTE v30[32]; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v31[5]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v32[592]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v33[528]; // [rsp+338h] [rbp+230h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+570h] [rbp+468h]

  v26[1] = (void *)-2LL;
  v26[2] = a1;
  std::wstring::wstring(a1);
  v24 = 1;
  ppv = 0;
  v4 = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &GUID_000214f9_0000_0000_c000_000000000046, &ppv);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1EC,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
      (const char *)(unsigned int)v4,
      v18);
  v21 = 0;
  v5 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
  v21 = 0;
  v6 = (*v5)(ppv, &GUID_0000010b_0000_0000_c000_000000000046, &v21);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
      (const char *)(unsigned int)v6,
      v18);
  if ( a2[3] <= 7u )
    v7 = a2;
  else
    v7 = (_QWORD *)*a2;
  if ( (*(int (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v21 + 40LL))(v21, v7, 0) >= 0 )
  {
    LODWORD(v20) = 0;
    v23 = 0;
    v8 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
    v23 = 0;
    v9 = (*v8)(ppv, &GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1, &v23);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
        (const char *)(unsigned int)v9,
        v18);
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 48LL))(v23, &v20);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
        (const char *)(unsigned int)v10,
        v18);
    if ( (v20 & 0x1000) == 0 )
    {
      pidl = 0;
      v11 = *(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
      p_pidl = &pidl;
      v28 = 0;
      LOBYTE(v29) = 1;
      v12 = ((__int64 (__fastcall *)(LPVOID, __int64 *))v11[4])(ppv, &v28);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x201,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
          (const char *)(unsigned int)v12,
          v18);
      wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
      v26[0] = 0;
      v13 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v26);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x204,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
          (const char *)(unsigned int)v13,
          v18);
      v25 = 0;
      if ( (*(int (__fastcall **)(void *, __int64, int *))(*(_QWORD *)v26[0] + 48LL))(v26[0], 0x1000000, &v25) >= 0 )
      {
        memset_0(v32, 0, sizeof(v32));
        v14 = (*(__int64 (__fastcall **)(LPVOID, _BYTE *, __int64, _BYTE *))(*(_QWORD *)ppv + 24LL))(ppv, v33, 260, v32);
        if ( v14 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x20D,
            (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\orphanfilefinder.cpp",
            (const char *)(unsigned int)v14,
            1);
        std::wstring::wstring(v30, v33);
        Utility::VerifyAndNormalizeFilePath((__int64)&p_pidl, (__int64)v30);
        std::wstring::~wstring(v30);
        if ( v29 )
        {
          DirectoryFromPath = Utility::GetDirectoryFromPath(v31, (__int64)&p_pidl);
          std::wstring::operator=(a1, DirectoryFromPath);
          std::wstring::~wstring(v31);
        }
        std::wstring::~wstring(&p_pidl);
      }
      wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(v26);
      v16 = (ITEMIDLIST *)pidl;
      pidl = 0;
      if ( v16 )
        CoTaskMemFree(v16);
    }
    wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(&v23);
  }
  else
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"OrphanFileFinder::GetTargetDirectoryFromShortcut",
      500,
      (unsigned int)"Failed to load shortcut: %ws");
  }
  wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(&v21);
  wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(&ppv);
  return a1;
}

```

## disassembly

```asm
0x18004e308  mov     rax, rsp
0x18004e30b  push    rbp
0x18004e30c  push    rsi
0x18004e30d  push    rdi
0x18004e30e  lea     rbp, [rax-468h]
0x18004e315  sub     rsp, 550h
0x18004e31c  mov     [rsp+560h+var_4F8], 0FFFFFFFFFFFFFFFEh
0x18004e325  mov     [rax+18h], rbx
0x18004e329  mov     rax, cs:__security_cookie
0x18004e330  xor     rax, rsp
0x18004e333  mov     [rbp+460h+var_20], rax
0x18004e33a  mov     rbx, rdx
0x18004e33d  mov     rdi, rcx
0x18004e340  mov     [rsp+560h+var_4F0], rcx
0x18004e345  mov     dword ptr [rsp+560h+var_508], 1
0x18004e34d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004e352  nop
0x18004e353  mov     dword ptr [rsp+560h+var_508], 1
0x18004e35b  xor     esi, esi
0x18004e35d  mov     [rsp+560h+ppv], rsi
0x18004e362  lea     rax, [rsp+560h+ppv]
0x18004e367  mov     [rsp+20h], rax; int
0x18004e36c  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046; riid
0x18004e373  xor     edx, edx; pUnkOuter
0x18004e375  lea     r8d, [rsi+1]; dwClsContext
0x18004e379  lea     rcx, CLSID_ShellLink; rclsid
0x18004e380  call    cs:__imp_CoCreateInstance
0x18004e386  mov     rcx, [rbp+468h]; this
0x18004e38d  test    eax, eax
0x18004e38f  jns     short loc_18004E3A6
0x18004e391  mov     r9d, eax; char *
0x18004e394  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18004e39b  mov     edx, 1ECh; void *
0x18004e3a0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e3a6  mov     [rsp+560h+var_520], rsi
0x18004e3ab  mov     rcx, [rsp+560h+ppv]
0x18004e3b0  mov     rax, [rcx]
0x18004e3b3  mov     [rsp+560h+var_520], rsi
0x18004e3b8  lea     r8, [rsp+560h+var_520]
0x18004e3bd  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18004e3c4  mov     rax, [rax]
0x18004e3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3cc  mov     rcx, [rbp+468h]; this
0x18004e3d3  test    eax, eax
0x18004e3d5  jns     short loc_18004E3EC
0x18004e3d7  mov     r9d, eax; char *
0x18004e3da  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18004e3e1  mov     edx, 1F0h; void *
0x18004e3e6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e3ec  mov     rcx, [rsp+560h+var_520]
0x18004e3f1  mov     rax, [rcx]
0x18004e3f4  cmp     qword ptr [rbx+18h], 7
0x18004e3f9  jbe     short loc_18004E400
0x18004e3fb  mov     rdx, [rbx]
0x18004e3fe  jmp     short loc_18004E403
0x18004e400  mov     rdx, rbx
0x18004e403  xor     r8d, r8d
0x18004e406  mov     rax, [rax+28h]
0x18004e40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e40f  test    eax, eax
0x18004e411  jns     short loc_18004E445
0x18004e413  cmp     qword ptr [rbx+18h], 7
0x18004e418  jbe     short loc_18004E41D
0x18004e41a  mov     rbx, [rbx]
0x18004e41d  mov     [rsp+20h], rbx
0x18004e422  lea     r9, aFailedToLoadSh; "Failed to load shortcut: %ws"
0x18004e429  mov     r8d, 1F4h
0x18004e42f  lea     rdx, aOrphanfilefind_4; "OrphanFileFinder::GetTargetDirectoryFro"...
0x18004e436  mov     ecx, 3
0x18004e43b  call    AslLogCallPrintf
0x18004e440  jmp     loc_18004E671
0x18004e445  mov     dword ptr [rsp+560h+var_528], esi
0x18004e449  mov     qword ptr [rsp+560h+var_510], rsi
0x18004e44e  mov     rcx, [rsp+560h+ppv]
0x18004e453  mov     rax, [rcx]
0x18004e456  mov     qword ptr [rsp+560h+var_510], rsi
0x18004e45b  lea     r8, [rsp+560h+var_510]
0x18004e460  lea     rdx, _GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1
0x18004e467  mov     rax, [rax]
0x18004e46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e46f  mov     rcx, [rbp+468h]; this
0x18004e476  test    eax, eax
0x18004e478  jns     short loc_18004E48F
0x18004e47a  mov     r9d, eax; char *
0x18004e47d  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18004e484  mov     edx, 1FBh; void *
0x18004e489  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e48f  mov     rcx, qword ptr [rsp+560h+var_510]
0x18004e494  mov     rax, [rcx]
0x18004e497  lea     rdx, [rsp+560h+var_528]
0x18004e49c  mov     rax, [rax+30h]
0x18004e4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4a5  mov     rcx, [rbp+468h]; this
0x18004e4ac  test    eax, eax
0x18004e4ae  jns     short loc_18004E4C5
0x18004e4b0  mov     r9d, eax; char *
0x18004e4b3  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18004e4ba  mov     edx, 1FCh; void *
0x18004e4bf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e4c5  test    dword ptr [rsp+560h+var_528], 1000h
0x18004e4cd  jnz     loc_18004E666
0x18004e4d3  mov     [rsp+560h+pidl], rsi
0x18004e4d8  mov     rcx, [rsp+560h+ppv]
0x18004e4dd  mov     rax, [rcx]
0x18004e4e0  lea     rdx, [rsp+560h+pidl]
0x18004e4e5  mov     [rsp+560h+var_4E8], rdx
0x18004e4ea  mov     [rbp+460h+var_4E0], rsi
0x18004e4ee  mov     byte ptr [rbp+460h+var_4D8], 1
0x18004e4f2  lea     rdx, [rbp+460h+var_4E0]
0x18004e4f6  mov     rax, [rax+20h]
0x18004e4fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e4ff  mov     rcx, [rbp+468h]; this
0x18004e506  test    eax, eax
0x18004e508  jns     short loc_18004E51F
0x18004e50a  mov     r9d, eax; char *
0x18004e50d  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18004e514  mov     edx, 201h; void *
0x18004e519  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e51f  lea     rcx, [rsp+560h+var_4E8]
0x18004e524  call    ??1?$out_param_t@V?$unique_ptr@U_ITEMIDLIST@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18004e529  nop
0x18004e52a  mov     [rsp+560h+var_500], rsi
0x18004e52f  lea     r8, [rsp+560h+var_500]; ppv
0x18004e534  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18004e53b  mov     rcx, [rsp+560h+pidl]; pidl
0x18004e540  call    cs:__imp_SHCreateItemFromIDList
0x18004e546  mov     rcx, [rbp+468h]; this
0x18004e54d  test    eax, eax
0x18004e54f  jns     short loc_18004E566
0x18004e551  mov     r9d, eax; char *
0x18004e554  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18004e55b  mov     edx, 204h; void *
0x18004e560  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e566  mov     dword ptr [rsp+560h+var_508+4], esi
0x18004e56a  mov     rcx, [rsp+560h+var_500]
0x18004e56f  mov     rax, [rcx]
0x18004e572  lea     r8, [rsp+560h+var_508+4]
0x18004e577  mov     edx, 1000000h
0x18004e57c  mov     rax, [rax+30h]
0x18004e580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e585  test    eax, eax
0x18004e587  js      loc_18004E645
0x18004e58d  xor     edx, edx; Val
0x18004e58f  mov     r8d, 250h; Size
0x18004e595  lea     rcx, [rbp+460h+var_480]; void *
0x18004e599  call    memset_0
0x18004e59e  mov     rcx, [rsp+560h+ppv]
0x18004e5a3  mov     rax, [rcx]
0x18004e5a6  mov     dword ptr [rsp+20h], 1; int
0x18004e5ae  lea     r9, [rbp+460h+var_480]
0x18004e5b2  mov     r8d, 104h
0x18004e5b8  lea     rdx, [rbp+460h+var_230]
0x18004e5bf  mov     rax, [rax+18h]
0x18004e5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e5c8  mov     rcx, [rbp+468h]; this
0x18004e5cf  test    eax, eax
0x18004e5d1  jns     short loc_18004E5E8
0x18004e5d3  mov     r9d, eax; char *
0x18004e5d6  lea     r8, aBaseAppcompatI_2; "base\\appcompat\\inventory\\software\\i"...
0x18004e5dd  mov     edx, 20Dh; void *
0x18004e5e2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004e5e8  lea     rdx, [rbp+460h+var_230]
0x18004e5ef  lea     rcx, [rbp+460h+var_4C8]
0x18004e5f3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e5f8  nop
0x18004e5f9  lea     rdx, [rbp+460h+var_4C8]
0x18004e5fd  lea     rcx, [rsp+560h+var_4E8]
0x18004e602  call    ?VerifyAndNormalizeFilePath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::VerifyAndNormalizeFilePath(std::wstring const &)
0x18004e607  nop
0x18004e608  lea     rcx, [rbp+460h+var_4C8]
0x18004e60c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e611  cmp     [rbp+460h+var_4D8], rsi
0x18004e615  jz      short loc_18004E63A
0x18004e617  lea     rdx, [rsp+560h+var_4E8]
0x18004e61c  lea     rcx, [rbp+460h+var_4A8]
0x18004e620  call    ?GetDirectoryFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetDirectoryFromPath(std::wstring const &)
0x18004e625  mov     rdx, rax
0x18004e628  mov     rcx, rdi
0x18004e62b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004e630  lea     rcx, [rbp+460h+var_4A8]
0x18004e634  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e639  nop
0x18004e63a  lea     rcx, [rsp+560h+var_4E8]
0x18004e63f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004e644  nop
0x18004e645  lea     rcx, [rsp+560h+var_500]
0x18004e64a  call    ??1?$com_ptr_t@UIShellLinkDataList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(void)
0x18004e64f  nop
0x18004e650  mov     rcx, [rsp+560h+pidl]; pv
0x18004e655  mov     [rsp+560h+pidl], rsi
0x18004e65a  test    rcx, rcx
0x18004e65d  jz      short loc_18004E666
0x18004e65f  call    cs:__imp_CoTaskMemFree
0x18004e665  nop
0x18004e666  lea     rcx, [rsp+560h+var_510]
0x18004e66b  call    ??1?$com_ptr_t@UIShellLinkDataList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(void)
0x18004e670  nop
0x18004e671  lea     rcx, [rsp+560h+var_520]
0x18004e676  call    ??1?$com_ptr_t@UIShellLinkDataList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(void)
0x18004e67b  nop
0x18004e67c  lea     rcx, [rsp+560h+ppv]
0x18004e681  call    ??1?$com_ptr_t@UIShellLinkDataList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IShellLinkDataList,wil::err_exception_policy>::~com_ptr_t<IShellLinkDataList,wil::err_exception_policy>(void)
0x18004e686  nop
0x18004e687  mov     rax, rdi
0x18004e68a  mov     rcx, [rbp+460h+var_20]
0x18004e691  xor     rcx, rsp; StackCookie
0x18004e694  call    __security_check_cookie
0x18004e699  mov     rbx, [rsp+560h+arg_10]
0x18004e6a1  add     rsp, 550h
0x18004e6a8  pop     rdi
0x18004e6a9  pop     rsi
0x18004e6aa  pop     rbp
0x18004e6ab  retn
```
