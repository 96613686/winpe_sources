# WdmlibRtlInitUnicodeStringEx

- ea: `0x1400022c0`
- end: `0x140002306`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e03c`
- `0x14000e224`
- `0x14000e390`
- `0x14000e6b8`
- `0x14000e718`
- `0x14000ea54`
- `0x14000eafc`

## callees

- `0x1400022c0`

## pseudocode

```c
NTSTATUS __stdcall WdmlibRtlInitUnicodeStringEx(PUNICODE_STRING DestinationString, PCWSTR SourceString)
{
  unsigned __int64 v2; // rax
  NTSTATUS result; // eax
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // r8

  if ( SourceString )
  {
    v2 = -1;
    do
      ++v2;
    while ( SourceString[v2] );
    if ( v2 > 0x7FFE )
      return -1073741562;
    v4 = 2 * v2;
    v5 = v4 + 2;
  }
  else
  {
    SourceString = 0;
    v5 = 0;
    v4 = 0;
  }
  DestinationString->Length = v4;
  result = 0;
  DestinationString->MaximumLength = v5;
  DestinationString->Buffer = (wchar_t *)SourceString;
  return result;
}

```

## disassembly

```asm
0x1400022c0  xor     r9d, r9d
0x1400022c3  test    rdx, rdx
0x1400022c6  jz      short loc_1400022EE
0x1400022c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400022cc  inc     rax
0x1400022cf  cmp     [rdx+rax*2], r9w
0x1400022d4  jnz     short loc_1400022CC
0x1400022d6  cmp     rax, 7FFEh
0x1400022dc  jbe     short loc_1400022E5
0x1400022de  mov     eax, 0C0000106h
0x1400022e3  retn
0x1400022e5  add     ax, ax
0x1400022e8  lea     r8d, [rax+2]
0x1400022ec  jmp     short loc_1400022F7
0x1400022ee  mov     rdx, r9
0x1400022f1  mov     r8d, r9d
0x1400022f4  mov     eax, r9d
0x1400022f7  mov     [rcx], ax
0x1400022fa  xor     eax, eax
0x1400022fc  mov     [rcx+2], r8w
0x140002301  mov     [rcx+8], rdx
0x140002305  retn
```
