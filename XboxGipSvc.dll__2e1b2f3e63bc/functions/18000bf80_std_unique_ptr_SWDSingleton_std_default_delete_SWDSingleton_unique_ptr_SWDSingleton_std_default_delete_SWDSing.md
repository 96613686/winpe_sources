# std::unique_ptr<SWDSingleton,std::default_delete<SWDSingleton>>::~unique_ptr<SWDSingleton,std::default_delete<SWDSingleton>>(void)

- ea: `0x18000bf80`
- end: `0x18000bfaf`
- name: `??1?$unique_ptr@VSWDSingleton@@U?$default_delete@VSWDSingleton@@@std@@@std@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011715`

## callees

- `0x180001b6c`
- `0x18000bf80`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000bf96`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000bf96`

## pseudocode

```c
void __fastcall std::unique_ptr<SWDSingleton>::~unique_ptr<SWDSingleton>(_QWORD **a1)
{
  _QWORD *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( *v1 )
      SwDeviceClose();
    operator delete(v1, (const struct std::nothrow_t *)8);
  }
}

```

## disassembly

```asm
0x18000bf80  push    rbx
0x18000bf82  sub     rsp, 20h
0x18000bf86  mov     rbx, [rcx]
0x18000bf89  test    rbx, rbx
0x18000bf8c  jz      short loc_18000BFA9
0x18000bf8e  mov     rcx, [rbx]
0x18000bf91  test    rcx, rcx
0x18000bf94  jz      short loc_18000BF9C
0x18000bf96  call    cs:__imp_SwDeviceClose
0x18000bf9c  mov     edx, 8; struct std::nothrow_t *
0x18000bfa1  mov     rcx, rbx; void *
0x18000bfa4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bfa9  add     rsp, 20h
0x18000bfad  pop     rbx
0x18000bfae  retn
```
