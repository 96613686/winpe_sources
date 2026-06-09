# win_dox::CopyByteVector(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800c80b4`
- end: `0x1800c817c`
- name: `?CopyByteVector@win_dox@@YAPEAEAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800c7c80`
- `0x1800c7d90`
- `0x1800c7ea0`
- `0x1800c7fb0`

## callees

- `0x1800517a0`
- `0x1800c80b4`
- `0x1800cd38c`
- `0x1800d5fd8`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c80f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c80f1`

## string_xrefs

- `0x1800c80ff`: `Unable to copy buffer`

## pseudocode

```c
void *__fastcall win_dox::CopyByteVector(__int64 a1)
{
  SIZE_T v2; // rbx
  void *v3; // rax
  void *v4; // rdi
  _BYTE pExceptionObject[160]; // [rsp+40h] [rbp-B8h] BYREF

  if ( *(_QWORD *)(a1 + 8) )
    v2 = *(_QWORD *)(a1 + 16) - *(_QWORD *)(a1 + 8);
  else
    v2 = 0;
  v3 = CoTaskMemAlloc(v2);
  v4 = v3;
  if ( !v3 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x1Eu,
      0x8007000E,
      (struct win_musl::TStringEllipseBase *)L"Unable to copy buffer");
    throw (SplException::THResultException *)pExceptionObject;
  }
  memcpy_0(v3, *(const void **)(a1 + 8), v2);
  return v4;
}

```

## disassembly

```asm
0x1800c80b4  mov     [rsp+arg_8], rbx
0x1800c80b9  mov     [rsp+arg_10], rsi
0x1800c80be  push    rdi
0x1800c80bf  sub     rsp, 0F0h
0x1800c80c6  mov     rax, cs:__security_cookie
0x1800c80cd  xor     rax, rsp
0x1800c80d0  mov     [rsp+0F8h+var_18], rax
0x1800c80d8  cmp     qword ptr [rcx+8], 0
0x1800c80dd  mov     rsi, rcx
0x1800c80e0  jnz     short loc_1800C80E6
0x1800c80e2  xor     ebx, ebx
0x1800c80e4  jmp     short loc_1800C80EE
0x1800c80e6  mov     rbx, [rcx+10h]
0x1800c80ea  sub     rbx, [rcx+8]
0x1800c80ee  mov     rcx, rbx; cb
0x1800c80f1  call    cs:__imp_CoTaskMemAlloc
0x1800c80f7  mov     rdi, rax
0x1800c80fa  test    rax, rax
0x1800c80fd  jnz     short loc_1800C8145
0x1800c80ff  lea     rax, aUnableToCopyBu; "Unable to copy buffer"
0x1800c8106  mov     [rsp+0F8h+var_C8], rax; struct win_musl::TStringEllipseBase *
0x1800c810b  lea     r9, word_18013A0B6
0x1800c8112  mov     [rsp+0F8h+var_D0], 8007000Eh; unsigned int
0x1800c811a  lea     r8, aNoFilename; "(no filename)"
0x1800c8121  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x1800c8126  mov     [rsp+0F8h+var_D8], 1Eh; unsigned int
0x1800c812e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c8133  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c813a  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800c813f  call    _CxxThrowException_0
0x1800c8145  mov     rdx, [rsi+8]; Src
0x1800c8149  mov     r8, rbx; Size
0x1800c814c  mov     rcx, rdi; void *
0x1800c814f  call    memcpy_0
0x1800c8154  mov     rax, rdi
0x1800c8157  mov     rcx, [rsp+0F8h+var_18]
0x1800c815f  xor     rcx, rsp; StackCookie
0x1800c8162  call    __security_check_cookie
0x1800c8167  lea     r11, [rsp+0F8h+var_8]
0x1800c816f  mov     rbx, [r11+18h]
0x1800c8173  mov     rsi, [r11+20h]
0x1800c8177  mov     rsp, r11
0x1800c817a  pop     rdi
0x1800c817b  retn
```
