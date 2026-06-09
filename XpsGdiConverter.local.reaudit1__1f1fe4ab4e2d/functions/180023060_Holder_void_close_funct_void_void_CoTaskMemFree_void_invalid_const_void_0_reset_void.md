# Holder<void *,close_funct<void (*)(void *),&CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(void)

- ea: `0x180023060`
- end: `0x180023084`
- name: `?reset@?$Holder@PEAXU?$close_funct@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@U?$invalid_const@PEAX$0A@@@@@QEAAXXZ`
- size: `36`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001d1ec`
- `0x18001d77c`
- `0x18001d788`
- `0x18002bcf0`
- `0x18003dcd4`

## callees

- `0x180023060`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180023071`
- `ole32!CoTaskMemFree` at `0x180023071`

## pseudocode

```c
void __fastcall Holder<void *,close_funct<void (*)(void *),&void CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180023060  push    rbx
0x180023062  sub     rsp, 20h
0x180023066  mov     rbx, rcx
0x180023069  mov     rcx, [rcx]; pv
0x18002306c  test    rcx, rcx
0x18002306f  jz      short loc_18002307E
0x180023071  call    cs:__imp_CoTaskMemFree
0x180023077  mov     qword ptr [rbx], 0
0x18002307e  add     rsp, 20h
0x180023082  pop     rbx
0x180023083  retn
```
