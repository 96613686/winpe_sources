# win_dox::NonCloneableStreamHolder::InnerStreamLocker::InnerStreamLocker(win_dox::NonCloneableStreamHolder *,win_dox::NonCloneableStreamHolder::MethodType)

- ea: `0x18004ec4c`
- end: `0x18004ed2c`
- name: `??0InnerStreamLocker@NonCloneableStreamHolder@win_dox@@QEAA@PEAV12@W4MethodType@12@@Z`
- size: `224`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x18004db44`
- `0x1800df870`
- `0x1800df8fc`
- `0x1800df990`
- `0x1800dfa8c`
- `0x1800dfaf0`
- `0x1800dfb80`
- `0x1800dfc00`

## callees

- `0x18004ec4c`
- `0x1800517a0`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004eca2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004eca2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ec8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ec8f`

## string_xrefs

- `0x18004ece6`: `Subsequent access to stream after failure not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall win_dox::NonCloneableStreamHolder::InnerStreamLocker::InnerStreamLocker(
        __int64 a1,
        __int64 a2,
        int a3)
{
  int v6; // ecx
  _BYTE pExceptionObject[160]; // [rsp+50h] [rbp-B8h] BYREF

  *(_QWORD *)a1 = a2 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  v6 = *(_DWORD *)(a2 + 52);
  *(_DWORD *)(a2 + 52) = v6 + 1;
  if ( !v6 )
    *(_DWORD *)(a2 + 48) = GetCurrentThreadId();
  *(_BYTE *)(a1 + 8) = a3 == 1;
  *(_QWORD *)(a1 + 16) = a2;
  if ( !*(_BYTE *)(a2 + 72) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Fu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Subsequent access to stream after failure not supported");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18004ec4c  mov     rax, rsp
0x18004ec4f  push    rdi
0x18004ec50  sub     rsp, 100h
0x18004ec57  mov     [rsp+108h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18004ec60  mov     [rax+10h], rbx
0x18004ec64  mov     [rax+18h], rsi
0x18004ec68  mov     rax, cs:__security_cookie
0x18004ec6f  xor     rax, rsp
0x18004ec72  mov     [rsp+108h+var_18], rax
0x18004ec7a  mov     esi, r8d
0x18004ec7d  mov     rdi, rdx
0x18004ec80  mov     rbx, rcx
0x18004ec83  mov     [rsp+108h+var_C0], rcx
0x18004ec88  lea     rcx, [rdx+8]; lpCriticalSection
0x18004ec8c  mov     [rbx], rcx
0x18004ec8f  call    cs:__imp_EnterCriticalSection
0x18004ec95  mov     ecx, [rdi+34h]
0x18004ec98  lea     eax, [rcx+1]
0x18004ec9b  mov     [rdi+34h], eax
0x18004ec9e  test    ecx, ecx
0x18004eca0  jnz     short loc_18004ECAB
0x18004eca2  call    cs:__imp_GetCurrentThreadId
0x18004eca8  mov     [rdi+30h], eax
0x18004ecab  cmp     esi, 1
0x18004ecae  setz    al
0x18004ecb1  mov     [rbx+8], al
0x18004ecb4  mov     [rbx+10h], rdi
0x18004ecb8  cmp     byte ptr [rdi+48h], 0
0x18004ecbc  jz      short loc_18004ECE6
0x18004ecbe  mov     rax, rbx
0x18004ecc1  mov     rcx, [rsp+108h+var_18]
0x18004ecc9  xor     rcx, rsp; StackCookie
0x18004eccc  call    __security_check_cookie
0x18004ecd1  lea     r11, [rsp+108h+var_8]
0x18004ecd9  mov     rbx, [r11+18h]
0x18004ecdd  mov     rsi, [r11+20h]
0x18004ece1  mov     rsp, r11
0x18004ece4  pop     rdi
0x18004ece5  retn
0x18004ece6  lea     rax, aSubsequentAcce; "Subsequent access to stream after failu"...
0x18004eced  mov     [rsp+108h+var_D8], rax; struct win_musl::TStringEllipseBase *
0x18004ecf2  mov     [rsp+108h+var_E0], 8000FFFFh; unsigned int
0x18004ecfa  mov     [rsp+108h+var_E8], 7Fh; unsigned int
0x18004ed02  lea     r9, word_18013A0B6
0x18004ed09  lea     r8, aNoFilename; "(no filename)"
0x18004ed10  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18004ed15  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18004ed1a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18004ed21  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18004ed26  call    _CxxThrowException_0
```
