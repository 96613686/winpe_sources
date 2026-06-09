# WdmlibRtlInitUnicodeStringEx

- ea: `0x18001b8ac`
- end: `0x18001b8f2`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18002bf3c`
- `0x18002c124`
- `0x18002c290`
- `0x18002c50c`
- `0x18002c5e0`
- `0x18002c91c`
- `0x18002c9c4`

## callees

- `0x18001b8ac`

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
0x18001b8ac  xor     r9d, r9d
0x18001b8af  test    rdx, rdx
0x18001b8b2  jz      short loc_18001B8DA
0x18001b8b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b8b8  inc     rax
0x18001b8bb  cmp     [rdx+rax*2], r9w
0x18001b8c0  jnz     short loc_18001B8B8
0x18001b8c2  cmp     rax, 7FFEh
0x18001b8c8  jbe     short loc_18001B8D1
0x18001b8ca  mov     eax, 0C0000106h
0x18001b8cf  retn
0x18001b8d1  add     ax, ax
0x18001b8d4  lea     r8d, [rax+2]
0x18001b8d8  jmp     short loc_18001B8E3
0x18001b8da  mov     rdx, r9
0x18001b8dd  mov     r8d, r9d
0x18001b8e0  mov     eax, r9d
0x18001b8e3  mov     [rcx], ax
0x18001b8e6  xor     eax, eax
0x18001b8e8  mov     [rcx+2], r8w
0x18001b8ed  mov     [rcx+8], rdx
0x18001b8f1  retn
```
