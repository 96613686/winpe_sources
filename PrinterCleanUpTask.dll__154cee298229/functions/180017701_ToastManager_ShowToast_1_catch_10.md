# _ToastManager::ShowToast_::_1_::catch$10

- ea: `0x180017701`
- end: `0x180017737`
- name: `_ToastManager::ShowToast_::_1_::catch$10`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180017712`: `printscan\print\shared\printercleanuptask\lib\toastmanager.cpp`

## pseudocode

```c
__int64 __fastcall ToastManager::ShowToast_::_1_::catch_10(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 88) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x1B,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\toastmanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017701  mov     [rsp+arg_8], rdx
0x180017706  push    rbp
0x180017707  sub     rsp, 20h
0x18001770b  mov     rbp, rdx
0x18001770e  mov     rcx, [rbp+48h]; this
0x180017712  lea     r8, aPrintscanPrint; "printscan\\print\\shared\\printercleanu"...
0x180017719  mov     edx, 1Bh; void *
0x18001771e  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017723  mov     [rbp+58h], eax
0x180017726  mov     rax, 0
0x180017730  add     rsp, 20h
0x180017734  pop     rbp
0x180017735  retn
```
