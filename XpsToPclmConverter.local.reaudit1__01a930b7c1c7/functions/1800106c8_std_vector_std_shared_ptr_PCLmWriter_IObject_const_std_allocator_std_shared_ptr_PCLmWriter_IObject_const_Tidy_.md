# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Tidy(void)

- ea: `0x1800106c8`
- end: `0x180010712`
- name: `?_Tidy@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@AEAAXXZ`
- size: `74`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f71c`
- `0x18000f808`
- `0x180010290`
- `0x180010984`
- `0x1800117e4`
- `0x180011968`
- `0x180014a14`
- `0x1800152f4`

## callees

- `0x18000edc0`
- `0x18000ee2c`
- `0x1800106c8`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Tidy(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(v2, a1[1]);
    result = std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800106c8  push    rbx
0x1800106ca  sub     rsp, 20h
0x1800106ce  mov     rbx, rcx
0x1800106d1  mov     rcx, [rcx]
0x1800106d4  test    rcx, rcx
0x1800106d7  jz      short loc_18001070C
0x1800106d9  mov     rdx, [rbx+8]
0x1800106dd  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,std::shared_ptr<PCLmWriter::IObject const> * const,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x1800106e2  mov     rdx, [rbx+10h]
0x1800106e6  sub     rdx, [rbx]
0x1800106e9  mov     rcx, [rbx]
0x1800106ec  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800106f0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800106f5  mov     qword ptr [rbx], 0
0x1800106fc  mov     qword ptr [rbx+8], 0
0x180010704  mov     qword ptr [rbx+10h], 0
0x18001070c  add     rsp, 20h
0x180010710  pop     rbx
0x180010711  retn
```
