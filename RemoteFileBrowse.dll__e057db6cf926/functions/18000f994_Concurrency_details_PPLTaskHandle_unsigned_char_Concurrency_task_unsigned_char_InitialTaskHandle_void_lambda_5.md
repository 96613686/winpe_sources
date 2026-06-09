# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_

- ea: `0x18000f994`
- end: `0x18000fa11`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010530`
- `0x180010580`

## callees

- `0x18000f994`
- `0x180019010`

## import_xrefs

- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18000f9b6`
- `msvcp_win!?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ` at `0x18000f9b6`

## pseudocode

```c
void **__fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void **result; // rax

  *a1 = &off_18001A798;
  Concurrency::details::_TaskEventLogger::_LogTaskCompleted((Concurrency::details::_TaskEventLogger *)(a1[1] + 352LL));
  v2 = (volatile signed __int32 *)a1[2];
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  result = &Concurrency::details::_TaskProcHandle::`vftable';
  *a1 = &Concurrency::details::_TaskProcHandle::`vftable';
  return result;
}

```

## disassembly

```asm
0x18000f994  mov     [rsp+arg_0], rbx
0x18000f999  push    rdi
0x18000f99a  sub     rsp, 20h
0x18000f99e  mov     rdi, rcx
0x18000f9a1  lea     rax, off_18001A798
0x18000f9a8  mov     [rcx], rax
0x18000f9ab  mov     rcx, [rcx+8]
0x18000f9af  add     rcx, 160h
0x18000f9b6  call    cs:__imp_?_LogTaskCompleted@_TaskEventLogger@details@Concurrency@@QEAAXXZ; Concurrency::details::_TaskEventLogger::_LogTaskCompleted(void)
0x18000f9bc  mov     rbx, [rdi+10h]
0x18000f9c0  test    rbx, rbx
0x18000f9c3  jz      short loc_18000F9FC
0x18000f9c5  or      eax, 0FFFFFFFFh
0x18000f9c8  lock xadd [rbx+8], eax
0x18000f9cd  cmp     eax, 1
0x18000f9d0  jnz     short loc_18000F9FC
0x18000f9d2  mov     rax, [rbx]
0x18000f9d5  mov     rcx, rbx
0x18000f9d8  mov     rax, [rax]
0x18000f9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9e0  or      eax, 0FFFFFFFFh
0x18000f9e3  lock xadd [rbx+0Ch], eax
0x18000f9e8  cmp     eax, 1
0x18000f9eb  jnz     short loc_18000F9FC
0x18000f9ed  mov     rax, [rbx]
0x18000f9f0  mov     rcx, rbx
0x18000f9f3  mov     rax, [rax+8]
0x18000f9f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9fc  lea     rax, ??_7_TaskProcHandle@details@Concurrency@@6B@; const Concurrency::details::_TaskProcHandle::`vftable'
0x18000fa03  mov     [rdi], rax
0x18000fa06  mov     rbx, [rsp+28h+arg_0]
0x18000fa0b  add     rsp, 20h
0x18000fa0f  pop     rdi
0x18000fa10  retn
```
