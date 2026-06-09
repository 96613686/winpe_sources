# win_musl::CreateFiber_OrThrow<win_musl::FiberBase,&win_musl::FiberBase::FiberProc(void)>(win_musl::FiberBase *,unsigned __int64)

- ea: `0x180079f68`
- end: `0x180079ff7`
- name: `??$CreateFiber_OrThrow@VFiberBase@win_musl@@$1?FiberProc@12@AEAAXXZ@win_musl@@YAPEAXPEAVFiberBase@0@_K@Z`
- size: `143`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180078a60`
- `0x180079ccc`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x180079f68`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-fibers-l2-1-0!CreateFiber` at `0x180079f8d`
- `api-ms-win-core-fibers-l2-1-0!CreateFiber` at `0x180079f8d`

## string_xrefs

- `0x180079f9d`: `CreateFiber failed!`

## pseudocode

```c
LPVOID __fastcall win_musl::CreateFiber_OrThrow<win_musl::FiberBase,&private: void win_musl::FiberBase::FiberProc(void)>(
        LPVOID lpParameter)
{
  LPVOID result; // rax
  win_musl::detail *v2; // rcx
  unsigned int LastErrorAsFailHR; // eax
  _BYTE pExceptionObject[160]; // [rsp+40h] [rbp-B8h] BYREF

  result = CreateFiber(
             0,
             win_musl::win32_fiberproc<win_musl::FiberBase,&private: void win_musl::FiberBase::FiberProc(void)>::proc,
             lpParameter);
  if ( !result )
  {
    LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v2);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0xF6u,
      LastErrorAsFailHR,
      (struct win_musl::TStringEllipseBase *)L"CreateFiber failed!");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180079f68  sub     rsp, 0F8h
0x180079f6f  mov     rax, cs:__security_cookie
0x180079f76  xor     rax, rsp
0x180079f79  mov     [rsp+0F8h+var_18], rax
0x180079f81  mov     r8, rcx; lpParameter
0x180079f84  lea     rdx, ?proc@?$win32_fiberproc@VFiberBase@win_musl@@$1?FiberProc@12@AEAAXXZ@win_musl@@SAXPEAX@Z; lpStartAddress
0x180079f8b  xor     ecx, ecx; dwStackSize
0x180079f8d  call    cs:__imp_CreateFiber
0x180079f93  test    rax, rax
0x180079f96  jnz     short loc_180079FDF
0x180079f98  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x180079f9d  lea     rcx, aCreatefiberFai; "CreateFiber failed!"
0x180079fa4  mov     [rsp+0F8h+var_C8], rcx; struct win_musl::TStringEllipseBase *
0x180079fa9  lea     r9, word_18013A0B6
0x180079fb0  mov     [rsp+0F8h+var_D0], eax; unsigned int
0x180079fb4  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x180079fb9  lea     r8, aNoFilename; "(no filename)"
0x180079fc0  mov     [rsp+0F8h+var_D8], 0F6h; unsigned int
0x180079fc8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180079fcd  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180079fd4  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x180079fd9  call    _CxxThrowException_0
0x180079fdf  mov     rcx, [rsp+0F8h+var_18]
0x180079fe7  xor     rcx, rsp; StackCookie
0x180079fea  call    __security_check_cookie
0x180079fef  add     rsp, 0F8h
0x180079ff6  retn
```
