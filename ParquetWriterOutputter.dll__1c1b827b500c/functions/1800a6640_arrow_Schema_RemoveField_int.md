# arrow::Schema::RemoveField(int)

- ea: `0x1800a6640`
- end: `0x1800a6831`
- name: `?RemoveField@Schema@arrow@@QEBA?AV?$Result@V?$shared_ptr@VSchema@arrow@@@std@@@2@H@Z`
- size: `497`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x1800f8f30`
- `0x180126460`

## callees

- `0x18001b890`
- `0x18001f8c0`
- `0x180086ed0`
- `0x18009a010`
- `0x1800a14f0`
- `0x1800a2590`
- `0x1800a2670`
- `0x1800a6640`
- `0x1800aae80`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1800a6777`: `Invalid column index to remove field.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall arrow::Schema::RemoveField(arrow::Schema *a1, _QWORD *a2, int a3)
{
  __int64 v3; // rbx
  __int64 v6; // rax
  _QWORD *v7; // rax
  volatile signed __int32 *v8; // rbx
  void *v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  _BYTE *v14; // rcx
  _QWORD *v16; // [rsp+20h] [rbp-88h] BYREF
  arrow::Status::State *v17; // [rsp+28h] [rbp-80h]
  _QWORD v18[4]; // [rsp+30h] [rbp-78h] BYREF
  char v19[8]; // [rsp+50h] [rbp-58h] BYREF
  volatile signed __int32 *v20; // [rsp+58h] [rbp-50h]
  _BYTE *v21; // [rsp+60h] [rbp-48h] BYREF
  __m128i si128; // [rsp+70h] [rbp-38h]

  v18[3] = -2;
  v3 = a3;
  v16 = a2;
  if ( a3 < 0 || a3 >= (int)arrow::Schema::num_fields(a1) )
  {
    v11 = arrow::util::StringBuilder<char const (&)[13]>(&v21, "Invalid column index to remove field.");
    LOBYTE(v12) = 4;
    arrow::Status::Status(&v16, v12, v11);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v13 = si128.m128i_i64[1] + 1;
      v14 = v21;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v13 = si128.m128i_i64[1] + 40;
        v14 = (_BYTE *)*((_QWORD *)v21 - 1);
        if ( (unsigned __int64)(v21 - v14 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v14, v13);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v21) = 0;
    arrow::Result<std::shared_ptr<arrow::ArrayData>>::Result<std::shared_ptr<arrow::ArrayData>>(a2, &v16);
    if ( v17 )
      arrow::Status::State::`scalar deleting destructor'(v17, 1u);
  }
  else
  {
    v6 = arrow::internal::DeleteVectorElement<std::shared_ptr<arrow::ChunkedArray>>(v18, *((_QWORD *)a1 + 4), v3);
    v7 = (_QWORD *)std::make_shared<arrow::Schema,std::vector<std::shared_ptr<arrow::Field>>,std::shared_ptr<arrow::KeyValueMetadata const> &>(
                     v19,
                     v6,
                     *((_QWORD *)a1 + 4) + 88LL);
    a2[1] = 0;
    a2[2] = 0;
    a2[3] = 0;
    a2[2] = *v7;
    a2[3] = v7[1];
    *v7 = 0;
    v7[1] = 0;
    v8 = v20;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    if ( v18[0] )
    {
      std::_Destroy_range<std::allocator<std::shared_ptr<arrow::ChunkedArray>>>(v18[0], v18[1], v18);
      v9 = (void *)v18[0];
      v10 = (v18[2] - v18[0]) & 0xFFFFFFFFFFFFFFF0uLL;
      if ( v10 >= 0x1000 )
      {
        v10 += 39LL;
        v9 = *(void **)(v18[0] - 8LL);
        if ( (unsigned __int64)(v18[0] - (_QWORD)v9 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v9, v10);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800a6640  push    rbx
0x1800a6642  push    rsi
0x1800a6643  push    rdi
0x1800a6644  sub     rsp, 90h
0x1800a664b  mov     [rsp+0A8h+var_60], 0FFFFFFFFFFFFFFFEh
0x1800a6654  mov     rax, cs:__security_cookie
0x1800a665b  xor     rax, rsp
0x1800a665e  mov     [rsp+0A8h+var_28], rax
0x1800a6666  movsxd  rbx, r8d
0x1800a6669  mov     rdi, rdx
0x1800a666c  mov     rsi, rcx
0x1800a666f  mov     [rsp+0A8h+var_88], rdx
0x1800a6674  test    r8d, r8d
0x1800a6677  js      loc_1800A6777
0x1800a667d  call    ?num_fields@Schema@arrow@@QEBAHXZ; arrow::Schema::num_fields(void)
0x1800a6682  cmp     ebx, eax
0x1800a6684  jge     loc_1800A6777
0x1800a668a  mov     r8, rbx
0x1800a668d  mov     rdx, [rsi+20h]
0x1800a6691  lea     rcx, [rsp+0A8h+var_78]
0x1800a6696  call    ??$DeleteVectorElement@V?$shared_ptr@VChunkedArray@arrow@@@std@@@internal@arrow@@YA?AV?$vector@V?$shared_ptr@VChunkedArray@arrow@@@std@@V?$allocator@V?$shared_ptr@VChunkedArray@arrow@@@std@@@2@@std@@AEBV23@_K@Z; arrow::internal::DeleteVectorElement<std::shared_ptr<arrow::ChunkedArray>>(std::vector<std::shared_ptr<arrow::ChunkedArray>> const &,unsigned __int64)
0x1800a669b  nop
0x1800a669c  mov     r8, [rsi+20h]
0x1800a66a0  add     r8, 58h ; 'X'
0x1800a66a4  mov     rdx, rax
0x1800a66a7  lea     rcx, [rsp+0A8h+var_58]
0x1800a66ac  call    ??$make_shared@VSchema@arrow@@V?$vector@V?$shared_ptr@VField@arrow@@@std@@V?$allocator@V?$shared_ptr@VField@arrow@@@std@@@2@@std@@AEAV?$shared_ptr@$$CBVKeyValueMetadata@arrow@@@4@@std@@YA?AV?$shared_ptr@VSchema@arrow@@@0@$$QEAV?$vector@V?$shared_ptr@VField@arrow@@@std@@V?$allocator@V?$shared_ptr@VField@arrow@@@std@@@2@@0@AEAV?$shared_ptr@$$CBVKeyValueMetadata@arrow@@@0@@Z; std::make_shared<arrow::Schema,std::vector<std::shared_ptr<arrow::Field>>,std::shared_ptr<arrow::KeyValueMetadata const> &>(std::vector<std::shared_ptr<arrow::Field>> &&,std::shared_ptr<arrow::KeyValueMetadata const> &)
0x1800a66b1  xor     edx, edx
0x1800a66b3  mov     [rdi+8], rdx
0x1800a66b7  mov     [rdi+10h], rdx
0x1800a66bb  mov     [rdi+18h], rdx
0x1800a66bf  mov     rcx, [rax]
0x1800a66c2  mov     [rdi+10h], rcx
0x1800a66c6  mov     rcx, [rax+8]
0x1800a66ca  mov     [rdi+18h], rcx
0x1800a66ce  mov     [rax], rdx
0x1800a66d1  mov     [rax+8], rdx
0x1800a66d5  mov     rbx, [rsp+0A8h+var_50]
0x1800a66da  test    rbx, rbx
0x1800a66dd  jz      short loc_1800A671A
0x1800a66df  mov     esi, 0FFFFFFFFh
0x1800a66e4  mov     eax, esi
0x1800a66e6  lock xadd [rbx+8], eax
0x1800a66eb  cmp     eax, 1
0x1800a66ee  jnz     short loc_1800A671A
0x1800a66f0  mov     rax, [rbx]
0x1800a66f3  mov     rcx, rbx
0x1800a66f6  mov     rax, [rax]
0x1800a66f9  call    cs:__guard_dispatch_icall_fptr
0x1800a66ff  lock xadd [rbx+0Ch], esi
0x1800a6704  cmp     esi, 1
0x1800a6707  jnz     short loc_1800A671A
0x1800a6709  mov     rax, [rbx]
0x1800a670c  mov     rcx, rbx
0x1800a670f  mov     rax, [rax+8]
0x1800a6713  call    cs:__guard_dispatch_icall_fptr
0x1800a6719  nop
0x1800a671a  mov     rcx, [rsp+0A8h+var_78]
0x1800a671f  test    rcx, rcx
0x1800a6722  jz      loc_1800A6807
0x1800a6728  lea     r8, [rsp+0A8h+var_78]
0x1800a672d  mov     rdx, [rsp+0A8h+var_70]
0x1800a6732  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VChunkedArray@arrow@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VChunkedArray@arrow@@@0@0AEAV?$allocator@V?$shared_ptr@VChunkedArray@arrow@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<arrow::ChunkedArray>>>(std::shared_ptr<arrow::ChunkedArray> *,std::shared_ptr<arrow::ChunkedArray> *,std::allocator<std::shared_ptr<arrow::ChunkedArray>> &)
0x1800a6737  mov     rdx, [rsp+0A8h+var_68]
0x1800a673c  mov     rcx, [rsp+0A8h+var_78]
0x1800a6741  sub     rdx, rcx
0x1800a6744  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800a6748  mov     rax, rcx
0x1800a674b  cmp     rdx, 1000h
0x1800a6752  jb      short loc_1800A676D
0x1800a6754  add     rdx, 27h ; '''; unsigned __int64
0x1800a6758  mov     rcx, [rcx-8]; void *
0x1800a675c  sub     rax, rcx
0x1800a675f  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a6763  cmp     rax, 1Fh
0x1800a6767  ja      loc_1800A682B
0x1800a676d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a6772  jmp     loc_1800A6807
0x1800a6777  lea     rdx, aInvalidColumnI; "Invalid column index to remove field."
0x1800a677e  lea     rcx, [rsp+0A8h+var_48]
0x1800a6783  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800a6788  nop
0x1800a6789  mov     r8, rax
0x1800a678c  mov     dl, 4
0x1800a678e  lea     rcx, [rsp+0A8h+var_88]
0x1800a6793  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800a6798  nop
0x1800a6799  mov     rdx, [rsp+0A8h+var_30]
0x1800a679e  cmp     rdx, 10h
0x1800a67a2  jb      short loc_1800A67D2
0x1800a67a4  inc     rdx
0x1800a67a7  mov     rcx, [rsp+0A8h+var_48]
0x1800a67ac  mov     rax, rcx
0x1800a67af  cmp     rdx, 1000h
0x1800a67b6  jb      short loc_1800A67CD
0x1800a67b8  add     rdx, 27h ; '''; unsigned __int64
0x1800a67bc  mov     rcx, [rcx-8]; void *
0x1800a67c0  sub     rax, rcx
0x1800a67c3  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800a67c7  cmp     rax, 1Fh
0x1800a67cb  ja      short loc_1800A6825
0x1800a67cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a67d2  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800a67da  movdqu  xmmword ptr [rsp+70h], xmm0
0x1800a67e0  mov     byte ptr [rsp+0A8h+var_48], 0
0x1800a67e5  lea     rdx, [rsp+0A8h+var_88]
0x1800a67ea  mov     rcx, rdi
0x1800a67ed  call    ??0?$Result@V?$shared_ptr@UArrayData@arrow@@@std@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<std::shared_ptr<arrow::ArrayData>>::Result<std::shared_ptr<arrow::ArrayData>>(arrow::Status const &)
0x1800a67f2  nop
0x1800a67f3  mov     rcx, [rsp+0A8h+var_80]; this
0x1800a67f8  test    rcx, rcx
0x1800a67fb  jz      short loc_1800A6807
0x1800a67fd  mov     edx, 1; unsigned int
0x1800a6802  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800a6807  mov     rax, rdi
0x1800a680a  mov     rcx, [rsp+0A8h+var_28]
0x1800a6812  xor     rcx, rsp; StackCookie
0x1800a6815  call    __security_check_cookie
0x1800a681a  add     rsp, 90h
0x1800a6821  pop     rdi
0x1800a6822  pop     rsi
0x1800a6823  pop     rbx
0x1800a6824  retn
0x1800a6825  call    _invalid_parameter_noinfo_noreturn
0x1800a682b  call    _invalid_parameter_noinfo_noreturn
```
