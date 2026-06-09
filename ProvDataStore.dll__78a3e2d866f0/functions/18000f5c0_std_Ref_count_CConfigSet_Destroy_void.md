# std::_Ref_count<CConfigSet>::_Destroy(void)

- ea: `0x18000f5c0`
- end: `0x18000f5e6`
- name: `?_Destroy@?$_Ref_count@VCConfigSet@@@std@@EEAAXXZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180009354`
- `0x18000f5c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f5da`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f5da`

## pseudocode

```c
void __fastcall std::_Ref_count<CConfigSet>::_Destroy(__int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 16);
  if ( v1 )
  {
    FreeProvisionData(*(struct _MVProvisionData **)(a1 + 16));
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000f5c0  push    rbx
0x18000f5c2  sub     rsp, 20h
0x18000f5c6  mov     rbx, [rcx+10h]
0x18000f5ca  test    rbx, rbx
0x18000f5cd  jz      short loc_18000F5E0
0x18000f5cf  mov     rcx, rbx; struct _MVProvisionData *
0x18000f5d2  call    ?FreeProvisionData@@YAXPEAU_MVProvisionData@@@Z; FreeProvisionData(_MVProvisionData *)
0x18000f5d7  mov     rcx, rbx
0x18000f5da  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f5e0  add     rsp, 20h
0x18000f5e4  pop     rbx
0x18000f5e5  retn
```
