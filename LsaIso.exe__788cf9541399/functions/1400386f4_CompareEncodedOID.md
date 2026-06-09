# CompareEncodedOID

- ea: `0x1400386f4`
- end: `0x140038720`
- name: `CompareEncodedOID`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140038814`

## callees

- `0x1400386f4`
- `0x140038cc6`

## pseudocode

```c
_BOOL8 __fastcall CompareEncodedOID(const void **a1, __int64 a2)
{
  return *(_DWORD *)a1 == *(_DWORD *)a2 && memcmp_0(a1[1], *(const void **)(a2 + 8), *(unsigned int *)a1) == 0;
}

```

## disassembly

```asm
0x1400386f4  sub     rsp, 28h
0x1400386f8  mov     eax, [rcx]
0x1400386fa  cmp     eax, [rdx]
0x1400386fc  jnz     short loc_140038719
0x1400386fe  mov     rdx, [rdx+8]; Buf2
0x140038702  mov     r8d, eax; Size
0x140038705  mov     rcx, [rcx+8]; Buf1
0x140038709  call    memcmp_0
0x14003870e  xor     ecx, ecx
0x140038710  test    eax, eax
0x140038712  setz    cl
0x140038715  mov     eax, ecx
0x140038717  jmp     short loc_14003871B
0x140038719  xor     eax, eax
0x14003871b  add     rsp, 28h
0x14003871f  retn
```
