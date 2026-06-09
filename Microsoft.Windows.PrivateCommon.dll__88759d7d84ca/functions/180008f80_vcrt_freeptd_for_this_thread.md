# __vcrt_freeptd_for_this_thread

- ea: `0x180008f80`
- end: `0x180008fc5`
- name: `__vcrt_freeptd_for_this_thread`
- size: `69`
- prototype: `void()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008c00`

## callees

- `0x180008f80`
- `0x18000b37c`
- `0x18000b3c4`
- `0x18000b604`

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
      if ( Value != qword_180016160 )
        free_0(Value);
    }
  }
}

```

## disassembly

```asm
0x180008f80  push    rbx
0x180008f82  sub     rsp, 20h
0x180008f86  mov     ecx, cs:dwTlsIndex
0x180008f8c  cmp     ecx, 0FFFFFFFFh
0x180008f8f  jz      short loc_180008FBF
0x180008f91  call    __vcrt_FlsGetValue
0x180008f96  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180008f9c  xor     edx, edx; lpTlsValue
0x180008f9e  mov     rbx, rax
0x180008fa1  call    __vcrt_FlsSetValue
0x180008fa6  test    rbx, rbx
0x180008fa9  jz      short loc_180008FBF
0x180008fab  lea     rax, qword_180016160
0x180008fb2  cmp     rbx, rax
0x180008fb5  jz      short loc_180008FBF
0x180008fb7  mov     rcx, rbx; Block
0x180008fba  call    free_0
0x180008fbf  add     rsp, 20h
0x180008fc3  pop     rbx
0x180008fc4  retn
```
