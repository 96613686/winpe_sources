# arrow::compute::internal::OptionsWrapper<arrow::compute::TakeOptions>::Init(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)

- ea: `0x180212150`
- end: `0x180212280`
- name: `?Init@?$OptionsWrapper@UTakeOptions@compute@arrow@@@internal@compute@arrow@@SA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@34@AEBUKernelInitArgs@34@@Z`
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
- `0x1801ffb30`
- `0x180212150`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1802121c5`: `Attempted to initialize KernelState from null FunctionOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall arrow::compute::internal::OptionsWrapper<arrow::compute::TakeOptions>::Init(
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
    v5 = (__int64 *)arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::TakeOptions>,arrow::compute::TakeOptions const &>(&v12);
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
0x180212150  push    rdi
0x180212152  sub     rsp, 60h
0x180212156  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x18021215f  mov     [rsp+68h+arg_18], rbx
0x180212167  mov     rax, cs:__security_cookie
0x18021216e  xor     rax, rsp
0x180212171  mov     [rsp+68h+var_10], rax
0x180212176  mov     rdi, rdx
0x180212179  mov     rbx, rcx
0x18021217c  mov     [rsp+68h+var_48], rcx
0x180212181  mov     rdx, [r8+10h]
0x180212185  test    rdx, rdx
0x180212188  jz      short loc_1802121C5
0x18021218a  lea     rcx, [rsp+68h+var_48]
0x18021218f  call    ??$make_unique@U?$OptionsWrapper@UTakeOptions@compute@arrow@@@internal@compute@arrow@@AEBUTakeOptions@34@@internal@arrow@@YA?AV?$unique_ptr@U?$OptionsWrapper@UTakeOptions@compute@arrow@@@internal@compute@arrow@@U?$default_delete@U?$OptionsWrapper@UTakeOptions@compute@arrow@@@internal@compute@arrow@@@std@@@std@@AEBUTakeOptions@compute@1@@Z; arrow::internal::make_unique<arrow::compute::internal::OptionsWrapper<arrow::compute::TakeOptions>,arrow::compute::TakeOptions const &>(arrow::compute::TakeOptions const &)
0x180212194  mov     rcx, [rax]
0x180212197  mov     qword ptr [rax], 0
0x18021219e  mov     [rbx], rcx
0x1802121a1  mov     rcx, [rsp+68h+var_48]
0x1802121a6  test    rcx, rcx
0x1802121a9  jz      loc_18021225C
0x1802121af  mov     rdx, [rcx]
0x1802121b2  mov     rax, [rdx]
0x1802121b5  mov     edx, 1
0x1802121ba  call    cs:__guard_dispatch_icall_fptr
0x1802121c0  jmp     loc_18021225C
0x1802121c5  lea     rdx, aAttemptedToIni; "Attempted to initialize KernelState fro"...
0x1802121cc  lea     rcx, [rsp+68h+var_30]
0x1802121d1  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1802121d6  nop
0x1802121d7  mov     r8, rax
0x1802121da  mov     dl, 4
0x1802121dc  lea     rcx, [rsp+68h+var_48]
0x1802121e1  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1802121e6  nop
0x1802121e7  mov     rdx, [rsp+68h+var_18]
0x1802121ec  cmp     rdx, 10h
0x1802121f0  jb      short loc_180212220
0x1802121f2  inc     rdx
0x1802121f5  mov     rcx, [rsp+68h+var_30]
0x1802121fa  mov     rax, rcx
0x1802121fd  cmp     rdx, 1000h
0x180212204  jb      short loc_18021221B
0x180212206  add     rdx, 27h ; '''; unsigned __int64
0x18021220a  mov     rcx, [rcx-8]; void *
0x18021220e  sub     rax, rcx
0x180212211  add     rax, 0FFFFFFFFFFFFFFF8h
0x180212215  cmp     rax, 1Fh
0x180212219  ja      short loc_18021227A
0x18021221b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180212220  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180212228  movdqu  xmmword ptr [rsp+48h], xmm0
0x18021222e  mov     byte ptr [rsp+68h+var_30], 0
0x180212233  lea     rdx, [rsp+68h+var_48]; struct arrow::Status *
0x180212238  mov     rcx, rdi; this
0x18021223b  call    ?SetStatus@KernelContext@compute@arrow@@QEAAXAEBVStatus@3@@Z; arrow::compute::KernelContext::SetStatus(arrow::Status const &)
0x180212240  nop
0x180212241  mov     rcx, [rsp+68h+var_40]; this
0x180212246  test    rcx, rcx
0x180212249  jz      short loc_180212255
0x18021224b  mov     edx, 1; unsigned int
0x180212250  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180212255  mov     qword ptr [rbx], 0
0x18021225c  mov     rax, rbx
0x18021225f  mov     rcx, [rsp+68h+var_10]
0x180212264  xor     rcx, rsp; StackCookie
0x180212267  call    __security_check_cookie
0x18021226c  mov     rbx, [rsp+68h+arg_18]
0x180212274  add     rsp, 60h
0x180212278  pop     rdi
0x180212279  retn
0x18021227a  call    _invalid_parameter_noinfo_noreturn
```
