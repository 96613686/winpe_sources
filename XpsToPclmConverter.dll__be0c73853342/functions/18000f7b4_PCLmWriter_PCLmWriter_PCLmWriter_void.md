# PCLmWriter::PCLmWriter::~PCLmWriter(void)

- ea: `0x18000f7b4`
- end: `0x18000f802`
- name: `??1PCLmWriter@0@UEAA@XZ`
- size: `78`
- prototype: `void __fastcall(PCLmWriter::PCLmWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fc80`

## callees

- `0x18000f7b4`
- `0x1800101cc`

## pseudocode

```c
void __fastcall PCLmWriter::PCLmWriter::~PCLmWriter(PCLmWriter::PCLmWriter *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx

  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 9);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 7);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 5);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18000f7b4  push    rbx
0x18000f7b6  sub     rsp, 20h
0x18000f7ba  mov     rbx, rcx
0x18000f7bd  mov     rcx, [rcx+48h]; this
0x18000f7c1  test    rcx, rcx
0x18000f7c4  jz      short loc_18000F7CB
0x18000f7c6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f7cb  mov     rcx, [rbx+38h]; this
0x18000f7cf  test    rcx, rcx
0x18000f7d2  jz      short loc_18000F7D9
0x18000f7d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f7d9  mov     rcx, [rbx+28h]; this
0x18000f7dd  test    rcx, rcx
0x18000f7e0  jz      short loc_18000F7E7
0x18000f7e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f7e7  mov     rcx, [rbx+18h]; this
0x18000f7eb  test    rcx, rcx
0x18000f7ee  jz      short loc_18000F7F5
0x18000f7f0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000f7f5  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18000f7fc  add     rsp, 20h
0x18000f800  pop     rbx
0x18000f801  retn
```
