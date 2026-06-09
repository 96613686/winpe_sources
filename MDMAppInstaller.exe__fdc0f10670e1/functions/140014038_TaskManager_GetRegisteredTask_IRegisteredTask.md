# TaskManager::GetRegisteredTask(IRegisteredTask * *)

- ea: `0x140014038`
- end: `0x14001416b`
- name: `?GetRegisteredTask@TaskManager@@CAJPEAPEAUIRegisteredTask@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140015108`

## callees

- `0x14000740c`
- `0x140014038`
- `0x140014174`
- `0x140014360`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400140bf`
- `OLEAUT32!__imp_SysAllocString` at `0x1400140bf`
- `OLEAUT32!__imp_SysFreeString` at `0x140014140`
- `OLEAUT32!__imp_SysFreeString` at `0x140014140`

## string_xrefs

- `0x14001414c`: `GetRegisteredTask() failed.  Error = 0x%1!x!.`
- `0x1400140b8`: `Resume App Installation Actions`

## pseudocode

```c
__int64 __fastcall TaskManager::GetRegisteredTask(struct IRegisteredTask **a1)
{
  struct ITaskFolder *v1; // rdi
  OLECHAR *v3; // r14
  int TaskService; // eax
  struct ITaskService *v5; // rsi
  int v6; // ebx
  int TaskFolder; // eax
  BSTR v8; // rax
  struct IRegisteredTask *v10; // [rsp+50h] [rbp+30h] BYREF
  struct ITaskFolder *v11; // [rsp+58h] [rbp+38h] BYREF
  struct ITaskService *v12; // [rsp+60h] [rbp+40h] BYREF

  v1 = 0;
  v12 = 0;
  *a1 = 0;
  v10 = 0;
  v11 = 0;
  v3 = 0;
  TaskService = TaskManager::GetTaskService(&v12);
  v5 = v12;
  v6 = TaskService;
  if ( TaskService >= 0 )
  {
    if ( !v12 )
    {
      v6 = -2147024882;
      goto LABEL_12;
    }
    TaskFolder = TaskManager::GetTaskFolder(v12, L"Microsoft\\Windows\\EnterpriseMgmt\\DesktopAppCSP", 0, &v11);
    v1 = v11;
    v6 = TaskFolder;
    if ( TaskFolder >= 0 )
    {
      if ( v11 && (v8 = SysAllocString(L"Resume App Installation Actions"), (v3 = v8) != 0) )
      {
        v6 = ((__int64 (__fastcall *)(struct ITaskFolder *, BSTR, struct IRegisteredTask **))v1->lpVtbl->GetTask)(
               v1,
               v8,
               &v10);
        if ( v6 >= 0 )
        {
          *a1 = v10;
          v10 = 0;
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  if ( v5 )
    ((void (__fastcall *)(struct ITaskService *))v5->lpVtbl->Release)(v5);
LABEL_12:
  if ( v10 )
  {
    ((void (__fastcall *)(struct IRegisteredTask *))v10->lpVtbl->Release)(v10);
    v10 = 0;
  }
  if ( v1 )
    ((void (__fastcall *)(struct ITaskFolder *))v1->lpVtbl->Release)(v1);
  SysFreeString(v3);
  if ( v6 < 0 )
    LogError(L"GetRegisteredTask() failed.  Error = 0x%1!x!.", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140014038  mov     [rsp-28h+arg_18], rbx
0x14001403d  push    rbp
0x14001403e  push    rsi
0x14001403f  push    rdi
0x140014040  push    r14
0x140014042  push    r15
0x140014044  mov     rbp, rsp
0x140014047  sub     rsp, 20h
0x14001404b  xor     edi, edi
0x14001404d  mov     [rbp+arg_10], 0
0x140014055  mov     [rcx], rdi
0x140014058  mov     r15, rcx
0x14001405b  lea     rcx, [rbp+arg_10]; struct ITaskService **
0x14001405f  mov     [rbp+arg_0], 0
0x140014067  mov     [rbp+arg_8], rdi
0x14001406b  xor     r14d, r14d
0x14001406e  call    ?GetTaskService@TaskManager@@CAJPEAPEAUITaskService@@@Z; TaskManager::GetTaskService(ITaskService * *)
0x140014073  mov     rsi, [rbp+arg_10]
0x140014077  mov     ebx, eax
0x140014079  test    eax, eax
0x14001407b  js      short loc_1400140F8
0x14001407d  test    rsi, rsi
0x140014080  jnz     short loc_14001408C
0x140014082  mov     ebx, 8007000Eh
0x140014087  jmp     loc_14001410C
0x14001408c  lea     r9, [rbp+arg_8]; struct ITaskFolder **
0x140014090  xor     r8d, r8d; bool
0x140014093  lea     rdx, aMicrosoftWindo; "Microsoft\\Windows\\EnterpriseMgmt\\Des"...
0x14001409a  mov     rcx, rsi; struct ITaskService *
0x14001409d  call    ?GetTaskFolder@TaskManager@@CAJPEAUITaskService@@PEBG_NPEAPEAUITaskFolder@@@Z; TaskManager::GetTaskFolder(ITaskService *,ushort const *,bool,ITaskFolder * *)
0x1400140a2  mov     rdi, [rbp+arg_8]
0x1400140a6  mov     ebx, eax
0x1400140a8  test    eax, eax
0x1400140aa  js      short loc_1400140F8
0x1400140ac  test    rdi, rdi
0x1400140af  jnz     short loc_1400140B8
0x1400140b1  mov     ebx, 8007000Eh
0x1400140b6  jmp     short loc_1400140F8
0x1400140b8  lea     rcx, psz; "Resume App Installation Actions"
0x1400140bf  call    cs:__imp_SysAllocString
0x1400140c5  mov     r14, rax
0x1400140c8  test    rax, rax
0x1400140cb  jz      short loc_1400140B1
0x1400140cd  mov     rax, [rdi]
0x1400140d0  lea     r8, [rbp+arg_0]
0x1400140d4  mov     rdx, r14
0x1400140d7  mov     rcx, rdi
0x1400140da  mov     rax, [rax+68h]
0x1400140de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400140e3  mov     ebx, eax
0x1400140e5  test    eax, eax
0x1400140e7  js      short loc_1400140F8
0x1400140e9  mov     rax, [rbp+arg_0]
0x1400140ed  mov     [r15], rax
0x1400140f0  mov     [rbp+arg_0], 0
0x1400140f8  test    rsi, rsi
0x1400140fb  jz      short loc_14001410C
0x1400140fd  mov     rax, [rsi]
0x140014100  mov     rcx, rsi
0x140014103  mov     rax, [rax+10h]
0x140014107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001410c  mov     rcx, [rbp+arg_0]
0x140014110  test    rcx, rcx
0x140014113  jz      short loc_140014129
0x140014115  mov     rax, [rcx]
0x140014118  mov     rax, [rax+10h]
0x14001411c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014121  mov     [rbp+arg_0], 0
0x140014129  test    rdi, rdi
0x14001412c  jz      short loc_14001413D
0x14001412e  mov     rax, [rdi]
0x140014131  mov     rcx, rdi
0x140014134  mov     rax, [rax+10h]
0x140014138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001413d  mov     rcx, r14; bstrString
0x140014140  call    cs:__imp_SysFreeString
0x140014146  test    ebx, ebx
0x140014148  jns     short loc_140014158
0x14001414a  mov     edx, ebx
0x14001414c  lea     rcx, aGetregisteredt; "GetRegisteredTask() failed.  Error = 0x"...
0x140014153  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140014158  mov     eax, ebx
0x14001415a  mov     rbx, [rsp+20h+arg_18]
0x14001415f  add     rsp, 20h
0x140014163  pop     r15
0x140014165  pop     r14
0x140014167  pop     rdi
0x140014168  pop     rsi
0x140014169  pop     rbp
0x14001416a  retn
```
