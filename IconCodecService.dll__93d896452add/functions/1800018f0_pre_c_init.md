# pre_c_init

- ea: `0x1800018f0`
- end: `0x180001927`
- name: `pre_c_init`
- size: `55`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800018f0`

## import_xrefs

- `msvcrt!malloc` at `0x1800018f9`
- `msvcrt!malloc` at `0x1800018f9`

## pseudocode

```c
__int64 pre_c_init()
{
  _QWORD *v0; // rax

  v0 = malloc(0x100u);
  _onexitbegin = v0;
  _onexitend = (__int64)v0;
  if ( !v0 )
    return 1;
  *v0 = 0;
  return 0;
}

```

## disassembly

```asm
0x1800018f0  sub     rsp, 28h
0x1800018f4  mov     ecx, 100h; Size
0x1800018f9  call    cs:__imp_malloc
0x1800018ff  mov     cs:__onexitbegin, rax
0x180001906  mov     cs:__onexitend, rax
0x18000190d  test    rax, rax
0x180001910  jnz     short loc_180001919
0x180001912  mov     eax, 1
0x180001917  jmp     short loc_180001922
0x180001919  mov     qword ptr [rax], 0
0x180001920  xor     eax, eax
0x180001922  add     rsp, 28h
0x180001926  retn
```
