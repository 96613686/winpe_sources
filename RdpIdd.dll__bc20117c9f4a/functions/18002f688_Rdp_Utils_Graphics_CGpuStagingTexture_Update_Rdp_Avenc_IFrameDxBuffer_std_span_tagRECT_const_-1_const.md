# Rdp::Utils::Graphics::CGpuStagingTexture::Update(Rdp::Avenc::IFrameDxBuffer &,std::span<tagRECT const,-1> const &)

- ea: `0x18002f688`
- end: `0x18002f823`
- name: `?Update@CGpuStagingTexture@Graphics@Utils@Rdp@@QEAAXAEAUIFrameDxBuffer@Avenc@4@AEBV?$span@$$CBUtagRECT@@$0?0@std@@@Z`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f0b0`

## callees

- `0x180006f60`
- `0x18000ead8`
- `0x18001dd50`
- `0x18002e3ec`
- `0x18002f688`
- `0x18003f010`

## string_xrefs

- `0x18002f811`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Utils::Graphics::CGpuStagingTexture::Update(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rbx
  void (__fastcall *v8)(__int64, __int64 *); // rdi
  _DWORD *v9; // rbx
  __int64 v10; // rdi
  int v12; // [rsp+20h] [rbp-39h]
  __int64 v13; // [rsp+50h] [rbp-9h] BYREF
  __int64 v14; // [rsp+58h] [rbp-1h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp+7h] BYREF
  __int64 v16; // [rsp+68h] [rbp+Fh]
  int v17; // [rsp+70h] [rbp+17h]
  int v18; // [rsp+74h] [rbp+1Bh]
  int v19; // [rsp+78h] [rbp+1Fh]
  int v20; // [rsp+7Ch] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 152LL))(a2);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v15, v5);
  v13 = 0;
  v14 = 0;
  if ( v15 )
  {
    v6 = (**v15)(v15, &GUID_dc8e63f3_d12b_4952_b47b_5e45026a862d, &v14);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
        (const char *)(unsigned int)v6,
        v12);
  }
  else
  {
    v14 = 0;
  }
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 320LL);
  v13 = 0;
  v8(v7, &v13);
  v9 = *(_DWORD **)a3;
  v10 = *(_QWORD *)a3 + 16LL * *(_QWORD *)(a3 + 8);
  while ( v9 != (_DWORD *)v10 )
  {
    v16 = 0;
    v17 = 0;
    LODWORD(v16) = *v9;
    v18 = v9[2];
    HIDWORD(v16) = v9[1];
    v19 = v9[3];
    v20 = 1;
    (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v13 + 368LL))(v13, *(_QWORD *)(a1 + 24), 0);
    v9 += 4;
  }
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v13);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v14);
  return wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v15);
}

```

## disassembly

```asm
0x18002f688  push    rbp
0x18002f68a  push    rbx
0x18002f68b  push    rsi
0x18002f68c  push    rdi
0x18002f68d  push    r14
0x18002f68f  lea     rbp, [rsp-37h]
0x18002f694  sub     rsp, 90h
0x18002f69b  mov     rax, cs:__security_cookie
0x18002f6a2  xor     rax, rsp
0x18002f6a5  mov     [rbp+57h+var_30], rax
0x18002f6a9  mov     r14, r8
0x18002f6ac  mov     rsi, rcx
0x18002f6af  mov     rax, [rdx]
0x18002f6b2  mov     rcx, rdx
0x18002f6b5  mov     rax, [rax+98h]
0x18002f6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6c1  mov     rdx, rax
0x18002f6c4  lea     rcx, [rbp+57h+var_50]
0x18002f6c8  call    ??0?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIDXGIResource@@@Z; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::com_ptr_t<IDXGIResource,wil::err_exception_policy>(IDXGIResource *)
0x18002f6cd  nop
0x18002f6ce  xor     ecx, ecx
0x18002f6d0  mov     [rbp+57h+var_60], rcx
0x18002f6d4  mov     [rbp+57h+var_58], rcx
0x18002f6d8  mov     r9, [rbp+57h+var_50]
0x18002f6dc  test    r9, r9
0x18002f6df  jz      short loc_18002F70C
0x18002f6e1  mov     rax, [r9]
0x18002f6e4  lea     r8, [rbp+57h+var_58]
0x18002f6e8  lea     rdx, _GUID_dc8e63f3_d12b_4952_b47b_5e45026a862d
0x18002f6ef  mov     rcx, r9
0x18002f6f2  mov     rax, [rax]
0x18002f6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6fa  mov     rcx, [rbp+5Fh]; this
0x18002f6fe  test    eax, eax
0x18002f700  js      loc_18002F80E
0x18002f706  mov     rcx, [rbp+57h+var_60]
0x18002f70a  jmp     short loc_18002F714
0x18002f70c  mov     [rbp+57h+var_58], 0
0x18002f714  mov     rbx, [rsi+10h]
0x18002f718  mov     rax, [rbx]
0x18002f71b  mov     rdi, [rax+140h]
0x18002f722  mov     [rbp+57h+var_60], 0
0x18002f72a  test    rcx, rcx
0x18002f72d  jz      short loc_18002F73C
0x18002f72f  mov     rdx, [rcx]
0x18002f732  mov     rax, [rdx+10h]
0x18002f736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f73b  nop
0x18002f73c  lea     rdx, [rbp+57h+var_60]
0x18002f740  mov     rcx, rbx
0x18002f743  mov     rax, rdi
0x18002f746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f74b  mov     rbx, [r14]
0x18002f74e  mov     rdi, [r14+8]
0x18002f752  shl     rdi, 4
0x18002f756  add     rdi, rbx
0x18002f759  jmp     short loc_18002F7D1
0x18002f75b  mov     [rbp+57h+var_48], 0
0x18002f763  mov     [rbp+57h+var_40], 0
0x18002f76a  mov     r9d, [rbx]
0x18002f76d  mov     dword ptr [rbp+57h+var_48], r9d
0x18002f771  mov     eax, [rbx+8]
0x18002f774  mov     [rbp+57h+var_3C], eax
0x18002f777  mov     r8d, [rbx+4]
0x18002f77b  mov     dword ptr [rbp+57h+var_48+4], r8d
0x18002f77f  mov     eax, [rbx+0Ch]
0x18002f782  mov     [rbp+57h+var_38], eax
0x18002f785  mov     [rbp+57h+var_34], 1
0x18002f78c  mov     rcx, [rbp+57h+var_60]
0x18002f790  mov     rax, [rcx]
0x18002f793  lea     rdx, [rbp+57h+var_48]
0x18002f797  mov     [rsp+0B0h+var_70], rdx
0x18002f79c  mov     [rsp+0B0h+var_78], 0
0x18002f7a4  mov     rdx, [rbp+57h+var_58]
0x18002f7a8  mov     [rsp+0B0h+var_80], rdx
0x18002f7ad  mov     [rsp+0B0h+var_88], 0
0x18002f7b5  mov     [rsp+0B0h+var_90], r8d
0x18002f7ba  xor     r8d, r8d
0x18002f7bd  mov     rdx, [rsi+18h]
0x18002f7c1  mov     rax, [rax+170h]
0x18002f7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7cd  add     rbx, 10h
0x18002f7d1  cmp     rbx, rdi
0x18002f7d4  jnz     short loc_18002F75B
0x18002f7d6  lea     rcx, [rbp+57h+var_60]
0x18002f7da  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f7df  nop
0x18002f7e0  lea     rcx, [rbp+57h+var_58]
0x18002f7e4  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f7e9  nop
0x18002f7ea  lea     rcx, [rbp+57h+var_50]
0x18002f7ee  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f7f3  mov     rcx, [rbp+57h+var_30]
0x18002f7f7  xor     rcx, rsp; StackCookie
0x18002f7fa  call    __security_check_cookie
0x18002f7ff  add     rsp, 90h
0x18002f806  pop     r14
0x18002f808  pop     rdi
0x18002f809  pop     rsi
0x18002f80a  pop     rbx
0x18002f80b  pop     rbp
0x18002f80c  retn
0x18002f80e  mov     r9d, eax; char *
0x18002f811  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f818  mov     edx, 1CBEh; void *
0x18002f81d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
