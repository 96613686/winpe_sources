# _McpService::GetMcpServiceType_::_1_::catch$0

- ea: `0x180029ea8`
- end: `0x180029ede`
- name: `_McpService::GetMcpServiceType_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029eb9`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::GetMcpServiceType_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x3F,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029ea8  mov     [rsp+arg_8], rdx
0x180029ead  push    rbp
0x180029eae  sub     rsp, 20h
0x180029eb2  mov     rbp, rdx
0x180029eb5  mov     rcx, [rbp+28h]; this
0x180029eb9  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180029ec0  mov     edx, 3Fh ; '?'; void *
0x180029ec5  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029eca  mov     [rbp+38h], eax
0x180029ecd  mov     rax, 0
0x180029ed7  add     rsp, 20h
0x180029edb  pop     rbp
0x180029edc  retn
```
