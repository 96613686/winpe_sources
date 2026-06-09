# MitigationRegUtils::DeleteMitigationRegKey(ushort const *)

- ea: `0x180029960`
- end: `0x180029ab4`
- name: `?DeleteMitigationRegKey@MitigationRegUtils@@SAJPEBG@Z`
- size: `340`
- prototype: `__int64 __fastcall(LPCWSTR pszSubKey)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18001f524`
- `0x18001f990`

## callees

- `0x18000a6e0`
- `0x18001206c`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x1800198b0`
- `0x180019f10`
- `0x18001fb04`
- `0x180024550`
- `0x180029960`
- `0x180029eb0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002999f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002999f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029a3a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029a3a`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180029a6c`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteKeyW` at `0x180029a6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MitigationRegUtils::DeleteMitigationRegKey(LPCWSTR pszSubKey)
{
  const char *v2; // r9
  unsigned int LastError; // ebx
  int MitigationRegistryPath; // eax
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rdx
  int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  HKEY hkey; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v12[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  hkey = 0;
  if ( InitOnceExecuteOnce(
         &MitigationRegUtils::s_InitOnce,
         (PINIT_ONCE_FN)MitigationRegUtils::InitStateSeparatedMitigationRootPath,
         0,
         0) )
  {
    std::wstring::wstring(v12);
    MitigationRegistryPath = MitigationRegUtils::GetMitigationRegistryPath(3, (__int64)v12);
    LastError = MitigationRegistryPath;
    if ( MitigationRegistryPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationregutils.cpp",
        (const char *)(unsigned int)MitigationRegistryPath,
        phkResult);
LABEL_5:
      std::wstring::_Tidy_deallocate(v12);
      goto LABEL_13;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0xF003Fu, &hkey);
    if ( v6 != 2 )
    {
      if ( v6 )
      {
        v7 = 300;
LABEL_9:
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)v7,
                      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationregutils.cpp",
                      (const char *)v6,
                      phkResulta);
        goto LABEL_5;
      }
      v6 = SHDeleteKeyW(hkey, pszSubKey);
      if ( (v6 & 0xFFFFFFFD) != 0 )
      {
        v7 = 310;
        goto LABEL_9;
      }
    }
    std::wstring::_Tidy_deallocate(v12);
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x11C,
                (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationregutils.cpp",
                v2);
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return LastError;
}

```

## disassembly

```asm
0x180029960  mov     [rsp-8+arg_8], rbx
0x180029965  mov     [rsp-8+arg_10], rdi
0x18002996a  push    rbp
0x18002996b  mov     rbp, rsp
0x18002996e  sub     rsp, 60h
0x180029972  mov     rax, cs:__security_cookie
0x180029979  xor     rax, rsp
0x18002997c  mov     [rbp+var_8], rax
0x180029980  mov     rdi, rcx
0x180029983  mov     [rbp+hkey], 0
0x18002998b  xor     r9d, r9d; Context
0x18002998e  xor     r8d, r8d; Parameter
0x180029991  lea     rdx, ?InitStateSeparatedMitigationRootPath@MitigationRegUtils@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180029998  lea     rcx, ?s_InitOnce@MitigationRegUtils@@0T_RTL_RUN_ONCE@@A; InitOnce
0x18002999f  call    cs:__imp_InitOnceExecuteOnce
0x1800299a5  test    eax, eax
0x1800299a7  jnz     short loc_1800299C5
0x1800299a9  mov     rcx, [rbp+8]; this
0x1800299ad  lea     r8, aOnecoreBaseDia_7; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800299b4  mov     edx, 11Ch; void *
0x1800299b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800299be  mov     ebx, eax
0x1800299c0  jmp     loc_180029A8B
0x1800299c5  lea     rcx, [rbp+var_28]
0x1800299c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800299ce  nop
0x1800299cf  lea     rdx, [rbp+var_28]
0x1800299d3  mov     ecx, 3
0x1800299d8  call    ?GetMitigationRegistryPath@MitigationRegUtils@@SAJW4MitigationRegistryKey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MitigationRegUtils::GetMitigationRegistryPath(MitigationRegistryKey,std::wstring &)
0x1800299dd  mov     ebx, eax
0x1800299df  test    eax, eax
0x1800299e1  jns     short loc_180029A0A
0x1800299e3  mov     rcx, [rbp+8]; this
0x1800299e7  mov     r9d, eax; char *
0x1800299ea  lea     r8, aOnecoreBaseDia_7; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800299f1  mov     edx, 11Fh; void *
0x1800299f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299fb  nop
0x1800299fc  lea     rcx, [rbp+var_28]
0x180029a00  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a05  jmp     loc_180029A8B
0x180029a0a  xor     edx, edx
0x180029a0c  lea     rcx, [rbp+hkey]
0x180029a10  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180029a15  lea     rcx, [rbp+var_28]
0x180029a19  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180029a1e  mov     rdx, rax; lpSubKey
0x180029a21  lea     rax, [rbp+hkey]
0x180029a25  mov     qword ptr [rsp+60h+phkResult], rax; unsigned int
0x180029a2a  mov     r9d, 0F003Fh; samDesired
0x180029a30  xor     r8d, r8d; ulOptions
0x180029a33  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180029a3a  call    cs:__imp_RegOpenKeyExW
0x180029a40  cmp     eax, 2
0x180029a43  jz      short loc_180029A80
0x180029a45  test    eax, eax
0x180029a47  jz      short loc_180029A65
0x180029a49  mov     edx, 12Ch; void *
0x180029a4e  lea     r8, aOnecoreBaseDia_7; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180029a55  mov     r9d, eax; char *
0x180029a58  mov     rcx, [rbp+8]; this
0x180029a5c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180029a61  mov     ebx, eax
0x180029a63  jmp     short loc_1800299FC
0x180029a65  mov     rdx, rdi; pszSubKey
0x180029a68  mov     rcx, [rbp+hkey]; hkey
0x180029a6c  call    cs:__imp_SHDeleteKeyW
0x180029a72  test    eax, 0FFFFFFFDh
0x180029a77  jz      short loc_180029A80
0x180029a79  mov     edx, 136h
0x180029a7e  jmp     short loc_180029A4E
0x180029a80  lea     rcx, [rbp+var_28]
0x180029a84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a89  xor     ebx, ebx
0x180029a8b  lea     rcx, [rbp+hkey]
0x180029a8f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029a94  mov     eax, ebx
0x180029a96  mov     rcx, [rbp+var_8]
0x180029a9a  xor     rcx, rsp; StackCookie
0x180029a9d  call    __security_check_cookie
0x180029aa2  lea     r11, [rsp+60h+var_s0]
0x180029aa7  mov     rbx, [r11+18h]
0x180029aab  mov     rdi, [r11+20h]
0x180029aaf  mov     rsp, r11
0x180029ab2  pop     rbp
0x180029ab3  retn
```
