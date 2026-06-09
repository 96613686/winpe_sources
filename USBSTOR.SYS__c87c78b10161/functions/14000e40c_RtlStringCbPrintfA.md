# RtlStringCbPrintfA

- ea: `0x14000e40c`
- end: `0x14000e48d`
- name: `RtlStringCbPrintfA`
- size: `129`
- prototype: `NTSTATUS(NTSTRSAFE_PSTR pszDest, size_t cbDest, NTSTRSAFE_PCSTR pszFormat, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f1c4`
- `0x140023ab8`
- `0x140024a24`
- `0x140028b50`

## callees

- `0x14000e40c`

## import_xrefs

- `ntoskrnl!_vsnprintf` at `0x14000e449`
- `ntoskrnl!_vsnprintf` at `0x14000e449`

## pseudocode

```c
NTSTATUS RtlStringCbPrintfA(NTSTRSAFE_PSTR pszDest, size_t cbDest, NTSTRSAFE_PCSTR pszFormat, ...)
{
  NTSTATUS result; // eax
  size_t v5; // rbx
  int v6; // eax
  __int64 v7; // rcx
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, pszFormat);
  if ( !cbDest )
    return -1073741811;
  if ( cbDest <= 0x7FFFFFFF )
  {
    v5 = cbDest - 1;
    v6 = _vsnprintf(pszDest, cbDest - 1, pszFormat, Args);
    if ( v6 < 0 || (v7 = v6, v6 > v5) )
    {
      pszDest[v5] = 0;
      return -2147483643;
    }
    else
    {
      result = 0;
      if ( v7 == v5 )
        pszDest[v5] = 0;
    }
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
0x14000e40c  mov     [rsp+arg_10], r8
0x14000e411  mov     qword ptr [rsp+Args], r9
0x14000e416  push    rbx
0x14000e417  push    rdi
0x14000e418  sub     rsp, 38h
0x14000e41c  mov     rdi, rcx
0x14000e41f  test    rdx, rdx
0x14000e422  jz      short loc_14000E478
0x14000e424  cmp     rdx, 7FFFFFFFh
0x14000e42b  jbe     short loc_14000E434
0x14000e42d  mov     eax, 0C000000Dh
0x14000e432  jmp     short loc_14000E482
0x14000e434  lea     rbx, [rdx-1]
0x14000e438  mov     [rsp+48h+var_28], 0
0x14000e441  mov     rdx, rbx; Count
0x14000e444  lea     r9, [rsp+48h+Args]; Args
0x14000e449  call    cs:__imp__vsnprintf
0x14000e450  nop     dword ptr [rax+rax+00h]
0x14000e455  test    eax, eax
0x14000e457  js      short loc_14000E46D
0x14000e459  movsxd  rcx, eax
0x14000e45c  cmp     rcx, rbx
0x14000e45f  ja      short loc_14000E46D
0x14000e461  xor     eax, eax
0x14000e463  cmp     rcx, rbx
0x14000e466  jnz     short loc_14000E485
0x14000e468  mov     [rbx+rdi], al
0x14000e46b  jmp     short loc_14000E485
0x14000e46d  mov     byte ptr [rbx+rdi], 0
0x14000e471  mov     eax, 80000005h
0x14000e476  jmp     short loc_14000E485
0x14000e478  mov     eax, 0C000000Dh
0x14000e47d  test    rdx, rdx
0x14000e480  jz      short loc_14000E485
0x14000e482  mov     byte ptr [rcx], 0
0x14000e485  add     rsp, 38h
0x14000e489  pop     rdi
0x14000e48a  pop     rbx
0x14000e48b  retn
```
