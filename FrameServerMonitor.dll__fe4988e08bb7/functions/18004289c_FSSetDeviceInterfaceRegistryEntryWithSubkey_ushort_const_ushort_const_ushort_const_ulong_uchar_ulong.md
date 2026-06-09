# FSSetDeviceInterfaceRegistryEntryWithSubkey(ushort const *,ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18004289c`
- end: `0x18004297f`
- name: `?FSSetDeviceInterfaceRegistryEntryWithSubkey@@YAJPEBG00KPEAEK@Z`
- size: `227`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, const unsigned __int16 *, LPCWSTR lpValueName, DWORD dwType, BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180022edc`

## callees

- `0x1800060f8`
- `0x180006a98`
- `0x18000e6bc`
- `0x180017b98`
- `0x18003fa34`
- `0x18004289c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180042923`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180042923`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042913`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180042913`

## pseudocode

```c
__int64 __fastcall FSSetDeviceInterfaceRegistryEntryWithSubkey(
        LPCWSTR pszDeviceInterface,
        const unsigned __int16 *a2,
        LPCWSTR lpValueName,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  signed int v10; // ebx
  LSTATUS v11; // eax
  HKEY hKey[7]; // [rsp+30h] [rbp-38h] BYREF

  hKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  v10 = FSCreateDeviceInterfaceRegistryKey(pszDeviceInterface, a2, hKey);
  if ( v10 >= 0 )
  {
    v11 = dwType && (lpData || cbData)
        ? RegSetValueExW(hKey[0], lpValueName, 0, dwType, lpData, cbData)
        : RegDeleteValueW(hKey[0], lpValueName);
    v10 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v10 = (unsigned __int16)v11 | 0x80070000;
      if ( v10 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v10);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004289c  push    rbx
0x18004289e  push    rbp
0x18004289f  push    rsi
0x1800428a0  push    rdi
0x1800428a1  sub     rsp, 48h
0x1800428a5  mov     rbx, rdx
0x1800428a8  mov     [rsp+68h+hKey], 0
0x1800428b1  mov     rdi, rcx
0x1800428b4  xor     edx, edx
0x1800428b6  lea     rcx, [rsp+68h+hKey]
0x1800428bb  mov     esi, r9d
0x1800428be  mov     rbp, r8
0x1800428c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800428c6  lea     r8, [rsp+68h+hKey]; HKEY *
0x1800428cb  mov     rdx, rbx; unsigned __int16 *
0x1800428ce  mov     rcx, rdi; pszDeviceInterface
0x1800428d1  call    ?FSCreateDeviceInterfaceRegistryKey@@YAJPEBG0PEAPEAUHKEY__@@@Z; FSCreateDeviceInterfaceRegistryKey(ushort const *,ushort const *,HKEY__ * *)
0x1800428d6  mov     ebx, eax
0x1800428d8  test    eax, eax
0x1800428da  js      loc_18004296A
0x1800428e0  test    esi, esi
0x1800428e2  jz      short loc_18004291B
0x1800428e4  mov     rcx, [rsp+68h+arg_20]
0x1800428ec  mov     eax, [rsp+68h+arg_28]
0x1800428f3  test    rcx, rcx
0x1800428f6  jnz     short loc_1800428FC
0x1800428f8  test    eax, eax
0x1800428fa  jz      short loc_18004291B
0x1800428fc  mov     [rsp+68h+cbData], eax; cbData
0x180042900  mov     r9d, esi; dwType
0x180042903  mov     [rsp+68h+lpData], rcx; lpData
0x180042908  xor     r8d, r8d; Reserved
0x18004290b  mov     rcx, [rsp+68h+hKey]; hKey
0x180042910  mov     rdx, rbp; lpValueName
0x180042913  call    cs:__imp_RegSetValueExW
0x180042919  jmp     short loc_180042929
0x18004291b  mov     rcx, [rsp+68h+hKey]; hKey
0x180042920  mov     rdx, rbp; lpValueName
0x180042923  call    cs:__imp_RegDeleteValueW
0x180042929  mov     ebx, eax
0x18004292b  test    eax, eax
0x18004292d  jz      short loc_18004296A
0x18004292f  jle     short loc_18004293A
0x180042931  movzx   ebx, bx
0x180042934  or      ebx, 80070000h
0x18004293a  test    ebx, ebx
0x18004293c  jns     short loc_18004296A
0x18004293e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180042943  cmp     al, 1
0x180042945  jb      short loc_18004296A
0x180042947  mov     rcx, cs:WPP_GLOBAL_Control
0x18004294e  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180042955  mov     edx, 26h ; '&'
0x18004295a  mov     dword ptr [rsp+68h+lpData], ebx
0x18004295e  xor     r9d, r9d
0x180042961  mov     rcx, [rcx+10h]
0x180042965  call    WPP_SF_qD
0x18004296a  lea     rcx, [rsp+68h+hKey]
0x18004296f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180042974  mov     eax, ebx
0x180042976  add     rsp, 48h
0x18004297a  pop     rdi
0x18004297b  pop     rsi
0x18004297c  pop     rbp
0x18004297d  pop     rbx
0x18004297e  retn
```
