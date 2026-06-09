# OOBE::Health::details::SetRegistryValue

- ea: `0x180026668`
- end: `0x180026763`
- name: `OOBE::Health::details::SetRegistryValue`
- size: `251`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022c50`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x18001475c`
- `0x1800227ac`
- `0x180024d70`
- `0x180026668`
- `0x180027aec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026728`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180026728`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800266f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800266f1`

## string_xrefs

- `0x18002669f`: `OOBECompletedForOOBEHealth`
- `0x180026698`: `Software\Microsoft\Windows\CurrentVersion\OOBE\OOBECompletedForOOBEHealth`
- `0x18002671d`: `AnyoneReadOOBECompleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OOBE::Health::details::SetRegistryValue(__int64 a1, HKEY a2)
{
  int RedirectionKeyPath; // eax
  unsigned int v3; // eax
  wil::details::in1diag3 *v4; // rcx
  __int64 v5; // rdx
  int phkResult; // [rsp+20h] [rbp-20h]
  unsigned int phkResulta; // [rsp+20h] [rbp-20h]
  BYTE Data[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  HKEY hKey; // [rsp+58h] [rbp+18h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+20h] BYREF

  hKey = a2;
  *(_DWORD *)Data = 1;
  lpSubKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpSubKey,
    0);
  RedirectionKeyPath = GetRedirectionKeyPath(
                         L"OOBECompletedForOOBEHealth",
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\OOBE\\OOBECompletedForOOBEHealth",
                         (unsigned __int16 **)&lpSubKey);
  if ( RedirectionKeyPath >= 0 )
  {
    hKey = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &hKey);
    v4 = retaddr;
    if ( v3 )
    {
      v5 = 400;
    }
    else
    {
      v3 = RegSetValueExW(hKey, L"AnyoneReadOOBECompleted", 0, 4u, Data, 4u);
      v4 = retaddr;
      if ( !v3 )
      {
LABEL_8:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
      }
      v5 = 402;
    }
    wil::details::in1diag3::_Log_Win32(
      v4,
      (void *)v5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
      (const char *)v3,
      phkResulta);
    goto LABEL_8;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x18D,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\OOBEHealthTracker.h",
    (const char *)(unsigned int)RedirectionKeyPath,
    phkResult);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpSubKey);
}

```

## disassembly

```asm
0x180026668  mov     [rsp-8+lpSubKey], r8
0x18002666d  mov     [rsp-8+hKey], rdx
0x180026672  push    rbp
0x180026673  mov     rbp, rsp
0x180026676  sub     rsp, 40h
0x18002667a  mov     dword ptr [rbp+Data], 1
0x180026681  mov     [rbp+lpSubKey], 0
0x180026689  xor     edx, edx
0x18002668b  lea     rcx, [rbp+lpSubKey]
0x18002668f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180026694  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x180026698  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002669f  lea     rcx, aOobecompletedf; "OOBECompletedForOOBEHealth"
0x1800266a6  call    ?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z; GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)
0x1800266ab  mov     rcx, [rbp+8]; this
0x1800266af  test    eax, eax
0x1800266b1  jns     short loc_1800266CC
0x1800266b3  mov     r9d, eax; char *
0x1800266b6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x1800266bd  mov     edx, 18Dh; void *
0x1800266c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800266c7  jmp     loc_180026754
0x1800266cc  mov     [rbp+hKey], 0
0x1800266d4  lea     rax, [rbp+hKey]
0x1800266d8  mov     [rsp+40h+phkResult], rax; phkResult
0x1800266dd  mov     r9d, 2001Fh; samDesired
0x1800266e3  xor     r8d, r8d; ulOptions
0x1800266e6  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x1800266ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800266f1  call    cs:__imp_RegOpenKeyExW
0x1800266f7  mov     rcx, [rbp+8]
0x1800266fb  test    eax, eax
0x1800266fd  jz      short loc_180026706
0x1800266ff  mov     edx, 190h
0x180026704  jmp     short loc_18002673B
0x180026706  mov     r9d, 4; dwType
0x18002670c  mov     [rsp+40h+cbData], r9d; cbData
0x180026711  lea     rax, [rbp+Data]
0x180026715  mov     [rsp+40h+phkResult], rax; unsigned int
0x18002671a  xor     r8d, r8d; Reserved
0x18002671d  lea     rdx, Value; "AnyoneReadOOBECompleted"
0x180026724  mov     rcx, [rbp+hKey]; hKey
0x180026728  call    cs:__imp_RegSetValueExW
0x18002672e  mov     rcx, [rbp+8]; this
0x180026732  test    eax, eax
0x180026734  jz      short loc_18002674A
0x180026736  mov     edx, 192h; void *
0x18002673b  mov     r9d, eax; char *
0x18002673e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\OOBEH"...
0x180026745  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002674a  lea     rcx, [rbp+hKey]
0x18002674e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180026753  nop
0x180026754  lea     rcx, [rbp+lpSubKey]
0x180026758  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002675d  add     rsp, 40h
0x180026761  pop     rbp
0x180026762  retn
```
