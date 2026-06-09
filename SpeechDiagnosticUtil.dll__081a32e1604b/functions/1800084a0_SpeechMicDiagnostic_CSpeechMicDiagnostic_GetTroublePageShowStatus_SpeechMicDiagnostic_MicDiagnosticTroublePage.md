# SpeechMicDiagnostic::CSpeechMicDiagnostic::GetTroublePageShowStatus(SpeechMicDiagnostic::MicDiagnosticTroublePageShowStatus *)

- ea: `0x1800084a0`
- end: `0x180008724`
- name: `?GetTroublePageShowStatus@CSpeechMicDiagnostic@SpeechMicDiagnostic@@UEAAJPEAW4MicDiagnosticTroublePageShowStatus@2@@Z`
- size: `644`
- prototype: `int(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this, enum SpeechMicDiagnostic::MicDiagnosticTroublePageShowStatus *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002910`
- `0x180005b28`
- `0x18000744c`
- `0x180007510`
- `0x180007f18`
- `0x1800084a0`
- `0x1800098c4`
- `0x18000a340`
- `0x18000b590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000854a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000854a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008602`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008602`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000864e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000868f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800085c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000864e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000868f`

## string_xrefs

- `0x180008573`: `RegOpenKeyEx for %ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::GetTroublePageShowStatus(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this,
        enum SpeechMicDiagnostic::MicDiagnosticTroublePageShowStatus *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int v6; // r15d
  int v7; // r12d
  bool v8; // r14
  unsigned int v9; // eax
  int v10; // edi
  int v11; // eax
  const WCHAR *v12; // rbx
  unsigned int v13; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v19[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "GetTroublePageShowStatus");
  v19[0] = &SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::`vftable';
  SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::StartActivity(
    (SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus *)v19,
    a2);
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 109;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
    goto LABEL_27;
  }
  v6 = *((_DWORD *)this + 10);
  v7 = *((_DWORD *)this + 11);
  v8 = 0;
  hKey = 0;
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\MicWiz\\LastRun",
         0,
         0x20019u,
         &hKey);
  v10 = 2;
  if ( v9 == 2 )
    goto LABEL_18;
  if ( v9 )
  {
    v11 = wil::details::in1diag3::Return_Win32Msg(
            retaddr,
            (void *)0x1ED,
            (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
            (const char *)v9,
            (unsigned int)"RegOpenKeyEx for %ls",
            (const char *)L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\MicWiz\\LastRun");
    goto LABEL_12;
  }
  v12 = *(const WCHAR **)(*((_QWORD *)this + 1) + 144LL);
  if ( !v12 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)0x80070057LL,
      phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_15;
  }
  Type = 0;
  v13 = RegQueryValueExW(hKey, v12, 0, &Type, 0, 0);
  if ( v13 == 2 )
  {
LABEL_18:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_20;
  }
  if ( !v13 )
  {
    v8 = Type == 1;
    goto LABEL_18;
  }
  v11 = wil::details::in1diag3::Return_Win32Msg(
          retaddr,
          (void *)0x1F7,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
          (const char *)v13,
          (unsigned int)"RegQueryValueEx for %ls",
          (const char *)v12);
LABEL_12:
  v4 = v11;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v4 < 0 )
  {
LABEL_15:
    v5 = 115;
    goto LABEL_16;
  }
LABEL_20:
  if ( v6 != 10001 || v8 )
  {
    *(_DWORD *)a2 = 0;
    v10 = 0;
  }
  else if ( (v7 & 4) != 0 )
  {
    *(_DWORD *)a2 = 2;
  }
  else
  {
    *(_DWORD *)a2 = 1;
    v10 = 1;
  }
  SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::Stop(
    (SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus *)v19,
    v10);
  v4 = 0;
LABEL_27:
  v19[0] = &SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::`vftable';
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v19);
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800084a0  mov     [rsp-8+arg_10], rbx
0x1800084a5  mov     [rsp-8+arg_18], rsi
0x1800084aa  push    rbp
0x1800084ab  push    rdi
0x1800084ac  push    r12
0x1800084ae  push    r14
0x1800084b0  push    r15
0x1800084b2  lea     rbp, [rsp-0A0h]
0x1800084ba  sub     rsp, 1A0h
0x1800084c1  mov     rax, cs:__security_cookie
0x1800084c8  xor     rax, rsp
0x1800084cb  mov     [rbp+0C0h+var_30], rax
0x1800084d2  mov     rsi, rdx
0x1800084d5  mov     rbx, rcx
0x1800084d8  lea     rdx, aGettroublepage_0; "GetTroublePageShowStatus"
0x1800084df  lea     rcx, [rsp+1C0h+var_180]
0x1800084e4  call    ??0?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800084e9  lea     rax, ??_7GetTroublePageShowStatus@SmdTraceProvider@SpeechMicDiagnostic@@6B@; const SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::`vftable'
0x1800084f0  mov     [rsp+1C0h+var_180], rax
0x1800084f5  mov     rdx, rsi; void *
0x1800084f8  lea     rcx, [rsp+1C0h+var_180]; this
0x1800084fd  call    ?StartActivity@GetTroublePageShowStatus@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXPEAX@Z; SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::StartActivity(void *)
0x180008502  nop
0x180008503  test    rsi, rsi
0x180008506  jnz     short loc_180008515
0x180008508  mov     ebx, 80070057h
0x18000850d  lea     edx, [rsi+6Dh]
0x180008510  jmp     loc_180008663
0x180008515  mov     r15d, [rbx+28h]
0x180008519  mov     r12d, [rbx+2Ch]
0x18000851d  xor     r14b, r14b
0x180008520  mov     [rsp+1C0h+hKey], 0
0x180008529  lea     rax, [rsp+1C0h+hKey]
0x18000852e  mov     [rsp+1C0h+phkResult], rax; int
0x180008533  mov     r9d, 20019h; samDesired
0x180008539  xor     r8d, r8d; ulOptions
0x18000853c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x180008543  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000854a  call    cs:__imp_RegOpenKeyExW
0x180008551  nop     dword ptr [rax+rax+00h]
0x180008556  mov     edi, 2
0x18000855b  cmp     eax, edi
0x18000855d  jz      loc_180008685
0x180008563  test    eax, eax
0x180008565  jz      short loc_180008589
0x180008567  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x18000856e  mov     [rsp+1C0h+lpcbData], rdx
0x180008573  lea     rdx, aRegopenkeyexFo; "RegOpenKeyEx for %ls"
0x18000857a  mov     [rsp+1C0h+phkResult], rdx
0x18000857f  mov     edx, 1EDh
0x180008584  jmp     loc_18000862C
0x180008589  mov     rax, [rbx+8]
0x18000858d  mov     rbx, [rax+90h]
0x180008594  test    rbx, rbx
0x180008597  jnz     short loc_1800085D8
0x180008599  mov     rcx, [rbp+0C8h]; this
0x1800085a0  mov     ebx, 80070057h
0x1800085a5  mov     r9d, ebx; char *
0x1800085a8  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x1800085af  mov     edx, 1F0h; void *
0x1800085b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085b9  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1800085be  test    rcx, rcx
0x1800085c1  jz      loc_18000865E
0x1800085c7  call    cs:__imp_RegCloseKey
0x1800085ce  nop     dword ptr [rax+rax+00h]
0x1800085d3  jmp     loc_18000865E
0x1800085d8  mov     [rsp+1C0h+Type], 0
0x1800085e0  mov     [rsp+1C0h+lpcbData], 0; lpcbData
0x1800085e9  mov     [rsp+1C0h+phkResult], 0; lpData
0x1800085f2  lea     r9, [rsp+1C0h+Type]; lpType
0x1800085f7  xor     r8d, r8d; lpReserved
0x1800085fa  mov     rdx, rbx; lpValueName
0x1800085fd  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008602  call    cs:__imp_RegQueryValueExW
0x180008609  nop     dword ptr [rax+rax+00h]
0x18000860e  cmp     eax, edi
0x180008610  jz      short loc_180008685
0x180008612  test    eax, eax
0x180008614  jz      short loc_18000867B
0x180008616  mov     [rsp+1C0h+lpcbData], rbx; char *
0x18000861b  lea     rdx, aRegqueryvaluee_0; "RegQueryValueEx for %ls"
0x180008622  mov     [rsp+1C0h+phkResult], rdx; int
0x180008627  mov     edx, 1F7h; void *
0x18000862c  mov     r9d, eax; char *
0x18000862f  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180008636  mov     rcx, [rbp+0C8h]; this
0x18000863d  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180008642  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180008647  test    rcx, rcx
0x18000864a  mov     ebx, eax
0x18000864c  jz      short loc_18000865A
0x18000864e  call    cs:__imp_RegCloseKey
0x180008655  nop     dword ptr [rax+rax+00h]
0x18000865a  test    ebx, ebx
0x18000865c  jns     short loc_18000869B
0x18000865e  mov     edx, 73h ; 's'; void *
0x180008663  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x18000866a  mov     r9d, ebx; char *
0x18000866d  mov     rcx, [rbp+0C8h]; this
0x180008674  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008679  jmp     short loc_1800086D6
0x18000867b  cmp     [rsp+1C0h+Type], 1
0x180008680  jnz     short loc_180008685
0x180008682  mov     r14b, 1
0x180008685  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18000868a  test    rcx, rcx
0x18000868d  jz      short loc_18000869B
0x18000868f  call    cs:__imp_RegCloseKey
0x180008696  nop     dword ptr [rax+rax+00h]
0x18000869b  cmp     r15d, 2711h
0x1800086a2  jnz     short loc_1800086C0
0x1800086a4  test    r14b, r14b
0x1800086a7  jnz     short loc_1800086C0
0x1800086a9  test    r12b, 4
0x1800086ad  jz      short loc_1800086B3
0x1800086af  mov     [rsi], edi
0x1800086b1  jmp     short loc_1800086C8
0x1800086b3  mov     dword ptr [rsi], 1
0x1800086b9  mov     edi, 1
0x1800086be  jmp     short loc_1800086C8
0x1800086c0  mov     dword ptr [rsi], 0
0x1800086c6  xor     edi, edi
0x1800086c8  mov     edx, edi; int
0x1800086ca  lea     rcx, [rsp+1C0h+var_180]; this
0x1800086cf  call    ?Stop@GetTroublePageShowStatus@SmdTraceProvider@SpeechMicDiagnostic@@QEAAXH@Z; SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::Stop(int)
0x1800086d4  xor     ebx, ebx
0x1800086d6  lea     rax, ??_7GetTroublePageShowStatus@SmdTraceProvider@SpeechMicDiagnostic@@6B@; const SpeechMicDiagnostic::SmdTraceProvider::GetTroublePageShowStatus::`vftable'
0x1800086dd  mov     [rsp+1C0h+var_180], rax
0x1800086e2  lea     rcx, [rsp+1C0h+var_180]
0x1800086e7  call    ?Destroy@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800086ec  lea     rcx, [rsp+1C0h+var_180]
0x1800086f1  call    ??1?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800086f6  mov     eax, ebx
0x1800086f8  mov     rcx, [rbp+0C0h+var_30]
0x1800086ff  xor     rcx, rsp; StackCookie
0x180008702  call    __security_check_cookie
0x180008707  lea     r11, [rsp+1C0h+var_20]
0x18000870f  mov     rbx, [r11+40h]
0x180008713  mov     rsi, [r11+48h]
0x180008717  mov     rsp, r11
0x18000871a  pop     r15
0x18000871c  pop     r14
0x18000871e  pop     r12
0x180008720  pop     rdi
0x180008721  pop     rbp
0x180008722  retn
```
