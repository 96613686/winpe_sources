# arrow::compute::internal::OptionsWrapper<arrow::compute::StrptimeOptions>::Init(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)

- ea: `0x1801d5420`
- end: `0x1801d5550`
- name: `?Init@?$OptionsWrapper@UStrptimeOptions@compute@arrow@@@internal@compute@arrow@@SA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@34@AEBUKernelInitArgs@34@@Z`
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
- `0x1801d3270`
- `0x1801d5420`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1801d5495`: `Attempted to initialize KernelState from null FunctionOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall arrow::compute::internal::OptionsWrapper<arrow::compute::StrptimeOptions>::Init(
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
    v5 = (__int64 *)arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::StrptimeOptions>,arrow::compute::StrptimeOptions const &>(&v12);
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
0x1801d5420  push    rdi
0x1801d5422  sub     rsp, 60h
0x1801d5426  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1801d542f  mov     [rsp+68h+arg_18], rbx
0x1801d5437  mov     rax, cs:__security_cookie
0x1801d543e  xor     rax, rsp
0x1801d5441  mov     [rsp+68h+var_10], rax
0x1801d5446  mov     rdi, rdx
0x1801d5449  mov     rbx, rcx
0x1801d544c  mov     [rsp+68h+var_48], rcx
0x1801d5451  mov     rdx, [r8+10h]
0x1801d5455  test    rdx, rdx
0x1801d5458  jz      short loc_1801D5495
0x1801d545a  lea     rcx, [rsp+68h+var_48]
0x1801d545f  call    ??$make_unique@U?$OptionsWrapper@UStrptimeOptions@compute@arrow@@@internal@compute@arrow@@AEBUStrptimeOptions@34@@internal@arrow@@YA?AV?$unique_ptr@U?$OptionsWrapper@UStrptimeOptions@compute@arrow@@@internal@compute@arrow@@U?$default_delete@U?$OptionsWrapper@UStrptimeOptions@compute@arrow@@@internal@compute@arrow@@@std@@@std@@AEBUStrptimeOptions@compute@1@@Z; arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::StrptimeOptions>,arrow::compute::StrptimeOptions const &>(arrow::compute::StrptimeOptions const &)
0x1801d5464  mov     rcx, [rax]
0x1801d5467  mov     qword ptr [rax], 0
0x1801d546e  mov     [rbx], rcx
0x1801d5471  mov     rcx, [rsp+68h+var_48]
0x1801d5476  test    rcx, rcx
0x1801d5479  jz      loc_1801D552C
0x1801d547f  mov     rdx, [rcx]
0x1801d5482  mov     rax, [rdx]
0x1801d5485  mov     edx, 1
0x1801d548a  call    cs:__guard_dispatch_icall_fptr
0x1801d5490  jmp     loc_1801D552C
0x1801d5495  lea     rdx, aAttemptedToIni; "Attempted to initialize KernelState fro"...
0x1801d549c  lea     rcx, [rsp+68h+var_30]
0x1801d54a1  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1801d54a6  nop
0x1801d54a7  mov     r8, rax
0x1801d54aa  mov     dl, 4
0x1801d54ac  lea     rcx, [rsp+68h+var_48]
0x1801d54b1  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1801d54b6  nop
0x1801d54b7  mov     rdx, [rsp+68h+var_18]
0x1801d54bc  cmp     rdx, 10h
0x1801d54c0  jb      short loc_1801D54F0
0x1801d54c2  inc     rdx
0x1801d54c5  mov     rcx, [rsp+68h+var_30]
0x1801d54ca  mov     rax, rcx
0x1801d54cd  cmp     rdx, 1000h
0x1801d54d4  jb      short loc_1801D54EB
0x1801d54d6  add     rdx, 27h ; '''; unsigned __int64
0x1801d54da  mov     rcx, [rcx-8]; void *
0x1801d54de  sub     rax, rcx
0x1801d54e1  add     rax, 0FFFFFFFFFFFFFFF8h
0x1801d54e5  cmp     rax, 1Fh
0x1801d54e9  ja      short loc_1801D554A
0x1801d54eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801d54f0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1801d54f8  movdqu  xmmword ptr [rsp+48h], xmm0
0x1801d54fe  mov     byte ptr [rsp+68h+var_30], 0
0x1801d5503  lea     rdx, [rsp+68h+var_48]; struct arrow::Status *
0x1801d5508  mov     rcx, rdi; this
0x1801d550b  call    ?SetStatus@KernelContext@compute@arrow@@QEAAXAEBVStatus@3@@Z; arrow::compute::KernelContext::SetStatus(arrow::Status const &)
0x1801d5510  nop
0x1801d5511  mov     rcx, [rsp+68h+var_40]; this
0x1801d5516  test    rcx, rcx
0x1801d5519  jz      short loc_1801D5525
0x1801d551b  mov     edx, 1; unsigned int
0x1801d5520  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801d5525  mov     qword ptr [rbx], 0
0x1801d552c  mov     rax, rbx
0x1801d552f  mov     rcx, [rsp+68h+var_10]
0x1801d5534  xor     rcx, rsp; StackCookie
0x1801d5537  call    __security_check_cookie
0x1801d553c  mov     rbx, [rsp+68h+arg_18]
0x1801d5544  add     rsp, 60h
0x1801d5548  pop     rdi
0x1801d5549  retn
0x1801d554a  call    _invalid_parameter_noinfo_noreturn
```
