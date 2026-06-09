# WdmlibRtlInitUnicodeStringEx

- ea: `0x1400138e0`
- end: `0x140013926`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14002553c`
- `0x140025724`
- `0x140025890`
- `0x140025b0c`
- `0x140025be0`
- `0x140025f1c`
- `0x140025fc4`

## callees

- `0x1400138e0`

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
0x1400138e0  xor     r9d, r9d
0x1400138e3  test    rdx, rdx
0x1400138e6  jz      short loc_14001390E
0x1400138e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400138ec  inc     rax
0x1400138ef  cmp     [rdx+rax*2], r9w
0x1400138f4  jnz     short loc_1400138EC
0x1400138f6  cmp     rax, 7FFEh
0x1400138fc  jbe     short loc_140013905
0x1400138fe  mov     eax, 0C0000106h
0x140013903  retn
0x140013905  add     ax, ax
0x140013908  lea     r8d, [rax+2]
0x14001390c  jmp     short loc_140013917
0x14001390e  mov     rdx, r9
0x140013911  mov     r8d, r9d
0x140013914  mov     eax, r9d
0x140013917  mov     [rcx], ax
0x14001391a  xor     eax, eax
0x14001391c  mov     [rcx+2], r8w
0x140013921  mov     [rcx+8], rdx
0x140013925  retn
```
