# _dynamic_initializer_for___breakpoint__

- ea: `0x180001110`
- end: `0x18000123d`
- name: `_dynamic_initializer_for___breakpoint__`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001110`
- `0x18001662c`
- `0x1800168f4`
- `0x180049b50`
- `0x18004ad26`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800011bf`
- `KERNEL32!GetCurrentProcessId` at `0x1800011bf`
- `KERNEL32!IsDebuggerPresent` at `0x180001205`
- `KERNEL32!IsDebuggerPresent` at `0x180001205`
- `KERNEL32!OutputDebugStringW` at `0x1800011f4`
- `KERNEL32!OutputDebugStringW` at `0x1800011f4`
- `KERNEL32!Sleep` at `0x1800011ff`
- `KERNEL32!Sleep` at `0x1800011ff`
- `KERNEL32!DebugBreak` at `0x18000120f`
- `KERNEL32!DebugBreak` at `0x18000120f`
- `ADVAPI32!RegCloseKey` at `0x18000121f`
- `ADVAPI32!RegCloseKey` at `0x18000121f`
- `ADVAPI32!RegQueryValueExW` at `0x180001196`
- `ADVAPI32!RegQueryValueExW` at `0x180001196`

## pseudocode

```c
void __fastcall dynamic_initializer_for___breakpoint__(__int64 a1, HKEY a2)
{
  int v2; // eax
  HKEY v3; // rcx
  HKEY hKey[3]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD Type[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR OutputString[1024]; // [rsp+60h] [rbp-A0h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v2 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a2, L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub\\Debug");
  v3 = hKey[0];
  if ( !v2 )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey[0], L"CollectorBridge", 0, Type, Data, &cbData) && Type[0] == 4 )
    {
      if ( *(_DWORD *)Data )
      {
        memset_0(OutputString, 0, sizeof(OutputString));
        GetCurrentProcessId();
        _snwprintf_s<1024>(OutputString, 0x3FFu, (wchar_t *)L"DiagnosticsHub - DebugBreak - %s - Attach to %d");
        if ( *(_DWORD *)Data == 2 )
        {
          while ( !IsDebuggerPresent() )
          {
            OutputDebugStringW(OutputString);
            Sleep(0x3E8u);
          }
          DebugBreak();
        }
      }
    }
    v3 = hKey[0];
  }
  if ( v3 )
    RegCloseKey(v3);
}

```

## disassembly

```asm
0x180001110  push    rbp
0x180001112  lea     rbp, [rsp-770h]
0x18000111a  sub     rsp, 870h
0x180001121  mov     rax, cs:__security_cookie
0x180001128  xor     rax, rsp
0x18000112b  mov     [rbp+770h+var_10], rax
0x180001132  lea     r8, aSoftwareMicros; "Software\\Microsoft\\VisualStudio\\Diag"...
0x180001139  mov     [rsp+870h+var_838], 0
0x180001142  lea     rcx, [rsp+870h+hKey]; this
0x180001147  mov     [rsp+870h+hKey], 0
0x180001150  mov     [rsp+870h+var_830], 0
0x180001159  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000115e  mov     rcx, [rsp+870h+hKey]; hKey
0x180001163  test    eax, eax
0x180001165  jnz     loc_18000121A
0x18000116b  lea     rax, [rsp+870h+cbData]
0x180001170  mov     [rsp+870h+cbData], 4
0x180001178  mov     [rsp+870h+lpcbData], rax; lpcbData
0x18000117d  lea     r9, [rsp+870h+Type]; lpType
0x180001182  lea     rax, [rsp+870h+Data]
0x180001187  xor     r8d, r8d; lpReserved
0x18000118a  lea     rdx, ValueName; "CollectorBridge"
0x180001191  mov     [rsp+870h+lpData], rax; lpData
0x180001196  call    cs:__imp_RegQueryValueExW
0x18000119c  test    eax, eax
0x18000119e  jnz     short loc_180001215
0x1800011a0  cmp     [rsp+870h+Type], 4
0x1800011a5  jnz     short loc_180001215
0x1800011a7  cmp     dword ptr [rsp+870h+Data], eax
0x1800011ab  jz      short loc_180001215
0x1800011ad  xor     edx, edx; Val
0x1800011af  lea     rcx, [rsp+870h+OutputString]; void *
0x1800011b4  mov     r8d, 800h; Size
0x1800011ba  call    memset_0
0x1800011bf  call    cs:__imp_GetCurrentProcessId
0x1800011c5  lea     r9, ValueName; "CollectorBridge"
0x1800011cc  mov     edx, 3FFh; MaxCount
0x1800011d1  lea     r8, aDiagnosticshub_3; "DiagnosticsHub - DebugBreak - %s - Atta"...
0x1800011d8  mov     dword ptr [rsp+870h+lpData], eax
0x1800011dc  lea     rcx, [rsp+870h+OutputString]; Buffer
0x1800011e1  call    ??$_snwprintf_s@$0EAA@@@YAHAEAY0EAA@G_KPEBGZZ; _snwprintf_s<1024>(ushort (&)[1024],unsigned __int64,ushort const *,...)
0x1800011e6  cmp     dword ptr [rsp+870h+Data], 2
0x1800011eb  jnz     short loc_180001215
0x1800011ed  jmp     short loc_180001205
0x1800011ef  lea     rcx, [rsp+870h+OutputString]; lpOutputString
0x1800011f4  call    cs:__imp_OutputDebugStringW
0x1800011fa  mov     ecx, 3E8h; dwMilliseconds
0x1800011ff  call    cs:__imp_Sleep
0x180001205  call    cs:__imp_IsDebuggerPresent
0x18000120b  test    eax, eax
0x18000120d  jz      short loc_1800011EF
0x18000120f  call    cs:__imp_DebugBreak
0x180001215  mov     rcx, [rsp+870h+hKey]; hKey
0x18000121a  test    rcx, rcx
0x18000121d  jz      short loc_180001225
0x18000121f  call    cs:__imp_RegCloseKey
0x180001225  mov     rcx, [rbp+770h+var_10]
0x18000122c  xor     rcx, rsp; StackCookie
0x18000122f  call    __security_check_cookie
0x180001234  add     rsp, 870h
0x18000123b  pop     rbp
0x18000123c  retn
```
