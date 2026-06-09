# SpeechMicDiagnostic::CSpeechMicDiagnostic::IsKwsEnabled(bool *)

- ea: `0x180008948`
- end: `0x180008a96`
- name: `?IsKwsEnabled@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJPEA_N@Z`
- size: `334`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800090dc`

## callees

- `0x180005b28`
- `0x180008948`
- `0x18000989c`
- `0x1800098c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800089ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800089ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008a24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008a24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800089da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800089da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008a7f`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::IsKwsEnabled(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this,
        bool *a2)
{
  unsigned int v3; // ebx
  unsigned int v5; // eax
  unsigned int v6; // r8d
  int v7; // eax
  unsigned int v8; // eax
  int phkResult; // [rsp+20h] [rbp-10h]
  unsigned int phkResulta; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  SpeechMicDiagnostic::CSpeechMicDiagnostic *Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = this;
  if ( !a2 )
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return v3;
  }
  *a2 = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Speech_OneCore\\Preferences", 0, 0x20019u, &hKey);
  if ( v5 )
  {
    v7 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x22B, v6, (const char *)v5, phkResulta);
    goto LABEL_6;
  }
  Data = 0;
  LODWORD(Type) = 0;
  cbData = 4;
  v8 = RegQueryValueExW(hKey, L"VoiceActivationOn", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData);
  if ( v8 != 2 )
  {
    if ( v8 )
    {
      v7 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x234,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
             (const char *)v8,
             (unsigned int)"RegQueryValueEx - %ls",
             (const char *)L"VoiceActivationOn");
LABEL_6:
      v3 = v7;
      if ( hKey )
        RegCloseKey(hKey);
      return v3;
    }
    if ( (_DWORD)Type == 4 && Data )
      *a2 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180008948  mov     [rsp-18h+Type], rcx
0x18000894d  push    rbp
0x18000894e  push    rbx
0x18000894f  push    rsi
0x180008950  mov     rbp, rsp
0x180008953  sub     rsp, 30h
0x180008957  mov     rbx, rdx
0x18000895a  test    rdx, rdx
0x18000895d  jnz     short loc_180008983
0x18000895f  mov     rcx, [rbp+18h]; this
0x180008963  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000896a  mov     ebx, 80004003h
0x18000896f  mov     edx, 224h; void *
0x180008974  mov     r9d, ebx; char *
0x180008977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000897c  mov     eax, ebx
0x18000897e  jmp     loc_180008A8D
0x180008983  mov     byte ptr [rdx], 0
0x180008986  lea     rax, [rbp+hKey]
0x18000898a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Speech_OneCore\\Pr"...
0x180008991  mov     [rsp+30h+phkResult], rax; unsigned int
0x180008996  mov     r9d, 20019h; samDesired
0x18000899c  mov     [rbp+hKey], 0
0x1800089a4  xor     r8d, r8d; ulOptions
0x1800089a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800089ae  call    cs:__imp_RegOpenKeyExW
0x1800089b5  nop     dword ptr [rax+rax+00h]
0x1800089ba  test    eax, eax
0x1800089bc  jz      short loc_1800089E8
0x1800089be  mov     rcx, [rbp+18h]; this
0x1800089c2  mov     r9d, eax; char *
0x1800089c5  mov     edx, 22Bh; void *
0x1800089ca  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800089cf  mov     rcx, [rbp+hKey]; hKey
0x1800089d3  mov     ebx, eax
0x1800089d5  test    rcx, rcx
0x1800089d8  jz      short loc_18000897C
0x1800089da  call    cs:__imp_RegCloseKey
0x1800089e1  nop     dword ptr [rax+rax+00h]
0x1800089e6  jmp     short loc_18000897C
0x1800089e8  mov     rcx, [rbp+hKey]; hKey
0x1800089ec  lea     rax, [rbp+cbData]
0x1800089f0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800089f5  lea     rsi, ValueName; "VoiceActivationOn"
0x1800089fc  lea     rax, [rbp+Data]
0x180008a00  mov     [rbp+Data], 0
0x180008a07  lea     r9, [rbp+Type]; lpType
0x180008a0b  mov     [rsp+30h+phkResult], rax; lpData
0x180008a10  xor     r8d, r8d; lpReserved
0x180008a13  mov     dword ptr [rbp+Type], 0
0x180008a1a  mov     rdx, rsi; lpValueName
0x180008a1d  mov     [rbp+cbData], 4
0x180008a24  call    cs:__imp_RegQueryValueExW
0x180008a2b  nop     dword ptr [rax+rax+00h]
0x180008a30  cmp     eax, 2
0x180008a33  jz      short loc_180008A76
0x180008a35  test    eax, eax
0x180008a37  jz      short loc_180008A67
0x180008a39  mov     rcx, [rbp+18h]; this
0x180008a3d  lea     rdx, aRegqueryvaluee; "RegQueryValueEx - %ls"
0x180008a44  mov     [rsp+30h+lpcbData], rsi; char *
0x180008a49  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180008a50  mov     [rsp+30h+phkResult], rdx; unsigned int
0x180008a55  mov     r9d, eax; char *
0x180008a58  mov     edx, 234h; void *
0x180008a5d  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180008a62  jmp     loc_1800089CF
0x180008a67  cmp     dword ptr [rbp+Type], 4
0x180008a6b  jnz     short loc_180008A76
0x180008a6d  cmp     [rbp+Data], 0
0x180008a71  jz      short loc_180008A76
0x180008a73  mov     byte ptr [rbx], 1
0x180008a76  mov     rcx, [rbp+hKey]; hKey
0x180008a7a  test    rcx, rcx
0x180008a7d  jz      short loc_180008A8B
0x180008a7f  call    cs:__imp_RegCloseKey
0x180008a86  nop     dword ptr [rax+rax+00h]
0x180008a8b  xor     eax, eax
0x180008a8d  add     rsp, 30h
0x180008a91  pop     rsi
0x180008a92  pop     rbx
0x180008a93  pop     rbp
0x180008a94  retn
```
