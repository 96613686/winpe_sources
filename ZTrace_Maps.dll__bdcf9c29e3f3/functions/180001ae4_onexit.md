# _onexit

- ea: `0x180001ae4`
- end: `0x180001b1e`
- name: `_onexit`
- size: `58`
- prototype: `_onexit_t __cdecl(_onexit_t Func)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001b24`

## callees

- `0x180001ae4`
- `0x18000225e`
- `0x18000228e`

## pseudocode

```c
_onexit_t __cdecl onexit(_onexit_t Func)
{
  int v2; // eax
  int (__cdecl *v3)(); // rdx

  if ( Table._first == (_PVFV *)-1LL )
    v2 = crt_atexit((_PVFV)Func);
  else
    v2 = o__register_onexit_function_0(&Table, Func);
  v3 = 0;
  if ( !v2 )
    return Func;
  return v3;
}

```

## disassembly

```asm
0x180001ae4  push    rbx
0x180001ae6  sub     rsp, 20h
0x180001aea  cmp     cs:Table._first, 0FFFFFFFFFFFFFFFFh
0x180001af2  mov     rbx, rcx
0x180001af5  jnz     short loc_180001AFE
0x180001af7  call    _crt_atexit
0x180001afc  jmp     short loc_180001B0D
0x180001afe  mov     rdx, rbx; Function
0x180001b01  lea     rcx, Table; Table
0x180001b08  call    _o__register_onexit_function_0
0x180001b0d  xor     edx, edx
0x180001b0f  test    eax, eax
0x180001b11  cmovz   rdx, rbx
0x180001b15  mov     rax, rdx
0x180001b18  add     rsp, 20h
0x180001b1c  pop     rbx
0x180001b1d  retn
```
