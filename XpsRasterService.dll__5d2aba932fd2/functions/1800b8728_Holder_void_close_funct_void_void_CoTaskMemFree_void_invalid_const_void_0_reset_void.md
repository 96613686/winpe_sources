# Holder<void *,close_funct<void (*)(void *),&CoTaskMemFree(void *)>,invalid_const<void *,0>>::reset(void)

- ea: `0x1800b8728`
- end: `0x1800b874c`
- name: `?reset@?$Holder@PEAXU?$close_funct@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@U?$invalid_const@PEAX$0A@@@@@QEAAXXZ`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7710`
- `0x1800b771c`
- `0x1800b78b8`

## callees

- `0x1800b8728`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b8739`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b8739`

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
0x1800b8728  push    rbx
0x1800b872a  sub     rsp, 20h
0x1800b872e  mov     rbx, rcx
0x1800b8731  mov     rcx, [rcx]; pv
0x1800b8734  test    rcx, rcx
0x1800b8737  jz      short loc_1800B8746
0x1800b8739  call    cs:__imp_CoTaskMemFree
0x1800b873f  mov     qword ptr [rbx], 0
0x1800b8746  add     rsp, 20h
0x1800b874a  pop     rbx
0x1800b874b  retn
```
