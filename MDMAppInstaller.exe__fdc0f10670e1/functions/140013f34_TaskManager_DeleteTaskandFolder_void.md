# TaskManager::DeleteTaskandFolder(void)

- ea: `0x140013f34`
- end: `0x140014031`
- name: `?DeleteTaskandFolder@TaskManager@@SAJXZ`
- size: `253`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006dc8`

## callees

- `0x14000740c`
- `0x140013e20`
- `0x140013f34`
- `0x140014174`
- `0x140014360`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140013fba`
- `OLEAUT32!__imp_SysAllocString` at `0x140013fba`
- `OLEAUT32!__imp_SysFreeString` at `0x14001400a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001400a`

## string_xrefs

- `0x140014016`: `DeleteTaskandFolder() failed.  Error = 0x%1!x!.`

## pseudocode

```c
__int64 TaskManager::DeleteTaskandFolder(void)
{
  struct ITaskFolder *v0; // rdi
  OLECHAR *v1; // rbp
  int v2; // ebx
  int TaskService; // eax
  struct ITaskService *v4; // rsi
  int TaskFolder; // eax
  BSTR v6; // rax
  struct ITaskFolder *v8; // [rsp+40h] [rbp+8h] BYREF
  struct ITaskService *v9; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  v9 = 0;
  v8 = 0;
  v1 = 0;
  v2 = TaskManager::DeleteScheduledTask();
  if ( v2 >= 0 )
  {
    TaskService = TaskManager::GetTaskService(&v9);
    v4 = v9;
    v2 = TaskService;
    if ( TaskService >= 0 )
    {
      if ( !v9 )
      {
        v2 = -2147024882;
        goto LABEL_14;
      }
      TaskFolder = TaskManager::GetTaskFolder(v9, L"Microsoft\\Windows\\EnterpriseMgmt", 0, &v8);
      v0 = v8;
      v2 = TaskFolder;
      if ( TaskFolder >= 0 )
      {
        if ( v8 && (v6 = SysAllocString(L"DesktopAppCSP"), (v1 = v6) != 0) )
          v2 = ((__int64 (__fastcall *)(struct ITaskFolder *, BSTR, _QWORD))v0->lpVtbl->DeleteFolder)(v0, v6, 0);
        else
          v2 = -2147024882;
      }
    }
    if ( v4 )
      ((void (__fastcall *)(struct ITaskService *))v4->lpVtbl->Release)(v4);
    if ( v0 )
      ((void (__fastcall *)(struct ITaskFolder *))v0->lpVtbl->Release)(v0);
  }
LABEL_14:
  SysFreeString(v1);
  if ( v2 < 0 )
    LogError(L"DeleteTaskandFolder() failed.  Error = 0x%1!x!.", (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140013f34  mov     [rsp+arg_10], rbx
0x140013f39  push    rbp
0x140013f3a  push    rsi
0x140013f3b  push    rdi
0x140013f3c  sub     rsp, 20h
0x140013f40  xor     edi, edi
0x140013f42  mov     [rsp+38h+arg_8], 0
0x140013f4b  mov     [rsp+38h+arg_0], rdi
0x140013f50  xor     ebp, ebp
0x140013f52  call    ?DeleteScheduledTask@TaskManager@@CAJXZ; TaskManager::DeleteScheduledTask(void)
0x140013f57  mov     ebx, eax
0x140013f59  test    eax, eax
0x140013f5b  js      loc_140014007
0x140013f61  lea     rcx, [rsp+38h+arg_8]; struct ITaskService **
0x140013f66  call    ?GetTaskService@TaskManager@@CAJPEAPEAUITaskService@@@Z; TaskManager::GetTaskService(ITaskService * *)
0x140013f6b  mov     rsi, [rsp+38h+arg_8]
0x140013f70  mov     ebx, eax
0x140013f72  test    eax, eax
0x140013f74  js      short loc_140013FDF
0x140013f76  test    rsi, rsi
0x140013f79  jnz     short loc_140013F85
0x140013f7b  mov     ebx, 8007000Eh
0x140013f80  jmp     loc_140014007
0x140013f85  lea     r9, [rsp+38h+arg_0]; struct ITaskFolder **
0x140013f8a  xor     r8d, r8d; bool
0x140013f8d  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows\\EnterpriseMgmt"
0x140013f94  mov     rcx, rsi; struct ITaskService *
0x140013f97  call    ?GetTaskFolder@TaskManager@@CAJPEAUITaskService@@PEBG_NPEAPEAUITaskFolder@@@Z; TaskManager::GetTaskFolder(ITaskService *,ushort const *,bool,ITaskFolder * *)
0x140013f9c  mov     rdi, [rsp+38h+arg_0]
0x140013fa1  mov     ebx, eax
0x140013fa3  test    eax, eax
0x140013fa5  js      short loc_140013FDF
0x140013fa7  test    rdi, rdi
0x140013faa  jnz     short loc_140013FB3
0x140013fac  mov     ebx, 8007000Eh
0x140013fb1  jmp     short loc_140013FDF
0x140013fb3  lea     rcx, aDesktopappcsp; "DesktopAppCSP"
0x140013fba  call    cs:__imp_SysAllocString
0x140013fc0  mov     rbp, rax
0x140013fc3  test    rax, rax
0x140013fc6  jz      short loc_140013FAC
0x140013fc8  mov     rax, [rdi]
0x140013fcb  xor     r8d, r8d
0x140013fce  mov     rdx, rbp
0x140013fd1  mov     rcx, rdi
0x140013fd4  mov     rax, [rax+60h]
0x140013fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013fdd  mov     ebx, eax
0x140013fdf  test    rsi, rsi
0x140013fe2  jz      short loc_140013FF3
0x140013fe4  mov     rax, [rsi]
0x140013fe7  mov     rcx, rsi
0x140013fea  mov     rax, [rax+10h]
0x140013fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ff3  test    rdi, rdi
0x140013ff6  jz      short loc_140014007
0x140013ff8  mov     rax, [rdi]
0x140013ffb  mov     rcx, rdi
0x140013ffe  mov     rax, [rax+10h]
0x140014002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014007  mov     rcx, rbp; bstrString
0x14001400a  call    cs:__imp_SysFreeString
0x140014010  test    ebx, ebx
0x140014012  jns     short loc_140014022
0x140014014  mov     edx, ebx
0x140014016  lea     rcx, aDeletetaskandf; "DeleteTaskandFolder() failed.  Error = "...
0x14001401d  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140014022  mov     eax, ebx
0x140014024  mov     rbx, [rsp+38h+arg_10]
0x140014029  add     rsp, 20h
0x14001402d  pop     rdi
0x14001402e  pop     rsi
0x14001402f  pop     rbp
0x140014030  retn
```
