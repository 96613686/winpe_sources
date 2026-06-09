# std::thread::~thread(void)

- ea: `0x180005a58`
- end: `0x180005a6e`
- name: `??1thread@std@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(std::thread *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000591c`
- `0x180007534`

## callees

- `0x180005a58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180005a62`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180005a62`

## pseudocode

```c
void __fastcall std::thread::~thread(std::thread *this)
{
  if ( *((_DWORD *)this + 2) )
  {
    _o_terminate();
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180005a58  sub     rsp, 28h
0x180005a5c  cmp     dword ptr [rcx+8], 0
0x180005a60  jz      short loc_180005A69
0x180005a62  call    cs:__imp__o_terminate
0x180005a68  int     3; Trap to Debugger
0x180005a69  add     rsp, 28h
0x180005a6d  retn
```
