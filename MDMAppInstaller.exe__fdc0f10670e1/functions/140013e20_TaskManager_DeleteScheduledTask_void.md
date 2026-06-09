# TaskManager::DeleteScheduledTask(void)

- ea: `0x140013e20`
- end: `0x140013f2c`
- name: `?DeleteScheduledTask@TaskManager@@CAJXZ`
- size: `268`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140006dc8`
- `0x140013c90`
- `0x140013f34`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x140013e20`
- `0x140014174`
- `0x140014360`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013ea5`
- `OLEAUT32!__imp_SysAllocString` at `0x140013ea5`
- `OLEAUT32!__imp_SysFreeString` at `0x140013f05`
- `OLEAUT32!__imp_SysFreeString` at `0x140013f05`

## string_xrefs

- `0x140013ece`: `Successfully deleted the MDMAppInstaller scheduled task.`
- `0x140013f11`: `DeleteScheduledTask() failed.  Error = 0x%1!x!.`
- `0x140013e9e`: `Resume App Installation Actions`

## pseudocode

```c
__int64 TaskManager::DeleteScheduledTask(void)
{
  struct ITaskFolder *v0; // rdi
  OLECHAR *v1; // rbp
  int TaskService; // eax
  struct ITaskService *v3; // rsi
  int v4; // ebx
  int TaskFolder; // eax
  BSTR v6; // rax
  struct ITaskFolder *v8; // [rsp+40h] [rbp+8h] BYREF
  struct ITaskService *v9; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  v9 = 0;
  v8 = 0;
  v1 = 0;
  TaskService = TaskManager::GetTaskService(&v9);
  v3 = v9;
  v4 = TaskService;
  if ( TaskService >= 0 )
  {
    if ( !v9 )
    {
      v4 = -2147024882;
      goto LABEL_16;
    }
    TaskFolder = TaskManager::GetTaskFolder(v9, L"Microsoft\\Windows\\EnterpriseMgmt\\DesktopAppCSP", 0, &v8);
    v0 = v8;
    v4 = TaskFolder;
    if ( TaskFolder == -2147024894 )
    {
      v4 = 0;
    }
    else if ( TaskFolder >= 0 )
    {
      if ( v8 && (v6 = SysAllocString(L"Resume App Installation Actions"), (v1 = v6) != 0) )
      {
        v4 = ((__int64 (__fastcall *)(struct ITaskFolder *, BSTR, _QWORD))v0->lpVtbl->DeleteTask)(v0, v6, 0);
        if ( v4 >= 0 )
          LogInfo(L"Successfully deleted the MDMAppInstaller scheduled task.");
      }
      else
      {
        v4 = -2147024882;
      }
    }
  }
  if ( v3 )
    ((void (__fastcall *)(struct ITaskService *))v3->lpVtbl->Release)(v3);
  if ( v0 )
    ((void (__fastcall *)(struct ITaskFolder *))v0->lpVtbl->Release)(v0);
LABEL_16:
  SysFreeString(v1);
  if ( v4 < 0 )
    LogError(L"DeleteScheduledTask() failed.  Error = 0x%1!x!.", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140013e20  mov     rax, rsp
0x140013e23  mov     [rax+18h], rbx
0x140013e27  push    rbp
0x140013e28  push    rsi
0x140013e29  push    rdi
0x140013e2a  sub     rsp, 20h
0x140013e2e  xor     edi, edi
0x140013e30  mov     qword ptr [rax+10h], 0
0x140013e38  lea     rcx, [rax+10h]; struct ITaskService **
0x140013e3c  mov     [rax+8], rdi
0x140013e40  xor     ebp, ebp
0x140013e42  call    ?GetTaskService@TaskManager@@CAJPEAPEAUITaskService@@@Z; TaskManager::GetTaskService(ITaskService * *)
0x140013e47  mov     rsi, [rsp+38h+arg_8]
0x140013e4c  mov     ebx, eax
0x140013e4e  test    eax, eax
0x140013e50  js      loc_140013EDA
0x140013e56  test    rsi, rsi
0x140013e59  jnz     short loc_140013E65
0x140013e5b  mov     ebx, 8007000Eh
0x140013e60  jmp     loc_140013F02
0x140013e65  lea     r9, [rsp+38h+arg_0]; struct ITaskFolder **
0x140013e6a  xor     r8d, r8d; bool
0x140013e6d  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\EnterpriseMgmt\\Des"...
0x140013e74  mov     rcx, rsi; struct ITaskService *
0x140013e77  call    ?GetTaskFolder@TaskManager@@CAJPEAUITaskService@@PEBG_NPEAPEAUITaskFolder@@@Z; TaskManager::GetTaskFolder(ITaskService *,ushort const *,bool,ITaskFolder * *)
0x140013e7c  mov     rdi, [rsp+38h+arg_0]
0x140013e81  mov     ebx, eax
0x140013e83  cmp     eax, 80070002h
0x140013e88  jnz     short loc_140013E8E
0x140013e8a  xor     ebx, ebx
0x140013e8c  jmp     short loc_140013EDA
0x140013e8e  test    eax, eax
0x140013e90  js      short loc_140013EDA
0x140013e92  test    rdi, rdi
0x140013e95  jnz     short loc_140013E9E
0x140013e97  mov     ebx, 8007000Eh
0x140013e9c  jmp     short loc_140013EDA
0x140013e9e  lea     rcx, psz; "Resume App Installation Actions"
0x140013ea5  call    cs:__imp_SysAllocString
0x140013eab  mov     rbp, rax
0x140013eae  test    rax, rax
0x140013eb1  jz      short loc_140013E97
0x140013eb3  mov     rax, [rdi]
0x140013eb6  xor     r8d, r8d
0x140013eb9  mov     rdx, rbp
0x140013ebc  mov     rcx, rdi
0x140013ebf  mov     rax, [rax+78h]
0x140013ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ec8  mov     ebx, eax
0x140013eca  test    eax, eax
0x140013ecc  js      short loc_140013EDA
0x140013ece  lea     rcx, aSuccessfullyDe; "Successfully deleted the MDMAppInstalle"...
0x140013ed5  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140013eda  test    rsi, rsi
0x140013edd  jz      short loc_140013EEE
0x140013edf  mov     rax, [rsi]
0x140013ee2  mov     rcx, rsi
0x140013ee5  mov     rax, [rax+10h]
0x140013ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013eee  test    rdi, rdi
0x140013ef1  jz      short loc_140013F02
0x140013ef3  mov     rax, [rdi]
0x140013ef6  mov     rcx, rdi
0x140013ef9  mov     rax, [rax+10h]
0x140013efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f02  mov     rcx, rbp; bstrString
0x140013f05  call    cs:__imp_SysFreeString
0x140013f0b  test    ebx, ebx
0x140013f0d  jns     short loc_140013F1D
0x140013f0f  mov     edx, ebx
0x140013f11  lea     rcx, aDeleteschedule; "DeleteScheduledTask() failed.  Error = "...
0x140013f18  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140013f1d  mov     eax, ebx
0x140013f1f  mov     rbx, [rsp+38h+arg_10]
0x140013f24  add     rsp, 20h
0x140013f28  pop     rdi
0x140013f29  pop     rsi
0x140013f2a  pop     rbp
0x140013f2b  retn
```
