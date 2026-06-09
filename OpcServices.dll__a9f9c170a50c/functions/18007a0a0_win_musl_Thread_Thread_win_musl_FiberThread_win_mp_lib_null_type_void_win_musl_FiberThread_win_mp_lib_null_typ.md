# win_musl::Thread::Thread(win_musl::FiberThread *,win_mp_lib::null_type,void (win_musl::FiberThread::*)(win_mp_lib::null_type))

- ea: `0x18007a0a0`
- end: `0x18007a1d5`
- name: `??$?0PEAVFiberThread@win_musl@@Vnull_type@win_mp_lib@@P801@EAAXV23@@Z@Thread@win_musl@@QEAA@PEAVFiberThread@1@Vnull_type@win_mp_lib@@P821@EAAX1@Z@Z`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180079ae0`

## callees

- `0x180018c00`
- `0x1800517a0`
- `0x180079ca0`
- `0x18007a0a0`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007a12d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007a12d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a140`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007a140`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall win_musl::Thread::Thread(__int64 a1, const char *a2, unsigned int a3)
{
  DWORD *v5; // rdi
  const char **v6; // rax
  const char **v7; // r9
  HANDLE Thread; // rax
  void *v9; // rcx
  unsigned int lpThreadId; // [rsp+28h] [rbp-F0h]
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-B8h] BYREF

  *(_QWORD *)a1 = &win_musl::Thread::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  v5 = (DWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 16) = 0;
  v6 = (const char **)operator new(0x18u, a2, a3);
  v7 = 0;
  if ( v6 )
  {
    *v6 = a2;
    v6[2] = (const char *)&win_musl::FiberThread::ThreadProc;
    v7 = v6;
  }
  Thread = CreateThread(
             0,
             0,
             win_musl::Thread::ThreadProc<win_musl::Thread::ThreadThunkData<win_musl::FiberThread *,win_mp_lib::null_type,void (win_musl::FiberThread::*)(win_mp_lib::null_type)>>,
             v7,
             0,
             v5);
  v9 = *(void **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = Thread;
  if ( v9 )
    CloseHandle(v9);
  if ( !*(_QWORD *)(a1 + 8) )
  {
    lpThreadId = win_musl::detail::GetLastErrorAsFailHR((win_musl::detail *)v9);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x59u,
      lpThreadId,
      (struct win_musl::TStringEllipseBase *)L"Unspecified error");
    throw (SplException::THResultException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18007a0a0  mov     rax, rsp
0x18007a0a3  push    rdi
0x18007a0a4  sub     rsp, 110h
0x18007a0ab  mov     [rsp+118h+var_D0], 0FFFFFFFFFFFFFFFEh
0x18007a0b4  mov     [rax+10h], rbx
0x18007a0b8  mov     [rax+18h], rsi
0x18007a0bc  mov     rax, cs:__security_cookie
0x18007a0c3  xor     rax, rsp
0x18007a0c6  mov     [rsp+118h+var_18], rax
0x18007a0ce  mov     rsi, rdx
0x18007a0d1  mov     rbx, rcx
0x18007a0d4  mov     [rsp+118h+var_C8], rcx
0x18007a0d9  lea     rax, ??_7Thread@win_musl@@6B@; const win_musl::Thread::`vftable'
0x18007a0e0  mov     [rcx], rax
0x18007a0e3  mov     qword ptr [rcx+8], 0
0x18007a0eb  lea     rdi, [rcx+10h]
0x18007a0ef  mov     dword ptr [rdi], 0
0x18007a0f5  mov     ecx, 18h; unsigned __int64
0x18007a0fa  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18007a0ff  mov     [rsp+118h+var_D8], rax
0x18007a104  xor     r9d, r9d; lpParameter
0x18007a107  test    rax, rax
0x18007a10a  jnz     loc_18007A1BD
0x18007a110  mov     [rsp+118h+var_D8], r9
0x18007a115  mov     [rsp+118h+lpThreadId], rdi; lpThreadId
0x18007a11a  mov     [rsp+118h+dwCreationFlags], 0; dwCreationFlags
0x18007a122  lea     r8, ??$ThreadProc@U?$ThreadThunkData@PEAVFiberThread@win_musl@@Vnull_type@win_mp_lib@@P812@EAAXV34@@Z@Thread@win_musl@@@Thread@win_musl@@CAKPEAX@Z; lpStartAddress
0x18007a129  xor     edx, edx; dwStackSize
0x18007a12b  xor     ecx, ecx; lpThreadAttributes
0x18007a12d  call    cs:__imp_CreateThread
0x18007a133  mov     rcx, [rbx+8]; hObject
0x18007a137  mov     [rbx+8], rax
0x18007a13b  test    rcx, rcx
0x18007a13e  jz      short loc_18007A146
0x18007a140  call    cs:__imp_CloseHandle
0x18007a146  cmp     qword ptr [rbx+8], 0
0x18007a14b  jz      short loc_18007A175
0x18007a14d  mov     rax, rbx
0x18007a150  mov     rcx, [rsp+118h+var_18]
0x18007a158  xor     rcx, rsp; StackCookie
0x18007a15b  call    __security_check_cookie
0x18007a160  lea     r11, [rsp+118h+var_8]
0x18007a168  mov     rbx, [r11+18h]
0x18007a16c  mov     rsi, [r11+20h]
0x18007a170  mov     rsp, r11
0x18007a173  pop     rdi
0x18007a174  retn
0x18007a175  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x18007a17a  nop
0x18007a17b  lea     rcx, aUnspecifiedErr; "Unspecified error"
0x18007a182  mov     [rsp+118h+var_E8], rcx; struct win_musl::TStringEllipseBase *
0x18007a187  mov     dword ptr [rsp+118h+lpThreadId], eax; unsigned int
0x18007a18b  mov     [rsp+118h+dwCreationFlags], 59h ; 'Y'; unsigned int
0x18007a193  lea     r9, word_18013A0B6
0x18007a19a  lea     r8, aNoFilename; "(no filename)"
0x18007a1a1  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18007a1a6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18007a1ab  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18007a1b2  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18007a1b7  call    _CxxThrowException_0
0x18007a1bd  mov     [rax], rsi
0x18007a1c0  lea     rcx, ?ThreadProc@FiberThread@win_musl@@AEAAXVnull_type@win_mp_lib@@@Z; win_musl::FiberThread::ThreadProc(win_mp_lib::null_type)
0x18007a1c7  mov     [rax+10h], rcx
0x18007a1cb  cmovnz  r9, rax
0x18007a1cf  jmp     loc_18007A110
```
