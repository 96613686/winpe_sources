# std::unique_ptr<uchar,Windows::Sms::Common::CoMemDeleter>::~unique_ptr<uchar,Windows::Sms::Common::CoMemDeleter>(void)

- ea: `0x1800288d4`
- end: `0x1800288eb`
- name: `??1?$unique_ptr@EVCoMemDeleter@Common@Sms@Windows@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006d077`
- `0x18006d1bb`

## callees

- `0x1800288d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800288e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800288e0`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char,Windows::Sms::Common::CoMemDeleter>::~unique_ptr<unsigned char,Windows::Sms::Common::CoMemDeleter>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x1800288d4  sub     rsp, 28h
0x1800288d8  mov     rcx, [rcx]; pv
0x1800288db  test    rcx, rcx
0x1800288de  jz      short loc_1800288E6
0x1800288e0  call    cs:__imp_CoTaskMemFree
0x1800288e6  add     rsp, 28h
0x1800288ea  retn
```
