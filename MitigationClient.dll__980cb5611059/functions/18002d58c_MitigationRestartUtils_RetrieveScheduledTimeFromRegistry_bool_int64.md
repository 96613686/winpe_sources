# MitigationRestartUtils::RetrieveScheduledTimeFromRegistry(bool &,__int64 &)

- ea: `0x18002d58c`
- end: `0x18002d6d6`
- name: `?RetrieveScheduledTimeFromRegistry@MitigationRestartUtils@@SAJAEA_NAEA_J@Z`
- size: `330`
- prototype: `static int(bool *, __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18002d4b0`
- `0x18002d4fc`

## callees

- `0x18000a6e0`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x1800198b0`
- `0x180019f10`
- `0x180024550`
- `0x180029eb0`
- `0x18002d58c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d60c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d60c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d674`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d674`

## string_xrefs

- `0x18002d666`: `RestartScheduledTimestamp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MitigationRestartUtils::RetrieveScheduledTimeFromRegistry(bool *a1, __int64 *a2)
{
  const WCHAR *v4; // rax
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  LSTATUS ValueW; // eax
  signed int v8; // ecx
  unsigned int v9; // eax
  int phkResult; // [rsp+20h] [rbp-68h]
  HKEY hkey; // [rsp+40h] [rbp-48h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-40h] BYREF
  _BYTE v14[32]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *a1 = 0;
  std::wstring::wstring((__int64)v14);
  MitigationRegUtils::GetMitigationRegistryPath(3, (__int64)v14);
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hkey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
  {
    pcbData = 8;
    ValueW = RegGetValueW(hkey, 0, L"RestartScheduledTimestamp", 8u, 0, a2, &pcbData);
    v8 = ValueW;
    if ( ValueW > 0 )
      v8 = (unsigned __int16)ValueW | 0x80070000;
    if ( v8 >= 0 )
      *a1 = 1;
    v9 = 0;
    if ( v8 != -2147024894 )
      v9 = v8;
    v6 = v9;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationrestartutils.cpp",
      (const char *)v6,
      phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  std::wstring::_Tidy_deallocate(v14);
  return v6;
}

```

## disassembly

```asm
0x18002d58c  mov     [rsp+arg_10], rbx
0x18002d591  mov     [rsp+arg_18], rsi
0x18002d596  push    rdi
0x18002d597  sub     rsp, 80h
0x18002d59e  mov     rax, cs:__security_cookie
0x18002d5a5  xor     rax, rsp
0x18002d5a8  mov     [rsp+88h+var_18], rax
0x18002d5ad  mov     rsi, rdx
0x18002d5b0  mov     rdi, rcx
0x18002d5b3  mov     byte ptr [rcx], 0
0x18002d5b6  lea     rcx, [rsp+88h+var_38]
0x18002d5bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d5c0  nop
0x18002d5c1  lea     rdx, [rsp+88h+var_38]
0x18002d5c6  mov     ecx, 3
0x18002d5cb  call    ?GetMitigationRegistryPath@MitigationRegUtils@@SAJW4MitigationRegistryKey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MitigationRegUtils::GetMitigationRegistryPath(MitigationRegistryKey,std::wstring &)
0x18002d5d0  mov     [rsp+88h+hkey], 0
0x18002d5d9  xor     edx, edx
0x18002d5db  lea     rcx, [rsp+88h+hkey]
0x18002d5e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002d5e5  lea     rcx, [rsp+88h+var_38]
0x18002d5ea  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002d5ef  mov     rdx, rax; lpSubKey
0x18002d5f2  lea     rax, [rsp+88h+hkey]
0x18002d5f7  mov     [rsp+88h+phkResult], rax; int
0x18002d5fc  mov     r9d, 20019h; samDesired
0x18002d602  xor     r8d, r8d; ulOptions
0x18002d605  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d60c  call    cs:__imp_RegOpenKeyExW
0x18002d612  mov     ebx, eax
0x18002d614  test    eax, eax
0x18002d616  jle     short loc_18002D621
0x18002d618  movzx   ebx, ax
0x18002d61b  or      ebx, 80070000h
0x18002d621  test    ebx, ebx
0x18002d623  jns     short loc_18002D643
0x18002d625  mov     rcx, [rsp+88h]; this
0x18002d62d  mov     r9d, ebx; char *
0x18002d630  lea     r8, aOnecoreBaseDia_18; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002d637  mov     edx, 52h ; 'R'; void *
0x18002d63c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d641  jmp     short loc_18002D69D
0x18002d643  mov     r9d, 8; dwFlags
0x18002d649  mov     [rsp+88h+var_40], r9d
0x18002d64e  lea     rax, [rsp+88h+var_40]
0x18002d653  mov     [rsp+88h+pcbData], rax; pcbData
0x18002d658  mov     [rsp+88h+pvData], rsi; pvData
0x18002d65d  mov     [rsp+88h+phkResult], 0; pdwType
0x18002d666  lea     r8, Value; "RestartScheduledTimestamp"
0x18002d66d  xor     edx, edx; lpSubKey
0x18002d66f  mov     rcx, [rsp+88h+hkey]; hkey
0x18002d674  call    cs:__imp_RegGetValueW
0x18002d67a  mov     ecx, eax
0x18002d67c  test    eax, eax
0x18002d67e  jle     short loc_18002D689
0x18002d680  movzx   ecx, ax
0x18002d683  or      ecx, 80070000h
0x18002d689  test    ecx, ecx
0x18002d68b  js      short loc_18002D690
0x18002d68d  mov     byte ptr [rdi], 1
0x18002d690  xor     eax, eax
0x18002d692  cmp     ecx, 80070002h
0x18002d698  cmovnz  eax, ecx
0x18002d69b  mov     ebx, eax
0x18002d69d  lea     rcx, [rsp+88h+hkey]
0x18002d6a2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d6a7  nop
0x18002d6a8  lea     rcx, [rsp+88h+var_38]
0x18002d6ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d6b2  mov     eax, ebx
0x18002d6b4  mov     rcx, [rsp+88h+var_18]
0x18002d6b9  xor     rcx, rsp; StackCookie
0x18002d6bc  call    __security_check_cookie
0x18002d6c1  lea     r11, [rsp+88h+var_8]
0x18002d6c9  mov     rbx, [r11+20h]
0x18002d6cd  mov     rsi, [r11+28h]
0x18002d6d1  mov     rsp, r11
0x18002d6d4  pop     rdi
0x18002d6d5  retn
```
