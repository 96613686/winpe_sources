# Microsoft::Bluetooth::Audio::GetBatsTransportPreference_0

- ea: `0x1800411b8`
- end: `0x18004125f`
- name: `Microsoft::Bluetooth::Audio::GetBatsTransportPreference_0`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041708`

## callees

- `0x180015b1c`
- `0x180019f80`
- `0x1800411b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800411f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800411f6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041237`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041237`

## string_xrefs

- `0x1800411e8`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Audio::GetBatsTransportPreference_0(__int64 a1)
{
  unsigned int v1; // ebx
  __int64 pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  pvData = a1;
  v1 = 0;
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats",
          0,
          0x20019u,
          &hkey) )
  {
    LODWORD(pvData) = 0;
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, L"UserPrefersClassicAudio", 0x10u, 0, &pvData, &pcbData) )
    {
      v1 = 1;
      if ( (_DWORD)pvData == 1 )
        v1 = 2;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v1;
}

```

## disassembly

```asm
0x1800411b8  mov     [rsp+arg_0], rcx
0x1800411bd  push    rbx
0x1800411be  sub     rsp, 40h
0x1800411c2  xor     ebx, ebx
0x1800411c4  lea     rcx, [rsp+48h+hkey]
0x1800411c9  xor     edx, edx
0x1800411cb  mov     [rsp+48h+hkey], rbx
0x1800411d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800411d5  lea     rax, [rsp+48h+hkey]
0x1800411da  mov     r9d, 20019h; samDesired
0x1800411e0  xor     r8d, r8d; ulOptions
0x1800411e3  mov     [rsp+48h+phkResult], rax; phkResult
0x1800411e8  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x1800411ef  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800411f6  call    cs:__imp_RegOpenKeyExW
0x1800411fc  test    eax, eax
0x1800411fe  jnz     short loc_18004124D
0x180041200  mov     rcx, [rsp+48h+hkey]; hkey
0x180041205  lea     rax, [rsp+48h+arg_8]
0x18004120a  mov     [rsp+48h+pcbData], rax; pcbData
0x18004120f  lea     r9d, [rbx+10h]; dwFlags
0x180041213  lea     rax, [rsp+48h+arg_0]
0x180041218  mov     dword ptr [rsp+48h+arg_0], ebx
0x18004121c  mov     [rsp+48h+pvData], rax; pvData
0x180041221  lea     r8, ValueName; "UserPrefersClassicAudio"
0x180041228  xor     edx, edx; lpSubKey
0x18004122a  mov     [rsp+48h+phkResult], rbx; pdwType
0x18004122f  mov     [rsp+48h+arg_8], 4
0x180041237  call    cs:__imp_RegGetValueW
0x18004123d  test    eax, eax
0x18004123f  jnz     short loc_18004124D
0x180041241  lea     ebx, [rax+1]
0x180041244  cmp     dword ptr [rsp+48h+arg_0], ebx
0x180041248  jnz     short loc_18004124D
0x18004124a  lea     ebx, [rax+2]
0x18004124d  lea     rcx, [rsp+48h+hkey]
0x180041252  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180041257  mov     eax, ebx
0x180041259  add     rsp, 40h
0x18004125d  pop     rbx
0x18004125e  retn
```
