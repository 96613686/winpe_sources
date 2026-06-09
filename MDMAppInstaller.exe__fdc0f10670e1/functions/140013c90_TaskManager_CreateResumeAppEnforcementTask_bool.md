# TaskManager::CreateResumeAppEnforcementTask(bool)

- ea: `0x140013c90`
- end: `0x140013e19`
- name: `?CreateResumeAppEnforcementTask@TaskManager@@CAJ_N@Z`
- size: `393`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140006dc8`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x140013c90`
- `0x140013e20`
- `0x140014360`
- `0x140014488`
- `0x140014664`
- `0x1400147ec`
- `0x1400149f8`
- `0x140014be4`
- `0x140014e1c`
- `0x140014f2c`
- `0x14001c010`

## import_xrefs

- `ole32!CoUninitialize` at `0x140013df2`
- `ole32!CoUninitialize` at `0x140013df2`
- `ole32!CoInitializeEx` at `0x140013cb0`
- `ole32!CoInitializeEx` at `0x140013cb0`

## string_xrefs

- `0x140013db5`: `Successfully created the MDMAppInstaller scheduled task. [LOGON trigger = %1]`
- `0x140013dfe`: `CreateResumeAppEnforcementTask() failed.  Error = 0x%1!x!.`

## pseudocode

```c
__int64 __fastcall TaskManager::CreateResumeAppEnforcementTask(bool a1)
{
  struct ITaskService *v2; // rdi
  HRESULT v3; // ebx
  int TaskService; // eax
  const unsigned __int16 *v5; // rcx
  bool v6; // dl
  bool v7; // dl
  const wchar_t *v8; // rdx
  struct ITaskService *v10; // [rsp+48h] [rbp+28h] BYREF
  struct ITaskDefinition *v11; // [rsp+50h] [rbp+30h] BYREF

  v2 = 0;
  v10 = 0;
  v11 = 0;
  v3 = CoInitializeEx(0, 0);
  if ( v3 >= 0 )
  {
    TaskService = TaskManager::GetTaskService(&v10);
    v2 = v10;
    v3 = TaskService;
    if ( TaskService >= 0 )
    {
      if ( v10 )
      {
        LOBYTE(v10) = 0;
        v3 = TaskManager::RegisteredTaskExists(v5, (bool *)&v10);
        if ( v3 >= 0 )
        {
          if ( !(_BYTE)v10 || (v3 = TaskManager::DeleteScheduledTask(), v3 >= 0) )
          {
            v3 = ((__int64 (__fastcall *)(struct ITaskService *, _QWORD, struct ITaskDefinition **))v2->lpVtbl->NewTask)(
                   v2,
                   0,
                   &v11);
            if ( v3 >= 0 )
            {
              if ( !v11 )
              {
                v3 = -2147024882;
                goto LABEL_22;
              }
              v3 = TaskManager::SetTaskSettings(v11, v6);
              if ( v3 >= 0 )
              {
                v3 = TaskManager::SetStartupTrigger(v11, v7);
                if ( v3 >= 0 )
                {
                  v3 = TaskManager::SetLogonTrigger(v11, a1);
                  if ( v3 >= 0 )
                  {
                    v3 = TaskManager::SetTaskAction(v11);
                    if ( v3 >= 0 )
                    {
                      v3 = TaskManager::SetTaskPrincipalToSystem(v11);
                      if ( v3 >= 0 )
                      {
                        v3 = TaskManager::RegisterTask(v2, v11);
                        if ( v3 >= 0 )
                        {
                          v8 = L"ENABLED";
                          if ( !a1 )
                            v8 = L"DISABLED";
                          LogInfo(L"Successfully created the MDMAppInstaller scheduled task. [LOGON trigger = %1]", v8);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      else
      {
        v3 = -2147024882;
      }
    }
  }
  if ( v11 )
  {
    ((void (__fastcall *)(struct ITaskDefinition *))v11->lpVtbl->Release)(v11);
    v11 = 0;
  }
LABEL_22:
  if ( v2 )
    ((void (__fastcall *)(struct ITaskService *))v2->lpVtbl->Release)(v2);
  CoUninitialize();
  if ( v3 < 0 )
    LogError(L"CreateResumeAppEnforcementTask() failed.  Error = 0x%1!x!.", (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140013c90  mov     [rsp-18h+arg_0], rbx
0x140013c95  push    rbp
0x140013c96  push    rsi
0x140013c97  push    rdi
0x140013c98  mov     rbp, rsp
0x140013c9b  sub     rsp, 20h
0x140013c9f  mov     sil, cl
0x140013ca2  xor     edi, edi
0x140013ca4  xor     ecx, ecx; pvReserved
0x140013ca6  mov     [rbp+arg_8], rdi
0x140013caa  xor     edx, edx; dwCoInit
0x140013cac  mov     [rbp+arg_10], rdi
0x140013cb0  call    cs:__imp_CoInitializeEx
0x140013cb6  mov     ebx, eax
0x140013cb8  test    eax, eax
0x140013cba  js      loc_140013DC1
0x140013cc0  lea     rcx, [rbp+arg_8]; struct ITaskService **
0x140013cc4  call    ?GetTaskService@TaskManager@@CAJPEAPEAUITaskService@@@Z; TaskManager::GetTaskService(ITaskService * *)
0x140013cc9  mov     rdi, [rbp+arg_8]
0x140013ccd  mov     ebx, eax
0x140013ccf  test    eax, eax
0x140013cd1  js      loc_140013DC1
0x140013cd7  test    rdi, rdi
0x140013cda  jnz     short loc_140013CE6
0x140013cdc  mov     ebx, 8007000Eh
0x140013ce1  jmp     loc_140013DC1
0x140013ce6  lea     rdx, [rbp+arg_8]; bool *
0x140013cea  mov     byte ptr [rbp+arg_8], 0
0x140013cee  call    ?RegisteredTaskExists@TaskManager@@CAJPEBGAEA_N@Z; TaskManager::RegisteredTaskExists(ushort const *,bool &)
0x140013cf3  mov     ebx, eax
0x140013cf5  test    eax, eax
0x140013cf7  js      loc_140013DC1
0x140013cfd  cmp     byte ptr [rbp+arg_8], 0
0x140013d01  jz      short loc_140013D12
0x140013d03  call    ?DeleteScheduledTask@TaskManager@@CAJXZ; TaskManager::DeleteScheduledTask(void)
0x140013d08  mov     ebx, eax
0x140013d0a  test    eax, eax
0x140013d0c  js      loc_140013DC1
0x140013d12  mov     rax, [rdi]
0x140013d15  lea     r8, [rbp+arg_10]
0x140013d19  xor     edx, edx
0x140013d1b  mov     rcx, rdi
0x140013d1e  mov     rax, [rax+48h]
0x140013d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d27  mov     ebx, eax
0x140013d29  test    eax, eax
0x140013d2b  js      loc_140013DC1
0x140013d31  mov     rcx, [rbp+arg_10]; struct ITaskDefinition *
0x140013d35  test    rcx, rcx
0x140013d38  jnz     short loc_140013D44
0x140013d3a  mov     ebx, 8007000Eh
0x140013d3f  jmp     loc_140013DDE
0x140013d44  call    ?SetTaskSettings@TaskManager@@CAJPEAUITaskDefinition@@_N@Z; TaskManager::SetTaskSettings(ITaskDefinition *,bool)
0x140013d49  mov     ebx, eax
0x140013d4b  test    eax, eax
0x140013d4d  js      short loc_140013DC1
0x140013d4f  mov     rcx, [rbp+arg_10]; struct ITaskDefinition *
0x140013d53  call    ?SetStartupTrigger@TaskManager@@CAJPEAUITaskDefinition@@_N@Z; TaskManager::SetStartupTrigger(ITaskDefinition *,bool)
0x140013d58  mov     ebx, eax
0x140013d5a  test    eax, eax
0x140013d5c  js      short loc_140013DC1
0x140013d5e  mov     rcx, [rbp+arg_10]; struct ITaskDefinition *
0x140013d62  mov     dl, sil; bool
0x140013d65  call    ?SetLogonTrigger@TaskManager@@CAJPEAUITaskDefinition@@_N@Z; TaskManager::SetLogonTrigger(ITaskDefinition *,bool)
0x140013d6a  mov     ebx, eax
0x140013d6c  test    eax, eax
0x140013d6e  js      short loc_140013DC1
0x140013d70  mov     rcx, [rbp+arg_10]; struct ITaskDefinition *
0x140013d74  call    ?SetTaskAction@TaskManager@@CAJPEAUITaskDefinition@@@Z; TaskManager::SetTaskAction(ITaskDefinition *)
0x140013d79  mov     ebx, eax
0x140013d7b  test    eax, eax
0x140013d7d  js      short loc_140013DC1
0x140013d7f  mov     rcx, [rbp+arg_10]; struct ITaskDefinition *
0x140013d83  call    ?SetTaskPrincipalToSystem@TaskManager@@CAJPEAUITaskDefinition@@@Z; TaskManager::SetTaskPrincipalToSystem(ITaskDefinition *)
0x140013d88  mov     ebx, eax
0x140013d8a  test    eax, eax
0x140013d8c  js      short loc_140013DC1
0x140013d8e  mov     rdx, [rbp+arg_10]; struct ITaskDefinition *
0x140013d92  mov     rcx, rdi; struct ITaskService *
0x140013d95  call    ?RegisterTask@TaskManager@@CAJPEAUITaskService@@PEAUITaskDefinition@@@Z; TaskManager::RegisterTask(ITaskService *,ITaskDefinition *)
0x140013d9a  mov     ebx, eax
0x140013d9c  test    eax, eax
0x140013d9e  js      short loc_140013DC1
0x140013da0  test    sil, sil
0x140013da3  lea     rax, aDisabled; "DISABLED"
0x140013daa  lea     rdx, aEnabled; "ENABLED"
0x140013db1  cmovz   rdx, rax
0x140013db5  lea     rcx, aSuccessfullyCr; "Successfully created the MDMAppInstalle"...
0x140013dbc  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140013dc1  mov     rcx, [rbp+arg_10]
0x140013dc5  test    rcx, rcx
0x140013dc8  jz      short loc_140013DDE
0x140013dca  mov     rax, [rcx]
0x140013dcd  mov     rax, [rax+10h]
0x140013dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013dd6  mov     [rbp+arg_10], 0
0x140013dde  test    rdi, rdi
0x140013de1  jz      short loc_140013DF2
0x140013de3  mov     rax, [rdi]
0x140013de6  mov     rcx, rdi
0x140013de9  mov     rax, [rax+10h]
0x140013ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013df2  call    cs:__imp_CoUninitialize
0x140013df8  test    ebx, ebx
0x140013dfa  jns     short loc_140013E0A
0x140013dfc  mov     edx, ebx
0x140013dfe  lea     rcx, aCreateresumeap; "CreateResumeAppEnforcementTask() failed"...
0x140013e05  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140013e0a  mov     eax, ebx
0x140013e0c  mov     rbx, [rsp+20h+arg_0]
0x140013e11  add     rsp, 20h
0x140013e15  pop     rdi
0x140013e16  pop     rsi
0x140013e17  pop     rbp
0x140013e18  retn
```
