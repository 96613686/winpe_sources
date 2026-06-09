# std::make_shared<PCLmWriter::ByteStreamFlateEncoder,std::shared_ptr<PCLmWriter::IByteStream> &>(std::shared_ptr<PCLmWriter::IByteStream> &)

- ea: `0x1800110b8`
- end: `0x18001116f`
- name: `??$make_shared@VByteStreamFlateEncoder@PCLmWriter@@AEAV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@std@@YA?AV?$shared_ptr@VByteStreamFlateEncoder@PCLmWriter@@@0@AEAV?$shared_ptr@VIByteStream@PCLmWriter@@@0@@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800124d0`

## callees

- `0x180001f6c`
- `0x1800101cc`
- `0x180010204`
- `0x1800109f4`
- `0x1800110b8`

## pseudocode

```c
_QWORD *__fastcall std::make_shared<PCLmWriter::ByteStreamFlateEncoder,std::shared_ptr<PCLmWriter::IByteStream> &>(
        _QWORD *a1)
{
  char *v2; // rdi
  char *v3; // rsi
  __int64 v4; // rcx
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rdx
  std::_Ref_count_base *v7; // rcx

  v2 = (char *)operator new(0x70u);
  *(_OWORD *)v2 = 0;
  *((_DWORD *)v2 + 2) = 1;
  v3 = v2 + 16;
  *((_DWORD *)v2 + 3) = 1;
  *(_QWORD *)v2 = &std::_Ref_count_obj2<PCLmWriter::ByteStreamFlateEncoder>::`vftable';
  std::_Construct_in_place<PCLmWriter::ByteStreamFlateEncoder,std::shared_ptr<PCLmWriter::IByteStream> &>((PCLmWriter::MemoryByteStream *)(v2 + 16));
  *a1 = v2 + 16;
  a1[1] = v2;
  if ( v2 != (char *)-16LL )
  {
    v4 = *((_QWORD *)v2 + 5);
    if ( !v4 || !*(_DWORD *)(v4 + 8) )
    {
      _InterlockedIncrement((volatile signed __int32 *)v2 + 2);
      v5 = (volatile signed __int32 *)a1[1];
      if ( v5 )
      {
        v6 = a1[1];
        _InterlockedIncrement(v5 + 3);
      }
      else
      {
        v6 = 0;
        v3 = 0;
      }
      *((_QWORD *)v2 + 4) = v3;
      v7 = (std::_Ref_count_base *)*((_QWORD *)v2 + 5);
      *((_QWORD *)v2 + 5) = v6;
      if ( v7 )
        std::_Ref_count_base::_Decwref(v7);
      if ( v5 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v5);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800110b8  push    rbx
0x1800110ba  push    rsi
0x1800110bb  push    rdi
0x1800110bc  push    r14
0x1800110be  sub     rsp, 38h
0x1800110c2  mov     r14, rcx
0x1800110c5  mov     rbx, rdx
0x1800110c8  mov     ecx, 70h ; 'p'; Size
0x1800110cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800110d2  mov     [rsp+58h+arg_0], rax
0x1800110d7  mov     rdi, rax
0x1800110da  xorps   xmm0, xmm0
0x1800110dd  mov     rdx, rbx
0x1800110e0  movups  xmmword ptr [rax], xmm0
0x1800110e3  mov     dword ptr [rax+8], 1
0x1800110ea  lea     rsi, [rdi+10h]
0x1800110ee  mov     dword ptr [rax+0Ch], 1
0x1800110f5  mov     rcx, rsi; this
0x1800110f8  lea     rax, ??_7?$_Ref_count_obj2@VByteStreamFlateEncoder@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::ByteStreamFlateEncoder>::`vftable'
0x1800110ff  mov     [rdi], rax
0x180011102  call    ??$_Construct_in_place@VByteStreamFlateEncoder@PCLmWriter@@AEAV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@std@@YAXAEAVByteStreamFlateEncoder@PCLmWriter@@AEAV?$shared_ptr@VIByteStream@PCLmWriter@@@0@@Z; std::_Construct_in_place<PCLmWriter::ByteStreamFlateEncoder,std::shared_ptr<PCLmWriter::IByteStream> &>(PCLmWriter::ByteStreamFlateEncoder &,std::shared_ptr<PCLmWriter::IByteStream> &)
0x180011107  mov     [r14], rsi
0x18001110a  mov     [r14+8], rdi
0x18001110e  test    rsi, rsi
0x180011111  jz      short loc_180011162
0x180011113  lea     rax, [rsi+10h]
0x180011117  mov     rcx, [rax+8]
0x18001111b  test    rcx, rcx
0x18001111e  jz      short loc_180011126
0x180011120  cmp     dword ptr [rcx+8], 0
0x180011124  jnz     short loc_180011162
0x180011126  lock inc dword ptr [rdi+8]
0x18001112a  mov     rbx, [r14+8]
0x18001112e  test    rbx, rbx
0x180011131  jz      short loc_18001113C
0x180011133  mov     rdx, rbx
0x180011136  lock inc dword ptr [rbx+0Ch]
0x18001113a  jmp     short loc_180011140
0x18001113c  xor     edx, edx
0x18001113e  xor     esi, esi
0x180011140  mov     [rax], rsi
0x180011143  mov     rcx, [rax+8]; this
0x180011147  mov     [rax+8], rdx
0x18001114b  test    rcx, rcx
0x18001114e  jz      short loc_180011155
0x180011150  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180011155  test    rbx, rbx
0x180011158  jz      short loc_180011162
0x18001115a  mov     rcx, rbx; this
0x18001115d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011162  mov     rax, r14
0x180011165  add     rsp, 38h
0x180011169  pop     r14
0x18001116b  pop     rdi
0x18001116c  pop     rsi
0x18001116d  pop     rbx
0x18001116e  retn
```
