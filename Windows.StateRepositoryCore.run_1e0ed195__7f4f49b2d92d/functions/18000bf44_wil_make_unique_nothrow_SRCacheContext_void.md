# wil::make_unique_nothrow<SRCacheContext,>(void)

- ea: `0x18000bf44`
- end: `0x18000bf76`
- name: `??$make_unique_nothrow@USRCacheContext@@$$V@wil@@YA?AV?$unique_ptr@USRCacheContext@@U?$default_delete@USRCacheContext@@@wistd@@@wistd@@XZ`
- size: `50`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c05c`
- `0x18000c430`
- `0x18000c950`
- `0x18000caa0`
- `0x18000cb60`
- `0x18000d090`
- `0x18000d170`

## callees

- `0x1800029dc`
- `0x18000bf44`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_nothrow<SRCacheContext,>(_QWORD *a1)
{
  _QWORD *v2; // rax

  v2 = operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    *v2 = 0;
  *a1 = v2;
  return a1;
}

```

## disassembly

```asm
0x18000bf44  push    rbx
0x18000bf46  sub     rsp, 20h
0x18000bf4a  mov     rbx, rcx
0x18000bf4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000bf54  mov     ecx, 8; unsigned __int64
0x18000bf59  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000bf5e  test    rax, rax
0x18000bf61  jz      short loc_18000BF6A
0x18000bf63  mov     qword ptr [rax], 0
0x18000bf6a  mov     [rbx], rax
0x18000bf6d  mov     rax, rbx
0x18000bf70  add     rsp, 20h
0x18000bf74  pop     rbx
0x18000bf75  retn
```
