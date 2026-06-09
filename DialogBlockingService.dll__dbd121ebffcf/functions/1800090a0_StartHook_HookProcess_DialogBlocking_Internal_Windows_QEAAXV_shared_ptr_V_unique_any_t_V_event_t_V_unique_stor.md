# ?StartHook@HookProcess@DialogBlocking@Internal@Windows@@QEAAXV?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@@Z

- ea: `0x1800090a0`
- end: `0x18000919a`
- name: `?StartHook@HookProcess@DialogBlocking@Internal@Windows@@QEAAXV?$shared_ptr@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@std@@@Z`
- size: `250`
- prototype: `void __fastcall(Windows::Internal::DialogBlocking::HookProcess *this, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008b04`

## callees

- `0x180008bbc`
- `0x1800090a0`
- `0x1800091a0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009134`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009134`

## pseudocode

```c
void __fastcall Windows::Internal::DialogBlocking::HookProcess::StartHook(
        Windows::Internal::DialogBlocking::HookProcess *this,
        _QWORD *a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rbx
  LPVOID pv[9]; // [rsp+20h] [rbp-48h] BYREF

  v4 = a2[1];
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  v5 = a2[1];
  *((_QWORD *)this + 3) = *a2;
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = v5;
  if ( v6 )
  {
    if ( !_InterlockedDecrement(v6 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( !_InterlockedDecrement(v6 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand(this, pv);
  Windows::Internal::DialogBlocking::HookProcess::StartProcess(this, (const unsigned __int16 *)pv[0]);
  if ( pv[0] )
  {
    CoTaskMemFree(pv[0]);
    pv[0] = 0;
  }
  pv[1] = 0;
  pv[2] = 0;
  v7 = (volatile signed __int32 *)a2[1];
  if ( v7 && !_InterlockedDecrement(v7 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
    if ( !_InterlockedDecrement(v7 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
  }
}

```

## disassembly

```asm
0x1800090a0  mov     [rsp+arg_8], rdx
0x1800090a5  push    rbx
0x1800090a6  push    rbp
0x1800090a7  push    rsi
0x1800090a8  push    rdi
0x1800090a9  sub     rsp, 48h
0x1800090ad  mov     rdi, rdx
0x1800090b0  mov     rsi, rcx
0x1800090b3  mov     rax, [rdx+8]
0x1800090b7  test    rax, rax
0x1800090ba  jz      short loc_1800090C0
0x1800090bc  lock inc dword ptr [rax+8]
0x1800090c0  mov     rcx, [rdx+8]
0x1800090c4  mov     rax, [rdx]
0x1800090c7  mov     [rsi+18h], rax
0x1800090cb  mov     rbx, [rsi+20h]
0x1800090cf  mov     [rsi+20h], rcx
0x1800090d3  or      ebp, 0FFFFFFFFh
0x1800090d6  test    rbx, rbx
0x1800090d9  jz      short loc_18000910E
0x1800090db  mov     eax, ebp
0x1800090dd  lock xadd [rbx+8], eax
0x1800090e2  add     eax, ebp
0x1800090e4  jnz     short loc_18000910E
0x1800090e6  mov     rax, [rbx]
0x1800090e9  mov     rcx, rbx
0x1800090ec  mov     rax, [rax]
0x1800090ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f4  mov     eax, ebp
0x1800090f6  lock xadd [rbx+0Ch], eax
0x1800090fb  add     eax, ebp
0x1800090fd  jnz     short loc_18000910E
0x1800090ff  mov     rax, [rbx]
0x180009102  mov     rcx, rbx
0x180009105  mov     rax, [rax+8]
0x180009109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000910e  lea     rdx, [rsp+68h+pv]
0x180009113  mov     rcx, rsi
0x180009116  call    ?BuildHookLaunchCommand@HookProcess@DialogBlocking@Internal@Windows@@AEAA?AV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@XZ; Windows::Internal::DialogBlocking::HookProcess::BuildHookLaunchCommand(void)
0x18000911b  nop
0x18000911c  mov     rdx, [rsp+68h+pv]; unsigned __int16 *
0x180009121  mov     rcx, rsi; this
0x180009124  call    ?StartProcess@HookProcess@DialogBlocking@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::DialogBlocking::HookProcess::StartProcess(ushort const *)
0x180009129  nop
0x18000912a  mov     rcx, [rsp+68h+pv]; pv
0x18000912f  test    rcx, rcx
0x180009132  jz      short loc_180009143
0x180009134  call    cs:__imp_CoTaskMemFree
0x18000913a  mov     [rsp+68h+pv], 0
0x180009143  mov     [rsp+68h+var_40], 0
0x18000914c  mov     [rsp+68h+var_38], 0
0x180009155  mov     rbx, [rdi+8]
0x180009159  test    rbx, rbx
0x18000915c  jz      short loc_180009191
0x18000915e  mov     eax, ebp
0x180009160  lock xadd [rbx+8], eax
0x180009165  add     eax, ebp
0x180009167  jnz     short loc_180009191
0x180009169  mov     rax, [rbx]
0x18000916c  mov     rcx, rbx
0x18000916f  mov     rax, [rax]
0x180009172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009177  mov     eax, ebp
0x180009179  lock xadd [rbx+0Ch], eax
0x18000917e  add     eax, ebp
0x180009180  jnz     short loc_180009191
0x180009182  mov     rax, [rbx]
0x180009185  mov     rcx, rbx
0x180009188  mov     rax, [rax+8]
0x18000918c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009191  add     rsp, 48h
0x180009195  pop     rdi
0x180009196  pop     rsi
0x180009197  pop     rbp
0x180009198  pop     rbx
0x180009199  retn
```
