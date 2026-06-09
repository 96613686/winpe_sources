# PCLmWriter::PDFFactory::CreateByteStreamFlateEncoder(std::shared_ptr<PCLmWriter::IByteStream>)

- ea: `0x1800124d0`
- end: `0x18001256d`
- name: `?CreateByteStreamFlateEncoder@PDFFactory@PCLmWriter@@UEAA?AV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@V34@@Z`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800101cc`
- `0x1800110b8`
- `0x1800124d0`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall PCLmWriter::PDFFactory::CreateByteStreamFlateEncoder(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v5; // rax
  std::_Ref_count_base *v6; // rcx
  __int64 v8; // [rsp+28h] [rbp-20h] BYREF
  std::_Ref_count_base *v9; // [rsp+30h] [rbp-18h]

  v5 = std::make_shared<PCLmWriter::ByteStreamFlateEncoder,std::shared_ptr<PCLmWriter::IByteStream> &>(&v8);
  *a2 = 0;
  a2[1] = 0;
  *a2 = *v5;
  a2[1] = v5[1];
  *v5 = 0;
  v5[1] = 0;
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 8LL))(*a2);
  v6 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  return a2;
}

```

## disassembly

```asm
0x1800124d0  mov     rax, rsp
0x1800124d3  mov     [rax+8], rbx
0x1800124d7  mov     [rax+18h], r8
0x1800124db  mov     [rax+10h], rdx
0x1800124df  push    rdi
0x1800124e0  sub     rsp, 40h
0x1800124e4  mov     rdi, r8
0x1800124e7  mov     rbx, rdx
0x1800124ea  mov     dword ptr [rax-28h], 0
0x1800124f1  mov     rdx, r8
0x1800124f4  lea     rcx, [rax-20h]
0x1800124f8  call    ??$make_shared@VByteStreamFlateEncoder@PCLmWriter@@AEAV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@std@@YA?AV?$shared_ptr@VByteStreamFlateEncoder@PCLmWriter@@@0@AEAV?$shared_ptr@VIByteStream@PCLmWriter@@@0@@Z; std::make_shared<PCLmWriter::ByteStreamFlateEncoder,std::shared_ptr<PCLmWriter::IByteStream> &>(std::shared_ptr<PCLmWriter::IByteStream> &)
0x1800124fd  mov     qword ptr [rbx], 0
0x180012504  mov     qword ptr [rbx+8], 0
0x18001250c  mov     rcx, [rax]
0x18001250f  mov     [rbx], rcx
0x180012512  mov     rcx, [rax+8]
0x180012516  mov     [rbx+8], rcx
0x18001251a  mov     qword ptr [rax], 0
0x180012521  mov     qword ptr [rax+8], 0
0x180012529  mov     [rsp+48h+var_28], 1
0x180012531  mov     rcx, [rsp+48h+var_18]; this
0x180012536  test    rcx, rcx
0x180012539  jz      short loc_180012540
0x18001253b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012540  mov     rcx, [rbx]
0x180012543  mov     rax, [rcx]
0x180012546  mov     rax, [rax+8]
0x18001254a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001254f  nop
0x180012550  mov     rcx, [rdi+8]; this
0x180012554  test    rcx, rcx
0x180012557  jz      short loc_18001255E
0x180012559  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001255e  mov     rax, rbx
0x180012561  mov     rbx, [rsp+48h+arg_0]
0x180012566  add     rsp, 40h
0x18001256a  pop     rdi
0x18001256b  retn
```
