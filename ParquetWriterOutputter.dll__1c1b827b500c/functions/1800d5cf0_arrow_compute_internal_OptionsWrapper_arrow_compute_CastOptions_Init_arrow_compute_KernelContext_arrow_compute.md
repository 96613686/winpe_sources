# arrow::compute::internal::OptionsWrapper<arrow::compute::CastOptions>::Init(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)

- ea: `0x1800d5cf0`
- end: `0x1800d5e20`
- name: `?Init@?$OptionsWrapper@UCastOptions@compute@arrow@@@internal@compute@arrow@@SA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@34@AEBUKernelInitArgs@34@@Z`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180086ed0`
- `0x18009a010`
- `0x1800d3330`
- `0x1800d5cf0`
- `0x180128400`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1800d5d65`: `Attempted to initialize KernelState from null FunctionOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall arrow::compute::internal::OptionsWrapper<arrow::compute::CastOptions>::Init(
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
    v5 = (__int64 *)arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::CastOptions>,arrow::compute::CastOptions const &>(&v12);
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
0x1800d5cf0  push    rdi
0x1800d5cf2  sub     rsp, 60h
0x1800d5cf6  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800d5cff  mov     [rsp+68h+arg_18], rbx
0x1800d5d07  mov     rax, cs:__security_cookie
0x1800d5d0e  xor     rax, rsp
0x1800d5d11  mov     [rsp+68h+var_10], rax
0x1800d5d16  mov     rdi, rdx
0x1800d5d19  mov     rbx, rcx
0x1800d5d1c  mov     [rsp+68h+var_48], rcx
0x1800d5d21  mov     rdx, [r8+10h]
0x1800d5d25  test    rdx, rdx
0x1800d5d28  jz      short loc_1800D5D65
0x1800d5d2a  lea     rcx, [rsp+68h+var_48]
0x1800d5d2f  call    ??$make_unique@U?$OptionsWrapper@UCastOptions@compute@arrow@@@internal@compute@arrow@@AEBUCastOptions@34@@internal@arrow@@YA?AV?$unique_ptr@U?$OptionsWrapper@UCastOptions@compute@arrow@@@internal@compute@arrow@@U?$default_delete@U?$OptionsWrapper@UCastOptions@compute@arrow@@@internal@compute@arrow@@@std@@@std@@AEBUCastOptions@compute@1@@Z; arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::CastOptions>,arrow::compute::CastOptions const &>(arrow::compute::CastOptions const &)
0x1800d5d34  mov     rcx, [rax]
0x1800d5d37  mov     qword ptr [rax], 0
0x1800d5d3e  mov     [rbx], rcx
0x1800d5d41  mov     rcx, [rsp+68h+var_48]
0x1800d5d46  test    rcx, rcx
0x1800d5d49  jz      loc_1800D5DFC
0x1800d5d4f  mov     rdx, [rcx]
0x1800d5d52  mov     rax, [rdx]
0x1800d5d55  mov     edx, 1
0x1800d5d5a  call    cs:__guard_dispatch_icall_fptr
0x1800d5d60  jmp     loc_1800D5DFC
0x1800d5d65  lea     rdx, aAttemptedToIni; "Attempted to initialize KernelState fro"...
0x1800d5d6c  lea     rcx, [rsp+68h+var_30]
0x1800d5d71  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800d5d76  nop
0x1800d5d77  mov     r8, rax
0x1800d5d7a  mov     dl, 4
0x1800d5d7c  lea     rcx, [rsp+68h+var_48]
0x1800d5d81  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800d5d86  nop
0x1800d5d87  mov     rdx, [rsp+68h+var_18]
0x1800d5d8c  cmp     rdx, 10h
0x1800d5d90  jb      short loc_1800D5DC0
0x1800d5d92  inc     rdx
0x1800d5d95  mov     rcx, [rsp+68h+var_30]
0x1800d5d9a  mov     rax, rcx
0x1800d5d9d  cmp     rdx, 1000h
0x1800d5da4  jb      short loc_1800D5DBB
0x1800d5da6  add     rdx, 27h ; '''; unsigned __int64
0x1800d5daa  mov     rcx, [rcx-8]; void *
0x1800d5dae  sub     rax, rcx
0x1800d5db1  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800d5db5  cmp     rax, 1Fh
0x1800d5db9  ja      short loc_1800D5E1A
0x1800d5dbb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d5dc0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800d5dc8  movdqu  xmmword ptr [rsp+48h], xmm0
0x1800d5dce  mov     byte ptr [rsp+68h+var_30], 0
0x1800d5dd3  lea     rdx, [rsp+68h+var_48]; struct arrow::Status *
0x1800d5dd8  mov     rcx, rdi; this
0x1800d5ddb  call    ?SetStatus@KernelContext@compute@arrow@@QEAAXAEBVStatus@3@@Z; arrow::compute::KernelContext::SetStatus(arrow::Status const &)
0x1800d5de0  nop
0x1800d5de1  mov     rcx, [rsp+68h+var_40]; this
0x1800d5de6  test    rcx, rcx
0x1800d5de9  jz      short loc_1800D5DF5
0x1800d5deb  mov     edx, 1; unsigned int
0x1800d5df0  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800d5df5  mov     qword ptr [rbx], 0
0x1800d5dfc  mov     rax, rbx
0x1800d5dff  mov     rcx, [rsp+68h+var_10]
0x1800d5e04  xor     rcx, rsp; StackCookie
0x1800d5e07  call    __security_check_cookie
0x1800d5e0c  mov     rbx, [rsp+68h+arg_18]
0x1800d5e14  add     rsp, 60h
0x1800d5e18  pop     rdi
0x1800d5e19  retn
0x1800d5e1a  call    _invalid_parameter_noinfo_noreturn
```
