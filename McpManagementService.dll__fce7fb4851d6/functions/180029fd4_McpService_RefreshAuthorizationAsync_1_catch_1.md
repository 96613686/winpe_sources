# _McpService::RefreshAuthorizationAsync_::_1_::catch$1

- ea: `0x180029fd4`
- end: `0x18002a00a`
- name: `_McpService::RefreshAuthorizationAsync_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callees

- `0x18001b08c`

## string_xrefs

- `0x180029fe5`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::RefreshAuthorizationAsync_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0xE0,
                           (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180029fd4  mov     [rsp+arg_8], rdx
0x180029fd9  push    rbp
0x180029fda  sub     rsp, 20h
0x180029fde  mov     rbp, rdx
0x180029fe1  mov     rcx, [rbp+38h]; this
0x180029fe5  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180029fec  mov     edx, 0E0h; void *
0x180029ff1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180029ff6  mov     [rbp+50h], eax
0x180029ff9  mov     rax, 0
0x18002a003  add     rsp, 20h
0x18002a007  pop     rbp
0x18002a008  retn
```
