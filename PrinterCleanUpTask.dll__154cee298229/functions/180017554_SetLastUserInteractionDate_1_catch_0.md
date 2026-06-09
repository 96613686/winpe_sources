# __SetLastUserInteractionDate_::_1_::catch$0

- ea: `0x180017554`
- end: `0x18001758a`
- name: `__SetLastUserInteractionDate_::_1_::catch$0`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800065c4`

## string_xrefs

- `0x180017565`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall _SetLastUserInteractionDate_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0x84,
                           (int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180017554  mov     [rsp+arg_8], rdx
0x180017559  push    rbp
0x18001755a  sub     rsp, 20h
0x18001755e  mov     rbp, rdx
0x180017561  mov     rcx, [rbp+68h]; this
0x180017565  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x18001756c  mov     edx, 84h; void *
0x180017571  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180017576  mov     [rbp+20h], eax
0x180017579  mov     rax, 0
0x180017583  add     rsp, 20h
0x180017587  pop     rbp
0x180017588  retn
```
