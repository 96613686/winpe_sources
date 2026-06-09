# tlx::unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>(void)

- ea: `0x180012e28`
- end: `0x180012e3f`
- name: `??1?$unique_any@U?$handle_traits@PEAEP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012f20`

## callees

- `0x180012e28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012e34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012e34`

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
0x180012e28  sub     rsp, 28h
0x180012e2c  mov     rcx, [rcx]; pv
0x180012e2f  test    rcx, rcx
0x180012e32  jz      short loc_180012E3A
0x180012e34  call    cs:__imp_CoTaskMemFree
0x180012e3a  add     rsp, 28h
0x180012e3e  retn
```
