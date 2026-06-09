# DECODED_CERT::~DECODED_CERT(void)

- ea: `0x180003628`
- end: `0x18000365b`
- name: `??1DECODED_CERT@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(DECODED_CERT *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003824`

## callees

- `0x180003628`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003641`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003641`

## pseudocode

```c
void __fastcall DECODED_CERT::~DECODED_CERT(DECODED_CERT *this)
{
  __int64 i; // rbx
  void *v3; // rcx

  for ( i = 0; i != 4; ++i )
  {
    v3 = (void *)*((_QWORD *)this + i + 5);
    if ( v3 )
      LocalFree(v3);
  }
}

```

## disassembly

```asm
0x180003628  mov     [rsp+arg_0], rbx
0x18000362d  push    rdi
0x18000362e  sub     rsp, 20h
0x180003632  mov     rdi, rcx
0x180003635  xor     ebx, ebx
0x180003637  mov     rcx, [rdi+rbx*8+28h]; hMem
0x18000363c  test    rcx, rcx
0x18000363f  jz      short loc_180003647
0x180003641  call    cs:__imp_LocalFree
0x180003647  inc     rbx
0x18000364a  cmp     rbx, 4
0x18000364e  jnz     short loc_180003637
0x180003650  mov     rbx, [rsp+28h+arg_0]
0x180003655  add     rsp, 20h
0x180003659  pop     rdi
0x18000365a  retn
```
