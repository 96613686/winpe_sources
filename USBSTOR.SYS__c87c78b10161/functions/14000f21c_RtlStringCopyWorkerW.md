# RtlStringCopyWorkerW

- ea: `0x14000f21c`
- end: `0x14000f276`
- name: `RtlStringCopyWorkerW`
- size: `90`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cchDest, size_t *pcchNewDestLength, STRSAFE_PCNZWCH pszSrc, size_t cchToCopy)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f5c0`

## callees

- `0x14000f21c`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCopyWorkerW(
        NTSTRSAFE_PWSTR pszDest,
        size_t cchDest,
        size_t *pcchNewDestLength,
        STRSAFE_PCNZWCH pszSrc,
        size_t cchToCopy)
{
  const wchar_t *v6; // rdx
  __int64 i; // rax
  NTSTRSAFE_PWSTR v8; // rdx
  NTSTATUS result; // eax

  v6 = L"\\Parameters";
  for ( i = 2147483646; cchDest; --cchDest )
  {
    if ( !i )
      break;
    if ( !*v6 )
      break;
    *pszDest++ = *v6++;
    --i;
  }
  v8 = pszDest - 1;
  result = cchDest == 0 ? 0x80000005 : 0;
  if ( cchDest )
    v8 = pszDest;
  *v8 = 0;
  return result;
}

```

## disassembly

```asm
0x14000f21c  mov     r8, rdx
0x14000f21f  xor     r10d, r10d
0x14000f222  lea     rdx, aParameters; "\\Parameters"
0x14000f229  mov     eax, 7FFFFFFEh
0x14000f22e  test    r8, r8
0x14000f231  jz      short loc_14000F257
0x14000f233  test    rax, rax
0x14000f236  jz      short loc_14000F257
0x14000f238  movzx   r9d, word ptr [rdx]
0x14000f23c  test    r9w, r9w
0x14000f240  jz      short loc_14000F257
0x14000f242  mov     [rcx], r9w
0x14000f246  add     rdx, 2
0x14000f24a  add     rcx, 2
0x14000f24e  dec     rax
0x14000f251  sub     r8, 1
0x14000f255  jnz     short loc_14000F233
0x14000f257  mov     rax, r8
0x14000f25a  lea     rdx, [rcx-2]
0x14000f25e  neg     rax
0x14000f261  sbb     eax, eax
0x14000f263  not     eax
0x14000f265  and     eax, 80000005h
0x14000f26a  test    r8, r8
0x14000f26d  cmovnz  rdx, rcx
0x14000f271  mov     [rdx], r10w
0x14000f275  retn
```
