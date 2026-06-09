# wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(_DEVPROPERTY *)

- ea: `0x18001e848`
- end: `0x18001e865`
- name: `??$reset@PEAU_DEVPROPERTY@@@?$unique_ptr@$$BY0A@U_DEVPROPERTY@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_DEVPROPERTY@@@Z`
- size: `29`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020a0c`
- `0x180023b24`
- `0x180047360`

## callees

- `0x18001e848`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e85a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e85a`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(
        void **a1,
        void *a2)
{
  void *v2; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18001e848  sub     rsp, 28h
0x18001e84c  mov     rax, [rcx]
0x18001e84f  mov     [rcx], rdx
0x18001e852  test    rax, rax
0x18001e855  jz      short loc_18001E860
0x18001e857  mov     rcx, rax; pv
0x18001e85a  call    cs:__imp_CoTaskMemFree
0x18001e860  add     rsp, 28h
0x18001e864  retn
```
