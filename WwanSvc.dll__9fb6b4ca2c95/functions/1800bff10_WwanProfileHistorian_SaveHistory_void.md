# WwanProfileHistorian::SaveHistory(void)

- ea: `0x1800bff10`
- end: `0x1800c009b`
- name: `?SaveHistory@WwanProfileHistorian@@QEAAJXZ`
- size: `395`
- prototype: `__int64 __fastcall(WwanProfileHistorian *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800b7f88`

## callees

- `0x1800bd1b4`
- `0x1800bd1dc`
- `0x1800bff10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bff61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bff61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c0048`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c0048`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bffee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bffee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0058`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c0058`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c0030`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c0030`
- `MobileNetworking!GetPersistentRegPath` at `0x1800bff9d`
- `MobileNetworking!GetPersistentRegPath` at `0x1800bff9d`

## pseudocode

```c
__int64 __fastcall WwanProfileHistorian::SaveHistory(WwanProfileHistorian *this)
{
  LPCRITICAL_SECTION v1; // rdi
  signed int v2; // ebx
  int PersistentRegPath; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  WwanProfileHistorian *v7; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  v7 = this;
  v1 = qword_180152B88;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_59efe20e95083d54484ef368743a0c87_Traceguids);
  hKey = 0;
  EnterCriticalSection(v1);
  if ( LOBYTE(v1[1].DebugInfo) )
  {
    if ( WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot )
      goto LABEL_10;
    LODWORD(v7) = 260;
    PersistentRegPath = GetPersistentRegPath(
                          0,
                          L"MobileBroadbandAccounts\\Data",
                          &v7,
                          &WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot);
    v2 = PersistentRegPath;
    if ( PersistentRegPath > 0 )
      v2 = (unsigned __int16)PersistentRegPath | 0x80070000;
    if ( v2 >= 0 )
    {
LABEL_10:
      v4 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             &WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot,
             0,
             0,
             0,
             0x20006u,
             0,
             &hKey,
             0);
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      if ( v2 >= 0 )
      {
        v5 = RegSetValueExW(
               hKey,
               L"ProfileHistory",
               0,
               3u,
               *(const BYTE **)&v1[1].LockCount,
               536 * LODWORD(v1[1].OwningThread));
        v2 = v5;
        if ( v5 > 0 )
          v2 = (unsigned __int16)v5 | 0x80070000;
      }
    }
  }
  else
  {
    v2 = -2147019873;
  }
  LeaveCriticalSection(v1);
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_59efe20e95083d54484ef368743a0c87_Traceguids,
      (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800bff10  mov     [rsp+arg_10], rbx
0x1800bff15  mov     [rsp+arg_0], rcx
0x1800bff1a  push    rsi
0x1800bff1b  push    rdi
0x1800bff1c  push    r14
0x1800bff1e  sub     rsp, 50h
0x1800bff22  mov     rdi, cs:qword_180152B88
0x1800bff29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bff30  lea     r14, WPP_GLOBAL_Control
0x1800bff37  cmp     rcx, r14
0x1800bff3a  jz      short loc_1800BFF57
0x1800bff3c  test    byte ptr [rcx+1Ch], 10h
0x1800bff40  jz      short loc_1800BFF57
0x1800bff42  mov     rcx, [rcx+10h]
0x1800bff46  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x1800bff4d  mov     edx, 11h
0x1800bff52  call    WPP_SF_
0x1800bff57  xor     esi, esi
0x1800bff59  mov     rcx, rdi; lpCriticalSection
0x1800bff5c  mov     [rsp+68h+hKey], rsi
0x1800bff61  call    cs:__imp_EnterCriticalSection
0x1800bff67  cmp     [rdi+28h], sil
0x1800bff6b  jnz     short loc_1800BFF77
0x1800bff6d  mov     ebx, 8007139Fh
0x1800bff72  jmp     loc_1800C0045
0x1800bff77  cmp     cs:?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA, si; ushort near * WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot
0x1800bff7e  jnz     short loc_1800BFFBA
0x1800bff80  lea     r9, ?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA; ushort near * WwanProfileHistorian::m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot
0x1800bff87  mov     dword ptr [rsp+68h+arg_0], 104h
0x1800bff8f  lea     r8, [rsp+68h+arg_0]
0x1800bff94  xor     ecx, ecx
0x1800bff96  lea     rdx, aMobilebroadban_0; "MobileBroadbandAccounts\\Data"
0x1800bff9d  call    cs:__imp_GetPersistentRegPath
0x1800bffa3  mov     ebx, eax
0x1800bffa5  test    eax, eax
0x1800bffa7  jle     short loc_1800BFFB2
0x1800bffa9  movzx   ebx, ax
0x1800bffac  or      ebx, 80070000h
0x1800bffb2  test    ebx, ebx
0x1800bffb4  js      loc_1800C0045
0x1800bffba  mov     [rsp+68h+lpdwDisposition], rsi; lpdwDisposition
0x1800bffbf  lea     rax, [rsp+68h+hKey]
0x1800bffc4  mov     [rsp+68h+phkResult], rax; phkResult
0x1800bffc9  lea     rdx, ?m_pszPersistentMobileBroadbandAccountsAccountsRegistryRoot@WwanProfileHistorian@@0PAGA; lpSubKey
0x1800bffd0  mov     [rsp+68h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800bffd5  xor     r9d, r9d; lpClass
0x1800bffd8  mov     [rsp+68h+samDesired], 20006h; samDesired
0x1800bffe0  xor     r8d, r8d; Reserved
0x1800bffe3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bffea  mov     [rsp+68h+dwOptions], esi; dwOptions
0x1800bffee  call    cs:__imp_RegCreateKeyExW
0x1800bfff4  mov     ebx, eax
0x1800bfff6  test    eax, eax
0x1800bfff8  jle     short loc_1800C0003
0x1800bfffa  movzx   ebx, ax
0x1800bfffd  or      ebx, 80070000h
0x1800c0003  test    ebx, ebx
0x1800c0005  js      short loc_1800C0045
0x1800c0007  imul    eax, [rdi+38h], 218h
0x1800c000e  lea     rdx, aProfilehistory; "ProfileHistory"
0x1800c0015  mov     rcx, [rsp+68h+hKey]; hKey
0x1800c001a  mov     r9d, 3; dwType
0x1800c0020  xor     r8d, r8d; Reserved
0x1800c0023  mov     [rsp+68h+samDesired], eax; cbData
0x1800c0027  mov     rax, [rdi+30h]
0x1800c002b  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800c0030  call    cs:__imp_RegSetValueExW
0x1800c0036  mov     ebx, eax
0x1800c0038  test    eax, eax
0x1800c003a  jle     short loc_1800C0045
0x1800c003c  movzx   ebx, ax
0x1800c003f  or      ebx, 80070000h
0x1800c0045  mov     rcx, rdi; lpCriticalSection
0x1800c0048  call    cs:__imp_LeaveCriticalSection
0x1800c004e  mov     rcx, [rsp+68h+hKey]; hKey
0x1800c0053  test    rcx, rcx
0x1800c0056  jz      short loc_1800C005E
0x1800c0058  call    cs:__imp_RegCloseKey
0x1800c005e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c0065  cmp     rcx, r14
0x1800c0068  jz      short loc_1800C0088
0x1800c006a  test    byte ptr [rcx+1Ch], 10h
0x1800c006e  jz      short loc_1800C0088
0x1800c0070  mov     rcx, [rcx+10h]
0x1800c0074  lea     r8, WPP_59efe20e95083d54484ef368743a0c87_Traceguids
0x1800c007b  mov     edx, 12h
0x1800c0080  mov     r9d, ebx
0x1800c0083  call    WPP_SF_d
0x1800c0088  mov     eax, ebx
0x1800c008a  mov     rbx, [rsp+68h+arg_10]
0x1800c0092  add     rsp, 50h
0x1800c0096  pop     r14
0x1800c0098  pop     rdi
0x1800c0099  pop     rsi
0x1800c009a  retn
```
