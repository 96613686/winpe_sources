# LexicalAnalyzer::IsNodeTypeString(ushort const *,ulong)

- ea: `0x18000e080`
- end: `0x18000e0f5`
- name: `?IsNodeTypeString@LexicalAnalyzer@@SA_NPEBGK@Z`
- size: `117`
- prototype: `bool __fastcall(wchar_t *String1, size_t MaxCount)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e26c`

## callees

- `0x18000e080`
- `0x180011816`

## string_xrefs

- `0x18000e08f`: `comment`

## pseudocode

```c
bool __fastcall LexicalAnalyzer::IsNodeTypeString(wchar_t *String1, size_t MaxCount)
{
  unsigned int v2; // ebx

  v2 = MaxCount;
  return !wcsncmp_0(String1, L"comment", (unsigned int)MaxCount)
      || !wcsncmp_0(String1, L"text", v2)
      || !wcsncmp_0(String1, L"processing-instruction", v2)
      || !wcsncmp_0(String1, L"node", v2);
}

```

## disassembly

```asm
0x18000e080  mov     [rsp+arg_0], rbx
0x18000e085  push    rdi
0x18000e086  sub     rsp, 20h
0x18000e08a  mov     ebx, edx
0x18000e08c  mov     r8d, edx; MaxCount
0x18000e08f  lea     rdx, aComment; "comment"
0x18000e096  mov     rdi, rcx
0x18000e099  call    wcsncmp_0
0x18000e09e  test    eax, eax
0x18000e0a0  jz      short loc_18000E0E8
0x18000e0a2  mov     r8d, ebx; MaxCount
0x18000e0a5  lea     rdx, aText; "text"
0x18000e0ac  mov     rcx, rdi; String1
0x18000e0af  call    wcsncmp_0
0x18000e0b4  test    eax, eax
0x18000e0b6  jz      short loc_18000E0E8
0x18000e0b8  mov     r8d, ebx; MaxCount
0x18000e0bb  lea     rdx, aProcessingInst; "processing-instruction"
0x18000e0c2  mov     rcx, rdi; String1
0x18000e0c5  call    wcsncmp_0
0x18000e0ca  test    eax, eax
0x18000e0cc  jz      short loc_18000E0E8
0x18000e0ce  mov     r8d, ebx; MaxCount
0x18000e0d1  lea     rdx, aNode; "node"
0x18000e0d8  mov     rcx, rdi; String1
0x18000e0db  call    wcsncmp_0
0x18000e0e0  test    eax, eax
0x18000e0e2  jz      short loc_18000E0E8
0x18000e0e4  xor     al, al
0x18000e0e6  jmp     short loc_18000E0EA
0x18000e0e8  mov     al, 1
0x18000e0ea  mov     rbx, [rsp+28h+arg_0]
0x18000e0ef  add     rsp, 20h
0x18000e0f3  pop     rdi
0x18000e0f4  retn
```
