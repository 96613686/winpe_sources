# PluginEngine::ShellExecuteProvTool(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *,ulong)

- ea: `0x180027380`
- end: `0x180027886`
- name: `?ShellExecuteProvTool@PluginEngine@@MEAAJPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `1286`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting`

## callees

- `0x1800087cc`
- `0x1800087ec`
- `0x18000f4cc`
- `0x18000f4fc`
- `0x18000f534`
- `0x1800108d0`
- `0x18001fbfc`
- `0x18001ff18`
- `0x18001ffe0`
- `0x180021c1c`
- `0x180021d6c`
- `0x180022bc8`
- `0x180027380`
- `0x180027bc4`
- `0x180027f24`
- `0x180028832`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800276e8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800276e8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800273c9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180027419`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800273c9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180027419`
- `ext-ms-win-shell-shell32-l1-2-0!ShellExecuteExW` at `0x180027601`
- `ext-ms-win-shell-shell32-l1-2-0!ShellExecuteExW` at `0x180027601`

## string_xrefs

- `0x180027439`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180027619`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180027681`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x18002770b`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x180027769`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`
- `0x1800277d2`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall PluginEngine::ShellExecuteProvTool(unsigned int *a1, __int64 a2, DWORD a3)
{
  const WCHAR *v5; // rbx
  const WCHAR *v6; // rcx
  __int64 v7; // rdi
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  const WCHAR *v21; // rax
  const WCHAR *v22; // rax
  const char *v23; // r9
  unsigned int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // rdx
  unsigned int v27; // ebx
  __int64 v28; // rdx
  __int64 v29; // rdx
  DWORD v30; // eax
  const char *v31; // r9
  __int64 v32; // rdx
  __int64 v33; // rdx
  unsigned int LastError; // ebx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  HANDLE hHandle; // [rsp+20h] [rbp-168h] BYREF
  LPWSTR lpDst[2]; // [rsp+28h] [rbp-160h] BYREF
  __int64 v43; // [rsp+38h] [rbp-150h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+40h] [rbp-148h] BYREF
  _QWORD v45[4]; // [rsp+B0h] [rbp-D8h] BYREF
  _QWORD v46[4]; // [rsp+D0h] [rbp-B8h] BYREF
  _BYTE v47[32]; // [rsp+F0h] [rbp-98h] BYREF
  _BYTE v48[32]; // [rsp+110h] [rbp-78h] BYREF
  _BYTE v49[32]; // [rsp+130h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v5 = (const WCHAR *)&lpSrc;
  v6 = (const WCHAR *)&lpSrc;
  if ( (unsigned __int64)qword_18003EFD8 >= 8 )
    v6 = lpSrc;
  v7 = ExpandEnvironmentStringsW(v6, 0, 0);
  LOWORD(hHandle) = 0;
  *(_OWORD *)lpDst = 0;
  v43 = 0;
  std::vector<unsigned short>::_Construct_n(lpDst, v7, &hHandle);
  if ( (unsigned __int64)qword_18003EFD8 >= 8 )
    v5 = lpSrc;
  if ( ExpandEnvironmentStringsW(v5, lpDst[0], v7) == (_DWORD)v7 )
  {
    std::wstring::wstring(v46, lpDst[0]);
    std::wstring::wstring(v45);
    v9 = std::wstring::wstring(v47, L" /source");
    v11 = std::char_traits<unsigned short>::length(L" ", v10, v9);
    v14 = std::wstring::insert(v13, v12, v13, v11, (_DWORD)hHandle);
    std::wstring::wstring(v49, v14);
    v15 = std::wstring::append(v49, L" ");
    std::wstring::wstring(v48, v15);
    std::wstring::append(v45, v48, 0, -1);
    LOBYTE(v16) = 1;
    std::wstring::_Tidy(v48, v16, 0);
    LOBYTE(v17) = 1;
    std::wstring::_Tidy(v49, v17, 0);
    LOBYTE(v18) = 1;
    std::wstring::_Tidy(v47, v18, 0);
    v19 = (*(__int64 (__fastcall **)(unsigned int *, _BYTE *, _QWORD))(*(_QWORD *)a1 + 112LL))(a1, v47, a1[14]);
    std::wstring::append(v45, v19, 0, -1);
    LOBYTE(v20) = 1;
    std::wstring::_Tidy(v47, v20, 0);
    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
    hHandle = 0;
    pExecInfo.cbSize = 112;
    pExecInfo.fMask = 64;
    pExecInfo.lpVerb = L"open";
    v21 = (const WCHAR *)v46;
    if ( v46[3] >= 8u )
      v21 = (const WCHAR *)v46[0];
    pExecInfo.lpFile = v21;
    v22 = (const WCHAR *)v45;
    if ( v45[3] >= 8u )
      v22 = (const WCHAR *)v45[0];
    pExecInfo.lpParameters = v22;
    pExecInfo.nShow = 0;
    if ( ShellExecuteExW(&pExecInfo) )
    {
      if ( pExecInfo.hProcess )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hHandle,
          pExecInfo.hProcess);
        v30 = WaitForSingleObject(hHandle, a3);
        if ( v30 == 258 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEC,
            (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
            (const char *)0x800705B4LL,
            (int)hHandle);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
          LOBYTE(v32) = 1;
          std::wstring::_Tidy(v45, v32, 0);
          LOBYTE(v33) = 1;
          std::wstring::_Tidy(v46, v33, 0);
          std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(lpDst);
          return 2147943860LL;
        }
        else if ( v30 == -1 )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xED,
                        (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                        v31);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
          LOBYTE(v35) = 1;
          std::wstring::_Tidy(v45, v35, 0);
          LOBYTE(v36) = 1;
          std::wstring::_Tidy(v46, v36, 0);
          std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(lpDst);
          return LastError;
        }
        else if ( v30 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xEE,
            (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
            (const char *)0x8000FFFFLL,
            (int)hHandle);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
          LOBYTE(v37) = 1;
          std::wstring::_Tidy(v45, v37, 0);
          LOBYTE(v38) = 1;
          std::wstring::_Tidy(v46, v38, 0);
          std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(lpDst);
          return 2147549183LL;
        }
        else
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
          LOBYTE(v39) = 1;
          std::wstring::_Tidy(v45, v39, 0);
          LOBYTE(v40) = 1;
          std::wstring::_Tidy(v46, v40, 0);
          std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(lpDst);
          return 0;
        }
      }
      else
      {
        v27 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0xE8,
                (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
                v23);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
        LOBYTE(v28) = 1;
        std::wstring::_Tidy(v45, v28, 0);
        LOBYTE(v29) = 1;
        std::wstring::_Tidy(v46, v29, 0);
        std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(lpDst);
        return v27;
      }
    }
    else
    {
      v24 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xE7,
              (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
              v23);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
      LOBYTE(v25) = 1;
      std::wstring::_Tidy(v45, v25, 0);
      LOBYTE(v26) = 1;
      std::wstring::_Tidy(v46, v26, 0);
      std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(lpDst);
      return v24;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
      (const char *)0x8000FFFFLL,
      (int)hHandle);
    std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(lpDst);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180027380  push    rbx
0x180027382  push    rsi
0x180027383  push    rdi
0x180027384  push    r14
0x180027386  push    r15
0x180027388  sub     rsp, 160h
0x18002738f  mov     rax, cs:__security_cookie
0x180027396  xor     rax, rsp
0x180027399  mov     [rsp+188h+var_38], rax
0x1800273a1  mov     r15d, r8d
0x1800273a4  mov     rsi, rdx
0x1800273a7  mov     r14, rcx
0x1800273aa  lea     rbx, lpSrc
0x1800273b1  mov     rcx, rbx
0x1800273b4  cmp     cs:qword_18003EFD8, 8
0x1800273bc  cmovnb  rcx, cs:lpSrc; lpSrc
0x1800273c4  xor     r8d, r8d; nSize
0x1800273c7  xor     edx, edx; lpDst
0x1800273c9  call    cs:__imp_ExpandEnvironmentStringsW
0x1800273d0  nop     dword ptr [rax+rax+00h]
0x1800273d5  mov     edi, eax
0x1800273d7  xor     ecx, ecx
0x1800273d9  mov     word ptr [rsp+188h+hHandle], cx; int
0x1800273de  xorps   xmm0, xmm0
0x1800273e1  movdqu  xmmword ptr [rsp+188h+lpDst], xmm0
0x1800273e7  mov     [rsp+188h+var_150], rcx
0x1800273ec  mov     edx, eax
0x1800273ee  lea     r8, [rsp+188h+hHandle]
0x1800273f3  lea     rcx, [rsp+188h+lpDst]
0x1800273f8  call    ?_Construct_n@?$vector@GV?$allocator@G@std@@@std@@QEAAX_KPEBG@Z; std::vector<ushort>::_Construct_n(unsigned __int64,ushort const *)
0x1800273fd  nop
0x1800273fe  cmp     cs:qword_18003EFD8, 8
0x180027406  cmovnb  rbx, cs:lpSrc
0x18002740e  mov     r8d, edi; nSize
0x180027411  mov     rdx, [rsp+188h+lpDst]; lpDst
0x180027416  mov     rcx, rbx; lpSrc
0x180027419  call    cs:__imp_ExpandEnvironmentStringsW
0x180027420  nop     dword ptr [rax+rax+00h]
0x180027425  cmp     eax, edi
0x180027427  jz      short loc_18002745C
0x180027429  mov     rcx, [rsp+188h]; this
0x180027431  mov     ebx, 8000FFFFh
0x180027436  mov     r9d, ebx; char *
0x180027439  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027440  mov     edx, 0D6h; void *
0x180027445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002744a  nop
0x18002744b  lea     rcx, [rsp+188h+lpDst]
0x180027450  call    ??1?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(void)
0x180027455  mov     eax, ebx
0x180027457  jmp     loc_180027866
0x18002745c  mov     rdx, [rsp+188h+lpDst]
0x180027461  lea     rcx, [rsp+188h+var_B8]
0x180027469  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002746e  nop
0x18002746f  mov     rdx, rsi
0x180027472  lea     rcx, [rsp+188h+var_D8]
0x18002747a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002747f  nop
0x180027480  lea     rdx, ?c_provSourceCmdLine@@3QBGB; " /source"
0x180027487  lea     rcx, [rsp+188h+var_98]
0x18002748f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180027494  mov     r8, rax
0x180027497  lea     rcx, asc_180034B44; " "
0x18002749e  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800274a3  mov     r9, rax
0x1800274a6  mov     rcx, r8
0x1800274a9  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KPEBG0@Z; std::wstring::insert(unsigned __int64,ushort const *,unsigned __int64)
0x1800274ae  mov     rdx, rax
0x1800274b1  lea     rcx, [rsp+188h+var_58]
0x1800274b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800274be  nop
0x1800274bf  lea     rdx, asc_180034B44; " "
0x1800274c6  lea     rcx, [rsp+188h+var_58]
0x1800274ce  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800274d3  mov     rdx, rax
0x1800274d6  lea     rcx, [rsp+188h+var_78]
0x1800274de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800274e3  nop
0x1800274e4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800274e8  mov     r9, rbx
0x1800274eb  xor     r8d, r8d
0x1800274ee  lea     rdx, [rsp+188h+var_78]
0x1800274f6  lea     rcx, [rsp+188h+var_D8]
0x1800274fe  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180027503  nop
0x180027504  xor     r8d, r8d
0x180027507  mov     dl, 1
0x180027509  lea     rcx, [rsp+188h+var_78]
0x180027511  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027516  nop
0x180027517  xor     r8d, r8d
0x18002751a  mov     dl, 1
0x18002751c  lea     rcx, [rsp+188h+var_58]
0x180027524  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027529  nop
0x18002752a  xor     r8d, r8d
0x18002752d  mov     dl, 1
0x18002752f  lea     rcx, [rsp+188h+var_98]
0x180027537  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002753c  mov     rax, [r14]
0x18002753f  mov     r8d, [r14+38h]
0x180027543  lea     rdx, [rsp+188h+var_98]
0x18002754b  mov     rcx, r14
0x18002754e  mov     rax, [rax+70h]
0x180027552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027557  nop
0x180027558  mov     r9, rbx
0x18002755b  xor     r8d, r8d
0x18002755e  mov     rdx, rax
0x180027561  lea     rcx, [rsp+188h+var_D8]
0x180027569  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002756e  nop
0x18002756f  xor     r8d, r8d
0x180027572  mov     dl, 1
0x180027574  lea     rcx, [rsp+188h+var_98]
0x18002757c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027581  mov     ebx, 70h ; 'p'
0x180027586  mov     r8d, ebx; Size
0x180027589  xor     edx, edx; Val
0x18002758b  lea     rcx, [rsp+188h+pExecInfo]; void *
0x180027590  call    memset_0
0x180027595  mov     [rsp+188h+hHandle], 0; int
0x18002759e  mov     [rsp+188h+pExecInfo.cbSize], ebx
0x1800275a2  mov     [rsp+188h+pExecInfo.fMask], 40h ; '@'
0x1800275aa  lea     rax, aOpen; "open"
0x1800275b1  mov     [rsp+188h+pExecInfo.lpVerb], rax
0x1800275b6  lea     rax, [rsp+188h+var_B8]
0x1800275be  cmp     [rsp+188h+var_A0], 8
0x1800275c7  cmovnb  rax, [rsp+188h+var_B8]
0x1800275d0  mov     [rsp+188h+pExecInfo.lpFile], rax
0x1800275d5  lea     rax, [rsp+188h+var_D8]
0x1800275dd  cmp     [rsp+188h+var_C0], 8
0x1800275e6  cmovnb  rax, [rsp+188h+var_D8]
0x1800275ef  mov     [rsp+188h+pExecInfo.lpParameters], rax
0x1800275f4  mov     [rsp+188h+pExecInfo.nShow], 0
0x1800275fc  lea     rcx, [rsp+188h+pExecInfo]; pExecInfo
0x180027601  call    cs:__imp_ShellExecuteExW
0x180027608  nop     dword ptr [rax+rax+00h]
0x18002760d  test    eax, eax
0x18002760f  jnz     short loc_18002766C
0x180027611  mov     rcx, [rsp+188h]; this
0x180027619  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027620  lea     edx, [rbx+77h]; void *
0x180027623  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027628  mov     ebx, eax
0x18002762a  lea     rcx, [rsp+188h+hHandle]
0x18002762f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180027634  nop
0x180027635  xor     r8d, r8d
0x180027638  mov     dl, 1
0x18002763a  lea     rcx, [rsp+188h+var_D8]
0x180027642  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027647  nop
0x180027648  xor     r8d, r8d
0x18002764b  mov     dl, 1
0x18002764d  lea     rcx, [rsp+188h+var_B8]
0x180027655  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002765a  nop
0x18002765b  lea     rcx, [rsp+188h+lpDst]
0x180027660  call    ??1?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(void)
0x180027665  mov     eax, ebx
0x180027667  jmp     loc_180027866
0x18002766c  mov     rdx, [rsp+188h+pExecInfo.hProcess]
0x180027674  test    rdx, rdx
0x180027677  jnz     short loc_1800276D6
0x180027679  mov     rcx, [rsp+188h]; this
0x180027681  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027688  mov     edx, 0E8h; void *
0x18002768d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027692  mov     ebx, eax
0x180027694  lea     rcx, [rsp+188h+hHandle]
0x180027699  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002769e  nop
0x18002769f  xor     r8d, r8d
0x1800276a2  mov     dl, 1
0x1800276a4  lea     rcx, [rsp+188h+var_D8]
0x1800276ac  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800276b1  nop
0x1800276b2  xor     r8d, r8d
0x1800276b5  mov     dl, 1
0x1800276b7  lea     rcx, [rsp+188h+var_B8]
0x1800276bf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800276c4  nop
0x1800276c5  lea     rcx, [rsp+188h+lpDst]
0x1800276ca  call    ??1?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(void)
0x1800276cf  mov     eax, ebx
0x1800276d1  jmp     loc_180027866
0x1800276d6  lea     rcx, [rsp+188h+hHandle]
0x1800276db  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800276e0  mov     edx, r15d; dwMilliseconds
0x1800276e3  mov     rcx, [rsp+188h+hHandle]; hHandle
0x1800276e8  call    cs:__imp_WaitForSingleObject
0x1800276ef  nop     dword ptr [rax+rax+00h]
0x1800276f4  cmp     eax, 102h
0x1800276f9  jnz     short loc_18002775C
0x1800276fb  mov     rcx, [rsp+188h]; this
0x180027703  mov     ebx, 800705B4h
0x180027708  mov     r9d, ebx; char *
0x18002770b  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027712  lea     edx, [rax-16h]; void *
0x180027715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002771a  lea     rcx, [rsp+188h+hHandle]
0x18002771f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180027724  nop
0x180027725  xor     r8d, r8d
0x180027728  mov     dl, 1
0x18002772a  lea     rcx, [rsp+188h+var_D8]
0x180027732  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027737  nop
0x180027738  xor     r8d, r8d
0x18002773b  mov     dl, 1
0x18002773d  lea     rcx, [rsp+188h+var_B8]
0x180027745  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002774a  nop
0x18002774b  lea     rcx, [rsp+188h+lpDst]
0x180027750  call    ??1?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(void)
0x180027755  mov     eax, ebx
0x180027757  jmp     loc_180027866
0x18002775c  cmp     eax, 0FFFFFFFFh
0x18002775f  jnz     short loc_1800277BE
0x180027761  mov     rcx, [rsp+188h]; this
0x180027769  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027770  mov     edx, 0EDh; void *
0x180027775  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002777a  mov     ebx, eax
0x18002777c  lea     rcx, [rsp+188h+hHandle]
0x180027781  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180027786  nop
0x180027787  xor     r8d, r8d
0x18002778a  mov     dl, 1
0x18002778c  lea     rcx, [rsp+188h+var_D8]
0x180027794  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027799  nop
0x18002779a  xor     r8d, r8d
0x18002779d  mov     dl, 1
0x18002779f  lea     rcx, [rsp+188h+var_B8]
0x1800277a7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800277ac  nop
0x1800277ad  lea     rcx, [rsp+188h+lpDst]
0x1800277b2  call    ??1?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(void)
0x1800277b7  mov     eax, ebx
0x1800277b9  jmp     loc_180027866
0x1800277be  test    eax, eax
0x1800277c0  jz      short loc_180027822
0x1800277c2  mov     rcx, [rsp+188h]; this
0x1800277ca  mov     ebx, 8000FFFFh
0x1800277cf  mov     r9d, ebx; char *
0x1800277d2  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x1800277d9  mov     edx, 0EEh; void *
0x1800277de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277e3  lea     rcx, [rsp+188h+hHandle]
0x1800277e8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800277ed  nop
0x1800277ee  xor     r8d, r8d
0x1800277f1  mov     dl, 1
0x1800277f3  lea     rcx, [rsp+188h+var_D8]
0x1800277fb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027800  nop
0x180027801  xor     r8d, r8d
0x180027804  mov     dl, 1
0x180027806  lea     rcx, [rsp+188h+var_B8]
0x18002780e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027813  nop
0x180027814  lea     rcx, [rsp+188h+lpDst]
0x180027819  call    ??1?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(void)
0x18002781e  mov     eax, ebx
0x180027820  jmp     short loc_180027866
0x180027822  lea     rcx, [rsp+188h+hHandle]
0x180027827  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002782c  nop
0x18002782d  xor     r8d, r8d
0x180027830  mov     dl, 1
0x180027832  lea     rcx, [rsp+188h+var_D8]
0x18002783a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002783f  nop
0x180027840  xor     r8d, r8d
0x180027843  mov     dl, 1
0x180027845  lea     rcx, [rsp+188h+var_B8]
0x18002784d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180027852  nop
0x180027853  lea     rcx, [rsp+188h+lpDst]
0x180027858  call    ??1?$vector@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@AEAUProvisioniongNotificationItem@@@DataModel@SystemSettings@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>::~vector<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<SystemSettings::DataModel::CSingletonHelper<ProvisioniongNotificationItem &>::CCallback *>>,std::_Iterator_base0>>>>(void)
0x18002785d  nop
0x18002785e  xor     eax, eax
0x180027860  jmp     short loc_180027866
0x180027862  mov     eax, dword ptr [rsp+188h+hHandle]
0x180027866  mov     rcx, [rsp+188h+var_38]
0x18002786e  xor     rcx, rsp; StackCookie
0x180027871  call    __security_check_cookie
0x180027876  add     rsp, 160h
0x18002787d  pop     r15
0x18002787f  pop     r14
0x180027881  pop     rdi
0x180027882  pop     rsi
0x180027883  pop     rbx
0x180027884  retn
```
