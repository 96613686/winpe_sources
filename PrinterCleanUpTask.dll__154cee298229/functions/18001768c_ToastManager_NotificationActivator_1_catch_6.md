# _ToastManager::NotificationActivator_::_1_::catch$6

- ea: `0x18001768c`
- end: `0x1800176c5`
- name: `_ToastManager::NotificationActivator_::_1_::catch$6`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x1800176a0`: `printscan\print\shared\printercleanuptask\lib\toastmanager.cpp`

## pseudocode

```c
__int64 __fastcall ToastManager::NotificationActivator_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0x30,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\toastmanager.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001768c  mov     [rsp+arg_8], rdx
0x180017691  push    rbp
0x180017692  sub     rsp, 30h
0x180017696  mov     rbp, rdx
0x180017699  mov     rcx, [rbp+0A8h]; this
0x1800176a0  lea     r8, aPrintscanPrint; "printscan\\print\\shared\\printercleanu"...
0x1800176a7  mov     edx, 30h ; '0'; void *
0x1800176ac  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800176b1  mov     [rbp+30h], eax
0x1800176b4  mov     rax, 0
0x1800176be  add     rsp, 30h
0x1800176c2  pop     rbp
0x1800176c3  retn
```
