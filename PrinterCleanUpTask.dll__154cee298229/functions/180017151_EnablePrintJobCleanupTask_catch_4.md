# EnablePrintJobCleanupTask$catch$4

- ea: `0x180017151`
- end: `0x18001718a`
- name: `EnablePrintJobCleanupTask$catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180017165`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall EnablePrintJobCleanupTask_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x174,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017151  mov     [rsp+arg_8], rdx
0x180017156  push    rbp
0x180017157  sub     rsp, 30h
0x18001715b  mov     rbp, rdx
0x18001715e  mov     rcx, [rbp+0F8h]; this
0x180017165  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18001716c  mov     edx, 174h; void *
0x180017171  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017176  mov     [rbp+30h], eax
0x180017179  mov     rax, 0
0x180017183  add     rsp, 30h
0x180017187  pop     rbp
0x180017188  retn
```
