# CoTaskMemResourceStr::~CoTaskMemResourceStr(void)

- ea: `0x180042e60`
- end: `0x180042e77`
- name: `??1CoTaskMemResourceStr@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a717a`
- `0x1800a718c`

## callees

- `0x180042e60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042e6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042e6c`

## pseudocode

```c
void __fastcall CoTaskMemResourceStr::~CoTaskMemResourceStr(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180042e60  sub     rsp, 28h
0x180042e64  mov     rcx, [rcx]; pv
0x180042e67  test    rcx, rcx
0x180042e6a  jz      short loc_180042E72
0x180042e6c  call    cs:__imp_CoTaskMemFree
0x180042e72  add     rsp, 28h
0x180042e76  retn
```
