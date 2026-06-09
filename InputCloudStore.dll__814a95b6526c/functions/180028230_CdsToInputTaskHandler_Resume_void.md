# CdsToInputTaskHandler::Resume(void)

- ea: `0x180028230`
- end: `0x18002825a`
- name: `?Resume@CdsToInputTaskHandler@@UEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(CdsToInputTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180006b14`

## string_xrefs

- `0x180028239`: `onecoreuap\windows\input\cloudstore\lib\cdstoinputtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall CdsToInputTaskHandler::Resume(CdsToInputTaskHandler *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F9,
    (unsigned int)"onecoreuap\\windows\\input\\cloudstore\\lib\\cdstoinputtaskhandler.cpp",
    (const char *)0x80004001LL,
    v2);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180028230  sub     rsp, 28h
0x180028234  mov     rcx, [rsp+28h]; this
0x180028239  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\input\\cloudstore"...
0x180028240  mov     r9d, 80004001h; char *
0x180028246  mov     edx, 1F9h; void *
0x18002824b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028250  mov     eax, 80004001h
0x180028255  add     rsp, 28h
0x180028259  retn
```
