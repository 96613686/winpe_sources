# Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>(void)

- ea: `0x180010e68`
- end: `0x180010e8e`
- name: `??1?$Lockable@V?$shared_ptr@VNetworkRequestInternalWinHttp@Pal@@@std@@@Pal@@QEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180011960`
- `0x18002ff18`
- `0x18002ffe4`

## callees

- `0x180010e68`
- `0x180013da8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010e87`

## pseudocode

```c
void __fastcall Pal::Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>::~Lockable<std::shared_ptr<Pal::NetworkRequestInternalWinHttp>>(
        __int64 a1)
{
  std::_Ref_count_base *v2; // rcx

  v2 = *(std::_Ref_count_base **)(a1 + 48);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)a1);
}

```

## disassembly

```asm
0x180010e68  push    rbx
0x180010e6a  sub     rsp, 20h
0x180010e6e  mov     rbx, rcx
0x180010e71  mov     rcx, [rcx+30h]; this
0x180010e75  test    rcx, rcx
0x180010e78  jz      short loc_180010E7F
0x180010e7a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010e7f  mov     rcx, rbx
0x180010e82  add     rsp, 20h
0x180010e86  pop     rbx
0x180010e87  jmp     cs:__imp_DeleteCriticalSection
```
