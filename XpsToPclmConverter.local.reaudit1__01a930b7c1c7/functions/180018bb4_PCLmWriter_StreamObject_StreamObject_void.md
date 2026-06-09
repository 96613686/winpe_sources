# PCLmWriter::StreamObject::~StreamObject(void)

- ea: `0x180018bb4`
- end: `0x180018c05`
- name: `??1StreamObject@PCLmWriter@@UEAA@XZ`
- size: `81`
- prototype: `void __fastcall(PCLmWriter::StreamObject *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018d80`

## callees

- `0x1800101cc`
- `0x180018bb4`

## pseudocode

```c
void __fastcall PCLmWriter::StreamObject::~StreamObject(PCLmWriter::StreamObject *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 8);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 4);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  *(_QWORD *)this = &PCLmWriter::IObject::`vftable';
}

```

## disassembly

```asm
0x180018bb4  push    rbx
0x180018bb6  sub     rsp, 20h
0x180018bba  mov     rbx, rcx
0x180018bbd  mov     rcx, [rcx+50h]; this
0x180018bc1  test    rcx, rcx
0x180018bc4  jz      short loc_180018BCB
0x180018bc6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018bcb  mov     rcx, [rbx+40h]; this
0x180018bcf  test    rcx, rcx
0x180018bd2  jz      short loc_180018BD9
0x180018bd4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018bd9  mov     rcx, [rbx+30h]; this
0x180018bdd  test    rcx, rcx
0x180018be0  jz      short loc_180018BE7
0x180018be2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018be7  mov     rcx, [rbx+20h]; this
0x180018beb  test    rcx, rcx
0x180018bee  jz      short loc_180018BF5
0x180018bf0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018bf5  lea     rax, ??_7IObject@PCLmWriter@@6B@; const PCLmWriter::IObject::`vftable'
0x180018bfc  mov     [rbx], rax
0x180018bff  add     rsp, 20h
0x180018c03  pop     rbx
0x180018c04  retn
```
