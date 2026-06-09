# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14001fc40`
- end: `0x14001ff41`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140009160`
- `0x140009220`
- `0x140009648`

## callees

- `0x140008f10`
- `0x14001c80c`
- `0x14001e7b0`
- `0x14001fc40`
- `0x140023db8`
- `0x140023de0`
- `0x140023f70`
- `0x140023f8c`
- `0x140032fa0`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001fd6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001fd6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14001fefc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14001fefc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14001fe8a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14001fe8a`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-58h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x14001fc40  mov     rax, rsp
0x14001fc43  mov     [rax+10h], edx
0x14001fc46  mov     [rax+8], rcx
0x14001fc4a  push    rbp
0x14001fc4b  push    rsi
0x14001fc4c  push    rdi
0x14001fc4d  push    r12
0x14001fc4f  push    r13
0x14001fc51  push    r14
0x14001fc53  push    r15
0x14001fc55  sub     rsp, 50h
0x14001fc59  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x14001fc61  mov     [rax+18h], rbx
0x14001fc65  mov     r12, r9
0x14001fc68  mov     r13, r8
0x14001fc6b  mov     r10, rcx
0x14001fc6e  xor     eax, eax
0x14001fc70  mov     rsi, [rsp+88h+lpOutputString]
0x14001fc78  mov     [rsi], ax
0x14001fc7b  mov     rax, [rsp+88h+arg_60]
0x14001fc83  mov     byte ptr [rax], 0
0x14001fc86  mov     r14, [rsp+88h+arg_38]
0x14001fc8e  mov     edi, [r14]
0x14001fc91  mov     rbx, [rsp+88h+arg_78]
0x14001fc99  mov     [rbx+8], edi
0x14001fc9c  mov     eax, [r14+4]
0x14001fca0  mov     [rbx+0Ch], eax
0x14001fca3  xor     ebp, ebp
0x14001fca5  mov     r15d, [rsp+88h+arg_30]
0x14001fcad  mov     ecx, r15d
0x14001fcb0  test    r15d, r15d
0x14001fcb3  jz      short loc_14001FD1B
0x14001fcb5  sub     ecx, 1
0x14001fcb8  jz      short loc_14001FD12
0x14001fcba  sub     ecx, 1
0x14001fcbd  jz      short loc_14001FCCD
0x14001fcbf  cmp     ecx, 1
0x14001fcc2  jnz     short loc_14001FD24
0x14001fcc4  mov     ecx, edi; this
0x14001fcc6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14001fccb  jmp     short loc_14001FD22
0x14001fccd  test    edi, edi
0x14001fccf  js      short loc_14001FD09
0x14001fcd1  mov     edi, 8007029Ch
0x14001fcd6  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x14001fcda  mov     rax, [rsp+88h+arg_28]
0x14001fce2  mov     [rsp+88h+var_60], rax; __int64
0x14001fce7  mov     rax, [rsp+88h+arg_20]
0x14001fcef  mov     [rsp+88h+var_68], rax; __int64
0x14001fcf4  mov     rcx, r10; int
0x14001fcf7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14001fcfc  mov     [rbx+8], edi
0x14001fcff  mov     ecx, edi; this
0x14001fd01  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14001fd06  mov     [rbx+0Ch], eax
0x14001fd09  mov     ecx, edi; this
0x14001fd0b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14001fd10  jmp     short loc_14001FD22
0x14001fd12  mov     ecx, edi; this
0x14001fd14  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14001fd19  jmp     short loc_14001FD22
0x14001fd1b  mov     ecx, edi; this
0x14001fd1d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14001fd22  mov     ebp, eax
0x14001fd24  mov     [rbx], r15d
0x14001fd27  mov     eax, [rsp+88h+arg_70]
0x14001fd2e  mov     [rbx+4], eax
0x14001fd31  cmp     dword ptr [r14+8], 1
0x14001fd36  jnz     short loc_14001FD3E
0x14001fd38  or      eax, 8
0x14001fd3b  mov     [rbx+4], eax
0x14001fd3e  mov     eax, 1
0x14001fd43  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14001fd4b  inc     eax
0x14001fd4d  mov     [rbx+10h], eax
0x14001fd50  mov     rax, [rsp+88h+arg_40]
0x14001fd58  xor     edi, edi
0x14001fd5a  test    rax, rax
0x14001fd5d  jz      short loc_14001FD64
0x14001fd5f  cmp     [rax], di
0x14001fd62  jnz     short loc_14001FD67
0x14001fd64  mov     rax, rdi
0x14001fd67  mov     [rbx+18h], rax
0x14001fd6b  call    cs:__imp_GetCurrentThreadId
0x14001fd71  mov     [rbx+20h], eax
0x14001fd74  mov     [rbx+38h], r13
0x14001fd78  mov     eax, [rsp+88h+arg_8]
0x14001fd7f  mov     [rbx+40h], eax
0x14001fd82  mov     [rbx+44h], ebp
0x14001fd85  mov     rax, [rsp+88h+arg_20]
0x14001fd8d  mov     [rbx+28h], rax
0x14001fd91  mov     [rbx+30h], r12
0x14001fd95  mov     rax, [rsp+88h+arg_28]
0x14001fd9d  mov     [rbx+88h], rax
0x14001fda4  mov     rax, [rsp+88h+arg_0]
0x14001fdac  mov     [rbx+90h], rax
0x14001fdb3  mov     [rbx+48h], rdi
0x14001fdb7  xorps   xmm0, xmm0
0x14001fdba  xor     eax, eax
0x14001fdbc  movups  xmmword ptr [rbx+68h], xmm0
0x14001fdc0  mov     [rbx+78h], rax
0x14001fdc4  movups  xmmword ptr [rbx+50h], xmm0
0x14001fdc8  mov     [rbx+60h], rax
0x14001fdcc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001fdd3  test    rax, rax
0x14001fdd6  jz      short loc_14001FDDF
0x14001fdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fddd  jmp     short loc_14001FDE2
0x14001fddf  mov     rax, rdi
0x14001fde2  mov     [rbx+80h], rax
0x14001fde9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14001fdf0  test    rax, rax
0x14001fdf3  jz      short loc_14001FDFD
0x14001fdf5  mov     rcx, rbx
0x14001fdf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fdfd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14001fe04  test    rax, rax
0x14001fe07  jz      short loc_14001FE1F
0x14001fe09  mov     r8d, 400h
0x14001fe0f  mov     rdx, [rsp+88h+arg_60]
0x14001fe17  mov     rcx, rbx
0x14001fe1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe1f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001fe26  test    rax, rax
0x14001fe29  jz      short loc_14001FE33
0x14001fe2b  mov     rcx, rbx
0x14001fe2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe33  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001fe3a  test    rax, rax
0x14001fe3d  jz      short loc_14001FE4D
0x14001fe3f  test    byte ptr [rbx+4], 2
0x14001fe43  jnz     short loc_14001FE4D
0x14001fe45  mov     rcx, rbx
0x14001fe48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe4d  cmp     [rbx+8], edi
0x14001fe50  jl      short loc_14001FE6C
0x14001fe52  cmp     r15d, 3
0x14001fe56  jnz     loc_14001FF3B
0x14001fe5c  mov     ecx, 8000FFFFh; this
0x14001fe61  mov     [rbx+8], ecx
0x14001fe64  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14001fe69  mov     [rbx+0Ch], eax
0x14001fe6c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14001fe73  jnz     short loc_14001FE94
0x14001fe75  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14001fe7c  test    rax, rax
0x14001fe7f  jz      short loc_14001FE8A
0x14001fe81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fe86  test    al, al
0x14001fe88  jmp     short loc_14001FE92
0x14001fe8a  call    cs:__imp_IsDebuggerPresent
0x14001fe90  test    eax, eax
0x14001fe92  jz      short loc_14001FE9A
0x14001fe94  test    byte ptr [rbx+4], 2
0x14001fe98  jz      short loc_14001FEBE
0x14001fe9a  mov     rax, cs:g_pfnResultLoggingCallback
0x14001fea1  test    rax, rax
0x14001fea4  jz      short loc_14001FF02
0x14001fea6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14001fead  jnz     short loc_14001FF02
0x14001feaf  xor     r8d, r8d
0x14001feb2  xor     edx, edx
0x14001feb4  mov     rcx, rbx
0x14001feb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001febc  jmp     short loc_14001FF02
0x14001febe  mov     ebp, 800h
0x14001fec3  mov     rax, cs:g_pfnResultLoggingCallback
0x14001feca  test    rax, rax
0x14001fecd  jz      short loc_14001FEE6
0x14001fecf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14001fed6  jnz     short loc_14001FEE6
0x14001fed8  mov     r8d, ebp
0x14001fedb  mov     rdx, rsi
0x14001fede  mov     rcx, rbx
0x14001fee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001fee6  cmp     [rsi], di
0x14001fee9  jnz     short loc_14001FEF9
0x14001feeb  mov     r8, rbx; unsigned __int64
0x14001feee  mov     rdx, rbp; wchar_t *
0x14001fef1  mov     rcx, rsi; this
0x14001fef4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14001fef9  mov     rcx, rsi; lpOutputString
0x14001fefc  call    cs:__imp_OutputDebugStringW
0x14001ff02  test    byte ptr [rbx+4], 4
0x14001ff06  jnz     short loc_14001FF11
0x14001ff08  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14001ff0f  jz      short loc_14001FF23
0x14001ff11  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14001ff18  test    rax, rax
0x14001ff1b  jz      short loc_14001FF23
0x14001ff1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ff22  nop
0x14001ff23  mov     rbx, [rsp+88h+arg_10]
0x14001ff2b  add     rsp, 50h
0x14001ff2f  pop     r15
0x14001ff31  pop     r14
0x14001ff33  pop     r13
0x14001ff35  pop     r12
0x14001ff37  pop     rdi
0x14001ff38  pop     rsi
0x14001ff39  pop     rbp
0x14001ff3a  retn
0x14001ff3b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
