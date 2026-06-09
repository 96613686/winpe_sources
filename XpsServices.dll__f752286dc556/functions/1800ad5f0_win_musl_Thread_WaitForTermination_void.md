# win_musl::Thread::WaitForTermination(void)

- ea: `0x1800ad5f0`
- end: `0x1800ad6a3`
- name: `?WaitForTermination@Thread@win_musl@@QEAAXXZ`
- size: `179`
- prototype: `void __fastcall(win_musl::Thread *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18010b38c`

## callees

- `0x180012450`
- `0x1800ad5f0`
- `0x180134b70`
- `0x1801359ce`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ad67c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ad67c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad625`

## string_xrefs

- `0x1800ad62f`: `Do not try to wait on the completion of the current thread, it just won't happen.`

## pseudocode

```c
void __fastcall win_musl::Thread::WaitForTermination(win_musl::Thread *this)
{
  int v2; // ebx
  _BYTE pExceptionObject[160]; // [rsp+40h] [rbp-B8h] BYREF

  if ( dword_180229950 != -1 && *((_QWORD *)this + 1) )
  {
    v2 = *((_DWORD *)this + 4);
    if ( v2 == GetCurrentThreadId() )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::THResultException *)pExceptionObject,
        0x71u,
        -2147418113,
        (__int64)L"Do not try to wait on the completion of the current thread, it just won't happen.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF);
  }
}

```

## disassembly

```asm
0x1800ad5f0  mov     [rsp+arg_8], rbx
0x1800ad5f5  push    rdi
0x1800ad5f6  sub     rsp, 0F0h
0x1800ad5fd  mov     rax, cs:__security_cookie
0x1800ad604  xor     rax, rsp
0x1800ad607  mov     [rsp+0F8h+var_18], rax
0x1800ad60f  cmp     cs:dword_180229950, 0FFFFFFFFh
0x1800ad616  mov     rdi, rcx
0x1800ad619  jz      short loc_1800AD682
0x1800ad61b  cmp     qword ptr [rcx+8], 0
0x1800ad620  jz      short loc_1800AD682
0x1800ad622  mov     ebx, [rcx+10h]
0x1800ad625  call    cs:__imp_GetCurrentThreadId
0x1800ad62b  cmp     ebx, eax
0x1800ad62d  jnz     short loc_1800AD675
0x1800ad62f  lea     rax, aDoNotTryToWait; "Do not try to wait on the completion of"...
0x1800ad636  mov     [rsp+0F8h+var_C8], rax; __int64
0x1800ad63b  lea     r9, Src
0x1800ad642  mov     [rsp+0F8h+var_D0], 8000FFFFh; int
0x1800ad64a  lea     r8, aNoFilename; "(no filename)"
0x1800ad651  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x1800ad656  mov     [rsp+0F8h+var_D8], 71h ; 'q'; unsigned int
0x1800ad65e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800ad663  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800ad66a  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800ad66f  call    _CxxThrowException_0
0x1800ad675  mov     rcx, [rdi+8]; hHandle
0x1800ad679  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800ad67c  call    cs:__imp_WaitForSingleObject
0x1800ad682  mov     rcx, [rsp+0F8h+var_18]
0x1800ad68a  xor     rcx, rsp; StackCookie
0x1800ad68d  call    __security_check_cookie
0x1800ad692  mov     rbx, [rsp+0F8h+arg_8]
0x1800ad69a  add     rsp, 0F0h
0x1800ad6a1  pop     rdi
0x1800ad6a2  retn
```
