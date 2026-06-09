# RegistryListener::CheckForRemovedProductCodes(RegistryLocation &)

- ea: `0x1800814b8`
- end: `0x180081616`
- name: `?CheckForRemovedProductCodes@RegistryListener@@AEAAXAEAURegistryLocation@@@Z`
- size: `350`
- prototype: `void __fastcall(RegistryListener *__hidden this, struct RegistryLocation *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080f58`

## callees

- `0x180012b84`
- `0x180012c0c`
- `0x18002498c`
- `0x180035d88`
- `0x180047164`
- `0x18006bd20`
- `0x1800814b8`
- `0x1800821ac`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800814e9`
- `ADVAPI32!RegOpenKeyExW` at `0x180081568`
- `ADVAPI32!RegOpenKeyExW` at `0x1800814e9`
- `ADVAPI32!RegOpenKeyExW` at `0x180081568`

## string_xrefs

- `0x1800814fb`: `pcshell\shell\cloudrestorelauncher\apprestore\lib\registrylistener.cpp`
- `0x1800815e8`: `pcshell\shell\cloudrestorelauncher\apprestore\lib\registrylistener.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RegistryListener::CheckForRemovedProductCodes(RegistryListener *this, struct RegistryLocation *a2)
{
  unsigned int v3; // eax
  _QWORD *v4; // rbx
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // r11
  __int64 v10; // rcx
  __int64 v11; // rax
  _QWORD *v12; // rdi
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  unsigned int phkResulta; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  HKEY v17; // [rsp+58h] [rbp+10h] BYREF
  char v18; // [rsp+60h] [rbp+18h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(*(HKEY *)a2, *((LPCWSTR *)a2 + 1), 0, 0x20019u, &hKey);
  if ( v3 )
  {
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0xB3,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\registrylistener.cpp",
      (const char *)v3,
      phkResult);
  }
  else
  {
    v4 = (_QWORD *)**((_QWORD **)a2 + 4);
    while ( v4 != *((_QWORD **)a2 + 4) )
    {
      winrt::hstring::hstring((winrt::hstring *)&v18, (const struct winrt::hstring *)(v4 + 2));
      v17 = 0;
      v5 = winrt::hstring::c_str((winrt::hstring *)&v18);
      v6 = RegOpenKeyExW(hKey, v5, 0, 0x20019u, &v17);
      if ( v6 == 2 )
      {
        v8 = std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>::operator()<winrt::hstring>(
               v7,
               v4 + 2);
        v9 = 2 * (*((_QWORD *)a2 + 9) & v8);
        v10 = *((_QWORD *)a2 + 6);
        if ( *(_QWORD **)(v10 + 16 * (*((_QWORD *)a2 + 9) & v8) + 8) == v4 )
        {
          if ( *(_QWORD **)(v10 + 16 * (*((_QWORD *)a2 + 9) & v8)) == v4 )
          {
            v11 = *((_QWORD *)a2 + 4);
            *(_QWORD *)(v10 + 8 * v9) = v11;
          }
          else
          {
            v11 = v4[1];
          }
          *(_QWORD *)(v10 + 8 * v9 + 8) = v11;
        }
        else if ( *(_QWORD **)(v10 + 16 * (*((_QWORD *)a2 + 9) & v8)) == v4 )
        {
          *(_QWORD *)(v10 + 16 * (*((_QWORD *)a2 + 9) & v8)) = *v4;
        }
        v12 = (_QWORD *)*v4;
        --*((_QWORD *)a2 + 5);
        *(_QWORD *)v4[1] = v12;
        v12[1] = v4[1];
        std::_List_node<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>,void *>>>(
          v10,
          v4);
        v4 = v12;
      }
      else
      {
        if ( v6 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0xCE,
            (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\apprestore\\lib\\registrylistener.cpp",
            (const char *)v6,
            phkResulta);
        v4 = (_QWORD *)*v4;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v17);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v18);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800814b8  mov     r11, rsp
0x1800814bb  mov     [r11+8], rcx
0x1800814bf  push    rbx
0x1800814c0  push    rsi
0x1800814c1  push    rdi
0x1800814c2  sub     rsp, 30h
0x1800814c6  mov     rsi, rdx
0x1800814c9  mov     qword ptr [r11+8], 0
0x1800814d1  lea     rax, [r11+8]
0x1800814d5  mov     [r11-28h], rax
0x1800814d9  mov     r9d, 20019h; samDesired
0x1800814df  xor     r8d, r8d; ulOptions
0x1800814e2  mov     rdx, [rdx+8]; lpSubKey
0x1800814e6  mov     rcx, [rsi]; hKey
0x1800814e9  call    cs:__imp_RegOpenKeyExW
0x1800814ef  mov     rcx, [rsp+48h]; this
0x1800814f4  test    eax, eax
0x1800814f6  jz      short loc_18008151F
0x1800814f8  mov     r9d, eax; char *
0x1800814fb  lea     r8, aPcshellShellCl_35; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x180081502  mov     edx, 0B3h; void *
0x180081507  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18008150c  nop
0x18008150d  lea     rcx, [rsp+48h+hKey]
0x180081512  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081517  add     rsp, 30h
0x18008151b  pop     rdi
0x18008151c  pop     rsi
0x18008151d  pop     rbx
0x18008151e  retn
0x18008151f  mov     rbx, [rsi+20h]
0x180081523  mov     rbx, [rbx]
0x180081526  cmp     rbx, [rsi+20h]
0x18008152a  jz      short loc_18008150D
0x18008152c  lea     rdx, [rbx+10h]; struct winrt::hstring *
0x180081530  lea     rcx, [rsp+48h+arg_10]; this
0x180081535  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18008153a  mov     [rsp+48h+arg_8], 0
0x180081543  lea     rcx, [rsp+48h+arg_10]; this
0x180081548  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18008154d  mov     rdx, rax; lpSubKey
0x180081550  lea     rax, [rsp+48h+arg_8]
0x180081555  mov     qword ptr [rsp+48h+phkResult], rax; unsigned int
0x18008155a  mov     r9d, 20019h; samDesired
0x180081560  xor     r8d, r8d; ulOptions
0x180081563  mov     rcx, [rsp+48h+hKey]; hKey
0x180081568  call    cs:__imp_RegOpenKeyExW
0x18008156e  cmp     eax, 2
0x180081571  jnz     short loc_1800815DC
0x180081573  lea     rdx, [rbx+10h]
0x180081577  call    ??$?RUhstring@winrt@@@?$_Uhash_compare@Uhstring@winrt@@U?$hash@Uhstring@winrt@@@std@@U?$equal_to@Uhstring@winrt@@@4@@std@@QEBA_KAEBUhstring@winrt@@@Z; std::_Uhash_compare<winrt::hstring,std::hash<winrt::hstring>,std::equal_to<winrt::hstring>>::operator()<winrt::hstring>(winrt::hstring const &)
0x18008157c  mov     r11, rax
0x18008157f  and     r11, [rsi+48h]
0x180081583  add     r11, r11
0x180081586  mov     rcx, [rsi+30h]
0x18008158a  cmp     [rcx+r11*8+8], rbx
0x18008158f  jnz     short loc_1800815AC
0x180081591  cmp     [rcx+r11*8], rbx
0x180081595  jnz     short loc_1800815A1
0x180081597  mov     rax, [rsi+20h]
0x18008159b  mov     [rcx+r11*8], rax
0x18008159f  jmp     short loc_1800815A5
0x1800815a1  mov     rax, [rbx+8]
0x1800815a5  mov     [rcx+r11*8+8], rax
0x1800815aa  jmp     short loc_1800815B9
0x1800815ac  cmp     [rcx+r11*8], rbx
0x1800815b0  jnz     short loc_1800815B9
0x1800815b2  mov     rax, [rbx]
0x1800815b5  mov     [rcx+r11*8], rax
0x1800815b9  mov     rdi, [rbx]
0x1800815bc  dec     qword ptr [rsi+28h]
0x1800815c0  mov     rax, [rbx+8]
0x1800815c4  mov     [rax], rdi
0x1800815c7  mov     rax, [rbx+8]
0x1800815cb  mov     [rdi+8], rax
0x1800815cf  mov     rdx, rbx
0x1800815d2  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBUhstring@winrt@@U?$pair@Uhstring@winrt@@U12@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>,void *>>>(std::allocator<std::_List_node<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>,void *>> &,std::_List_node<std::pair<winrt::hstring const,std::pair<winrt::hstring,winrt::hstring>>,void *> *)
0x1800815d7  mov     rbx, rdi
0x1800815da  jmp     short loc_1800815FC
0x1800815dc  test    eax, eax
0x1800815de  jz      short loc_1800815F9
0x1800815e0  mov     rcx, [rsp+48h]; this
0x1800815e5  mov     r9d, eax; char *
0x1800815e8  lea     r8, aPcshellShellCl_35; "pcshell\\shell\\cloudrestorelauncher\\a"...
0x1800815ef  mov     edx, 0CEh; void *
0x1800815f4  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800815f9  mov     rbx, [rbx]
0x1800815fc  lea     rcx, [rsp+48h+arg_8]
0x180081601  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081606  lea     rcx, [rsp+48h+arg_10]
0x18008160b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180081610  jmp     loc_180081526
```
