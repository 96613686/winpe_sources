# std::default_delete<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>>::operator()(std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>> *)

- ea: `0x1800095d4`
- end: `0x180009645`
- name: `??R?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@std@@QEBAXPEAV?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@1@@Z`
- size: `113`
- prototype: `void __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x180008d94`
- `0x18002b890`
- `0x18002d310`

## callees

- `0x180002b90`
- `0x180006e34`
- `0x1800083f8`
- `0x1800095d4`

## pseudocode

```c
void __fastcall std::default_delete<std::vector<NetSetup2::Property>>::operator()(__int64 a1, _QWORD *a2)
{
  if ( a2 )
  {
    if ( *a2 )
    {
      std::_Destroy_range<std::allocator<NetSetup2::Property>>(*a2, a2[1]);
      std::_Deallocate<16>((_QWORD *)*a2, 16 * ((__int64)(a2[2] - *a2) >> 4));
      *a2 = 0;
      a2[1] = 0;
      a2[2] = 0;
    }
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x1800095d4  test    rdx, rdx
0x1800095d7  jz      short locret_180009644
0x1800095d9  push    rbx
0x1800095da  sub     rsp, 20h
0x1800095de  mov     rcx, [rdx]
0x1800095e1  mov     rbx, rdx
0x1800095e4  test    rcx, rcx
0x1800095e7  jz      short loc_180009632
0x1800095e9  mov     rdx, [rdx+8]
0x1800095ed  call    ??$_Destroy_range@V?$allocator@VProperty@NetSetup2@@@std@@@std@@YAXPEAVProperty@NetSetup2@@QEAV12@AEAV?$allocator@VProperty@NetSetup2@@@0@@Z; std::_Destroy_range<std::allocator<NetSetup2::Property>>(NetSetup2::Property *,NetSetup2::Property * const,std::allocator<NetSetup2::Property> &)
0x1800095f2  mov     rax, [rbx+10h]
0x1800095f6  mov     rcx, 0AAAAAAAAAAAAAAABh
0x180009600  sub     rax, [rbx]
0x180009603  sar     rax, 4
0x180009607  imul    rax, rcx
0x18000960b  mov     rcx, [rbx]
0x18000960e  lea     rdx, [rax+rax*2]
0x180009612  shl     rdx, 4
0x180009616  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000961b  mov     qword ptr [rbx], 0
0x180009622  mov     qword ptr [rbx+8], 0
0x18000962a  mov     qword ptr [rbx+10h], 0
0x180009632  mov     edx, 18h; unsigned __int64
0x180009637  mov     rcx, rbx; void *
0x18000963a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000963f  add     rsp, 20h
0x180009643  pop     rbx
0x180009644  retn
```
