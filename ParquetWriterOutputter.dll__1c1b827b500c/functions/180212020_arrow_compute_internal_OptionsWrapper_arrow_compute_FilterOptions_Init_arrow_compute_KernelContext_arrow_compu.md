# arrow::compute::internal::OptionsWrapper<arrow::compute::FilterOptions>::Init(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)

- ea: `0x180212020`
- end: `0x180212150`
- name: `?Init@?$OptionsWrapper@UFilterOptions@compute@arrow@@@internal@compute@arrow@@SA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@34@AEBUKernelInitArgs@34@@Z`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180086ed0`
- `0x18009a010`
- `0x180128400`
- `0x1801ffad0`
- `0x180212020`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x180212095`: `Attempted to initialize KernelState from null FunctionOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall arrow::compute::internal::OptionsWrapper<arrow::compute::FilterOptions>::Init(
        _QWORD *a1,
        arrow::compute::KernelContext *a2,
        __int64 a3)
{
  __int64 *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  _BYTE *v10; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // [rsp+20h] [rbp-48h] BYREF
  arrow::Status::State *v13; // [rsp+28h] [rbp-40h]
  __int64 v14; // [rsp+30h] [rbp-38h]
  _BYTE *v15; // [rsp+38h] [rbp-30h] BYREF
  __m128i si128; // [rsp+48h] [rbp-20h]

  v14 = -2;
  v12 = (void (__fastcall ***)(_QWORD, __int64))a1;
  if ( *(_QWORD *)(a3 + 16) )
  {
    v5 = (__int64 *)arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::FilterOptions>,arrow::compute::FilterOptions const &>(&v12);
    v6 = *v5;
    *v5 = 0;
    *a1 = v6;
    if ( v12 )
      (**v12)(v12, 1);
  }
  else
  {
    v7 = arrow::util::StringBuilder<char const (&)[13]>(
           &v15,
           "Attempted to initialize KernelState from null FunctionOptions");
    LOBYTE(v8) = 4;
    arrow::Status::Status(&v12, v8, v7);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v9 = si128.m128i_i64[1] + 1;
      v10 = v15;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v9 = si128.m128i_i64[1] + 40;
        v10 = (_BYTE *)*((_QWORD *)v15 - 1);
        if ( (unsigned __int64)(v15 - v10 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v10, v9);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v15) = 0;
    arrow::compute::KernelContext::SetStatus(a2, (const struct arrow::Status *)&v12);
    if ( v13 )
      arrow::Status::State::`scalar deleting destructor'(v13, 1u);
    *a1 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180212020  push    rdi
0x180212022  sub     rsp, 60h
0x180212026  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x18021202f  mov     [rsp+68h+arg_18], rbx
0x180212037  mov     rax, cs:__security_cookie
0x18021203e  xor     rax, rsp
0x180212041  mov     [rsp+68h+var_10], rax
0x180212046  mov     rdi, rdx
0x180212049  mov     rbx, rcx
0x18021204c  mov     [rsp+68h+var_48], rcx
0x180212051  mov     rdx, [r8+10h]
0x180212055  test    rdx, rdx
0x180212058  jz      short loc_180212095
0x18021205a  lea     rcx, [rsp+68h+var_48]
0x18021205f  call    ??$make_unique@U?$OptionsWrapper@UFilterOptions@compute@arrow@@@internal@compute@arrow@@AEBUFilterOptions@34@@internal@arrow@@YA?AV?$unique_ptr@U?$OptionsWrapper@UFilterOptions@compute@arrow@@@internal@compute@arrow@@U?$default_delete@U?$OptionsWrapper@UFilterOptions@compute@arrow@@@internal@compute@arrow@@@std@@@std@@AEBUFilterOptions@compute@1@@Z; arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::FilterOptions>,arrow::compute::FilterOptions const &>(arrow::compute::FilterOptions const &)
0x180212064  mov     rcx, [rax]
0x180212067  mov     qword ptr [rax], 0
0x18021206e  mov     [rbx], rcx
0x180212071  mov     rcx, [rsp+68h+var_48]
0x180212076  test    rcx, rcx
0x180212079  jz      loc_18021212C
0x18021207f  mov     rdx, [rcx]
0x180212082  mov     rax, [rdx]
0x180212085  mov     edx, 1
0x18021208a  call    cs:__guard_dispatch_icall_fptr
0x180212090  jmp     loc_18021212C
0x180212095  lea     rdx, aAttemptedToIni; "Attempted to initialize KernelState fro"...
0x18021209c  lea     rcx, [rsp+68h+var_30]
0x1802120a1  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1802120a6  nop
0x1802120a7  mov     r8, rax
0x1802120aa  mov     dl, 4
0x1802120ac  lea     rcx, [rsp+68h+var_48]
0x1802120b1  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1802120b6  nop
0x1802120b7  mov     rdx, [rsp+68h+var_18]
0x1802120bc  cmp     rdx, 10h
0x1802120c0  jb      short loc_1802120F0
0x1802120c2  inc     rdx
0x1802120c5  mov     rcx, [rsp+68h+var_30]
0x1802120ca  mov     rax, rcx
0x1802120cd  cmp     rdx, 1000h
0x1802120d4  jb      short loc_1802120EB
0x1802120d6  add     rdx, 27h ; '''; unsigned __int64
0x1802120da  mov     rcx, [rcx-8]; void *
0x1802120de  sub     rax, rcx
0x1802120e1  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802120e5  cmp     rax, 1Fh
0x1802120e9  ja      short loc_18021214A
0x1802120eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802120f0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1802120f8  movdqu  xmmword ptr [rsp+48h], xmm0
0x1802120fe  mov     byte ptr [rsp+68h+var_30], 0
0x180212103  lea     rdx, [rsp+68h+var_48]; struct arrow::Status *
0x180212108  mov     rcx, rdi; this
0x18021210b  call    ?SetStatus@KernelContext@compute@arrow@@QEAAXAEBVStatus@3@@Z; arrow::compute::KernelContext::SetStatus(arrow::Status const &)
0x180212110  nop
0x180212111  mov     rcx, [rsp+68h+var_40]; this
0x180212116  test    rcx, rcx
0x180212119  jz      short loc_180212125
0x18021211b  mov     edx, 1; unsigned int
0x180212120  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180212125  mov     qword ptr [rbx], 0
0x18021212c  mov     rax, rbx
0x18021212f  mov     rcx, [rsp+68h+var_10]
0x180212134  xor     rcx, rsp; StackCookie
0x180212137  call    __security_check_cookie
0x18021213c  mov     rbx, [rsp+68h+arg_18]
0x180212144  add     rsp, 60h
0x180212148  pop     rdi
0x180212149  retn
0x18021214a  call    _invalid_parameter_noinfo_noreturn
```
