# wWinMain

- ea: `0x1400230ec`
- end: `0x14002499d`
- name: `wWinMain`
- size: `6321`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `46`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1403795a0`

## callees

- `0x140021294`
- `0x14002163c`
- `0x140021a24`
- `0x140022afc`
- `0x140022bdc`
- `0x1400230ec`
- `0x1400249a4`
- `0x140024bdc`
- `0x140024de0`
- `0x140028d74`
- `0x140028df4`
- `0x1400291a0`
- `0x14002a108`
- `0x14002a848`
- `0x14002afc8`
- `0x14002b5f0`
- `0x14002cc08`
- `0x14002f218`
- `0x14003c578`
- `0x1400400e4`
- `0x140040184`
- `0x140040308`
- `0x140040364`
- `0x14004045c`
- `0x1400413a8`
- `0x1400441e4`
- `0x140045404`
- `0x140057920`
- `0x140057a20`
- `0x140071f48`
- `0x140072104`
- `0x140072718`
- `0x140072884`
- `0x140072a98`
- `0x140072c6c`
- `0x1400730a4`
- `0x14007320c`
- `0x14012d7d8`
- `0x14012d864`
- `0x140378d44`
- `0x140378dc8`
- `0x140379070`
- `0x1403790cc`
- `0x1403790d8`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140023226`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140023226`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002360e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002360e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002319e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002319e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002464c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002464c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400233f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002352f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023fba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400233f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002352f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023fba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002391a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400239be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023bc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023c5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024263`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024307`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024586`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002461d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002391a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400239be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023bc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023c5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024263`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024307`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024586`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002461d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400234b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400234b5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x140023a61`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400243e7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x140023a61`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400243e7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002358f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x14002358f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140023c3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400245ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140023c3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400245ff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400233e3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140023521`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1400233e3`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140023521`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140023cea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140023cea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400238f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400239a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002423f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400242e9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400238f3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400239a0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002423f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400242e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140023fa8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x140023fa8`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140023960`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400242a9`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140023960`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1400242a9`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x14002314a`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x14002314a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140023235`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140023235`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14002377c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140023894`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140023b8c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140023fe5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1400241e9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140024515`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x14002377c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140023894`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140023b8c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140023fe5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1400241e9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140024515`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140023b35`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400244bb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140023b35`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1400244bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023194`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002357c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023194`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023444`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002357c`
- `USER32!TranslateMessage` at `0x140023b0f`
- `USER32!TranslateMessage` at `0x140024495`
- `USER32!TranslateMessage` at `0x140023b0f`
- `USER32!TranslateMessage` at `0x140024495`
- `USER32!DispatchMessageW` at `0x140023b1d`
- `USER32!DispatchMessageW` at `0x1400244a3`
- `USER32!DispatchMessageW` at `0x140023b1d`
- `USER32!DispatchMessageW` at `0x1400244a3`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140023aae`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140024434`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140023aae`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140024434`
- `USER32!PeekMessageW` at `0x140023ae3`
- `USER32!PeekMessageW` at `0x140024469`
- `USER32!PeekMessageW` at `0x140023ae3`
- `USER32!PeekMessageW` at `0x140024469`
- `USER32!GetMessageW` at `0x140023afd`
- `USER32!GetMessageW` at `0x140024483`
- `USER32!GetMessageW` at `0x140023afd`
- `USER32!GetMessageW` at `0x140024483`

## string_xrefs

- `0x14002468e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x1400246a3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024714`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1400247b2`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1400247c4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1400247d6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1400247e8`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x14002480f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024833`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024845`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1400248cc`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1400248de`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1400248f0`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024902`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024929`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x14002494d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x14002495f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140024871`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14002488b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1400248a5`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14002498b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1400246d3`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  LPWSTR *v5; // rax
  LPWSTR *v6; // rbx
  int v7; // edi
  const wchar_t **v8; // rsi
  HRESULT v9; // eax
  __int64 System; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rax
  char v13; // bl
  const char *v14; // r9
  int i; // ebx
  const char *v16; // r9
  void (__fastcall ***v17)(_QWORD, __int64); // rdi
  int v18; // esi
  _QWORD *v19; // rax
  volatile signed __int32 *v20; // rbx
  HANDLE v21; // rbx
  __int64 v22; // rax
  wil::details *v23; // rcx
  HANDLE Mutex; // rsi
  int LastErrorFailHr; // eax
  const char *v26; // r9
  __int64 v27; // rax
  wil::details *v28; // rcx
  HANDLE v29; // rsi
  int v30; // eax
  DWORD v31; // eax
  const char *v32; // r9
  HANDLE v33; // r13
  HRESULT v34; // eax
  int v35; // eax
  char *v36; // rax
  const char *v37; // r9
  __int64 v38; // r11
  char *v39; // rax
  _QWORD *v40; // rax
  __int64 v41; // rax
  __int64 v42; // r14
  __int64 (__fastcall *v43)(__int64, __int128 *, int *); // rsi
  unsigned int v44; // esi
  _QWORD *v45; // rax
  __int64 v46; // rdx
  const char *v47; // r9
  int v48; // eax
  const char *v49; // r9
  const char *v50; // r9
  PSECURITY_DESCRIPTOR v51; // rsi
  __int64 v52; // rax
  HANDLE v53; // rax
  char v54; // r14
  const char *v55; // r9
  const char *v56; // r9
  void *v57; // rcx
  __int64 v58; // rax
  __int64 v59; // rcx
  char v60; // si
  const char *v61; // r9
  DWORD v62; // eax
  const char *v63; // r9
  DWORD v64; // eax
  const char *v65; // r9
  winrt *v66; // rcx
  const char *v67; // r9
  const char *v68; // r9
  const char *v69; // r9
  const wchar_t *v70; // r8
  __int128 v71; // xmm6
  __int64 v72; // rax
  _BYTE *traits_1_unsigned_char; // rax
  const char *v74; // r9
  _BYTE *v75; // r11
  void *v76; // rax
  GUID *v77; // rcx
  _QWORD *v78; // rax
  __int64 v79; // rax
  __int64 v80; // rsi
  __int64 v81; // rax
  __int64 traits_2_unsigned_short; // rax
  const char *v83; // r9
  __int64 v84; // r11
  __int64 v85; // rax
  const char *v86; // r9
  volatile signed __int32 *v87; // rsi
  volatile signed __int32 *v88; // rsi
  HANDLE Event; // rsi
  const char *v90; // r9
  _QWORD *v91; // rax
  __int64 v92; // rax
  __int64 v93; // rsi
  void *v94; // rax
  const char *v95; // r9
  __int64 v96; // r11
  __int64 v97; // rax
  volatile signed __int32 *v98; // rsi
  volatile signed __int32 *v99; // rsi
  _QWORD *v100; // rax
  __int64 v101; // rdx
  const char *v102; // r9
  volatile signed __int32 *v103; // rsi
  int v104; // eax
  const char *v105; // r9
  const char *v106; // r9
  HANDLE v107; // rsi
  __int64 v108; // rax
  HANDLE v109; // rax
  const char *v110; // r9
  const char *v111; // r9
  void *v112; // rcx
  __int64 v113; // rax
  __int64 v114; // rcx
  volatile signed __int32 *v115; // rsi
  const char *v116; // r9
  DWORD v117; // eax
  const char *v118; // r9
  DWORD v119; // eax
  const char *v120; // r9
  winrt *v121; // rcx
  volatile signed __int32 *v122; // rsi
  const char *v123; // r9
  const char *v124; // r9
  const char *v125; // r9
  const struct wil::FailureInfo *v127; // rdx
  int ppv; // [rsp+20h] [rbp-2C8h]
  int ppva; // [rsp+20h] [rbp-2C8h]
  char v130; // [rsp+30h] [rbp-2B8h]
  char v131; // [rsp+30h] [rbp-2B8h]
  HANDLE hObject; // [rsp+38h] [rbp-2B0h] BYREF
  HANDLE hEvent[2]; // [rsp+40h] [rbp-2A8h] BYREF
  __int128 v134; // [rsp+50h] [rbp-298h] BYREF
  char v135; // [rsp+60h] [rbp-288h]
  HANDLE hHandle; // [rsp+68h] [rbp-280h] BYREF
  __int128 v137; // [rsp+70h] [rbp-278h] BYREF
  void (__fastcall ***v138)(_QWORD, __int64); // [rsp+80h] [rbp-268h]
  _OWORD v139[2]; // [rsp+90h] [rbp-258h] BYREF
  HANDLE v140; // [rsp+B0h] [rbp-238h]
  int pNumArgs; // [rsp+B8h] [rbp-230h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+C0h] [rbp-228h] BYREF
  struct tagMSG MutexAttributes; // [rsp+D0h] [rbp-218h] BYREF
  LPVOID v144; // [rsp+100h] [rbp-1E8h] BYREF
  __int128 v145; // [rsp+108h] [rbp-1E0h] BYREF
  __int128 v146; // [rsp+118h] [rbp-1D0h]
  char v147; // [rsp+128h] [rbp-1C0h]
  _QWORD v148[42]; // [rsp+130h] [rbp-1B8h] BYREF
  HLOCAL hMem[2]; // [rsp+280h] [rbp-68h] BYREF
  HANDLE Handles[2]; // [rsp+290h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  set_invalid_parameter_handler(InvalidParameterHandler);
  pNumArgs = 0;
  v5 = CommandLineToArgvW(lpCmdLine, &pNumArgs);
  v6 = v5;
  if ( v5 )
  {
    v7 = 0;
    if ( pNumArgs > 0 )
    {
      v8 = (const wchar_t **)v5;
      do
      {
        if ( !wcsicmp(*v8, L"useprivatenamespaces") )
          g_usoSvcSupportsPrivateNamespaces = 1;
        ++v7;
        ++v8;
      }
      while ( v7 < pNumArgs );
    }
    LocalFree(v6);
  }
  v9 = CoInitializeEx(0, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1284,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v9,
      ppv);
  try
  {
    v135 = 1;
    pNumArgs = 4;
    System = SystemInterface::Providers::GetSystem(Handles);
    v11 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    v12 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 48LL))(v11, &v137);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 40LL))(*v12);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(&v137);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(Handles);
    if ( v13 )
    {
      for ( i = 0; i < 200; ++i )
      {
        if ( IsDebuggerPresent() )
          break;
        Sleep(0x3E8u);
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x7F,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
      v14);
  }
  try
  {
    v138 = 0;
    SecurityDescriptor[0] = operator new(0x10u);
    v17 = (void (__fastcall ***)(_QWORD, __int64))uus::Session::Session(
                                                    (uus::Session *)SecurityDescriptor[0],
                                                    L"MoUsoCoreWorker");
    v18 = 5;
    pNumArgs = 5;
    v138 = v17;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x87,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
      v16);
    v17 = v138;
    v18 = pNumArgs;
  }
  v19 = (_QWORD *)SystemInterface::Service::GetSystem(&v137);
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 176LL))(*v19) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
      (const char *)0x80070005LL,
      ppv);
  v20 = (volatile signed __int32 *)*((_QWORD *)&v137 + 1);
  if ( *((_QWORD *)&v137 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v137 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v21 = 0;
  hHandle = 0;
  if ( g_usoSvcSupportsPrivateNamespaces )
  {
    v145 = 0;
    *(_QWORD *)&v146 = 0;
    anonymous_namespace_::GetSids(&v145);
    *(_OWORD *)hMem = 0;
    anonymous_namespace_::SecurityDescriptorAndAcls::SecurityDescriptorAndAcls(hMem, &v145);
    MutexAttributes.hwnd = (HWND)24;
    MutexAttributes.wParam = 0;
    *(HLOCAL *)&MutexAttributes.message = hMem[1];
    anonymous_namespace_::CreateOrOpenPrivateNamespace(&v145);
    SecurityDescriptor[0] = 0;
    pNumArgs = v18 | 2;
    v22 = anonymous_namespace_::FullObjectName(v139, L"\\UsoCoreworkerRunning");
    if ( *(_QWORD *)(v22 + 24) > 7u )
      v22 = *(_QWORD *)v22;
    Mutex = CreateMutexExW((LPSECURITY_ATTRIBUTES)&MutexAttributes, (LPCWSTR)v22, 0, 0x1F0001u);
    if ( Mutex )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        SecurityDescriptor,
        Mutex);
      LastErrorFailHr = 0;
      v21 = SecurityDescriptor[0];
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v23);
    }
    if ( LastErrorFailHr < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
        (const char *)(unsigned int)LastErrorFailHr,
        ppv);
    std::wstring::~wstring(v139);
    if ( hMem[1] )
      LocalFree(hMem[1]);
    if ( hMem[0] )
      operator delete(hMem[0]);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&v145);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &hHandle,
      v21);
    v21 = hHandle;
  }
  else
  {
    HIDWORD(MutexAttributes.hwnd) = 0;
    HIDWORD(MutexAttributes.wParam) = 0;
    SecurityDescriptor[0] = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GA;;;SY)", 1u, SecurityDescriptor, 0) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x9B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        v26);
    LODWORD(MutexAttributes.hwnd) = 24;
    *(PSECURITY_DESCRIPTOR *)&MutexAttributes.message = SecurityDescriptor[0];
    LODWORD(MutexAttributes.wParam) = 0;
    v27 = GlobalObjectName(&v145, L"\\UsoCoreworkerRunning");
    if ( *(_QWORD *)(v27 + 24) > 7u )
      v27 = *(_QWORD *)v27;
    v29 = CreateMutexExW((LPSECURITY_ATTRIBUTES)&MutexAttributes, (LPCWSTR)v27, 0, 0x1F0001u);
    if ( v29 )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &hHandle,
        v29);
      v30 = 0;
      v21 = hHandle;
    }
    else
    {
      v30 = wil::details::GetLastErrorFailHr(v28);
    }
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        (const char *)(unsigned int)v30,
        ppv);
    std::wstring::~wstring(&v145);
    if ( SecurityDescriptor[0] )
      LocalFree(SecurityDescriptor[0]);
  }
  v31 = WaitForSingleObjectEx(v21, 0xFFFFFFFF, 0);
  if ( v31 == 258 )
  {
    v33 = 0;
  }
  else
  {
    if ( (v31 & 0xFFFFFF7F) != 0 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC2D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v32);
    v33 = v21;
  }
  hEvent[0] = v33;
  v140 = v33;
  if ( v31 == -1 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xA5,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
      v32);
  if ( (v31 & 0xFFFFFF7F) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
      (const char *)0x80070005LL,
      ppv);
  v144 = 0;
  v34 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v144);
  if ( v34 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
      (const char *)(unsigned int)v34,
      ppva);
  v35 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v144 + 24LL))(v144, 1, 2);
  if ( v35 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
      (const char *)(unsigned int)v35,
      ppva);
  if ( wil::details::g_pfnTelemetryCallback
    && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != Windows::Telemetry::WorkerErrors::FallbackTelemetryCallback )
  {
    memset(v148, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v148, v127);
  }
  wil::details::g_pfnTelemetryCallback = (__int64)Windows::Telemetry::WorkerErrors::FallbackTelemetryCallback;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Calliope_USO_TelemetryConnections>::GetImpl'::`2'::impl) )
  {
    memset(v148, 0, 0x148u);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v148,
      "MoUsoCoreWorkerRunning");
    try
    {
      v148[0] = &Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::`vftable';
      v71 = (__int128)*Windows::Strings::to_guid(
                         (Windows::Strings *)&MutexAttributes,
                         (struct _GUID *)&stru_1403BE170,
                         v70);
      hObject = 0;
      wil::ActivityBase<Windows::Telemetry::BaseCore,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        v148,
        &hObject);
      v72 = v148[34];
      *(_OWORD *)(v148[34] + 24LL) = v71;
      *(_BYTE *)(v72 + 4) = 1;
      if ( hObject )
        ReleaseSRWLockExclusive((PSRWLOCK)hObject);
      traits_1_unsigned_char = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                                          "1507.2603.28012.0",
                                          &unk_1403BDC42,
                                          0);
      if ( traits_1_unsigned_char == (_BYTE *)&unk_1403BDC42
        || (v76 = (void *)(traits_1_unsigned_char - v75), v76 == (void *)-1LL) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v74);
      }
      hMem[0] = v75;
      hMem[1] = v76;
      v139[0] = *(_OWORD *)hMem;
      Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::StartActivity(v148, v139);
      v77 = &GUID_NULL;
      if ( v148[34] != -8 )
        v77 = (GUID *)(v148[34] + 8LL);
      v139[0] = *v77;
      v78 = (_QWORD *)SystemInterface::Providers::GetSystem(&v134);
      v79 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v78 + 16LL))(*v78, &v137);
      v80 = *(_QWORD *)v79;
      hObject = *(HANDLE *)(**(_QWORD **)v79 + 56LL);
      v81 = Windows::Strings::to_wstring(&MutexAttributes, v139);
      v145 = 0;
      v146 = 0u;
      v145 = *(_OWORD *)v81;
      v146 = *(_OWORD *)(v81 + 16);
      *(_QWORD *)(v81 + 16) = 0;
      *(_QWORD *)(v81 + 24) = 7;
      *(_WORD *)v81 = 0;
      v147 = 4;
      traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                  L"MoUsoCoreWorkerActivityId",
                                  &unk_1403BE1F4,
                                  0);
      if ( traits_2_unsigned_short == v84
        || (v85 = (traits_2_unsigned_short - (__int64)L"MoUsoCoreWorkerActivityId") >> 1, v85 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v83);
      }
      hMem[0] = L"MoUsoCoreWorkerActivityId";
      hMem[1] = (HLOCAL)v85;
      v139[0] = *(_OWORD *)hMem;
      ((void (__fastcall *)(__int64, _OWORD *, __int128 *))hObject)(v80, v139, &v145);
      if ( v147 != -1 && v147 && v147 != 1 && v147 != 2 && v147 != 3 )
        std::wstring::~wstring(&v145);
      std::wstring::~wstring(&MutexAttributes);
      v87 = (volatile signed __int32 *)*((_QWORD *)&v137 + 1);
      if ( *((_QWORD *)&v137 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v137 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v87)(v87);
          if ( _InterlockedExchangeAdd(v87 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v87 + 8LL))(v87);
        }
      }
      v88 = (volatile signed __int32 *)*((_QWORD *)&v134 + 1);
      if ( *((_QWORD *)&v134 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v134 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
          if ( _InterlockedExchangeAdd(v88 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
        }
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xBC,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        v86);
      v17 = v138;
      v21 = hHandle;
      v33 = hEvent[0];
    }
    *(_QWORD *)&v134 = v148;
    BYTE8(v134) = 1;
    SecurityDescriptor[0] = 0;
    CreateServiceShutdownEvent(SecurityDescriptor);
    *(_OWORD *)hMem = 0;
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    if ( !Event )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CA0,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
        v90);
    GetLastError();
    _reset___shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAAXPEAX_Z(
      hMem,
      Event);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::initOnceOutOfProc_,
      `Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_140549E10 = 1;
    v91 = (_QWORD *)SystemInterface::Service::GetSystem(&MutexAttributes);
    v92 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v91 + 40LL))(*v91, &v145);
    v93 = *(_QWORD *)v92;
    hObject = *(HANDLE *)(**(_QWORD **)v92 + 56LL);
    pNumArgs = 60;
    v94 = (void *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                    L"MoUsoCoreWorkerShutdownDelay",
                    &unk_1403BE232,
                    0);
    if ( v94 == &unk_1403BE232 || (v97 = ((__int64)v94 - v96) >> 1, v97 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v95);
    *(_QWORD *)&v137 = v96;
    *((_QWORD *)&v137 + 1) = v97;
    v139[0] = v137;
    LODWORD(hObject) = 1000 * ((__int64 (__fastcall *)(__int64, _OWORD *, int *))hObject)(v93, v139, &pNumArgs);
    v98 = (volatile signed __int32 *)*((_QWORD *)&v145 + 1);
    if ( *((_QWORD *)&v145 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v145 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
        if ( !_InterlockedDecrement(v98 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
      }
    }
    v99 = *(volatile signed __int32 **)&MutexAttributes.message;
    if ( *(_QWORD *)&MutexAttributes.message )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&MutexAttributes.message + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
        if ( !_InterlockedDecrement(v99 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
      }
    }
    try
    {
      v100 = (_QWORD *)SystemInterface::Service::GetSystem(&MutexAttributes);
      if ( hMem[0] )
        v101 = *(_QWORD *)hMem[0];
      else
        v101 = 0;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v100 + 240LL))(*v100, v101, (unsigned int)hObject);
      v103 = *(volatile signed __int32 **)&MutexAttributes.message;
      if ( *(_QWORD *)&MutexAttributes.message )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&MutexAttributes.message + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v103)(v103);
          if ( _InterlockedExchangeAdd(v103 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v103 + 8LL))(v103);
        }
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xE9,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        v102);
      v17 = v138;
      v21 = hHandle;
      v33 = hEvent[0];
    }
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::initOnceOutOfProc_,
      `Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_140549E10 = 1;
    v104 = Microsoft::WRL::Details::RegisterObjects<2>(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<2>,1,int>::instance_);
    if ( v104 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        (const char *)(unsigned int)v104,
        ppva);
    hEvent[0] = 0;
    if ( g_usoSvcSupportsPrivateNamespaces )
    {
      Windows::PrivateNamespaceHelpers::TryOpenPrivateNamespaceEvent(hEvent, L"\\UsoCoreWorkerStarted");
      if ( hEvent[0] )
      {
        if ( !SetEvent(hEvent[0]) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9C7,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            v105);
        if ( hEvent[0] && !CloseHandle(hEvent[0]) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9D1,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            v106);
      }
    }
    else
    {
      v107 = 0;
      v108 = GlobalObjectName(&MutexAttributes, L"\\UsoCoreWorkerStarted");
      if ( *(_QWORD *)(v108 + 24) > 7u )
        v108 = *(_QWORD *)v108;
      v109 = OpenEventW(0x100002u, 0, (LPCWSTR)v108);
      if ( v109 )
      {
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          hEvent,
          v109);
        v130 = 1;
        v107 = hEvent[0];
      }
      else
      {
        v130 = 0;
      }
      std::wstring::~wstring(&MutexAttributes);
      if ( v130 && !SetEvent(v107) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9C7,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v110);
      if ( v107 && !CloseHandle(v107) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v111);
    }
    if ( hMem[0] )
      v112 = *(void **)hMem[0];
    else
      v112 = 0;
    Handles[0] = v112;
    Handles[1] = SecurityDescriptor[0];
    v113 = SystemInterface::Providers::GetSystem(&MutexAttributes);
    v114 = *(_QWORD *)v113 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v113 + 8LL) + 4LL);
    v131 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v114 + 192LL))(v114);
    v115 = *(volatile signed __int32 **)&MutexAttributes.message;
    if ( *(_QWORD *)&MutexAttributes.message )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&MutexAttributes.message + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v115)(v115);
        if ( _InterlockedExchangeAdd(v115 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v115 + 8LL))(v115);
      }
    }
    if ( v131 )
    {
      if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) == -1 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x108,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
          v116);
    }
    else
    {
      memset(&MutexAttributes, 0, sizeof(MutexAttributes));
      while ( 1 )
      {
        v117 = MsgWaitForMultipleObjectsEx(2u, Handles, 0xFFFFFFFF, 0x1CFFu, 4u);
        if ( v117 == -1 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x115,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
            v118);
        if ( v117 != 2 )
          break;
        while ( PeekMessageW(&MutexAttributes, 0, 0, 0, 0) )
        {
          if ( GetMessageW(&MutexAttributes, 0, 0, 0) )
          {
            TranslateMessage(&MutexAttributes);
            DispatchMessageW(&MutexAttributes);
            v119 = WaitForMultipleObjects(2u, Handles, 0, 0);
            if ( v119 == -1 )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x12E,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
                v120);
            if ( v119 > 1 )
              continue;
          }
          goto LABEL_175;
        }
      }
    }
LABEL_175:
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      SecurityDescriptor,
      0);
    g_coreWorkerShuttingDown = 1;
    BYTE8(v134) = 0;
    wWinMain_::_22_::_lambda_1_::operator()(&v134);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::initOnceOutOfProc_,
      `Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_140549E10 = 1;
    Microsoft::WRL::Module<2,Microsoft::WRL::Details::DefaultModule<2>>::UnregisterObjects((Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<2>,1,int>::instance_);
    winrt::clear_factory_cache(v121);
    v122 = (volatile signed __int32 *)hMem[1];
    if ( hMem[1] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)hMem[1] + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v122)(v122);
        if ( !_InterlockedDecrement(v122 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v122 + 8LL))(v122);
      }
    }
    if ( SecurityDescriptor[0] && !CloseHandle(SecurityDescriptor[0]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v123);
    if ( BYTE8(v134) )
    {
      BYTE8(v134) = 0;
      wWinMain_::_22_::_lambda_1_::operator()(&v134);
    }
    v148[0] = &Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::`vftable';
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v148);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v148);
    if ( v144 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v144 + 16LL))(v144);
    if ( v33 && !ReleaseMutex(v33) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9DB,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v124);
    if ( v21 && !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v125);
  }
  else
  {
    memset(v148, 0, 0x148u);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
      v148,
      "MoUsoCoreWorkerRunning");
    v148[0] = &Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::`vftable';
    v36 = (char *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_1_unsigned_char_(
                    "1507.2603.28012.0",
                    &unk_1403BDC42,
                    0);
    if ( v36 == (char *)&unk_1403BDC42 || (v39 = &v36[-v38], v39 == (char *)-1LL) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v37);
    *(_QWORD *)&v134 = v38;
    *((_QWORD *)&v134 + 1) = v39;
    v137 = v134;
    Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::StartActivity(v148, &v137);
    *(_QWORD *)&v134 = v148;
    BYTE8(v134) = 1;
    hObject = 0;
    CreateServiceShutdownEvent(&hObject);
    *(_OWORD *)Handles = 0;
    pNumArgs = 1;
    ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      Handles,
      &pNumArgs);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::initOnceOutOfProc_,
      `Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_140549E10 = 1;
    v40 = (_QWORD *)SystemInterface::Service::GetSystem(v139);
    v41 = (*(__int64 (__fastcall **)(_QWORD, PSECURITY_DESCRIPTOR *))(*(_QWORD *)*v40 + 40LL))(*v40, SecurityDescriptor);
    v42 = *(_QWORD *)v41;
    v43 = *(__int64 (__fastcall **)(__int64, __int128 *, int *))(**(_QWORD **)v41 + 56LL);
    pNumArgs = 60;
    v137 = *(_OWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(
                        &MutexAttributes,
                        L"MoUsoCoreWorkerShutdownDelay");
    v44 = 1000 * v43(v42, &v137, &pNumArgs);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(SecurityDescriptor);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v139);
    try
    {
      v45 = (_QWORD *)SystemInterface::Service::GetSystem(v139);
      if ( Handles[0] )
        v46 = *(_QWORD *)Handles[0];
      else
        v46 = 0;
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v45 + 240LL))(*v45, v46, v44);
      std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v139);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x17B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        v47);
      v17 = v138;
      v21 = hHandle;
      v33 = hEvent[0];
    }
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::initOnceOutOfProc_,
      `Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_140549E10 = 1;
    v48 = Microsoft::WRL::Details::RegisterObjects<2>(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<2>,1,int>::instance_);
    if ( v48 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x17E,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
        (const char *)(unsigned int)v48,
        ppva);
    SecurityDescriptor[0] = 0;
    if ( g_usoSvcSupportsPrivateNamespaces )
    {
      Windows::PrivateNamespaceHelpers::TryOpenPrivateNamespaceEvent(SecurityDescriptor, L"\\UsoCoreWorkerStarted");
      if ( SecurityDescriptor[0] )
      {
        if ( !SetEvent(SecurityDescriptor[0]) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9C7,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            v49);
        if ( SecurityDescriptor[0] && !CloseHandle(SecurityDescriptor[0]) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x9D1,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            v50);
      }
    }
    else
    {
      v51 = 0;
      v52 = GlobalObjectName(&MutexAttributes, L"\\UsoCoreWorkerStarted");
      if ( *(_QWORD *)(v52 + 24) > 7u )
        v52 = *(_QWORD *)v52;
      v53 = OpenEventW(0x100002u, 0, (LPCWSTR)v52);
      if ( v53 )
      {
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          SecurityDescriptor,
          v53);
        v54 = 1;
        v51 = SecurityDescriptor[0];
      }
      else
      {
        v54 = 0;
      }
      std::wstring::~wstring(&MutexAttributes);
      if ( v54 && !SetEvent(v51) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9C7,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v55);
      if ( v51 && !CloseHandle(v51) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v56);
    }
    if ( Handles[0] )
      v57 = *(void **)Handles[0];
    else
      v57 = 0;
    hMem[0] = v57;
    hMem[1] = hObject;
    v58 = SystemInterface::Providers::GetSystem(v139);
    v59 = *(_QWORD *)v58 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v58 + 8LL) + 4LL);
    v60 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 192LL))(v59);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(v139);
    if ( v60 )
    {
      if ( WaitForMultipleObjectsEx(2u, hMem, 0, 0xFFFFFFFF, 0) == -1 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x19A,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
          v61);
    }
    else
    {
      memset(&MutexAttributes, 0, sizeof(MutexAttributes));
      while ( 1 )
      {
        v62 = MsgWaitForMultipleObjectsEx(2u, hMem, 0xFFFFFFFF, 0x1CFFu, 4u);
        if ( v62 == -1 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x1A7,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
            v63);
        if ( v62 != 2 )
          break;
        while ( PeekMessageW(&MutexAttributes, 0, 0, 0, 0) )
        {
          if ( GetMessageW(&MutexAttributes, 0, 0, 0) )
          {
            TranslateMessage(&MutexAttributes);
            DispatchMessageW(&MutexAttributes);
            v64 = WaitForMultipleObjects(2u, hMem, 0, 0);
            if ( v64 == -1 )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x1C0,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\coreworker\\MoUsoCoreWorker.cpp",
                v65);
            if ( v64 > 1 )
              continue;
          }
          goto LABEL_88;
        }
      }
    }
LABEL_88:
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &hObject,
      0);
    g_coreWorkerShuttingDown = 1;
    BYTE8(v134) = 0;
    wWinMain_::_65_::_lambda_2_::operator()(&v134);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::initOnceOutOfProc_,
      `Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_140549E10 = 1;
    Microsoft::WRL::Module<2,Microsoft::WRL::Details::DefaultModule<2>>::UnregisterObjects((Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<2>,1,int>::instance_);
    winrt::clear_factory_cache(v66);
    std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(Handles);
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v67);
    if ( BYTE8(v134) )
    {
      BYTE8(v134) = 0;
      wWinMain_::_65_::_lambda_2_::operator()(&v134);
    }
    v148[0] = &Windows::Telemetry::Worker::MoUsoCoreWorkerRunning::`vftable';
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v148);
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v148);
    if ( v144 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v144 + 16LL))(v144);
    if ( v33 && !ReleaseMutex(v33) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9DB,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v68);
    if ( v21 && !CloseHandle(v21) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x9D1,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v69);
  }
  if ( v17 )
    (**v17)(v17, 1);
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1400230ec  mov     rax, rsp
0x1400230ef  mov     [rax+8], rbx
0x1400230f3  mov     [rax+10h], rsi
0x1400230f7  push    rdi
0x1400230f8  push    r12
0x1400230fa  push    r13
0x1400230fc  push    r14
0x1400230fe  push    r15
0x140023100  sub     rsp, 2C0h
0x140023107  movaps  xmmword ptr [rax-38h], xmm6
0x14002310b  mov     rax, cs:__security_cookie
0x140023112  xor     rax, rsp
0x140023115  mov     [rsp+2E8h+var_48], rax
0x14002311d  mov     rbx, r8
0x140023120  xor     r15d, r15d
0x140023123  mov     [rsp+2E8h+pNumArgs], r15d
0x14002312b  lea     rcx, ?InvalidParameterHandler@@YAXPEB_W00I_K@Z; Handler
0x140023132  call    _set_invalid_parameter_handler
0x140023137  mov     [rsp+2E8h+pNumArgs], r15d
0x14002313f  lea     rdx, [rsp+2E8h+pNumArgs]; pNumArgs
0x140023147  mov     rcx, rbx; lpCmdLine
0x14002314a  call    cs:__imp_CommandLineToArgvW
0x140023150  mov     rbx, rax
0x140023153  test    rax, rax
0x140023156  jz      short loc_14002319A
0x140023158  mov     edi, r15d
0x14002315b  cmp     [rsp+2E8h+pNumArgs], r15d
0x140023163  jle     short loc_140023191
0x140023165  mov     rsi, rax
0x140023168  lea     rdx, aUseprivatename; "useprivatenamespaces"
0x14002316f  mov     rcx, [rsi]; String1
0x140023172  call    _wcsicmp
0x140023177  test    eax, eax
0x140023179  jnz     short loc_140023182
0x14002317b  mov     cs:?g_usoSvcSupportsPrivateNamespaces@@3_NA, 1; bool g_usoSvcSupportsPrivateNamespaces
0x140023182  inc     edi
0x140023184  add     rsi, 8
0x140023188  cmp     edi, [rsp+2E8h+pNumArgs]
0x14002318f  jl      short loc_140023168
0x140023191  mov     rcx, rbx; hMem
0x140023194  call    cs:__imp_LocalFree
0x14002319a  xor     edx, edx; dwCoInit
0x14002319c  xor     ecx, ecx; pvReserved
0x14002319e  call    cs:__imp_CoInitializeEx
0x1400231a4  mov     rcx, [rsp+2E8h]; this
0x1400231ac  test    eax, eax
0x1400231ae  js      loc_1400246A0
0x1400231b4  mov     [rsp+2E8h+var_288], 1
0x1400231b9  mov     [rsp+2E8h+pNumArgs], 4
0x1400231c4  lea     rcx, [rsp+2E8h+Handles]
0x1400231cc  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x1400231d1  nop
0x1400231d2  mov     rdx, [rax]
0x1400231d5  mov     rax, [rdx+8]
0x1400231d9  movsxd  rcx, dword ptr [rax+4]
0x1400231dd  add     rdx, 8
0x1400231e1  add     rcx, rdx
0x1400231e4  mov     rax, [rcx]
0x1400231e7  lea     rdx, [rsp+2E8h+var_278]
0x1400231ec  mov     rax, [rax+30h]
0x1400231f0  call    _guard_dispatch_icall
0x1400231f5  nop
0x1400231f6  mov     rcx, [rax]
0x1400231f9  mov     rax, [rcx]
0x1400231fc  mov     rax, [rax+28h]
0x140023200  call    _guard_dispatch_icall
0x140023205  mov     bl, al
0x140023207  lea     rcx, [rsp+2E8h+var_278]; void *
0x14002320c  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x140023211  nop
0x140023212  lea     rcx, [rsp+2E8h+Handles]; void *
0x14002321a  call    ??1?$shared_ptr@VInputBuilder@RebootDowntime@Windows@@@std@@QEAA@XZ; std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(void)
0x14002321f  test    bl, bl
0x140023221  jz      short loc_140023245
0x140023223  mov     ebx, r15d
0x140023226  call    cs:__imp_IsDebuggerPresent
0x14002322c  test    eax, eax
0x14002322e  jnz     short loc_140023245
0x140023230  mov     ecx, 3E8h; dwMilliseconds
0x140023235  call    cs:__imp_Sleep
0x14002323b  inc     ebx
0x14002323d  cmp     ebx, 0C8h
0x140023243  jl      short loc_140023226
0x140023245  jmp     short loc_14002324A
0x140023247  xor     r15d, r15d
0x14002324a  mov     [rsp+2E8h+var_268], r15
0x140023252  mov     ecx, 10h; Size
0x140023257  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002325c  mov     [rsp+2E8h+SecurityDescriptor], rax
0x140023264  lea     rdx, aMousocoreworke_1; "MoUsoCoreWorker"
0x14002326b  mov     rcx, rax; this
0x14002326e  call    ??0Session@uus@@QEAA@PEB_W@Z; uus::Session::Session(wchar_t const *)
0x140023273  mov     rdi, rax
0x140023276  mov     esi, 5
0x14002327b  mov     [rsp+2E8h+pNumArgs], esi
0x140023282  mov     [rsp+2E8h+var_268], rax
0x14002328a  jmp     short loc_14002329E
0x14002328c  xor     r15d, r15d
0x14002328f  mov     rdi, [rsp+2E8h+var_268]
0x140023297  mov     esi, [rsp+2E8h+pNumArgs]
0x14002329e  lea     rcx, [rsp+2E8h+var_278]
0x1400232a3  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1400232a8  nop
0x1400232a9  mov     rcx, [rax]
0x1400232ac  mov     rbx, [rsp+2E8h]
0x1400232b4  mov     rax, [rcx]
0x1400232b7  mov     rax, [rax+0B0h]
0x1400232be  call    _guard_dispatch_icall
0x1400232c3  test    al, al
0x1400232c5  jz      loc_1400246B5
0x1400232cb  mov     rbx, qword ptr [rsp+2E8h+var_278+8]
0x1400232d0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400232d4  test    rbx, rbx
0x1400232d7  jz      short loc_140023310
0x1400232d9  mov     eax, r14d
0x1400232dc  lock xadd [rbx+8], eax
0x1400232e1  add     eax, r14d
0x1400232e4  jnz     short loc_140023310
0x1400232e6  mov     rax, [rbx]
0x1400232e9  mov     rcx, rbx
0x1400232ec  mov     rax, [rax]
0x1400232ef  call    _guard_dispatch_icall
0x1400232f4  mov     eax, r14d
0x1400232f7  lock xadd [rbx+0Ch], eax
0x1400232fc  add     eax, r14d
0x1400232ff  jnz     short loc_140023310
0x140023301  mov     rax, [rbx]
0x140023304  mov     rcx, rbx
0x140023307  mov     rax, [rax+8]
0x14002330b  call    _guard_dispatch_icall
0x140023310  mov     rbx, r15
0x140023313  mov     [rsp+2E8h+hHandle], rbx
0x140023318  cmp     cs:?g_usoSvcSupportsPrivateNamespaces@@3_NA, r15b; bool g_usoSvcSupportsPrivateNamespaces
0x14002331f  jz      loc_140023487
0x140023325  xorps   xmm0, xmm0
0x140023328  xor     eax, eax
0x14002332a  movups  [rsp+2E8h+var_1E0], xmm0
0x140023332  mov     qword ptr [rsp+2E8h+var_1D0], rax
0x14002333a  lea     rcx, [rsp+2E8h+var_1E0]
0x140023342  call    _anonymous_namespace___GetSids
0x140023347  nop
0x140023348  xorps   xmm0, xmm0
0x14002334b  movups  xmmword ptr [rsp+2E8h+hMem], xmm0
0x140023353  lea     rdx, [rsp+2E8h+var_1E0]
0x14002335b  lea     rcx, [rsp+2E8h+hMem]
0x140023363  call    _anonymous_namespace___SecurityDescriptorAndAcls__SecurityDescriptorAndAcls
0x140023368  nop
0x140023369  mov     qword ptr [rsp+2E8h+MutexAttributes.nLength], 18h
0x140023375  mov     qword ptr [rsp+2E8h+MutexAttributes.bInheritHandle], 0
0x140023381  mov     rax, [rsp+2E8h+hMem+8]
0x140023389  mov     [rsp+2E8h+MutexAttributes.lpSecurityDescriptor], rax
0x140023391  lea     rcx, [rsp+2E8h+var_1E0]
0x140023399  call    _anonymous_namespace___CreateOrOpenPrivateNamespace
0x14002339e  mov     [rsp+2E8h+SecurityDescriptor], rbx
0x1400233a6  or      esi, 2
0x1400233a9  mov     [rsp+2E8h+pNumArgs], esi
0x1400233b0  lea     rdx, aUsocoreworkerr_0; "\\UsoCoreworkerRunning"
0x1400233b7  lea     rcx, [rsp+2E8h+var_258]
0x1400233bf  call    _anonymous_namespace___FullObjectName
0x1400233c4  nop
0x1400233c5  cmp     qword ptr [rax+18h], 7
0x1400233ca  jbe     short loc_1400233CF
0x1400233cc  mov     rax, [rax]
0x1400233cf  mov     r9d, 1F0001h; dwDesiredAccess
0x1400233d5  xor     r8d, r8d; dwFlags
0x1400233d8  mov     rdx, rax; lpName
0x1400233db  lea     rcx, [rsp+2E8h+MutexAttributes]; lpMutexAttributes
0x1400233e3  call    cs:__imp_CreateMutexExW
0x1400233e9  mov     rsi, rax
0x1400233ec  test    rax, rax
0x1400233ef  jz      short loc_140023414
0x1400233f1  call    cs:__imp_GetLastError
0x1400233f7  mov     rdx, rsi
0x1400233fa  lea     rcx, [rsp+2E8h+SecurityDescriptor]
0x140023402  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140023407  mov     eax, r15d
0x14002340a  mov     rbx, [rsp+2E8h+SecurityDescriptor]
0x140023412  jmp     short loc_140023419
0x140023414  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140023419  mov     rcx, [rsp+2E8h]; this
0x140023421  test    eax, eax
0x140023423  js      loc_1400246D0
0x140023429  lea     rcx, [rsp+2E8h+var_258]
0x140023431  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023436  nop
0x140023437  mov     rcx, [rsp+2E8h+hMem+8]; hMem
0x14002343f  test    rcx, rcx
0x140023442  jz      short loc_14002344A
0x140023444  call    cs:__imp_LocalFree
0x14002344a  mov     rcx, [rsp+2E8h+hMem]; Block
0x140023452  test    rcx, rcx
0x140023455  jz      short loc_140023462
0x140023457  mov     edx, 8
0x14002345c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140023461  nop
0x140023462  lea     rcx, [rsp+2E8h+var_1E0]
0x14002346a  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x14002346f  mov     rdx, rbx
0x140023472  lea     rcx, [rsp+2E8h+hHandle]
0x140023477  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14002347c  nop
0x14002347d  mov     rbx, [rsp+2E8h+hHandle]
0x140023482  jmp     loc_140023582
0x140023487  mov     dword ptr [rsp+2E8h+MutexAttributes+4], r15d
0x14002348f  mov     dword ptr [rsp+2E8h+MutexAttributes+14h], r15d
0x140023497  mov     [rsp+2E8h+SecurityDescriptor], r15
0x14002349f  xor     r9d, r9d; SecurityDescriptorSize
0x1400234a2  lea     r8, [rsp+2E8h+SecurityDescriptor]; SecurityDescriptor
0x1400234aa  lea     edx, [r9+1]; StringSDRevision
0x1400234ae  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x1400234b5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400234bb  mov     rcx, [rsp+2E8h]; this
0x1400234c3  test    eax, eax
0x1400234c5  jz      loc_1400246E5
0x1400234cb  mov     [rsp+2E8h+MutexAttributes.nLength], 18h
0x1400234d6  mov     rax, [rsp+2E8h+SecurityDescriptor]
0x1400234de  mov     [rsp+2E8h+MutexAttributes.lpSecurityDescriptor], rax
0x1400234e6  mov     [rsp+2E8h+MutexAttributes.bInheritHandle], r15d
0x1400234ee  lea     rdx, aUsocoreworkerr_0; "\\UsoCoreworkerRunning"
0x1400234f5  lea     rcx, [rsp+2E8h+var_1E0]; void *
0x1400234fd  call    ?GlobalObjectName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; GlobalObjectName(wchar_t const *)
0x140023502  nop
0x140023503  cmp     qword ptr [rax+18h], 7
0x140023508  jbe     short loc_14002350D
0x14002350a  mov     rax, [rax]
0x14002350d  mov     r9d, 1F0001h; dwDesiredAccess
0x140023513  xor     r8d, r8d; dwFlags
0x140023516  mov     rdx, rax; lpName
0x140023519  lea     rcx, [rsp+2E8h+MutexAttributes]; lpMutexAttributes
0x140023521  call    cs:__imp_CreateMutexExW
0x140023527  mov     rsi, rax
0x14002352a  test    rax, rax
0x14002352d  jz      short loc_14002354C
0x14002352f  call    cs:__imp_GetLastError
0x140023535  mov     rdx, rsi
0x140023538  lea     rcx, [rsp+2E8h+hHandle]
0x14002353d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140023542  mov     eax, r15d
0x140023545  mov     rbx, [rsp+2E8h+hHandle]
0x14002354a  jmp     short loc_140023551
0x14002354c  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140023551  mov     rcx, [rsp+2E8h]; this
0x140023559  test    eax, eax
0x14002355b  js      loc_1400246F7
0x140023561  lea     rcx, [rsp+2E8h+var_1E0]
0x140023569  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002356e  nop
0x14002356f  mov     rcx, [rsp+2E8h+SecurityDescriptor]; hMem
0x140023577  test    rcx, rcx
0x14002357a  jz      short loc_140023582
0x14002357c  call    cs:__imp_LocalFree
0x140023582  xor     r8d, r8d; bAlertable
0x140023585  or      r12d, 0FFFFFFFFh
0x140023589  mov     edx, r12d; dwMilliseconds
0x14002358c  mov     rcx, rbx; hHandle
0x14002358f  call    cs:__imp_WaitForSingleObjectEx
0x140023595  cmp     eax, 102h
0x14002359a  jz      short loc_1400235AC
0x14002359c  test    eax, 0FFFFFF7Fh
0x1400235a1  jnz     loc_14002470C
0x1400235a7  mov     r13, rbx
0x1400235aa  jmp     short loc_1400235AF
0x1400235ac  mov     r13, r15
0x1400235af  mov     [rsp+2E8h+hEvent], r13
0x1400235b4  mov     [rsp+2E8h+var_238], r13
0x1400235bc  mov     rcx, [rsp+2E8h]; this
0x1400235c4  cmp     eax, r12d
0x1400235c7  jz      loc_140024726
0x1400235cd  test    eax, 0FFFFFF7Fh
0x1400235d2  setnz   al
0x1400235d5  mov     rcx, [rsp+2E8h]; this
0x1400235dd  test    al, al
0x1400235df  jnz     loc_140024738
0x1400235e5  mov     [rsp+2E8h+var_1E8], r15
0x1400235ed  lea     rax, [rsp+2E8h+var_1E8]
0x1400235f5  mov     qword ptr [rsp+2E8h+ppv], rax; int
0x1400235fa  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x140023601  xor     edx, edx; pUnkOuter
0x140023603  lea     r8d, [rdx+1]; dwClsContext
0x140023607  lea     rcx, CLSID_GlobalOptions; rclsid
0x14002360e  call    cs:__imp_CoCreateInstance
0x140023614  mov     rcx, [rsp+2E8h]; this
0x14002361c  test    eax, eax
0x14002361e  js      loc_140024750
0x140023624  mov     rcx, [rsp+2E8h+var_1E8]
0x14002362c  mov     rax, [rcx]
0x14002362f  mov     edx, 1
0x140023634  lea     r8d, [rdx+1]
0x140023638  mov     rax, [rax+18h]
0x14002363c  call    _guard_dispatch_icall
0x140023641  mov     rcx, [rsp+2E8h]; this
0x140023649  test    eax, eax
0x14002364b  js      loc_140024765
0x140023651  mov     rcx, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140023658  lea     rax, ?FallbackTelemetryCallback@WorkerErrors@Telemetry@Windows@@SAX_NAEBUFailureInfo@wil@@@Z; Windows::Telemetry::WorkerErrors::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x14002365f  test    rcx, rcx
0x140023662  jz      short loc_14002366D
0x140023664  cmp     rcx, rax
0x140023667  jnz     loc_14002477A
0x14002366d  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rax
  ... truncated ...
```
