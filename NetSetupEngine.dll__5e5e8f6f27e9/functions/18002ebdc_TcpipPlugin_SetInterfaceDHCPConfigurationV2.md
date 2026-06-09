# TcpipPlugin::SetInterfaceDHCPConfigurationV2

- ea: `0x18002ebdc`
- end: `0x18002edd8`
- name: `TcpipPlugin::SetInterfaceDHCPConfigurationV2`
- size: `508`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18002ee80`
- `0x180051cf0`

## callees

- `0x18000a430`
- `0x180011740`
- `0x180012108`
- `0x180015f50`
- `0x180017320`
- `0x180020f40`
- `0x18002ebdc`
- `0x180044324`
- `0x18004a2d0`
- `0x18005a5e8`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ed1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ed75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ed1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ed75`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ed9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ed9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ed60`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ed60`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TcpipPlugin::SetInterfaceDHCPConfigurationV2(void **a1, __int64 a2, int a3)
{
  HKEY v6; // rbx
  unsigned int v7; // ebx
  _BYTE v9[8]; // [rsp+70h] [rbp-90h] BYREF
  HKEY Uint64; // [rsp+78h] [rbp-88h]
  void **v11; // [rsp+80h] [rbp-80h] BYREF
  __int64 v12; // [rsp+88h] [rbp-78h] BYREF
  int v13; // [rsp+90h] [rbp-70h]
  __int128 v14; // [rsp+94h] [rbp-6Ch]
  __int64 v15; // [rsp+A8h] [rbp-58h]
  GUID v16; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v17[24]; // [rsp+C8h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+E0h] [rbp-20h] BYREF
  BYTE Data[8]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR SubKey[264]; // [rsp+F0h] [rbp-10h] BYREF

  v15 = -2;
  *(_DWORD *)Data = !NetSetup2::NetworkInterface::getordefault_DisableDhcp((NetSetup2::NetworkInterface *)a2);
  hKey = 0;
  v11 = a1;
  v12 = 0;
  v13 = 9;
  v14 = 0;
  NetSetup2::ActiveObject::GetProperty(&v11, &v16, (__int128 *)&NETSETUPPKEY_Transaction_OsDataHiveRegistryHandle, 0);
  Uint64 = (HKEY)NetSetup2::Property::GetUint64((NetSetup2::Property *)&v16);
  std::vector<_NETSETUPPROPKEY>::_Tidy(v17);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v12);
  swprintf_s<260>(
    SubKey,
    L"Networking\\Dhcp\\Client%u\\{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    a3 != 0 ? 6 : 4,
    *(unsigned int *)(a2 + 20),
    *(unsigned __int16 *)(a2 + 24),
    *(unsigned __int16 *)(a2 + 26),
    *(unsigned __int8 *)(a2 + 28),
    *(unsigned __int8 *)(a2 + 29),
    *(unsigned __int8 *)(a2 + 30),
    *(unsigned __int8 *)(a2 + 31),
    *(unsigned __int8 *)(a2 + 32),
    *(unsigned __int8 *)(a2 + 33),
    *(unsigned __int8 *)(a2 + 34),
    *(unsigned __int8 *)(a2 + 35));
  v6 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v9);
    RegCloseKey(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
  }
  hKey = 0;
  v7 = RegCreateKeyExW(Uint64, SubKey, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v7 )
  {
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    v7 = RegSetValueExW(hKey, L"EnableDHCP", 0, 4u, Data, 4u);
    if ( !v7 )
      v7 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x18002ebdc  push    rbp
0x18002ebde  push    rbx
0x18002ebdf  push    rsi
0x18002ebe0  push    rdi
0x18002ebe1  push    r12
0x18002ebe3  push    r13
0x18002ebe5  push    r14
0x18002ebe7  push    r15
0x18002ebe9  lea     rbp, [rsp-218h]
0x18002ebf1  sub     rsp, 318h
0x18002ebf8  mov     [rbp+250h+var_2A8], 0FFFFFFFFFFFFFFFEh
0x18002ec00  mov     rax, cs:__security_cookie
0x18002ec07  xor     rax, rsp
0x18002ec0a  mov     [rbp+250h+var_50], rax
0x18002ec11  mov     r12d, r8d
0x18002ec14  mov     r13, rdx
0x18002ec17  mov     rbx, rcx
0x18002ec1a  xor     edi, edi
0x18002ec1c  mov     rcx, rdx; this
0x18002ec1f  call    ?getordefault_DisableDhcp@NetworkInterface@NetSetup2@@QEBA_NXZ; NetSetup2::NetworkInterface::getordefault_DisableDhcp(void)
0x18002ec24  movzx   eax, al
0x18002ec27  xor     eax, 1
0x18002ec2a  mov     dword ptr [rbp+250h+Data], eax
0x18002ec2d  mov     [rbp+250h+hKey], rdi
0x18002ec31  xorps   xmm0, xmm0
0x18002ec34  mov     [rbp+250h+var_2D0], rbx
0x18002ec38  mov     [rbp+250h+var_2C8], rdi
0x18002ec3c  mov     [rbp+250h+var_2C0], 9
0x18002ec43  movdqu  [rbp+250h+var_2BC], xmm0
0x18002ec48  xor     r9d, r9d
0x18002ec4b  lea     r8, NETSETUPPKEY_Transaction_OsDataHiveRegistryHandle; unsigned int
0x18002ec52  lea     rdx, [rbp+250h+var_2A0]; struct _NETSETUPPROPKEY *
0x18002ec56  lea     rcx, [rbp+250h+var_2D0]; this
0x18002ec5a  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18002ec5f  nop
0x18002ec60  lea     rcx, [rbp+250h+var_2A0]; this
0x18002ec64  call    ?GetUint64@Property@NetSetup2@@QEBA_KXZ; NetSetup2::Property::GetUint64(void)
0x18002ec69  mov     [rsp+350h+var_2D8], rax
0x18002ec6e  lea     rcx, [rbp+250h+var_288]
0x18002ec72  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002ec77  nop
0x18002ec78  lea     rcx, [rbp+250h+var_2C8]
0x18002ec7c  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18002ec81  movzx   ecx, byte ptr [r13+23h]
0x18002ec86  movzx   edx, byte ptr [r13+22h]
0x18002ec8b  movzx   r10d, byte ptr [r13+21h]
0x18002ec90  movzx   r11d, byte ptr [r13+20h]
0x18002ec95  movzx   ebx, byte ptr [r13+1Fh]
0x18002ec9a  movzx   edi, byte ptr [r13+1Eh]
0x18002ec9f  movzx   eax, byte ptr [r13+1Dh]
0x18002eca4  movzx   esi, byte ptr [r13+1Ch]
0x18002eca9  movzx   r14d, word ptr [r13+1Ah]
0x18002ecae  movzx   r15d, word ptr [r13+18h]
0x18002ecb3  neg     r12d
0x18002ecb6  sbb     r8d, r8d
0x18002ecb9  and     r8d, 2
0x18002ecbd  mov     r12d, 4
0x18002ecc3  add     r8d, r12d
0x18002ecc6  mov     [rsp+350h+var_2E8], ecx
0x18002ecca  mov     [rsp+350h+var_2F0], edx
0x18002ecce  mov     [rsp+350h+var_2F8], r10d
0x18002ecd3  mov     [rsp+350h+var_300], r11d
0x18002ecd8  mov     [rsp+350h+var_308], ebx
0x18002ecdc  mov     dword ptr [rsp+350h+lpdwDisposition], edi
0x18002ece0  mov     dword ptr [rsp+350h+phkResult], eax
0x18002ece4  mov     dword ptr [rsp+350h+lpSecurityAttributes], esi
0x18002ece8  mov     [rsp+350h+samDesired], r14d
0x18002eced  mov     [rsp+350h+dwOptions], r15d
0x18002ecf2  mov     r9d, [r13+14h]
0x18002ecf6  lea     rdx, aNetworkingDhcp; "Networking\\Dhcp\\Client%u\\{%08x-%04x-"...
0x18002ecfd  lea     rcx, [rbp+250h+SubKey]
0x18002ed01  call    ??$swprintf_s@$0BAE@@@YAHAEAY0BAE@_WPEB_WZZ; swprintf_s<260>(wchar_t (&)[260],wchar_t const *,...)
0x18002ed06  mov     rbx, [rbp+250h+hKey]
0x18002ed0a  xor     edi, edi
0x18002ed0c  test    rbx, rbx
0x18002ed0f  jz      short loc_18002ED2E
0x18002ed11  lea     rcx, [rsp+350h+var_2E0]; this
0x18002ed16  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002ed1b  mov     rcx, rbx; hKey
0x18002ed1e  call    cs:__imp_RegCloseKey
0x18002ed24  lea     rcx, [rsp+350h+var_2E0]; this
0x18002ed29  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002ed2e  mov     [rbp+250h+hKey], rdi
0x18002ed32  mov     [rsp+350h+lpdwDisposition], rdi; lpdwDisposition
0x18002ed37  lea     rax, [rbp+250h+hKey]
0x18002ed3b  mov     [rsp+350h+phkResult], rax; phkResult
0x18002ed40  mov     [rsp+350h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18002ed45  mov     [rsp+350h+samDesired], 2; samDesired
0x18002ed4d  mov     [rsp+350h+dwOptions], edi; dwOptions
0x18002ed51  xor     r9d, r9d; lpClass
0x18002ed54  xor     r8d, r8d; Reserved
0x18002ed57  lea     rdx, [rbp+250h+SubKey]; lpSubKey
0x18002ed5b  mov     rcx, [rsp+350h+var_2D8]; hKey
0x18002ed60  call    cs:__imp_RegCreateKeyExW
0x18002ed66  mov     ebx, eax
0x18002ed68  test    eax, eax
0x18002ed6a  jz      short loc_18002ED7D
0x18002ed6c  mov     rcx, [rbp+250h+hKey]; hKey
0x18002ed70  test    rcx, rcx
0x18002ed73  jz      short loc_18002EDB3
0x18002ed75  call    cs:__imp_RegCloseKey
0x18002ed7b  jmp     short loc_18002EDB3
0x18002ed7d  mov     [rsp+350h+samDesired], r12d; cbData
0x18002ed82  lea     rax, [rbp+250h+Data]
0x18002ed86  mov     qword ptr [rsp+350h+dwOptions], rax; lpData
0x18002ed8b  mov     r9d, r12d; dwType
0x18002ed8e  xor     r8d, r8d; Reserved
0x18002ed91  lea     rdx, aEnabledhcp; "EnableDHCP"
0x18002ed98  mov     rcx, [rbp+250h+hKey]; hKey
0x18002ed9c  call    cs:__imp_RegSetValueExW
0x18002eda2  mov     ebx, eax
0x18002eda4  test    eax, eax
0x18002eda6  jnz     short loc_18002EDAA
0x18002eda8  mov     ebx, edi
0x18002edaa  lea     rcx, [rbp+250h+hKey]
0x18002edae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002edb3  mov     eax, ebx
0x18002edb5  mov     rcx, [rbp+250h+var_50]
0x18002edbc  xor     rcx, rsp; StackCookie
0x18002edbf  call    __security_check_cookie
0x18002edc4  add     rsp, 318h
0x18002edcb  pop     r15
0x18002edcd  pop     r14
0x18002edcf  pop     r13
0x18002edd1  pop     r12
0x18002edd3  pop     rdi
0x18002edd4  pop     rsi
0x18002edd5  pop     rbx
0x18002edd6  pop     rbp
0x18002edd7  retn
```
