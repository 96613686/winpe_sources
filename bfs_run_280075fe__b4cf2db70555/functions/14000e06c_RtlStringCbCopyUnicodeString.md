# RtlStringCbCopyUnicodeString

- ea: `0x14000e06c`
- end: `0x14000e105`
- name: `RtlStringCbCopyUnicodeString`
- size: `153`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dadc`

## callees

- `0x14000e06c`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyUnicodeString(NTSTRSAFE_PWSTR pszDest, size_t cbDest, PCUNICODE_STRING SourceString)
{
  size_t v3; // rdx
  unsigned __int64 Length; // rcx
  USHORT MaximumLength; // ax
  wchar_t *Buffer; // r10
  unsigned __int64 v8; // r8
  NTSTRSAFE_PWSTR v9; // rcx

  v3 = cbDest >> 1;
  if ( v3 - 1 > 0x7FFE )
    return -1073741811;
  Length = SourceString->Length;
  if ( (Length & 1) != 0
    || (MaximumLength = SourceString->MaximumLength, (MaximumLength & 1) != 0)
    || (unsigned __int16)Length > MaximumLength
    || MaximumLength == 0xFFFF
    || (Buffer = SourceString->Buffer) == 0 && ((_WORD)Length || MaximumLength) )
  {
    *pszDest = 0;
    return -1073741811;
  }
  v8 = Length >> 1;
  do
  {
    if ( !v8 )
      break;
    --v8;
    *pszDest++ = *Buffer++;
    --v3;
  }
  while ( v3 );
  v9 = pszDest - 1;
  if ( v3 )
    v9 = pszDest;
  *v9 = 0;
  return v3 == 0 ? 0x80000005 : 0;
}

```

## disassembly

```asm
0x14000e06c  shr     rdx, 1
0x14000e06f  mov     r9, rcx
0x14000e072  lea     rax, [rdx-1]
0x14000e076  cmp     rax, 7FFEh
0x14000e07c  ja      short loc_14000E0FD
0x14000e07e  movzx   ecx, word ptr [r8]
0x14000e082  xor     r11d, r11d
0x14000e085  test    cl, 1
0x14000e088  jnz     short loc_14000E0F9
0x14000e08a  movzx   eax, word ptr [r8+2]
0x14000e08f  test    al, 1
0x14000e091  jnz     short loc_14000E0F9
0x14000e093  cmp     cx, ax
0x14000e096  ja      short loc_14000E0F9
0x14000e098  mov     r10d, 0FFFEh
0x14000e09e  cmp     ax, r10w
0x14000e0a2  ja      short loc_14000E0F9
0x14000e0a4  mov     r10, [r8+8]
0x14000e0a8  test    r10, r10
0x14000e0ab  jnz     short loc_14000E0B7
0x14000e0ad  test    cx, cx
0x14000e0b0  jnz     short loc_14000E0F9
0x14000e0b2  test    ax, ax
0x14000e0b5  jnz     short loc_14000E0F9
0x14000e0b7  mov     r8, rcx
0x14000e0ba  shr     r8, 1
0x14000e0bd  test    r8, r8
0x14000e0c0  jz      short loc_14000E0DB
0x14000e0c2  movzx   eax, word ptr [r10]
0x14000e0c6  dec     r8
0x14000e0c9  mov     [r9], ax
0x14000e0cd  add     r10, 2
0x14000e0d1  add     r9, 2
0x14000e0d5  sub     rdx, 1
0x14000e0d9  jnz     short loc_14000E0BD
0x14000e0db  test    rdx, rdx
0x14000e0de  lea     rcx, [r9-2]
0x14000e0e2  cmovnz  rcx, r9
0x14000e0e6  neg     rdx
0x14000e0e9  mov     [rcx], r11w
0x14000e0ed  sbb     ecx, ecx
0x14000e0ef  not     ecx
0x14000e0f1  and     ecx, 80000005h
0x14000e0f7  jmp     short loc_14000E102
0x14000e0f9  mov     [r9], r11w
0x14000e0fd  mov     ecx, 0C000000Dh
0x14000e102  mov     eax, ecx
0x14000e104  retn
```
