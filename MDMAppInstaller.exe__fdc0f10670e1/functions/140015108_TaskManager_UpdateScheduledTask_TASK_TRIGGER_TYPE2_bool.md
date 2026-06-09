# TaskManager::UpdateScheduledTask(_TASK_TRIGGER_TYPE2,bool)

- ea: `0x140015108`
- end: `0x14001541d`
- name: `?UpdateScheduledTask@TaskManager@@SAJW4_TASK_TRIGGER_TYPE2@@_N@Z`
- size: `789`
- prototype: `__int64 __fastcall(enum _TASK_TRIGGER_TYPE2, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update`

## callers

- `0x140006dc8`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x140014038`
- `0x140014360`
- `0x140014488`
- `0x140014664`
- `0x140015108`
- `0x14001c010`

## import_xrefs

- `ole32!CoUninitialize` at `0x1400153eb`
- `ole32!CoUninitialize` at `0x1400153eb`
- `ole32!CoInitializeEx` at `0x14001513f`
- `ole32!CoInitializeEx` at `0x14001513f`

## string_xrefs

- `0x14001531e`: `Updated MDMAppInstaller task [%1 trigger = %2]`
- `0x140015357`: `No change to MDMAppInstaller task. [%1 trigger = %2]`
- `0x1400153f7`: `UpdateScheduledTask() failed.  Error = 0x%1!x!.`

## pseudocode

```c
__int64 __fastcall TaskManager::UpdateScheduledTask(enum _TASK_TRIGGER_TYPE2 a1, unsigned __int8 a2)
{
  struct ITaskService *v2; // rdi
  const unsigned __int16 *v5; // rcx
  HRESULT v6; // ebx
  int TaskService; // eax
  int RegisteredTask; // eax
  struct IRegisteredTask *v9; // rsi
  int v10; // r14d
  unsigned __int16 v11; // r15
  const wchar_t *v12; // rcx
  const wchar_t *v13; // r8
  const wchar_t *v14; // rdx
  __int64 v16; // [rsp+20h] [rbp-20h] BYREF
  struct ITaskDefinition *v17; // [rsp+28h] [rbp-18h] BYREF
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  struct IRegisteredTask *v19; // [rsp+38h] [rbp-8h] BYREF
  __int16 v20; // [rsp+88h] [rbp+48h] BYREF
  int v21; // [rsp+90h] [rbp+50h] BYREF
  struct ITaskService *v22; // [rsp+98h] [rbp+58h] BYREF

  v2 = 0;
  v22 = 0;
  v19 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  v6 = CoInitializeEx(0, 0);
  if ( v6 >= 0 )
  {
    LOBYTE(v20) = 0;
    v6 = TaskManager::RegisteredTaskExists(v5, (bool *)&v20);
    if ( v6 >= 0 )
    {
      if ( !(_BYTE)v20 )
      {
        v6 = 0;
        goto LABEL_38;
      }
      TaskService = TaskManager::GetTaskService((LPVOID *)&v22);
      v2 = v22;
      v6 = TaskService;
      if ( TaskService >= 0 )
      {
        if ( !v22 )
          goto LABEL_37;
        RegisteredTask = TaskManager::GetRegisteredTask(&v19);
        v9 = v19;
        v6 = RegisteredTask;
        if ( RegisteredTask < 0 )
          goto LABEL_35;
        if ( !v19 )
        {
LABEL_37:
          v6 = -2147024882;
          goto LABEL_38;
        }
        v6 = ((__int64 (__fastcall *)(struct IRegisteredTask *, struct ITaskDefinition **))v19->lpVtbl->get_Definition)(
               v19,
               &v17);
        if ( v6 >= 0 )
        {
          if ( v17 )
          {
            v6 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))v17->lpVtbl->get_Triggers)(v17, &v18);
            if ( v6 < 0 )
              goto LABEL_35;
            if ( v18 )
            {
              v21 = 0;
              v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v21);
              if ( v6 >= 0 )
              {
                v10 = 1;
                v11 = (a2 ^ 1) - 1;
                while ( 1 )
                {
                  if ( v10 > v21 )
                  {
                    v12 = L"No change to MDMAppInstaller task. [%1 trigger = %2]";
                    goto LABEL_28;
                  }
                  LODWORD(v22) = 0;
                  v20 = 0;
                  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v18 + 64LL))(
                         v18,
                         (unsigned int)v10,
                         &v16);
                  if ( v6 < 0 )
                    goto LABEL_35;
                  if ( !v16 )
                    goto LABEL_34;
                  v6 = (*(__int64 (__fastcall **)(__int64, struct ITaskService **))(*(_QWORD *)v16 + 56LL))(v16, &v22);
                  if ( v6 < 0 )
                    goto LABEL_35;
                  v6 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v16 + 144LL))(v16, &v20);
                  if ( v6 < 0 )
                    goto LABEL_35;
                  if ( (_DWORD)v22 == a1 && v20 != v11 )
                    break;
                  if ( v16 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
                    v16 = 0;
                  }
                  ++v10;
                }
                v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 152LL))(v16, v11);
                if ( v6 < 0 )
                  goto LABEL_35;
                v6 = TaskManager::RegisterTask(v2, v17);
                if ( v6 < 0 )
                  goto LABEL_35;
                v12 = L"Updated MDMAppInstaller task [%1 trigger = %2]";
LABEL_28:
                v13 = L"ENABLED";
                if ( !a2 )
                  v13 = L"DISABLED";
                v14 = L"RESTART";
                if ( a1 != TASK_TRIGGER_BOOT )
                  v14 = L"LOGON";
                LogInfo(v12, v14, v13);
              }
              goto LABEL_35;
            }
          }
LABEL_34:
          v6 = -2147024882;
        }
LABEL_35:
        if ( v9 )
          ((void (__fastcall *)(struct IRegisteredTask *))v9->lpVtbl->Release)(v9);
      }
    }
  }
LABEL_38:
  if ( v17 )
  {
    ((void (__fastcall *)(struct ITaskDefinition *))v17->lpVtbl->Release)(v17);
    v17 = 0;
  }
  if ( v2 )
    ((void (__fastcall *)(struct ITaskService *))v2->lpVtbl->Release)(v2);
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
  }
  CoUninitialize();
  if ( v6 < 0 )
    LogError(L"UpdateScheduledTask() failed.  Error = 0x%1!x!.", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140015108  mov     [rsp-38h+arg_0], rbx
0x14001510d  push    rbp
0x14001510e  push    rsi
0x14001510f  push    rdi
0x140015110  push    r12
0x140015112  push    r13
0x140015114  push    r14
0x140015116  push    r15
0x140015118  mov     rbp, rsp
0x14001511b  sub     rsp, 40h
0x14001511f  xor     edi, edi
0x140015121  mov     r13b, dl
0x140015124  mov     r12d, ecx
0x140015127  mov     [rbp+arg_18], rdi
0x14001512b  xor     edx, edx; dwCoInit
0x14001512d  mov     [rbp+var_8], rdi
0x140015131  xor     ecx, ecx; pvReserved
0x140015133  mov     [rbp+var_18], rdi
0x140015137  mov     [rbp+var_10], rdi
0x14001513b  mov     [rbp+var_20], rdi
0x14001513f  call    cs:__imp_CoInitializeEx
0x140015145  mov     ebx, eax
0x140015147  test    eax, eax
0x140015149  js      loc_140015380
0x14001514f  lea     rdx, [rbp+arg_8]; bool *
0x140015153  mov     byte ptr [rbp+arg_8], dil
0x140015157  call    ?RegisteredTaskExists@TaskManager@@CAJPEBGAEA_N@Z; TaskManager::RegisteredTaskExists(ushort const *,bool &)
0x14001515c  mov     ebx, eax
0x14001515e  test    eax, eax
0x140015160  js      loc_140015380
0x140015166  cmp     byte ptr [rbp+arg_8], dil
0x14001516a  jnz     short loc_140015173
0x14001516c  xor     ebx, ebx
0x14001516e  jmp     loc_140015380
0x140015173  lea     rcx, [rbp+arg_18]; struct ITaskService **
0x140015177  call    ?GetTaskService@TaskManager@@CAJPEAPEAUITaskService@@@Z; TaskManager::GetTaskService(ITaskService * *)
0x14001517c  mov     rdi, [rbp+arg_18]
0x140015180  mov     ebx, eax
0x140015182  test    eax, eax
0x140015184  js      loc_140015380
0x14001518a  test    rdi, rdi
0x14001518d  jz      loc_14001537B
0x140015193  lea     rcx, [rbp+var_8]; struct IRegisteredTask **
0x140015197  call    ?GetRegisteredTask@TaskManager@@CAJPEAPEAUIRegisteredTask@@@Z; TaskManager::GetRegisteredTask(IRegisteredTask * *)
0x14001519c  mov     rsi, [rbp+var_8]
0x1400151a0  mov     ebx, eax
0x1400151a2  test    eax, eax
0x1400151a4  js      loc_140015365
0x1400151aa  test    rsi, rsi
0x1400151ad  jz      loc_14001537B
0x1400151b3  mov     rax, [rsi]
0x1400151b6  lea     rdx, [rbp+var_18]
0x1400151ba  mov     rcx, rsi
0x1400151bd  mov     rax, [rax+98h]
0x1400151c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151c9  mov     ebx, eax
0x1400151cb  test    eax, eax
0x1400151cd  js      loc_140015365
0x1400151d3  mov     rcx, [rbp+var_18]
0x1400151d7  test    rcx, rcx
0x1400151da  jz      loc_140015360
0x1400151e0  mov     rax, [rcx]
0x1400151e3  lea     rdx, [rbp+var_10]
0x1400151e7  mov     rax, [rax+48h]
0x1400151eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400151f0  mov     ebx, eax
0x1400151f2  test    eax, eax
0x1400151f4  js      loc_140015365
0x1400151fa  mov     rcx, [rbp+var_10]
0x1400151fe  test    rcx, rcx
0x140015201  jz      loc_140015360
0x140015207  mov     [rbp+arg_10], 0
0x14001520e  lea     rdx, [rbp+arg_10]
0x140015212  mov     rax, [rcx]
0x140015215  mov     rax, [rax+38h]
0x140015219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001521e  mov     ebx, eax
0x140015220  test    eax, eax
0x140015222  js      loc_140015365
0x140015228  mov     ecx, 1
0x14001522d  mov     al, r13b
0x140015230  xor     al, cl
0x140015232  mov     r14d, ecx
0x140015235  movzx   r15d, al
0x140015239  sub     r15w, cx
0x14001523d  cmp     r14d, [rbp+arg_10]
0x140015241  jg      loc_140015357
0x140015247  mov     rcx, [rbp+var_10]
0x14001524b  lea     r8, [rbp+var_20]
0x14001524f  xor     eax, eax
0x140015251  mov     dword ptr [rbp+arg_18], 0
0x140015258  mov     [rbp+arg_8], ax
0x14001525c  mov     edx, r14d
0x14001525f  mov     rax, [rcx]
0x140015262  mov     rax, [rax+40h]
0x140015266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001526b  mov     ebx, eax
0x14001526d  test    eax, eax
0x14001526f  js      loc_140015365
0x140015275  mov     rcx, [rbp+var_20]
0x140015279  test    rcx, rcx
0x14001527c  jz      loc_140015360
0x140015282  mov     rax, [rcx]
0x140015285  lea     rdx, [rbp+arg_18]
0x140015289  mov     rax, [rax+38h]
0x14001528d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015292  mov     ebx, eax
0x140015294  test    eax, eax
0x140015296  js      loc_140015365
0x14001529c  mov     rcx, [rbp+var_20]
0x1400152a0  lea     rdx, [rbp+arg_8]
0x1400152a4  mov     rax, [rcx]
0x1400152a7  mov     rax, [rax+90h]
0x1400152ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152b3  mov     ebx, eax
0x1400152b5  test    eax, eax
0x1400152b7  js      loc_140015365
0x1400152bd  cmp     dword ptr [rbp+arg_18], r12d
0x1400152c1  jnz     short loc_1400152CA
0x1400152c3  cmp     [rbp+arg_8], r15w
0x1400152c8  jnz     short loc_1400152EF
0x1400152ca  mov     rcx, [rbp+var_20]
0x1400152ce  test    rcx, rcx
0x1400152d1  jz      short loc_1400152E7
0x1400152d3  mov     rax, [rcx]
0x1400152d6  mov     rax, [rax+10h]
0x1400152da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400152df  mov     [rbp+var_20], 0
0x1400152e7  inc     r14d
0x1400152ea  jmp     loc_14001523D
0x1400152ef  mov     rcx, [rbp+var_20]
0x1400152f3  movzx   edx, r15w
0x1400152f7  mov     rax, [rcx]
0x1400152fa  mov     rax, [rax+98h]
0x140015301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015306  mov     ebx, eax
0x140015308  test    eax, eax
0x14001530a  js      short loc_140015365
0x14001530c  mov     rdx, [rbp+var_18]; struct ITaskDefinition *
0x140015310  mov     rcx, rdi; struct ITaskService *
0x140015313  call    ?RegisterTask@TaskManager@@CAJPEAUITaskService@@PEAUITaskDefinition@@@Z; TaskManager::RegisterTask(ITaskService *,ITaskDefinition *)
0x140015318  mov     ebx, eax
0x14001531a  test    eax, eax
0x14001531c  js      short loc_140015365
0x14001531e  lea     rcx, aUpdatedMdmappi; "Updated MDMAppInstaller task [%1 trigge"...
0x140015325  test    r13b, r13b
0x140015328  lea     rax, aDisabled; "DISABLED"
0x14001532f  lea     r8, aEnabled; "ENABLED"
0x140015336  cmovz   r8, rax
0x14001533a  lea     rdx, aRestart; "RESTART"
0x140015341  cmp     r12d, 8
0x140015345  lea     rax, aLogon; "LOGON"
0x14001534c  cmovnz  rdx, rax
0x140015350  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140015355  jmp     short loc_140015365
0x140015357  lea     rcx, aNoChangeToMdma; "No change to MDMAppInstaller task. [%1 "...
0x14001535e  jmp     short loc_140015325
0x140015360  mov     ebx, 8007000Eh
0x140015365  test    rsi, rsi
0x140015368  jz      short loc_140015380
0x14001536a  mov     rax, [rsi]
0x14001536d  mov     rcx, rsi
0x140015370  mov     rax, [rax+10h]
0x140015374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015379  jmp     short loc_140015380
0x14001537b  mov     ebx, 8007000Eh
0x140015380  mov     rcx, [rbp+var_18]
0x140015384  test    rcx, rcx
0x140015387  jz      short loc_14001539D
0x140015389  mov     rax, [rcx]
0x14001538c  mov     rax, [rax+10h]
0x140015390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015395  mov     [rbp+var_18], 0
0x14001539d  test    rdi, rdi
0x1400153a0  jz      short loc_1400153B1
0x1400153a2  mov     rax, [rdi]
0x1400153a5  mov     rcx, rdi
0x1400153a8  mov     rax, [rax+10h]
0x1400153ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400153b1  mov     rcx, [rbp+var_10]
0x1400153b5  test    rcx, rcx
0x1400153b8  jz      short loc_1400153CE
0x1400153ba  mov     rax, [rcx]
0x1400153bd  mov     rax, [rax+10h]
0x1400153c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400153c6  mov     [rbp+var_10], 0
0x1400153ce  mov     rcx, [rbp+var_20]
0x1400153d2  test    rcx, rcx
0x1400153d5  jz      short loc_1400153EB
0x1400153d7  mov     rax, [rcx]
0x1400153da  mov     rax, [rax+10h]
0x1400153de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400153e3  mov     [rbp+var_20], 0
0x1400153eb  call    cs:__imp_CoUninitialize
0x1400153f1  test    ebx, ebx
0x1400153f3  jns     short loc_140015403
0x1400153f5  mov     edx, ebx
0x1400153f7  lea     rcx, aUpdateschedule; "UpdateScheduledTask() failed.  Error = "...
0x1400153fe  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140015403  mov     eax, ebx
0x140015405  mov     rbx, [rsp+40h+arg_0]
0x14001540d  add     rsp, 40h
0x140015411  pop     r15
0x140015413  pop     r14
0x140015415  pop     r13
0x140015417  pop     r12
0x140015419  pop     rdi
0x14001541a  pop     rsi
0x14001541b  pop     rbp
0x14001541c  retn
```
