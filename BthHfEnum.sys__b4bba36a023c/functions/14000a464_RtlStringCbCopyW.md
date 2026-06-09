# RtlStringCbCopyW

- ea: `0x14000a464`
- end: `0x14000a4d1`
- name: `RtlStringCbCopyW`
- size: `109`
- prototype: `NTSTATUS __stdcall(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007dc0`

## callees

- `0x14000a464`

## pseudocode

```c
NTSTATUS __stdcall RtlStringCbCopyW(NTSTRSAFE_PWSTR pszDest, size_t cbDest, NTSTRSAFE_PCWSTR pszSrc)
{
  size_t v3; // rdx
  NTSTATUS result; // eax
  __int64 v5; // rax
  NTSTRSAFE_PWSTR v6; // rax

  v3 = cbDest >> 1;
  if ( !v3 )
    return -1073741811;
  if ( v3 <= 0x7FFFFFFF )
  {
    v5 = 2147483646;
    do
    {
      if ( !v5 )
        break;
      if ( !*pszSrc )
        break;
      *pszDest++ = *pszSrc++;
      --v5;
      --v3;
    }
    while ( v3 );
    v6 = pszDest - 1;
    if ( v3 )
      v6 = pszDest;
    *v6 = 0;
    return v3 == 0 ? 0x80000005 : 0;
  }
  else
  {
    result = -1073741811;
    *pszDest = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000a464  xor     r9d, r9d
0x14000a467  shr     rdx, 1
0x14000a46a  jz      short loc_14000A4C2
0x14000a46c  cmp     rdx, 7FFFFFFFh
0x14000a473  jbe     short loc_14000A47C
0x14000a475  mov     eax, 0C000000Dh
0x14000a47a  jmp     short loc_14000A4CC
0x14000a47c  mov     eax, 7FFFFFFEh
0x14000a481  test    rax, rax
0x14000a484  jz      short loc_14000A4A5
0x14000a486  movzx   r10d, word ptr [r8]
0x14000a48a  test    r10w, r10w
0x14000a48e  jz      short loc_14000A4A5
0x14000a490  mov     [rcx], r10w
0x14000a494  add     r8, 2
0x14000a498  add     rcx, 2
0x14000a49c  dec     rax
0x14000a49f  sub     rdx, 1
0x14000a4a3  jnz     short loc_14000A481
0x14000a4a5  test    rdx, rdx
0x14000a4a8  lea     rax, [rcx-2]
0x14000a4ac  cmovnz  rax, rcx
0x14000a4b0  neg     rdx
0x14000a4b3  mov     [rax], r9w
0x14000a4b7  sbb     eax, eax
0x14000a4b9  not     eax
0x14000a4bb  and     eax, 80000005h
0x14000a4c0  retn
0x14000a4c2  mov     eax, 0C000000Dh
0x14000a4c7  test    rdx, rdx
0x14000a4ca  jz      short locret_14000A4D0
0x14000a4cc  mov     [rcx], r9w
0x14000a4d0  retn
```
