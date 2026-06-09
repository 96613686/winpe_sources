# InitOnceHolder::~InitOnceHolder(void)

- ea: `0x180043bb4`
- end: `0x180043bd2`
- name: `??1InitOnceHolder@@QEAA@XZ`
- size: `30`
- prototype: `void __fastcall(InitOnceHolder *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003e410`
- `0x180099108`
- `0x1800991e8`
- `0x18009a954`

## callees

- `0x180043bb4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180043bc7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180043bc7`

## pseudocode

```c
void __fastcall InitOnceHolder::~InitOnceHolder(union _RTL_RUN_ONCE **this)
{
  union _RTL_RUN_ONCE *v1; // rcx

  v1 = *this;
  if ( v1 )
    InitOnceComplete(v1, 4u, 0);
}

```

## disassembly

```asm
0x180043bb4  sub     rsp, 28h
0x180043bb8  mov     rcx, [rcx]; lpInitOnce
0x180043bbb  test    rcx, rcx
0x180043bbe  jz      short loc_180043BCD
0x180043bc0  xor     r8d, r8d; lpContext
0x180043bc3  lea     edx, [r8+4]; dwFlags
0x180043bc7  call    cs:__imp_InitOnceComplete
0x180043bcd  add     rsp, 28h
0x180043bd1  retn
```
