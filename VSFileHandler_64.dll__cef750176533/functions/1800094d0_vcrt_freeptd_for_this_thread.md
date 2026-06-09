# __vcrt_freeptd_for_this_thread

- ea: `0x1800094d0`
- end: `0x180009515`
- name: `__vcrt_freeptd_for_this_thread`
- size: `69`
- prototype: `void()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800092c0`

## callees

- `0x1800094d0`
- `0x18000b86c`
- `0x18000b8b4`
- `0x18000bb08`

## pseudocode

```c
void _vcrt_freeptd_for_this_thread()
{
  __int64 *Value; // rbx

  if ( dwTlsIndex != -1 )
  {
    Value = (__int64 *)_vcrt_FlsGetValue();
    _vcrt_FlsSetValue(dwTlsIndex, 0);
    if ( Value )
    {
      if ( Value != qword_18003E1A0 )
        free(Value);
    }
  }
}

```

## disassembly

```asm
0x1800094d0  push    rbx
0x1800094d2  sub     rsp, 20h
0x1800094d6  mov     ecx, cs:dwTlsIndex
0x1800094dc  cmp     ecx, 0FFFFFFFFh
0x1800094df  jz      short loc_18000950F
0x1800094e1  call    __vcrt_FlsGetValue
0x1800094e6  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800094ec  xor     edx, edx; lpTlsValue
0x1800094ee  mov     rbx, rax
0x1800094f1  call    __vcrt_FlsSetValue
0x1800094f6  test    rbx, rbx
0x1800094f9  jz      short loc_18000950F
0x1800094fb  lea     rax, qword_18003E1A0
0x180009502  cmp     rbx, rax
0x180009505  jz      short loc_18000950F
0x180009507  mov     rcx, rbx; Block
0x18000950a  call    free
0x18000950f  add     rsp, 20h
0x180009513  pop     rbx
0x180009514  retn
```
