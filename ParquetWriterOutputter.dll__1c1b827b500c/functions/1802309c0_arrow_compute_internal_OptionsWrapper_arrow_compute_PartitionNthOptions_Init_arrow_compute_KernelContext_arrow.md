# arrow::compute::internal::OptionsWrapper<arrow::compute::PartitionNthOptions>::Init(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)

- ea: `0x1802309c0`
- end: `0x180230af0`
- name: `?Init@?$OptionsWrapper@UPartitionNthOptions@compute@arrow@@@internal@compute@arrow@@SA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@34@AEBUKernelInitArgs@34@@Z`
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
- `0x18022a3c0`
- `0x1802309c0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x180230a35`: `Attempted to initialize KernelState from null FunctionOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall arrow::compute::internal::OptionsWrapper<arrow::compute::PartitionNthOptions>::Init(
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
    v5 = (__int64 *)arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::PartitionNthOptions>,arrow::compute::PartitionNthOptions const &>(&v12);
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
0x1802309c0  push    rdi
0x1802309c2  sub     rsp, 60h
0x1802309c6  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1802309cf  mov     [rsp+68h+arg_18], rbx
0x1802309d7  mov     rax, cs:__security_cookie
0x1802309de  xor     rax, rsp
0x1802309e1  mov     [rsp+68h+var_10], rax
0x1802309e6  mov     rdi, rdx
0x1802309e9  mov     rbx, rcx
0x1802309ec  mov     [rsp+68h+var_48], rcx
0x1802309f1  mov     rdx, [r8+10h]
0x1802309f5  test    rdx, rdx
0x1802309f8  jz      short loc_180230A35
0x1802309fa  lea     rcx, [rsp+68h+var_48]
0x1802309ff  call    ??$make_unique@U?$OptionsWrapper@UPartitionNthOptions@compute@arrow@@@internal@compute@arrow@@AEBUPartitionNthOptions@34@@internal@arrow@@YA?AV?$unique_ptr@U?$OptionsWrapper@UPartitionNthOptions@compute@arrow@@@internal@compute@arrow@@U?$default_delete@U?$OptionsWrapper@UPartitionNthOptions@compute@arrow@@@internal@compute@arrow@@@std@@@std@@AEBUPartitionNthOptions@compute@1@@Z; arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::PartitionNthOptions>,arrow::compute::PartitionNthOptions const &>(arrow::compute::PartitionNthOptions const &)
0x180230a04  mov     rcx, [rax]
0x180230a07  mov     qword ptr [rax], 0
0x180230a0e  mov     [rbx], rcx
0x180230a11  mov     rcx, [rsp+68h+var_48]
0x180230a16  test    rcx, rcx
0x180230a19  jz      loc_180230ACC
0x180230a1f  mov     rdx, [rcx]
0x180230a22  mov     rax, [rdx]
0x180230a25  mov     edx, 1
0x180230a2a  call    cs:__guard_dispatch_icall_fptr
0x180230a30  jmp     loc_180230ACC
0x180230a35  lea     rdx, aAttemptedToIni; "Attempted to initialize KernelState fro"...
0x180230a3c  lea     rcx, [rsp+68h+var_30]
0x180230a41  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x180230a46  nop
0x180230a47  mov     r8, rax
0x180230a4a  mov     dl, 4
0x180230a4c  lea     rcx, [rsp+68h+var_48]
0x180230a51  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180230a56  nop
0x180230a57  mov     rdx, [rsp+68h+var_18]
0x180230a5c  cmp     rdx, 10h
0x180230a60  jb      short loc_180230A90
0x180230a62  inc     rdx
0x180230a65  mov     rcx, [rsp+68h+var_30]
0x180230a6a  mov     rax, rcx
0x180230a6d  cmp     rdx, 1000h
0x180230a74  jb      short loc_180230A8B
0x180230a76  add     rdx, 27h ; '''; unsigned __int64
0x180230a7a  mov     rcx, [rcx-8]; void *
0x180230a7e  sub     rax, rcx
0x180230a81  add     rax, 0FFFFFFFFFFFFFFF8h
0x180230a85  cmp     rax, 1Fh
0x180230a89  ja      short loc_180230AEA
0x180230a8b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180230a90  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180230a98  movdqu  xmmword ptr [rsp+48h], xmm0
0x180230a9e  mov     byte ptr [rsp+68h+var_30], 0
0x180230aa3  lea     rdx, [rsp+68h+var_48]; struct arrow::Status *
0x180230aa8  mov     rcx, rdi; this
0x180230aab  call    ?SetStatus@KernelContext@compute@arrow@@QEAAXAEBVStatus@3@@Z; arrow::compute::KernelContext::SetStatus(arrow::Status const &)
0x180230ab0  nop
0x180230ab1  mov     rcx, [rsp+68h+var_40]; this
0x180230ab6  test    rcx, rcx
0x180230ab9  jz      short loc_180230AC5
0x180230abb  mov     edx, 1; unsigned int
0x180230ac0  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180230ac5  mov     qword ptr [rbx], 0
0x180230acc  mov     rax, rbx
0x180230acf  mov     rcx, [rsp+68h+var_10]
0x180230ad4  xor     rcx, rsp; StackCookie
0x180230ad7  call    __security_check_cookie
0x180230adc  mov     rbx, [rsp+68h+arg_18]
0x180230ae4  add     rsp, 60h
0x180230ae8  pop     rdi
0x180230ae9  retn
0x180230aea  call    _invalid_parameter_noinfo_noreturn
```
