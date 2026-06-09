# AgentUser::SetSessionConfigId(Windows::AI::IsolationEnvironment::IsolationConfigurationId)

- ea: `0x18003cfc8`
- end: `0x18003d14f`
- name: `?SetSessionConfigId@AgentUser@@QEAAJW4IsolationConfigurationId@IsolationEnvironment@AI@Windows@@@Z`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800238a0`

## callees

- `0x18000a464`
- `0x180011e18`
- `0x18003cfc8`
- `0x1800472d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d035`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003d035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d0fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d085`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003d0fd`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003d0b6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003d0b6`

## string_xrefs

- `0x18003d129`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentuser.cpp`
- `0x18003d110`: `SetIsolationConfigId invalid value %d`
- `0x18003d0d2`: `Failed to set isolation configuration ID in registry, hr: 0x%X`
- `0x18003d065`: `Failed to open registry key, hr: 0x%X`
- `0x18003d0e1`: `Set isolation configuration ID to %d, agent user name '%s'`
- `0x18003d027`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\ConfigIds`
- `0x18003d050`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker\ConfigIds`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AgentUser::SetSessionConfigId(__int64 a1, unsigned int a2)
{
  _QWORD *v4; // r14
  const WCHAR *v5; // rsi
  LSTATUS v6; // eax
  __int64 v7; // rcx
  bool v8; // sf
  int v9; // eax
  unsigned int v10; // ebx
  LSTATUS v11; // eax
  int phkResult; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+10h] BYREF

  v4 = (_QWORD *)(a1 + 144);
  if ( *(_QWORD *)(a1 + 168) > 7u )
    v4 = (_QWORD *)*v4;
  v5 = (const WCHAR *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) > 7u )
    v5 = *(const WCHAR **)v5;
  if ( a2 > 3 )
  {
    Log(3u, L"SetIsolationConfigId invalid value %d", a2);
    v10 = -2147024809;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentuser.cpp",
      (const char *)v10,
      phkResult);
    return v10;
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
    v10 = v9;
    if ( v9 < 0 )
    {
      Log(2u, L"Failed to open registry key, hr: 0x%X", (unsigned int)v9);
      goto LABEL_11;
    }
  }
  Data = a2;
  v11 = RegSetKeyValueW(hKey, 0, v5, 4u, &Data, 4u);
  v10 = v11;
  if ( v11 > 0 )
    v10 = (unsigned __int16)v11 | 0x80070000;
  if ( (v10 & 0x80000000) != 0 )
  {
    Log(2u, L"Failed to set isolation configuration ID in registry, hr: 0x%X", v10);
LABEL_11:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_21;
  }
  Log(4u, L"Set isolation configuration ID to %d, agent user name '%s'", a2, v4);
  if ( hKey )
    RegCloseKey(hKey);
  *(_DWORD *)(a1 + 240) = a2;
  return 0;
}

```

## disassembly

```asm
0x18003cfc8  mov     [rsp+arg_10], rbx
0x18003cfcd  mov     [rsp+arg_18], rbp
0x18003cfd2  push    rsi
0x18003cfd3  push    rdi
0x18003cfd4  push    r14
0x18003cfd6  sub     rsp, 30h
0x18003cfda  mov     edi, edx
0x18003cfdc  mov     rbp, rcx
0x18003cfdf  lea     r14, [rcx+90h]
0x18003cfe6  cmp     qword ptr [r14+18h], 7
0x18003cfeb  jbe     short loc_18003CFF0
0x18003cfed  mov     r14, [r14]
0x18003cff0  lea     rsi, [rcx+50h]
0x18003cff4  cmp     qword ptr [rsi+18h], 7
0x18003cff9  jbe     short loc_18003CFFE
0x18003cffb  mov     rsi, [rsi]
0x18003cffe  mov     ecx, 3; unsigned __int8
0x18003d003  cmp     edi, ecx
0x18003d005  ja      loc_18003D10D
0x18003d00b  mov     [rsp+48h+hKey], 0
0x18003d014  lea     rax, [rsp+48h+hKey]
0x18003d019  mov     [rsp+48h+phkResult], rax; phkResult
0x18003d01e  mov     r9d, 0F003Fh; samDesired
0x18003d024  xor     r8d, r8d; ulOptions
0x18003d027  lea     rdx, ?c_isoBrokerConfigIdRegPath@AgentAccountHelpers@@0QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18003d02e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003d035  call    cs:__imp_RegOpenKeyExW
0x18003d03b  test    eax, eax
0x18003d03d  jle     short loc_18003D049
0x18003d03f  movzx   eax, ax
0x18003d042  or      eax, 80070000h
0x18003d047  test    eax, eax
0x18003d049  jns     short loc_18003D090
0x18003d04b  lea     r8, [rsp+48h+hKey]
0x18003d050  lea     rdx, ?c_isoBrokerConfigIdRegPath@AgentAccountHelpers@@0QB_WB; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x18003d057  call    ?create_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEB_WAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::create_unique_key_nothrow(HKEY__ *,wchar_t const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18003d05c  mov     ebx, eax
0x18003d05e  test    eax, eax
0x18003d060  jns     short loc_18003D090
0x18003d062  mov     r8d, eax
0x18003d065  lea     rdx, aFailedToOpenRe; "Failed to open registry key, hr: 0x%X"
0x18003d06c  mov     ecx, 2; unsigned __int8
0x18003d071  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003d076  nop
0x18003d077  mov     rcx, [rsp+48h+hKey]; hKey
0x18003d07c  test    rcx, rcx
0x18003d07f  jz      loc_18003D121
0x18003d085  call    cs:__imp_RegCloseKey
0x18003d08b  jmp     loc_18003D121
0x18003d090  mov     [rsp+48h+Data], edi
0x18003d094  mov     [rsp+48h+cbData], 4; cbData
0x18003d09c  lea     rax, [rsp+48h+Data]
0x18003d0a1  mov     [rsp+48h+phkResult], rax; lpData
0x18003d0a6  mov     r9d, 4; dwType
0x18003d0ac  mov     r8, rsi; lpValueName
0x18003d0af  xor     edx, edx; lpSubKey
0x18003d0b1  mov     rcx, [rsp+48h+hKey]; hKey
0x18003d0b6  call    cs:__imp_RegSetKeyValueW
0x18003d0bc  mov     ebx, eax
0x18003d0be  test    eax, eax
0x18003d0c0  jle     short loc_18003D0CB
0x18003d0c2  movzx   ebx, ax
0x18003d0c5  or      ebx, 80070000h
0x18003d0cb  test    ebx, ebx
0x18003d0cd  jns     short loc_18003D0DB
0x18003d0cf  mov     r8d, ebx
0x18003d0d2  lea     rdx, aFailedToSetIso; "Failed to set isolation configuration I"...
0x18003d0d9  jmp     short loc_18003D06C
0x18003d0db  mov     r9, r14
0x18003d0de  mov     r8d, edi
0x18003d0e1  lea     rdx, aSetIsolationCo; "Set isolation configuration ID to %d, a"...
0x18003d0e8  mov     ecx, 4; unsigned __int8
0x18003d0ed  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003d0f2  nop
0x18003d0f3  mov     rcx, [rsp+48h+hKey]; hKey
0x18003d0f8  test    rcx, rcx
0x18003d0fb  jz      short loc_18003D103
0x18003d0fd  call    cs:__imp_RegCloseKey
0x18003d103  mov     [rbp+0F0h], edi
0x18003d109  xor     eax, eax
0x18003d10b  jmp     short loc_18003D13C
0x18003d10d  mov     r8d, edi
0x18003d110  lea     rdx, aSetisolationco; "SetIsolationConfigId invalid value %d"
0x18003d117  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003d11c  mov     ebx, 80070057h
0x18003d121  mov     rcx, [rsp+48h]; this
0x18003d126  mov     r9d, ebx; char *
0x18003d129  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003d130  mov     edx, 20Ah; void *
0x18003d135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d13a  mov     eax, ebx
0x18003d13c  mov     rbx, [rsp+48h+arg_10]
0x18003d141  mov     rbp, [rsp+48h+arg_18]
0x18003d146  add     rsp, 30h
0x18003d14a  pop     r14
0x18003d14c  pop     rdi
0x18003d14d  pop     rsi
0x18003d14e  retn
```
