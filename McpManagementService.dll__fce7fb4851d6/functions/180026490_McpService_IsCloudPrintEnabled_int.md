# McpService::IsCloudPrintEnabled(int *)

- ea: `0x180026490`
- end: `0x1800264dd`
- name: `?IsCloudPrintEnabled@McpService@@UEAAJPEAH@Z`
- size: `77`
- prototype: `int(McpService *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000c4cc`
- `0x180018e60`
- `0x180026490`

## string_xrefs

- `0x1800264ab`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::IsCloudPrintEnabled(CloudPrint::CloudPrintHelper **this, int *a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    *a2 = CloudPrint::CloudPrintHelper::IsCloudPrintEnabled(this[3]);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)0x80004003LL,
      v3);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180026490  push    rbx; int
0x180026492  sub     rsp, 20h
0x180026496  mov     rbx, rdx
0x180026499  test    rdx, rdx
0x18002649c  jnz     short loc_1800264C0
0x18002649e  mov     rcx, [rsp+28h]; this
0x1800264a3  mov     ebx, 80004003h
0x1800264a8  mov     r9d, ebx; char *
0x1800264ab  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x1800264b2  mov     edx, 24h ; '$'; void *
0x1800264b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800264bc  mov     eax, ebx
0x1800264be  jmp     short loc_1800264D6
0x1800264c0  mov     rcx, [rcx+18h]; this
0x1800264c4  call    ?IsCloudPrintEnabled@CloudPrintHelper@CloudPrint@@QEBA_NXZ; CloudPrint::CloudPrintHelper::IsCloudPrintEnabled(void)
0x1800264c9  movzx   eax, al
0x1800264cc  mov     [rbx], eax
0x1800264ce  xor     eax, eax
0x1800264d0  jmp     short loc_1800264D6
0x1800264d2  mov     eax, [rsp+28h+arg_8]
0x1800264d6  add     rsp, 20h
0x1800264da  pop     rbx
0x1800264db  retn
```
