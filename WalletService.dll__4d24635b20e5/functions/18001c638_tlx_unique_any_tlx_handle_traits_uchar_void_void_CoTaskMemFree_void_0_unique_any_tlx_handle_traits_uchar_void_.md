# tlx::unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>(void)

- ea: `0x18001c638`
- end: `0x18001c64f`
- name: `??1?$unique_any@U?$handle_traits@PEAEP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d114`
- `0x18001d2a0`
- `0x180037ce0`
- `0x180043b4f`

## callees

- `0x18001c638`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c644`

## pseudocode

```c
void __fastcall tlx::unique_any<tlx::handle_traits<unsigned char *,void (*)(void *),&void CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<unsigned char *,void (*)(void *),&void CoTaskMemFree(void *),0>>(
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
0x18001c638  sub     rsp, 28h
0x18001c63c  mov     rcx, [rcx]; pv
0x18001c63f  test    rcx, rcx
0x18001c642  jz      short loc_18001C64A
0x18001c644  call    cs:__imp_CoTaskMemFree
0x18001c64a  add     rsp, 28h
0x18001c64e  retn
```
