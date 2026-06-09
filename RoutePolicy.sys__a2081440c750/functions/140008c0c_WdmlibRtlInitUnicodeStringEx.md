# WdmlibRtlInitUnicodeStringEx

- ea: `0x140008c0c`
- end: `0x140008c52`
- name: `WdmlibRtlInitUnicodeStringEx`
- size: `70`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING DestinationString, PCWSTR SourceString)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140017fdc`
- `0x1400181c4`
- `0x140018330`
- `0x1400185ac`
- `0x140018680`
- `0x1400189bc`
- `0x140018a64`

## callees

- `0x140008c0c`

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
0x140008c0c  xor     r9d, r9d
0x140008c0f  test    rdx, rdx
0x140008c12  jz      short loc_140008C3A
0x140008c14  or      rax, 0FFFFFFFFFFFFFFFFh
0x140008c18  inc     rax
0x140008c1b  cmp     [rdx+rax*2], r9w
0x140008c20  jnz     short loc_140008C18
0x140008c22  cmp     rax, 7FFEh
0x140008c28  jbe     short loc_140008C31
0x140008c2a  mov     eax, 0C0000106h
0x140008c2f  retn
0x140008c31  add     ax, ax
0x140008c34  lea     r8d, [rax+2]
0x140008c38  jmp     short loc_140008C43
0x140008c3a  mov     rdx, r9
0x140008c3d  mov     r8d, r9d
0x140008c40  mov     eax, r9d
0x140008c43  mov     [rcx], ax
0x140008c46  xor     eax, eax
0x140008c48  mov     [rcx+2], r8w
0x140008c4d  mov     [rcx+8], rdx
0x140008c51  retn
```
