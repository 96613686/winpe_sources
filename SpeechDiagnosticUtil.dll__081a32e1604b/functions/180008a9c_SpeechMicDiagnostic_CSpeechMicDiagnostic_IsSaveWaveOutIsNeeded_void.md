# SpeechMicDiagnostic::CSpeechMicDiagnostic::IsSaveWaveOutIsNeeded(void)

- ea: `0x180008a9c`
- end: `0x180008c4f`
- name: `?IsSaveWaveOutIsNeeded@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c88`

## callees

- `0x180005b28`
- `0x1800087b0`
- `0x180008a9c`
- `0x18000989c`
- `0x1800098c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008c10`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008c10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ad4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ad4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008b47`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008b47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008c33`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::IsSaveWaveOutIsNeeded(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this)
{
  unsigned int v2; // eax
  unsigned int v3; // r8d
  __int64 v4; // rdx
  int v5; // eax
  int inited; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  const BYTE *v10; // rcx
  __int64 v11; // rax
  unsigned int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\MicWiz", 0, 0x2001Fu, &hKey);
  if ( v2 )
  {
    v4 = 368;
LABEL_3:
    v5 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v4, v3, (const char *)v2, phkResult);
LABEL_4:
    inited = v5;
LABEL_5:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)inited;
  }
  Data = 0;
  Type = 0;
  cbData = 4;
  v8 = RegQueryValueExW(hKey, L"SaveWave", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v8 != 2 )
  {
    if ( v8 )
    {
      v5 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x17B,
             (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
             (const char *)v8,
             (unsigned int)"RegQueryValueEx - %ls",
             (const char *)L"SaveWave");
      goto LABEL_4;
    }
    if ( Type != 4 )
    {
      inited = -2147418113;
      v9 = 380;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
        (const char *)(unsigned int)inited,
        phkResulta);
      goto LABEL_5;
    }
    if ( Data )
    {
      *((_BYTE *)this + 48) = 1;
      inited = SpeechMicDiagnostic::CSpeechMicDiagnostic::InitOutputFileName(this);
      if ( inited < 0 )
      {
        v9 = 386;
        goto LABEL_13;
      }
      v10 = (const BYTE *)*((_QWORD *)this + 4);
      LODWORD(v11) = 0;
      if ( v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v10[2 * v11] );
      }
      v2 = RegSetValueExW(hKey, L"SaveWaveFileName", 0, 1u, v10, 2 * v11 + 2);
      if ( v2 )
      {
        v4 = 393;
        goto LABEL_3;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180008a9c  mov     [rsp-18h+arg_0], rbx
0x180008aa1  push    rbp
0x180008aa2  push    rsi
0x180008aa3  push    rdi
0x180008aa4  mov     rbp, rsp
0x180008aa7  sub     rsp, 40h
0x180008aab  mov     rdi, rcx
0x180008aae  xor     esi, esi
0x180008ab0  mov     [rbp+hKey], rsi
0x180008ab4  lea     rax, [rbp+hKey]
0x180008ab8  mov     [rsp+40h+phkResult], rax; unsigned int
0x180008abd  mov     r9d, 2001Fh; samDesired
0x180008ac3  xor     r8d, r8d; ulOptions
0x180008ac6  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x180008acd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008ad4  call    cs:__imp_RegOpenKeyExW
0x180008adb  nop     dword ptr [rax+rax+00h]
0x180008ae0  test    eax, eax
0x180008ae2  jz      short loc_180008B13
0x180008ae4  mov     edx, 170h; void *
0x180008ae9  mov     r9d, eax; char *
0x180008aec  mov     rcx, [rbp+18h]; this
0x180008af0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008af5  mov     ebx, eax
0x180008af7  mov     rcx, [rbp+hKey]; hKey
0x180008afb  test    rcx, rcx
0x180008afe  jz      short loc_180008B0C
0x180008b00  call    cs:__imp_RegCloseKey
0x180008b07  nop     dword ptr [rax+rax+00h]
0x180008b0c  mov     eax, ebx
0x180008b0e  jmp     loc_180008C41
0x180008b13  mov     [rbp+Data], esi
0x180008b16  mov     [rbp+Type], esi
0x180008b19  mov     [rbp+cbData], 4
0x180008b20  lea     rax, [rbp+cbData]
0x180008b24  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180008b29  lea     rax, [rbp+Data]
0x180008b2d  mov     [rsp+40h+phkResult], rax; int
0x180008b32  lea     r9, [rbp+Type]; lpType
0x180008b36  xor     r8d, r8d; lpReserved
0x180008b39  lea     rbx, aSavewave; "SaveWave"
0x180008b40  mov     rdx, rbx; lpValueName
0x180008b43  mov     rcx, [rbp+hKey]; hKey
0x180008b47  call    cs:__imp_RegQueryValueExW
0x180008b4e  nop     dword ptr [rax+rax+00h]
0x180008b53  cmp     eax, 2
0x180008b56  jz      loc_180008C2A
0x180008b5c  test    eax, eax
0x180008b5e  jz      short loc_180008B8E
0x180008b60  mov     rcx, [rbp+18h]; this
0x180008b64  mov     [rsp+40h+lpcbData], rbx; char *
0x180008b69  lea     rdx, aRegqueryvaluee; "RegQueryValueEx - %ls"
0x180008b70  mov     [rsp+40h+phkResult], rdx; unsigned int
0x180008b75  mov     r9d, eax; char *
0x180008b78  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180008b7f  mov     edx, 17Bh; void *
0x180008b84  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180008b89  jmp     loc_180008AF5
0x180008b8e  cmp     [rbp+Type], 4
0x180008b92  jz      short loc_180008BB6
0x180008b94  mov     ebx, 8000FFFFh
0x180008b99  mov     edx, 17Ch; void *
0x180008b9e  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180008ba5  mov     r9d, ebx; char *
0x180008ba8  mov     rcx, [rbp+18h]; this
0x180008bac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bb1  jmp     loc_180008AF7
0x180008bb6  cmp     [rbp+Data], esi
0x180008bb9  jz      short loc_180008C2A
0x180008bbb  mov     byte ptr [rdi+30h], 1
0x180008bbf  mov     rcx, rdi; this
0x180008bc2  call    ?InitOutputFileName@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJXZ; SpeechMicDiagnostic::CSpeechMicDiagnostic::InitOutputFileName(void)
0x180008bc7  mov     ebx, eax
0x180008bc9  test    eax, eax
0x180008bcb  jns     short loc_180008BD4
0x180008bcd  mov     edx, 182h
0x180008bd2  jmp     short loc_180008B9E
0x180008bd4  mov     rcx, [rdi+20h]
0x180008bd8  mov     eax, esi
0x180008bda  test    rcx, rcx
0x180008bdd  jz      short loc_180008BEC
0x180008bdf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008be3  inc     rax
0x180008be6  cmp     [rcx+rax*2], si
0x180008bea  jnz     short loc_180008BE3
0x180008bec  lea     eax, ds:2[rax*2]
0x180008bf3  mov     dword ptr [rsp+40h+lpcbData], eax; cbData
0x180008bf7  mov     [rsp+40h+phkResult], rcx; lpData
0x180008bfc  mov     r9d, 1; dwType
0x180008c02  xor     r8d, r8d; Reserved
0x180008c05  lea     rdx, aSavewavefilena; "SaveWaveFileName"
0x180008c0c  mov     rcx, [rbp+hKey]; hKey
0x180008c10  call    cs:__imp_RegSetValueExW
0x180008c17  nop     dword ptr [rax+rax+00h]
0x180008c1c  test    eax, eax
0x180008c1e  jz      short loc_180008C2A
0x180008c20  mov     edx, 189h
0x180008c25  jmp     loc_180008AE9
0x180008c2a  mov     rcx, [rbp+hKey]; hKey
0x180008c2e  test    rcx, rcx
0x180008c31  jz      short loc_180008C3F
0x180008c33  call    cs:__imp_RegCloseKey
0x180008c3a  nop     dword ptr [rax+rax+00h]
0x180008c3f  xor     eax, eax
0x180008c41  mov     rbx, [rsp+40h+arg_0]
0x180008c46  add     rsp, 40h
0x180008c4a  pop     rdi
0x180008c4b  pop     rsi
0x180008c4c  pop     rbp
0x180008c4d  retn
```
