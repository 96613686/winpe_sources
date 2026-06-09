# _Accommodation::Open_::_1_::dtor$3

- ea: `0x140016008`
- end: `0x140016014`
- name: `_Accommodation::Open_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000c27c`

## pseudocode

```c
void __fastcall Accommodation::Open_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  ATL::CAutoPtr<Accommodation>::~CAutoPtr<Accommodation>((Accommodation **)(a2 + 144));
}

```

## disassembly

```asm
0x140016008  lea     rcx, [rdx+90h]
0x14001600f  jmp     ??1?$CAutoPtr@VAccommodation@@@ATL@@QEAA@XZ; ATL::CAutoPtr<Accommodation>::~CAutoPtr<Accommodation>(void)
```
