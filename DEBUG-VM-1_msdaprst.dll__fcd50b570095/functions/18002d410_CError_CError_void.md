# CError::CError(void)

- ea: `0x18002d410`
- end: `0x18002d49e`
- name: `??0CError@@QEAA@XZ`
- size: `142`
- prototype: `CError *__fastcall(CError *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002ce20`
- `0x18002db9c`

## callees

- `0x18002d410`

## string_xrefs

- `0x18002d421`: `resource dll.`

## pseudocode

```c
CError *__fastcall CError::CError(CError *this)
{
  const char *v1; // r9
  __int64 v3; // r8
  __int64 v4; // rax
  char *v5; // rcx
  char *v6; // rax

  *((_DWORD *)this + 1033) = 0;
  v1 = "resource dll.";
  v3 = 261;
  *((GUID *)this + 1) = GUID_NULL;
  *((_QWORD *)this + 552) = &word_1800394C6;
  v4 = 2147483646;
  *(_QWORD *)this = 0;
  *((GUID *)this + 275) = GUID_NULL;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 553) = 0;
  v5 = (char *)this + 4136;
  do
  {
    if ( !v4 )
      break;
    if ( !*v1 )
      break;
    *v5++ = *v1++;
    --v4;
    --v3;
  }
  while ( v3 );
  v6 = v5 - 1;
  if ( v3 )
    v6 = v5;
  *v6 = 0;
  return this;
}

```

## disassembly

```asm
0x18002d410  xor     r11d, r11d
0x18002d413  lea     rax, word_1800394C6
0x18002d41a  mov     [rcx+1024h], r11d
0x18002d421  lea     r9, aResourceDll; "resource dll."
0x18002d428  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002d42f  mov     rdx, rcx
0x18002d432  mov     r8d, 105h
0x18002d438  movdqu  xmmword ptr [rcx+10h], xmm0
0x18002d43d  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18002d444  mov     [rcx+1140h], rax
0x18002d44b  mov     eax, 7FFFFFFEh
0x18002d450  mov     [rcx], r11
0x18002d453  movdqu  xmmword ptr [rcx+1130h], xmm1
0x18002d45b  mov     [rcx+8], r11
0x18002d45f  mov     [rcx+1148h], r11
0x18002d466  add     rcx, 1028h
0x18002d46d  test    rax, rax
0x18002d470  jz      short loc_18002D48C
0x18002d472  mov     r10b, [r9]
0x18002d475  test    r10b, r10b
0x18002d478  jz      short loc_18002D48C
0x18002d47a  mov     [rcx], r10b
0x18002d47d  inc     r9
0x18002d480  inc     rcx
0x18002d483  dec     rax
0x18002d486  sub     r8, 1
0x18002d48a  jnz     short loc_18002D46D
0x18002d48c  test    r8, r8
0x18002d48f  lea     rax, [rcx-1]
0x18002d493  cmovnz  rax, rcx
0x18002d497  mov     [rax], r11b
0x18002d49a  mov     rax, rdx
0x18002d49d  retn
```
