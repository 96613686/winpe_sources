# win_musl::Thread::WaitForTermination(void)

- ea: `0x18002f500`
- end: `0x18002f5b3`
- name: `?WaitForTermination@Thread@win_musl@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(win_musl::Thread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002f48c`

## callees

- `0x18002f500`
- `0x1800517a0`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f535`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f535`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f546`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002f546`

## string_xrefs

- `0x18002f56d`: `Do not try to wait on the completion of the current thread, it just won't happen.`

## pseudocode

```c
void __fastcall win_musl::Thread::WaitForTermination(win_musl::Thread *this)
{
  int v2; // ebx
  _BYTE pExceptionObject[160]; // [rsp+40h] [rbp-B8h] BYREF

  if ( *((_QWORD *)this + 1) && dword_1801C4F30 != -1 )
  {
    v2 = *((_DWORD *)this + 4);
    if ( v2 == GetCurrentThreadId() )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x71u,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"Do not try to wait on the completion of the current thread, it just won't happen.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF);
  }
}

```

## disassembly

```asm
0x18002f500  mov     [rsp+arg_8], rbx
0x18002f505  push    rdi
0x18002f506  sub     rsp, 0F0h
0x18002f50d  mov     rax, cs:__security_cookie
0x18002f514  xor     rax, rsp
0x18002f517  mov     [rsp+0F8h+var_18], rax
0x18002f51f  cmp     qword ptr [rcx+8], 0
0x18002f524  mov     rdi, rcx
0x18002f527  jz      short loc_18002F54C
0x18002f529  cmp     cs:dword_1801C4F30, 0FFFFFFFFh
0x18002f530  jz      short loc_18002F54C
0x18002f532  mov     ebx, [rcx+10h]
0x18002f535  call    cs:__imp_GetCurrentThreadId
0x18002f53b  cmp     ebx, eax
0x18002f53d  jz      short loc_18002F56D
0x18002f53f  mov     rcx, [rdi+8]; hHandle
0x18002f543  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002f546  call    cs:__imp_WaitForSingleObject
0x18002f54c  mov     rcx, [rsp+0F8h+var_18]
0x18002f554  xor     rcx, rsp; StackCookie
0x18002f557  call    __security_check_cookie
0x18002f55c  mov     rbx, [rsp+0F8h+arg_8]
0x18002f564  add     rsp, 0F0h
0x18002f56b  pop     rdi
0x18002f56c  retn
0x18002f56d  lea     rax, aDoNotTryToWait; "Do not try to wait on the completion of"...
0x18002f574  mov     [rsp+0F8h+var_C8], rax; struct win_musl::TStringEllipseBase *
0x18002f579  lea     r9, word_18013A0B6
0x18002f580  mov     [rsp+0F8h+var_D0], 8000FFFFh; unsigned int
0x18002f588  lea     r8, aNoFilename; "(no filename)"
0x18002f58f  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x18002f594  mov     [rsp+0F8h+var_D8], 71h ; 'q'; unsigned int
0x18002f59c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18002f5a1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18002f5a8  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18002f5ad  call    _CxxThrowException_0
```
