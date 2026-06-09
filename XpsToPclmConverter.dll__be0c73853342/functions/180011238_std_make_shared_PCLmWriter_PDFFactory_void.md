# std::make_shared<PCLmWriter::PDFFactory,>(void)

- ea: `0x180011238`
- end: `0x1800112ea`
- name: `??$make_shared@VPDFFactory@PCLmWriter@@$$V@std@@YA?AV?$shared_ptr@VPDFFactory@PCLmWriter@@@0@XZ`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000f924`

## callees

- `0x180001f6c`
- `0x1800101cc`
- `0x180010204`
- `0x180010bb4`
- `0x180011238`

## pseudocode

```c
_QWORD *__fastcall std::make_shared<PCLmWriter::PDFFactory,>(_QWORD *a1)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int v4; // r9d
  _QWORD *v5; // rax
  __int64 v6; // r8
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rdx
  std::_Ref_count_base *v9; // rcx
  _DWORD *v11; // [rsp+40h] [rbp+8h]

  v11 = operator new(0x28u);
  *(_OWORD *)v11 = 0;
  v11[2] = 1;
  v11[3] = 1;
  *(_QWORD *)v11 = &std::_Ref_count_obj2<PCLmWriter::PDFFactory>::`vftable';
  std::_Construct_in_place<PCLmWriter::PDFFactory,>(v11 + 4);
  *a1 = v3;
  a1[1] = v2;
  if ( v3 )
  {
    v5 = (_QWORD *)(v3 + 8);
    v6 = *(_QWORD *)(v3 + 16);
    if ( !v6 || !*(_DWORD *)(v6 + 8) )
    {
      _InterlockedAdd((volatile signed __int32 *)(v2 + 8), v4);
      v7 = (volatile signed __int32 *)a1[1];
      if ( v7 )
      {
        v8 = a1[1];
        _InterlockedAdd(v7 + 3, v4);
      }
      else
      {
        v8 = 0;
        v3 = 0;
      }
      *v5 = v3;
      v9 = (std::_Ref_count_base *)v5[1];
      v5[1] = v8;
      if ( v9 )
        std::_Ref_count_base::_Decwref(v9);
      if ( v7 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v7);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180011238  mov     [rsp+arg_8], rbx
0x18001123d  push    rdi
0x18001123e  sub     rsp, 30h
0x180011242  mov     rdi, rcx
0x180011245  mov     ecx, 28h ; '('; Size
0x18001124a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001124f  mov     [rsp+38h+arg_0], rax
0x180011254  mov     rdx, rax
0x180011257  mov     r9d, 1
0x18001125d  xorps   xmm0, xmm0
0x180011260  movups  xmmword ptr [rax], xmm0
0x180011263  mov     [rax+8], r9d
0x180011267  lea     rcx, [rdx+10h]
0x18001126b  mov     [rax+0Ch], r9d
0x18001126f  lea     rax, ??_7?$_Ref_count_obj2@VPDFFactory@PCLmWriter@@@std@@6B@; const std::_Ref_count_obj2<PCLmWriter::PDFFactory>::`vftable'
0x180011276  mov     [rdx], rax
0x180011279  call    ??$_Construct_in_place@VPDFFactory@PCLmWriter@@$$V@std@@YAXAEAVPDFFactory@PCLmWriter@@@Z; std::_Construct_in_place<PCLmWriter::PDFFactory,>(PCLmWriter::PDFFactory &)
0x18001127e  mov     [rdi], rcx
0x180011281  mov     [rdi+8], rdx
0x180011285  test    rcx, rcx
0x180011288  jz      short loc_1800112DC
0x18001128a  lea     rax, [rcx+8]
0x18001128e  mov     r8, [rax+8]
0x180011292  test    r8, r8
0x180011295  jz      short loc_18001129E
0x180011297  cmp     dword ptr [r8+8], 0
0x18001129c  jnz     short loc_1800112DC
0x18001129e  lock add [rdx+8], r9d
0x1800112a3  mov     rbx, [rdi+8]
0x1800112a7  test    rbx, rbx
0x1800112aa  jz      short loc_1800112B6
0x1800112ac  mov     rdx, rbx
0x1800112af  lock add [rbx+0Ch], r9d
0x1800112b4  jmp     short loc_1800112BA
0x1800112b6  xor     edx, edx
0x1800112b8  xor     ecx, ecx
0x1800112ba  mov     [rax], rcx
0x1800112bd  mov     rcx, [rax+8]; this
0x1800112c1  mov     [rax+8], rdx
0x1800112c5  test    rcx, rcx
0x1800112c8  jz      short loc_1800112CF
0x1800112ca  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800112cf  test    rbx, rbx
0x1800112d2  jz      short loc_1800112DC
0x1800112d4  mov     rcx, rbx; this
0x1800112d7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800112dc  mov     rbx, [rsp+38h+arg_8]
0x1800112e1  mov     rax, rdi
0x1800112e4  add     rsp, 30h
0x1800112e8  pop     rdi
0x1800112e9  retn
```
