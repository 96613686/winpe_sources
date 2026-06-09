# std::vector<std::shared_ptr<PCLmWriter::IObject const>,std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x18000f898`
- end: `0x18000f8cc`
- name: `??1_Reallocation_guard@?$vector@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@2@@std@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ee94`
- `0x180013be0`
- `0x180014158`

## callees

- `0x18000edc0`
- `0x18000ee2c`
- `0x18000f898`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<PCLmWriter::IObject const>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( a1[1] )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(a1[3], a1[4]);
    return std::_Deallocate<16>(a1[1], 16LL * a1[2]);
  }
  return result;
}

```

## disassembly

```asm
0x18000f898  push    rbx
0x18000f89a  sub     rsp, 20h
0x18000f89e  cmp     qword ptr [rcx+8], 0
0x18000f8a3  mov     rbx, rcx
0x18000f8a6  jz      short loc_18000F8C6
0x18000f8a8  mov     rdx, [rcx+20h]
0x18000f8ac  mov     rcx, [rcx+18h]
0x18000f8b0  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@$$CBVIObject@PCLmWriter@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PCLmWriter::IObject const>>>(std::shared_ptr<PCLmWriter::IObject const> *,std::shared_ptr<PCLmWriter::IObject const> * const,std::allocator<std::shared_ptr<PCLmWriter::IObject const>> &)
0x18000f8b5  mov     rdx, [rbx+10h]
0x18000f8b9  mov     rcx, [rbx+8]
0x18000f8bd  shl     rdx, 4
0x18000f8c1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000f8c6  add     rsp, 20h
0x18000f8ca  pop     rbx
0x18000f8cb  retn
```
