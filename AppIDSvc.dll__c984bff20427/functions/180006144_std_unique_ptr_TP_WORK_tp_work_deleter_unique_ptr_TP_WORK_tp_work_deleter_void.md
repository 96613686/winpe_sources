# std::unique_ptr<_TP_WORK,tp_work_deleter>::~unique_ptr<_TP_WORK,tp_work_deleter>(void)

- ea: `0x180006144`
- end: `0x18000615c`
- name: `??1?$unique_ptr@U_TP_WORK@@Utp_work_deleter@@@std@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(struct _TP_WORK **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c78c`

## callees

- `0x180006144`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180006150`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180006150`

## pseudocode

```c
void __fastcall std::unique_ptr<_TP_WORK,tp_work_deleter>::~unique_ptr<_TP_WORK,tp_work_deleter>(struct _TP_WORK **a1)
{
  struct _TP_WORK *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CloseThreadpoolWork(v1);
}

```

## disassembly

```asm
0x180006144  sub     rsp, 28h
0x180006148  mov     rcx, [rcx]; pwk
0x18000614b  test    rcx, rcx
0x18000614e  jz      short loc_180006157
0x180006150  call    cs:__imp_CloseThreadpoolWork
0x180006156  nop
0x180006157  add     rsp, 28h
0x18000615b  retn
```
