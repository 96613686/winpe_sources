# std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>(void)

- ea: `0x180005b10`
- end: `0x180005b27`
- name: `??1?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a984`
- `0x18001b027`
- `0x18001b03d`
- `0x18001b056`

## callees

- `0x180005b10`
- `0x180005b30`

## pseudocode

```c
void __fastcall std::shared_ptr<Broker::ApplicationStateTable::State>::~shared_ptr<Broker::ApplicationStateTable::State>(
        _QWORD *a1)
{
  std::_Ref_count_base *v1; // rcx

  v1 = (std::_Ref_count_base *)a1[1];
  if ( v1 )
    std::_Ref_count_base::_Decref(v1);
}

```

## disassembly

```asm
0x180005b10  sub     rsp, 28h
0x180005b14  mov     rcx, [rcx+8]; this
0x180005b18  test    rcx, rcx
0x180005b1b  jz      short loc_180005B22
0x180005b1d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ
0x180005b22  add     rsp, 28h
0x180005b26  retn
```
