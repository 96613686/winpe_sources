# Windows::UI::Input::Inking::InkPresenterStencilBase::_SetManipulationTransform(D2D1::Matrix3x2F const &)

- ea: `0x1800c3cc8`
- end: `0x1800c3d75`
- name: `?_SetManipulationTransform@InkPresenterStencilBase@Inking@Input@UI@Windows@@IEAAJAEBVMatrix3x2F@D2D1@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::InkPresenterStencilBase *__hidden this, const struct D2D1::Matrix3x2F *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800b44d0`
- `0x1800b7bd0`
- `0x1800b9e94`
- `0x1800bdb10`
- `0x1800c1640`
- `0x1800c1830`
- `0x1800c4480`

## callees

- `0x1800062a0`
- `0x1800c3cc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c3d4d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c3d4d`
- `d2d1!__imp_D2D1InvertMatrix` at `0x1800c3d0b`
- `d2d1!__imp_D2D1InvertMatrix` at `0x1800c3d0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c3d34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c3d34`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c3d5a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800c3d5a`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::InkPresenterStencilBase::_SetManipulationTransform(
        Windows::UI::Input::Inking::InkPresenterStencilBase *this,
        const struct D2D1::Matrix3x2F *a2)
{
  D2D1_MATRIX_3X2_F *v2; // rcx
  unsigned int v3; // ebx
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF

  *(_OWORD *)((char *)this + 268) = *(_OWORD *)a2;
  *(_QWORD *)((char *)this + 284) = *((_QWORD *)a2 + 2);
  v2 = (D2D1_MATRIX_3X2_F *)((char *)this + 292);
  *(_OWORD *)&v2->m11 = *(_OWORD *)a2;
  *(_QWORD *)&v2->m[2][0] = *((_QWORD *)a2 + 2);
  if ( D2D1InvertMatrix(v2) )
  {
    return 0;
  }
  else
  {
    v3 = -2147418113;
    if ( WindowsCreateStringReference(L"The specified transform is not invertible", 0x29u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    RoOriginateError(2147549183LL, string);
  }
  return v3;
}

```

## disassembly

```asm
0x1800c3cc8  push    rbx
0x1800c3cca  sub     rsp, 50h
0x1800c3cce  mov     rax, cs:__security_cookie
0x1800c3cd5  xor     rax, rsp
0x1800c3cd8  mov     [rsp+58h+var_18], rax
0x1800c3cdd  movups  xmm0, xmmword ptr [rdx]
0x1800c3ce0  movups  xmmword ptr [rcx+10Ch], xmm0
0x1800c3ce7  movsd   xmm1, qword ptr [rdx+10h]
0x1800c3cec  movsd   qword ptr [rcx+11Ch], xmm1
0x1800c3cf4  add     rcx, 124h; matrix
0x1800c3cfb  movups  xmm0, xmmword ptr [rdx]
0x1800c3cfe  movups  xmmword ptr [rcx], xmm0
0x1800c3d01  movsd   xmm1, qword ptr [rdx+10h]
0x1800c3d06  movsd   qword ptr [rcx+10h], xmm1
0x1800c3d0b  call    cs:__imp_D2D1InvertMatrix
0x1800c3d11  test    eax, eax
0x1800c3d13  jz      short loc_1800C3D19
0x1800c3d15  xor     ebx, ebx
0x1800c3d17  jmp     short loc_1800C3D60
0x1800c3d19  lea     r9, [rsp+58h+string]; string
0x1800c3d1e  mov     edx, 29h ; ')'; length
0x1800c3d23  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800c3d28  mov     ebx, 8000FFFFh
0x1800c3d2d  lea     rcx, aTheSpecifiedTr; "The specified transform is not invertib"...
0x1800c3d34  call    cs:__imp_WindowsCreateStringReference
0x1800c3d3a  test    eax, eax
0x1800c3d3c  jns     short loc_1800C3D53
0x1800c3d3e  xor     r9d, r9d; lpArguments
0x1800c3d41  xor     r8d, r8d; nNumberOfArguments
0x1800c3d44  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800c3d49  lea     edx, [r9+1]; dwExceptionFlags
0x1800c3d4d  call    cs:__imp_RaiseException
0x1800c3d53  mov     rdx, [rsp+58h+string]
0x1800c3d58  mov     ecx, ebx
0x1800c3d5a  call    cs:__imp_RoOriginateError
0x1800c3d60  mov     eax, ebx
0x1800c3d62  mov     rcx, [rsp+58h+var_18]
0x1800c3d67  xor     rcx, rsp; StackCookie
0x1800c3d6a  call    __security_check_cookie
0x1800c3d6f  add     rsp, 50h
0x1800c3d73  pop     rbx
0x1800c3d74  retn
```
