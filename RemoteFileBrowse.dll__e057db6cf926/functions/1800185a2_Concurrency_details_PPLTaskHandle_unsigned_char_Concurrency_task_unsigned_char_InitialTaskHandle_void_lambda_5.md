# _Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$4

- ea: `0x1800185a2`
- end: `0x1800185e6`
- name: `_Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch$4`
- size: `68`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180019010`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_PPLTaskHandle_unsigned_char_Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358__Concurrency::details::_TypeSelectorNoAsync__Concurrency::details::_TaskProcHandle_::invoke_::_1_::catch_4(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx
  __int64 v3; // rdx

  v2 = *(_QWORD *)(*(_QWORD *)(a2 + 96) + 8LL);
  v3 = v2 + 16;
  LOBYTE(v3) = 1;
  (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v2 + 8LL))(v2, v3, 0, 0, v2 + 16);
  return 0;
}

```

## disassembly

```asm
0x1800185a2  mov     [rsp+arg_8], rdx
0x1800185a7  push    rbp
0x1800185a8  sub     rsp, 30h
0x1800185ac  mov     rbp, rdx
0x1800185af  mov     rax, [rbp+60h]
0x1800185b3  mov     rcx, [rax+8]
0x1800185b7  mov     rax, [rcx]
0x1800185ba  lea     rdx, [rcx+10h]
0x1800185be  mov     [rsp+38h+var_18], rdx
0x1800185c3  xor     r9d, r9d
0x1800185c6  xor     r8d, r8d
0x1800185c9  mov     dl, 1
0x1800185cb  mov     rax, [rax+8]
0x1800185cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185d4  nop
0x1800185d5  mov     rax, 0
0x1800185df  add     rsp, 30h
0x1800185e3  pop     rbp
0x1800185e4  retn
```
