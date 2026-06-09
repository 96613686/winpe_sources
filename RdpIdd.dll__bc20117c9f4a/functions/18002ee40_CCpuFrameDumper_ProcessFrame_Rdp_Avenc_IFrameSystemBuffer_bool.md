# CCpuFrameDumper::ProcessFrame(Rdp::Avenc::IFrameSystemBuffer &,bool *)

- ea: `0x18002ee40`
- end: `0x18002f0a9`
- name: `?ProcessFrame@CCpuFrameDumper@@UEAAJAEAUIFrameSystemBuffer@Avenc@Rdp@@PEA_N@Z`
- size: `617`
- prototype: `__int64 __fastcall(CCpuFrameDumper *__hidden this, struct Rdp::Avenc::IFrameSystemBuffer *, bool *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006f60`
- `0x18000ead8`
- `0x1800107ec`
- `0x18001ddf4`
- `0x18002e860`
- `0x18002ead0`
- `0x18002eb30`
- `0x18002ee40`
- `0x18003f010`

## string_xrefs

- `0x18002efb8`: `CreateBitmapFromMemory failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CCpuFrameDumper::ProcessFrame(
        CCpuFrameDumper *this,
        struct Rdp::Avenc::IFrameSystemBuffer *a2,
        bool *a3,
        const char *a4)
{
  bool *v4; // rsi
  struct Rdp::Avenc::IFrameSystemBuffer *v5; // rbx
  CCpuFrameDumper *v6; // rdi
  int v7; // r13d
  __int64 v8; // r14
  unsigned int v9; // eax
  enum DXGI_FORMAT v10; // edx
  const struct _GUID *v11; // r15
  unsigned int v12; // r12d
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 FileName; // rax
  __int64 result; // rax
  const char *v17; // r9
  char *v18; // [rsp+28h] [rbp-110h]
  int v19; // [rsp+50h] [rbp-E8h]
  __int64 v20; // [rsp+58h] [rbp-E0h] BYREF
  int v21; // [rsp+60h] [rbp-D8h]
  _QWORD *v22; // [rsp+68h] [rbp-D0h]
  __int64 v23; // [rsp+70h] [rbp-C8h]
  CCpuFrameDumper *v24; // [rsp+78h] [rbp-C0h]
  bool *v25; // [rsp+80h] [rbp-B8h]
  struct Rdp::Avenc::IFrameSystemBuffer *v26; // [rsp+88h] [rbp-B0h]
  _QWORD v27[8]; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v28[32]; // [rsp+D0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  try
  {
    try
    {
      v4 = a3;
      v5 = a2;
      v6 = this;
      v24 = this;
      v26 = a2;
      v25 = a3;
      if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 5) + 232LL) + 505LL) )
      {
        v20 = 0;
        v7 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameSystemBuffer *))(*(_QWORD *)a2 + 152LL))(a2);
        v21 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameSystemBuffer *))(*(_QWORD *)v5 + 168LL))(v5);
        v8 = *((_QWORD *)v6 + 3);
        v22 = *(_QWORD **)(*(_QWORD *)v8 + 160LL);
        v20 = 0;
        v23 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameSystemBuffer *))(*(_QWORD *)v5 + 184LL))(v5);
        v19 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameSystemBuffer *))(*(_QWORD *)v5 + 152LL))(v5);
        v9 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameSystemBuffer *))(*(_QWORD *)v5 + 176LL))(v5);
        v11 = Rdp::Utils::Graphics::DxgiFormat2WICPixelFormat((Rdp::Utils::Graphics *)v9, v10);
        v12 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameSystemBuffer *))(*(_QWORD *)v5 + 168LL))(v5);
        v13 = (*(__int64 (__fastcall **)(struct Rdp::Avenc::IFrameSystemBuffer *))(*(_QWORD *)v5 + 160LL))(v5);
        v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, const struct _GUID *, int, int, __int64, __int64 *))v22)(
                v8,
                v13,
                v12,
                v11,
                v19,
                v21 * v7,
                v23,
                &v20);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0xBD,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
          (const char *)v14,
          (int)"CreateBitmapFromMemory failed",
          v18);
        v22 = v27;
        v27[0] = off_180040F90;
        v27[1] = &v20;
        v27[7] = v27;
        FileName = CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::GetFileName(v6, v28, v5);
        CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::Dump((__int64)v6, FileName, (__int64)v27);
        std::wstring::_Tidy_deallocate(v28);
        wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v20);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
        a4);
      v6 = v24;
      v4 = v25;
      v5 = v26;
    }
    result = (*(__int64 (__fastcall **)(_QWORD, struct Rdp::Avenc::IFrameSystemBuffer *, bool *))(**((_QWORD **)v6 + 4)
                                                                                                + 64LL))(
               *((_QWORD *)v6 + 4),
               v5,
               v4);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xCF,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x18002ee40  push    rbx
0x18002ee42  push    rsi
0x18002ee43  push    rdi
0x18002ee44  push    r12
0x18002ee46  push    r13
0x18002ee48  push    r14
0x18002ee4a  push    r15
0x18002ee4c  sub     rsp, 100h
0x18002ee53  mov     rax, cs:__security_cookie
0x18002ee5a  xor     rax, rsp
0x18002ee5d  mov     [rsp+138h+var_48], rax
0x18002ee65  mov     rsi, r8
0x18002ee68  mov     rbx, rdx
0x18002ee6b  mov     rdi, rcx
0x18002ee6e  mov     [rsp+138h+var_C0], rcx
0x18002ee73  mov     [rsp+138h+var_B0], rdx
0x18002ee7b  mov     [rsp+138h+var_B8], r8
0x18002ee83  mov     rax, [rcx+28h]
0x18002ee87  mov     rdx, [rax+0E8h]
0x18002ee8e  mov     al, [rdx+1F9h]
0x18002ee94  nop
0x18002ee95  test    al, al
0x18002ee97  jz      loc_18002F069
0x18002ee9d  mov     [rsp+138h+var_E0], 0
0x18002eea6  mov     rax, [rbx]
0x18002eea9  mov     rcx, rbx
0x18002eeac  mov     rax, [rax+98h]
0x18002eeb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeb8  mov     r13d, eax
0x18002eebb  mov     rcx, [rbx]
0x18002eebe  mov     rax, [rcx+0A8h]
0x18002eec5  mov     rcx, rbx
0x18002eec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eecd  mov     [rsp+138h+var_D8], eax
0x18002eed1  mov     r14, [rdi+18h]
0x18002eed5  mov     rcx, [r14]
0x18002eed8  mov     rax, [rcx+0A0h]
0x18002eedf  mov     [rsp+138h+var_D0], rax
0x18002eee4  mov     rcx, [rsp+138h+var_E0]
0x18002eee9  mov     [rsp+138h+var_E0], 0
0x18002eef2  test    rcx, rcx
0x18002eef5  jz      short loc_18002EF04
0x18002eef7  mov     rax, [rcx]
0x18002eefa  mov     rax, [rax+10h]
0x18002eefe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef03  nop
0x18002ef04  mov     rax, [rbx]
0x18002ef07  mov     rcx, rbx
0x18002ef0a  mov     rax, [rax+0B8h]
0x18002ef11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef16  mov     [rsp+138h+var_C8], rax
0x18002ef1b  mov     rcx, [rbx]
0x18002ef1e  mov     rax, [rcx+98h]
0x18002ef25  mov     rcx, rbx
0x18002ef28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef2d  mov     [rsp+138h+var_E8], eax
0x18002ef31  mov     rcx, [rbx]
0x18002ef34  mov     rax, [rcx+0B0h]
0x18002ef3b  mov     rcx, rbx
0x18002ef3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef43  mov     ecx, eax; this
0x18002ef45  call    ?DxgiFormat2WICPixelFormat@Graphics@Utils@Rdp@@YAAEBU_GUID@@W4DXGI_FORMAT@@@Z; Rdp::Utils::Graphics::DxgiFormat2WICPixelFormat(DXGI_FORMAT)
0x18002ef4a  mov     r15, rax
0x18002ef4d  mov     rcx, [rbx]
0x18002ef50  mov     rax, [rcx+0A8h]
0x18002ef57  mov     rcx, rbx
0x18002ef5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef5f  mov     r12d, eax
0x18002ef62  mov     rcx, [rbx]
0x18002ef65  mov     rax, [rcx+0A0h]
0x18002ef6c  mov     rcx, rbx
0x18002ef6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef74  imul    r13d, [rsp+138h+var_D8]
0x18002ef7a  lea     rcx, [rsp+138h+var_E0]
0x18002ef7f  mov     [rsp+138h+var_100], rcx
0x18002ef84  mov     rcx, [rsp+138h+var_C8]
0x18002ef89  mov     [rsp+138h+var_108], rcx
0x18002ef8e  mov     dword ptr [rsp+138h+var_110], r13d; char *
0x18002ef93  mov     ecx, [rsp+138h+var_E8]
0x18002ef97  mov     [rsp+138h+var_118], ecx
0x18002ef9b  mov     r9, r15
0x18002ef9e  mov     r8d, r12d
0x18002efa1  mov     edx, eax
0x18002efa3  mov     rcx, r14
0x18002efa6  mov     rax, [rsp+138h+var_D0]
0x18002efab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efb0  mov     rcx, [rsp+138h]; this
0x18002efb8  lea     rdx, aCreatebitmapfr; "CreateBitmapFromMemory failed"
0x18002efbf  mov     qword ptr [rsp+138h+var_118], rdx; int
0x18002efc4  mov     r9d, eax; char *
0x18002efc7  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002efce  mov     edx, 0BDh; void *
0x18002efd3  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002efd8  lea     rax, [rsp+138h+var_A8]
0x18002efe0  mov     [rsp+138h+var_D0], rax
0x18002efe5  lea     rax, off_180040F90
0x18002efec  mov     [rsp+138h+var_A8], rax
0x18002eff4  lea     rax, [rsp+138h+var_E0]
0x18002eff9  mov     [rsp+138h+var_A0], rax
0x18002f001  lea     rax, [rsp+138h+var_A8]
0x18002f009  mov     [rsp+138h+var_70], rax
0x18002f011  mov     r8, rbx
0x18002f014  lea     rdx, [rsp+138h+var_68]
0x18002f01c  mov     rcx, rdi
0x18002f01f  call    ?GetFileName@?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUIFrameBuffer@Avenc@Rdp@@@Z; CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::GetFileName(Rdp::Avenc::IFrameBuffer &)
0x18002f024  nop
0x18002f025  lea     r8, [rsp+138h+var_A8]
0x18002f02d  mov     rdx, rax
0x18002f030  mov     rcx, rdi
0x18002f033  call    ?Dump@?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$function@$$A6AXPEAUIWICBitmapFrameEncode@@@Z@3@@Z; CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::Dump(std::wstring const &,std::function<void (IWICBitmapFrameEncode *)>)
0x18002f038  nop
0x18002f039  lea     rcx, [rsp+138h+var_68]
0x18002f041  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002f046  nop
0x18002f047  lea     rcx, [rsp+138h+var_E0]
0x18002f04c  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002f051  nop
0x18002f052  jmp     short loc_18002F069
0x18002f054  mov     rdi, [rsp+138h+var_C0]
0x18002f059  mov     rsi, [rsp+138h+var_B8]
0x18002f061  mov     rbx, [rsp+138h+var_B0]
0x18002f069  mov     rcx, [rdi+20h]
0x18002f06d  mov     rax, [rcx]
0x18002f070  mov     r8, rsi
0x18002f073  mov     rdx, rbx
0x18002f076  mov     rax, [rax+40h]
0x18002f07a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f07f  jmp     short loc_18002F085
0x18002f081  mov     eax, [rsp+138h+var_E8]
0x18002f085  mov     rcx, [rsp+138h+var_48]
0x18002f08d  xor     rcx, rsp; StackCookie
0x18002f090  call    __security_check_cookie
0x18002f095  add     rsp, 100h
0x18002f09c  pop     r15
0x18002f09e  pop     r14
0x18002f0a0  pop     r13
0x18002f0a2  pop     r12
0x18002f0a4  pop     rdi
0x18002f0a5  pop     rsi
0x18002f0a6  pop     rbx
0x18002f0a7  retn
```
