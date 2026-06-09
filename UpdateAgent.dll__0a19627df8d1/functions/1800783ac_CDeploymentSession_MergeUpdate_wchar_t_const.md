# CDeploymentSession::MergeUpdate(wchar_t const *)

- ea: `0x1800783ac`
- end: `0x1800789eb`
- name: `?MergeUpdate@CDeploymentSession@@QEAAJPEB_W@Z`
- size: `1599`
- prototype: `int(CDeploymentSession *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002efc0`

## callees

- `0x180039f90`
- `0x18003c418`
- `0x180077664`
- `0x1800783ac`
- `0x180078b9c`
- `0x18008c4c4`
- `0x1800acd88`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180078451`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180078451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800786c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800786ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800788f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078923`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078967`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007899e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800786c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800786ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800788f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078923`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078967`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007899e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800786de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007890a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007897c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800789b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800786de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078714`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007890a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180078938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007897c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800789b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800785d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800785d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078847`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180078837`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x180078837`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800785c1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800785c1`

## string_xrefs

- `0x180078421`: `CDeploymentSession::MergeUpdate`
- `0x1800784a9`: `CDeploymentSession::MergeUpdate`
- `0x180078569`: `CDeploymentSession::MergeUpdate`
- `0x18007876b`: `CDeploymentSession::MergeUpdate`
- `0x1800787d7`: `CDeploymentSession::MergeUpdate`
- `0x180078891`: `CDeploymentSession::MergeUpdate`
- `0x1800784c1`: `MergeUpdate: MergedSandBoxPath [%s]`
- `0x1800784fe`: `ActionList_%s.xml`
- `0x1800785a3`: `MergeUpdate: Copying ActionList to [%s]`
- `0x18007862f`: `MergeUpdate: Calling Arbiter to load the ActionList`
- `0x18007881b`: `MergeUpdate: Moving File: [%s]`
- `0x1800788d2`: `MergeUpdate: Update successfully merged`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDeploymentSession::MergeUpdate(CDeploymentSession *this, const wchar_t *a2)
{
  __int64 v4; // rcx
  signed int v5; // edi
  __int64 updated; // rcx
  DWORD FileAttributesW; // ebx
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  __int64 v12; // r8
  signed int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // r12d
  __int64 v17; // rcx
  unsigned int i; // r13d
  __int64 v19; // rbx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  signed int LastError; // eax
  __int64 v25; // rax
  __int64 v26; // rcx
  const char *v27; // r9
  wchar_t *v28; // rbx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  int v31; // [rsp+20h] [rbp-88h]
  int v32; // [rsp+28h] [rbp-80h]
  __int64 v33; // [rsp+48h] [rbp-60h] BYREF
  wchar_t *v34; // [rsp+50h] [rbp-58h] BYREF
  __int64 v35; // [rsp+58h] [rbp-50h]
  __int64 v36; // [rsp+60h] [rbp-48h]
  const wchar_t *v37; // [rsp+68h] [rbp-40h]
  __int64 v38; // [rsp+70h] [rbp-38h]
  __int64 v39; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v39 = -2;
  try
  {
    v37 = a2;
    v34 = 0;
    v33 = 0;
    if ( a2 )
    {
      FileAttributesW = GetFileAttributesW(a2);
      if ( FileAttributesW == -1 )
        v8 = 0;
      else
        v8 = (FileAttributesW >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      v9 = *((_QWORD *)this + 75);
      if ( v8 )
      {
        if ( v9 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v9, 2, L"MergeUpdate: MergedSandBoxPath [%s]", a2);
        if ( *((_QWORD *)this + 9) )
        {
          v10 = STRAPI_Format(&v34, L"ActionList_%s.xml");
          v5 = v10;
          if ( v10 >= 0 )
          {
            v11 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)a2, (__int64)v34, 0);
            v5 = v11;
            updated = *((_QWORD *)this + 75);
            if ( v11 < 0 )
            {
              if ( updated )
              {
                updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                          updated,
                                          4,
                                          L"%s(%d): Result = 0x%X",
                                          L"CDeploymentSession::MergeUpdate",
                                          5378,
                                          v11);
LABEL_27:
                if ( (int)updated < 0 )
                  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
              }
              goto LABEL_58;
            }
            if ( updated )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(updated, 2, L"MergeUpdate: Copying ActionList to [%s]", 0);
            if ( CopyFileW(*((LPCWSTR *)this + 63), 0, 0) )
            {
              v14 = *((_QWORD *)this + 75);
              if ( v14 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v14,
                  2,
                  L"MergeUpdate: Calling Arbiter to load the ActionList");
              v15 = LoadActionList(0, *((_QWORD *)this + 63), v12, &v33);
              v5 = v15;
              if ( v15 >= 0 )
              {
                v16 = 0;
LABEL_46:
                if ( v16 >= *(_DWORD *)(v33 + 72) )
                {
                  v26 = *((_QWORD *)this + 75);
                  if ( v26 )
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v26, 2, L"MergeUpdate: Update successfully merged");
                  goto LABEL_73;
                }
                v17 = *(_QWORD *)(v33 + 64) + 168LL * v16;
                v38 = v17;
                for ( i = 0; ; ++i )
                {
                  if ( i >= *(_DWORD *)(v17 + 120) )
                  {
                    ++v16;
                    goto LABEL_46;
                  }
                  v36 = 184LL * i;
                  v35 = *(_QWORD *)(v17 + 112);
                  v19 = v35;
                  v20 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), *(_QWORD *)(v36 + v35 + 24), 0);
                  v5 = v20;
                  if ( v20 < 0 )
                  {
                    updated = *((_QWORD *)this + 75);
                    if ( updated )
                    {
                      v21 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              updated,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::MergeUpdate",
                              5398,
                              v20);
                      updated = (unsigned int)v21;
                      if ( v21 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v21);
                    }
                    goto LABEL_58;
                  }
                  v22 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)v37, *(_QWORD *)(v36 + v19 + 24), 0);
                  v5 = v22;
                  updated = *((_QWORD *)this + 75);
                  if ( v22 < 0 )
                  {
                    if ( updated )
                    {
                      v23 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              updated,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::MergeUpdate",
                              5399,
                              v22);
                      updated = (unsigned int)v23;
                      if ( v23 < 0 )
                        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v23);
                    }
                    goto LABEL_58;
                  }
                  if ( updated )
                    CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(updated, 2, L"MergeUpdate: Moving File: [%s]", 0);
                  if ( !MoveFileW(0, 0) )
                    break;
                  v17 = v38;
                }
                LastError = GetLastError();
                v5 = LastError;
                if ( LastError )
                {
                  if ( LastError > 0 )
                    v5 = (unsigned __int16)LastError | 0x80070000;
                }
                else
                {
                  v5 = -2147467259;
                }
                v25 = *((_QWORD *)this + 75);
                updated = 0;
                if ( v5 < 0 && v25 )
                {
                  updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                            v25,
                                            4,
                                            L"%s(%d): Result = 0x%X",
                                            L"CDeploymentSession::MergeUpdate",
                                            5402,
                                            v5);
                  goto LABEL_27;
                }
LABEL_58:
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_73:
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
                if ( v33 )
                  (**(void (__fastcall ***)(__int64))v33)(v33);
                if ( v34 )
                {
                  v28 = v34 - 2;
                  ProcessHeap = GetProcessHeap();
                  HeapFree(ProcessHeap, 0, v28);
                  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
                }
                return (unsigned int)v5;
              }
              v9 = *((_QWORD *)this + 75);
              if ( !v9 )
              {
LABEL_4:
                updated = 0;
                goto LABEL_58;
              }
              v32 = v15;
              v31 = 5387;
            }
            else
            {
              v13 = GetLastError();
              v5 = v13;
              if ( v13 )
              {
                if ( v13 > 0 )
                  v5 = (unsigned __int16)v13 | 0x80070000;
              }
              else
              {
                v5 = -2147467259;
              }
              updated = 0;
              if ( v5 >= 0 || !*((_QWORD *)this + 75) )
                goto LABEL_58;
              v32 = v5;
              v31 = 5380;
              v9 = *((_QWORD *)this + 75);
            }
          }
          else
          {
            v9 = *((_QWORD *)this + 75);
            if ( !v9 )
              goto LABEL_4;
            v32 = v10;
            v31 = 5377;
          }
        }
        else
        {
          v9 = *((_QWORD *)this + 75);
          v5 = -2147418113;
          if ( !v9 )
            goto LABEL_4;
          v32 = -2147418113;
          v31 = 5376;
        }
      }
      else
      {
        v5 = -2147024893;
        if ( !v9 )
          goto LABEL_4;
        v32 = -2147024893;
        v31 = 5368;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v9,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::MergeUpdate",
                                v31,
                                v32);
    }
    else
    {
      v4 = *((_QWORD *)this + 75);
      v5 = -2147024809;
      if ( !v4 )
        goto LABEL_4;
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v4,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::MergeUpdate",
                                5366,
                                -2147024809);
    }
    if ( (int)updated < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated);
    goto LABEL_58;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1522,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v27);
  }
  return result;
}

```

## disassembly

```asm
0x1800783ac  mov     rax, rsp
0x1800783af  push    rdi
0x1800783b0  push    r12
0x1800783b2  push    r13
0x1800783b4  push    r14
0x1800783b6  push    r15
0x1800783b8  sub     rsp, 80h
0x1800783bf  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFEh
0x1800783c7  mov     [rax+18h], rbx
0x1800783cb  mov     [rax+20h], rsi
0x1800783cf  mov     r12, rdx
0x1800783d2  mov     [rsp+0A8h+var_40], rdx
0x1800783d7  mov     rsi, rcx
0x1800783da  xor     edx, edx
0x1800783dc  mov     [rax-58h], rdx
0x1800783e0  xor     r13d, r13d
0x1800783e3  mov     [rax-78h], r13
0x1800783e7  xor     ebx, ebx
0x1800783e9  mov     [rax-60h], rbx
0x1800783ed  xor     r14d, r14d
0x1800783f0  mov     [rax-70h], r14
0x1800783f4  xor     r15d, r15d
0x1800783f7  mov     [rax-68h], r15
0x1800783fb  test    r12, r12
0x1800783fe  jnz     short loc_18007844E
0x180078400  mov     rcx, [rcx+258h]
0x180078407  mov     edi, 80070057h
0x18007840c  test    rcx, rcx
0x18007840f  jnz     short loc_180078415
0x180078411  xor     ecx, ecx
0x180078413  jmp     short loc_180078444
0x180078415  mov     [rsp+0A8h+var_80], edi
0x180078419  mov     [rsp+0A8h+var_88], 14F6h
0x180078421  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x180078428  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18007842f  mov     edx, 4
0x180078434  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180078439  mov     ecx, eax
0x18007843b  test    ecx, ecx
0x18007843d  jns     short loc_180078444
0x18007843f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180078444  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078449  jmp     loc_1800788E8
0x18007844e  mov     rcx, r12; lpFileName
0x180078451  call    cs:__imp_GetFileAttributesW
0x180078458  nop     dword ptr [rax+rax+00h]
0x18007845d  mov     ebx, eax
0x18007845f  cmp     eax, 0FFFFFFFFh
0x180078462  jz      short loc_18007846C
0x180078464  shr     ebx, 4
0x180078467  and     ebx, 1
0x18007846a  jmp     short loc_18007846E
0x18007846c  xor     ebx, ebx
0x18007846e  xor     ecx, ecx
0x180078470  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078475  xor     ecx, ecx
0x180078477  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007847c  mov     rcx, [rsi+258h]
0x180078483  test    ebx, ebx
0x180078485  jnz     short loc_1800784B9
0x180078487  mov     edi, 80070003h
0x18007848c  test    rcx, rcx
0x18007848f  jz      short loc_180078411
0x180078491  mov     [rsp+0A8h+var_80], edi
0x180078495  mov     [rsp+0A8h+var_88], 14F8h
0x18007849d  mov     edx, 4
0x1800784a2  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800784a9  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x1800784b0  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800784b5  mov     ecx, eax
0x1800784b7  jmp     short loc_18007843B
0x1800784b9  test    rcx, rcx
0x1800784bc  jz      short loc_1800784D2
0x1800784be  mov     r9, r12
0x1800784c1  lea     r8, aMergeupdateMer; "MergeUpdate: MergedSandBoxPath [%s]"
0x1800784c8  mov     edx, 2
0x1800784cd  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800784d2  mov     r8, [rsi+48h]
0x1800784d6  test    r8, r8
0x1800784d9  jnz     short loc_1800784FE
0x1800784db  mov     rcx, [rsi+258h]
0x1800784e2  mov     edi, 8000FFFFh
0x1800784e7  test    rcx, rcx
0x1800784ea  jz      loc_180078411
0x1800784f0  mov     [rsp+0A8h+var_80], edi
0x1800784f4  mov     [rsp+0A8h+var_88], 1500h
0x1800784fc  jmp     short loc_18007849D
0x1800784fe  lea     rdx, aActionlistSXml; "ActionList_%s.xml"
0x180078505  lea     rcx, [rsp+0A8h+var_58]; wchar_t **
0x18007850a  call    ?STRAPI_Format@@YAJPEAPEA_WPEB_WZZ; STRAPI_Format(wchar_t * *,wchar_t const *,...)
0x18007850f  mov     edi, eax
0x180078511  test    eax, eax
0x180078513  jns     short loc_180078536
0x180078515  mov     rcx, [rsi+258h]
0x18007851c  test    rcx, rcx
0x18007851f  jz      loc_180078411
0x180078525  mov     [rsp+0A8h+var_80], eax
0x180078529  mov     [rsp+0A8h+var_88], 1501h
0x180078531  jmp     loc_18007849D
0x180078536  lea     r9, [rsp+0A8h+lpNewFileName]
0x18007853b  xor     r8d, r8d
0x18007853e  mov     rdx, [rsp+0A8h+var_58]
0x180078543  mov     rcx, r12
0x180078546  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18007854b  mov     edi, eax
0x18007854d  mov     rcx, [rsi+258h]
0x180078554  test    eax, eax
0x180078556  jns     short loc_180078596
0x180078558  test    rcx, rcx
0x18007855b  jz      short loc_18007858C
0x18007855d  mov     [rsp+0A8h+var_80], eax
0x180078561  mov     [rsp+0A8h+var_88], 1502h
0x180078569  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x180078570  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180078577  mov     edx, 4
0x18007857c  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180078581  mov     ecx, eax
0x180078583  test    ecx, ecx
0x180078585  jns     short loc_18007858C
0x180078587  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18007858c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078591  jmp     loc_1800788E3
0x180078596  mov     r13, [rsp+0A8h+lpNewFileName]
0x18007859b  test    rcx, rcx
0x18007859e  jz      short loc_1800785B4
0x1800785a0  mov     r9, r13
0x1800785a3  lea     r8, aMergeupdateCop; "MergeUpdate: Copying ActionList to [%s]"
0x1800785aa  mov     edx, 2
0x1800785af  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800785b4  xor     r8d, r8d; bFailIfExists
0x1800785b7  mov     rdx, r13; lpNewFileName
0x1800785ba  mov     rcx, [rsi+1F8h]; lpExistingFileName
0x1800785c1  call    cs:__imp_CopyFileW
0x1800785c8  nop     dword ptr [rax+rax+00h]
0x1800785cd  test    eax, eax
0x1800785cf  jnz     short loc_180078623
0x1800785d1  call    cs:__imp_GetLastError
0x1800785d8  nop     dword ptr [rax+rax+00h]
0x1800785dd  mov     edi, eax
0x1800785df  test    eax, eax
0x1800785e1  jnz     short loc_1800785EA
0x1800785e3  mov     edi, 80004005h
0x1800785e8  jmp     short loc_1800785F5
0x1800785ea  jle     short loc_1800785F5
0x1800785ec  movzx   edi, ax
0x1800785ef  or      edi, 80070000h
0x1800785f5  mov     rax, [rsi+258h]
0x1800785fc  xor     ecx, ecx
0x1800785fe  test    edi, edi
0x180078600  jns     loc_180078444
0x180078606  test    rax, rax
0x180078609  jz      loc_180078444
0x18007860f  mov     [rsp+0A8h+var_80], edi
0x180078613  mov     [rsp+0A8h+var_88], 1504h
0x18007861b  mov     rcx, rax
0x18007861e  jmp     loc_18007849D
0x180078623  mov     rcx, [rsi+258h]
0x18007862a  test    rcx, rcx
0x18007862d  jz      short loc_180078640
0x18007862f  lea     r8, aMergeupdateCal; "MergeUpdate: Calling Arbiter to load th"...
0x180078636  mov     edx, 2
0x18007863b  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180078640  lea     r9, [rsp+0A8h+var_60]
0x180078645  mov     rdx, [rsi+1F8h]
0x18007864c  xor     ecx, ecx
0x18007864e  call    LoadActionList
0x180078653  mov     edi, eax
0x180078655  test    eax, eax
0x180078657  jns     short loc_18007867A
0x180078659  mov     rcx, [rsi+258h]
0x180078660  test    rcx, rcx
0x180078663  jz      loc_180078411
0x180078669  mov     [rsp+0A8h+var_80], eax
0x18007866d  mov     [rsp+0A8h+var_88], 150Bh
0x180078675  jmp     loc_18007849D
0x18007867a  xor     r12d, r12d
0x18007867d  mov     rbx, [rsp+0A8h+var_60]
0x180078682  cmp     r12d, [rbx+48h]
0x180078686  jnb     loc_1800788C6
0x18007868c  mov     eax, r12d
0x18007868f  imul    rcx, rax, 0A8h
0x180078696  add     rcx, [rbx+40h]
0x18007869a  mov     [rsp+0A8h+var_38], rcx
0x18007869f  xor     r13d, r13d
0x1800786a2  cmp     r13d, [rcx+78h]
0x1800786a6  jnb     loc_1800788BE
0x1800786ac  mov     eax, r13d
0x1800786af  imul    rdi, rax, 0B8h
0x1800786b6  mov     [rsp+0A8h+var_48], rdi
0x1800786bb  mov     rax, [rcx+70h]
0x1800786bf  mov     [rsp+0A8h+var_50], rax
0x1800786c4  test    r14, r14
0x1800786c7  jz      short loc_1800786FA
0x1800786c9  call    cs:__imp_GetProcessHeap
0x1800786d0  nop     dword ptr [rax+rax+00h]
0x1800786d5  mov     rcx, rax; hHeap
0x1800786d8  lea     r8, [r14-4]; lpMem
0x1800786dc  xor     edx, edx; dwFlags
0x1800786de  call    cs:__imp_HeapFree
0x1800786e5  nop     dword ptr [rax+rax+00h]
0x1800786ea  xor     ecx, ecx
0x1800786ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800786f1  mov     [rsp+0A8h+lpExistingFileName], 0
0x1800786fa  test    r15, r15
0x1800786fd  jz      short loc_18007872F
0x1800786ff  call    cs:__imp_GetProcessHeap
0x180078706  nop     dword ptr [rax+rax+00h]
0x18007870b  mov     rcx, rax; hHeap
0x18007870e  lea     r8, [r15-4]; lpMem
0x180078712  xor     edx, edx; dwFlags
0x180078714  call    cs:__imp_HeapFree
0x18007871b  nop     dword ptr [rax+rax+00h]
0x180078720  xor     ecx, ecx
0x180078722  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078727  xor     r15d, r15d
0x18007872a  mov     [rsp+0A8h+var_68], r15
0x18007872f  lea     r9, [rsp+0A8h+lpExistingFileName]
0x180078734  xor     r8d, r8d
0x180078737  mov     rbx, [rsp+0A8h+var_50]
0x18007873c  mov     rdx, [rdi+rbx+18h]
0x180078741  mov     rcx, [rsi+1E8h]
0x180078748  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18007874d  mov     edi, eax
0x18007874f  test    eax, eax
0x180078751  jns     short loc_18007879D
0x180078753  mov     rcx, [rsi+258h]
0x18007875a  test    rcx, rcx
0x18007875d  jz      short loc_18007878E
0x18007875f  mov     [rsp+0A8h+var_80], eax
0x180078763  mov     [rsp+0A8h+var_88], 1516h
0x18007876b  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x180078772  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180078779  mov     edx, 4
0x18007877e  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x180078783  mov     ecx, eax
0x180078785  test    eax, eax
0x180078787  jns     short loc_18007878E
0x180078789  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18007878e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180078793  mov     r14, [rsp+0A8h+lpExistingFileName]
0x180078798  jmp     loc_1800788E3
0x18007879d  lea     r9, [rsp+0A8h+var_68]
0x1800787a2  xor     r8d, r8d
0x1800787a5  mov     rdx, [rsp+0A8h+var_48]
0x1800787aa  mov     rdx, [rdx+rbx+18h]
0x1800787af  mov     rcx, [rsp+0A8h+var_40]
0x1800787b4  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x1800787b9  mov     edi, eax
0x1800787bb  mov     rcx, [rsi+258h]
0x1800787c2  test    eax, eax
0x1800787c4  jns     short loc_18007880E
0x1800787c6  test    rcx, rcx
0x1800787c9  jz      short loc_1800787FA
0x1800787cb  mov     [rsp+0A8h+var_80], eax
0x1800787cf  mov     [rsp+0A8h+var_88], 1517h
0x1800787d7  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
0x1800787de  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800787e5  mov     edx, 4
0x1800787ea  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x1800787ef  mov     ecx, eax
0x1800787f1  test    eax, eax
0x1800787f3  jns     short loc_1800787FA
0x1800787f5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800787fa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800787ff  mov     r14, [rsp+0A8h+lpExistingFileName]
0x180078804  mov     r15, [rsp+0A8h+var_68]
0x180078809  jmp     loc_1800788E3
0x18007880e  mov     r14, [rsp+0A8h+lpExistingFileName]
0x180078813  test    rcx, rcx
0x180078816  jz      short loc_18007882C
0x180078818  mov     r9, r14
0x18007881b  lea     r8, aMergeupdateMov; "MergeUpdate: Moving File: [%s]"
0x180078822  mov     edx, 2
0x180078827  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18007882c  mov     r15, [rsp+0A8h+var_68]
0x180078831  mov     rdx, r15; lpNewFileName
0x180078834  mov     rcx, r14; lpExistingFileName
0x180078837  call    cs:__imp_MoveFileW
0x18007883e  nop     dword ptr [rax+rax+00h]
0x180078843  test    eax, eax
0x180078845  jnz     short loc_1800788B1
0x180078847  call    cs:__imp_GetLastError
0x18007884e  nop     dword ptr [rax+rax+00h]
0x180078853  mov     edi, eax
0x180078855  test    eax, eax
0x180078857  jnz     short loc_180078860
0x180078859  mov     edi, 80004005h
0x18007885e  jmp     short loc_18007886B
0x180078860  jle     short loc_18007886B
0x180078862  movzx   edi, ax
0x180078865  or      edi, 80070000h
0x18007886b  mov     rax, [rsi+258h]
0x180078872  xor     ecx, ecx
0x180078874  test    edi, edi
0x180078876  jns     loc_18007858C
0x18007887c  test    rax, rax
0x18007887f  jz      loc_18007858C
0x180078885  mov     [rsp+0A8h+var_80], edi
0x180078889  mov     [rsp+0A8h+var_88], 151Ah
0x180078891  lea     r9, aCdeploymentses_71; "CDeploymentSession::MergeUpdate"
  ... truncated ...
```
