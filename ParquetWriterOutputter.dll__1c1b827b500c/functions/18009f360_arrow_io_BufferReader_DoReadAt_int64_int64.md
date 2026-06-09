# arrow::io::BufferReader::DoReadAt(__int64,__int64)

- ea: `0x18009f360`
- end: `0x18009f79c`
- name: `?DoReadAt@BufferReader@io@arrow@@IEAA?AV?$Result@V?$shared_ptr@VBuffer@arrow@@@std@@@3@_J0@Z`
- size: `1084`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x18009ef40`
- `0x1800a0020`
- `0x1800a0180`

## callees

- `0x18001d5b0`
- `0x18001f8c0`
- `0x180033e20`
- `0x180049a90`
- `0x180059010`
- `0x180086ed0`
- `0x1800973c0`
- `0x180098620`
- `0x18009a010`
- `0x18009a530`
- `0x18009db90`
- `0x18009df80`
- `0x18009f360`
- `0x1800e4bb0`
- `0x1802f0fb0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x18009f3a9`: `Operation forbidden on closed BufferReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall arrow::io::BufferReader::DoReadAt(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  _BYTE *v11; // rcx
  arrow::Status::State *v12; // rax
  arrow::Status::State *v13; // rcx
  const struct arrow::Status *Range; // rax
  __int64 v15; // r14
  __int64 v16; // rax
  void *v17; // rcx
  unsigned __int64 v18; // rdx
  char *v19; // rax
  _DWORD *v20; // rsi
  _QWORD *v21; // r15
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r15
  _DWORD *v27; // rax
  __int64 v28; // rax
  unsigned __int8 v30; // [rsp+20h] [rbp-E0h]
  _QWORD v31[2]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v32[24]; // [rsp+38h] [rbp-C8h] BYREF
  char v33[8]; // [rsp+50h] [rbp-B0h] BYREF
  arrow::Status::State *v34; // [rsp+58h] [rbp-A8h]
  char v35[8]; // [rsp+60h] [rbp-A0h] BYREF
  arrow::Status::State *v36; // [rsp+68h] [rbp-98h]
  _QWORD *v37; // [rsp+70h] [rbp-90h]
  char *v38; // [rsp+78h] [rbp-88h] BYREF
  char *v39; // [rsp+88h] [rbp-78h]
  char v40[8]; // [rsp+90h] [rbp-70h] BYREF
  arrow::Status::State *v41; // [rsp+98h] [rbp-68h]
  _QWORD v42[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v43[8]; // [rsp+B0h] [rbp-50h] BYREF
  arrow::Status::State *v44; // [rsp+B8h] [rbp-48h]
  char v45[8]; // [rsp+C0h] [rbp-40h] BYREF
  arrow::Status::State *v46; // [rsp+C8h] [rbp-38h]
  __int64 v47; // [rsp+D0h] [rbp-30h]
  char v48[16]; // [rsp+D8h] [rbp-28h] BYREF
  char v49[8]; // [rsp+E8h] [rbp-18h] BYREF
  arrow::Status::State *v50; // [rsp+F0h] [rbp-10h]
  __int64 v51; // [rsp+F8h] [rbp-8h]
  char v52[8]; // [rsp+100h] [rbp+0h] BYREF
  arrow::Status::State *v53; // [rsp+108h] [rbp+8h]
  _BYTE *v54; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v55; // [rsp+130h] [rbp+30h]

  v47 = -2;
  v37 = a2;
  if ( *(_BYTE *)(a1 + 104) )
  {
    v12 = 0;
  }
  else
  {
    v8 = arrow::util::StringBuilder<char const (&)[13]>(&v54, "Operation forbidden on closed BufferReader");
    LOBYTE(v9) = 4;
    arrow::Status::Status(v40, v9, v8);
    if ( v55 >= 0x10 )
    {
      v10 = v55 + 1;
      v11 = v54;
      if ( v55 + 1 >= 0x1000 )
      {
        v10 = v55 + 40;
        v11 = (_BYTE *)*((_QWORD *)v54 - 1);
        if ( (unsigned __int64)(v54 - v11 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v11, v10);
    }
    v12 = v41;
  }
  v44 = v12;
  v41 = 0;
  if ( v12 )
  {
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v43);
    v13 = v44;
  }
  else
  {
    Range = (const struct arrow::Status *)arrow::io::internal::ValidateReadRange(
                                            (__int64)v52,
                                            a3,
                                            a4,
                                            *(_QWORD *)(a1 + 88));
    v50 = 0;
    if ( *((_QWORD *)Range + 1) )
    {
      arrow::Status::CopyFrom((arrow::Status *)v49, Range);
    }
    else
    {
      v50 = 0;
      *((_QWORD *)Range + 1) = 0;
      v51 = *((_QWORD *)Range + 2);
    }
    if ( v53 )
    {
      arrow::Status::State::`scalar deleting destructor'(v53, 1u);
      v53 = 0;
    }
    arrow::Status::Status((arrow::Status *)v33, (const struct arrow::Status *)v49);
    if ( v34 )
    {
      arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v33);
      if ( v34 )
      {
        arrow::Status::State::`scalar deleting destructor'(v34, 1u);
        v34 = 0;
      }
    }
    else
    {
      v15 = v51;
      v37 = (_QWORD *)v51;
      v42[0] = a3 + *(_QWORD *)(a1 + 80);
      v42[1] = v51;
      memset(v32, 0, sizeof(v32));
      std::vector<arrow::internal::MemoryRegion>::_Range_construct_or_tidy<arrow::internal::MemoryRegion const *>(
        v32,
        v42,
        v43,
        v30);
      v16 = arrow::internal::MemoryAdviseWillNeed(v45, v32);
      v36 = *(arrow::Status::State **)(v16 + 8);
      *(_QWORD *)(v16 + 8) = 0;
      if ( v46 )
      {
        arrow::Status::State::`scalar deleting destructor'(v46, 1u);
        v46 = 0;
      }
      v17 = *(void **)v32;
      if ( *(_QWORD *)v32 )
      {
        v18 = (*(_QWORD *)&v32[16] - *(_QWORD *)v32) & 0xFFFFFFFFFFFFFFF0uLL;
        if ( v18 >= 0x1000 )
        {
          v18 += 39LL;
          v17 = *(void **)(*(_QWORD *)v32 - 8LL);
          if ( (unsigned __int64)(*(_QWORD *)v32 - (_QWORD)v17 - 8LL) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v17, v18);
        memset(v32, 0, sizeof(v32));
      }
      if ( v36 )
      {
        arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v35);
        if ( v36 )
        {
          arrow::Status::State::`scalar deleting destructor'(v36, 1u);
          v36 = 0;
        }
      }
      else
      {
        if ( v15 > 0 && (unsigned __int8)std::operator!=<parquet::TypedStatistics<parquet::PhysicalType<3>>>(a1 + 64, 0) )
        {
          v19 = (char *)operator new(0x60u);
          v20 = v19;
          v38 = v19;
          if ( v19 )
          {
            *((_DWORD *)v19 + 2) = 1;
            *((_DWORD *)v19 + 3) = 1;
            *(_QWORD *)v19 = &std::_Ref_count_obj<arrow::Buffer>::`vftable';
            v21 = v19 + 16;
            v39 = v19 + 16;
            v22 = a3 + *(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL);
            *((_QWORD *)v19 + 2) = &arrow::Buffer::`vftable';
            *((_WORD *)v19 + 12) = 256;
            *((_QWORD *)v19 + 4) = v22;
            *((_QWORD *)v19 + 5) = 0;
            *((_QWORD *)v19 + 6) = v15;
            *((_QWORD *)v19 + 7) = v15;
            *((_QWORD *)v19 + 8) = 0;
            *((_QWORD *)v19 + 9) = 0;
            *((_QWORD *)v19 + 10) = 0;
            *((_QWORD *)v19 + 11) = 0;
            v23 = arrow::default_cpu_memory_manager(v48);
            arrow::Buffer::SetMemoryManager(v20 + 4, v23);
            *v21 = &arrow::Buffer::`vftable';
            std::shared_ptr<arrow::ArrayData>::operator=(v20 + 16, a1 + 64);
            v24 = *(_QWORD *)(a1 + 64);
            v25 = *(_QWORD *)(v24 + 72);
            if ( v25 )
            {
              _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
              v25 = *(_QWORD *)(v24 + 72);
            }
            v31[0] = *(_QWORD *)(v24 + 64);
            v31[1] = v25;
            arrow::Buffer::SetMemoryManager(v20 + 4, v31);
          }
          else
          {
            v20 = 0;
          }
          a2[1] = 0;
        }
        else
        {
          v26 = a3 + *(_QWORD *)(a1 + 80);
          v27 = operator new(0x60u);
          v20 = v27;
          v31[0] = v27;
          if ( v27 )
          {
            v27[2] = 1;
            v27[3] = 1;
            *(_QWORD *)v27 = &std::_Ref_count_obj<arrow::Buffer>::`vftable';
            v39 = (char *)(v27 + 4);
            *((_QWORD *)v27 + 2) = &arrow::Buffer::`vftable';
            *((_WORD *)v27 + 12) = 256;
            *((_QWORD *)v27 + 4) = v26;
            *((_QWORD *)v27 + 5) = 0;
            *((_QWORD *)v27 + 6) = v15;
            *((_QWORD *)v27 + 7) = v15;
            *((_QWORD *)v27 + 8) = 0;
            *((_QWORD *)v27 + 9) = 0;
            *((_QWORD *)v27 + 10) = 0;
            *((_QWORD *)v27 + 11) = 0;
            v28 = arrow::default_cpu_memory_manager(&v38);
            arrow::Buffer::SetMemoryManager(v20 + 4, v28);
          }
          else
          {
            v20 = 0;
          }
          a2[1] = 0;
        }
        a2[3] = v20;
        a2[2] = v20 + 4;
      }
    }
    v13 = v50;
  }
  if ( v13 )
    arrow::Status::State::`scalar deleting destructor'(v13, 1u);
  return a2;
}

```

## disassembly

```asm
0x18009f360  push    rbp
0x18009f362  push    rbx
0x18009f363  push    rsi
0x18009f364  push    rdi
0x18009f365  push    r12
0x18009f367  push    r13
0x18009f369  push    r14
0x18009f36b  push    r15
0x18009f36d  lea     rbp, [rsp-48h]
0x18009f372  sub     rsp, 148h
0x18009f379  mov     [rbp+80h+var_B0], 0FFFFFFFFFFFFFFFEh
0x18009f381  mov     rax, cs:__security_cookie
0x18009f388  xor     rax, rsp
0x18009f38b  mov     [rbp+80h+var_48], rax
0x18009f38f  mov     rsi, r9
0x18009f392  mov     r13, r8
0x18009f395  mov     rdi, rdx
0x18009f398  mov     rbx, rcx
0x18009f39b  mov     [rsp+180h+var_110], rdx
0x18009f3a0  xor     r12d, r12d
0x18009f3a3  cmp     [rcx+68h], r12b
0x18009f3a7  jnz     short loc_18009F40A
0x18009f3a9  lea     rdx, aOperationForbi; "Operation forbidden on closed BufferRea"...
0x18009f3b0  lea     rcx, [rbp+80h+var_68]
0x18009f3b4  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18009f3b9  nop
0x18009f3ba  mov     r8, rax
0x18009f3bd  mov     dl, 4
0x18009f3bf  lea     rcx, [rbp+80h+var_F0]
0x18009f3c3  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18009f3c8  nop
0x18009f3c9  mov     rdx, [rbp+80h+var_50]
0x18009f3cd  cmp     rdx, 10h
0x18009f3d1  jb      short loc_18009F404
0x18009f3d3  inc     rdx
0x18009f3d6  mov     rcx, [rbp+80h+var_68]
0x18009f3da  mov     rax, rcx
0x18009f3dd  cmp     rdx, 1000h
0x18009f3e4  jb      short loc_18009F3FF
0x18009f3e6  add     rdx, 27h ; '''; unsigned __int64
0x18009f3ea  mov     rcx, [rcx-8]; void *
0x18009f3ee  sub     rax, rcx
0x18009f3f1  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009f3f5  cmp     rax, 1Fh
0x18009f3f9  ja      loc_18009F796
0x18009f3ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009f404  mov     rax, [rbp+80h+var_E8]
0x18009f408  jmp     short loc_18009F40D
0x18009f40a  mov     rax, r12
0x18009f40d  mov     [rbp+80h+var_C8], rax
0x18009f411  mov     [rbp+80h+var_E8], r12
0x18009f415  test    rax, rax
0x18009f418  jz      short loc_18009F430
0x18009f41a  lea     rdx, [rbp+80h+var_D0]
0x18009f41e  mov     rcx, rdi
0x18009f421  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f426  nop
0x18009f427  mov     rcx, [rbp+80h+var_C8]
0x18009f42b  jmp     loc_18009F75E
0x18009f430  mov     r9, [rbx+58h]
0x18009f434  mov     r8, rsi
0x18009f437  mov     rdx, r13
0x18009f43a  lea     rcx, [rbp+80h+var_80]
0x18009f43e  call    ?ValidateReadRange@internal@io@arrow@@YA?AV?$Result@_J@3@_J00@Z; arrow::io::internal::ValidateReadRange(__int64,__int64,__int64)
0x18009f443  nop
0x18009f444  mov     [rbp+80h+var_90], r12
0x18009f448  cmp     qword ptr [rax+8], 0
0x18009f44d  jnz     short loc_18009F461
0x18009f44f  mov     [rbp+80h+var_90], r12
0x18009f453  mov     [rax+8], r12
0x18009f457  mov     rax, [rax+10h]
0x18009f45b  mov     [rbp+80h+var_88], rax
0x18009f45f  jmp     short loc_18009F46E
0x18009f461  mov     rdx, rax; struct arrow::Status *
0x18009f464  lea     rcx, [rbp+80h+var_98]; this
0x18009f468  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x18009f46d  nop
0x18009f46e  mov     rcx, [rbp+80h+var_78]; this
0x18009f472  test    rcx, rcx
0x18009f475  jz      short loc_18009F485
0x18009f477  mov     edx, 1; unsigned int
0x18009f47c  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f481  mov     [rbp+80h+var_78], r12
0x18009f485  lea     rdx, [rbp+80h+var_98]; struct arrow::Status *
0x18009f489  lea     rcx, [rsp+180h+var_130]; this
0x18009f48e  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x18009f493  nop
0x18009f494  cmp     [rsp+180h+var_128], 0
0x18009f49a  jz      short loc_18009F4CC
0x18009f49c  lea     rdx, [rsp+180h+var_130]
0x18009f4a1  mov     rcx, rdi
0x18009f4a4  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f4a9  nop
0x18009f4aa  mov     rcx, [rsp+180h+var_128]; this
0x18009f4af  test    rcx, rcx
0x18009f4b2  jz      loc_18009F75A
0x18009f4b8  mov     edx, 1; unsigned int
0x18009f4bd  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f4c2  mov     [rsp+180h+var_128], r12
0x18009f4c7  jmp     loc_18009F75A
0x18009f4cc  mov     r14, [rbp+80h+var_88]
0x18009f4d0  mov     [rsp+180h+var_110], r14
0x18009f4d5  mov     rcx, [rbx+50h]
0x18009f4d9  add     rcx, r13
0x18009f4dc  mov     [rbp+80h+var_E0], rcx
0x18009f4e0  mov     [rbp+80h+var_D8], r14
0x18009f4e4  mov     qword ptr [rsp+180h+var_148], r12
0x18009f4e9  xorps   xmm0, xmm0
0x18009f4ec  movdqu  [rsp+180h+var_148+8], xmm0
0x18009f4f2  movzx   r9d, [rsp+180h+var_160]
0x18009f4f8  lea     r8, [rbp+80h+var_D0]
0x18009f4fc  lea     rdx, [rbp+80h+var_E0]
0x18009f500  lea     rcx, [rsp+180h+var_148]
0x18009f505  call    ??$_Range_construct_or_tidy@PEBUMemoryRegion@internal@arrow@@@?$vector@UMemoryRegion@internal@arrow@@V?$allocator@UMemoryRegion@internal@arrow@@@std@@@std@@AEAAXPEBUMemoryRegion@internal@arrow@@0Uforward_iterator_tag@1@@Z; std::vector<arrow::internal::MemoryRegion>::_Range_construct_or_tidy<arrow::internal::MemoryRegion const *>(arrow::internal::MemoryRegion const *,arrow::internal::MemoryRegion const *,std::forward_iterator_tag)
0x18009f50a  nop
0x18009f50b  lea     rdx, [rsp+180h+var_148]
0x18009f510  lea     rcx, [rbp+80h+var_C0]
0x18009f514  call    ?MemoryAdviseWillNeed@internal@arrow@@YA?AVStatus@2@AEBV?$vector@UMemoryRegion@internal@arrow@@V?$allocator@UMemoryRegion@internal@arrow@@@std@@@std@@@Z; arrow::internal::MemoryAdviseWillNeed(std::vector<arrow::internal::MemoryRegion> const &)
0x18009f519  mov     rcx, [rax+8]
0x18009f51d  mov     [rsp+180h+var_118], rcx
0x18009f522  mov     [rax+8], r12
0x18009f526  mov     rcx, [rbp+80h+var_B8]; this
0x18009f52a  test    rcx, rcx
0x18009f52d  jz      short loc_18009F53D
0x18009f52f  mov     edx, 1; unsigned int
0x18009f534  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f539  mov     [rbp+80h+var_B8], r12
0x18009f53d  mov     rcx, qword ptr [rsp+180h+var_148]
0x18009f542  test    rcx, rcx
0x18009f545  jz      short loc_18009F58B
0x18009f547  mov     rdx, [rsp+180h+var_138]
0x18009f54c  sub     rdx, rcx
0x18009f54f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18009f553  mov     rax, rcx
0x18009f556  cmp     rdx, 1000h
0x18009f55d  jb      short loc_18009F578
0x18009f55f  add     rdx, 27h ; '''; unsigned __int64
0x18009f563  mov     rcx, [rcx-8]; void *
0x18009f567  sub     rax, rcx
0x18009f56a  add     rax, 0FFFFFFFFFFFFFFF8h
0x18009f56e  cmp     rax, 1Fh
0x18009f572  ja      loc_18009F790
0x18009f578  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009f57d  xorps   xmm0, xmm0
0x18009f580  movdqu  [rsp+180h+var_148], xmm0
0x18009f586  mov     [rsp+180h+var_138], r12
0x18009f58b  cmp     [rsp+180h+var_118], 0
0x18009f591  jz      short loc_18009F5C3
0x18009f593  lea     rdx, [rsp+180h+var_120]
0x18009f598  mov     rcx, rdi
0x18009f59b  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18009f5a0  nop
0x18009f5a1  mov     rcx, [rsp+180h+var_118]; this
0x18009f5a6  test    rcx, rcx
0x18009f5a9  jz      loc_18009F75A
0x18009f5af  mov     edx, 1; unsigned int
0x18009f5b4  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f5b9  mov     [rsp+180h+var_118], r12
0x18009f5be  jmp     loc_18009F75A
0x18009f5c3  test    r14, r14
0x18009f5c6  jle     loc_18009F6C1
0x18009f5cc  xor     edx, edx
0x18009f5ce  lea     rcx, [rbx+40h]
0x18009f5d2  call    ??$?9V?$TypedStatistics@U?$PhysicalType@$02@parquet@@@parquet@@@std@@YA_NAEBV?$shared_ptr@V?$TypedStatistics@U?$PhysicalType@$02@parquet@@@parquet@@@0@$$T@Z; std::operator!=<parquet::TypedStatistics<parquet::PhysicalType<3>>>(std::shared_ptr<parquet::TypedStatistics<parquet::PhysicalType<3>>> const &,std::nullptr_t)
0x18009f5d7  test    al, al
0x18009f5d9  jz      loc_18009F6BE
0x18009f5df  mov     ecx, 60h ; '`'; Size
0x18009f5e4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009f5e9  mov     rsi, rax
0x18009f5ec  mov     [rsp+180h+var_108], rax
0x18009f5f1  test    rax, rax
0x18009f5f4  jz      loc_18009F6AF
0x18009f5fa  mov     dword ptr [rax+8], 1
0x18009f601  mov     dword ptr [rax+0Ch], 1
0x18009f608  lea     rax, ??_7?$_Ref_count_obj@VBuffer@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::Buffer>::`vftable'
0x18009f60f  mov     [rsi], rax
0x18009f612  lea     r15, [rsi+10h]
0x18009f616  mov     [rbp+80h+var_F8], r15
0x18009f61a  mov     rcx, [rbx+40h]
0x18009f61e  mov     rcx, [rcx+10h]
0x18009f622  add     rcx, r13
0x18009f625  lea     r13, ??_7Buffer@arrow@@6B@; const arrow::Buffer::`vftable'
0x18009f62c  mov     [r15], r13
0x18009f62f  mov     word ptr [r15+8], 100h
0x18009f636  mov     [r15+10h], rcx
0x18009f63a  xor     eax, eax
0x18009f63c  mov     [r15+18h], rax
0x18009f640  mov     [r15+20h], r14
0x18009f644  mov     [r15+28h], r14
0x18009f648  mov     [r15+30h], rax
0x18009f64c  mov     [r15+38h], rax
0x18009f650  mov     [r15+40h], rax
0x18009f654  mov     [r15+48h], rax
0x18009f658  lea     rcx, [rbp+80h+var_A8]
0x18009f65c  call    ?default_cpu_memory_manager@arrow@@YA?AV?$shared_ptr@VMemoryManager@arrow@@@std@@XZ; arrow::default_cpu_memory_manager(void)
0x18009f661  mov     rdx, rax
0x18009f664  mov     rcx, r15
0x18009f667  call    ?SetMemoryManager@Buffer@arrow@@IEAAXV?$shared_ptr@VMemoryManager@arrow@@@std@@@Z; arrow::Buffer::SetMemoryManager(std::shared_ptr<arrow::MemoryManager>)
0x18009f66c  nop
0x18009f66d  mov     [r15], r13
0x18009f670  lea     rdx, [rbx+40h]
0x18009f674  lea     rcx, [r15+30h]
0x18009f678  call    ??4?$shared_ptr@UArrayData@arrow@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<arrow::ArrayData>::operator=(std::shared_ptr<arrow::ArrayData> const &)
0x18009f67d  mov     rax, [rbx+40h]
0x18009f681  mov     rdx, [rax+48h]
0x18009f685  test    rdx, rdx
0x18009f688  jz      short loc_18009F692
0x18009f68a  lock inc dword ptr [rdx+8]
0x18009f68e  mov     rdx, [rax+48h]
0x18009f692  mov     rax, [rax+40h]
0x18009f696  mov     [rsp+180h+var_158], rax
0x18009f69b  mov     [rsp+180h+var_150], rdx
0x18009f6a0  lea     rdx, [rsp+180h+var_158]
0x18009f6a5  mov     rcx, r15
0x18009f6a8  call    ?SetMemoryManager@Buffer@arrow@@IEAAXV?$shared_ptr@VMemoryManager@arrow@@@std@@@Z; arrow::Buffer::SetMemoryManager(std::shared_ptr<arrow::MemoryManager>)
0x18009f6ad  jmp     short loc_18009F6B1
0x18009f6af  xor     esi, esi
0x18009f6b1  mov     qword ptr [rdi+8], 0
0x18009f6b9  jmp     loc_18009F74E
0x18009f6be  xor     r12d, r12d
0x18009f6c1  mov     r15, [rbx+50h]
0x18009f6c5  add     r15, r13
0x18009f6c8  mov     ecx, 60h ; '`'; Size
0x18009f6cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18009f6d2  mov     rsi, rax
0x18009f6d5  mov     [rsp+180h+var_158], rax
0x18009f6da  test    rax, rax
0x18009f6dd  jz      short loc_18009F747
0x18009f6df  mov     dword ptr [rax+8], 1
0x18009f6e6  mov     dword ptr [rax+0Ch], 1
0x18009f6ed  lea     rax, ??_7?$_Ref_count_obj@VBuffer@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::Buffer>::`vftable'
0x18009f6f4  mov     [rsi], rax
0x18009f6f7  lea     rbx, [rsi+10h]
0x18009f6fb  mov     [rbp+80h+var_F8], rbx
0x18009f6ff  lea     r13, ??_7Buffer@arrow@@6B@; const arrow::Buffer::`vftable'
0x18009f706  mov     [rbx], r13
0x18009f709  mov     word ptr [rbx+8], 100h
0x18009f70f  mov     [rbx+10h], r15
0x18009f713  mov     [rbx+18h], r12
0x18009f717  mov     [rbx+20h], r14
0x18009f71b  mov     [rbx+28h], r14
0x18009f71f  mov     [rbx+30h], r12
0x18009f723  mov     [rbx+38h], r12
0x18009f727  mov     [rbx+40h], r12
0x18009f72b  mov     [rbx+48h], r12
0x18009f72f  lea     rcx, [rsp+180h+var_108]
0x18009f734  call    ?default_cpu_memory_manager@arrow@@YA?AV?$shared_ptr@VMemoryManager@arrow@@@std@@XZ; arrow::default_cpu_memory_manager(void)
0x18009f739  mov     rdx, rax
0x18009f73c  mov     rcx, rbx
0x18009f73f  call    ?SetMemoryManager@Buffer@arrow@@IEAAXV?$shared_ptr@VMemoryManager@arrow@@@std@@@Z; arrow::Buffer::SetMemoryManager(std::shared_ptr<arrow::MemoryManager>)
0x18009f744  nop
0x18009f745  jmp     short loc_18009F74A
0x18009f747  mov     rsi, r12
0x18009f74a  mov     [rdi+8], r12
0x18009f74e  lea     rax, [rsi+10h]
0x18009f752  mov     [rdi+18h], rsi
0x18009f756  mov     [rdi+10h], rax
0x18009f75a  mov     rcx, [rbp+80h+var_90]; this
0x18009f75e  test    rcx, rcx
0x18009f761  jz      short loc_18009F76D
0x18009f763  mov     edx, 1; unsigned int
0x18009f768  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009f76d  mov     rax, rdi
0x18009f770  mov     rcx, [rbp+80h+var_48]
0x18009f774  xor     rcx, rsp; StackCookie
0x18009f777  call    __security_check_cookie
0x18009f77c  add     rsp, 148h
0x18009f783  pop     r15
0x18009f785  pop     r14
0x18009f787  pop     r13
0x18009f789  pop     r12
0x18009f78b  pop     rdi
0x18009f78c  pop     rsi
0x18009f78d  pop     rbx
0x18009f78e  pop     rbp
0x18009f78f  retn
0x18009f790  call    _invalid_parameter_noinfo_noreturn
0x18009f796  call    _invalid_parameter_noinfo_noreturn
```
