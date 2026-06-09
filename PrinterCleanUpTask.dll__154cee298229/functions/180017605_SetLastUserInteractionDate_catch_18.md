# SetLastUserInteractionDate$catch$18

- ea: `0x180017605`
- end: `0x18001763e`
- name: `SetLastUserInteractionDate$catch$18`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180017619`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall SetLastUserInteractionDate_catch_18(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 200),
                           (void *)0x150,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017605  mov     [rsp+arg_8], rdx
0x18001760a  push    rbp
0x18001760b  sub     rsp, 40h
0x18001760f  mov     rbp, rdx
0x180017612  mov     rcx, [rbp+0C8h]; this
0x180017619  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180017620  mov     edx, 150h; void *
0x180017625  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001762a  mov     [rbp+40h], eax
0x18001762d  mov     rax, 0
0x180017637  add     rsp, 40h
0x18001763b  pop     rbp
0x18001763c  retn
```
