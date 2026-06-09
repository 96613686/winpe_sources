# GetContentTypeFromFilePath

- ea: `0x1800083b0`
- end: `0x1800083d4`
- name: `GetContentTypeFromFilePath`
- size: `36`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007d80`
- `0x1800083b0`

## pseudocode

```c
__int64 __fastcall GetContentTypeFromFilePath(__int64 a1, _QWORD *a2)
{
  int ContentTypeFromFilePathThroughPacMan; // eax
  unsigned int v4; // ecx

  if ( *a2 )
    return 2147942487LL;
  ContentTypeFromFilePathThroughPacMan = GetContentTypeFromFilePathThroughPacMan();
  v4 = 0;
  if ( ContentTypeFromFilePathThroughPacMan < 0 )
    return (unsigned int)ContentTypeFromFilePathThroughPacMan;
  return v4;
}

```

## disassembly

```asm
0x1800083b0  sub     rsp, 28h
0x1800083b4  cmp     qword ptr [rdx], 0
0x1800083b8  jz      short loc_1800083C1
0x1800083ba  mov     eax, 80070057h
0x1800083bf  jmp     short loc_1800083CF
0x1800083c1  call    GetContentTypeFromFilePathThroughPacMan
0x1800083c6  xor     ecx, ecx
0x1800083c8  test    eax, eax
0x1800083ca  cmovs   ecx, eax
0x1800083cd  mov     eax, ecx
0x1800083cf  add     rsp, 28h
0x1800083d3  retn
```
