# BrlApiService::GetDeviceConfig(void)

- ea: `0x1400706c0`
- end: `0x1400707c8`
- name: `?GetDeviceConfig@BrlApiService@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400708a8`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14000d850`
- `0x14000ed38`
- `0x14002c070`
- `0x1400706c0`
- `0x14007087c`

## import_xrefs

- `KERNEL32!RegQueryValueExW` at `0x14007076b`
- `KERNEL32!RegQueryValueExW` at `0x14007076b`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140070724`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x140070724`

## string_xrefs

- `0x140070764`: `BrailleDeviceConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrlApiService::GetDeviceConfig(__int64 a1, __int64 a2)
{
  HKEY *v3; // rax
  unsigned int v4; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  BYTE *v7; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type[5]; // [rsp+3Ch] [rbp-C4h] BYREF
  BYTE Data[528]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  hKey = 0;
  memset_0(Data, 0, 0x208u);
  v3 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v4 = RegOpenKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Narrator\\NoRoam", v3);
  if ( v4
    || hKey
    && (Type[0] = 1, cbData = 520, (v4 = RegQueryValueExW(hKey, L"BrailleDeviceConfig", 0, Type, Data, &cbData)) != 0) )
  {
    wil::details::in1diag3::Log_Win32(retaddr, v5, v6, (const char *)v4, lpData);
    v7 = (BYTE *)&::Data;
  }
  else
  {
    v7 = Data;
  }
  std::wstring::wstring(a2, (__int64)v7);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return a2;
}

```

## disassembly

```asm
0x1400706c0  mov     [rsp-8+arg_0], rbx
0x1400706c5  push    rbp
0x1400706c6  lea     rbp, [rsp-170h]
0x1400706ce  sub     rsp, 270h
0x1400706d5  mov     rax, cs:__security_cookie
0x1400706dc  xor     rax, rsp
0x1400706df  mov     [rbp+170h+var_10], rax
0x1400706e6  mov     rbx, rdx
0x1400706e9  mov     [rsp+270h+hKey], rdx
0x1400706ee  mov     [rsp+270h+hKey], 0
0x1400706f7  xor     edx, edx; Val
0x1400706f9  mov     r8d, 208h; Size
0x1400706ff  lea     rcx, [rsp+270h+Data]; void *
0x140070704  call    memset_0
0x140070709  lea     rcx, [rsp+270h+hKey]
0x14007070e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140070713  mov     r8, rax; phkResult
0x140070716  lea     rdx, aSoftwareMicros_13; "Software\\Microsoft\\Narrator\\NoRoam"
0x14007071d  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140070724  call    cs:__imp_RegOpenKeyW
0x14007072a  test    eax, eax
0x14007072c  jnz     short loc_14007077C
0x14007072e  mov     rcx, [rsp+270h+hKey]; hKey
0x140070733  test    rcx, rcx
0x140070736  jz      short loc_140070775
0x140070738  mov     [rsp+270h+Type], 1
0x140070740  mov     [rsp+270h+cbData], 208h
0x140070748  lea     rax, [rsp+270h+cbData]
0x14007074d  mov     [rsp+270h+lpcbData], rax; lpcbData
0x140070752  lea     rax, [rsp+270h+Data]
0x140070757  mov     [rsp+270h+lpData], rax; lpData
0x14007075c  lea     r9, [rsp+270h+Type]; lpType
0x140070761  xor     r8d, r8d; lpReserved
0x140070764  lea     rdx, aBrailledevicec; "BrailleDeviceConfig"
0x14007076b  call    cs:__imp_RegQueryValueExW
0x140070771  test    eax, eax
0x140070773  jnz     short loc_14007077C
0x140070775  lea     rdx, [rsp+270h+Data]
0x14007077a  jmp     short loc_140070792
0x14007077c  mov     rcx, [rbp+178h]; this
0x140070783  mov     r9d, eax; char *
0x140070786  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x14007078b  lea     rdx, Data
0x140070792  mov     rcx, rbx
0x140070795  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14007079a  nop
0x14007079b  lea     rcx, [rsp+270h+hKey]
0x1400707a0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400707a5  mov     rax, rbx
0x1400707a8  mov     rcx, [rbp+170h+var_10]
0x1400707af  xor     rcx, rsp; StackCookie
0x1400707b2  call    __security_check_cookie
0x1400707b7  mov     rbx, [rsp+270h+arg_0]
0x1400707bf  add     rsp, 270h
0x1400707c6  pop     rbp
0x1400707c7  retn
```
