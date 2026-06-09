# McpGetCloudPrintServiceResult::GetOperationResult(long *)

- ea: `0x180023b30`
- end: `0x180023b6f`
- name: `?GetOperationResult@McpGetCloudPrintServiceResult@@UEAAJPEAJ@Z`
- size: `63`
- prototype: `__int64 __fastcall(McpGetCloudPrintServiceResult *__hidden this, int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000c4cc`
- `0x180023b30`

## string_xrefs

- `0x180023b44`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpgetcloudprintserviceresult.cpp`

## pseudocode

```c
__int64 __fastcall McpGetCloudPrintServiceResult::GetOperationResult(McpGetCloudPrintServiceResult *this, int *a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    *a2 = *((_DWORD *)this + 6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpgetcloudprintserviceresult.cpp",
      (const char *)0x80004003LL,
      v3);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180023b30  sub     rsp, 28h
0x180023b34  test    rdx, rdx
0x180023b37  jnz     short loc_180023B5C
0x180023b39  mov     rcx, [rsp+28h]; this
0x180023b3e  mov     r9d, 80004003h; char *
0x180023b44  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180023b4b  mov     edx, 18h; void *
0x180023b50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b55  mov     eax, 80004003h
0x180023b5a  jmp     short loc_180023B69
0x180023b5c  mov     eax, [rcx+18h]
0x180023b5f  mov     [rdx], eax
0x180023b61  xor     eax, eax
0x180023b63  jmp     short loc_180023B69
0x180023b65  mov     eax, [rsp+28h+arg_8]
0x180023b69  add     rsp, 28h
0x180023b6d  retn
```
