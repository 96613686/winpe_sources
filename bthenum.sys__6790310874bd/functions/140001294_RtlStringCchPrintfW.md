# RtlStringCchPrintfW

- ea: `0x140001294`
- end: `0x14000131f`
- name: `RtlStringCchPrintfW`
- size: `139`
- prototype: `NTSTATUS(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszFormat, ...)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1400031b8`
- `0x14001812c`
- `0x140018234`
- `0x14001833c`
- `0x14001849c`
- `0x140018a54`
- `0x140018b90`
- `0x140018d54`
- `0x14001bb54`
- `0x14001bc4c`
- `0x14001f300`

## callees

- `0x140001294`

## import_xrefs

- `ntoskrnl!_vsnwprintf` at `0x1400012d3`
- `ntoskrnl!_vsnwprintf` at `0x1400012d3`

## pseudocode

```c
NTSTATUS RtlStringCchPrintfW(NTSTRSAFE_PWSTR pszDest, size_t cchDest, NTSTRSAFE_PCWSTR pszFormat, ...)
{
  NTSTATUS v4; // edx
  size_t v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cchDest )
    return -1073741811;
  if ( cchDest <= 0x7FFFFFFF )
  {
    v5 = cchDest - 1;
    v6 = _vsnwprintf(pszDest, cchDest - 1, pszFormat, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      v4 = -2147483643;
      pszDest[v5] = 0;
    }
    else
    {
      v4 = 0;
      if ( v6 == v5 )
        pszDest[v5] = 0;
    }
  }
  else
  {
    v4 = -1073741811;
    *pszDest = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x140001294  mov     [rsp+arg_10], r8
0x140001299  mov     qword ptr [rsp+Args], r9
0x14000129e  push    rbx
0x14000129f  push    rdi
0x1400012a0  sub     rsp, 38h
0x1400012a4  mov     rax, rdx
0x1400012a7  mov     rdi, rcx
0x1400012aa  test    rdx, rdx
0x1400012ad  jz      short loc_140001306
0x1400012af  cmp     rax, 7FFFFFFFh
0x1400012b5  jbe     short loc_1400012BE
0x1400012b7  mov     edx, 0C000000Dh
0x1400012bc  jmp     short loc_140001310
0x1400012be  lea     rbx, [rdx-1]
0x1400012c2  mov     [rsp+48h+var_28], 0
0x1400012cb  mov     rdx, rbx; Count
0x1400012ce  lea     r9, [rsp+48h+Args]; Args
0x1400012d3  call    cs:__imp__vsnwprintf
0x1400012da  nop     dword ptr [rax+rax+00h]
0x1400012df  test    eax, eax
0x1400012e1  js      short loc_1400012F9
0x1400012e3  cdqe
0x1400012e5  cmp     rax, rbx
0x1400012e8  ja      short loc_1400012F9
0x1400012ea  xor     edx, edx
0x1400012ec  cmp     rax, rbx
0x1400012ef  jnz     short loc_140001315
0x1400012f1  xor     eax, eax
0x1400012f3  mov     [rdi+rbx*2], ax
0x1400012f7  jmp     short loc_140001315
0x1400012f9  xor     eax, eax
0x1400012fb  mov     edx, 80000005h
0x140001300  mov     [rdi+rbx*2], ax
0x140001304  jmp     short loc_140001315
0x140001306  mov     edx, 0C000000Dh
0x14000130b  test    rax, rax
0x14000130e  jz      short loc_140001315
0x140001310  xor     ecx, ecx
0x140001312  mov     [rdi], cx
0x140001315  mov     eax, edx
0x140001317  add     rsp, 38h
0x14000131b  pop     rdi
0x14000131c  pop     rbx
0x14000131d  retn
```
