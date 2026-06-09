# wistd::unique_ptr<_DOT11_ADAPTER_CAPABILITIES,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>::~unique_ptr<_DOT11_ADAPTER_CAPABILITIES,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>(void)

- ea: `0x18001ddfc`
- end: `0x18001de1d`
- name: `??1?$unique_ptr@U_DOT11_ADAPTER_CAPABILITIES@@U?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(void **)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18003eb64`
- `0x18003ed01`
- `0x18003ee16`
- `0x18003f200`
- `0x18003f212`
- `0x18003f437`
- `0x18003fce9`
- `0x1800403b3`

## callees

- `0x18001ddfc`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18001de12`
- `wlanapi!WlanFreeMemory` at `0x18001de12`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_DOT11_ADAPTER_CAPABILITIES,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>::~unique_ptr<_DOT11_ADAPTER_CAPABILITIES,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    WlanFreeMemory(v1);
}

```

## disassembly

```asm
0x18001ddfc  sub     rsp, 28h
0x18001de00  mov     rax, [rcx]
0x18001de03  mov     qword ptr [rcx], 0
0x18001de0a  test    rax, rax
0x18001de0d  jz      short loc_18001DE18
0x18001de0f  mov     rcx, rax; pMemory
0x18001de12  call    cs:__imp_WlanFreeMemory
0x18001de18  add     rsp, 28h
0x18001de1c  retn
```
