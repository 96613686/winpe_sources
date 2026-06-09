# SpeechMicDiagnostic::CSpeechMicDiagnostic::QueryDeviceInfo(void)

- ea: `0x1800095fc`
- end: `0x180009894`
- name: `?QueryDeviceInfo@CSpeechMicDiagnostic@SpeechMicDiagnostic@@AEAAJXZ`
- size: `664`
- prototype: `__int64 __fastcall(SpeechMicDiagnostic::CSpeechMicDiagnostic *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007c88`

## callees

- `0x180005b28`
- `0x1800095fc`
- `0x18000989c`
- `0x1800098c4`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000975e`
- `KERNEL32!GetLastError` at `0x18000975e`
- `KERNEL32!SetLastError` at `0x18000977d`
- `KERNEL32!SetLastError` at `0x18000977d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800097b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009815`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009815`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009714`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000976f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000987a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009714`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000976f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000987a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::QueryDeviceInfo(
        SpeechMicDiagnostic::CSpeechMicDiagnostic *this)
{
  int *v2; // rdi
  unsigned int v3; // ebx
  __int64 v4; // r14
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v10; // rcx
  int v11; // r14d
  HKEY v12; // rdi
  DWORD LastError; // ebx
  unsigned int v14; // eax
  unsigned int v15; // r8d
  int v16; // eax
  unsigned int v17; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  unsigned int phkResultb; // [rsp+20h] [rbp-20h]
  __int64 v21; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  v2 = (int *)((char *)this + 44);
  if ( this == (SpeechMicDiagnostic::CSpeechMicDiagnostic *)-44LL )
  {
    v3 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)0x80070057LL,
      phkResult);
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
      (const char *)v3,
      phkResulta);
LABEL_11:
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  v4 = *((_QWORD *)this + 1);
  v21 = 0;
  v5 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v4)(
         *(_QWORD *)v4,
         &GUID_4b887004_cc72_43df_b2e8_182d9586f2bc,
         &v21);
  v3 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
    v6 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    goto LABEL_10;
  }
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 40LL))(v21, v2);
  v3 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\capturestream.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
    v8 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_10;
  }
  if ( !*(_BYTE *)(v4 + 200) )
    *v2 |= 4u;
  v10 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = *v2;
  v12 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v12);
    SetLastError(LastError);
  }
  hKey = 0;
  v14 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioInput\\MicWiz",
          0,
          0x20019u,
          &hKey);
  if ( v14 )
  {
    v16 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x209, v15, (const char *)v14, phkResultb);
LABEL_22:
    v3 = v16;
    goto LABEL_11;
  }
  Data = 0;
  Type = 0;
  cbData = 4;
  v17 = RegQueryValueExW(hKey, L"DefaultDefaultMicGain", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v17 != 2 )
  {
    if ( v17 )
    {
      v16 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x212,
              (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\speechmicdiagnostic\\lib\\speechmicdiagnostic.cpp",
              (const char *)v17,
              (unsigned int)"RegQueryValueEx - %ls",
              (const char *)L"DefaultDefaultMicGain");
      goto LABEL_22;
    }
    if ( Type == 4 && Data <= 0x2710 && (v11 & 2) != 0 )
      *((_DWORD *)this + 10) = Data;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800095fc  push    rbp
0x1800095fe  push    rbx
0x1800095ff  push    rsi
0x180009600  push    rdi
0x180009601  push    r14
0x180009603  mov     rbp, rsp
0x180009606  sub     rsp, 40h
0x18000960a  mov     rsi, rcx
0x18000960d  mov     [rbp+hKey], 0
0x180009615  lea     rdi, [rcx+2Ch]
0x180009619  test    rdi, rdi
0x18000961c  jnz     short loc_18000963E
0x18000961e  mov     rcx, [rbp+28h]; this
0x180009622  mov     ebx, 80070057h
0x180009627  mov     r9d, ebx; char *
0x18000962a  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180009631  lea     edx, [rdi+6Ah]; void *
0x180009634  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009639  jmp     loc_1800096F2
0x18000963e  mov     r14, [rcx+8]
0x180009642  mov     [rbp+var_10], 0
0x18000964a  mov     rcx, [r14]
0x18000964d  mov     rax, [rcx]
0x180009650  lea     r8, [rbp+var_10]
0x180009654  lea     rdx, _GUID_4b887004_cc72_43df_b2e8_182d9586f2bc
0x18000965b  mov     rax, [rax]
0x18000965e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009663  mov     ebx, eax
0x180009665  test    eax, eax
0x180009667  jns     short loc_1800096A2
0x180009669  mov     rcx, [rbp+28h]; this
0x18000966d  mov     r9d, eax; char *
0x180009670  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180009677  mov     edx, 6Dh ; 'm'; void *
0x18000967c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009681  nop
0x180009682  mov     rcx, [rbp+var_10]
0x180009686  test    rcx, rcx
0x180009689  jz      short loc_1800096A0
0x18000968b  mov     [rbp+var_10], 0
0x180009693  mov     rax, [rcx]
0x180009696  mov     rax, [rax+10h]
0x18000969a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000969f  nop
0x1800096a0  jmp     short loc_1800096F2
0x1800096a2  mov     rcx, [rbp+var_10]
0x1800096a6  mov     rax, [rcx]
0x1800096a9  mov     rdx, rdi
0x1800096ac  mov     rax, [rax+28h]
0x1800096b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096b5  mov     ebx, eax
0x1800096b7  test    eax, eax
0x1800096b9  jns     short loc_180009727
0x1800096bb  mov     rcx, [rbp+28h]; this
0x1800096bf  mov     r9d, eax; char *
0x1800096c2  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x1800096c9  mov     edx, 6Fh ; 'o'; void *
0x1800096ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096d3  nop
0x1800096d4  mov     rcx, [rbp+var_10]
0x1800096d8  test    rcx, rcx
0x1800096db  jz      short loc_1800096F2
0x1800096dd  mov     [rbp+var_10], 0
0x1800096e5  mov     rax, [rcx]
0x1800096e8  mov     rax, [rax+10h]
0x1800096ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096f1  nop
0x1800096f2  mov     rcx, [rbp+28h]; this
0x1800096f6  mov     r9d, ebx; char *
0x1800096f9  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180009700  mov     edx, 204h; void *
0x180009705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000970a  nop
0x18000970b  mov     rcx, [rbp+hKey]; hKey
0x18000970f  test    rcx, rcx
0x180009712  jz      short loc_180009720
0x180009714  call    cs:__imp_RegCloseKey
0x18000971b  nop     dword ptr [rax+rax+00h]
0x180009720  mov     eax, ebx
0x180009722  jmp     loc_180009888
0x180009727  cmp     byte ptr [r14+0C8h], 0
0x18000972f  jnz     short loc_180009734
0x180009731  or      dword ptr [rdi], 4
0x180009734  mov     rcx, [rbp+var_10]
0x180009738  test    rcx, rcx
0x18000973b  jz      short loc_180009752
0x18000973d  mov     [rbp+var_10], 0
0x180009745  mov     rax, [rcx]
0x180009748  mov     rax, [rax+10h]
0x18000974c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009751  nop
0x180009752  mov     r14d, [rdi]
0x180009755  mov     rdi, [rbp+hKey]
0x180009759  test    rdi, rdi
0x18000975c  jz      short loc_180009789
0x18000975e  call    cs:__imp_GetLastError
0x180009765  nop     dword ptr [rax+rax+00h]
0x18000976a  mov     ebx, eax
0x18000976c  mov     rcx, rdi; hKey
0x18000976f  call    cs:__imp_RegCloseKey
0x180009776  nop     dword ptr [rax+rax+00h]
0x18000977b  mov     ecx, ebx; dwErrCode
0x18000977d  call    cs:__imp_SetLastError
0x180009784  nop     dword ptr [rax+rax+00h]
0x180009789  mov     [rbp+hKey], 0
0x180009791  lea     rax, [rbp+hKey]
0x180009795  mov     [rsp+40h+phkResult], rax; unsigned int
0x18000979a  mov     r9d, 20019h; samDesired
0x1800097a0  xor     r8d, r8d; ulOptions
0x1800097a3  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x1800097aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800097b1  call    cs:__imp_RegOpenKeyExW
0x1800097b8  nop     dword ptr [rax+rax+00h]
0x1800097bd  test    eax, eax
0x1800097bf  jz      short loc_1800097D9
0x1800097c1  mov     rcx, [rbp+28h]; this
0x1800097c5  mov     r9d, eax; char *
0x1800097c8  mov     edx, 209h; void *
0x1800097cd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800097d2  mov     ebx, eax
0x1800097d4  jmp     loc_18000970B
0x1800097d9  mov     [rbp+Data], 0
0x1800097e0  mov     [rbp+Type], 0
0x1800097e7  mov     [rbp+cbData], 4
0x1800097ee  lea     rax, [rbp+cbData]
0x1800097f2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800097f7  lea     rax, [rbp+Data]
0x1800097fb  mov     [rsp+40h+phkResult], rax; lpData
0x180009800  lea     r9, [rbp+Type]; lpType
0x180009804  xor     r8d, r8d; lpReserved
0x180009807  lea     rbx, aDefaultdefault; "DefaultDefaultMicGain"
0x18000980e  mov     rdx, rbx; lpValueName
0x180009811  mov     rcx, [rbp+hKey]; hKey
0x180009815  call    cs:__imp_RegQueryValueExW
0x18000981c  nop     dword ptr [rax+rax+00h]
0x180009821  cmp     eax, 2
0x180009824  jz      short loc_180009871
0x180009826  test    eax, eax
0x180009828  jz      short loc_180009858
0x18000982a  mov     rcx, [rbp+28h]; this
0x18000982e  mov     [rsp+40h+lpcbData], rbx; char *
0x180009833  lea     rdx, aRegqueryvaluee; "RegQueryValueEx - %ls"
0x18000983a  mov     [rsp+40h+phkResult], rdx; unsigned int
0x18000983f  mov     r9d, eax; char *
0x180009842  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\nui\\onecore\\spee"...
0x180009849  mov     edx, 212h; void *
0x18000984e  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180009853  jmp     loc_1800097D2
0x180009858  cmp     [rbp+Type], 4
0x18000985c  jnz     short loc_180009871
0x18000985e  mov     eax, [rbp+Data]
0x180009861  cmp     eax, 2710h
0x180009866  ja      short loc_180009871
0x180009868  test    r14b, 2
0x18000986c  jz      short loc_180009871
0x18000986e  mov     [rsi+28h], eax
0x180009871  mov     rcx, [rbp+hKey]; hKey
0x180009875  test    rcx, rcx
0x180009878  jz      short loc_180009886
0x18000987a  call    cs:__imp_RegCloseKey
0x180009881  nop     dword ptr [rax+rax+00h]
0x180009886  xor     eax, eax
0x180009888  add     rsp, 40h
0x18000988c  pop     r14
0x18000988e  pop     rdi
0x18000988f  pop     rsi
0x180009890  pop     rbx
0x180009891  pop     rbp
0x180009892  retn
```
