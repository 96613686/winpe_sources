# std::thread::~thread(void)

- ea: `0x180012a80`
- end: `0x180012a96`
- name: `??1thread@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(std::thread *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d9fc`

## callees

- `0x180012a80`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x180012a8a`
- `api-ms-win-crt-runtime-l1-1-0!terminate` at `0x180012a8a`

## pseudocode

```c
void __fastcall std::thread::~thread(std::thread *this)
{
  if ( *((_DWORD *)this + 2) )
    terminate();
}

```

## disassembly

```asm
0x180012a80  sub     rsp, 28h
0x180012a84  cmp     dword ptr [rcx+8], 0
0x180012a88  jz      short loc_180012A91
0x180012a8a  call    cs:__imp_terminate
0x180012a91  add     rsp, 28h
0x180012a95  retn
```
