# RtlStringCbCopyUnicodeString

- ea: `0x14000e200`
- end: `0x14000e299`
- name: `RtlStringCbCopyUnicodeString`
- size: `153`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dc70`

## callees

- `0x14000e200`

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
0x14000e200  shr     rdx, 1
0x14000e203  mov     r9, rcx
0x14000e206  lea     rax, [rdx-1]
0x14000e20a  cmp     rax, 7FFEh
0x14000e210  ja      short loc_14000E291
0x14000e212  movzx   ecx, word ptr [r8]
0x14000e216  xor     r11d, r11d
0x14000e219  test    cl, 1
0x14000e21c  jnz     short loc_14000E28D
0x14000e21e  movzx   eax, word ptr [r8+2]
0x14000e223  test    al, 1
0x14000e225  jnz     short loc_14000E28D
0x14000e227  cmp     cx, ax
0x14000e22a  ja      short loc_14000E28D
0x14000e22c  mov     r10d, 0FFFEh
0x14000e232  cmp     ax, r10w
0x14000e236  ja      short loc_14000E28D
0x14000e238  mov     r10, [r8+8]
0x14000e23c  test    r10, r10
0x14000e23f  jnz     short loc_14000E24B
0x14000e241  test    cx, cx
0x14000e244  jnz     short loc_14000E28D
0x14000e246  test    ax, ax
0x14000e249  jnz     short loc_14000E28D
0x14000e24b  mov     r8, rcx
0x14000e24e  shr     r8, 1
0x14000e251  test    r8, r8
0x14000e254  jz      short loc_14000E26F
0x14000e256  movzx   eax, word ptr [r10]
0x14000e25a  dec     r8
0x14000e25d  mov     [r9], ax
0x14000e261  add     r10, 2
0x14000e265  add     r9, 2
0x14000e269  sub     rdx, 1
0x14000e26d  jnz     short loc_14000E251
0x14000e26f  test    rdx, rdx
0x14000e272  lea     rcx, [r9-2]
0x14000e276  cmovnz  rcx, r9
0x14000e27a  neg     rdx
0x14000e27d  mov     [rcx], r11w
0x14000e281  sbb     ecx, ecx
0x14000e283  not     ecx
0x14000e285  and     ecx, 80000005h
0x14000e28b  jmp     short loc_14000E296
0x14000e28d  mov     [r9], r11w
0x14000e291  mov     ecx, 0C000000Dh
0x14000e296  mov     eax, ecx
0x14000e298  retn
```
