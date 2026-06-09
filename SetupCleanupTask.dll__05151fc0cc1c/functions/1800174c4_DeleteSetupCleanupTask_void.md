# DeleteSetupCleanupTask(void)

- ea: `0x1800174c4`
- end: `0x1800177b3`
- name: `?DeleteSetupCleanupTask@@YAJXZ`
- size: `751`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180006838`
- `0x180032f49`

## callees

- `0x18000638c`
- `0x1800174c4`
- `0x1800177bc`
- `0x180017888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001754d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001761d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001754d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800175c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001761d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017742`
- `WDSCORE!CurrentIP` at `0x1800174e3`
- `WDSCORE!CurrentIP` at `0x180017555`
- `WDSCORE!CurrentIP` at `0x1800175d0`
- `WDSCORE!CurrentIP` at `0x180017625`
- `WDSCORE!CurrentIP` at `0x18001768a`
- `WDSCORE!CurrentIP` at `0x1800176f5`
- `WDSCORE!CurrentIP` at `0x18001774a`
- `WDSCORE!CurrentIP` at `0x1800174e3`
- `WDSCORE!CurrentIP` at `0x180017555`
- `WDSCORE!CurrentIP` at `0x1800175d0`
- `WDSCORE!CurrentIP` at `0x180017625`
- `WDSCORE!CurrentIP` at `0x18001768a`
- `WDSCORE!CurrentIP` at `0x1800176f5`
- `WDSCORE!CurrentIP` at `0x18001774a`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017547`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001759c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017617`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001766c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800176db`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001773c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017791`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017547`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001759c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017617`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001766c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800176db`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001773c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180017791`

## string_xrefs

- `0x180017521`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskmanager.cpp`
- `0x1800175ba`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskmanager.cpp`
- `0x180017515`: `DeleteSetupCleanupTask`
- `0x1800175b3`: `DeleteSetupCleanupTask`
- `0x1800174ec`: `DeleteSetupCleanupTask started...`
- `0x1800175d9`: `Cleanup jobs deleted successfully`
- `0x18001762e`: `Deleting the setup cleanup task...`
- `0x18001769b`: `Failed to delete the Setup cleanup task. hr = 0x%x`
- `0x1800176fe`: `Setup cleanup task deleted successfully`
- `0x180017753`: `DeleteSetupCleanupTask finished.`

## pseudocode

```c
__int64 DeleteSetupCleanupTask(void)
{
  DWORD LastError; // edi
  __int64 v1; // rbx
  struct tagLOG_PARTIAL_MSG *v2; // rax
  DWORD v3; // edi
  __int64 v4; // rbx
  struct tagLOG_PARTIAL_MSG *v5; // rax
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  DWORD v12; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rsi
  __int64 v22; // rbx
  const wchar_t *CString; // rax
  UnBCL::String *v24; // rax
  struct tagLOG_PARTIAL_MSG *v25; // rax
  __int64 v26; // [rsp+60h] [rbp-38h] BYREF
  int v27; // [rsp+A0h] [rbp+8h]

  LastError = GetLastError();
  v1 = CurrentIP();
  v2 = ConstructPartialMsgW(0x4000000, "DeleteSetupCleanupTask started...");
  WdsSetupLogMessageW(
    v2,
    0,
    L"D",
    0,
    672,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
    L"DeleteSetupCleanupTask",
    v1,
    LastError,
    0,
    0);
  v3 = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(0x4000000, "Deleting cleanup jobs...");
  WdsSetupLogMessageW(
    v5,
    0,
    L"D",
    0,
    675,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
    L"DeleteSetupCleanupTask",
    v4,
    v3,
    0,
    0);
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ((void (*)(void))pDeleteSetupCleanupJobs)();
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &UnBCL::Exception * `RTTI Type Descriptor', (UnBCL::Exception **)&v26) )
    {
      v20 = GetLastError();
      v21 = CurrentIP();
      v22 = v26;
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 72LL))(v22) )
      {
        v24 = (UnBCL::String *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 72LL))(v22);
        CString = UnBCL::String::get_CString(v24);
      }
      else
      {
        CString = L"(NULL)";
      }
      v25 = ConstructPartialMsgW(0x2000000, "Failed to delete the Setup cleanup jobs. %s", (const char *)CString);
      WdsSetupLogMessageW(
        v25,
        0,
        L"D",
        0,
        682,
        L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
        L"DeleteSetupCleanupTask",
        v21,
        v20,
        0,
        0);
      (**(void (__fastcall ***)(__int64, __int64))v22)(v22, 1);
      __eh34_try_continuation(0, &UnBCL::Exception * `RTTI Type Descriptor', &loc_1800175AB);
    }
  }
  v6 = GetLastError();
  v7 = CurrentIP();
  v8 = ConstructPartialMsgW(0x4000000, "Cleanup jobs deleted successfully");
  WdsSetupLogMessageW(
    v8,
    0,
    L"D",
    0,
    685,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
    L"DeleteSetupCleanupTask",
    v7,
    v6,
    0,
    0);
  v9 = GetLastError();
  v10 = CurrentIP();
  v11 = ConstructPartialMsgW(0x4000000, "Deleting the setup cleanup task...");
  WdsSetupLogMessageW(
    v11,
    0,
    L"D",
    0,
    688,
    L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
    L"DeleteSetupCleanupTask",
    v10,
    v9,
    0,
    0);
  v27 = pDeleteSetupCleanupTask();
  v12 = GetLastError();
  v13 = CurrentIP();
  if ( v27 >= 0 )
  {
    v16 = ConstructPartialMsgW(0x4000000, "Setup cleanup task deleted successfully");
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      695,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"DeleteSetupCleanupTask",
      v13,
      v12,
      0,
      0);
    v17 = GetLastError();
    v18 = CurrentIP();
    v19 = ConstructPartialMsgW(0x4000000, "DeleteSetupCleanupTask finished.");
    WdsSetupLogMessageW(
      v19,
      0,
      L"D",
      0,
      698,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"DeleteSetupCleanupTask",
      v18,
      v17,
      0,
      0);
    return 0;
  }
  else
  {
    v14 = ConstructPartialMsgW(0x2000000, "Failed to delete the Setup cleanup task. hr = 0x%x", v27);
    WdsSetupLogMessageW(
      v14,
      0,
      L"D",
      0,
      692,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskmanager.cpp",
      L"DeleteSetupCleanupTask",
      v13,
      v12,
      0,
      0);
    return (unsigned int)v27;
  }
}

```

## disassembly

```asm
0x1800174c4  mov     [rsp+arg_8], rbx
0x1800174c9  mov     [rsp+arg_10], rsi
0x1800174ce  push    rdi
0x1800174cf  push    r12
0x1800174d1  push    r13
0x1800174d3  push    r14
0x1800174d5  push    r15
0x1800174d7  sub     rsp, 70h
0x1800174db  call    cs:__imp_GetLastError
0x1800174e1  mov     edi, eax
0x1800174e3  call    cs:__imp_CurrentIP
0x1800174e9  mov     rbx, rax
0x1800174ec  lea     rdx, aDeletesetupcle_0; "DeleteSetupCleanupTask started..."
0x1800174f3  mov     r13d, 4000000h
0x1800174f9  mov     ecx, r13d; unsigned int
0x1800174fc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017501  xor     esi, esi
0x180017503  mov     [rsp+98h+var_48], esi
0x180017507  mov     [rsp+98h+var_50], rsi
0x18001750c  mov     [rsp+98h+var_58], edi
0x180017510  mov     [rsp+98h+var_60], rbx
0x180017515  lea     r15, aDeletesetupcle; "DeleteSetupCleanupTask"
0x18001751c  mov     [rsp+98h+var_68], r15
0x180017521  lea     r12, aBaseNtsetupSet_0; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180017528  mov     [rsp+98h+var_70], r12
0x18001752d  mov     [rsp+98h+var_78], 2A0h
0x180017535  xor     r9d, r9d
0x180017538  lea     r14, aD_0; "D"
0x18001753f  mov     r8, r14
0x180017542  xor     edx, edx
0x180017544  mov     rcx, rax
0x180017547  call    cs:__imp_WdsSetupLogMessageW
0x18001754d  call    cs:__imp_GetLastError
0x180017553  mov     edi, eax
0x180017555  call    cs:__imp_CurrentIP
0x18001755b  mov     rbx, rax
0x18001755e  lea     rdx, aDeletingCleanu; "Deleting cleanup jobs..."
0x180017565  mov     ecx, r13d; unsigned int
0x180017568  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001756d  mov     [rsp+98h+var_48], esi
0x180017571  mov     [rsp+98h+var_50], rsi
0x180017576  mov     [rsp+98h+var_58], edi
0x18001757a  mov     [rsp+98h+var_60], rbx
0x18001757f  mov     [rsp+98h+var_68], r15
0x180017584  mov     [rsp+98h+var_70], r12
0x180017589  mov     [rsp+98h+var_78], 2A3h
0x180017591  xor     r9d, r9d
0x180017594  mov     r8, r14
0x180017597  xor     edx, edx
0x180017599  mov     rcx, rax
0x18001759c  call    cs:__imp_WdsSetupLogMessageW
0x1800175a2  nop
0x1800175a3  call    ?pDeleteSetupCleanupJobs@@YAXXZ; pDeleteSetupCleanupJobs(void)
0x1800175a8  nop
0x1800175a9  jmp     short loc_1800175C8
0x1800175ab  xor     esi, esi
0x1800175ad  mov     r13d, 4000000h
0x1800175b3  lea     r15, aDeletesetupcle; "DeleteSetupCleanupTask"
0x1800175ba  lea     r12, aBaseNtsetupSet_0; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800175c1  lea     r14, aD_0; "D"
0x1800175c8  call    cs:__imp_GetLastError
0x1800175ce  mov     edi, eax
0x1800175d0  call    cs:__imp_CurrentIP
0x1800175d6  mov     rbx, rax
0x1800175d9  lea     rdx, aCleanupJobsDel; "Cleanup jobs deleted successfully"
0x1800175e0  mov     ecx, r13d; unsigned int
0x1800175e3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800175e8  mov     [rsp+98h+var_48], esi
0x1800175ec  mov     [rsp+98h+var_50], rsi
0x1800175f1  mov     [rsp+98h+var_58], edi
0x1800175f5  mov     [rsp+98h+var_60], rbx
0x1800175fa  mov     [rsp+98h+var_68], r15
0x1800175ff  mov     [rsp+98h+var_70], r12
0x180017604  mov     [rsp+98h+var_78], 2ADh
0x18001760c  xor     r9d, r9d
0x18001760f  mov     r8, r14
0x180017612  xor     edx, edx
0x180017614  mov     rcx, rax
0x180017617  call    cs:__imp_WdsSetupLogMessageW
0x18001761d  call    cs:__imp_GetLastError
0x180017623  mov     edi, eax
0x180017625  call    cs:__imp_CurrentIP
0x18001762b  mov     rbx, rax
0x18001762e  lea     rdx, aDeletingTheSet; "Deleting the setup cleanup task..."
0x180017635  mov     ecx, r13d; unsigned int
0x180017638  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001763d  mov     [rsp+98h+var_48], esi
0x180017641  mov     [rsp+98h+var_50], rsi
0x180017646  mov     [rsp+98h+var_58], edi
0x18001764a  mov     [rsp+98h+var_60], rbx
0x18001764f  mov     [rsp+98h+var_68], r15
0x180017654  mov     [rsp+98h+var_70], r12
0x180017659  mov     [rsp+98h+var_78], 2B0h
0x180017661  xor     r9d, r9d
0x180017664  mov     r8, r14
0x180017667  xor     edx, edx
0x180017669  mov     rcx, rax
0x18001766c  call    cs:__imp_WdsSetupLogMessageW
0x180017672  call    ?pDeleteSetupCleanupTask@@YAJXZ; pDeleteSetupCleanupTask(void)
0x180017677  mov     [rsp+98h+arg_0], eax
0x18001767e  test    eax, eax
0x180017680  jns     short loc_1800176ED
0x180017682  call    cs:__imp_GetLastError
0x180017688  mov     edi, eax
0x18001768a  call    cs:__imp_CurrentIP
0x180017690  mov     rbx, rax
0x180017693  mov     r8d, [rsp+98h+arg_0]
0x18001769b  lea     rdx, aFailedToDelete_2; "Failed to delete the Setup cleanup task"...
0x1800176a2  mov     ecx, 2000000h; unsigned int
0x1800176a7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800176ac  mov     [rsp+98h+var_48], esi
0x1800176b0  mov     [rsp+98h+var_50], rsi
0x1800176b5  mov     [rsp+98h+var_58], edi
0x1800176b9  mov     [rsp+98h+var_60], rbx
0x1800176be  mov     [rsp+98h+var_68], r15
0x1800176c3  mov     [rsp+98h+var_70], r12
0x1800176c8  mov     [rsp+98h+var_78], 2B4h
0x1800176d0  xor     r9d, r9d
0x1800176d3  mov     r8, r14
0x1800176d6  xor     edx, edx
0x1800176d8  mov     rcx, rax
0x1800176db  call    cs:__imp_WdsSetupLogMessageW
0x1800176e1  mov     eax, [rsp+98h+arg_0]
0x1800176e8  jmp     loc_180017799
0x1800176ed  call    cs:__imp_GetLastError
0x1800176f3  mov     edi, eax
0x1800176f5  call    cs:__imp_CurrentIP
0x1800176fb  mov     rbx, rax
0x1800176fe  lea     rdx, aSetupCleanupTa_1; "Setup cleanup task deleted successfully"
0x180017705  mov     ecx, r13d; unsigned int
0x180017708  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001770d  mov     [rsp+98h+var_48], esi
0x180017711  mov     [rsp+98h+var_50], rsi
0x180017716  mov     [rsp+98h+var_58], edi
0x18001771a  mov     [rsp+98h+var_60], rbx
0x18001771f  mov     [rsp+98h+var_68], r15
0x180017724  mov     [rsp+98h+var_70], r12
0x180017729  mov     [rsp+98h+var_78], 2B7h
0x180017731  xor     r9d, r9d
0x180017734  mov     r8, r14
0x180017737  xor     edx, edx
0x180017739  mov     rcx, rax
0x18001773c  call    cs:__imp_WdsSetupLogMessageW
0x180017742  call    cs:__imp_GetLastError
0x180017748  mov     edi, eax
0x18001774a  call    cs:__imp_CurrentIP
0x180017750  mov     rbx, rax
0x180017753  lea     rdx, aDeletesetupcle_1; "DeleteSetupCleanupTask finished."
0x18001775a  mov     ecx, r13d; unsigned int
0x18001775d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180017762  mov     [rsp+98h+var_48], esi
0x180017766  mov     [rsp+98h+var_50], rsi
0x18001776b  mov     [rsp+98h+var_58], edi
0x18001776f  mov     [rsp+98h+var_60], rbx
0x180017774  mov     [rsp+98h+var_68], r15
0x180017779  mov     [rsp+98h+var_70], r12
0x18001777e  mov     [rsp+98h+var_78], 2BAh
0x180017786  xor     r9d, r9d
0x180017789  mov     r8, r14
0x18001778c  xor     edx, edx
0x18001778e  mov     rcx, rax
0x180017791  call    cs:__imp_WdsSetupLogMessageW
0x180017797  xor     eax, eax
0x180017799  lea     r11, [rsp+98h+var_28]
0x18001779e  mov     rbx, [r11+38h]
0x1800177a2  mov     rsi, [r11+40h]
0x1800177a6  mov     rsp, r11
0x1800177a9  pop     r15
0x1800177ab  pop     r14
0x1800177ad  pop     r13
0x1800177af  pop     r12
0x1800177b1  pop     rdi
0x1800177b2  retn
```
