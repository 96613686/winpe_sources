# APP_POOL_SID_DATA::~APP_POOL_SID_DATA(void)

- ea: `0x180002290`
- end: `0x1800022bf`
- name: `??1APP_POOL_SID_DATA@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(APP_POOL_SID_DATA *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180002290`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800022a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800022b8`

## pseudocode

```c
void __fastcall APP_POOL_SID_DATA::~APP_POOL_SID_DATA(APP_POOL_SID_DATA *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 7);
  if ( v2 )
  {
    LocalFree(v2);
    *((_QWORD *)this + 7) = 0;
  }
  STRU::~STRU(this);
}

```

## disassembly

```asm
0x180002290  push    rbx
0x180002292  sub     rsp, 20h
0x180002296  mov     rbx, rcx
0x180002299  mov     rcx, [rcx+38h]; hMem
0x18000229d  test    rcx, rcx
0x1800022a0  jz      short loc_1800022B0
0x1800022a2  call    cs:__imp_LocalFree
0x1800022a8  mov     qword ptr [rbx+38h], 0
0x1800022b0  mov     rcx, rbx
0x1800022b3  add     rsp, 20h
0x1800022b7  pop     rbx
0x1800022b8  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
