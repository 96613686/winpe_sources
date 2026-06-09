# OEMRUIsSameData(tagOEMRUDATA *,uchar *,void const *,uint)

- ea: `0x18000d5e4`
- end: `0x18000d628`
- name: `?OEMRUIsSameData@@YAHPEAUtagOEMRUDATA@@PEAEPEBXI@Z`
- size: `68`
- prototype: `__int64 __fastcall(struct tagOEMRUDATA *, unsigned __int8 *, const void *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d640`
- `0x18000da60`
- `0x18000e010`

## callees

- `0x18000d5e4`
- `0x180014010`

## pseudocode

```c
_BOOL8 __fastcall OEMRUIsSameData(struct tagOEMRUDATA *a1, unsigned __int8 *a2, const void *a3, unsigned int a4)
{
  int (__cdecl *v4)(const void *, const void *, size_t); // rax

  v4 = (int (__cdecl *)(const void *, const void *, size_t))*((_QWORD *)a1 + 1);
  if ( v4 == _mymemcmp )
  {
    if ( *(_DWORD *)a2 != a4 )
      return 0;
  }
  else if ( *(_DWORD *)a2 < a4 )
  {
    a4 = *(_DWORD *)a2;
  }
  return ((unsigned int (__fastcall *)(const void *, unsigned __int8 *, _QWORD))v4)(a3, a2 + 4, (int)a4) == 0;
}

```

## disassembly

```asm
0x18000d5e4  sub     rsp, 28h
0x18000d5e8  mov     rax, [rcx+8]
0x18000d5ec  mov     r10, r8
0x18000d5ef  lea     rcx, ?_mymemcmp@@YAHPEBX0_K@Z; _mymemcmp(void const *,void const *,unsigned __int64)
0x18000d5f6  cmp     rax, rcx
0x18000d5f9  jnz     short loc_18000D604
0x18000d5fb  cmp     [rdx], r9d
0x18000d5fe  jz      short loc_18000D60B
0x18000d600  xor     eax, eax
0x18000d602  jmp     short loc_18000D623
0x18000d604  cmp     [rdx], r9d
0x18000d607  cmovb   r9d, [rdx]
0x18000d60b  movsxd  r8, r9d
0x18000d60e  add     rdx, 4
0x18000d612  mov     rcx, r10
0x18000d615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61a  xor     ecx, ecx
0x18000d61c  test    eax, eax
0x18000d61e  setz    cl
0x18000d621  mov     eax, ecx
0x18000d623  add     rsp, 28h
0x18000d627  retn
```
