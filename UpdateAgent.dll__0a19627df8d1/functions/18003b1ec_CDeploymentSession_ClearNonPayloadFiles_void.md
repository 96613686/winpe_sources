# CDeploymentSession::ClearNonPayloadFiles(void)

- ea: `0x18003b1ec`
- end: `0x18003b498`
- name: `?ClearNonPayloadFiles@CDeploymentSession@@QEAAJXZ`
- size: `684`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025a50`

## callees

- `0x18003b1ec`
- `0x18003c418`
- `0x180077664`
- `0x180078b9c`
- `0x18008b360`
- `0x18008b38c`
- `0x18009f0b0`
- `0x180223ec8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003b2de`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003b3f4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003b2de`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003b3f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b276`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b310`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b38c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b426`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b45c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b276`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b310`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b38c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b426`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b45c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b28b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b325`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b3a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b43b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b471`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b28b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b325`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b3a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b43b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b471`

## string_xrefs

- `0x18003b25a`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18003b2f3`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18003b370`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18003b409`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18003b239`: `windlp.state.xml`
- `0x18003b34f`: `windlp.state-old.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeploymentSession::ClearNonPayloadFiles(CDeploymentSession *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // edi
  const char *v5; // r9
  LPCWSTR v6; // rbx
  HANDLE v7; // rax
  __int64 result; // rax
  __int64 v9; // rcx
  const char *v10; // r9
  unsigned int v11; // edi
  LPCWSTR v12; // rbx
  HANDLE v13; // rax
  int v14; // eax
  unsigned int v15; // edi
  LPCWSTR v16; // rbx
  HANDLE v17; // rax
  __int64 v18; // rcx
  unsigned int LastError; // edi
  LPCWSTR v20; // rbx
  HANDLE v21; // rax
  LPCWSTR v22; // rbx
  HANDLE ProcessHeap; // rax
  LPCWSTR lpFileName[3]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  lpFileName[1] = (LPCWSTR)-2LL;
  try
  {
    v2 = *((_QWORD *)this + 75);
    if ( v2 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v2, 2, L"Deleting non payload files from sandbox.");
    lpFileName[0] = 0;
    _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(lpFileName);
    v3 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), (__int64)L"windlp.state.xml", 0);
    v4 = v3;
    if ( v3 >= 0 )
    {
      if ( !(unsigned int)FileExists(lpFileName[0]) )
        goto LABEL_15;
      v9 = *((_QWORD *)this + 75);
      if ( v9 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v9, 2, L"Deleting %s", lpFileName[0]);
      if ( DeleteFileW(lpFileName[0]) )
      {
LABEL_15:
        _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(lpFileName);
        v14 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 61), (__int64)L"windlp.state-old.xml", 0);
        v15 = v14;
        if ( v14 >= 0 )
        {
          if ( !(unsigned int)FileExists(lpFileName[0]) )
            goto LABEL_26;
          v18 = *((_QWORD *)this + 75);
          if ( v18 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v18, 2, L"Deleting %s", lpFileName[0]);
          if ( DeleteFileW(lpFileName[0]) )
          {
LABEL_26:
            v22 = lpFileName[0];
            if ( lpFileName[0] )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, (LPVOID)(v22 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            result = 0;
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x21E8,
                          (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                          v5);
            v20 = lpFileName[0];
            if ( lpFileName[0] )
            {
              v21 = GetProcessHeap();
              HeapFree(v21, 0, (LPVOID)(v20 - 2));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            result = LastError;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21E4,
            (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
            (const char *)(unsigned int)v14,
            (int)lpFileName[0]);
          v16 = lpFileName[0];
          if ( lpFileName[0] )
          {
            v17 = GetProcessHeap();
            HeapFree(v17, 0, (LPVOID)(v16 - 2));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
          result = v15;
        }
      }
      else
      {
        v11 = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x21E1,
                (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                v10);
        v12 = lpFileName[0];
        if ( lpFileName[0] )
        {
          v13 = GetProcessHeap();
          HeapFree(v13, 0, (LPVOID)(v12 - 2));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        result = v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21DD,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)v3,
        (int)lpFileName[0]);
      v6 = lpFileName[0];
      if ( lpFileName[0] )
      {
        v7 = GetProcessHeap();
        HeapFree(v7, 0, (LPVOID)(v6 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      result = v4;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x21ED,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x18003b1ec  push    rdi
0x18003b1ee  sub     rsp, 30h
0x18003b1f2  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFEh
0x18003b1fb  mov     [rsp+38h+arg_8], rbx
0x18003b200  mov     rbx, rcx
0x18003b203  mov     rcx, [rcx+258h]
0x18003b20a  test    rcx, rcx
0x18003b20d  jz      short loc_18003B220
0x18003b20f  lea     r8, aDeletingNonPay; "Deleting non payload files from sandbox"...
0x18003b216  mov     edx, 2
0x18003b21b  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003b220  mov     [rsp+38h+lpFileName], 0; int
0x18003b229  lea     rcx, [rsp+38h+lpFileName]
0x18003b22e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x18003b233  mov     r9, rax
0x18003b236  xor     r8d, r8d
0x18003b239  lea     rdx, aWindlpStateXml; "windlp.state.xml"
0x18003b240  mov     rcx, [rbx+1E8h]
0x18003b247  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18003b24c  mov     edi, eax
0x18003b24e  test    eax, eax
0x18003b250  jns     short loc_18003B2A5
0x18003b252  mov     rcx, [rsp+38h]; this
0x18003b257  mov     r9d, eax; char *
0x18003b25a  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18003b261  mov     edx, 21DDh; void *
0x18003b266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b26b  nop
0x18003b26c  mov     rbx, [rsp+38h+lpFileName]
0x18003b271  test    rbx, rbx
0x18003b274  jz      short loc_18003B29E
0x18003b276  call    cs:__imp_GetProcessHeap
0x18003b27d  nop     dword ptr [rax+rax+00h]
0x18003b282  mov     rcx, rax; hHeap
0x18003b285  lea     r8, [rbx-4]; lpMem
0x18003b289  xor     edx, edx; dwFlags
0x18003b28b  call    cs:__imp_HeapFree
0x18003b292  nop     dword ptr [rax+rax+00h]
0x18003b297  xor     ecx, ecx
0x18003b299  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b29e  mov     eax, edi
0x18003b2a0  jmp     loc_18003B48C
0x18003b2a5  mov     rcx, [rsp+38h+lpFileName]
0x18003b2aa  call    FileExists
0x18003b2af  test    eax, eax
0x18003b2b1  jz      loc_18003B33F
0x18003b2b7  mov     rcx, [rbx+258h]
0x18003b2be  test    rcx, rcx
0x18003b2c1  jz      short loc_18003B2D9
0x18003b2c3  mov     r9, [rsp+38h+lpFileName]
0x18003b2c8  lea     r8, aDeletingS; "Deleting %s"
0x18003b2cf  mov     edx, 2
0x18003b2d4  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003b2d9  mov     rcx, [rsp+38h+lpFileName]; lpFileName
0x18003b2de  call    cs:__imp_DeleteFileW
0x18003b2e5  nop     dword ptr [rax+rax+00h]
0x18003b2ea  test    eax, eax
0x18003b2ec  jnz     short loc_18003B33F
0x18003b2ee  mov     rcx, [rsp+38h]; this
0x18003b2f3  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18003b2fa  mov     edx, 21E1h; void *
0x18003b2ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b304  mov     edi, eax
0x18003b306  mov     rbx, [rsp+38h+lpFileName]
0x18003b30b  test    rbx, rbx
0x18003b30e  jz      short loc_18003B338
0x18003b310  call    cs:__imp_GetProcessHeap
0x18003b317  nop     dword ptr [rax+rax+00h]
0x18003b31c  mov     rcx, rax; hHeap
0x18003b31f  lea     r8, [rbx-4]; lpMem
0x18003b323  xor     edx, edx; dwFlags
0x18003b325  call    cs:__imp_HeapFree
0x18003b32c  nop     dword ptr [rax+rax+00h]
0x18003b331  xor     ecx, ecx
0x18003b333  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b338  mov     eax, edi
0x18003b33a  jmp     loc_18003B48C
0x18003b33f  lea     rcx, [rsp+38h+lpFileName]
0x18003b344  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x18003b349  mov     r9, rax
0x18003b34c  xor     r8d, r8d
0x18003b34f  lea     rdx, aWindlpStateOld; "windlp.state-old.xml"
0x18003b356  mov     rcx, [rbx+1E8h]
0x18003b35d  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18003b362  mov     edi, eax
0x18003b364  test    eax, eax
0x18003b366  jns     short loc_18003B3BB
0x18003b368  mov     rcx, [rsp+38h]; this
0x18003b36d  mov     r9d, eax; char *
0x18003b370  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18003b377  mov     edx, 21E4h; void *
0x18003b37c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b381  nop
0x18003b382  mov     rbx, [rsp+38h+lpFileName]
0x18003b387  test    rbx, rbx
0x18003b38a  jz      short loc_18003B3B4
0x18003b38c  call    cs:__imp_GetProcessHeap
0x18003b393  nop     dword ptr [rax+rax+00h]
0x18003b398  mov     rcx, rax; hHeap
0x18003b39b  lea     r8, [rbx-4]; lpMem
0x18003b39f  xor     edx, edx; dwFlags
0x18003b3a1  call    cs:__imp_HeapFree
0x18003b3a8  nop     dword ptr [rax+rax+00h]
0x18003b3ad  xor     ecx, ecx
0x18003b3af  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b3b4  mov     eax, edi
0x18003b3b6  jmp     loc_18003B48C
0x18003b3bb  mov     rcx, [rsp+38h+lpFileName]
0x18003b3c0  call    FileExists
0x18003b3c5  test    eax, eax
0x18003b3c7  jz      loc_18003B452
0x18003b3cd  mov     rcx, [rbx+258h]
0x18003b3d4  test    rcx, rcx
0x18003b3d7  jz      short loc_18003B3EF
0x18003b3d9  mov     r9, [rsp+38h+lpFileName]
0x18003b3de  lea     r8, aDeletingS; "Deleting %s"
0x18003b3e5  mov     edx, 2
0x18003b3ea  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003b3ef  mov     rcx, [rsp+38h+lpFileName]; lpFileName
0x18003b3f4  call    cs:__imp_DeleteFileW
0x18003b3fb  nop     dword ptr [rax+rax+00h]
0x18003b400  test    eax, eax
0x18003b402  jnz     short loc_18003B452
0x18003b404  mov     rcx, [rsp+38h]; this
0x18003b409  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18003b410  mov     edx, 21E8h; void *
0x18003b415  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b41a  mov     edi, eax
0x18003b41c  mov     rbx, [rsp+38h+lpFileName]
0x18003b421  test    rbx, rbx
0x18003b424  jz      short loc_18003B44E
0x18003b426  call    cs:__imp_GetProcessHeap
0x18003b42d  nop     dword ptr [rax+rax+00h]
0x18003b432  mov     rcx, rax; hHeap
0x18003b435  lea     r8, [rbx-4]; lpMem
0x18003b439  xor     edx, edx; dwFlags
0x18003b43b  call    cs:__imp_HeapFree
0x18003b442  nop     dword ptr [rax+rax+00h]
0x18003b447  xor     ecx, ecx
0x18003b449  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b44e  mov     eax, edi
0x18003b450  jmp     short loc_18003B48C
0x18003b452  mov     rbx, [rsp+38h+lpFileName]
0x18003b457  test    rbx, rbx
0x18003b45a  jz      short loc_18003B484
0x18003b45c  call    cs:__imp_GetProcessHeap
0x18003b463  nop     dword ptr [rax+rax+00h]
0x18003b468  mov     rcx, rax; hHeap
0x18003b46b  lea     r8, [rbx-4]; lpMem
0x18003b46f  xor     edx, edx; dwFlags
0x18003b471  call    cs:__imp_HeapFree
0x18003b478  nop     dword ptr [rax+rax+00h]
0x18003b47d  xor     ecx, ecx
0x18003b47f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b484  xor     eax, eax
0x18003b486  jmp     short loc_18003B48C
0x18003b488  mov     eax, dword ptr [rsp+38h+lpFileName]
0x18003b48c  mov     rbx, [rsp+38h+arg_8]
0x18003b491  add     rsp, 30h
0x18003b495  pop     rdi
0x18003b496  retn
```
