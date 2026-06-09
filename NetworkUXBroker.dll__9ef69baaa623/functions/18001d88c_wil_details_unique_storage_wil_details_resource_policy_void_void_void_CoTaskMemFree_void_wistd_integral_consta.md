# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x18001d88c`
- end: `0x18001d8a3`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `30`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001cca4`
- `0x18001d858`
- `0x18001f650`
- `0x18001f71c`
- `0x18001f7b0`
- `0x18001f870`
- `0x18001f970`
- `0x18001fa2c`
- `0x18001fb30`
- `0x18001fd80`
- `0x18001fe10`
- `0x18001fea0`
- `0x18001ff30`
- `0x18001ffc0`
- `0x180020090`
- `0x180020120`
- `0x1800201b0`
- `0x180020240`
- `0x1800202d0`
- `0x180022194`
- `0x1800259e4`
- `0x180028d90`
- `0x180034500`
- `0x180034c9c`
- `0x1800351bc`
- `0x180035878`
- `0x180036464`
- `0x18003732c`
- `0x180039564`
- `0x180039ec0`

## callees

- `0x18001d88c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d898`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d898`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
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
0x18001d88c  sub     rsp, 28h
0x18001d890  mov     rcx, [rcx]; pv
0x18001d893  test    rcx, rcx
0x18001d896  jz      short loc_18001D89E
0x18001d898  call    cs:__imp_CoTaskMemFree
0x18001d89e  add     rsp, 28h
0x18001d8a2  retn
```
