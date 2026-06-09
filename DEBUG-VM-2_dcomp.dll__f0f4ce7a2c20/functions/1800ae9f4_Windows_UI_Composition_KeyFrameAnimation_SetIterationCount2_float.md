# Windows::UI::Composition::KeyFrameAnimation::SetIterationCount2(float)

- ea: `0x1800ae9f4`
- end: `0x1800aea7e`
- name: `?SetIterationCount2@KeyFrameAnimation@Composition@UI@Windows@@QEAAJM@Z`
- size: `138`
- prototype: `__int64 __fastcall(Windows::UI::Composition::KeyFrameAnimation *__hidden this, float)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800ae8e0`
- `0x1800ae970`

## callees

- `0x1800ae9f4`
- `0x1800f6f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aea60`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800aea60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aea4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800aea4a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800aea71`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800aea71`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::KeyFrameAnimation::SetIterationCount2(
        Windows::UI::Composition::KeyFrameAnimation *this,
        float a2)
{
  HRESULT v3; // eax
  HSTRING_HEADER hstringHeader; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+38h] [rbp-20h] BYREF

  if ( a2 <= 0.0 )
  {
    string = 0;
    v3 = WindowsCreateStringReference(
           L"An invalid IterationCount is specified. It must be greater than 0.",
           0x42u,
           &hstringHeader,
           &string);
    if ( v3 < 0 )
    {
      RaiseException(v3, 1u, 0, 0);
      __debugbreak();
    }
    RoOriginateError(2147942487LL);
    return 2147942487LL;
  }
  else
  {
    *((float *)this + 122) = a2;
    return 0;
  }
}

```

## disassembly

```asm
0x1800ae9f4  sub     rsp, 58h
0x1800ae9f8  mov     rax, cs:__security_cookie
0x1800ae9ff  xor     rax, rsp
0x1800aea02  mov     [rsp+58h+var_18], rax
0x1800aea07  xorps   xmm0, xmm0
0x1800aea0a  comiss  xmm0, xmm1
0x1800aea0d  jnb     short loc_1800AEA2B
0x1800aea0f  movss   dword ptr [rcx+1E8h], xmm1
0x1800aea17  xor     eax, eax
0x1800aea19  mov     rcx, [rsp+58h+var_18]
0x1800aea1e  xor     rcx, rsp; StackCookie
0x1800aea21  call    __security_check_cookie
0x1800aea26  add     rsp, 58h
0x1800aea2a  retn
0x1800aea2b  lea     r9, [rsp+58h+string]; string
0x1800aea30  mov     [rsp+58h+string], 0
0x1800aea39  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800aea3e  mov     edx, 42h ; 'B'; length
0x1800aea43  lea     rcx, aAnInvalidItera; "An invalid IterationCount is specified."...
0x1800aea4a  call    cs:__imp_WindowsCreateStringReference
0x1800aea50  test    eax, eax
0x1800aea52  jns     short loc_1800AEA67
0x1800aea54  xor     r9d, r9d; lpArguments
0x1800aea57  xor     r8d, r8d; nNumberOfArguments
0x1800aea5a  mov     ecx, eax; dwExceptionCode
0x1800aea5c  lea     edx, [r9+1]; dwExceptionFlags
0x1800aea60  call    cs:__imp_RaiseException
0x1800aea66  int     3; Trap to Debugger
0x1800aea67  mov     rdx, [rsp+58h+string]
0x1800aea6c  mov     ecx, 80070057h
0x1800aea71  call    cs:__imp_RoOriginateError
0x1800aea77  mov     eax, 80070057h
0x1800aea7c  jmp     short loc_1800AEA19
```
