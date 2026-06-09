# CloudExperienceHostBroker::Cortana::ReadRegistryDword(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180008d6c`
- end: `0x180008e2f`
- name: `?ReadRegistryDword@Cortana@CloudExperienceHostBroker@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `195`
- prototype: `__int64 __fastcall(CloudExperienceHostBroker::Cortana *this, HKEY, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031e40`
- `0x180031eb0`

## callees

- `0x180008d6c`
- `0x18002253c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008dfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008dfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008db4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008db4`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::Cortana::ReadRegistryDword(
        CloudExperienceHostBroker::Cortana *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  LSTATUS v6; // eax
  bool v7; // sf
  LSTATUS Value; // eax
  bool v9; // sf
  CloudExperienceHostBroker::Cortana *cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = a2;
  cbData = this;
  *(_DWORD *)a4 = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioPolicy", 0, 0x20019u, &hKey);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  if ( !v7 )
  {
    LODWORD(Data) = 0;
    LODWORD(cbData) = 4;
    Value = RegQueryValueExW(hKey, a3, 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData);
    v9 = Value < 0;
    if ( Value > 0 )
      v9 = 1;
    if ( !v9 )
      *(_DWORD *)a4 = (_DWORD)Data;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180008d6c  mov     r11, rsp
0x180008d6f  mov     [r11+18h], rbx
0x180008d73  mov     [r11+10h], rdx
0x180008d77  mov     [r11+8], rcx
0x180008d7b  push    rdi
0x180008d7c  sub     rsp, 30h
0x180008d80  mov     rbx, r9
0x180008d83  mov     dword ptr [r9], 0
0x180008d8a  mov     rdi, r8
0x180008d8d  mov     qword ptr [r11+20h], 0
0x180008d95  lea     rax, [r11+20h]
0x180008d99  mov     r9d, 20019h; samDesired
0x180008d9f  xor     r8d, r8d; ulOptions
0x180008da2  mov     [r11-18h], rax
0x180008da6  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x180008dad  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008db4  call    cs:__imp_RegOpenKeyExW
0x180008dba  test    eax, eax
0x180008dbc  jle     short loc_180008DC8
0x180008dbe  movzx   eax, ax
0x180008dc1  or      eax, 80070000h
0x180008dc6  test    eax, eax
0x180008dc8  js      short loc_180008E18
0x180008dca  mov     rcx, [rsp+38h+hKey]; hKey
0x180008dcf  lea     rax, [rsp+38h+cbData]
0x180008dd4  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180008dd9  xor     r9d, r9d; lpType
0x180008ddc  lea     rax, [rsp+38h+Data]
0x180008de1  mov     dword ptr [rsp+38h+Data], 0
0x180008de9  xor     r8d, r8d; lpReserved
0x180008dec  mov     [rsp+38h+lpData], rax; lpData
0x180008df1  mov     rdx, rdi; lpValueName
0x180008df4  mov     dword ptr [rsp+38h+cbData], 4
0x180008dfc  call    cs:__imp_RegQueryValueExW
0x180008e02  test    eax, eax
0x180008e04  jle     short loc_180008E10
0x180008e06  movzx   eax, ax
0x180008e09  or      eax, 80070000h
0x180008e0e  test    eax, eax
0x180008e10  js      short loc_180008E18
0x180008e12  mov     eax, dword ptr [rsp+38h+Data]
0x180008e16  mov     [rbx], eax
0x180008e18  lea     rcx, [rsp+38h+hKey]
0x180008e1d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180008e22  mov     rbx, [rsp+38h+arg_10]
0x180008e27  xor     eax, eax
0x180008e29  add     rsp, 30h
0x180008e2d  pop     rdi
0x180008e2e  retn
```
