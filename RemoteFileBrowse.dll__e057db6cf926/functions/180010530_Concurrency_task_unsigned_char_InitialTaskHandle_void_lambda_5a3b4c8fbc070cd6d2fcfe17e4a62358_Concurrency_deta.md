# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_scalar_deleting_destructor_

- ea: `0x180010530`
- end: `0x18001056e`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_scalar_deleting_destructor_`
- size: `62`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002054`
- `0x18000f994`
- `0x180010530`

## pseudocode

```c
_QWORD *__fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync_::_scalar_deleting_destructor_(
        _QWORD *a1,
        char a2)
{
  *a1 = &off_18001A788;
  Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::__PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010530  mov     [rsp+arg_0], rbx
0x180010535  push    rdi
0x180010536  sub     rsp, 20h
0x18001053a  lea     rax, off_18001A788
0x180010541  mov     ebx, edx
0x180010543  mov     [rcx], rax
0x180010546  mov     rdi, rcx
0x180010549  call    Concurrency__details___PPLTaskHandle_unsigned_char_Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency__details___TypeSelectorNoAsync__Concurrency__details___TaskProcHandle_____PPLTaskHandle_unsigned_char_Concurrency__task_unsigned_char____InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency__details___TypeSelectorNoAsync__Concurrency__details___TaskProcHandle_
0x18001054e  test    bl, 1
0x180010551  jz      short loc_180010560
0x180010553  mov     edx, 20h ; ' '; unsigned __int64
0x180010558  mov     rcx, rdi; void *
0x18001055b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010560  mov     rbx, [rsp+28h+arg_0]
0x180010565  mov     rax, rdi
0x180010568  add     rsp, 20h
0x18001056c  pop     rdi
0x18001056d  retn
```
