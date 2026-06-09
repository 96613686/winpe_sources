# CdsToInputTaskHandler::Pause(void)

- ea: `0x180028150`
- end: `0x18002817a`
- name: `?Pause@CdsToInputTaskHandler@@UEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(CdsToInputTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180006b14`

## string_xrefs

- `0x180028159`: `onecoreuap\windows\input\cloudstore\lib\cdstoinputtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall CdsToInputTaskHandler::Pause(CdsToInputTaskHandler *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F4,
    (unsigned int)"onecoreuap\\windows\\input\\cloudstore\\lib\\cdstoinputtaskhandler.cpp",
    (const char *)0x80004001LL,
    v2);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180028150  sub     rsp, 28h
0x180028154  mov     rcx, [rsp+28h]; this
0x180028159  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\input\\cloudstore"...
0x180028160  mov     r9d, 80004001h; char *
0x180028166  mov     edx, 1F4h; void *
0x18002816b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028170  mov     eax, 80004001h
0x180028175  add     rsp, 28h
0x180028179  retn
```
