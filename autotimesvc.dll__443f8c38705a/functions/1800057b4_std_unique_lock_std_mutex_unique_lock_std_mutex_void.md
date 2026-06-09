# std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)

- ea: `0x1800057b4`
- end: `0x1800057cc`
- name: `??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ`
- size: `24`
- prototype: `int __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800081ac`
- `0x18000a3c0`
- `0x18000a53c`
- `0x18000a720`
- `0x18001146d`
- `0x1800114c7`

## callees

- `0x1800057b4`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800057c1`
- `msvcp_win!_Mtx_unlock` at `0x1800057c1`

## pseudocode

```c
int __fastcall std::unique_lock<std::mutex>::~unique_lock<std::mutex>(__int64 a1)
{
  int result; // eax

  if ( *(_BYTE *)(a1 + 8) )
    return _Mtx_unlock(*(_Mtx_t *)a1);
  return result;
}

```

## disassembly

```asm
0x1800057b4  sub     rsp, 28h
0x1800057b8  cmp     byte ptr [rcx+8], 0
0x1800057bc  jz      short loc_1800057C7
0x1800057be  mov     rcx, [rcx]; _Mtx_t
0x1800057c1  call    cs:__imp__Mtx_unlock
0x1800057c7  add     rsp, 28h
0x1800057cb  retn
```
