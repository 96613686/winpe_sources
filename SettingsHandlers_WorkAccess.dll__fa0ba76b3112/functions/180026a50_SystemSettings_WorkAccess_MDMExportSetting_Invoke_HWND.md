# SystemSettings::WorkAccess::MDMExportSetting::Invoke(HWND__ *)

- ea: `0x180026a50`
- end: `0x180026ab8`
- name: `?Invoke@MDMExportSetting@WorkAccess@SystemSettings@@UEAAJPEAUHWND__@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(PVOID pv, HWND)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800096ec`
- `0x180026a50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180026aa3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180026aa3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180026a66`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180026a66`

## string_xrefs

- `0x180026a83`: `shellcommon\shell\settingshandlers\workaccess\lib\connectworkschoolaccountsetting.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::MDMExportSetting::Invoke(PVOID pv, HWND a2)
{
  struct _TP_WORK *ThreadpoolWork; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  ThreadpoolWork = CreateThreadpoolWork(SystemSettings::WorkAccess::MDMExportSetting::s_DeviceManagementWorker, pv, 0);
  *((_QWORD *)pv + 27) = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    SubmitThreadpoolWork(ThreadpoolWork);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\connectworkschoolaccountsetting.cpp",
      (const char *)0x80004005LL,
      v5);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180026a50  push    rbx; int
0x180026a52  sub     rsp, 20h
0x180026a56  mov     rbx, rcx
0x180026a59  mov     rdx, rcx; pv
0x180026a5c  lea     rcx, ?s_DeviceManagementWorker@MDMExportSetting@WorkAccess@SystemSettings@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180026a63  xor     r8d, r8d; pcbe
0x180026a66  call    cs:__imp_CreateThreadpoolWork
0x180026a6d  nop     dword ptr [rax+rax+00h]
0x180026a72  mov     [rbx+0D8h], rax
0x180026a79  test    rax, rax
0x180026a7c  jnz     short loc_180026AA0
0x180026a7e  mov     rcx, [rsp+28h]; this
0x180026a83  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\settingshandlers\\w"...
0x180026a8a  mov     ebx, 80004005h
0x180026a8f  mov     edx, 144h; void *
0x180026a94  mov     r9d, ebx; char *
0x180026a97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026a9c  mov     eax, ebx
0x180026a9e  jmp     short loc_180026AB1
0x180026aa0  mov     rcx, rax; pwk
0x180026aa3  call    cs:__imp_SubmitThreadpoolWork
0x180026aaa  nop     dword ptr [rax+rax+00h]
0x180026aaf  xor     eax, eax
0x180026ab1  add     rsp, 20h
0x180026ab5  pop     rbx
0x180026ab6  retn
```
