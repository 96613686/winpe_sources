# TaskManager::RegisteredTaskExists(ushort const *,bool &)

- ea: `0x140014664`
- end: `0x1400147e4`
- name: `?RegisteredTaskExists@TaskManager@@CAJPEBGAEA_N@Z`
- size: `384`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140006dc8`
- `0x140013c90`
- `0x140015108`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x140014360`
- `0x140014664`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400146bc`
- `OLEAUT32!__imp_SysAllocString` at `0x140014716`
- `OLEAUT32!__imp_SysAllocString` at `0x1400146bc`
- `OLEAUT32!__imp_SysAllocString` at `0x140014716`
- `OLEAUT32!__imp_SysFreeString` at `0x140014762`
- `OLEAUT32!__imp_SysFreeString` at `0x14001476b`
- `OLEAUT32!__imp_SysFreeString` at `0x140014762`
- `OLEAUT32!__imp_SysFreeString` at `0x14001476b`

## string_xrefs

- `0x1400146f8`: `Scheduled Task folder %1 was not found.`
- `0x14001474f`: `Scheduled Task %1 was not found.`
- `0x1400147c5`: `RegisteredTaskExists() failed.  Error = 0x%1!x!.`
- `0x14001470f`: `Resume App Installation Actions`

## pseudocode

```c
__int64 __fastcall TaskManager::RegisteredTaskExists(const unsigned __int16 *a1, bool *a2)
{
  OLECHAR *v2; // rsi
  OLECHAR *v4; // rdi
  int TaskService; // eax
  struct ITaskService *v6; // r14
  int v7; // ebx
  BSTR v8; // rax
  int v9; // eax
  BSTR v10; // rax
  __int64 v12; // [rsp+50h] [rbp+30h] BYREF
  __int64 v13; // [rsp+58h] [rbp+38h] BYREF
  struct ITaskService *v14; // [rsp+60h] [rbp+40h] BYREF

  v2 = 0;
  v14 = 0;
  *a2 = 0;
  v13 = 0;
  v12 = 0;
  v4 = 0;
  TaskService = TaskManager::GetTaskService((LPVOID *)&v14);
  v6 = v14;
  v7 = TaskService;
  if ( TaskService < 0 )
    goto LABEL_14;
  v8 = SysAllocString(L"Microsoft\\Windows\\EnterpriseMgmt\\DesktopAppCSP");
  v4 = v8;
  if ( !v8 )
    goto LABEL_3;
  v9 = ((__int64 (__fastcall *)(struct ITaskService *, BSTR, __int64 *))v6->lpVtbl->GetFolder)(v6, v8, &v12);
  if ( v9 < 0 )
  {
    if ( v9 == -2147024894 )
    {
      LogInfo(L"Scheduled Task folder %1 was not found.", v4);
      return 0;
    }
    goto LABEL_13;
  }
  if ( v12 )
  {
    v10 = SysAllocString(L"Resume App Installation Actions");
    v2 = v10;
    if ( v10 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v12 + 104LL))(v12, v10, &v13);
      if ( v9 >= 0 )
      {
        *a2 = 1;
        goto LABEL_14;
      }
      if ( v9 == -2147024894 )
      {
        LogInfo(L"Scheduled Task %1 was not found.", v2);
        goto LABEL_14;
      }
LABEL_13:
      v7 = v9;
      goto LABEL_14;
    }
  }
LABEL_3:
  v7 = -2147024882;
LABEL_14:
  SysFreeString(v4);
  SysFreeString(v2);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v6 )
    ((void (__fastcall *)(struct ITaskService *))v6->lpVtbl->Release)(v6);
  if ( v7 < 0 )
    LogError(L"RegisteredTaskExists() failed.  Error = 0x%1!x!.", (unsigned int)v7);
  return 0;
}

```

## disassembly

```asm
0x140014664  mov     [rsp-28h+arg_18], rbx
0x140014669  mov     [rsp-28h+arg_0], rcx
0x14001466e  push    rbp
0x14001466f  push    rsi
0x140014670  push    rdi
0x140014671  push    r14
0x140014673  push    r15
0x140014675  mov     rbp, rsp
0x140014678  sub     rsp, 20h
0x14001467c  xor     esi, esi
0x14001467e  mov     [rbp+arg_10], 0
0x140014686  lea     rcx, [rbp+arg_10]; struct ITaskService **
0x14001468a  mov     [rdx], sil
0x14001468d  mov     r15, rdx
0x140014690  mov     [rbp+arg_8], 0
0x140014698  mov     [rbp+arg_0], 0
0x1400146a0  xor     edi, edi
0x1400146a2  call    ?GetTaskService@TaskManager@@CAJPEAPEAUITaskService@@@Z; TaskManager::GetTaskService(ITaskService * *)
0x1400146a7  mov     r14, [rbp+arg_10]
0x1400146ab  mov     ebx, eax
0x1400146ad  test    eax, eax
0x1400146af  js      loc_14001475F
0x1400146b5  lea     rcx, aMicrosoftWindo; "Microsoft\\Windows\\EnterpriseMgmt\\Des"...
0x1400146bc  call    cs:__imp_SysAllocString
0x1400146c2  mov     rdi, rax
0x1400146c5  test    rax, rax
0x1400146c8  jnz     short loc_1400146D4
0x1400146ca  mov     ebx, 8007000Eh
0x1400146cf  jmp     loc_14001475F
0x1400146d4  mov     rax, [r14]
0x1400146d7  lea     r8, [rbp+arg_0]
0x1400146db  mov     rdx, rdi
0x1400146de  mov     rcx, r14
0x1400146e1  mov     rax, [rax+38h]
0x1400146e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146ea  test    eax, eax
0x1400146ec  jns     short loc_140014709
0x1400146ee  cmp     eax, 80070002h
0x1400146f3  jnz     short loc_14001475D
0x1400146f5  mov     rdx, rdi
0x1400146f8  lea     rcx, aScheduledTaskF; "Scheduled Task folder %1 was not found."
0x1400146ff  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x140014704  jmp     loc_1400147D1
0x140014709  cmp     [rbp+arg_0], rsi
0x14001470d  jz      short loc_1400146CA
0x14001470f  lea     rcx, psz; "Resume App Installation Actions"
0x140014716  call    cs:__imp_SysAllocString
0x14001471c  mov     rsi, rax
0x14001471f  test    rax, rax
0x140014722  jz      short loc_1400146CA
0x140014724  mov     rcx, [rbp+arg_0]
0x140014728  lea     r8, [rbp+arg_8]
0x14001472c  mov     rdx, rsi
0x14001472f  mov     rax, [rcx]
0x140014732  mov     rax, [rax+68h]
0x140014736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001473b  test    eax, eax
0x14001473d  js      short loc_140014745
0x14001473f  mov     byte ptr [r15], 1
0x140014743  jmp     short loc_14001475F
0x140014745  cmp     eax, 80070002h
0x14001474a  jnz     short loc_14001475D
0x14001474c  mov     rdx, rsi
0x14001474f  lea     rcx, aScheduledTask1; "Scheduled Task %1 was not found."
0x140014756  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14001475b  jmp     short loc_14001475F
0x14001475d  mov     ebx, eax
0x14001475f  mov     rcx, rdi; bstrString
0x140014762  call    cs:__imp_SysFreeString
0x140014768  mov     rcx, rsi; bstrString
0x14001476b  call    cs:__imp_SysFreeString
0x140014771  mov     rcx, [rbp+arg_0]
0x140014775  test    rcx, rcx
0x140014778  jz      short loc_14001478E
0x14001477a  mov     rax, [rcx]
0x14001477d  mov     rax, [rax+10h]
0x140014781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014786  mov     [rbp+arg_0], 0
0x14001478e  mov     rcx, [rbp+arg_8]
0x140014792  test    rcx, rcx
0x140014795  jz      short loc_1400147AB
0x140014797  mov     rax, [rcx]
0x14001479a  mov     rax, [rax+10h]
0x14001479e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400147a3  mov     [rbp+arg_8], 0
0x1400147ab  test    r14, r14
0x1400147ae  jz      short loc_1400147BF
0x1400147b0  mov     rax, [r14]
0x1400147b3  mov     rcx, r14
0x1400147b6  mov     rax, [rax+10h]
0x1400147ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400147bf  test    ebx, ebx
0x1400147c1  jns     short loc_1400147D1
0x1400147c3  mov     edx, ebx
0x1400147c5  lea     rcx, aRegisteredtask; "RegisteredTaskExists() failed.  Error ="...
0x1400147cc  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400147d1  mov     rbx, [rsp+20h+arg_18]
0x1400147d6  xor     eax, eax
0x1400147d8  add     rsp, 20h
0x1400147dc  pop     r15
0x1400147de  pop     r14
0x1400147e0  pop     rdi
0x1400147e1  pop     rsi
0x1400147e2  pop     rbp
0x1400147e3  retn
```
