# arrow::util::internal::_anonymous_namespace_::BrotliCodec::MakeCompressor

- ea: `0x1800dff40`
- end: `0x1800e01a7`
- name: `arrow::util::internal::_anonymous_namespace_::BrotliCodec::MakeCompressor`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180042fd0`
- `0x180059010`
- `0x18009a010`
- `0x1800dff40`
- `0x180265910`
- `0x180265b90`
- `0x1802f0fb0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1800e0075`: `Brotli set compression level failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall arrow::util::internal::_anonymous_namespace_::BrotliCodec::MakeCompressor(__int64 a1, _QWORD *a2)
{
  char *v4; // rax
  char *v5; // rbx
  int v6; // eax
  __int64 Instance; // rax
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  _BYTE *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  const char *v15; // [rsp+20h] [rbp-98h] BYREF
  char v16[8]; // [rsp+28h] [rbp-90h] BYREF
  arrow::Status::State *v17; // [rsp+30h] [rbp-88h]
  const char *v18; // [rsp+38h] [rbp-80h] BYREF
  char v19[8]; // [rsp+40h] [rbp-78h] BYREF
  arrow::Status::State *v20; // [rsp+48h] [rbp-70h]
  __int64 v21; // [rsp+50h] [rbp-68h]
  char *v22; // [rsp+58h] [rbp-60h]
  char *v23; // [rsp+60h] [rbp-58h]
  _BYTE *v24; // [rsp+68h] [rbp-50h] BYREF
  unsigned __int64 v25; // [rsp+80h] [rbp-38h]
  _BYTE *v26; // [rsp+88h] [rbp-30h] BYREF
  unsigned __int64 v27; // [rsp+A0h] [rbp-18h]

  v21 = -2;
  v4 = (char *)operator new(0x28u);
  v5 = v4;
  v15 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 2) = 1;
    *((_DWORD *)v4 + 3) = 1;
    *(_QWORD *)v4 = std::_Ref_count_obj<arrow::util::internal::`anonymous namespace'::BrotliCompressor>::`vftable';
    v6 = *(_DWORD *)(a1 + 8);
    *((_QWORD *)v5 + 2) = &arrow::util::internal::`anonymous namespace'::BrotliCompressor::`vftable';
    *((_QWORD *)v5 + 3) = 0;
    *((_DWORD *)v5 + 8) = v6;
  }
  else
  {
    v5 = 0;
  }
  v22 = v5 + 16;
  v23 = v5;
  Instance = BrotliEncoderCreateInstance(0, 0, 0);
  *((_QWORD *)v5 + 3) = Instance;
  if ( !Instance )
  {
    v18 = "Brotli init failed";
    v8 = arrow::util::StringBuilder<char const *>(&v24, &v18);
    LOBYTE(v9) = 5;
    arrow::Status::Status(v16, v9, v8);
    if ( v25 < 0x10 )
      goto LABEL_15;
    v10 = v25 + 1;
    v11 = v24;
    if ( v25 + 1 >= 0x1000 )
    {
      v10 = v25 + 40;
      v11 = (_BYTE *)*((_QWORD *)v24 - 1);
      if ( (unsigned __int64)(v24 - v11 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    goto LABEL_8;
  }
  if ( (unsigned int)BrotliEncoderSetParameter(Instance, 1, *((unsigned int *)v5 + 8)) )
  {
    v17 = 0;
  }
  else
  {
    v15 = "Brotli set compression level failed";
    v12 = arrow::util::StringBuilder<char const *>(&v26, &v15);
    LOBYTE(v13) = 5;
    arrow::Status::Status(v16, v13, v12);
    if ( v27 >= 0x10 )
    {
      v10 = v27 + 1;
      v11 = v26;
      if ( v27 + 1 >= 0x1000 )
      {
        v10 = v27 + 40;
        v11 = (_BYTE *)*((_QWORD *)v26 - 1);
        if ( (unsigned __int64)(v26 - v11 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
LABEL_8:
      operator delete(v11, v10);
    }
  }
LABEL_15:
  v20 = v17;
  v17 = 0;
  if ( v20 )
  {
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v19);
    if ( v20 )
    {
      arrow::Status::State::`scalar deleting destructor'(v20, 1u);
      v20 = 0;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(char *))v5)(v5);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  else
  {
    a2[1] = 0;
    a2[2] = v5 + 16;
    a2[3] = v5;
  }
  return a2;
}

```

## disassembly

```asm
0x1800dff40  mov     rax, rsp
0x1800dff43  push    rdi
0x1800dff44  sub     rsp, 0B0h
0x1800dff4b  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x1800dff53  mov     [rax+8], rbx
0x1800dff57  mov     [rax+18h], rbp
0x1800dff5b  mov     [rax+20h], rsi
0x1800dff5f  mov     rax, cs:__security_cookie
0x1800dff66  xor     rax, rsp
0x1800dff69  mov     [rsp+0B8h+var_10], rax
0x1800dff71  mov     rdi, rdx
0x1800dff74  mov     rsi, rcx
0x1800dff77  mov     [rsp+0B8h+var_98], rdx
0x1800dff7c  mov     ecx, 28h ; '('; Size
0x1800dff81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dff86  mov     rbx, rax
0x1800dff89  mov     [rsp+0B8h+var_98], rax
0x1800dff8e  test    rax, rax
0x1800dff91  jz      short loc_1800DFFC4
0x1800dff93  mov     dword ptr [rax+8], 1
0x1800dff9a  mov     dword ptr [rax+0Ch], 1
0x1800dffa1  lea     rax, ??_7?$_Ref_count_obj@VBrotliCompressor@?A0xf9fe67e1@internal@util@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::util::internal::`anonymous namespace'::BrotliCompressor>::`vftable'
0x1800dffa8  mov     [rbx], rax
0x1800dffab  mov     eax, [rsi+8]
0x1800dffae  lea     rcx, ??_7BrotliCompressor@?A0xf9fe67e1@internal@util@arrow@@6B@; const arrow::util::internal::`anonymous namespace'::BrotliCompressor::`vftable'
0x1800dffb5  mov     [rbx+10h], rcx
0x1800dffb9  xor     esi, esi
0x1800dffbb  mov     [rbx+18h], rsi
0x1800dffbf  mov     [rbx+20h], eax
0x1800dffc2  jmp     short loc_1800DFFC8
0x1800dffc4  xor     esi, esi
0x1800dffc6  mov     ebx, esi
0x1800dffc8  lea     rbp, [rbx+10h]
0x1800dffcc  mov     [rsp+0B8h+var_60], rbp
0x1800dffd1  mov     [rsp+0B8h+var_58], rbx
0x1800dffd6  xor     r8d, r8d
0x1800dffd9  xor     edx, edx
0x1800dffdb  xor     ecx, ecx
0x1800dffdd  call    BrotliEncoderCreateInstance
0x1800dffe2  mov     [rbx+18h], rax
0x1800dffe6  test    rax, rax
0x1800dffe9  jnz     short loc_1800E0060
0x1800dffeb  lea     rax, aBrotliInitFail; "Brotli init failed"
0x1800dfff2  mov     [rsp+0B8h+var_80], rax
0x1800dfff7  lea     rdx, [rsp+0B8h+var_80]
0x1800dfffc  lea     rcx, [rsp+0B8h+var_50]
0x1800e0001  call    ??$StringBuilder@PEBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAPEBD@Z; arrow::util::StringBuilder<char const *>(char const * &&)
0x1800e0006  nop
0x1800e0007  mov     r8, rax
0x1800e000a  mov     dl, 5
0x1800e000c  lea     rcx, [rsp+0B8h+var_90]
0x1800e0011  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e0016  nop
0x1800e0017  mov     rdx, [rsp+0B8h+var_38]
0x1800e001f  cmp     rdx, 10h
0x1800e0023  jb      loc_1800E00EC
0x1800e0029  inc     rdx
0x1800e002c  mov     rcx, [rsp+0B8h+var_50]
0x1800e0031  mov     rax, rcx
0x1800e0034  cmp     rdx, 1000h
0x1800e003b  jb      short loc_1800E0056
0x1800e003d  add     rdx, 27h ; '''; unsigned __int64
0x1800e0041  mov     rcx, [rcx-8]; void *
0x1800e0045  sub     rax, rcx
0x1800e0048  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e004c  cmp     rax, 1Fh
0x1800e0050  ja      loc_1800E019B
0x1800e0056  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e005b  jmp     loc_1800E00EC
0x1800e0060  mov     r8d, [rbx+20h]
0x1800e0064  mov     edx, 1
0x1800e0069  mov     rcx, rax
0x1800e006c  call    BrotliEncoderSetParameter
0x1800e0071  test    eax, eax
0x1800e0073  jnz     short loc_1800E00E7
0x1800e0075  lea     rax, aBrotliSetCompr; "Brotli set compression level failed"
0x1800e007c  mov     [rsp+0B8h+var_98], rax
0x1800e0081  lea     rdx, [rsp+0B8h+var_98]
0x1800e0086  lea     rcx, [rsp+0B8h+var_30]
0x1800e008e  call    ??$StringBuilder@PEBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAPEBD@Z; arrow::util::StringBuilder<char const *>(char const * &&)
0x1800e0093  nop
0x1800e0094  mov     r8, rax
0x1800e0097  mov     dl, 5
0x1800e0099  lea     rcx, [rsp+0B8h+var_90]
0x1800e009e  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e00a3  nop
0x1800e00a4  mov     rdx, [rsp+0B8h+var_18]
0x1800e00ac  cmp     rdx, 10h
0x1800e00b0  jb      short loc_1800E00EC
0x1800e00b2  inc     rdx
0x1800e00b5  mov     rcx, [rsp+0B8h+var_30]
0x1800e00bd  mov     rax, rcx
0x1800e00c0  cmp     rdx, 1000h
0x1800e00c7  jb      short loc_1800E0056
0x1800e00c9  add     rdx, 27h ; '''
0x1800e00cd  mov     rcx, [rcx-8]
0x1800e00d1  sub     rax, rcx
0x1800e00d4  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e00d8  cmp     rax, 1Fh
0x1800e00dc  ja      loc_1800E01A1
0x1800e00e2  jmp     loc_1800E0056
0x1800e00e7  mov     [rsp+0B8h+var_88], rsi
0x1800e00ec  mov     rax, [rsp+0B8h+var_88]
0x1800e00f1  mov     [rsp+0B8h+var_70], rax
0x1800e00f6  mov     [rsp+0B8h+var_88], rsi
0x1800e00fb  test    rax, rax
0x1800e00fe  jz      short loc_1800E0163
0x1800e0100  lea     rdx, [rsp+0B8h+var_78]
0x1800e0105  mov     rcx, rdi
0x1800e0108  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e010d  nop
0x1800e010e  mov     rcx, [rsp+0B8h+var_70]; this
0x1800e0113  test    rcx, rcx
0x1800e0116  jz      short loc_1800E0127
0x1800e0118  mov     edx, 1; unsigned int
0x1800e011d  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e0122  mov     [rsp+0B8h+var_70], rsi
0x1800e0127  mov     esi, 0FFFFFFFFh
0x1800e012c  mov     eax, esi
0x1800e012e  lock xadd [rbx+8], eax
0x1800e0133  cmp     eax, 1
0x1800e0136  jnz     short loc_1800E016F
0x1800e0138  mov     rax, [rbx]
0x1800e013b  mov     rcx, rbx
0x1800e013e  mov     rax, [rax]
0x1800e0141  call    cs:__guard_dispatch_icall_fptr
0x1800e0147  lock xadd [rbx+0Ch], esi
0x1800e014c  cmp     esi, 1
0x1800e014f  jnz     short loc_1800E016F
0x1800e0151  mov     rdx, [rbx]
0x1800e0154  mov     rcx, rbx
0x1800e0157  mov     rax, [rdx+8]
0x1800e015b  call    cs:__guard_dispatch_icall_fptr
0x1800e0161  jmp     short loc_1800E016F
0x1800e0163  mov     [rdi+8], rsi
0x1800e0167  mov     [rdi+10h], rbp
0x1800e016b  mov     [rdi+18h], rbx
0x1800e016f  mov     rax, rdi
0x1800e0172  mov     rcx, [rsp+0B8h+var_10]
0x1800e017a  xor     rcx, rsp; StackCookie
0x1800e017d  call    __security_check_cookie
0x1800e0182  lea     r11, [rsp+0B8h+var_8]
0x1800e018a  mov     rbx, [r11+10h]
0x1800e018e  mov     rbp, [r11+20h]
0x1800e0192  mov     rsi, [r11+28h]
0x1800e0196  mov     rsp, r11
0x1800e0199  pop     rdi
0x1800e019a  retn
0x1800e019b  call    _invalid_parameter_noinfo_noreturn
0x1800e01a1  call    _invalid_parameter_noinfo_noreturn
```
