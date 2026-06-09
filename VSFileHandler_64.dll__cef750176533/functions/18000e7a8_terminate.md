# terminate

- ea: `0x18000e7a8`
- end: `0x18000e7c8`
- name: `terminate`
- size: `32`
- prototype: `void __noreturn()`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180008cf0`
- `0x180008db8`
- `0x180008e20`
- `0x180009af4`
- `0x18000d920`

## callees

- `0x18000e7a8`
- `0x18000e7c8`
- `0x1800102a4`
- `0x1800241c0`

## pseudocode

```c
void __noreturn terminate()
{
  void (*v0)(void); // rax

  v0 = *(void (**)(void))(_acrt_getptd() + 24);
  if ( v0 )
    v0();
  abort();
}

```

## disassembly

```asm
0x18000e7a8  sub     rsp, 28h
0x18000e7ac  call    __acrt_getptd
0x18000e7b1  mov     rax, [rax+18h]
0x18000e7b5  test    rax, rax
0x18000e7b8  jz      short loc_18000E7C2
0x18000e7ba  call    cs:__guard_dispatch_icall_fptr
0x18000e7c0  jmp     short $+2
0x18000e7c2  call    abort
```
