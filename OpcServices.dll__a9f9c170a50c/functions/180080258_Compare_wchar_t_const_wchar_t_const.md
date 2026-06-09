# Compare(wchar_t const *,wchar_t const *)

- ea: `0x180080258`
- end: `0x180080301`
- name: `?Compare@@YAHPEB_W0@Z`
- size: `169`
- prototype: `int(const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800433e4`
- `0x1800e19b0`

## callees

- `0x1800517a0`
- `0x180079ca0`
- `0x180080258`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180080286`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180080286`

## string_xrefs

- `0x1800802bb`: `::CompareString returned invalid return value`

## pseudocode

```c
__int64 __fastcall Compare(const wchar_t *a1, const wchar_t *a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  win_musl::detail *v4; // rcx
  int v6; // eax
  unsigned int LastErrorAsFailHR; // eax
  _BYTE pExceptionObject[160]; // [rsp+40h] [rbp-B8h] BYREF

  v2 = 1;
  v3 = CompareStringOrdinal(a1, -1, a2, -1, 1) - 1;
  if ( v3 )
  {
    v6 = v3 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        LastErrorAsFailHR = win_musl::detail::GetLastErrorAsFailHR(v4);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x5B4u,
          LastErrorAsFailHR,
          (struct win_musl::TStringEllipseBase *)L"::CompareString returned invalid return value");
        throw (SplException::THResultException *)pExceptionObject;
      }
    }
    else
    {
      return 0;
    }
  }
  else
  {
    return (unsigned int)-1;
  }
  return v2;
}

```

## disassembly

```asm
0x180080258  push    rbx
0x18008025a  sub     rsp, 0F0h
0x180080261  mov     rax, cs:__security_cookie
0x180080268  xor     rax, rsp
0x18008026b  mov     [rsp+0F8h+var_18], rax
0x180080273  or      r9d, 0FFFFFFFFh; cchCount2
0x180080277  mov     r8, rdx; lpString2
0x18008027a  mov     ebx, 1
0x18008027f  or      edx, r9d; cchCount1
0x180080282  mov     [rsp+0F8h+bIgnoreCase], ebx; bIgnoreCase
0x180080286  call    cs:__imp_CompareStringOrdinal
0x18008028c  sub     eax, ebx
0x18008028e  jnz     short loc_1800802AE
0x180080290  or      ebx, 0FFFFFFFFh
0x180080293  mov     eax, ebx
0x180080295  mov     rcx, [rsp+0F8h+var_18]
0x18008029d  xor     rcx, rsp; StackCookie
0x1800802a0  call    __security_check_cookie
0x1800802a5  add     rsp, 0F0h
0x1800802ac  pop     rbx
0x1800802ad  retn
0x1800802ae  sub     eax, ebx
0x1800802b0  jz      short loc_1800802FD
0x1800802b2  cmp     eax, ebx
0x1800802b4  jz      short loc_180080293
0x1800802b6  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800802bb  lea     rcx, aComparestringR; "::CompareString returned invalid return"...
0x1800802c2  mov     [rsp+0F8h+var_C8], rcx; struct win_musl::TStringEllipseBase *
0x1800802c7  lea     r9, word_18013A0B6
0x1800802ce  mov     [rsp+0F8h+var_D0], eax; unsigned int
0x1800802d2  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x1800802d7  lea     r8, aNoFilename; "(no filename)"
0x1800802de  mov     [rsp+0F8h+bIgnoreCase], 5B4h; unsigned int
0x1800802e6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800802eb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800802f2  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800802f7  call    _CxxThrowException_0
0x1800802fd  xor     ebx, ebx
0x1800802ff  jmp     short loc_180080293
```
