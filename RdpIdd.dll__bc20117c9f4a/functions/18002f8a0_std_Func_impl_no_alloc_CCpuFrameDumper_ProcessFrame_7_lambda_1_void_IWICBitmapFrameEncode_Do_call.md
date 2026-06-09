# std::_Func_impl_no_alloc__CCpuFrameDumper::ProcessFrame_::_7_::_lambda_1__void_IWICBitmapFrameEncode___::_Do_call

- ea: `0x18002f8a0`
- end: `0x18002f8eb`
- name: `std::_Func_impl_no_alloc__CCpuFrameDumper::ProcessFrame_::_7_::_lambda_1__void_IWICBitmapFrameEncode___::_Do_call`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001ddf4`
- `0x18003f010`

## string_xrefs

- `0x18002f8c5`: `WicFrameEncode->WriteSource failed`

## pseudocode

```c
__int64 __fastcall std::_Func_impl_no_alloc__CCpuFrameDumper::ProcessFrame_::_7_::_lambda_1__void_IWICBitmapFrameEncode___::_Do_call(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v2; // eax
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*a2 + 88LL))(*a2, **(_QWORD **)(a1 + 8), 0);
  return wil::details::in1diag3::Throw_IfFailedMsg(
           retaddr,
           (void *)0xC7,
           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
           (const char *)v2,
           (int)"WicFrameEncode->WriteSource failed",
           v4);
}

```

## disassembly

```asm
0x18002f8a0  sub     rsp, 38h
0x18002f8a4  mov     r9, [rdx]
0x18002f8a7  xor     r8d, r8d
0x18002f8aa  mov     rdx, [rcx+8]
0x18002f8ae  mov     rcx, r9
0x18002f8b1  mov     rax, [r9]
0x18002f8b4  mov     rdx, [rdx]
0x18002f8b7  mov     rax, [rax+58h]
0x18002f8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8c0  mov     rcx, [rsp+38h]; this
0x18002f8c5  lea     rdx, aWicframeencode_0; "WicFrameEncode->WriteSource failed"
0x18002f8cc  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18002f8d1  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002f8d8  mov     edx, 0C7h; void *
0x18002f8dd  mov     r9d, eax; char *
0x18002f8e0  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002f8e5  add     rsp, 38h
0x18002f8e9  retn
```
