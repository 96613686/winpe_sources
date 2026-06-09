# arrow::compute::internal::OptionsWrapper<arrow::compute::MatchSubstringOptions>::Init(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)

- ea: `0x1801d52f0`
- end: `0x1801d5420`
- name: `?Init@?$OptionsWrapper@UMatchSubstringOptions@compute@arrow@@@internal@compute@arrow@@SA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@34@AEBUKernelInitArgs@34@@Z`
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
- `0x1801d31e0`
- `0x1801d52f0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1801d5365`: `Attempted to initialize KernelState from null FunctionOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall arrow::compute::internal::OptionsWrapper<arrow::compute::MatchSubstringOptions>::Init(
        _QWORD *a1,
        arrow::compute::KernelContext *a2,
        __int64 a3)
{
  __int64 *matched; // rax
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
    matched = (__int64 *)arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::MatchSubstringOptions>,arrow::compute::MatchSubstringOptions const &>(&v12);
    v6 = *matched;
    *matched = 0;
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
0x1801d52f0  push    rdi
0x1801d52f2  sub     rsp, 60h
0x1801d52f6  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1801d52ff  mov     [rsp+68h+arg_18], rbx
0x1801d5307  mov     rax, cs:__security_cookie
0x1801d530e  xor     rax, rsp
0x1801d5311  mov     [rsp+68h+var_10], rax
0x1801d5316  mov     rdi, rdx
0x1801d5319  mov     rbx, rcx
0x1801d531c  mov     [rsp+68h+var_48], rcx
0x1801d5321  mov     rdx, [r8+10h]
0x1801d5325  test    rdx, rdx
0x1801d5328  jz      short loc_1801D5365
0x1801d532a  lea     rcx, [rsp+68h+var_48]
0x1801d532f  call    ??$make_unique@U?$OptionsWrapper@UMatchSubstringOptions@compute@arrow@@@internal@compute@arrow@@AEBUMatchSubstringOptions@34@@internal@arrow@@YA?AV?$unique_ptr@U?$OptionsWrapper@UMatchSubstringOptions@compute@arrow@@@internal@compute@arrow@@U?$default_delete@U?$OptionsWrapper@UMatchSubstringOptions@compute@arrow@@@internal@compute@arrow@@@std@@@std@@AEBUMatchSubstringOptions@compute@1@@Z; arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::MatchSubstringOptions>,arrow::compute::MatchSubstringOptions const &>(arrow::compute::MatchSubstringOptions const &)
0x1801d5334  mov     rcx, [rax]
0x1801d5337  mov     qword ptr [rax], 0
0x1801d533e  mov     [rbx], rcx
0x1801d5341  mov     rcx, [rsp+68h+var_48]
0x1801d5346  test    rcx, rcx
0x1801d5349  jz      loc_1801D53FC
0x1801d534f  mov     rdx, [rcx]
0x1801d5352  mov     rax, [rdx]
0x1801d5355  mov     edx, 1
0x1801d535a  call    cs:__guard_dispatch_icall_fptr
0x1801d5360  jmp     loc_1801D53FC
0x1801d5365  lea     rdx, aAttemptedToIni; "Attempted to initialize KernelState fro"...
0x1801d536c  lea     rcx, [rsp+68h+var_30]
0x1801d5371  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1801d5376  nop
0x1801d5377  mov     r8, rax
0x1801d537a  mov     dl, 4
0x1801d537c  lea     rcx, [rsp+68h+var_48]
0x1801d5381  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1801d5386  nop
0x1801d5387  mov     rdx, [rsp+68h+var_18]
0x1801d538c  cmp     rdx, 10h
0x1801d5390  jb      short loc_1801D53C0
0x1801d5392  inc     rdx
0x1801d5395  mov     rcx, [rsp+68h+var_30]
0x1801d539a  mov     rax, rcx
0x1801d539d  cmp     rdx, 1000h
0x1801d53a4  jb      short loc_1801D53BB
0x1801d53a6  add     rdx, 27h ; '''; unsigned __int64
0x1801d53aa  mov     rcx, [rcx-8]; void *
0x1801d53ae  sub     rax, rcx
0x1801d53b1  add     rax, 0FFFFFFFFFFFFFFF8h
0x1801d53b5  cmp     rax, 1Fh
0x1801d53b9  ja      short loc_1801D541A
0x1801d53bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1801d53c0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1801d53c8  movdqu  xmmword ptr [rsp+48h], xmm0
0x1801d53ce  mov     byte ptr [rsp+68h+var_30], 0
0x1801d53d3  lea     rdx, [rsp+68h+var_48]; struct arrow::Status *
0x1801d53d8  mov     rcx, rdi; this
0x1801d53db  call    ?SetStatus@KernelContext@compute@arrow@@QEAAXAEBVStatus@3@@Z; arrow::compute::KernelContext::SetStatus(arrow::Status const &)
0x1801d53e0  nop
0x1801d53e1  mov     rcx, [rsp+68h+var_40]; this
0x1801d53e6  test    rcx, rcx
0x1801d53e9  jz      short loc_1801D53F5
0x1801d53eb  mov     edx, 1; unsigned int
0x1801d53f0  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801d53f5  mov     qword ptr [rbx], 0
0x1801d53fc  mov     rax, rbx
0x1801d53ff  mov     rcx, [rsp+68h+var_10]
0x1801d5404  xor     rcx, rsp; StackCookie
0x1801d5407  call    __security_check_cookie
0x1801d540c  mov     rbx, [rsp+68h+arg_18]
0x1801d5414  add     rsp, 60h
0x1801d5418  pop     rdi
0x1801d5419  retn
0x1801d541a  call    _invalid_parameter_noinfo_noreturn
```
