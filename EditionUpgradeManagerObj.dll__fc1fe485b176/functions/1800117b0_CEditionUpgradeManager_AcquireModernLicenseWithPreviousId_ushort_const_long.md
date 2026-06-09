# CEditionUpgradeManager::AcquireModernLicenseWithPreviousId(ushort const *,long *)

- ea: `0x1800117b0`
- end: `0x180011d5b`
- name: `?AcquireModernLicenseWithPreviousId@CEditionUpgradeManager@@UEAAJPEBGPEAJ@Z`
- size: `1451`
- prototype: `__int64 __fastcall(CEditionUpgradeManager *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001ac0`
- `0x1800026b4`
- `0x1800090dc`
- `0x180009480`
- `0x18000f264`
- `0x1800117b0`
- `0x1800133e0`
- `0x180013b8c`
- `0x1800166a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011d22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011cf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011cf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011d13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a8b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180011afd`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180011afd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180011a17`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180011a17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011cd9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ce7`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001189b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001189b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011ccb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011ccb`
- `USER32!PeekMessageW` at `0x180011ab5`
- `USER32!PeekMessageW` at `0x180011ae3`
- `USER32!PeekMessageW` at `0x180011ab5`
- `USER32!PeekMessageW` at `0x180011ae3`
- `USER32!DispatchMessageW` at `0x180011acd`
- `USER32!DispatchMessageW` at `0x180011acd`
- `USER32!TranslateMessage` at `0x180011ac3`
- `USER32!TranslateMessage` at `0x180011ac3`
- `USER32!MsgWaitForMultipleObjects` at `0x180011a71`
- `USER32!MsgWaitForMultipleObjects` at `0x180011a71`

## pseudocode

```c
__int64 __fastcall CEditionUpgradeManager::AcquireModernLicenseWithPreviousId(
        CEditionUpgradeManager *this,
        const unsigned __int16 *a2,
        int *a3)
{
  LPWSTR v3; // r13
  const WCHAR *v5; // r14
  __int64 v6; // r15
  HANDLE hProcess; // rbx
  HANDLE hThread; // rdi
  unsigned __int16 *v9; // r12
  unsigned int v10; // esi
  int v11; // edx
  __int64 v12; // r8
  int *v13; // r9
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  signed int v17; // eax
  int v18; // r14d
  DWORD v19; // eax
  CEditionUpgradeManager *v20; // rcx
  signed int LastError; // eax
  int ConnectedAccountTicket; // eax
  CEditionUpgradeManager *v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v29; // rax
  const unsigned __int16 *v31; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  DWORD ExitCode; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpCommandLine; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v35; // [rsp+70h] [rbp-90h] BYREF
  int *v36; // [rsp+78h] [rbp-88h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+80h] [rbp-80h] BYREF
  struct tagMSG Msg; // [rsp+98h] [rbp-68h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v40[32]; // [rsp+140h] [rbp+40h] BYREF
  const WCHAR *v41; // [rsp+160h] [rbp+60h]
  int v42; // [rsp+168h] [rbp+68h]
  int v43; // [rsp+16Ch] [rbp+6Ch]
  const unsigned __int16 **v44; // [rsp+170h] [rbp+70h]
  __int64 v45; // [rsp+178h] [rbp+78h]
  __int64 *v46; // [rsp+180h] [rbp+80h]
  __int64 v47; // [rsp+188h] [rbp+88h]
  _BYTE v48[32]; // [rsp+190h] [rbp+90h] BYREF

  v36 = a3;
  v3 = 0;
  v31 = a2;
  ExitCode = 0;
  v5 = a2;
  lpCommandLine = 0;
  v6 = 0;
  v32 = 0;
  memset(&Msg, 0, sizeof(Msg));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v35 = 0;
  hProcess = 0;
  hThread = 0;
  v9 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( v5 && a3 )
  {
    if ( (unsigned int)dword_18002F1D0 > 5
      && (qword_18002F1E0 & 0x800000000000LL) != 0
      && (qword_18002F1E8 & 0x800000000000LL) == qword_18002F1E8 )
    {
      EventActivityIdControl(3u, &ActivityId);
    }
    else
    {
      ActivityId = 0;
    }
    g_osReactivationE2EActivity = 1;
    if ( (unsigned int)dword_18002F1D0 > 5
      && (qword_18002F1E0 & 0x800000000000LL) != 0
      && (qword_18002F1E8 & 0x800000000000LL) == qword_18002F1E8 )
    {
      if ( byte_18002FBD4 && (dword_18002FBE8 || dword_18002FBEC || dword_18002FBF0 || dword_18002FBF4) )
        v13 = &dword_18002FBE8;
      else
        v13 = 0;
      tlgWriteTransfer_EventWriteTransfer(&dword_18002F1D0, word_18002B1B2, &ActivityId, v13, 2, v48);
    }
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    v15 = CMiscHelpersT<CEmptyType>::ExpandFileName(v14, &v32);
    v10 = v15;
    if ( v15 >= 0 )
    {
      v6 = v32;
      v16 = STRAPI_Format(&lpCommandLine, L"%s -%s -%s %s", v32, L"o", L"previd", v5);
      v10 = v16;
      if ( v16 >= 0 )
      {
        v3 = lpCommandLine;
        if ( CreateProcessW(0, lpCommandLine, 0, 0, 0, 0x8000000u, 0, 0, &StartupInfo, &ProcessInformation) )
        {
          hProcess = ProcessInformation.hProcess;
          v18 = 0;
          hThread = ProcessInformation.hThread;
          do
          {
            v19 = MsgWaitForMultipleObjects(1u, &ProcessInformation.hProcess, 0, 0xFFFFFFFF, 0x1CFFu);
            if ( v19 )
            {
              if ( v19 == 1 )
              {
                if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
                {
                  do
                  {
                    TranslateMessage(&Msg);
                    DispatchMessageW(&Msg);
                  }
                  while ( PeekMessageW(&Msg, 0, 0, 0, 1u) );
                  v6 = v32;
                }
              }
              else if ( v19 == -1 )
              {
                goto LABEL_34;
              }
            }
            else
            {
              if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
              {
LABEL_34:
                LastError = GetLastError();
                v10 = LastError;
                if ( LastError )
                {
                  if ( LastError > 0 )
                    v10 = (unsigned __int16)LastError | 0x80070000;
                }
                else
                {
                  v10 = -2147467259;
                }
LABEL_48:
                v25 = v10;
LABEL_49:
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v25);
                goto LABEL_50;
              }
              v18 = 1;
              v10 = ExitCode;
              if ( (ExitCode & 0x80000000) != 0 )
                goto LABEL_48;
            }
          }
          while ( !v18 );
          ConnectedAccountTicket = CEditionUpgradeManager::GetConnectedAccountTicket(v20, &v35);
          v10 = ConnectedAccountTicket;
          if ( ConnectedAccountTicket < 0 )
          {
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)ConnectedAccountTicket);
            v9 = v35;
            goto LABEL_50;
          }
          v9 = v35;
          v24 = CEditionUpgradeManager::AcquireModernLicenseForWindowsWithUserTicket(v23, v35, 0, v36);
          v11 = 0;
          v10 = v24;
          if ( v24 < 0 )
          {
            v25 = (unsigned int)v24;
            goto LABEL_49;
          }
LABEL_50:
          v5 = v31;
        }
        else
        {
          v17 = GetLastError();
          v10 = v17;
          if ( v17 )
          {
            if ( v17 > 0 )
              v10 = (unsigned __int16)v17 | 0x80070000;
          }
          else
          {
            v10 = -2147467259;
          }
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
        }
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
        v3 = lpCommandLine;
      }
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15);
      v6 = v32;
    }
    v12 = 0x800000000000LL;
  }
  else
  {
    v10 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
  }
  if ( (unsigned int)dword_18002F1D0 > 5 && (qword_18002F1E0 & v12) != 0 && (v12 & qword_18002F1E8) == qword_18002F1E8 )
  {
    LODWORD(v32) = v10;
    v47 = 4;
    v45 = 4;
    LODWORD(v31) = *v36;
    v46 = &v32;
    v44 = &v31;
    if ( v5 )
    {
      v26 = -1;
      do
        ++v26;
      while ( v5[v26] != (_WORD)v11 );
      v27 = 2 * v26 + 2;
    }
    else
    {
      v5 = &LocaleName;
      v27 = 2;
    }
    v42 = v27;
    v43 = v11;
    v41 = v5;
    tlgWriteTransfer_EventWriteTransfer(&dword_18002F1D0, byte_18002B161, &ActivityId, 0, 5, v40);
  }
  g_osReactivationE2EActivity = 2;
  if ( (unsigned int)dword_18002F1D0 > 5
    && (qword_18002F1E0 & 0x800000000000LL) != 0
    && (qword_18002F1E8 & 0x800000000000LL) == qword_18002F1E8 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_18002F1D0, &byte_18002B13F, &ActivityId, 0, 2, v48);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
  if ( v9 )
    LocalFree(v9);
  if ( hThread )
    CloseHandle(hThread);
  if ( hProcess )
    CloseHandle(hProcess);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, v3 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v10;
}

```

## disassembly

```asm
0x1800117b0  mov     [rsp-8+arg_0], rbx
0x1800117b5  push    rbp
0x1800117b6  push    rsi
0x1800117b7  push    rdi
0x1800117b8  push    r12
0x1800117ba  push    r13
0x1800117bc  push    r14
0x1800117be  push    r15
0x1800117c0  lea     rbp, [rsp-0C0h]
0x1800117c8  sub     rsp, 1C0h
0x1800117cf  mov     rax, cs:__security_cookie
0x1800117d6  xor     rax, rsp
0x1800117d9  mov     [rbp+0F0h+var_40], rax
0x1800117e0  xorps   xmm0, xmm0
0x1800117e3  mov     [rsp+1F0h+var_178], r8
0x1800117e8  xor     r13d, r13d
0x1800117eb  mov     [rsp+1F0h+var_1A0], rdx
0x1800117f0  mov     rsi, r8
0x1800117f3  mov     [rsp+1F0h+ExitCode], 0
0x1800117fb  mov     r14, rdx
0x1800117fe  mov     [rsp+1F0h+lpCommandLine], r13
0x180011803  xor     r15d, r15d
0x180011806  lea     rcx, [rbp+0F0h+StartupInfo]; void *
0x18001180a  lea     r8d, [r13+68h]; Size
0x18001180e  mov     [rsp+1F0h+var_198], r15
0x180011813  xor     edx, edx; Val
0x180011815  movups  xmmword ptr [rbp+0F0h+Msg.hwnd], xmm0
0x180011819  movups  xmmword ptr [rbp+0F0h+Msg.wParam], xmm0
0x18001181d  movups  xmmword ptr [rbp+0F0h+Msg.time], xmm0
0x180011821  call    memset_0
0x180011826  xor     edx, edx
0x180011828  xor     eax, eax
0x18001182a  mov     qword ptr [rbp+0F0h+ProcessInformation.dwProcessId], rax
0x18001182e  xorps   xmm0, xmm0
0x180011831  mov     [rsp+1F0h+var_180], rdx
0x180011836  mov     ebx, edx
0x180011838  mov     edi, edx
0x18001183a  mov     r12d, edx
0x18001183d  mov     r8, 800000000000h
0x180011847  movups  xmmword ptr [rbp+0F0h+ProcessInformation.hProcess], xmm0
0x18001184b  test    r14, r14
0x18001184e  jnz     short loc_180011861
0x180011850  mov     ecx, 80070057h
0x180011855  mov     esi, ecx
0x180011857  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001185c  jmp     loc_180011B82
0x180011861  test    rsi, rsi
0x180011864  jz      short loc_180011850
0x180011866  mov     eax, cs:dword_18002F1D0
0x18001186c  cmp     eax, 5
0x18001186f  jbe     short loc_1800118AF
0x180011871  mov     rcx, cs:qword_18002F1E8
0x180011878  mov     rax, cs:qword_18002F1E0
0x18001187f  test    r8, rax
0x180011882  jz      short loc_1800118AF
0x180011884  mov     rax, rcx
0x180011887  and     rax, r8
0x18001188a  cmp     rax, rcx
0x18001188d  jnz     short loc_1800118AF
0x18001188f  lea     rdx, ActivityId; ActivityId
0x180011896  mov     ecx, 3; ControlCode
0x18001189b  call    cs:__imp_EventActivityIdControl
0x1800118a1  xor     edx, edx
0x1800118a3  mov     r8, 800000000000h
0x1800118ad  jmp     short loc_1800118B6
0x1800118af  movups  xmmword ptr cs:ActivityId.Data1, xmm0
0x1800118b6  mov     eax, cs:dword_18002F1D0
0x1800118bc  mov     cs:?g_osReactivationE2EActivity@@3V?$TraceLoggingActivity@$1?g_ChangePKTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0IAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 1; TraceLoggingActivity<&_tlgProvider_t const * const g_ChangePKTraceLoggingProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider> g_osReactivationE2EActivity
0x1800118c6  cmp     eax, 5
0x1800118c9  jbe     loc_18001194F
0x1800118cf  mov     rcx, cs:qword_18002F1E8
0x1800118d6  mov     rax, cs:qword_18002F1E0
0x1800118dd  test    r8, rax
0x1800118e0  jz      short loc_18001194F
0x1800118e2  mov     rax, rcx
0x1800118e5  and     rax, r8
0x1800118e8  cmp     rax, rcx
0x1800118eb  jnz     short loc_18001194F
0x1800118ed  cmp     cs:byte_18002FBD4, dl
0x1800118f3  jz      short loc_18001191E
0x1800118f5  cmp     cs:dword_18002FBE8, edx
0x1800118fb  jnz     short loc_180011915
0x1800118fd  cmp     cs:dword_18002FBEC, edx
0x180011903  jnz     short loc_180011915
0x180011905  cmp     cs:dword_18002FBF0, edx
0x18001190b  jnz     short loc_180011915
0x18001190d  cmp     cs:dword_18002FBF4, edx
0x180011913  jz      short loc_18001191E
0x180011915  lea     r9, dword_18002FBE8
0x18001191c  jmp     short loc_180011921
0x18001191e  mov     r9, rdx
0x180011921  lea     rax, [rbp+0F0h+var_60]
0x180011928  mov     qword ptr [rsp+1F0h+dwCreationFlags], rax
0x18001192d  lea     r8, ActivityId
0x180011934  lea     rdx, word_18002B1B2
0x18001193b  mov     [rsp+1F0h+bInheritHandles], 2
0x180011943  lea     rcx, dword_18002F1D0
0x18001194a  call    _tlgWriteTransfer_EventWriteTransfer
0x18001194f  xor     edx, edx; Val
0x180011951  lea     rcx, [rbp+0F0h+StartupInfo+4]; void *
0x180011955  lea     r8d, [rdx+64h]; Size
0x180011959  call    memset_0
0x18001195e  xorps   xmm0, xmm0
0x180011961  mov     [rbp+0F0h+StartupInfo.cb], 68h ; 'h'
0x180011968  xor     eax, eax
0x18001196a  lea     rdx, [rsp+1F0h+var_198]
0x18001196f  movups  xmmword ptr [rbp+0F0h+ProcessInformation.hProcess], xmm0
0x180011973  mov     qword ptr [rbp+0F0h+ProcessInformation.dwProcessId], rax
0x180011977  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x18001197c  xor     edx, edx
0x18001197e  mov     esi, eax
0x180011980  test    eax, eax
0x180011982  jns     short loc_180011995
0x180011984  mov     ecx, eax
0x180011986  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001198b  mov     r15, [rsp+1F0h+var_198]
0x180011990  jmp     loc_180011B78
0x180011995  mov     r15, [rsp+1F0h+var_198]
0x18001199a  lea     rax, aPrevid; "previd"
0x1800119a1  mov     r8, r15
0x1800119a4  mov     qword ptr [rsp+1F0h+dwCreationFlags], r14
0x1800119a9  lea     r9, aO; "o"
0x1800119b0  mov     qword ptr [rsp+1F0h+bInheritHandles], rax
0x1800119b5  lea     rdx, aSSSS; "%s -%s -%s %s"
0x1800119bc  lea     rcx, [rsp+1F0h+lpCommandLine]; unsigned __int16 **
0x1800119c1  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x1800119c6  xor     edx, edx
0x1800119c8  mov     esi, eax
0x1800119ca  test    eax, eax
0x1800119cc  jns     short loc_1800119DF
0x1800119ce  mov     ecx, eax
0x1800119d0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800119d5  mov     r13, [rsp+1F0h+lpCommandLine]
0x1800119da  jmp     loc_180011B78
0x1800119df  mov     r13, [rsp+1F0h+lpCommandLine]
0x1800119e4  lea     rax, [rbp+0F0h+ProcessInformation]
0x1800119e8  mov     [rsp+1F0h+lpProcessInformation], rax; lpProcessInformation
0x1800119ed  xor     r9d, r9d; lpThreadAttributes
0x1800119f0  lea     rax, [rbp+0F0h+StartupInfo]
0x1800119f4  xor     r8d, r8d; lpProcessAttributes
0x1800119f7  mov     [rsp+1F0h+lpStartupInfo], rax; lpStartupInfo
0x1800119fc  xor     ecx, ecx; lpApplicationName
0x1800119fe  mov     [rsp+1F0h+lpCurrentDirectory], rdx; lpCurrentDirectory
0x180011a03  mov     [rsp+1F0h+lpEnvironment], rdx; lpEnvironment
0x180011a08  mov     [rsp+1F0h+dwCreationFlags], 8000000h; dwCreationFlags
0x180011a10  mov     [rsp+1F0h+bInheritHandles], edx; bInheritHandles
0x180011a14  mov     rdx, r13; lpCommandLine
0x180011a17  call    cs:__imp_CreateProcessW
0x180011a1d  test    eax, eax
0x180011a1f  jnz     short loc_180011A4D
0x180011a21  call    cs:__imp_GetLastError
0x180011a27  xor     edx, edx
0x180011a29  mov     esi, eax
0x180011a2b  test    eax, eax
0x180011a2d  jnz     short loc_180011A36
0x180011a2f  mov     esi, 80004005h
0x180011a34  jmp     short loc_180011A41
0x180011a36  jle     short loc_180011A41
0x180011a38  movzx   esi, ax
0x180011a3b  or      esi, 80070000h
0x180011a41  mov     ecx, esi
0x180011a43  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180011a48  jmp     loc_180011B78
0x180011a4d  mov     rbx, [rbp+0F0h+ProcessInformation.hProcess]
0x180011a51  xor     r14d, r14d
0x180011a54  mov     rdi, [rbp+0F0h+ProcessInformation.hThread]
0x180011a58  lea     esi, [r14+1]
0x180011a5c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180011a60  mov     [rsp+1F0h+bInheritHandles], 1CFFh; dwWakeMask
0x180011a68  xor     r8d, r8d; fWaitAll
0x180011a6b  lea     rdx, [rbp+0F0h+ProcessInformation]; pHandles
0x180011a6f  mov     ecx, esi; nCount
0x180011a71  call    cs:__imp_MsgWaitForMultipleObjects
0x180011a77  xor     edx, edx; hWnd
0x180011a79  test    eax, eax
0x180011a7b  jz      short loc_180011AF4
0x180011a7d  cmp     eax, 1
0x180011a80  jz      short loc_180011AA7
0x180011a82  cmp     eax, 0FFFFFFFFh
0x180011a85  jnz     loc_180011B17
0x180011a8b  call    cs:__imp_GetLastError
0x180011a91  xor     edx, edx
0x180011a93  mov     esi, eax
0x180011a95  test    eax, eax
0x180011a97  jnz     loc_180011B61
0x180011a9d  mov     esi, 80004005h
0x180011aa2  jmp     loc_180011B6C
0x180011aa7  xor     r9d, r9d; wMsgFilterMax
0x180011aaa  mov     [rsp+1F0h+bInheritHandles], esi; wRemoveMsg
0x180011aae  xor     r8d, r8d; wMsgFilterMin
0x180011ab1  lea     rcx, [rbp+0F0h+Msg]; lpMsg
0x180011ab5  call    cs:__imp_PeekMessageW
0x180011abb  test    eax, eax
0x180011abd  jz      short loc_180011B17
0x180011abf  lea     rcx, [rbp+0F0h+Msg]; lpMsg
0x180011ac3  call    cs:__imp_TranslateMessage
0x180011ac9  lea     rcx, [rbp+0F0h+Msg]; lpMsg
0x180011acd  call    cs:__imp_DispatchMessageW
0x180011ad3  xor     r9d, r9d; wMsgFilterMax
0x180011ad6  mov     [rsp+1F0h+bInheritHandles], esi; wRemoveMsg
0x180011ada  xor     r8d, r8d; wMsgFilterMin
0x180011add  lea     rcx, [rbp+0F0h+Msg]; lpMsg
0x180011ae1  xor     edx, edx; hWnd
0x180011ae3  call    cs:__imp_PeekMessageW
0x180011ae9  test    eax, eax
0x180011aeb  jnz     short loc_180011ABF
0x180011aed  mov     r15, [rsp+1F0h+var_198]
0x180011af2  jmp     short loc_180011B17
0x180011af4  mov     rcx, [rbp+0F0h+ProcessInformation.hProcess]; hProcess
0x180011af8  lea     rdx, [rsp+1F0h+ExitCode]; lpExitCode
0x180011afd  call    cs:__imp_GetExitCodeProcess
0x180011b03  xor     edx, edx
0x180011b05  test    eax, eax
0x180011b07  jz      short loc_180011A8B
0x180011b09  mov     r14d, esi
0x180011b0c  mov     esi, [rsp+1F0h+ExitCode]
0x180011b10  test    esi, esi
0x180011b12  js      short loc_180011B6C
0x180011b14  lea     esi, [rdx+1]
0x180011b17  test    r14d, r14d
0x180011b1a  jz      loc_180011A5C
0x180011b20  lea     rdx, [rsp+1F0h+var_180]; unsigned __int16 **
0x180011b25  call    ?GetConnectedAccountTicket@CEditionUpgradeManager@@AEAAJPEAPEAG@Z; CEditionUpgradeManager::GetConnectedAccountTicket(ushort * *)
0x180011b2a  xor     edx, edx
0x180011b2c  mov     esi, eax
0x180011b2e  test    eax, eax
0x180011b30  jns     short loc_180011B40
0x180011b32  mov     ecx, eax
0x180011b34  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180011b39  mov     r12, [rsp+1F0h+var_180]
0x180011b3e  jmp     short loc_180011B73
0x180011b40  mov     r12, [rsp+1F0h+var_180]
0x180011b45  xor     r8d, r8d; int
0x180011b48  mov     r9, [rsp+1F0h+var_178]; int *
0x180011b4d  mov     rdx, r12; unsigned __int16 *
0x180011b50  call    ?AcquireModernLicenseForWindowsWithUserTicket@CEditionUpgradeManager@@AEAAJPEAGHPEAJ@Z; CEditionUpgradeManager::AcquireModernLicenseForWindowsWithUserTicket(ushort *,int,long *)
0x180011b55  xor     edx, edx
0x180011b57  mov     esi, eax
0x180011b59  test    eax, eax
0x180011b5b  jns     short loc_180011B73
0x180011b5d  mov     ecx, eax
0x180011b5f  jmp     short loc_180011B6E
0x180011b61  jle     short loc_180011B6C
0x180011b63  movzx   esi, ax
0x180011b66  or      esi, 80070000h
0x180011b6c  mov     ecx, esi
0x180011b6e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180011b73  mov     r14, [rsp+1F0h+var_1A0]
0x180011b78  mov     r8, 800000000000h
0x180011b82  mov     eax, cs:dword_18002F1D0
0x180011b88  cmp     eax, 5
0x180011b8b  jbe     loc_180011C4E
0x180011b91  mov     rcx, cs:qword_18002F1E8
0x180011b98  mov     rax, cs:qword_18002F1E0
0x180011b9f  test    r8, rax
0x180011ba2  jz      loc_180011C4E
0x180011ba8  mov     rax, rcx
0x180011bab  and     rax, r8
0x180011bae  cmp     rax, rcx
0x180011bb1  jnz     loc_180011C4E
0x180011bb7  mov     rax, [rsp+1F0h+var_178]
0x180011bbc  mov     dword ptr [rsp+1F0h+var_198], esi
0x180011bc0  mov     [rbp+0F0h+var_68], 4
0x180011bcb  mov     [rbp+0F0h+var_78], 4
0x180011bd3  mov     eax, [rax]
0x180011bd5  mov     dword ptr [rsp+1F0h+var_1A0], eax
0x180011bd9  lea     rax, [rsp+1F0h+var_198]
0x180011bde  mov     [rbp+0F0h+var_70], rax
0x180011be5  lea     rax, [rsp+1F0h+var_1A0]
0x180011bea  mov     [rbp+0F0h+var_80], rax
0x180011bee  test    r14, r14
0x180011bf1  jz      short loc_180011C0A
0x180011bf3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011bf7  inc     rax
0x180011bfa  cmp     [r14+rax*2], dx
0x180011bff  jnz     short loc_180011BF7
0x180011c01  lea     eax, ds:2[rax*2]
0x180011c08  jmp     short loc_180011C16
0x180011c0a  lea     r14, LocaleName
0x180011c11  mov     eax, 2
0x180011c16  mov     [rbp+0F0h+var_88], eax
0x180011c19  lea     r8, ActivityId
0x180011c20  lea     rax, [rbp+0F0h+var_B0]
0x180011c24  mov     [rbp+0F0h+var_84], edx
0x180011c27  mov     qword ptr [rsp+1F0h+dwCreationFlags], rax
0x180011c2c  lea     rdx, byte_18002B161
0x180011c33  xor     r9d, r9d
0x180011c36  mov     [rsp+1F0h+bInheritHandles], 5
0x180011c3e  lea     rcx, dword_18002F1D0
0x180011c45  mov     [rbp+0F0h+var_90], r14
0x180011c49  call    _tlgWriteTransfer_EventWriteTransfer
0x180011c4e  mov     eax, cs:dword_18002F1D0
0x180011c54  mov     r10d, 2
0x180011c5a  mov     cs:?g_osReactivationE2EActivity@@3V?$TraceLoggingActivity@$1?g_ChangePKTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0IAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, r10d; TraceLoggingActivity<&_tlgProvider_t const * const g_ChangePKTraceLoggingProvider,140737488355328,5,_TlgReflectorTag_Param0IsHProvider> g_osReactivationE2EActivity
0x180011c61  cmp     eax, 5
0x180011c64  jbe     short loc_180011CBC
0x180011c66  mov     rdx, cs:qword_18002F1E8
0x180011c6d  mov     r9, 800000000000h
0x180011c77  mov     rax, cs:qword_18002F1E0
0x180011c7e  test    r9, rax
  ... truncated ...
```
