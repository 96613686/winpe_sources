# PCLmWriter::MemoryByteStream::AppendToStream(uchar const *,uint)

- ea: `0x180012340`
- end: `0x180012416`
- name: `?AppendToStream@MemoryByteStream@PCLmWriter@@MEAAXPEBEI@Z`
- size: `214`
- prototype: `void(PCLmWriter::MemoryByteStream *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800020ba`
- `0x180002148`
- `0x180007739`
- `0x180010f34`
- `0x180012340`
- `0x180012cc0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800123f4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800123f4`

## pseudocode

```c
void __fastcall PCLmWriter::MemoryByteStream::AppendToStream(
        PCLmWriter::MemoryByteStream *this,
        const unsigned __int8 *a2,
        unsigned int a3)
{
  size_t v4; // r13
  unsigned int v6; // eax
  __int64 v7; // r12
  __int64 v8; // r14
  __int64 v9; // r15
  __int64 v10; // rdx
  unsigned __int64 v11; // rcx
  size_t v12; // rax
  size_t v13; // rbx
  size_t v14; // r8
  void *v15; // rcx

  v4 = a3;
  v6 = (*(__int64 (__fastcall **)(PCLmWriter::MemoryByteStream *))(*(_QWORD *)this + 16LL))(this);
  v7 = v6;
  v8 = v6 + (unsigned int)v4;
  if ( (unsigned int)v8 < v6 )
    PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow();
  v9 = *((_QWORD *)this + 6);
  v10 = *((_QWORD *)this + 5);
  v11 = v9 - v10;
  if ( (unsigned int)v8 >= (unsigned __int64)(v9 - v10) )
  {
    if ( (unsigned int)v8 <= v11 )
      goto LABEL_10;
    if ( (unsigned int)v8 > (unsigned __int64)(*((_QWORD *)this + 7) - v10) )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>((char *)this + 40, (unsigned int)v8);
      goto LABEL_10;
    }
    v13 = (unsigned int)v8 - v11;
    memset_0(*((void **)this + 6), 0, v13);
    v12 = v13 + v9;
  }
  else
  {
    v12 = v10 + v8;
  }
  *((_QWORD *)this + 6) = v12;
LABEL_10:
  *((_DWORD *)this + 18) = v8;
  v14 = v4;
  if ( !(_DWORD)v4 )
    return;
  v15 = (void *)(*((_QWORD *)this + 5) + v7);
  if ( v15 )
  {
    if ( a2 )
    {
      memcpy_0(v15, a2, v4);
      return;
    }
    memset_0(v15, 0, v4);
  }
  *(_DWORD *)_o__errno(v15, v10, v14) = 22;
  invalid_parameter_noinfo();
}

```

## disassembly

```asm
0x180012340  push    rbx
0x180012342  push    rbp
0x180012343  push    rsi
0x180012344  push    rdi
0x180012345  push    r12
0x180012347  push    r13
0x180012349  push    r14
0x18001234b  push    r15
0x18001234d  sub     rsp, 28h
0x180012351  mov     rax, [rcx]
0x180012354  mov     rbp, rdx
0x180012357  mov     r13d, r8d
0x18001235a  mov     rsi, rcx
0x18001235d  mov     rax, [rax+10h]
0x180012361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012366  mov     r12d, eax
0x180012369  lea     r14d, [r12+r13]
0x18001236d  cmp     r14d, eax
0x180012370  jnb     short loc_180012378
0x180012372  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@PCLmWriter@@@PCLmWriter@@SAXXZ; PCLmWriter::SafeIntExceptionHandler<PCLmWriter::Exception>::SafeIntOnOverflow(void)
0x180012378  lea     rdi, [rsi+28h]
0x18001237c  mov     ebx, r14d
0x18001237f  mov     r15, [rdi+8]
0x180012383  mov     rdx, [rdi]
0x180012386  mov     rcx, r15
0x180012389  sub     rcx, rdx
0x18001238c  cmp     rbx, rcx
0x18001238f  jnb     short loc_180012397
0x180012391  lea     rax, [rdx+r14]
0x180012395  jmp     short loc_1800123C6
0x180012397  jbe     short loc_1800123CA
0x180012399  mov     rax, [rdi+10h]
0x18001239d  sub     rax, rdx
0x1800123a0  cmp     rbx, rax
0x1800123a3  jbe     short loc_1800123B2
0x1800123a5  mov     rdx, rbx
0x1800123a8  mov     rcx, rdi
0x1800123ab  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800123b0  jmp     short loc_1800123CA
0x1800123b2  sub     rbx, rcx
0x1800123b5  xor     edx, edx; Val
0x1800123b7  mov     r8, rbx; Size
0x1800123ba  mov     rcx, r15; void *
0x1800123bd  call    memset_0
0x1800123c2  lea     rax, [rbx+r15]
0x1800123c6  mov     [rdi+8], rax
0x1800123ca  mov     [rsi+48h], r14d
0x1800123ce  mov     r8, r13; Size
0x1800123d1  test    r13d, r13d
0x1800123d4  jz      short loc_180012405
0x1800123d6  mov     rcx, r12
0x1800123d9  add     rcx, [rdi]; void *
0x1800123dc  jz      short loc_1800123F4
0x1800123de  test    rbp, rbp
0x1800123e1  jz      short loc_1800123ED
0x1800123e3  mov     rdx, rbp; Src
0x1800123e6  call    memcpy_0
0x1800123eb  jmp     short loc_180012405
0x1800123ed  xor     edx, edx; Val
0x1800123ef  call    memset_0
0x1800123f4  call    cs:__imp__o__errno
0x1800123fa  mov     dword ptr [rax], 16h
0x180012400  call    _invalid_parameter_noinfo
0x180012405  add     rsp, 28h
0x180012409  pop     r15
0x18001240b  pop     r14
0x18001240d  pop     r13
0x18001240f  pop     r12
0x180012411  pop     rdi
0x180012412  pop     rsi
0x180012413  pop     rbp
0x180012414  pop     rbx
0x180012415  retn
```
