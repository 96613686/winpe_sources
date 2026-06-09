# std::shared_ptr<AppMon::Win32PrintStorage>::~shared_ptr<AppMon::Win32PrintStorage>(void)

- ea: `0x180006448`
- end: `0x18000645f`
- name: `??1?$shared_ptr@VWin32PrintStorage@AppMon@@@std@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f49a`
- `0x18000f5b1`
- `0x18000f5c3`
- `0x18000f5f9`
- `0x18000f61d`
- `0x18000f731`
- `0x18000f743`
- `0x18000f755`
- `0x18000fa08`

## callees

- `0x180006448`
- `0x18000798c`

## pseudocode

```c
void __fastcall std::shared_ptr<AppMon::Win32PrintStorage>::~shared_ptr<AppMon::Win32PrintStorage>(__int64 a1)
{
  std::_Ref_count_base *v1; // rcx

  v1 = *(std::_Ref_count_base **)(a1 + 8);
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
}

```

## disassembly

```asm
0x180006448  sub     rsp, 28h
0x18000644c  mov     rcx, [rcx+8]; this
0x180006450  test    rcx, rcx
0x180006453  jz      short loc_18000645A
0x180006455  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ
0x18000645a  add     rsp, 28h
0x18000645e  retn
```
