# CTransaction::CTransaction(CResourceManager *,ulong,int)

- ea: `0x180061aa4`
- end: `0x180061dbb`
- name: `??0CTransaction@@QEAA@PEAVCResourceManager@@KH@Z`
- size: `791`
- prototype: `CTransaction *__fastcall(CTransaction *this, struct CResourceManager *, int, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180072e18`
- `0x180072fcc`
- `0x180073728`
- `0x180074154`
- `0x180074430`

## callees

- `0x180004d91`
- `0x18000e558`
- `0x18000f35c`
- `0x18002c6c8`
- `0x180061aa4`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180061d0d`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180061d0d`
- `KERNEL32!GetLastError` at `0x180061ca4`
- `KERNEL32!GetLastError` at `0x180061ca4`
- `KERNEL32!CreateEventW` at `0x180061ae6`
- `KERNEL32!CreateEventW` at `0x180061ae6`

## pseudocode

```c
CTransaction *__fastcall CTransaction::CTransaction(CTransaction *this, struct CResourceManager *a2, int a3, int a4)
{
  DWORD LastError; // ebx
  int v9; // ecx
  _QWORD pExceptionObject[4]; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)this = &CTransaction::`vftable';
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 13) = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 20) = CTransaction::HandleTransaction;
  *((_QWORD *)this + 21) = CTransaction::HandleTransaction;
  *((_OWORD *)this + 8) = 0;
  *((_OWORD *)this + 9) = 0;
  *((_QWORD *)this + 26) = CTransaction::TimeToRetryAbort1;
  *((_QWORD *)this + 27) = CTransaction::TimeToRetryAbort1;
  *((_OWORD *)this + 11) = 0;
  *((_OWORD *)this + 12) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 35) = CTransaction::TimeToRetryAbort2;
  *((_QWORD *)this + 36) = CTransaction::TimeToRetryAbort2;
  *(_OWORD *)((char *)this + 248) = 0;
  *(_OWORD *)((char *)this + 264) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 44) = CTransaction::TimeToRetrySortedCommit;
  *((_QWORD *)this + 45) = CTransaction::TimeToRetrySortedCommit;
  *((_OWORD *)this + 20) = 0;
  *((_OWORD *)this + 21) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 53) = CTransaction::TimeToRetryCommit2;
  *((_QWORD *)this + 54) = CTransaction::TimeToRetryCommit2;
  *(_OWORD *)((char *)this + 392) = 0;
  *(_OWORD *)((char *)this + 408) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 62) = CTransaction::TimeToRetryCommit3;
  *((_QWORD *)this + 63) = CTransaction::TimeToRetryCommit3;
  *((_OWORD *)this + 29) = 0;
  *((_OWORD *)this + 30) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 71) = CTransaction::TimeToRetryCommitLogging;
  *((_QWORD *)this + 72) = CTransaction::TimeToRetryCommitLogging;
  *(_OWORD *)((char *)this + 536) = 0;
  *(_OWORD *)((char *)this + 552) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 3) = 1;
  *((_QWORD *)this + 8) = a2;
  *((_QWORD *)this + 7) = -1;
  *((_DWORD *)this + 20) = 0;
  *((_BYTE *)this + 112) = 0;
  *((_DWORD *)this + 29) = 0;
  *((_BYTE *)this + 608) = 0;
  if ( !*((_QWORD *)this + 13) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 42), 13, WPP_217e75a21d58303895838556812afd25_Traceguids, LastError);
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"xact", 0x5DDu);
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  *((_DWORD *)this + 5) = 0;
  if ( !a3 )
  {
    v9 = *((_DWORD *)a2 + 27);
    a3 = 0;
    if ( v9 != -1 )
      a3 = v9 + 1;
    *((_DWORD *)a2 + 27) = a3;
  }
  *((_DWORD *)this + 4) = a3;
  if ( a4 )
    *((_DWORD *)this + 5) |= 0x60u;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 42), a3);
  return this;
}

```

## disassembly

```asm
0x180061aa4  mov     [rsp+arg_8], rbx
0x180061aa9  mov     [rsp+arg_10], rbp
0x180061aae  mov     [rsp+arg_0], rcx
0x180061ab3  push    rsi
0x180061ab4  push    rdi
0x180061ab5  push    r14
0x180061ab7  sub     rsp, 50h
0x180061abb  mov     ebp, r9d
0x180061abe  mov     edi, r8d
0x180061ac1  mov     rsi, rdx
0x180061ac4  mov     rbx, rcx
0x180061ac7  lea     rax, ??_7CTransaction@@6B@; const CTransaction::`vftable'
0x180061ace  mov     [rcx], rax
0x180061ad1  xor     r14d, r14d
0x180061ad4  mov     [rcx+48h], r14
0x180061ad8  mov     [rcx+58h], r14
0x180061adc  xor     r9d, r9d; lpName
0x180061adf  xor     r8d, r8d; bInitialState
0x180061ae2  xor     edx, edx; bManualReset
0x180061ae4  xor     ecx, ecx; lpEventAttributes
0x180061ae6  call    cs:__imp_CreateEventW
0x180061aec  mov     [rbx+68h], rax
0x180061af0  lea     rax, ?HandleTransaction@CTransaction@@CAXPEAVEXOVERLAPPED@@@Z; CTransaction::HandleTransaction(EXOVERLAPPED *)
0x180061af7  mov     [rbx+0A0h], rax
0x180061afe  mov     [rbx+0A8h], rax
0x180061b05  xorps   xmm0, xmm0
0x180061b08  movups  xmmword ptr [rbx+80h], xmm0
0x180061b0f  movups  xmmword ptr [rbx+90h], xmm0
0x180061b16  lea     rax, ?TimeToRetryAbort1@CTransaction@@CAXPEAVCTimer@@@Z; CTransaction::TimeToRetryAbort1(CTimer *)
0x180061b1d  mov     [rbx+0D0h], rax
0x180061b24  mov     [rbx+0D8h], rax
0x180061b2b  movups  xmmword ptr [rbx+0B0h], xmm0
0x180061b32  movups  xmmword ptr [rbx+0C0h], xmm0
0x180061b39  mov     [rbx+0E0h], r14
0x180061b40  mov     [rbx+0E8h], r14
0x180061b47  mov     [rbx+0F0h], r14
0x180061b4e  lea     rax, ?TimeToRetryAbort2@CTransaction@@CAXPEAVCTimer@@@Z; CTransaction::TimeToRetryAbort2(CTimer *)
0x180061b55  mov     [rbx+118h], rax
0x180061b5c  mov     [rbx+120h], rax
0x180061b63  movups  xmmword ptr [rbx+0F8h], xmm0
0x180061b6a  movups  xmmword ptr [rbx+108h], xmm0
0x180061b71  mov     [rbx+128h], r14
0x180061b78  mov     [rbx+130h], r14
0x180061b7f  mov     [rbx+138h], r14
0x180061b86  lea     rax, ?TimeToRetrySortedCommit@CTransaction@@CAXPEAVCTimer@@@Z; CTransaction::TimeToRetrySortedCommit(CTimer *)
0x180061b8d  mov     [rbx+160h], rax
0x180061b94  mov     [rbx+168h], rax
0x180061b9b  movups  xmmword ptr [rbx+140h], xmm0
0x180061ba2  movups  xmmword ptr [rbx+150h], xmm0
0x180061ba9  mov     [rbx+170h], r14
0x180061bb0  mov     [rbx+178h], r14
0x180061bb7  mov     [rbx+180h], r14
0x180061bbe  lea     rax, ?TimeToRetryCommit2@CTransaction@@CAXPEAVCTimer@@@Z; CTransaction::TimeToRetryCommit2(CTimer *)
0x180061bc5  mov     [rbx+1A8h], rax
0x180061bcc  mov     [rbx+1B0h], rax
0x180061bd3  movups  xmmword ptr [rbx+188h], xmm0
0x180061bda  movups  xmmword ptr [rbx+198h], xmm0
0x180061be1  mov     [rbx+1B8h], r14
0x180061be8  mov     [rbx+1C0h], r14
0x180061bef  mov     [rbx+1C8h], r14
0x180061bf6  lea     rax, ?TimeToRetryCommit3@CTransaction@@CAXPEAVCTimer@@@Z; CTransaction::TimeToRetryCommit3(CTimer *)
0x180061bfd  mov     [rbx+1F0h], rax
0x180061c04  mov     [rbx+1F8h], rax
0x180061c0b  movups  xmmword ptr [rbx+1D0h], xmm0
0x180061c12  movups  xmmword ptr [rbx+1E0h], xmm0
0x180061c19  mov     [rbx+200h], r14
0x180061c20  mov     [rbx+208h], r14
0x180061c27  mov     [rbx+210h], r14
0x180061c2e  lea     rax, ?TimeToRetryCommitLogging@CTransaction@@CAXPEAVCTimer@@@Z; CTransaction::TimeToRetryCommitLogging(CTimer *)
0x180061c35  mov     [rbx+238h], rax
0x180061c3c  mov     [rbx+240h], rax
0x180061c43  movups  xmmword ptr [rbx+218h], xmm0
0x180061c4a  movups  xmmword ptr [rbx+228h], xmm0
0x180061c51  mov     [rbx+248h], r14
0x180061c58  mov     [rbx+250h], r14
0x180061c5f  mov     [rbx+258h], r14
0x180061c66  xor     eax, eax
0x180061c68  movups  xmmword ptr [rbx+10h], xmm0
0x180061c6c  movups  xmmword ptr [rbx+20h], xmm0
0x180061c70  mov     [rbx+30h], rax
0x180061c74  mov     dword ptr [rbx+0Ch], 1
0x180061c7b  mov     [rbx+40h], rsi
0x180061c7f  mov     qword ptr [rbx+38h], 0FFFFFFFFFFFFFFFFh
0x180061c87  mov     [rbx+50h], r14d
0x180061c8b  mov     [rbx+70h], r14b
0x180061c8f  mov     [rbx+74h], r14d
0x180061c93  mov     [rbx+260h], r14b
0x180061c9a  cmp     [rbx+68h], r14
0x180061c9e  jnz     loc_180061D31
0x180061ca4  call    cs:__imp_GetLastError
0x180061caa  mov     ebx, eax
0x180061cac  lea     rax, WPP_GLOBAL_Control
0x180061cb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180061cba  cmp     rcx, rax
0x180061cbd  jz      short loc_180061CE2
0x180061cbf  test    byte ptr [rcx+15Ch], 1
0x180061cc6  jz      short loc_180061CE2
0x180061cc8  lea     edx, [r14+0Dh]
0x180061ccc  mov     r9d, ebx
0x180061ccf  lea     r8, WPP_217e75a21d58303895838556812afd25_Traceguids
0x180061cd6  mov     rcx, [rcx+150h]
0x180061cdd  call    WPP_SF_d
0x180061ce2  test    ebx, ebx
0x180061ce4  jz      short loc_180061CFB
0x180061ce6  mov     r8d, 5DDh; unsigned __int16
0x180061cec  lea     rdx, aXact; "xact"
0x180061cf3  mov     ecx, ebx; int
0x180061cf5  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180061cfa  nop
0x180061cfb  mov     r8d, 1
0x180061d01  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x180061d08  lea     rcx, [rsp+68h+pExceptionObject]
0x180061d0d  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x180061d13  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180061d1a  mov     [rsp+68h+pExceptionObject], rax
0x180061d1f  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180061d26  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180061d2b  call    _CxxThrowException_0
0x180061d31  mov     [rbx+14h], r14d
0x180061d35  test    edi, edi
0x180061d37  jnz     short loc_180061D4B
0x180061d39  mov     ecx, [rsi+6Ch]
0x180061d3c  lea     eax, [rcx+1]
0x180061d3f  mov     edi, r14d
0x180061d42  cmp     ecx, 0FFFFFFFFh
0x180061d45  cmovnz  edi, eax
0x180061d48  mov     [rsi+6Ch], edi
0x180061d4b  mov     [rbx+10h], edi
0x180061d4e  test    ebp, ebp
0x180061d50  jz      short loc_180061D56
0x180061d52  or      dword ptr [rbx+14h], 60h
0x180061d56  lea     rax, WPP_GLOBAL_Control
0x180061d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061d64  cmp     rcx, rax
0x180061d67  jz      short loc_180061DA3
0x180061d69  test    byte ptr [rcx+15Ch], 4
0x180061d70  jz      short loc_180061DA3
0x180061d72  lea     rax, aDouble; "Double"
0x180061d79  lea     r9, aSingle; "Single"
0x180061d80  test    ebp, ebp
0x180061d82  cmovz   r9, rax
0x180061d86  mov     edx, 0Eh
0x180061d8b  mov     dword ptr [rsp+68h+var_48], edi; char
0x180061d8f  lea     r8, WPP_217e75a21d58303895838556812afd25_Traceguids
0x180061d96  mov     rcx, [rcx+150h]; LoggerHandle
0x180061d9d  call    WPP_SF_Sd
0x180061da2  nop
0x180061da3  mov     rax, rbx
0x180061da6  lea     r11, [rsp+68h+var_18]
0x180061dab  mov     rbx, [r11+28h]
0x180061daf  mov     rbp, [r11+30h]
0x180061db3  mov     rsp, r11
0x180061db6  pop     r14
0x180061db8  pop     rdi
0x180061db9  pop     rsi
0x180061dba  retn
```
