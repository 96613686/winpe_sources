# std::unique_ptr<_POLICY,release::Deleter<void>>::~unique_ptr<_POLICY,release::Deleter<void>>(void)

- ea: `0x140002834`
- end: `0x14000284b`
- name: `??1?$unique_ptr@U_POLICY@@U?$Deleter@X@release@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _POLICY **)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140013e46`
- `0x140013e58`

## callees

- `0x140002834`
- `0x140005464`

## pseudocode

```c
void __fastcall std::unique_ptr<_POLICY,release::Deleter<void>>::~unique_ptr<_POLICY,release::Deleter<void>>(
        struct _POLICY **a1)
{
  struct _POLICY *v1; // rcx

  v1 = *a1;
  if ( v1 )
    FreePolicy(v1);
}

```

## disassembly

```asm
0x140002834  sub     rsp, 28h
0x140002838  mov     rcx, [rcx]; struct _POLICY *
0x14000283b  test    rcx, rcx
0x14000283e  jz      short loc_140002846
0x140002840  call    ?FreePolicy@@YAXPEAU_POLICY@@@Z; FreePolicy(_POLICY *)
0x140002845  nop
0x140002846  add     rsp, 28h
0x14000284a  retn
```
