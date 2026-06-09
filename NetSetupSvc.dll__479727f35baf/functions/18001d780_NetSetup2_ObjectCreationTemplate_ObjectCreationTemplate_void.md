# NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate(void)

- ea: `0x18001d780`
- end: `0x18001d7e0`
- name: `??1ObjectCreationTemplate@NetSetup2@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(NetSetup2::ObjectCreationTemplate *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001c984`
- `0x18001d664`
- `0x18001d6cc`
- `0x18001e3a8`
- `0x18001f2e4`
- `0x180020384`
- `0x180023af4`

## callees

- `0x180006e34`
- `0x1800083f8`
- `0x18001d780`

## pseudocode

```c
void __fastcall NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate(NetSetup2::ObjectCreationTemplate *this)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)this;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<NetSetup2::Property>>(v2, *((_QWORD *)this + 1));
    std::_Deallocate<16>(*(_QWORD **)this, 16 * ((__int64)(*((_QWORD *)this + 2) - *(_QWORD *)this) >> 4));
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18001d780  push    rbx
0x18001d782  sub     rsp, 20h
0x18001d786  mov     rbx, rcx
0x18001d789  mov     rcx, [rcx]
0x18001d78c  test    rcx, rcx
0x18001d78f  jz      short loc_18001D7DA
0x18001d791  mov     rdx, [rbx+8]
0x18001d795  call    ??$_Destroy_range@V?$allocator@VProperty@NetSetup2@@@std@@@std@@YAXPEAVProperty@NetSetup2@@QEAV12@AEAV?$allocator@VProperty@NetSetup2@@@0@@Z; std::_Destroy_range<std::allocator<NetSetup2::Property>>(NetSetup2::Property *,NetSetup2::Property * const,std::allocator<NetSetup2::Property> &)
0x18001d79a  mov     rax, [rbx+10h]
0x18001d79e  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18001d7a8  sub     rax, [rbx]
0x18001d7ab  sar     rax, 4
0x18001d7af  imul    rax, rcx
0x18001d7b3  mov     rcx, [rbx]
0x18001d7b6  lea     rdx, [rax+rax*2]
0x18001d7ba  shl     rdx, 4
0x18001d7be  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001d7c3  mov     qword ptr [rbx], 0
0x18001d7ca  mov     qword ptr [rbx+8], 0
0x18001d7d2  mov     qword ptr [rbx+10h], 0
0x18001d7da  add     rsp, 20h
0x18001d7de  pop     rbx
0x18001d7df  retn
```
