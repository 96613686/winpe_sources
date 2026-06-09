# win_dox::NonCloneableStreamHolder::InnerStreamLocker::InnerStreamLocker(win_dox::NonCloneableStreamHolder *,win_dox::NonCloneableStreamHolder::MethodType)

- ea: `0x18005969c`
- end: `0x180059772`
- name: `??0InnerStreamLocker@NonCloneableStreamHolder@win_dox@@QEAA@PEAV12@W4MethodType@12@@Z`
- size: `214`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180059354`
- `0x18005ae24`
- `0x1801af230`
- `0x1801af2e0`
- `0x1801af34c`
- `0x1801af3a0`
- `0x1801af420`
- `0x1801af580`

## callees

- `0x180012450`
- `0x18005969c`
- `0x180134b70`
- `0x1801359ce`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800596d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800596d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800596e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800596e8`

## string_xrefs

- `0x18005972c`: `Subsequent access to stream after failure not supported`

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
      (SplException::THResultException *)pExceptionObject,
      0x7Fu,
      -2147418113,
      (__int64)L"Subsequent access to stream after failure not supported");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18005969c  mov     [rsp+arg_8], rbx
0x1800596a1  mov     [rsp+arg_10], rsi
0x1800596a6  push    rdi
0x1800596a7  sub     rsp, 100h
0x1800596ae  mov     rax, cs:__security_cookie
0x1800596b5  xor     rax, rsp
0x1800596b8  mov     [rsp+108h+var_18], rax
0x1800596c0  mov     esi, r8d
0x1800596c3  mov     rdi, rdx
0x1800596c6  mov     rbx, rcx
0x1800596c9  mov     [rsp+108h+var_C8], rcx
0x1800596ce  lea     rcx, [rdx+8]; lpCriticalSection
0x1800596d2  mov     [rbx], rcx
0x1800596d5  call    cs:__imp_EnterCriticalSection
0x1800596db  mov     ecx, [rdi+34h]
0x1800596de  lea     eax, [rcx+1]
0x1800596e1  mov     [rdi+34h], eax
0x1800596e4  test    ecx, ecx
0x1800596e6  jnz     short loc_1800596F1
0x1800596e8  call    cs:__imp_GetCurrentThreadId
0x1800596ee  mov     [rdi+30h], eax
0x1800596f1  cmp     esi, 1
0x1800596f4  setz    al
0x1800596f7  mov     [rbx+8], al
0x1800596fa  mov     [rbx+10h], rdi
0x1800596fe  cmp     byte ptr [rdi+48h], 0
0x180059702  jz      short loc_18005972C
0x180059704  mov     rax, rbx
0x180059707  mov     rcx, [rsp+108h+var_18]
0x18005970f  xor     rcx, rsp; StackCookie
0x180059712  call    __security_check_cookie
0x180059717  lea     r11, [rsp+108h+var_8]
0x18005971f  mov     rbx, [r11+18h]
0x180059723  mov     rsi, [r11+20h]
0x180059727  mov     rsp, r11
0x18005972a  pop     rdi
0x18005972b  retn
0x18005972c  lea     rax, aSubsequentAcce; "Subsequent access to stream after failu"...
0x180059733  mov     [rsp+108h+var_D8], rax; __int64
0x180059738  mov     [rsp+108h+var_E0], 8000FFFFh; int
0x180059740  mov     [rsp+108h+var_E8], 7Fh; unsigned int
0x180059748  lea     r9, Src
0x18005974f  lea     r8, aNoFilename; "(no filename)"
0x180059756  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18005975b  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180059760  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180059767  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18005976c  call    _CxxThrowException_0
```
