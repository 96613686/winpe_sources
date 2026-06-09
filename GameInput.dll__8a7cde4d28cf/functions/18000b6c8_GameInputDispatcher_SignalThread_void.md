# GameInputDispatcher::SignalThread(void)

- ea: `0x18000b6c8`
- end: `0x18000b6f7`
- name: `?SignalThread@GameInputDispatcher@@AEAAJXZ`
- size: `47`
- prototype: `__int64 __fastcall(GameInputDispatcher *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180003e28`
- `0x1800055a0`
- `0x180008860`
- `0x180009010`
- `0x1800094b0`
- `0x180009f90`
- `0x18000a5a0`
- `0x18000afd0`

## callees

- `0x18000b6c8`

## import_xrefs

- `ntdll!NtAlertThread` at `0x18000b6d6`
- `ntdll!NtAlertThread` at `0x18000b6d6`

## pseudocode

```c
__int64 __fastcall GameInputDispatcher::SignalThread(GameInputDispatcher *this)
{
  void *v1; // rcx

  v1 = (void *)*((_QWORD *)this + 7);
  if ( v1 )
    return (NtAlertThread(v1) >> 31) & 0x80004005;
  else
    return 1;
}

```

## disassembly

```asm
0x18000b6c8  sub     rsp, 28h
0x18000b6cc  mov     rcx, [rcx+38h]; ThreadHandle
0x18000b6d0  nop
0x18000b6d1  test    rcx, rcx
0x18000b6d4  jz      short loc_18000B6EC
0x18000b6d6  call    cs:__imp_NtAlertThread
0x18000b6dd  nop     dword ptr [rax+rax+00h]
0x18000b6e2  sar     eax, 1Fh
0x18000b6e5  and     eax, 80004005h
0x18000b6ea  jmp     short loc_18000B6F1
0x18000b6ec  mov     eax, 1
0x18000b6f1  add     rsp, 28h
0x18000b6f5  retn
```
