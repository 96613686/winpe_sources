# Jot::RunNotebookRegistryMigration(void)

- ea: `0x1400ce06c`
- end: `0x1400ce2dd`
- name: `?RunNotebookRegistryMigration@Jot@@YAXXZ`
- size: `625`
- prototype: `void __fastcall(Jot *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400121c8`

## callees

- `0x14003f250`
- `0x1400408d0`
- `0x140056ac0`
- `0x140085570`
- `0x1400ce06c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1400ce17a`
- `ADVAPI32!RegQueryValueExW` at `0x1400ce17a`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce0f0`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce114`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce138`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce20d`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce231`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce255`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce0f0`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce114`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce138`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce20d`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce231`
- `ADVAPI32!RegOpenKeyExW` at `0x1400ce255`
- `ADVAPI32!RegCloseKey` at `0x1400ce1a7`
- `ADVAPI32!RegCloseKey` at `0x1400ce1b7`
- `ADVAPI32!RegCloseKey` at `0x1400ce293`
- `ADVAPI32!RegCloseKey` at `0x1400ce2a3`
- `ADVAPI32!RegCloseKey` at `0x1400ce2b3`
- `ADVAPI32!RegCloseKey` at `0x1400ce1a7`
- `ADVAPI32!RegCloseKey` at `0x1400ce1b7`
- `ADVAPI32!RegCloseKey` at `0x1400ce293`
- `ADVAPI32!RegCloseKey` at `0x1400ce2a3`
- `ADVAPI32!RegCloseKey` at `0x1400ce2b3`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x1400ce197`
- `Mso20Win32Client!__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z` at `0x1400ce197`
- `Mso20Win32Client!__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x1400ce0b2`
- `Mso20Win32Client!__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x1400ce1d2`
- `Mso20Win32Client!__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x1400ce0b2`
- `Mso20Win32Client!__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x1400ce1d2`
- `Mso20Win32Client!__imp_?MsoRegCreateKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x1400ce26b`
- `Mso20Win32Client!__imp_?MsoRegCreateKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x1400ce26b`

## string_xrefs

- `0x1400ce0e6`: `Software\Microsoft\Office\15.0\OneNote\Options\Paths\`
- `0x1400ce203`: `Software\Microsoft\Office\15.0\OneNote\OpenNotebooks\`
- `0x1400ce12e`: `Software\Microsoft\Office\12.0\OneNote\Options\Paths\`
- `0x1400ce24b`: `Software\Microsoft\Office\12.0\OneNote\OpenNotebooks\`
- `0x1400ce227`: `Software\Microsoft\Office\14.0\OneNote\OpenNotebooks\`
- `0x1400ce10a`: `Software\Microsoft\Office\14.0\OneNote\Options\Paths\`

## pseudocode

```c
void __fastcall Jot::RunNotebookRegistryMigration(Jot *this)
{
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v4; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v5; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Data[2136]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = 0;
  if ( MsoRegOpenKey((const struct _msoreg *)&vmsoridOneNoteQuickNoteSection, &v4) == 2 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Office\\15.0\\OneNote\\Options\\Paths\\",
            0,
            0x20019u,
            &hKey)
      || !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Office\\14.0\\OneNote\\Options\\Paths\\",
            0,
            0x20019u,
            &hKey)
      || !RegOpenKeyExW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Office\\12.0\\OneNote\\Options\\Paths\\",
            0,
            0x20019u,
            &hKey) )
    {
      Type = 0;
      cbData[0] = 4168;
      if ( !RegQueryValueExW(hKey, L"UnfiledNotesSection", 0, &Type, (LPBYTE)Data, cbData) && Type == 2 )
        MsoFRegSetWz((const struct _msoreg *)&vmsoridOneNoteQuickNoteSection, Data);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( v4 )
    RegCloseKey(v4);
  v5 = 0;
  if ( MsoRegOpenKey((const struct _msoreg *)&vmsoridOneNoteOpenNotebooksHook, &v5) == 2 )
  {
    hKey = 0;
    *(_QWORD *)cbData = 0;
    if ( (!RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Office\\15.0\\OneNote\\OpenNotebooks\\",
             0,
             0x20019u,
             &hKey)
       || !RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Office\\14.0\\OneNote\\OpenNotebooks\\",
             0,
             0x20019u,
             &hKey)
       || !RegOpenKeyExW(
             HKEY_CURRENT_USER,
             L"Software\\Microsoft\\Office\\12.0\\OneNote\\OpenNotebooks\\",
             0,
             0x20019u,
             &hKey))
      && !MsoRegCreateKey((const struct _msoreg *)&vmsoridOneNoteOpenNotebooksHook, (HKEY *)cbData) )
    {
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(Data);
      Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(Data);
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( *(_QWORD *)cbData )
      RegCloseKey(*(HKEY *)cbData);
  }
  if ( v5 )
    RegCloseKey(v5);
}

```

## disassembly

```asm
0x1400ce06c  mov     [rsp-8+arg_0], rsi
0x1400ce071  mov     [rsp-8+arg_8], rdi
0x1400ce076  push    rbp
0x1400ce077  lea     rbp, [rsp-1020h]
0x1400ce07f  mov     eax, 1120h
0x1400ce084  call    _alloca_probe
0x1400ce089  sub     rsp, rax
0x1400ce08c  mov     rax, cs:__security_cookie
0x1400ce093  xor     rax, rsp
0x1400ce096  mov     [rbp+1020h+var_10], rax
0x1400ce09d  lea     rdx, [rsp+1120h+var_10D8]
0x1400ce0a2  mov     [rsp+1120h+var_10D8], 0
0x1400ce0ab  lea     rcx, ?vmsoridOneNoteQuickNoteSection@@3U_msoreg@@B; _msoreg const vmsoridOneNoteQuickNoteSection
0x1400ce0b2  call    cs:__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z; MsoRegOpenKey(_msoreg const *,HKEY__ * *)
0x1400ce0b8  mov     edi, 20019h
0x1400ce0bd  mov     rsi, 0FFFFFFFF80000001h
0x1400ce0c4  cmp     eax, 2
0x1400ce0c7  jnz     loc_1400CE1AD
0x1400ce0cd  lea     rax, [rsp+1120h+hKey]
0x1400ce0d2  mov     [rsp+1120h+hKey], 0
0x1400ce0db  mov     r9d, edi; samDesired
0x1400ce0de  mov     [rsp+1120h+phkResult], rax; phkResult
0x1400ce0e3  xor     r8d, r8d; ulOptions
0x1400ce0e6  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Office\\15.0\\OneN"...
0x1400ce0ed  mov     rcx, rsi; hKey
0x1400ce0f0  call    cs:__imp_RegOpenKeyExW
0x1400ce0f6  test    eax, eax
0x1400ce0f8  jz      short loc_1400CE142
0x1400ce0fa  lea     rax, [rsp+1120h+hKey]
0x1400ce0ff  mov     r9d, edi; samDesired
0x1400ce102  xor     r8d, r8d; ulOptions
0x1400ce105  mov     [rsp+1120h+phkResult], rax; phkResult
0x1400ce10a  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Office\\14.0\\OneN"...
0x1400ce111  mov     rcx, rsi; hKey
0x1400ce114  call    cs:__imp_RegOpenKeyExW
0x1400ce11a  test    eax, eax
0x1400ce11c  jz      short loc_1400CE142
0x1400ce11e  lea     rax, [rsp+1120h+hKey]
0x1400ce123  mov     r9d, edi; samDesired
0x1400ce126  xor     r8d, r8d; ulOptions
0x1400ce129  mov     [rsp+1120h+phkResult], rax; phkResult
0x1400ce12e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Office\\12.0\\OneN"...
0x1400ce135  mov     rcx, rsi; hKey
0x1400ce138  call    cs:__imp_RegOpenKeyExW
0x1400ce13e  test    eax, eax
0x1400ce140  jnz     short loc_1400CE19D
0x1400ce142  mov     rcx, [rsp+1120h+hKey]; hKey
0x1400ce147  lea     rax, [rsp+1120h+cbData]
0x1400ce14c  mov     [rsp+1120h+lpcbData], rax; lpcbData
0x1400ce151  lea     r9, [rsp+1120h+Type]; lpType
0x1400ce156  lea     rax, [rsp+1120h+Data]
0x1400ce15b  mov     [rsp+1120h+Type], 0
0x1400ce163  xor     r8d, r8d; lpReserved
0x1400ce166  mov     [rsp+1120h+phkResult], rax; lpData
0x1400ce16b  lea     rdx, aUnfilednotesse; "UnfiledNotesSection"
0x1400ce172  mov     [rsp+1120h+cbData], 1048h
0x1400ce17a  call    cs:__imp_RegQueryValueExW
0x1400ce180  test    eax, eax
0x1400ce182  jnz     short loc_1400CE19D
0x1400ce184  cmp     [rsp+1120h+Type], 2
0x1400ce189  jnz     short loc_1400CE19D
0x1400ce18b  lea     rdx, [rsp+1120h+Data]
0x1400ce190  lea     rcx, ?vmsoridOneNoteQuickNoteSection@@3U_msoreg@@B; _msoreg const vmsoridOneNoteQuickNoteSection
0x1400ce197  call    cs:__imp_?MsoFRegSetWz@@YAHPEBU_msoreg@@PEB_W@Z; MsoFRegSetWz(_msoreg const *,wchar_t const *)
0x1400ce19d  mov     rcx, [rsp+1120h+hKey]; hKey
0x1400ce1a2  test    rcx, rcx
0x1400ce1a5  jz      short loc_1400CE1AD
0x1400ce1a7  call    cs:__imp_RegCloseKey
0x1400ce1ad  mov     rcx, [rsp+1120h+var_10D8]; hKey
0x1400ce1b2  test    rcx, rcx
0x1400ce1b5  jz      short loc_1400CE1BD
0x1400ce1b7  call    cs:__imp_RegCloseKey
0x1400ce1bd  lea     rdx, [rsp+1120h+var_10D0]
0x1400ce1c2  mov     [rsp+1120h+var_10D0], 0
0x1400ce1cb  lea     rcx, ?vmsoridOneNoteOpenNotebooksHook@@3U_msoreg@@B; _msoreg const vmsoridOneNoteOpenNotebooksHook
0x1400ce1d2  call    cs:__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z; MsoRegOpenKey(_msoreg const *,HKEY__ * *)
0x1400ce1d8  cmp     eax, 2
0x1400ce1db  jnz     loc_1400CE2A9
0x1400ce1e1  lea     rax, [rsp+1120h+hKey]
0x1400ce1e6  mov     [rsp+1120h+hKey], 0
0x1400ce1ef  mov     r9d, edi; samDesired
0x1400ce1f2  mov     [rsp+1120h+phkResult], rax; phkResult
0x1400ce1f7  xor     r8d, r8d; ulOptions
0x1400ce1fa  mov     qword ptr [rsp+1120h+cbData], 0
0x1400ce203  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Office\\15.0\\OneN"...
0x1400ce20a  mov     rcx, rsi; hKey
0x1400ce20d  call    cs:__imp_RegOpenKeyExW
0x1400ce213  test    eax, eax
0x1400ce215  jz      short loc_1400CE25F
0x1400ce217  lea     rax, [rsp+1120h+hKey]
0x1400ce21c  mov     r9d, edi; samDesired
0x1400ce21f  xor     r8d, r8d; ulOptions
0x1400ce222  mov     [rsp+1120h+phkResult], rax; phkResult
0x1400ce227  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Office\\14.0\\OneN"...
0x1400ce22e  mov     rcx, rsi; hKey
0x1400ce231  call    cs:__imp_RegOpenKeyExW
0x1400ce237  test    eax, eax
0x1400ce239  jz      short loc_1400CE25F
0x1400ce23b  lea     rax, [rsp+1120h+hKey]
0x1400ce240  mov     r9d, edi; samDesired
0x1400ce243  xor     r8d, r8d; ulOptions
0x1400ce246  mov     [rsp+1120h+phkResult], rax; phkResult
0x1400ce24b  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Office\\12.0\\OneN"...
0x1400ce252  mov     rcx, rsi; hKey
0x1400ce255  call    cs:__imp_RegOpenKeyExW
0x1400ce25b  test    eax, eax
0x1400ce25d  jnz     short loc_1400CE289
0x1400ce25f  lea     rdx, [rsp+1120h+cbData]
0x1400ce264  lea     rcx, ?vmsoridOneNoteOpenNotebooksHook@@3U_msoreg@@B; _msoreg const vmsoridOneNoteOpenNotebooksHook
0x1400ce26b  call    cs:__imp_?MsoRegCreateKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z; MsoRegCreateKey(_msoreg const *,HKEY__ * *)
0x1400ce271  test    eax, eax
0x1400ce273  jnz     short loc_1400CE289
0x1400ce275  lea     rcx, [rsp+1120h+Data]
0x1400ce27a  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x1400ce27f  lea     rcx, [rsp+1120h+Data]
0x1400ce284  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0ICF@@2@@MsoCF@@$0ICE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2085>>,2084>(void)
0x1400ce289  mov     rcx, [rsp+1120h+hKey]; hKey
0x1400ce28e  test    rcx, rcx
0x1400ce291  jz      short loc_1400CE299
0x1400ce293  call    cs:__imp_RegCloseKey
0x1400ce299  mov     rcx, qword ptr [rsp+1120h+cbData]; hKey
0x1400ce29e  test    rcx, rcx
0x1400ce2a1  jz      short loc_1400CE2A9
0x1400ce2a3  call    cs:__imp_RegCloseKey
0x1400ce2a9  mov     rcx, [rsp+1120h+var_10D0]; hKey
0x1400ce2ae  test    rcx, rcx
0x1400ce2b1  jz      short loc_1400CE2B9
0x1400ce2b3  call    cs:__imp_RegCloseKey
0x1400ce2b9  mov     rcx, [rbp+1020h+var_10]
0x1400ce2c0  xor     rcx, rsp; StackCookie
0x1400ce2c3  call    __security_check_cookie
0x1400ce2c8  lea     r11, [rsp+1120h+var_s0]
0x1400ce2d0  mov     rsi, [r11+10h]
0x1400ce2d4  mov     rdi, [r11+18h]
0x1400ce2d8  mov     rsp, r11
0x1400ce2db  pop     rbp
0x1400ce2dc  retn
```
