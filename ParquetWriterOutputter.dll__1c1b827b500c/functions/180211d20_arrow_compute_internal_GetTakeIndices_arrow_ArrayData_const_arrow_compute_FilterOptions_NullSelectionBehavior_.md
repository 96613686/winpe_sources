# arrow::compute::internal::GetTakeIndices(arrow::ArrayData const &,arrow::compute::FilterOptions::NullSelectionBehavior,arrow::MemoryPool *)

- ea: `0x180211d20`
- end: `0x180211f3f`
- name: `?GetTakeIndices@internal@compute@arrow@@YA?AV?$Result@V?$shared_ptr@UArrayData@arrow@@@std@@@3@AEBUArrayData@3@W4NullSelectionBehavior@FilterOptions@23@PEAVMemoryPool@3@@Z`
- size: `543`
- prototype: `__int64 __fastcall(arrow::Status *this)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18020fa50`
- `0x1802153e0`

## callees

- `0x18001f8c0`
- `0x180086ed0`
- `0x18009a010`
- `0x18009a530`
- `0x1800a2670`
- `0x1800fab50`
- `0x1801f0cc0`
- `0x1801f16e0`
- `0x180211d20`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x180211e8b`: `Filter length exceeds UINT32_MAX, consider a different strategy for selecting elements`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
arrow::Status *__fastcall arrow::compute::internal::GetTakeIndices(arrow::Status *this, __int64 a2)
{
  __int64 v3; // rax
  const struct arrow::Status *v4; // rax
  const struct arrow::Status *v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  arrow::Status::State *v8; // rcx
  volatile signed __int32 *v9; // rdi
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  _BYTE *v14; // rcx
  _QWORD v16[3]; // [rsp+20h] [rbp-98h] BYREF
  _BYTE *v17; // [rsp+38h] [rbp-80h] BYREF
  __m128i si128; // [rsp+48h] [rbp-70h]
  char v19[8]; // [rsp+58h] [rbp-60h] BYREF
  arrow::Status::State *v20; // [rsp+60h] [rbp-58h]
  volatile signed __int32 *v21; // [rsp+70h] [rbp-48h]
  char v22[8]; // [rsp+78h] [rbp-40h] BYREF
  arrow::Status::State *v23; // [rsp+80h] [rbp-38h]
  volatile signed __int32 *v24; // [rsp+90h] [rbp-28h]

  v16[2] = -2;
  v16[0] = this;
  v3 = *(_QWORD *)(a2 + 16);
  if ( v3 <= 0xFFFF )
  {
    v4 = (const struct arrow::Status *)arrow::compute::internal::GetTakeIndicesImpl<arrow::UInt16Type>(v19);
    v5 = v4;
    *((_QWORD *)this + 1) = 0;
    if ( *((_QWORD *)v4 + 1) )
    {
      arrow::Status::CopyFrom(this, v4);
    }
    else
    {
      *((_QWORD *)this + 1) = 0;
      *((_QWORD *)v4 + 1) = 0;
      v6 = *((_QWORD *)v4 + 2);
      v7 = *((_QWORD *)v4 + 3);
      *((_QWORD *)v5 + 2) = 0;
      *((_QWORD *)v5 + 3) = 0;
      *((_QWORD *)this + 2) = v6;
      *((_QWORD *)this + 3) = v7;
    }
    v8 = v20;
    if ( v20 )
      goto LABEL_24;
    v9 = v21;
    if ( !v21 )
      return this;
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
    v8 = v20;
    goto LABEL_23;
  }
  if ( v3 > 0xFFFFFFFFLL )
  {
    v11 = arrow::util::StringBuilder<char const (&)[13]>(
            &v17,
            "Filter length exceeds UINT32_MAX, consider a different strategy for selecting elements");
    LOBYTE(v12) = 10;
    arrow::Status::Status(v16, v12, v11);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v13 = si128.m128i_i64[1] + 1;
      v14 = v17;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v13 = si128.m128i_i64[1] + 40;
        v14 = (_BYTE *)*((_QWORD *)v17 - 1);
        if ( (unsigned __int64)(v17 - v14 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v14, v13);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v17) = 0;
    arrow::Result<std::shared_ptr<arrow::ArrayData>>::Result<std::shared_ptr<arrow::ArrayData>>(this, v16);
    v8 = (arrow::Status::State *)v16[1];
LABEL_23:
    if ( v8 )
      goto LABEL_24;
    return this;
  }
  arrow::compute::internal::GetTakeIndicesImpl<arrow::UInt32Type>(v22);
  arrow::Result<std::shared_ptr<arrow::StructArray>>::Result<std::shared_ptr<arrow::StructArray>>(this);
  v8 = v23;
  if ( v23 )
  {
LABEL_24:
    arrow::Status::State::`scalar deleting destructor'(v8, 1u);
    return this;
  }
  v10 = v24;
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    v8 = v23;
    goto LABEL_23;
  }
  return this;
}

```

## disassembly

```asm
0x180211d20  push    rbx
0x180211d22  push    rsi
0x180211d23  push    rdi
0x180211d24  sub     rsp, 0A0h
0x180211d2b  mov     [rsp+0B8h+var_88], 0FFFFFFFFFFFFFFFEh
0x180211d34  mov     rax, cs:__security_cookie
0x180211d3b  xor     rax, rsp
0x180211d3e  mov     [rsp+0B8h+var_20], rax
0x180211d46  mov     rsi, rcx
0x180211d49  mov     [rsp+0B8h+var_98], rcx
0x180211d4e  mov     rax, [rdx+10h]
0x180211d52  cmp     rax, 0FFFFh
0x180211d58  jg      loc_180211E03
0x180211d5e  lea     rcx, [rsp+0B8h+var_60]
0x180211d63  call    ??$GetTakeIndicesImpl@VUInt16Type@arrow@@@internal@compute@arrow@@YA?AV?$Result@V?$shared_ptr@UArrayData@arrow@@@std@@@2@AEBUArrayData@2@W4NullSelectionBehavior@FilterOptions@12@PEAVMemoryPool@2@@Z; arrow::compute::internal::GetTakeIndicesImpl<arrow::UInt16Type>(arrow::ArrayData const &,arrow::compute::FilterOptions::NullSelectionBehavior,arrow::MemoryPool *)
0x180211d68  mov     rdx, rax; struct arrow::Status *
0x180211d6b  xor     r8d, r8d
0x180211d6e  mov     [rsi+8], r8
0x180211d72  cmp     [rax+8], r8
0x180211d76  jnz     short loc_180211D9A
0x180211d78  mov     [rsi+8], r8
0x180211d7c  mov     [rax+8], r8
0x180211d80  mov     rcx, [rax+10h]
0x180211d84  mov     rax, [rax+18h]
0x180211d88  mov     [rdx+10h], r8
0x180211d8c  mov     [rdx+18h], r8
0x180211d90  mov     [rsi+10h], rcx
0x180211d94  mov     [rsi+18h], rax
0x180211d98  jmp     short loc_180211DA3
0x180211d9a  mov     rcx, rsi; this
0x180211d9d  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x180211da2  nop
0x180211da3  mov     rcx, [rsp+0B8h+var_58]
0x180211da8  test    rcx, rcx
0x180211dab  jnz     loc_180211F11
0x180211db1  mov     rdi, [rsp+0B8h+var_48]
0x180211db6  test    rdi, rdi
0x180211db9  jz      loc_180211F1B
0x180211dbf  mov     ebx, 0FFFFFFFFh
0x180211dc4  mov     eax, ebx
0x180211dc6  lock xadd [rdi+8], eax
0x180211dcb  cmp     eax, 1
0x180211dce  jnz     short loc_180211DF9
0x180211dd0  mov     rax, [rdi]
0x180211dd3  mov     rcx, rdi
0x180211dd6  mov     rax, [rax]
0x180211dd9  call    cs:__guard_dispatch_icall_fptr
0x180211ddf  lock xadd [rdi+0Ch], ebx
0x180211de4  cmp     ebx, 1
0x180211de7  jnz     short loc_180211DF9
0x180211de9  mov     rax, [rdi]
0x180211dec  mov     rcx, rdi
0x180211def  mov     rax, [rax+8]
0x180211df3  call    cs:__guard_dispatch_icall_fptr
0x180211df9  mov     rcx, [rsp+0B8h+var_58]
0x180211dfe  jmp     loc_180211F0C
0x180211e03  mov     ecx, 0FFFFFFFFh
0x180211e08  cmp     rax, rcx
0x180211e0b  jg      short loc_180211E8B
0x180211e0d  lea     rcx, [rsp+0B8h+var_40]
0x180211e12  call    ??$GetTakeIndicesImpl@VUInt32Type@arrow@@@internal@compute@arrow@@YA?AV?$Result@V?$shared_ptr@UArrayData@arrow@@@std@@@2@AEBUArrayData@2@W4NullSelectionBehavior@FilterOptions@12@PEAVMemoryPool@2@@Z; arrow::compute::internal::GetTakeIndicesImpl<arrow::UInt32Type>(arrow::ArrayData const &,arrow::compute::FilterOptions::NullSelectionBehavior,arrow::MemoryPool *)
0x180211e17  mov     rdx, rax
0x180211e1a  mov     rcx, rsi; this
0x180211e1d  call    ??$?0V?$shared_ptr@VStructArray@arrow@@@std@@X@?$Result@V?$shared_ptr@VStructArray@arrow@@@std@@@arrow@@QEAA@$$QEAV01@@Z; arrow::Result<std::shared_ptr<arrow::StructArray>>::Result<std::shared_ptr<arrow::StructArray>>(arrow::Result<std::shared_ptr<arrow::StructArray>> &&)
0x180211e22  mov     rcx, [rsp+0B8h+var_38]
0x180211e2a  test    rcx, rcx
0x180211e2d  jnz     loc_180211F11
0x180211e33  mov     rdi, [rsp+0B8h+var_28]
0x180211e3b  test    rdi, rdi
0x180211e3e  jz      loc_180211F1B
0x180211e44  mov     ebx, 0FFFFFFFFh
0x180211e49  mov     eax, ebx
0x180211e4b  lock xadd [rdi+8], eax
0x180211e50  cmp     eax, 1
0x180211e53  jnz     short loc_180211E7E
0x180211e55  mov     rax, [rdi]
0x180211e58  mov     rcx, rdi
0x180211e5b  mov     rax, [rax]
0x180211e5e  call    cs:__guard_dispatch_icall_fptr
0x180211e64  lock xadd [rdi+0Ch], ebx
0x180211e69  cmp     ebx, 1
0x180211e6c  jnz     short loc_180211E7E
0x180211e6e  mov     rax, [rdi]
0x180211e71  mov     rcx, rdi
0x180211e74  mov     rax, [rax+8]
0x180211e78  call    cs:__guard_dispatch_icall_fptr
0x180211e7e  mov     rcx, [rsp+0B8h+var_38]
0x180211e86  jmp     loc_180211F0C
0x180211e8b  lea     rdx, aFilterLengthEx; "Filter length exceeds UINT32_MAX, consi"...
0x180211e92  lea     rcx, [rsp+0B8h+var_80]
0x180211e97  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x180211e9c  nop
0x180211e9d  mov     r8, rax
0x180211ea0  mov     dl, 0Ah
0x180211ea2  lea     rcx, [rsp+0B8h+var_98]
0x180211ea7  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180211eac  nop
0x180211ead  mov     rdx, [rsp+0B8h+var_68]
0x180211eb2  cmp     rdx, 10h
0x180211eb6  jb      short loc_180211EE6
0x180211eb8  inc     rdx
0x180211ebb  mov     rcx, [rsp+0B8h+var_80]
0x180211ec0  mov     rax, rcx
0x180211ec3  cmp     rdx, 1000h
0x180211eca  jb      short loc_180211EE1
0x180211ecc  add     rdx, 27h ; '''; unsigned __int64
0x180211ed0  mov     rcx, [rcx-8]; void *
0x180211ed4  sub     rax, rcx
0x180211ed7  add     rax, 0FFFFFFFFFFFFFFF8h
0x180211edb  cmp     rax, 1Fh
0x180211edf  ja      short loc_180211F39
0x180211ee1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180211ee6  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180211eee  movdqu  xmmword ptr [rsp+48h], xmm0
0x180211ef4  mov     byte ptr [rsp+0B8h+var_80], 0
0x180211ef9  lea     rdx, [rsp+0B8h+var_98]
0x180211efe  mov     rcx, rsi
0x180211f01  call    ??0?$Result@V?$shared_ptr@UArrayData@arrow@@@std@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<std::shared_ptr<arrow::ArrayData>>::Result<std::shared_ptr<arrow::ArrayData>>(arrow::Status const &)
0x180211f06  nop
0x180211f07  mov     rcx, [rsp+0B8h+var_90]; this
0x180211f0c  test    rcx, rcx
0x180211f0f  jz      short loc_180211F1B
0x180211f11  mov     edx, 1; unsigned int
0x180211f16  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180211f1b  mov     rax, rsi
0x180211f1e  mov     rcx, [rsp+0B8h+var_20]
0x180211f26  xor     rcx, rsp; StackCookie
0x180211f29  call    __security_check_cookie
0x180211f2e  add     rsp, 0A0h
0x180211f35  pop     rdi
0x180211f36  pop     rsi
0x180211f37  pop     rbx
0x180211f38  retn
0x180211f39  call    _invalid_parameter_noinfo_noreturn
```
