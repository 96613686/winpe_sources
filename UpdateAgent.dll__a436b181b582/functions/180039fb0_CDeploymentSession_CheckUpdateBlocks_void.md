# CDeploymentSession::CheckUpdateBlocks(void)

- ea: `0x180039fb0`
- end: `0x18003a4a7`
- name: `?CheckUpdateBlocks@CDeploymentSession@@QEAAJXZ`
- size: `1271`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18006b348`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180039fb0`
- `0x180064fe4`
- `0x1800674f0`
- `0x180073dac`
- `0x180077664`
- `0x180078b9c`
- `0x18009692c`
- `0x180096d6c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18003a33d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18003a33d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003a11b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003a358`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003a11b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18003a358`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18003a46f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18003a46f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18003a083`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18003a083`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a3fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a3fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a413`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a09c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a12c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a09c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a12c`

## string_xrefs

- `0x18003a336`: `ntdll.dll`
- `0x18003a044`: `CDeploymentSession::CheckUpdateBlocks`
- `0x18003a0de`: `CDeploymentSession::CheckUpdateBlocks`
- `0x18003a17d`: `CDeploymentSession::CheckUpdateBlocks`
- `0x18003a111`: `PE_CreateProductEnumerator`
- `0x18003a37e`: `OTA updates are not available for dev mode on state-separated devices`
- `0x18003a3c1`: `Not a dev mode, state separated device, no OTA update block needed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDeploymentSession::CheckUpdateBlocks(CDeploymentSession *this)
{
  HMODULE v2; // rbx
  LPCWSTR v3; // r15
  int IsHostOSMobile; // eax
  int ProductEnumeratorPath; // eax
  signed int v6; // esi
  __int64 v7; // rcx
  int updated; // eax
  __int64 v9; // rdx
  HMODULE Library; // rax
  signed int LastError; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  FARPROC ProcAddress; // rax
  signed int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  BOOL v22; // r14d
  int Value; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  BOOL v26; // eax
  HMODULE ModuleHandleW; // rax
  unsigned __int8 (*v28)(void); // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  const char *v32; // r9
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  int v35; // [rsp+20h] [rbp-68h]
  int v36; // [rsp+28h] [rbp-60h]
  int v37; // [rsp+30h] [rbp-58h] BYREF
  int v38; // [rsp+34h] [rbp-54h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-50h] BYREF
  HMODULE v40; // [rsp+40h] [rbp-48h]
  __int64 v41; // [rsp+48h] [rbp-40h]
  struct IProduct *v42; // [rsp+50h] [rbp-38h] BYREF
  __int64 v43; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v41 = -2;
  v2 = 0;
  v40 = 0;
  v43 = 0;
  v42 = 0;
  v3 = 0;
  lpLibFileName = 0;
  v37 = 0;
  IsHostOSMobile = CMoUpdateHelpersT<CEmptyType>::IsHostOSMobile(&v37, *((_QWORD *)this + 70));
  try
  {
    if ( IsHostOSMobile < 0 || !v37 )
    {
      v6 = 0;
      v31 = *((_QWORD *)this + 75);
      if ( v31 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v31, 2, L"Not a WCOS device, won't incur reflash logic");
      goto LABEL_64;
    }
    ProductEnumeratorPath = CMoUpdateHelpersT<CEmptyType>::GetProductEnumeratorPath(&lpLibFileName);
    v6 = ProductEnumeratorPath;
    if ( ProductEnumeratorPath < 0 )
    {
      v7 = *((_QWORD *)this + 75);
      if ( v7 )
      {
        updated = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v7,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDeploymentSession::CheckUpdateBlocks",
                    746,
                    ProductEnumeratorPath);
        v7 = (unsigned int)updated;
        if ( updated < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)updated, v9);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
      v3 = lpLibFileName;
      goto LABEL_64;
    }
    v3 = lpLibFileName;
    Library = LoadLibraryExW(lpLibFileName, 0, 0);
    v2 = Library;
    if ( !Library )
    {
      v40 = 0;
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = -2147467259;
      }
      v12 = *((_QWORD *)this + 75);
      v13 = 0;
      if ( v6 >= 0 || !v12 )
        goto LABEL_19;
      v13 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            v12,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDeploymentSession::CheckUpdateBlocks",
                            749,
                            v6);
      goto LABEL_17;
    }
    v40 = Library;
    ProcAddress = GetProcAddress(Library, "PE_CreateProductEnumerator");
    if ( !ProcAddress )
    {
      v16 = GetLastError();
      v6 = v16;
      if ( v16 )
      {
        if ( v16 > 0 )
          v6 = (unsigned __int16)v16 | 0x80070000;
      }
      else
      {
        v6 = -2147467259;
      }
      v13 = 0;
      if ( v6 >= 0 || !*((_QWORD *)this + 75) )
        goto LABEL_19;
      v36 = v6;
      v35 = 752;
      v17 = *((_QWORD *)this + 75);
      goto LABEL_28;
    }
    v18 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v43);
    v6 = v18;
    if ( v18 < 0 )
    {
      v17 = *((_QWORD *)this + 75);
      if ( !v17 )
      {
LABEL_31:
        v13 = 0;
LABEL_19:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
LABEL_64:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
        if ( v3 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, (LPVOID)(v3 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        if ( v42 )
        {
          (*(void (__fastcall **)(struct IProduct *))(*(_QWORD *)v42 + 16LL))(v42);
          v42 = 0;
        }
        if ( v43 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
          v43 = 0;
        }
        if ( v2 )
          FreeLibrary(v2);
        return (unsigned int)v6;
      }
      v36 = v18;
      v35 = 754;
LABEL_28:
      v13 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                            v17,
                            4,
                            L"%s(%d): Result = 0x%X",
                            L"CDeploymentSession::CheckUpdateBlocks",
                            v35,
                            v36);
LABEL_17:
      if ( (int)v13 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13, v14);
      goto LABEL_19;
    }
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, struct IProduct **))(*(_QWORD *)v43 + 32LL))(
           v43,
           L"WCOSDevice0.OS.amd64",
           &v42) < 0 )
    {
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, struct IProduct **))(*(_QWORD *)v43 + 32LL))(
             v43,
             L"HOLOLENS.OS.RS2.arm64",
             &v42) < 0 )
      {
        v20 = *((_QWORD *)this + 75);
        if ( v20 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v20, 2, L"No reflash needed for this WCOS device");
      }
      else
      {
        v21 = CDeploymentSession::VerifyReflashNotNeeded(this, v42, L"dd8569bf-a248-475a-9a4e-bdf7bc3e67c6", 0);
        v6 = v21;
        if ( v21 < 0 )
        {
          v17 = *((_QWORD *)this + 75);
          if ( !v17 )
            goto LABEL_31;
          v36 = v21;
          v35 = 762;
          goto LABEL_28;
        }
      }
    }
    else
    {
      v19 = CDeploymentSession::VerifyReflashNotNeeded(this, v42, L"04b7c63b-88d2-4621-9868-125c7797ca80", 1);
      v6 = v19;
      if ( v19 < 0 )
      {
        v17 = *((_QWORD *)this + 75);
        if ( !v17 )
          goto LABEL_31;
        v36 = v19;
        v35 = 758;
        goto LABEL_28;
      }
    }
    v22 = 0;
    v37 = 0;
    v38 = 0;
    Value = CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(v20, L"SYSTEM", L"DevModeEverEnabled", &v37);
    v6 = Value;
    if ( Value < 0 )
      goto LABEL_44;
    v26 = 0;
    if ( v37 )
    {
      Value = CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v25, L"SYSTEM", L"DevModeEverEnabled", &v38);
      v6 = Value;
      if ( Value < 0 )
      {
LABEL_44:
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Value, v24);
        goto LABEL_49;
      }
      v26 = v38 != 0;
    }
    v22 = v26;
LABEL_49:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
    if ( v6 >= 0 )
    {
      if ( !v22
        || (ModuleHandleW = GetModuleHandleW(L"ntdll.dll")) == 0
        || (v28 = (unsigned __int8 (*)(void))GetProcAddress(ModuleHandleW, "RtlIsStateSeparationEnabled")) == 0
        || !v28() )
      {
        v30 = *((_QWORD *)this + 75);
        if ( v30 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v30,
            2,
            L"Not a dev mode, state separated device, no OTA update block needed");
        goto LABEL_64;
      }
      v29 = *((_QWORD *)this + 75);
      if ( v29 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v29,
          2,
          L"OTA updates are not available for dev mode on state-separated devices");
      v17 = *((_QWORD *)this + 75);
      v6 = -1047479587;
      if ( !v17 )
        goto LABEL_31;
      v36 = -1047479587;
      v35 = 773;
    }
    else
    {
      v17 = *((_QWORD *)this + 75);
      if ( !v17 )
        goto LABEL_31;
      v36 = v6;
      v35 = 769;
    }
    goto LABEL_28;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x313,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x180039fb0  mov     r11, rsp
0x180039fb3  push    rdi
0x180039fb4  push    r14
0x180039fb6  push    r15
0x180039fb8  sub     rsp, 70h
0x180039fbc  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x180039fc4  mov     [r11+10h], rbx
0x180039fc8  mov     [r11+18h], rsi
0x180039fcc  mov     rax, cs:__security_cookie
0x180039fd3  xor     rax, rsp
0x180039fd6  mov     [rsp+88h+var_28], rax
0x180039fdb  mov     rdi, rcx
0x180039fde  xor     ebx, ebx
0x180039fe0  mov     [rsp+88h+var_48], rbx
0x180039fe5  mov     [r11-30h], rbx
0x180039fe9  mov     [r11-38h], rbx
0x180039fed  xor     r15d, r15d
0x180039ff0  mov     [r11-50h], r15
0x180039ff4  mov     [rsp+88h+var_58], r15d
0x180039ff9  mov     rdx, [rcx+230h]
0x18003a000  lea     rcx, [r11-58h]
0x18003a004  call    ?IsHostOSMobile@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEAHPEB_W@Z; CMoUpdateHelpersT<CEmptyType>::IsHostOSMobile(int *,wchar_t const *)
0x18003a009  test    eax, eax
0x18003a00b  js      loc_18003A3D4
0x18003a011  cmp     [rsp+88h+var_58], r15d
0x18003a016  jz      loc_18003A3D4
0x18003a01c  lea     rcx, [rsp+88h+lpLibFileName]
0x18003a021  call    ?GetProductEnumeratorPath@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEAPEA_W@Z; CMoUpdateHelpersT<CEmptyType>::GetProductEnumeratorPath(wchar_t * *)
0x18003a026  mov     esi, eax
0x18003a028  test    eax, eax
0x18003a02a  jns     short loc_18003A076
0x18003a02c  mov     rcx, [rdi+258h]
0x18003a033  test    rcx, rcx
0x18003a036  jz      short loc_18003A067
0x18003a038  mov     [rsp+88h+var_60], eax
0x18003a03c  mov     [rsp+88h+var_68], 2EAh
0x18003a044  lea     r9, aCdeploymentses_119; "CDeploymentSession::CheckUpdateBlocks"
0x18003a04b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003a052  mov     edx, 4
0x18003a057  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003a05c  mov     ecx, eax
0x18003a05e  test    eax, eax
0x18003a060  jns     short loc_18003A067
0x18003a062  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003a067  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a06c  mov     r15, [rsp+88h+lpLibFileName]
0x18003a071  jmp     loc_18003A3F1
0x18003a076  mov     r15, [rsp+88h+lpLibFileName]
0x18003a07b  xor     r8d, r8d; dwFlags
0x18003a07e  xor     edx, edx; hFile
0x18003a080  mov     rcx, r15; lpLibFileName
0x18003a083  call    cs:__imp_LoadLibraryExW
0x18003a08a  nop     dword ptr [rax+rax+00h]
0x18003a08f  mov     rbx, rax
0x18003a092  test    rax, rax
0x18003a095  jnz     short loc_18003A10C
0x18003a097  mov     [rsp+88h+var_48], rax
0x18003a09c  call    cs:__imp_GetLastError
0x18003a0a3  nop     dword ptr [rax+rax+00h]
0x18003a0a8  mov     esi, eax
0x18003a0aa  test    eax, eax
0x18003a0ac  jnz     short loc_18003A0B5
0x18003a0ae  mov     esi, 80004005h
0x18003a0b3  jmp     short loc_18003A0C0
0x18003a0b5  jle     short loc_18003A0C0
0x18003a0b7  movzx   esi, ax
0x18003a0ba  or      esi, 80070000h
0x18003a0c0  mov     rax, [rdi+258h]
0x18003a0c7  xor     ecx, ecx
0x18003a0c9  test    esi, esi
0x18003a0cb  jns     short loc_18003A102
0x18003a0cd  test    rax, rax
0x18003a0d0  jz      short loc_18003A102
0x18003a0d2  mov     [rsp+88h+var_60], esi
0x18003a0d6  mov     [rsp+88h+var_68], 2EDh
0x18003a0de  lea     r9, aCdeploymentses_119; "CDeploymentSession::CheckUpdateBlocks"
0x18003a0e5  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003a0ec  lea     edx, [rcx+4]
0x18003a0ef  mov     rcx, rax
0x18003a0f2  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003a0f7  mov     ecx, eax
0x18003a0f9  test    ecx, ecx
0x18003a0fb  jns     short loc_18003A102
0x18003a0fd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003a102  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a107  jmp     loc_18003A3F1
0x18003a10c  mov     [rsp+88h+var_48], rax
0x18003a111  lea     rdx, aPeCreateproduc; "PE_CreateProductEnumerator"
0x18003a118  mov     rcx, rax; hModule
0x18003a11b  call    cs:__imp_GetProcAddress
0x18003a122  nop     dword ptr [rax+rax+00h]
0x18003a127  test    rax, rax
0x18003a12a  jnz     short loc_18003A190
0x18003a12c  call    cs:__imp_GetLastError
0x18003a133  nop     dword ptr [rax+rax+00h]
0x18003a138  mov     esi, eax
0x18003a13a  test    eax, eax
0x18003a13c  jnz     short loc_18003A145
0x18003a13e  mov     esi, 80004005h
0x18003a143  jmp     short loc_18003A150
0x18003a145  jle     short loc_18003A150
0x18003a147  movzx   esi, ax
0x18003a14a  or      esi, 80070000h
0x18003a150  mov     rax, [rdi+258h]
0x18003a157  xor     ecx, ecx
0x18003a159  test    esi, esi
0x18003a15b  jns     short loc_18003A102
0x18003a15d  test    rax, rax
0x18003a160  jz      short loc_18003A102
0x18003a162  mov     [rsp+88h+var_60], esi
0x18003a166  mov     [rsp+88h+var_68], 2F0h
0x18003a16e  mov     rcx, rax
0x18003a171  mov     edx, 4
0x18003a176  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003a17d  lea     r9, aCdeploymentses_119; "CDeploymentSession::CheckUpdateBlocks"
0x18003a184  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003a189  mov     ecx, eax
0x18003a18b  jmp     loc_18003A0F9
0x18003a190  lea     rcx, [rsp+88h+var_30]
0x18003a195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a19a  mov     esi, eax
0x18003a19c  test    eax, eax
0x18003a19e  jns     short loc_18003A1C1
0x18003a1a0  mov     rcx, [rdi+258h]
0x18003a1a7  test    rcx, rcx
0x18003a1aa  jnz     short loc_18003A1B3
0x18003a1ac  xor     ecx, ecx
0x18003a1ae  jmp     loc_18003A102
0x18003a1b3  mov     [rsp+88h+var_60], eax
0x18003a1b7  mov     [rsp+88h+var_68], 2F2h
0x18003a1bf  jmp     short loc_18003A171
0x18003a1c1  mov     rcx, [rsp+88h+var_30]
0x18003a1c6  mov     rax, [rcx]
0x18003a1c9  lea     r8, [rsp+88h+var_38]
0x18003a1ce  lea     rdx, aWcosdevice0OsA; "WCOSDevice0.OS.amd64"
0x18003a1d5  mov     rax, [rax+20h]
0x18003a1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1de  test    eax, eax
0x18003a1e0  js      short loc_18003A223
0x18003a1e2  mov     r9d, 1; int
0x18003a1e8  lea     r8, a04b7c63b88d246; "04b7c63b-88d2-4621-9868-125c7797ca80"
0x18003a1ef  mov     rdx, [rsp+88h+var_38]; struct IProduct *
0x18003a1f4  mov     rcx, rdi; this
0x18003a1f7  call    ?VerifyReflashNotNeeded@CDeploymentSession@@QEAAJPEAUIProduct@@PEB_WH@Z; CDeploymentSession::VerifyReflashNotNeeded(IProduct *,wchar_t const *,int)
0x18003a1fc  mov     esi, eax
0x18003a1fe  test    eax, eax
0x18003a200  jns     loc_18003A29F
0x18003a206  mov     rcx, [rdi+258h]
0x18003a20d  test    rcx, rcx
0x18003a210  jz      short loc_18003A1AC
0x18003a212  mov     [rsp+88h+var_60], eax
0x18003a216  mov     [rsp+88h+var_68], 2F6h
0x18003a21e  jmp     loc_18003A171
0x18003a223  mov     rcx, [rsp+88h+var_30]
0x18003a228  mov     rax, [rcx]
0x18003a22b  lea     r8, [rsp+88h+var_38]
0x18003a230  lea     rdx, aHololensOsRs2A; "HOLOLENS.OS.RS2.arm64"
0x18003a237  mov     rax, [rax+20h]
0x18003a23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a240  test    eax, eax
0x18003a242  js      short loc_18003A282
0x18003a244  xor     r9d, r9d; int
0x18003a247  lea     r8, aDd8569bfA24847; "dd8569bf-a248-475a-9a4e-bdf7bc3e67c6"
0x18003a24e  mov     rdx, [rsp+88h+var_38]; struct IProduct *
0x18003a253  mov     rcx, rdi; this
0x18003a256  call    ?VerifyReflashNotNeeded@CDeploymentSession@@QEAAJPEAUIProduct@@PEB_WH@Z; CDeploymentSession::VerifyReflashNotNeeded(IProduct *,wchar_t const *,int)
0x18003a25b  mov     esi, eax
0x18003a25d  test    eax, eax
0x18003a25f  jns     short loc_18003A29F
0x18003a261  mov     rcx, [rdi+258h]
0x18003a268  test    rcx, rcx
0x18003a26b  jz      loc_18003A1AC
0x18003a271  mov     [rsp+88h+var_60], eax
0x18003a275  mov     [rsp+88h+var_68], 2FAh
0x18003a27d  jmp     loc_18003A171
0x18003a282  mov     rcx, [rdi+258h]
0x18003a289  test    rcx, rcx
0x18003a28c  jz      short loc_18003A29F
0x18003a28e  lea     r8, aNoReflashNeede; "No reflash needed for this WCOS device"
0x18003a295  mov     edx, 2
0x18003a29a  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003a29f  xor     r14d, r14d
0x18003a2a2  mov     [rsp+88h+var_58], r14d
0x18003a2a7  mov     [rsp+88h+var_54], r14d
0x18003a2ac  lea     r9, [rsp+88h+var_58]
0x18003a2b1  lea     r8, aDevmodeeverena; "DevModeEverEnabled"
0x18003a2b8  lea     rdx, aSystem; "SYSTEM"
0x18003a2bf  call    ?ValueExists@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAH@Z; CRegUtilT<ulong,CRegType,0,1>::ValueExists(HKEY__ *,wchar_t const *,wchar_t const *,int *)
0x18003a2c4  mov     esi, eax
0x18003a2c6  test    eax, eax
0x18003a2c8  jns     short loc_18003A2D3
0x18003a2ca  mov     ecx, eax
0x18003a2cc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003a2d1  jmp     short loc_18003A305
0x18003a2d3  xor     eax, eax
0x18003a2d5  cmp     [rsp+88h+var_58], eax
0x18003a2d9  jz      short loc_18003A302
0x18003a2db  lea     r9, [rsp+88h+var_54]
0x18003a2e0  lea     r8, aDevmodeeverena; "DevModeEverEnabled"
0x18003a2e7  lea     rdx, aSystem; "SYSTEM"
0x18003a2ee  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x18003a2f3  mov     esi, eax
0x18003a2f5  test    eax, eax
0x18003a2f7  js      short loc_18003A2CA
0x18003a2f9  xor     eax, eax
0x18003a2fb  cmp     [rsp+88h+var_54], eax
0x18003a2ff  setnz   al
0x18003a302  mov     r14d, eax
0x18003a305  mov     ecx, esi
0x18003a307  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a30c  test    esi, esi
0x18003a30e  jns     short loc_18003A331
0x18003a310  mov     rcx, [rdi+258h]
0x18003a317  test    rcx, rcx
0x18003a31a  jz      loc_18003A1AC
0x18003a320  mov     [rsp+88h+var_60], esi
0x18003a324  mov     [rsp+88h+var_68], 301h
0x18003a32c  jmp     loc_18003A171
0x18003a331  test    r14d, r14d
0x18003a334  jz      short loc_18003A3B5
0x18003a336  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18003a33d  call    cs:__imp_GetModuleHandleW
0x18003a344  nop     dword ptr [rax+rax+00h]
0x18003a349  test    rax, rax
0x18003a34c  jz      short loc_18003A3B5
0x18003a34e  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18003a355  mov     rcx, rax; hModule
0x18003a358  call    cs:__imp_GetProcAddress
0x18003a35f  nop     dword ptr [rax+rax+00h]
0x18003a364  test    rax, rax
0x18003a367  jz      short loc_18003A3B5
0x18003a369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a36e  test    al, al
0x18003a370  jz      short loc_18003A3B5
0x18003a372  mov     rcx, [rdi+258h]
0x18003a379  test    rcx, rcx
0x18003a37c  jz      short loc_18003A38F
0x18003a37e  lea     r8, aOtaUpdatesAreN; "OTA updates are not available for dev m"...
0x18003a385  mov     edx, 2
0x18003a38a  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003a38f  mov     rcx, [rdi+258h]
0x18003a396  mov     esi, 0C190BADDh
0x18003a39b  test    rcx, rcx
0x18003a39e  jz      loc_18003A1AC
0x18003a3a4  mov     [rsp+88h+var_60], esi
0x18003a3a8  mov     [rsp+88h+var_68], 305h
0x18003a3b0  jmp     loc_18003A171
0x18003a3b5  mov     rcx, [rdi+258h]
0x18003a3bc  test    rcx, rcx
0x18003a3bf  jz      short loc_18003A3F1
0x18003a3c1  lea     r8, aNotADevModeSta; "Not a dev mode, state separated device,"...
0x18003a3c8  mov     edx, 2
0x18003a3cd  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003a3d2  jmp     short loc_18003A3F1
0x18003a3d4  xor     esi, esi
0x18003a3d6  mov     rcx, [rdi+258h]
0x18003a3dd  test    rcx, rcx
0x18003a3e0  jz      short loc_18003A3F1
0x18003a3e2  lea     r8, aNotAWcosDevice; "Not a WCOS device, won't incur reflash "...
0x18003a3e9  lea     edx, [rsi+2]
0x18003a3ec  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003a3f1  mov     ecx, esi
0x18003a3f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a3f8  nop
0x18003a3f9  test    r15, r15
0x18003a3fc  jz      short loc_18003A427
0x18003a3fe  call    cs:__imp_GetProcessHeap
0x18003a405  nop     dword ptr [rax+rax+00h]
0x18003a40a  mov     rcx, rax; hHeap
0x18003a40d  lea     r8, [r15-4]; lpMem
0x18003a411  xor     edx, edx; dwFlags
0x18003a413  call    cs:__imp_HeapFree
0x18003a41a  nop     dword ptr [rax+rax+00h]
0x18003a41f  xor     ecx, ecx
0x18003a421  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003a426  nop
0x18003a427  mov     rcx, [rsp+88h+var_38]
0x18003a42c  test    rcx, rcx
0x18003a42f  jz      short loc_18003A447
0x18003a431  mov     rax, [rcx]
0x18003a434  mov     rax, [rax+10h]
0x18003a438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a43d  nop
0x18003a43e  mov     [rsp+88h+var_38], 0
0x18003a447  mov     rcx, [rsp+88h+var_30]
0x18003a44c  test    rcx, rcx
0x18003a44f  jz      short loc_18003A467
0x18003a451  mov     rax, [rcx]
0x18003a454  mov     rax, [rax+10h]
0x18003a458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a45d  nop
0x18003a45e  mov     [rsp+88h+var_30], 0
0x18003a467  test    rbx, rbx
0x18003a46a  jz      short loc_18003A47B
0x18003a46c  mov     rcx, rbx; hLibModule
0x18003a46f  call    cs:__imp_FreeLibrary
0x18003a476  nop     dword ptr [rax+rax+00h]
0x18003a47b  mov     eax, esi
0x18003a47d  jmp     short loc_18003A483
0x18003a47f  mov     eax, [rsp+88h+var_54]
  ... truncated ...
```
