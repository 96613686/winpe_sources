# Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::_scalar_deleting_destructor_

- ea: `0x180010580`
- end: `0x1800105b4`
- name: `Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::_scalar_deleting_destructor_`
- size: `52`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002054`
- `0x18000f994`
- `0x180010580`

## pseudocode

```c
_QWORD *__fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::_scalar_deleting_destructor_(
        _QWORD *a1,
        char a2)
{
  Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010580  mov     [rsp+arg_0], rbx
0x180010585  push    rdi
0x180010586  sub     rsp, 20h
0x18001058a  mov     ebx, edx
0x18001058c  mov     rdi, rcx
0x18001058f  call    Concurrency__details___PPLTaskHandle_unsigned_char_Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency__details___TypeSelectorNoAsync__Concurrency__details___TaskProcHandle_____PPLTaskHandle_unsigned_char_Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency__details___TypeSelectorNoAsync__Concurrency__details___TaskProcHandle_
0x180010594  test    bl, 1
0x180010597  jz      short loc_1800105A6
0x180010599  mov     edx, 18h; unsigned __int64
0x18001059e  mov     rcx, rdi; void *
0x1800105a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800105a6  mov     rbx, [rsp+28h+arg_0]
0x1800105ab  mov     rax, rdi
0x1800105ae  add     rsp, 20h
0x1800105b2  pop     rdi
0x1800105b3  retn
```
