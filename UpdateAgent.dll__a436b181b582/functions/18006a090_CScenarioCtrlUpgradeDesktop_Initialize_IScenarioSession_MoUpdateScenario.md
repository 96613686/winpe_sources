# CScenarioCtrlUpgradeDesktop::Initialize(IScenarioSession *,MoUpdateScenario)

- ea: `0x18006a090`
- end: `0x18006a5db`
- name: `?Initialize@CScenarioCtrlUpgradeDesktop@@UEAAJPEAVIScenarioSession@@W4MoUpdateScenario@@@Z`
- size: `1355`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x180069f20`
- `0x18006a090`
- `0x180077664`
- `0x180078b9c`
- `0x18008c4c4`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006a32f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006a404`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006a4d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006a32f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006a404`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006a4d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a58d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a58d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a5a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006a5a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a50c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a195`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a50c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006a185`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18006a185`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a34a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a41f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a4f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a34a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a41f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a4f4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006a572`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006a572`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CScenarioCtrlUpgradeDesktop::Initialize(__int64 a1, __int64 a2)
{
  __int64 updated; // rcx
  signed int v5; // edi
  __int64 v6; // rdx
  int v7; // eax
  signed int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  HANDLE v14; // rbx
  void *v15; // rcx
  signed int v16; // eax
  int v17; // eax
  HANDLE v18; // rbx
  void *v19; // rcx
  signed int v20; // eax
  int v21; // eax
  HANDLE v22; // rbx
  void *v23; // rcx
  signed int LastError; // eax
  const char *v25; // r9
  __int64 v26; // rbx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  int v29; // [rsp+20h] [rbp-88h]
  signed int v30; // [rsp+28h] [rbp-80h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-70h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp-58h] BYREF
  __int64 v33; // [rsp+58h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  try
  {
    v33 = 0;
    SecurityDescriptor = 0;
    memset(&EventAttributes, 0, sizeof(EventAttributes));
    SecurityDescriptorSize = 0;
    if ( !a2 )
    {
      updated = 0;
      v5 = -2147024809;
      if ( *(_QWORD *)(a1 + 32) )
      {
        updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                  *(_QWORD *)(a1 + 32),
                                  4,
                                  L"%s(%d): Result = 0x%X",
                                  L"CScenarioCtrlUpgradeDesktop::Initialize",
                                  65,
                                  -2147024809,
                                  -2,
                                  *(_QWORD *)&EventAttributes.nLength,
                                  EventAttributes.lpSecurityDescriptor,
                                  *(_QWORD *)&EventAttributes.bInheritHandle);
        goto LABEL_5;
      }
LABEL_7:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_72:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
      if ( SecurityDescriptor )
      {
        LocalFree(SecurityDescriptor);
        SecurityDescriptor = 0;
      }
      v26 = v33;
      if ( v33 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v26 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      return (unsigned int)v5;
    }
    v7 = CScenarioCtrlBase::Initialize();
    v5 = v7;
    if ( v7 >= 0 )
    {
      SecurityDescriptorSize = 0;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
             L"D:(A;;GA;;;BA)(A;;GA;;;OW)",
             1u,
             &SecurityDescriptor,
             &SecurityDescriptorSize) )
      {
        *(_QWORD *)&EventAttributes.nLength = 24;
        *(_QWORD *)&EventAttributes.bInheritHandle = 0;
        EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v33);
        v5 = v9;
        if ( v9 >= 0 )
        {
          v10 = STRAPI_Format((wchar_t **)(a1 + 80), L"C-%s", v33);
          v5 = v10;
          if ( v10 >= 0 )
          {
            v11 = STRAPI_Format((wchar_t **)(a1 + 88), L"P-%s", v33);
            v5 = v11;
            if ( v11 >= 0 )
            {
              v12 = STRAPI_Format((wchar_t **)(a1 + 96), L"S-%s", v33);
              v5 = v12;
              if ( v12 >= 0 )
              {
                v13 = STRAPI_Format((wchar_t **)(a1 + 104), L"%s{%s}", L"Global\\MoSetup", *(_QWORD *)(a1 + 80));
                v5 = v13;
                if ( v13 >= 0 )
                {
                  v14 = CreateEventW(&EventAttributes, 1, 0, *(LPCWSTR *)(a1 + 104));
                  v15 = *(void **)(a1 + 128);
                  if ( v15 )
                    CloseHandle(v15);
                  if ( v14 )
                  {
                    *(_QWORD *)(a1 + 128) = v14;
                    v17 = STRAPI_Format((wchar_t **)(a1 + 112), L"%s{%s}", L"Global\\MoSetup", *(_QWORD *)(a1 + 88));
                    v5 = v17;
                    if ( v17 >= 0 )
                    {
                      v18 = CreateEventW(&EventAttributes, 1, 0, *(LPCWSTR *)(a1 + 112));
                      v19 = *(void **)(a1 + 136);
                      if ( v19 )
                        CloseHandle(v19);
                      if ( v18 )
                      {
                        *(_QWORD *)(a1 + 136) = v18;
                        v21 = STRAPI_Format((wchar_t **)(a1 + 120), L"%s{%s}", L"Global\\MoSetup", *(_QWORD *)(a1 + 96));
                        v5 = v21;
                        if ( v21 >= 0 )
                        {
                          v22 = CreateEventW(&EventAttributes, 1, 0, *(LPCWSTR *)(a1 + 120));
                          v23 = *(void **)(a1 + 144);
                          if ( v23 )
                            CloseHandle(v23);
                          if ( v22 )
                          {
                            *(_QWORD *)(a1 + 144) = v22;
                            goto LABEL_72;
                          }
                          *(_QWORD *)(a1 + 144) = 0;
                          LastError = GetLastError();
                          v5 = LastError;
                          if ( LastError )
                          {
                            if ( LastError > 0 )
                              v5 = (unsigned __int16)LastError | 0x80070000;
                            updated = 0;
                            if ( v5 >= 0 )
                              goto LABEL_7;
                          }
                          else
                          {
                            v5 = -2147467259;
                            updated = 0;
                          }
                          if ( !*(_QWORD *)(a1 + 32) )
                            goto LABEL_7;
                          v30 = v5;
                          v29 = 96;
                        }
                        else
                        {
                          updated = 0;
                          if ( !*(_QWORD *)(a1 + 32) )
                            goto LABEL_7;
                          v30 = v21;
                          v29 = 94;
                        }
                      }
                      else
                      {
                        *(_QWORD *)(a1 + 136) = 0;
                        v20 = GetLastError();
                        v5 = v20;
                        if ( v20 )
                        {
                          if ( v20 > 0 )
                            v5 = (unsigned __int16)v20 | 0x80070000;
                          updated = 0;
                          if ( v5 >= 0 )
                            goto LABEL_7;
                        }
                        else
                        {
                          v5 = -2147467259;
                          updated = 0;
                        }
                        if ( !*(_QWORD *)(a1 + 32) )
                          goto LABEL_7;
                        v30 = v5;
                        v29 = 92;
                      }
                    }
                    else
                    {
                      updated = 0;
                      if ( !*(_QWORD *)(a1 + 32) )
                        goto LABEL_7;
                      v30 = v17;
                      v29 = 90;
                    }
                  }
                  else
                  {
                    *(_QWORD *)(a1 + 128) = 0;
                    v16 = GetLastError();
                    v5 = v16;
                    if ( v16 )
                    {
                      if ( v16 > 0 )
                        v5 = (unsigned __int16)v16 | 0x80070000;
                      updated = 0;
                      if ( v5 >= 0 )
                        goto LABEL_7;
                    }
                    else
                    {
                      v5 = -2147467259;
                      updated = 0;
                    }
                    if ( !*(_QWORD *)(a1 + 32) )
                      goto LABEL_7;
                    v30 = v5;
                    v29 = 88;
                  }
                }
                else
                {
                  updated = 0;
                  if ( !*(_QWORD *)(a1 + 32) )
                    goto LABEL_7;
                  v30 = v13;
                  v29 = 86;
                }
              }
              else
              {
                updated = 0;
                if ( !*(_QWORD *)(a1 + 32) )
                  goto LABEL_7;
                v30 = v12;
                v29 = 84;
              }
            }
            else
            {
              updated = 0;
              if ( !*(_QWORD *)(a1 + 32) )
                goto LABEL_7;
              v30 = v11;
              v29 = 83;
            }
          }
          else
          {
            updated = 0;
            if ( !*(_QWORD *)(a1 + 32) )
              goto LABEL_7;
            v30 = v10;
            v29 = 82;
          }
        }
        else
        {
          updated = 0;
          if ( !*(_QWORD *)(a1 + 32) )
            goto LABEL_7;
          v30 = v9;
          v29 = 81;
        }
      }
      else
      {
        v8 = GetLastError();
        v5 = v8;
        if ( v8 )
        {
          if ( v8 > 0 )
            v5 = (unsigned __int16)v8 | 0x80070000;
          updated = 0;
          if ( v5 >= 0 )
            goto LABEL_7;
        }
        else
        {
          v5 = -2147467259;
          updated = 0;
        }
        if ( !*(_QWORD *)(a1 + 32) )
          goto LABEL_7;
        v30 = v5;
        v29 = 73;
      }
    }
    else
    {
      updated = 0;
      if ( !*(_QWORD *)(a1 + 32) )
        goto LABEL_7;
      v30 = v7;
      v29 = 67;
    }
    updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              *(_QWORD *)(a1 + 32),
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CScenarioCtrlUpgradeDesktop::Initialize",
                              v29,
                              v30,
                              -2,
                              *(_QWORD *)&EventAttributes.nLength,
                              EventAttributes.lpSecurityDescriptor,
                              *(_QWORD *)&EventAttributes.bInheritHandle);
LABEL_5:
    if ( (int)updated < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v6);
    goto LABEL_7;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x64,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\ScenarioCtrlUpgradeDesktopImpl.h",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x18006a090  mov     r11, rsp
0x18006a093  push    rbx
0x18006a094  push    rsi
0x18006a095  push    rdi
0x18006a096  push    r12
0x18006a098  push    r13
0x18006a09a  push    r14
0x18006a09c  push    r15
0x18006a09e  sub     rsp, 70h
0x18006a0a2  mov     qword ptr [r11-78h], 0FFFFFFFFFFFFFFFEh
0x18006a0aa  mov     rax, cs:__security_cookie
0x18006a0b1  xor     rax, rsp
0x18006a0b4  mov     [rsp+0A8h+var_40], rax
0x18006a0b9  mov     rbx, rdx
0x18006a0bc  mov     rsi, rcx
0x18006a0bf  xor     r13d, r13d
0x18006a0c2  mov     [r11-50h], r13
0x18006a0c6  mov     [r11-48h], r13
0x18006a0ca  xorps   xmm0, xmm0
0x18006a0cd  xor     eax, eax
0x18006a0cf  movups  xmmword ptr [rsp+0A8h+EventAttributes.nLength], xmm0
0x18006a0d4  mov     [r11-60h], rax
0x18006a0d8  mov     [r11-58h], r13d
0x18006a0dc  test    rdx, rdx
0x18006a0df  jnz     short loc_18006A12A
0x18006a0e1  mov     ecx, r13d
0x18006a0e4  mov     edi, 80070057h
0x18006a0e9  cmp     [rsi+20h], r13
0x18006a0ed  jz      short loc_18006A120
0x18006a0ef  mov     [rsp+0A8h+var_80], edi
0x18006a0f3  mov     [rsp+0A8h+var_88], 41h ; 'A'
0x18006a0fb  lea     r9, aCscenarioctrlu_0; "CScenarioCtrlUpgradeDesktop::Initialize"
0x18006a102  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006a109  lea     edx, [rbx+4]
0x18006a10c  mov     rcx, [rsi+20h]
0x18006a110  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18006a115  mov     ecx, eax
0x18006a117  test    ecx, ecx
0x18006a119  jns     short loc_18006A120
0x18006a11b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18006a120  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006a125  jmp     loc_18006A560
0x18006a12a  call    ?Initialize@CScenarioCtrlBase@@UEAAJPEAVIScenarioSession@@W4MoUpdateScenario@@@Z; CScenarioCtrlBase::Initialize(IScenarioSession *,MoUpdateScenario)
0x18006a12f  mov     edi, eax
0x18006a131  test    eax, eax
0x18006a133  jns     short loc_18006A16A
0x18006a135  mov     ecx, r13d
0x18006a138  cmp     [rsi+20h], r13
0x18006a13c  jz      short loc_18006A120
0x18006a13e  mov     [rsp+0A8h+var_80], eax
0x18006a142  mov     [rsp+0A8h+var_88], 43h ; 'C'
0x18006a14a  lea     r9, aCscenarioctrlu_0; "CScenarioCtrlUpgradeDesktop::Initialize"
0x18006a151  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18006a158  mov     edx, 4
0x18006a15d  mov     rcx, [rsi+20h]
0x18006a161  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18006a166  mov     ecx, eax
0x18006a168  jmp     short loc_18006A117
0x18006a16a  mov     [rsp+0A8h+SecurityDescriptorSize], r13d
0x18006a16f  lea     r9, [rsp+0A8h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18006a174  lea     r8, [rsp+0A8h+SecurityDescriptor]; SecurityDescriptor
0x18006a179  mov     edx, 1; StringSDRevision
0x18006a17e  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;BA)(A;;GA;;;OW)"
0x18006a185  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18006a18c  nop     dword ptr [rax+rax+00h]
0x18006a191  test    eax, eax
0x18006a193  jnz     short loc_18006A1E2
0x18006a195  call    cs:__imp_GetLastError
0x18006a19c  nop     dword ptr [rax+rax+00h]
0x18006a1a1  mov     edi, eax
0x18006a1a3  test    eax, eax
0x18006a1a5  jnz     short loc_18006A1B1
0x18006a1a7  mov     edi, 80004005h
0x18006a1ac  mov     ecx, r13d
0x18006a1af  jmp     short loc_18006A1C7
0x18006a1b1  jle     short loc_18006A1BC
0x18006a1b3  movzx   edi, ax
0x18006a1b6  or      edi, 80070000h
0x18006a1bc  mov     ecx, r13d
0x18006a1bf  test    edi, edi
0x18006a1c1  jns     loc_18006A120
0x18006a1c7  cmp     [rsi+20h], r13
0x18006a1cb  jz      loc_18006A120
0x18006a1d1  mov     [rsp+0A8h+var_80], edi
0x18006a1d5  mov     [rsp+0A8h+var_88], 49h ; 'I'
0x18006a1dd  jmp     loc_18006A14A
0x18006a1e2  mov     qword ptr [rsp+0A8h+EventAttributes.nLength], 18h
0x18006a1eb  mov     qword ptr [rsp+0A8h+EventAttributes.bInheritHandle], r13
0x18006a1f0  mov     rax, [rsp+0A8h+SecurityDescriptor]
0x18006a1f5  mov     [rsp+0A8h+EventAttributes.lpSecurityDescriptor], rax
0x18006a1fa  mov     rax, [rbx]
0x18006a1fd  lea     rdx, [rsp+0A8h+var_50]
0x18006a202  mov     rcx, rbx
0x18006a205  mov     rax, [rax+48h]
0x18006a209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a20e  mov     edi, eax
0x18006a210  test    eax, eax
0x18006a212  jns     short loc_18006A232
0x18006a214  mov     ecx, r13d
0x18006a217  cmp     [rsi+20h], r13
0x18006a21b  jz      loc_18006A120
0x18006a221  mov     [rsp+0A8h+var_80], eax
0x18006a225  mov     [rsp+0A8h+var_88], 51h ; 'Q'
0x18006a22d  jmp     loc_18006A14A
0x18006a232  mov     r8, [rsp+0A8h+var_50]
0x18006a237  lea     rdx, aCS; "C-%s"
0x18006a23e  lea     rcx, [rsi+50h]; wchar_t **
0x18006a242  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18006a247  mov     edi, eax
0x18006a249  test    eax, eax
0x18006a24b  jns     short loc_18006A26B
0x18006a24d  mov     ecx, r13d
0x18006a250  cmp     [rsi+20h], r13
0x18006a254  jz      loc_18006A120
0x18006a25a  mov     [rsp+0A8h+var_80], eax
0x18006a25e  mov     [rsp+0A8h+var_88], 52h ; 'R'
0x18006a266  jmp     loc_18006A14A
0x18006a26b  mov     r8, [rsp+0A8h+var_50]
0x18006a270  lea     rdx, aPS; "P-%s"
0x18006a277  lea     rcx, [rsi+58h]; wchar_t **
0x18006a27b  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18006a280  mov     edi, eax
0x18006a282  test    eax, eax
0x18006a284  jns     short loc_18006A2A4
0x18006a286  mov     ecx, r13d
0x18006a289  cmp     [rsi+20h], r13
0x18006a28d  jz      loc_18006A120
0x18006a293  mov     [rsp+0A8h+var_80], eax
0x18006a297  mov     [rsp+0A8h+var_88], 53h ; 'S'
0x18006a29f  jmp     loc_18006A14A
0x18006a2a4  mov     r8, [rsp+0A8h+var_50]
0x18006a2a9  lea     rdx, aSS_2; "S-%s"
0x18006a2b0  lea     rcx, [rsi+60h]; wchar_t **
0x18006a2b4  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18006a2b9  mov     edi, eax
0x18006a2bb  test    eax, eax
0x18006a2bd  jns     short loc_18006A2DD
0x18006a2bf  mov     ecx, r13d
0x18006a2c2  cmp     [rsi+20h], r13
0x18006a2c6  jz      loc_18006A120
0x18006a2cc  mov     [rsp+0A8h+var_80], eax
0x18006a2d0  mov     [rsp+0A8h+var_88], 54h ; 'T'
0x18006a2d8  jmp     loc_18006A14A
0x18006a2dd  mov     r9, [rsi+50h]
0x18006a2e1  lea     r8, aGlobalMosetup; "Global\\MoSetup"
0x18006a2e8  lea     rdx, aSS_0; "%s{%s}"
0x18006a2ef  lea     rcx, [rsi+68h]; wchar_t **
0x18006a2f3  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18006a2f8  mov     edi, eax
0x18006a2fa  test    eax, eax
0x18006a2fc  jns     short loc_18006A31C
0x18006a2fe  mov     ecx, r13d
0x18006a301  cmp     [rsi+20h], r13
0x18006a305  jz      loc_18006A120
0x18006a30b  mov     [rsp+0A8h+var_80], eax
0x18006a30f  mov     [rsp+0A8h+var_88], 56h ; 'V'
0x18006a317  jmp     loc_18006A14A
0x18006a31c  mov     r9, [rsi+68h]; lpName
0x18006a320  xor     r8d, r8d; bInitialState
0x18006a323  lea     r15d, [r8+1]
0x18006a327  mov     edx, r15d; bManualReset
0x18006a32a  lea     rcx, [rsp+0A8h+EventAttributes]; lpEventAttributes
0x18006a32f  call    cs:__imp_CreateEventW
0x18006a336  nop     dword ptr [rax+rax+00h]
0x18006a33b  mov     rbx, rax
0x18006a33e  mov     rcx, [rsi+80h]; hObject
0x18006a345  test    rcx, rcx
0x18006a348  jz      short loc_18006A356
0x18006a34a  call    cs:__imp_CloseHandle
0x18006a351  nop     dword ptr [rax+rax+00h]
0x18006a356  test    rbx, rbx
0x18006a359  jnz     short loc_18006A3AF
0x18006a35b  mov     [rsi+80h], r13
0x18006a362  call    cs:__imp_GetLastError
0x18006a369  nop     dword ptr [rax+rax+00h]
0x18006a36e  mov     edi, eax
0x18006a370  test    eax, eax
0x18006a372  jnz     short loc_18006A37E
0x18006a374  mov     edi, 80004005h
0x18006a379  mov     ecx, r13d
0x18006a37c  jmp     short loc_18006A394
0x18006a37e  jle     short loc_18006A389
0x18006a380  movzx   edi, ax
0x18006a383  or      edi, 80070000h
0x18006a389  mov     ecx, r13d
0x18006a38c  test    edi, edi
0x18006a38e  jns     loc_18006A120
0x18006a394  cmp     [rsi+20h], r13
0x18006a398  jz      loc_18006A120
0x18006a39e  mov     [rsp+0A8h+var_80], edi
0x18006a3a2  mov     [rsp+0A8h+var_88], 58h ; 'X'
0x18006a3aa  jmp     loc_18006A14A
0x18006a3af  mov     [rsi+80h], rbx
0x18006a3b6  mov     r9, [rsi+58h]
0x18006a3ba  lea     r8, aGlobalMosetup; "Global\\MoSetup"
0x18006a3c1  lea     rdx, aSS_0; "%s{%s}"
0x18006a3c8  lea     rcx, [rsi+70h]; wchar_t **
0x18006a3cc  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18006a3d1  mov     edi, eax
0x18006a3d3  test    eax, eax
0x18006a3d5  jns     short loc_18006A3F5
0x18006a3d7  mov     ecx, r13d
0x18006a3da  cmp     [rsi+20h], r13
0x18006a3de  jz      loc_18006A120
0x18006a3e4  mov     [rsp+0A8h+var_80], eax
0x18006a3e8  mov     [rsp+0A8h+var_88], 5Ah ; 'Z'
0x18006a3f0  jmp     loc_18006A14A
0x18006a3f5  mov     r9, [rsi+70h]; lpName
0x18006a3f9  xor     r8d, r8d; bInitialState
0x18006a3fc  mov     edx, r15d; bManualReset
0x18006a3ff  lea     rcx, [rsp+0A8h+EventAttributes]; lpEventAttributes
0x18006a404  call    cs:__imp_CreateEventW
0x18006a40b  nop     dword ptr [rax+rax+00h]
0x18006a410  mov     rbx, rax
0x18006a413  mov     rcx, [rsi+88h]; hObject
0x18006a41a  test    rcx, rcx
0x18006a41d  jz      short loc_18006A42B
0x18006a41f  call    cs:__imp_CloseHandle
0x18006a426  nop     dword ptr [rax+rax+00h]
0x18006a42b  test    rbx, rbx
0x18006a42e  jnz     short loc_18006A484
0x18006a430  mov     [rsi+88h], r13
0x18006a437  call    cs:__imp_GetLastError
0x18006a43e  nop     dword ptr [rax+rax+00h]
0x18006a443  mov     edi, eax
0x18006a445  test    eax, eax
0x18006a447  jnz     short loc_18006A453
0x18006a449  mov     edi, 80004005h
0x18006a44e  mov     ecx, r13d
0x18006a451  jmp     short loc_18006A469
0x18006a453  jle     short loc_18006A45E
0x18006a455  movzx   edi, ax
0x18006a458  or      edi, 80070000h
0x18006a45e  mov     ecx, r13d
0x18006a461  test    edi, edi
0x18006a463  jns     loc_18006A120
0x18006a469  cmp     [rsi+20h], r13
0x18006a46d  jz      loc_18006A120
0x18006a473  mov     [rsp+0A8h+var_80], edi
0x18006a477  mov     [rsp+0A8h+var_88], 5Ch ; '\'
0x18006a47f  jmp     loc_18006A14A
0x18006a484  mov     [rsi+88h], rbx
0x18006a48b  mov     r9, [rsi+60h]
0x18006a48f  lea     r8, aGlobalMosetup; "Global\\MoSetup"
0x18006a496  lea     rdx, aSS_0; "%s{%s}"
0x18006a49d  lea     rcx, [rsi+78h]; wchar_t **
0x18006a4a1  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18006a4a6  mov     edi, eax
0x18006a4a8  test    eax, eax
0x18006a4aa  jns     short loc_18006A4CA
0x18006a4ac  mov     ecx, r13d
0x18006a4af  cmp     [rsi+20h], r13
0x18006a4b3  jz      loc_18006A120
0x18006a4b9  mov     [rsp+0A8h+var_80], eax
0x18006a4bd  mov     [rsp+0A8h+var_88], 5Eh ; '^'
0x18006a4c5  jmp     loc_18006A14A
0x18006a4ca  mov     r9, [rsi+78h]; lpName
0x18006a4ce  xor     r8d, r8d; bInitialState
0x18006a4d1  mov     edx, r15d; bManualReset
0x18006a4d4  lea     rcx, [rsp+0A8h+EventAttributes]; lpEventAttributes
0x18006a4d9  call    cs:__imp_CreateEventW
0x18006a4e0  nop     dword ptr [rax+rax+00h]
0x18006a4e5  mov     rbx, rax
0x18006a4e8  mov     rcx, [rsi+90h]; hObject
0x18006a4ef  test    rcx, rcx
0x18006a4f2  jz      short loc_18006A500
0x18006a4f4  call    cs:__imp_CloseHandle
0x18006a4fb  nop     dword ptr [rax+rax+00h]
0x18006a500  test    rbx, rbx
0x18006a503  jnz     short loc_18006A559
0x18006a505  mov     [rsi+90h], r13
0x18006a50c  call    cs:__imp_GetLastError
0x18006a513  nop     dword ptr [rax+rax+00h]
0x18006a518  mov     edi, eax
0x18006a51a  test    eax, eax
0x18006a51c  jnz     short loc_18006A528
0x18006a51e  mov     edi, 80004005h
0x18006a523  mov     ecx, r13d
0x18006a526  jmp     short loc_18006A53E
0x18006a528  jle     short loc_18006A533
0x18006a52a  movzx   edi, ax
0x18006a52d  or      edi, 80070000h
0x18006a533  mov     ecx, r13d
0x18006a536  test    edi, edi
0x18006a538  jns     loc_18006A120
0x18006a53e  cmp     [rsi+20h], r13
0x18006a542  jz      loc_18006A120
0x18006a548  mov     [rsp+0A8h+var_80], edi
0x18006a54c  mov     [rsp+0A8h+var_88], 60h ; '`'
0x18006a554  jmp     loc_18006A14A
0x18006a559  mov     [rsi+90h], rbx
0x18006a560  mov     ecx, edi
0x18006a562  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18006a567  nop
0x18006a568  mov     rcx, [rsp+0A8h+SecurityDescriptor]; hMem
0x18006a56d  test    rcx, rcx
0x18006a570  jz      short loc_18006A583
0x18006a572  call    cs:__imp_LocalFree
0x18006a579  nop     dword ptr [rax+rax+00h]
0x18006a57e  mov     [rsp+0A8h+SecurityDescriptor], r13
  ... truncated ...
```
