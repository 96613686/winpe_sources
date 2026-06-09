# utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)

- ea: `0x14001ab60`
- end: `0x14001ab76`
- name: `??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140018ff0`
- `0x14001ab7c`
- `0x14001b45c`
- `0x14001b7cc`
- `0x14001bad8`
- `0x14001bfa8`
- `0x14001e8dc`
- `0x14001ea54`

## callees

- `0x14001ab60`
- `0x14001abc8`

## pseudocode

```c
__int64 __fastcall utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return utl::default_delete<KerberosCryptoPolicy>::operator()();
  return result;
}

```

## disassembly

```asm
0x14001ab60  sub     rsp, 28h
0x14001ab64  mov     rdx, [rcx]
0x14001ab67  test    rdx, rdx
0x14001ab6a  jz      short loc_14001AB71
0x14001ab6c  call    ??R?$default_delete@VKerberosCryptoPolicy@@@utl@@QEBAXPEAVKerberosCryptoPolicy@@@Z; utl::default_delete<KerberosCryptoPolicy>::operator()(KerberosCryptoPolicy *)
0x14001ab71  add     rsp, 28h
0x14001ab75  retn
```
