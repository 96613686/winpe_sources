# AgentAccountHelpers2::SetSessionConfigId(wchar_t const *,wchar_t const *,Windows::AI::IsolationEnvironment::Preview::IsolationConfigurationId_Exp2)

- ea: `0x18005acac`
- end: `0x18005ade3`
- name: `?SetSessionConfigId@AgentAccountHelpers2@@SAJPEB_W0W4IsolationConfigurationId_Exp2@Preview@IsolationEnvironment@AI@Windows@@@Z`
- size: `311`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005ef20`
- `0x18005f3bc`

## callees

- `0x180011e18`
- `0x1800472d8`
- `0x18005acac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005acf8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005acf8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ad44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005adbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ad44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005adbb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005ad77`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005ad77`

## string_xrefs

- `0x18005adc5`: `SetIsolationConfigId invalid value %d`
- `0x18005ad90`: `Failed to set isolation configuration ID in registry, hr: 0x%X`
- `0x18005ad25`: `Failed to open registry key, hr: 0x%X`
- `0x18005ad9f`: `Set isolation configuration ID to %d, agent user name '%s'`
- `0x18005acea`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\ConfigIds`
- `0x18005ad13`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\ConfigIds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AgentAccountHelpers2::SetSessionConfigId(const WCHAR *a1, __int64 a2, unsigned int a3)
{
  LSTATUS v6; // eax
  __int64 v7; // rcx
  bool v8; // sf
  signed int v9; // ebx
  LSTATUS v11; // eax
  unsigned int Data; // [rsp+60h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+20h] BYREF

  if ( a3 > 3 )
  {
    Log(3u, L"SetIsolationConfigId invalid value %d");
    return 2147942487LL;
  }
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker\\ConfigIds",
         0,
         0xF003Fu,
         &hKey);
  v8 = v6 < 0;
  if ( v6 > 0 )
    v8 = 1;
  if ( v8 )
  {
    v9 = wil::reg::create_unique_key_nothrow(v7, L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker\\ConfigIds", &hKey);
    if ( v9 < 0 )
    {
      Log(2u, L"Failed to open registry key, hr: 0x%X", (unsigned int)v9);
LABEL_7:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v9;
    }
  }
  Data = a3;
  v11 = RegSetKeyValueW(hKey, 0, a1, 4u, &Data, 4u);
  v9 = v11;
  if ( v11 > 0 )
    v9 = (unsigned __int16)v11 | 0x80070000;
  if ( v9 < 0 )
  {
    Log(2u, L"Failed to set isolation configuration ID in registry, hr: 0x%X", (unsigned int)v9);
    goto LABEL_7;
  }
  Log(4u, L"Set isolation configuration ID to %d, agent user name '%s'", a3, a2);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18005acac  mov     r11, rsp
0x18005acaf  mov     [r11+8], rbx
0x18005acb3  push    rbp
0x18005acb4  push    rsi
0x18005acb5  push    rdi
0x18005acb6  sub     rsp, 30h
0x18005acba  mov     edi, r8d
0x18005acbd  mov     rsi, rdx
0x18005acc0  mov     rbp, rcx
0x18005acc3  mov     ecx, 3; unsigned __int8
0x18005acc8  cmp     r8d, ecx
0x18005accb  ja      loc_18005ADC5
0x18005acd1  mov     qword ptr [r11+20h], 0
0x18005acd9  lea     rax, [r11+20h]
0x18005acdd  mov     [r11-28h], rax
0x18005ace1  mov     r9d, 0F003Fh; samDesired
0x18005ace7  xor     r8d, r8d; ulOptions
0x18005acea  lea     rdx, ?c_isoBrokerConfigIdRegPath@AgentAccountHelpers2@@0QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18005acf1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005acf8  call    cs:__imp_RegOpenKeyExW
0x18005acfe  test    eax, eax
0x18005ad00  jle     short loc_18005AD0C
0x18005ad02  movzx   eax, ax
0x18005ad05  or      eax, 80070000h
0x18005ad0a  test    eax, eax
0x18005ad0c  jns     short loc_18005AD51
0x18005ad0e  lea     r8, [rsp+48h+hKey]
0x18005ad13  lea     rdx, ?c_isoBrokerConfigIdRegPath@AgentAccountHelpers2@@0QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18005ad1a  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18005ad1f  mov     ebx, eax
0x18005ad21  test    eax, eax
0x18005ad23  jns     short loc_18005AD51
0x18005ad25  lea     rdx, aFailedToOpenRe; "Failed to open registry key, hr: 0x%X"
0x18005ad2c  mov     r8d, ebx
0x18005ad2f  mov     ecx, 2; unsigned __int8
0x18005ad34  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005ad39  nop
0x18005ad3a  mov     rcx, [rsp+48h+hKey]; hKey
0x18005ad3f  test    rcx, rcx
0x18005ad42  jz      short loc_18005AD4A
0x18005ad44  call    cs:__imp_RegCloseKey
0x18005ad4a  mov     eax, ebx
0x18005ad4c  jmp     loc_18005ADD6
0x18005ad51  mov     [rsp+48h+Data], edi
0x18005ad55  mov     [rsp+48h+cbData], 4; cbData
0x18005ad5d  lea     rax, [rsp+48h+Data]
0x18005ad62  mov     [rsp+48h+lpData], rax; lpData
0x18005ad67  mov     r9d, 4; dwType
0x18005ad6d  mov     r8, rbp; lpValueName
0x18005ad70  xor     edx, edx; lpSubKey
0x18005ad72  mov     rcx, [rsp+48h+hKey]; hKey
0x18005ad77  call    cs:__imp_RegSetKeyValueW
0x18005ad7d  mov     ebx, eax
0x18005ad7f  test    eax, eax
0x18005ad81  jle     short loc_18005AD8C
0x18005ad83  movzx   ebx, ax
0x18005ad86  or      ebx, 80070000h
0x18005ad8c  test    ebx, ebx
0x18005ad8e  jns     short loc_18005AD99
0x18005ad90  lea     rdx, aFailedToSetIso; "Failed to set isolation configuration I"...
0x18005ad97  jmp     short loc_18005AD2C
0x18005ad99  mov     r9, rsi
0x18005ad9c  mov     r8d, edi
0x18005ad9f  lea     rdx, aSetIsolationCo; "Set isolation configuration ID to %d, a"...
0x18005ada6  mov     ecx, 4; unsigned __int8
0x18005adab  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005adb0  nop
0x18005adb1  mov     rcx, [rsp+48h+hKey]; hKey
0x18005adb6  test    rcx, rcx
0x18005adb9  jz      short loc_18005ADC1
0x18005adbb  call    cs:__imp_RegCloseKey
0x18005adc1  xor     eax, eax
0x18005adc3  jmp     short loc_18005ADD6
0x18005adc5  lea     rdx, aSetisolationco; "SetIsolationConfigId invalid value %d"
0x18005adcc  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005add1  mov     eax, 80070057h
0x18005add6  mov     rbx, [rsp+48h+arg_0]
0x18005addb  add     rsp, 30h
0x18005addf  pop     rdi
0x18005ade0  pop     rsi
0x18005ade1  pop     rbp
0x18005ade2  retn
```
