# TlmiRemoveCommandLineArgs

- ea: `0x180019dc0`
- end: `0x180019e6a`
- name: `TlmiRemoveCommandLineArgs`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017728`

## callees

- `0x180019dc0`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x180019e10`
- `ntdll!RtlPrefixUnicodeString` at `0x180019e10`

## pseudocode

```c
char __fastcall TlmiRemoveCommandLineArgs(__m128i *a1)
{
  WCHAR *v1; // rax
  int v3; // edi
  USHORT v4; // ax
  PWSTR Buffer; // rcx
  USHORT MaximumLength; // dx
  UNICODE_STRING String2; // [rsp+20h] [rbp-10h] BYREF

  v1 = (WCHAR *)(a1->m128i_i64[1] + 2);
  *(_QWORD *)&String2.Length = a1->m128i_i64[0];
  String2.Length -= 2;
  String2.MaximumLength -= 2;
  String2.Buffer = v1;
  v3 = 0;
  while ( 1 )
  {
    LOBYTE(v4) = RtlPrefixUnicodeString((PCUNICODE_STRING)&asc_180028710[8 * v3], &String2, 1u);
    if ( (_BYTE)v4 )
      break;
    if ( (unsigned int)++v3 >= 2 )
    {
      v4 = _mm_cvtsi128_si32(*a1);
      String2 = (UNICODE_STRING)*a1;
      if ( v4 )
      {
        Buffer = String2.Buffer;
        MaximumLength = String2.MaximumLength;
        do
        {
          if ( *Buffer == 32 )
            break;
          ++Buffer;
          v4 -= 2;
          MaximumLength -= 2;
          String2.Buffer = Buffer;
          String2.Length = v4;
          String2.MaximumLength = MaximumLength;
        }
        while ( v4 );
      }
      a1->m128i_i16[0] -= v4;
      return v4;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180019dc0  push    rbp
0x180019dc2  push    rbx
0x180019dc3  push    rsi
0x180019dc4  push    rdi
0x180019dc5  push    r14
0x180019dc7  mov     rbp, rsp
0x180019dca  sub     rsp, 30h
0x180019dce  movups  xmm0, xmmword ptr [rcx]
0x180019dd1  mov     rax, [rcx+8]
0x180019dd5  mov     r14d, 0FFFEh
0x180019ddb  add     rax, 2
0x180019ddf  mov     rbx, rcx
0x180019de2  movups  xmmword ptr [rbp+String2.Length], xmm0
0x180019de6  add     [rbp+String2.Length], r14w
0x180019deb  add     [rbp+String2.MaximumLength], r14w
0x180019df0  xor     esi, esi
0x180019df2  mov     [rbp+String2.Buffer], rax
0x180019df6  mov     edi, esi
0x180019df8  lea     rax, asc_180028710; "<>"
0x180019dff  movsxd  rcx, edi
0x180019e02  shl     rcx, 4
0x180019e06  lea     rdx, [rbp+String2]; String2
0x180019e0a  add     rcx, rax; String1
0x180019e0d  mov     r8b, 1; CaseInsensitive
0x180019e10  call    cs:__imp_RtlPrefixUnicodeString
0x180019e16  test    al, al
0x180019e18  jnz     short loc_180019E5F
0x180019e1a  inc     edi
0x180019e1c  cmp     edi, 2
0x180019e1f  jb      short loc_180019DF8
0x180019e21  movups  xmm0, xmmword ptr [rbx]
0x180019e24  movd    eax, xmm0
0x180019e28  movups  xmmword ptr [rbp+String2.Length], xmm0
0x180019e2c  test    ax, ax
0x180019e2f  jz      short loc_180019E5C
0x180019e31  mov     rcx, [rbp+String2.Buffer]
0x180019e35  movzx   edx, [rbp+String2.MaximumLength]
0x180019e39  cmp     word ptr [rcx], 20h ; ' '
0x180019e3d  jz      short loc_180019E5C
0x180019e3f  add     rcx, 2
0x180019e43  add     ax, r14w
0x180019e47  add     dx, r14w
0x180019e4b  mov     [rbp+String2.Buffer], rcx
0x180019e4f  mov     [rbp+String2.Length], ax
0x180019e53  mov     [rbp+String2.MaximumLength], dx
0x180019e57  test    ax, ax
0x180019e5a  jnz     short loc_180019E39
0x180019e5c  sub     [rbx], ax
0x180019e5f  add     rsp, 30h
0x180019e63  pop     r14
0x180019e65  pop     rdi
0x180019e66  pop     rsi
0x180019e67  pop     rbx
0x180019e68  pop     rbp
0x180019e69  retn
```
