# _CGpuFrameDumper::ProcessFrame_::_7_::_lambda_1_::operator()

- ea: `0x18002e6dc`
- end: `0x18002e79b`
- name: `_CGpuFrameDumper::ProcessFrame_::_7_::_lambda_1_::operator()`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f900`

## callees

- `0x18000ead8`
- `0x18001ddf4`
- `0x18003f010`

## string_xrefs

- `0x18002e721`: `CreateImageEncoder failed`
- `0x18002e764`: `imageEncoder->WriteFrame failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGpuFrameDumper::ProcessFrame_::_7_::_lambda_1_::operator()(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 *v5; // rcx
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  const char *v10; // [rsp+28h] [rbp-10h]
  const char *v11; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = 0;
  v4 = *a1;
  v5 = *(__int64 **)(*a1 + 24);
  v6 = *v5;
  v13 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v6 + 224))(v5, *(_QWORD *)(v4 + 104), &v13);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x185,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v7,
    (int)"CreateImageEncoder failed",
    v10);
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v13 + 24LL))(
         v13,
         *(_QWORD *)a1[1],
         a2,
         0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x18C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)v8,
    (int)"imageEncoder->WriteFrame failed",
    v11);
  return wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v13);
}

```

## disassembly

```asm
0x18002e6dc  mov     r11, rsp
0x18002e6df  mov     [r11+10h], rbx
0x18002e6e3  push    rdi
0x18002e6e4  sub     rsp, 30h
0x18002e6e8  mov     rdi, rdx
0x18002e6eb  mov     rbx, rcx
0x18002e6ee  mov     qword ptr [r11+8], 0
0x18002e6f6  mov     rdx, [rcx]
0x18002e6f9  mov     rcx, [rdx+18h]
0x18002e6fd  mov     rax, [rcx]
0x18002e700  mov     qword ptr [r11+8], 0
0x18002e708  lea     r8, [r11+8]
0x18002e70c  mov     rdx, [rdx+68h]
0x18002e710  mov     rax, [rax+0E0h]
0x18002e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e71c  mov     rcx, [rsp+38h]; this
0x18002e721  lea     rdx, aCreateimageenc; "CreateImageEncoder failed"
0x18002e728  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18002e72d  mov     r9d, eax; char *
0x18002e730  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002e737  mov     edx, 185h; void *
0x18002e73c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e741  mov     rcx, [rsp+38h+arg_0]
0x18002e746  mov     rax, [rcx]
0x18002e749  mov     rdx, [rbx+8]
0x18002e74d  xor     r9d, r9d
0x18002e750  mov     r8, rdi
0x18002e753  mov     rdx, [rdx]
0x18002e756  mov     rax, [rax+18h]
0x18002e75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e75f  mov     rcx, [rsp+38h]; this
0x18002e764  lea     rdx, aImageencoderWr; "imageEncoder->WriteFrame failed"
0x18002e76b  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18002e770  mov     r9d, eax; char *
0x18002e773  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002e77a  mov     edx, 18Ch; void *
0x18002e77f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e784  nop
0x18002e785  lea     rcx, [rsp+38h+arg_0]
0x18002e78a  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x18002e78f  mov     rbx, [rsp+38h+arg_8]
0x18002e794  add     rsp, 30h
0x18002e798  pop     rdi
0x18002e799  retn
```
