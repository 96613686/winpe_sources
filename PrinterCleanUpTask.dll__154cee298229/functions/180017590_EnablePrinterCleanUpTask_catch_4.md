# EnablePrinterCleanUpTask$catch$4

- ea: `0x180017590`
- end: `0x1800175c9`
- name: `EnablePrinterCleanUpTask$catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x1800175a4`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall EnablePrinterCleanUpTask_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x162,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017590  mov     [rsp+arg_8], rdx
0x180017595  push    rbp
0x180017596  sub     rsp, 30h
0x18001759a  mov     rbp, rdx
0x18001759d  mov     rcx, [rbp+0F8h]; this
0x1800175a4  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x1800175ab  mov     edx, 162h; void *
0x1800175b0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800175b5  mov     [rbp+30h], eax
0x1800175b8  mov     rax, 0
0x1800175c2  add     rsp, 30h
0x1800175c6  pop     rbp
0x1800175c7  retn
```
