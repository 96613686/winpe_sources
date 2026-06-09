# GetFileExtensionFromContentType

- ea: `0x1800083e0`
- end: `0x180008404`
- name: `GetFileExtensionFromContentType`
- size: `36`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800080d0`
- `0x1800083e0`

## pseudocode

```c
__int64 __fastcall GetFileExtensionFromContentType(__int64 a1, _QWORD *a2)
{
  int FileExtensionFromContentTypeThroughPacMan; // eax
  unsigned int v4; // ecx

  if ( *a2 )
    return 2147942487LL;
  FileExtensionFromContentTypeThroughPacMan = GetFileExtensionFromContentTypeThroughPacMan();
  v4 = 0;
  if ( FileExtensionFromContentTypeThroughPacMan < 0 )
    return (unsigned int)FileExtensionFromContentTypeThroughPacMan;
  return v4;
}

```

## disassembly

```asm
0x1800083e0  sub     rsp, 28h
0x1800083e4  cmp     qword ptr [rdx], 0
0x1800083e8  jz      short loc_1800083F1
0x1800083ea  mov     eax, 80070057h
0x1800083ef  jmp     short loc_1800083FF
0x1800083f1  call    GetFileExtensionFromContentTypeThroughPacMan
0x1800083f6  xor     ecx, ecx
0x1800083f8  test    eax, eax
0x1800083fa  cmovs   ecx, eax
0x1800083fd  mov     eax, ecx
0x1800083ff  add     rsp, 28h
0x180008403  retn
```
