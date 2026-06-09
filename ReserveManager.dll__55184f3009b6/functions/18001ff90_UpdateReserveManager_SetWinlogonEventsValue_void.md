# UpdateReserveManager::SetWinlogonEventsValue(void)

- ea: `0x18001ff90`
- end: `0x180020150`
- name: `?SetWinlogonEventsValue@UpdateReserveManager@@AEAAJXZ`
- size: `448`
- prototype: `__int64 __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001bd30`
- `0x18001c23c`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x18001ff90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002007a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002007a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020124`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fffb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020070`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002011a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020070`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002011a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800200c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800200c9`

## string_xrefs

- `0x18002000b`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800200d5`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001fff0`: `Control\Winlogon\Notifications\Components\TrustedInstaller`
- `0x180020016`: `UpdateReserveManager::SetWinlogonEventsValue`
- `0x1800200e0`: `UpdateReserveManager::SetWinlogonEventsValue`
- `0x180020029`: `::RegCreateKeyExW(m_CurrentControlSetKey, L"Control\\Winlogon\\Notifications\\Components\\TrustedInstaller", 0, nullptr, (0x00000004L), ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | ((((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))), nullptr, &WinlogonKey, nullptr)`
- `0x18002008e`: `CreateSession`
- `0x1800200f3`: `::RegSetValueExW(WinlogonKey, L"Events", 0, ( 1ul ), reinterpret_cast<LPBYTE>(&szCreateSession), sizeof(szCreateSession))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::SetWinlogonEventsValue(HKEY *this)
{
  int v1; // ebx
  const char *v2; // rax
  const char *v4; // [rsp+58h] [rbp-9h] BYREF
  const char *v5; // [rsp+60h] [rbp-1h]
  __int64 v6; // [rsp+68h] [rbp+7h]
  const char *v7; // [rsp+70h] [rbp+Fh]
  __int64 v8; // [rsp+78h] [rbp+17h]
  HKEY hKey; // [rsp+80h] [rbp+1Fh] BYREF
  BYTE Data[32]; // [rsp+88h] [rbp+27h] BYREF

  v8 = -2;
  hKey = 0;
  v1 = RegCreateKeyExW(
         this[15],
         L"Control\\Winlogon\\Notifications\\Components\\TrustedInstaller",
         0,
         0,
         4u,
         0x2001Fu,
         0,
         &hKey,
         0);
  if ( v1 )
  {
    v4 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v5 = "UpdateReserveManager::SetWinlogonEventsValue";
    v6 = 4162;
    v2 = "::RegCreateKeyExW(m_CurrentControlSetKey, L\"Control\\\\Winlogon\\\\Notifications\\\\Components\\\\TrustedInsta"
         "ller\", 0, nullptr, (0x00000004L), ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))) | (("
         "((0x00020000L)) | (0x0002) | (0x0004)) & (~(0x00100000L))), nullptr, &WinlogonKey, nullptr)";
LABEL_3:
    v7 = v2;
    if ( v1 > 0 )
      v1 = (unsigned __int16)v1 | 0x80070000;
    RtlReportErrorOrigination(&v4, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v1);
    if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL )
    {
      if ( RegCloseKey(hKey) )
      {
        GetLastError();
        __fastfail(7u);
      }
    }
    return (unsigned int)v1;
  }
  *(_OWORD *)Data = *(_OWORD *)L"CreateSession";
  *(_OWORD *)&Data[12] = *(_OWORD *)L"Session";
  v1 = RegSetValueExW(hKey, L"Events", 0, 1u, Data, 0x1Cu);
  if ( v1 )
  {
    v4 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v5 = "UpdateReserveManager::SetWinlogonEventsValue";
    v6 = 4170;
    v2 = "::RegSetValueExW(WinlogonKey, L\"Events\", 0, ( 1ul ), reinterpret_cast<LPBYTE>(&szCreateSession), sizeof(szCreateSession))";
    goto LABEL_3;
  }
  if ( hKey && ((unsigned __int64)hKey & 0xFFFFFFFF80000000uLL) != 0xFFFFFFFF80000000uLL && RegCloseKey(hKey) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ff90  mov     r11, rsp
0x18001ff93  push    rbp
0x18001ff94  lea     rbp, [r11-5Fh]
0x18001ff98  sub     rsp, 0B0h
0x18001ff9f  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x18001ffa7  mov     [r11+10h], rbx
0x18001ffab  mov     rax, cs:__security_cookie
0x18001ffb2  xor     rax, rsp
0x18001ffb5  mov     [rbp+57h+var_10], rax
0x18001ffb9  mov     [rbp+57h+hKey], 0
0x18001ffc1  mov     qword ptr [r11-78h], 0
0x18001ffc9  lea     rax, [rbp+57h+hKey]
0x18001ffcd  mov     [r11-80h], rax
0x18001ffd1  mov     qword ptr [rsp+30h], 0; lpSecurityAttributes
0x18001ffda  mov     [rsp+0B0h+samDesired], 2001Fh; samDesired
0x18001ffe2  mov     [rsp+0B0h+dwOptions], 4; dwOptions
0x18001ffea  xor     r9d, r9d; lpClass
0x18001ffed  xor     r8d, r8d; Reserved
0x18001fff0  lea     rdx, aControlWinlogo; "Control\\Winlogon\\Notifications\\Compo"...
0x18001fff7  mov     rcx, [rcx+78h]; hKey
0x18001fffb  call    cs:__imp_RegCreateKeyExW
0x180020001  mov     ebx, eax
0x180020003  test    eax, eax
0x180020005  jz      loc_18002008E
0x18002000b  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180020012  mov     [rbp+57h+var_60], rax
0x180020016  lea     rax, aUpdatereservem_48; "UpdateReserveManager::SetWinlogonEvents"...
0x18002001d  mov     [rbp+57h+var_58], rax
0x180020021  mov     [rbp+57h+var_50], 1042h
0x180020029  lea     rax, aRegcreatekeyex; "::RegCreateKeyExW(m_CurrentControlSetKe"...
0x180020030  test    ebx, ebx
0x180020032  mov     [rbp+57h+var_48], rax
0x180020036  jle     short loc_180020041
0x180020038  movzx   ebx, bx
0x18002003b  or      ebx, 80070000h
0x180020041  mov     r8d, ebx
0x180020044  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18002004b  lea     rcx, [rbp+57h+var_60]
0x18002004f  call    RtlReportErrorOrigination
0x180020054  nop
0x180020055  mov     rcx, [rbp+57h+hKey]; hKey
0x180020059  test    rcx, rcx
0x18002005c  jz      short loc_180020087
0x18002005e  mov     rax, rcx
0x180020061  mov     rdx, 0FFFFFFFF80000000h
0x180020068  and     rax, rdx
0x18002006b  cmp     rax, rdx
0x18002006e  jz      short loc_180020087
0x180020070  call    cs:__imp_RegCloseKey
0x180020076  test    eax, eax
0x180020078  jz      short loc_180020087
0x18002007a  call    cs:__imp_GetLastError
0x180020080  mov     ecx, 7
0x180020085  int     29h; Win8: RtlFailFast(ecx)
0x180020087  mov     eax, ebx
0x180020089  jmp     loc_180020133
0x18002008e  movups  xmm0, xmmword ptr cs:aCreatesession; "CreateSession"
0x180020095  movups  xmmword ptr [rbp+57h+Data], xmm0
0x180020099  movups  xmm1, xmmword ptr cs:aCreatesession+0Ch; "Session"
0x1800200a0  movups  xmmword ptr [rbp+57h+Data+0Ch], xmm1
0x1800200a4  mov     [rsp+0B0h+samDesired], 1Ch; cbData
0x1800200ac  lea     rax, [rbp+57h+Data]
0x1800200b0  mov     qword ptr [rsp+0B0h+dwOptions], rax; lpData
0x1800200b5  mov     r9d, 1; dwType
0x1800200bb  xor     r8d, r8d; Reserved
0x1800200be  lea     rdx, aEvents; "Events"
0x1800200c5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800200c9  call    cs:__imp_RegSetValueExW
0x1800200cf  mov     ebx, eax
0x1800200d1  test    eax, eax
0x1800200d3  jz      short loc_1800200FF
0x1800200d5  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800200dc  mov     [rbp+57h+var_60], rax
0x1800200e0  lea     rax, aUpdatereservem_48; "UpdateReserveManager::SetWinlogonEvents"...
0x1800200e7  mov     [rbp+57h+var_58], rax
0x1800200eb  mov     [rbp+57h+var_50], 104Ah
0x1800200f3  lea     rax, aRegsetvalueexw_2; "::RegSetValueExW(WinlogonKey, L\"Events"...
0x1800200fa  jmp     loc_180020030
0x1800200ff  mov     rcx, [rbp+57h+hKey]; hKey
0x180020103  test    rcx, rcx
0x180020106  jz      short loc_180020131
0x180020108  mov     rax, rcx
0x18002010b  mov     rdx, 0FFFFFFFF80000000h
0x180020112  and     rax, rdx
0x180020115  cmp     rax, rdx
0x180020118  jz      short loc_180020131
0x18002011a  call    cs:__imp_RegCloseKey
0x180020120  test    eax, eax
0x180020122  jz      short loc_180020131
0x180020124  call    cs:__imp_GetLastError
0x18002012a  mov     ecx, 7
0x18002012f  int     29h; Win8: RtlFailFast(ecx)
0x180020131  xor     eax, eax
0x180020133  mov     rcx, [rbp+57h+var_10]
0x180020137  xor     rcx, rsp; StackCookie
0x18002013a  call    __security_check_cookie
0x18002013f  mov     rbx, [rsp+0B0h+arg_8]
0x180020147  add     rsp, 0B0h
0x18002014e  pop     rbp
0x18002014f  retn
```
