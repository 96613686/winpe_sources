# GetTimestampFromRegistryOrCreateNew(ushort const *,ushort const *,unsigned __int64 *)

- ea: `0x180061d48`
- end: `0x180061e1e`
- name: `?GetTimestampFromRegistryOrCreateNew@@YAJPEBG0PEA_K@Z`
- size: `214`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180005914`

## callees

- `0x180004644`
- `0x180061d48`
- `0x180061e24`
- `0x180061f40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180061da0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180061da0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061e0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180061e0b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061de2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061de2`

## pseudocode

```c
__int64 __fastcall GetTimestampFromRegistryOrCreateNew(unsigned __int16 *a1, const unsigned __int16 *a2, BYTE *a3)
{
  unsigned int v4; // ebx
  HKEY v5; // rcx
  HKEY v6; // rcx
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  const unsigned __int16 *pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  pcbData = a2;
  hKey = (HKEY)a1;
  v4 = 0;
  GetServiceMutableStateKey(&hkey, 0x2001Fu);
  v5 = hkey;
  *(_QWORD *)a3 = 0;
  LODWORD(pcbData) = 8;
  if ( RegGetValueW(v5, 0, L"LastCheckedBannedListTimeStamp", 0x40u, 0, a3, (LPDWORD)&pcbData) == 2 )
  {
    hKey = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::swap(
      &hKey,
      &hkey);
    v6 = hKey;
    *(_QWORD *)a3 = 0;
    v7 = RegSetValueExW(v6, L"LastCheckedBannedListTimeStamp", 0, 0xBu, a3, 8u);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v4;
}

```

## disassembly

```asm
0x180061d48  mov     rax, rsp
0x180061d4b  mov     [rax+20h], rbx
0x180061d4f  mov     [rax+10h], rdx
0x180061d53  mov     [rax+8], rcx
0x180061d57  push    rdi
0x180061d58  sub     rsp, 40h
0x180061d5c  mov     edx, 2001Fh; samDesired
0x180061d61  lea     rcx, [rax+18h]; phkResult
0x180061d65  mov     rdi, r8
0x180061d68  xor     ebx, ebx
0x180061d6a  call    ?GetServiceMutableStateKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; GetServiceMutableStateKey(ulong)
0x180061d6f  mov     rcx, [rsp+48h+hkey]; hkey
0x180061d74  lea     rax, [rsp+48h+arg_8]
0x180061d79  mov     [rsp+48h+pcbData], rax; pcbData
0x180061d7e  lea     r9d, [rbx+40h]; dwFlags
0x180061d82  mov     [rsp+48h+pvData], rdi; pvData
0x180061d87  lea     r8, aLastcheckedban; "LastCheckedBannedListTimeStamp"
0x180061d8e  xor     edx, edx; lpSubKey
0x180061d90  mov     [rsp+48h+pdwType], rbx; pdwType
0x180061d95  mov     [rdi], rbx
0x180061d98  mov     dword ptr [rsp+48h+arg_8], 8
0x180061da0  call    cs:__imp_RegGetValueW
0x180061da6  cmp     eax, 2
0x180061da9  jnz     short loc_180061E01
0x180061dab  lea     rdx, [rsp+48h+hkey]
0x180061db0  mov     [rsp+48h+hKey], rbx
0x180061db5  lea     rcx, [rsp+48h+hKey]
0x180061dba  call    ?swap@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x180061dbf  mov     rcx, [rsp+48h+hKey]; hKey
0x180061dc4  lea     r9d, [rbx+0Bh]; dwType
0x180061dc8  xor     r8d, r8d; Reserved
0x180061dcb  mov     dword ptr [rsp+48h+pvData], 8; cbData
0x180061dd3  lea     rdx, aLastcheckedban; "LastCheckedBannedListTimeStamp"
0x180061dda  mov     [rdi], rbx
0x180061ddd  mov     [rsp+48h+pdwType], rdi; lpData
0x180061de2  call    cs:__imp_RegSetValueExW
0x180061de8  mov     ebx, eax
0x180061dea  test    eax, eax
0x180061dec  jle     short loc_180061DF7
0x180061dee  movzx   ebx, ax
0x180061df1  or      ebx, 80070000h
0x180061df7  lea     rcx, [rsp+48h+hKey]
0x180061dfc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180061e01  mov     rcx, [rsp+48h+hkey]; hKey
0x180061e06  test    rcx, rcx
0x180061e09  jz      short loc_180061E11
0x180061e0b  call    cs:__imp_RegCloseKey
0x180061e11  mov     eax, ebx
0x180061e13  mov     rbx, [rsp+48h+arg_18]
0x180061e18  add     rsp, 40h
0x180061e1c  pop     rdi
0x180061e1d  retn
```
