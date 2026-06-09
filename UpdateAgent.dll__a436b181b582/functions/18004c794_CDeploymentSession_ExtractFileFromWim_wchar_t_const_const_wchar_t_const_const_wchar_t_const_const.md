# CDeploymentSession::ExtractFileFromWim(wchar_t const * const,wchar_t const * const,wchar_t const * const)

- ea: `0x18004c794`
- end: `0x18004ca8c`
- name: `?ExtractFileFromWim@CDeploymentSession@@AEAAJQEB_W00@Z`
- size: `760`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, const wchar_t *const, const wchar_t *const, const wchar_t *const)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18003dc94`
- `0x18007c740`

## callees

- `0x18004c794`
- `0x180066bd4`
- `0x180077664`
- `0x18008b360`
- `0x18008b38c`
- `0x18009f0b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c85b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c8d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c951`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c9e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ca37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c85b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c8d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c951`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c9e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ca37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c870`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c8e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c9f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ca4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c870`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c8e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c9f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004ca4c`
- `WIMGAPI!WIMCloseHandle` at `0x18004c887`
- `WIMGAPI!WIMCloseHandle` at `0x18004c900`
- `WIMGAPI!WIMCloseHandle` at `0x18004c97d`
- `WIMGAPI!WIMCloseHandle` at `0x18004c9ca`
- `WIMGAPI!WIMCloseHandle` at `0x18004ca0d`
- `WIMGAPI!WIMCloseHandle` at `0x18004ca20`
- `WIMGAPI!WIMCloseHandle` at `0x18004ca63`
- `WIMGAPI!WIMCloseHandle` at `0x18004c887`
- `WIMGAPI!WIMCloseHandle` at `0x18004c900`
- `WIMGAPI!WIMCloseHandle` at `0x18004c97d`
- `WIMGAPI!WIMCloseHandle` at `0x18004c9ca`
- `WIMGAPI!WIMCloseHandle` at `0x18004ca0d`
- `WIMGAPI!WIMCloseHandle` at `0x18004ca20`
- `WIMGAPI!WIMCloseHandle` at `0x18004ca63`
- `WIMGAPI!WIMExtractImagePath` at `0x18004c99f`
- `WIMGAPI!WIMExtractImagePath` at `0x18004c99f`
- `WIMGAPI!WIMCreateFile` at `0x18004c7e1`
- `WIMGAPI!WIMCreateFile` at `0x18004c7e1`
- `WIMGAPI!WIMLoadImage` at `0x18004c91b`
- `WIMGAPI!WIMLoadImage` at `0x18004c91b`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18004c8a2`
- `WIMGAPI!WIMSetTemporaryPath` at `0x18004c8a2`

## string_xrefs

- `0x18004c7ff`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18004c83f`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18004c8b7`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18004c934`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`
- `0x18004c9b4`: `onecore\base\ntsetup\conx\mosetup\updateagent\src\DeploymentSessionImpl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDeploymentSession::ExtractFileFromWim(
        CDeploymentSession *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v6; // rbx
  const char *v7; // r9
  __int64 result; // rax
  __int64 v9; // rax
  int TempDir; // eax
  unsigned int LastError; // esi
  CDeploymentSession *v12; // rdi
  HANDLE v13; // rax
  const char *v14; // r9
  CDeploymentSession *v15; // rdi
  HANDLE v16; // rax
  __int64 v17; // rax
  const char *v18; // r9
  __int64 v19; // rdi
  CDeploymentSession *v20; // rdi
  HANDLE v21; // rax
  const char *v22; // r9
  CDeploymentSession *v23; // rdi
  HANDLE v24; // rax
  const char *v25; // r9
  CDeploymentSession *v26; // rdi
  HANDLE ProcessHeap; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CDeploymentSession *v29; // [rsp+60h] [rbp+8h] BYREF

  v29 = this;
  v6 = WIMCreateFile(a2, 0x80000000LL, 3, 0x20000000);
  if ( !v6 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2BD0,
             (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
             v7);
  v29 = 0;
  v9 = _put___unique_any_t_V__unique_storage_U__resource_policy_PEA_WP6AJPEA_W__E_1_STRAPI_Release__YAJ0_ZU__integral_constant__K_0A__wistd__PEA_WPEA_W_0A___T_details_wil___details_wil___wil__QEAAPEAPEA_WXZ(&v29);
  try
  {
    TempDir = CMiscHelpersT<CEmptyType>::GetTempDir(v9);
    LastError = TempDir;
    if ( TempDir >= 0 )
    {
      if ( (unsigned int)WIMSetTemporaryPath(v6, v29) )
      {
        v17 = WIMLoadImage(v6, 1);
        v19 = v17;
        if ( v17 )
        {
          if ( (unsigned int)WIMExtractImagePath(v17, a3, a4, 131104, 0, 0, -2, v6) )
          {
            WIMCloseHandle(v19);
            v26 = v29;
            if ( v29 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, (char *)v26 - 4);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            WIMCloseHandle(v6);
            return 0;
          }
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x2BDD,
                        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                        v22);
          WIMCloseHandle(v19);
          v23 = v29;
          if ( v29 )
          {
            v24 = GetProcessHeap();
            HeapFree(v24, 0, (char *)v23 - 4);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x2BD7,
                        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                        v18);
          v20 = v29;
          if ( v29 )
          {
            v21 = GetProcessHeap();
            HeapFree(v21, 0, (char *)v20 - 4);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          }
        }
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2BD4,
                      (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                      v14);
        v15 = v29;
        if ( v29 )
        {
          v16 = GetProcessHeap();
          HeapFree(v16, 0, (char *)v15 - 4);
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2BD3,
        (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
        (const char *)(unsigned int)TempDir,
        0);
      v12 = v29;
      if ( v29 )
      {
        v13 = GetProcessHeap();
        HeapFree(v13, 0, (char *)v12 - 4);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
    }
    WIMCloseHandle(v6);
    result = LastError;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2BE1,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x18004c794  mov     r11, rsp
0x18004c797  mov     [r11+8], rcx
0x18004c79b  push    rdi
0x18004c79c  push    r14
0x18004c79e  push    r15
0x18004c7a0  sub     rsp, 40h
0x18004c7a4  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x18004c7ac  mov     [r11+10h], rbx
0x18004c7b0  mov     [r11+18h], rsi
0x18004c7b4  mov     r14, r9
0x18004c7b7  mov     r15, r8
0x18004c7ba  mov     rax, rdx
0x18004c7bd  mov     qword ptr [r11-30h], 0
0x18004c7c5  mov     [rsp+58h+var_38], 0; int
0x18004c7cd  mov     edx, 80000000h
0x18004c7d2  mov     r9d, 20000000h
0x18004c7d8  mov     r8d, 3
0x18004c7de  mov     rcx, rax
0x18004c7e1  call    cs:__imp_WIMCreateFile
0x18004c7e8  nop     dword ptr [rax+rax+00h]
0x18004c7ed  mov     rbx, rax
0x18004c7f0  mov     [rsp+58h+var_20], rax
0x18004c7f5  test    rax, rax
0x18004c7f8  jnz     short loc_18004C816
0x18004c7fa  mov     rcx, [rsp+58h]; this
0x18004c7ff  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18004c806  mov     edx, 2BD0h; void *
0x18004c80b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004c810  nop
0x18004c811  jmp     loc_18004CA77
0x18004c816  mov     [rsp+58h+arg_0], 0
0x18004c81f  lea     rcx, [rsp+58h+arg_0]
0x18004c824  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AJPEA_W@_E$1?STRAPI_Release@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ
0x18004c829  mov     rcx, rax
0x18004c82c  call    ?GetTempDir@?$CMiscHelpersT@VCEmptyType@@@@SAJPEAPEA_W@Z; CMiscHelpersT<CEmptyType>::GetTempDir(wchar_t * *)
0x18004c831  mov     esi, eax
0x18004c833  test    eax, eax
0x18004c835  jns     short loc_18004C89A
0x18004c837  mov     rcx, [rsp+58h]; this
0x18004c83c  mov     r9d, eax; char *
0x18004c83f  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18004c846  mov     edx, 2BD3h; void *
0x18004c84b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c850  nop
0x18004c851  mov     rdi, [rsp+58h+arg_0]
0x18004c856  test    rdi, rdi
0x18004c859  jz      short loc_18004C884
0x18004c85b  call    cs:__imp_GetProcessHeap
0x18004c862  nop     dword ptr [rax+rax+00h]
0x18004c867  mov     rcx, rax; hHeap
0x18004c86a  lea     r8, [rdi-4]; lpMem
0x18004c86e  xor     edx, edx; dwFlags
0x18004c870  call    cs:__imp_HeapFree
0x18004c877  nop     dword ptr [rax+rax+00h]
0x18004c87c  xor     ecx, ecx
0x18004c87e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004c883  nop
0x18004c884  mov     rcx, rbx
0x18004c887  call    cs:__imp_WIMCloseHandle
0x18004c88e  nop     dword ptr [rax+rax+00h]
0x18004c893  mov     eax, esi
0x18004c895  jmp     loc_18004CA77
0x18004c89a  mov     rdx, [rsp+58h+arg_0]
0x18004c89f  mov     rcx, rbx
0x18004c8a2  call    cs:__imp_WIMSetTemporaryPath
0x18004c8a9  nop     dword ptr [rax+rax+00h]
0x18004c8ae  test    eax, eax
0x18004c8b0  jnz     short loc_18004C913
0x18004c8b2  mov     rcx, [rsp+58h]; this
0x18004c8b7  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18004c8be  mov     edx, 2BD4h; void *
0x18004c8c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004c8c8  mov     esi, eax
0x18004c8ca  mov     rdi, [rsp+58h+arg_0]
0x18004c8cf  test    rdi, rdi
0x18004c8d2  jz      short loc_18004C8FD
0x18004c8d4  call    cs:__imp_GetProcessHeap
0x18004c8db  nop     dword ptr [rax+rax+00h]
0x18004c8e0  mov     rcx, rax; hHeap
0x18004c8e3  lea     r8, [rdi-4]; lpMem
0x18004c8e7  xor     edx, edx; dwFlags
0x18004c8e9  call    cs:__imp_HeapFree
0x18004c8f0  nop     dword ptr [rax+rax+00h]
0x18004c8f5  xor     ecx, ecx
0x18004c8f7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004c8fc  nop
0x18004c8fd  mov     rcx, rbx
0x18004c900  call    cs:__imp_WIMCloseHandle
0x18004c907  nop     dword ptr [rax+rax+00h]
0x18004c90c  mov     eax, esi
0x18004c90e  jmp     loc_18004CA77
0x18004c913  mov     edx, 1
0x18004c918  mov     rcx, rbx
0x18004c91b  call    cs:__imp_WIMLoadImage
0x18004c922  nop     dword ptr [rax+rax+00h]
0x18004c927  mov     rdi, rax
0x18004c92a  test    rax, rax
0x18004c92d  jnz     short loc_18004C990
0x18004c92f  mov     rcx, [rsp+58h]; this
0x18004c934  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18004c93b  mov     edx, 2BD7h; void *
0x18004c940  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004c945  mov     esi, eax
0x18004c947  mov     rdi, [rsp+58h+arg_0]
0x18004c94c  test    rdi, rdi
0x18004c94f  jz      short loc_18004C97A
0x18004c951  call    cs:__imp_GetProcessHeap
0x18004c958  nop     dword ptr [rax+rax+00h]
0x18004c95d  mov     rcx, rax; hHeap
0x18004c960  lea     r8, [rdi-4]; lpMem
0x18004c964  xor     edx, edx; dwFlags
0x18004c966  call    cs:__imp_HeapFree
0x18004c96d  nop     dword ptr [rax+rax+00h]
0x18004c972  xor     ecx, ecx
0x18004c974  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004c979  nop
0x18004c97a  mov     rcx, rbx
0x18004c97d  call    cs:__imp_WIMCloseHandle
0x18004c984  nop     dword ptr [rax+rax+00h]
0x18004c989  mov     eax, esi
0x18004c98b  jmp     loc_18004CA77
0x18004c990  mov     r9d, 20020h
0x18004c996  mov     r8, r14
0x18004c999  mov     rdx, r15
0x18004c99c  mov     rcx, rdi
0x18004c99f  call    cs:__imp_WIMExtractImagePath
0x18004c9a6  nop     dword ptr [rax+rax+00h]
0x18004c9ab  test    eax, eax
0x18004c9ad  jnz     short loc_18004CA1D
0x18004c9af  mov     rcx, [rsp+58h]; this
0x18004c9b4  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\conx\\mosetup\\"...
0x18004c9bb  mov     edx, 2BDDh; void *
0x18004c9c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004c9c5  mov     esi, eax
0x18004c9c7  mov     rcx, rdi
0x18004c9ca  call    cs:__imp_WIMCloseHandle
0x18004c9d1  nop     dword ptr [rax+rax+00h]
0x18004c9d6  nop
0x18004c9d7  mov     rdi, [rsp+58h+arg_0]
0x18004c9dc  test    rdi, rdi
0x18004c9df  jz      short loc_18004CA0A
0x18004c9e1  call    cs:__imp_GetProcessHeap
0x18004c9e8  nop     dword ptr [rax+rax+00h]
0x18004c9ed  mov     rcx, rax; hHeap
0x18004c9f0  lea     r8, [rdi-4]; lpMem
0x18004c9f4  xor     edx, edx; dwFlags
0x18004c9f6  call    cs:__imp_HeapFree
0x18004c9fd  nop     dword ptr [rax+rax+00h]
0x18004ca02  xor     ecx, ecx
0x18004ca04  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004ca09  nop
0x18004ca0a  mov     rcx, rbx
0x18004ca0d  call    cs:__imp_WIMCloseHandle
0x18004ca14  nop     dword ptr [rax+rax+00h]
0x18004ca19  mov     eax, esi
0x18004ca1b  jmp     short loc_18004CA77
0x18004ca1d  mov     rcx, rdi
0x18004ca20  call    cs:__imp_WIMCloseHandle
0x18004ca27  nop     dword ptr [rax+rax+00h]
0x18004ca2c  nop
0x18004ca2d  mov     rdi, [rsp+58h+arg_0]
0x18004ca32  test    rdi, rdi
0x18004ca35  jz      short loc_18004CA60
0x18004ca37  call    cs:__imp_GetProcessHeap
0x18004ca3e  nop     dword ptr [rax+rax+00h]
0x18004ca43  mov     rcx, rax; hHeap
0x18004ca46  lea     r8, [rdi-4]; lpMem
0x18004ca4a  xor     edx, edx; dwFlags
0x18004ca4c  call    cs:__imp_HeapFree
0x18004ca53  nop     dword ptr [rax+rax+00h]
0x18004ca58  xor     ecx, ecx
0x18004ca5a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004ca5f  nop
0x18004ca60  mov     rcx, rbx
0x18004ca63  call    cs:__imp_WIMCloseHandle
0x18004ca6a  nop     dword ptr [rax+rax+00h]
0x18004ca6f  xor     eax, eax
0x18004ca71  jmp     short loc_18004CA77
0x18004ca73  mov     eax, dword ptr [rsp+58h+arg_0]
0x18004ca77  mov     rbx, [rsp+58h+arg_8]
0x18004ca7c  mov     rsi, [rsp+58h+arg_10]
0x18004ca81  add     rsp, 40h
0x18004ca85  pop     r15
0x18004ca87  pop     r14
0x18004ca89  pop     rdi
0x18004ca8a  retn
```
