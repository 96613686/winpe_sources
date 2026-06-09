# _McpGetCloudPrintServiceOperation::RuntimeClassInitialize_::_1_::catch$10

- ea: `0x180029703`
- end: `0x18002973f`
- name: `_McpGetCloudPrintServiceOperation::RuntimeClassInitialize_::_1_::catch$10`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029717`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceoperation.cpp`

## pseudocode

```c
__int64 __fastcall McpGetCloudPrintServiceOperation::RuntimeClassInitialize_::_1_::catch_10(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 184) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 168),
                            (void *)0x4D,
                            (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceoperation.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x180029703  mov     [rsp+arg_8], rdx
0x180029708  push    rbp
0x180029709  sub     rsp, 30h
0x18002970d  mov     rbp, rdx
0x180029710  mov     rcx, [rbp+0A8h]; this
0x180029717  lea     r8, aOnecoreuapPrin_6; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x18002971e  mov     edx, 4Dh ; 'M'; void *
0x180029723  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029728  mov     [rbp+0B8h], eax
0x18002972e  mov     rax, 0
0x180029738  add     rsp, 30h
0x18002973c  pop     rbp
0x18002973d  retn
```
