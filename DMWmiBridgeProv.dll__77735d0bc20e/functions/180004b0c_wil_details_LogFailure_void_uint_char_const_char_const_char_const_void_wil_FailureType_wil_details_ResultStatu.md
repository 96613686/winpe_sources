# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004b0c`
- end: `0x180004e05`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003148`
- `0x180003494`

## callees

- `0x180003088`
- `0x180004174`
- `0x180004948`
- `0x180004b0c`
- `0x180008adc`
- `0x180008b00`
- `0x180008b14`
- `0x180008b30`
- `0x1800099e0`
- `0x18024f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c2f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004dc0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004dc0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d4e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004d4e`

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
  wil::details *v28; // [rsp+30h] [rbp-48h]

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x180004b0c  mov     [rsp+arg_10], rbx
0x180004b11  mov     [rsp+arg_8], edx
0x180004b15  mov     [rsp+arg_0], rcx
0x180004b1a  push    rbp
0x180004b1b  push    rsi
0x180004b1c  push    rdi
0x180004b1d  push    r12
0x180004b1f  push    r13
0x180004b21  push    r14
0x180004b23  push    r15
0x180004b25  sub     rsp, 40h
0x180004b29  mov     r12, r9
0x180004b2c  mov     r13, r8
0x180004b2f  mov     r10, rcx
0x180004b32  xor     eax, eax
0x180004b34  mov     rsi, [rsp+78h+lpOutputString]
0x180004b3c  mov     [rsi], ax
0x180004b3f  mov     rax, [rsp+78h+arg_60]
0x180004b47  mov     byte ptr [rax], 0
0x180004b4a  mov     r14, [rsp+78h+arg_38]
0x180004b52  mov     edi, [r14]
0x180004b55  mov     rbx, [rsp+78h+arg_78]
0x180004b5d  mov     [rbx+8], edi
0x180004b60  mov     eax, [r14+4]
0x180004b64  mov     [rbx+0Ch], eax
0x180004b67  xor     ebp, ebp
0x180004b69  mov     r15d, [rsp+78h+arg_30]
0x180004b71  mov     ecx, r15d
0x180004b74  test    r15d, r15d
0x180004b77  jz      short loc_180004BDF
0x180004b79  sub     ecx, 1
0x180004b7c  jz      short loc_180004BD6
0x180004b7e  sub     ecx, 1
0x180004b81  jz      short loc_180004B91
0x180004b83  cmp     ecx, 1
0x180004b86  jnz     short loc_180004BE8
0x180004b88  mov     ecx, edi; this
0x180004b8a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004b8f  jmp     short loc_180004BE6
0x180004b91  test    edi, edi
0x180004b93  js      short loc_180004BCD
0x180004b95  mov     edi, 8007029Ch
0x180004b9a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004b9e  mov     rax, [rsp+78h+arg_28]
0x180004ba6  mov     [rsp+78h+var_50], rax; __int64
0x180004bab  mov     rax, [rsp+78h+arg_20]
0x180004bb3  mov     [rsp+78h+var_58], rax; __int64
0x180004bb8  mov     rcx, r10; int
0x180004bbb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004bc0  mov     [rbx+8], edi
0x180004bc3  mov     ecx, edi; this
0x180004bc5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004bca  mov     [rbx+0Ch], eax
0x180004bcd  mov     ecx, edi; this
0x180004bcf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004bd4  jmp     short loc_180004BE6
0x180004bd6  mov     ecx, edi; this
0x180004bd8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004bdd  jmp     short loc_180004BE6
0x180004bdf  mov     ecx, edi; this
0x180004be1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004be6  mov     ebp, eax
0x180004be8  mov     [rbx], r15d
0x180004beb  mov     eax, [rsp+78h+arg_70]
0x180004bf2  mov     [rbx+4], eax
0x180004bf5  cmp     dword ptr [r14+8], 1
0x180004bfa  jnz     short loc_180004C02
0x180004bfc  or      eax, 8
0x180004bff  mov     [rbx+4], eax
0x180004c02  mov     eax, 1
0x180004c07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004c0f  inc     eax
0x180004c11  mov     [rbx+10h], eax
0x180004c14  mov     rax, [rsp+78h+arg_40]
0x180004c1c  xor     edi, edi
0x180004c1e  test    rax, rax
0x180004c21  jz      short loc_180004C28
0x180004c23  cmp     [rax], di
0x180004c26  jnz     short loc_180004C2B
0x180004c28  mov     rax, rdi
0x180004c2b  mov     [rbx+18h], rax
0x180004c2f  call    cs:__imp_GetCurrentThreadId
0x180004c35  mov     [rbx+20h], eax
0x180004c38  mov     [rbx+38h], r13
0x180004c3c  mov     eax, [rsp+78h+arg_8]
0x180004c43  mov     [rbx+40h], eax
0x180004c46  mov     [rbx+44h], ebp
0x180004c49  mov     rax, [rsp+78h+arg_20]
0x180004c51  mov     [rbx+28h], rax
0x180004c55  mov     [rbx+30h], r12
0x180004c59  mov     rax, [rsp+78h+arg_28]
0x180004c61  mov     [rbx+88h], rax
0x180004c68  mov     rax, [rsp+78h+arg_0]
0x180004c70  mov     [rbx+90h], rax
0x180004c77  mov     [rbx+48h], rdi
0x180004c7b  xorps   xmm0, xmm0
0x180004c7e  xor     eax, eax
0x180004c80  movups  xmmword ptr [rbx+68h], xmm0
0x180004c84  mov     [rbx+78h], rax
0x180004c88  movups  xmmword ptr [rbx+50h], xmm0
0x180004c8c  mov     [rbx+60h], rax
0x180004c90  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004c97  test    rax, rax
0x180004c9a  jz      short loc_180004CA3
0x180004c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca1  jmp     short loc_180004CA6
0x180004ca3  mov     rax, rdi
0x180004ca6  mov     [rbx+80h], rax
0x180004cad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004cb4  test    rax, rax
0x180004cb7  jz      short loc_180004CC1
0x180004cb9  mov     rcx, rbx
0x180004cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004cc8  test    rax, rax
0x180004ccb  jz      short loc_180004CE3
0x180004ccd  mov     r8d, 400h
0x180004cd3  mov     rdx, [rsp+78h+arg_60]
0x180004cdb  mov     rcx, rbx
0x180004cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004cea  test    rax, rax
0x180004ced  jz      short loc_180004CF7
0x180004cef  mov     rcx, rbx
0x180004cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cf7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004cfe  test    rax, rax
0x180004d01  jz      short loc_180004D11
0x180004d03  test    byte ptr [rbx+4], 2
0x180004d07  jnz     short loc_180004D11
0x180004d09  mov     rcx, rbx
0x180004d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d11  cmp     [rbx+8], edi
0x180004d14  jl      short loc_180004D30
0x180004d16  cmp     r15d, 3
0x180004d1a  jnz     loc_180004DFF
0x180004d20  mov     ecx, 8000FFFFh; this
0x180004d25  mov     [rbx+8], ecx
0x180004d28  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004d2d  mov     [rbx+0Ch], eax
0x180004d30  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004d37  jnz     short loc_180004D58
0x180004d39  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004d40  test    rax, rax
0x180004d43  jz      short loc_180004D4E
0x180004d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d4a  test    al, al
0x180004d4c  jmp     short loc_180004D56
0x180004d4e  call    cs:__imp_IsDebuggerPresent
0x180004d54  test    eax, eax
0x180004d56  jz      short loc_180004D5E
0x180004d58  test    byte ptr [rbx+4], 2
0x180004d5c  jz      short loc_180004D82
0x180004d5e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d65  test    rax, rax
0x180004d68  jz      short loc_180004DC6
0x180004d6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004d71  jnz     short loc_180004DC6
0x180004d73  xor     r8d, r8d
0x180004d76  xor     edx, edx
0x180004d78  mov     rcx, rbx
0x180004d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d80  jmp     short loc_180004DC6
0x180004d82  mov     ebp, 800h
0x180004d87  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d8e  test    rax, rax
0x180004d91  jz      short loc_180004DAA
0x180004d93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004d9a  jnz     short loc_180004DAA
0x180004d9c  mov     r8d, ebp
0x180004d9f  mov     rdx, rsi
0x180004da2  mov     rcx, rbx
0x180004da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004daa  cmp     [rsi], di
0x180004dad  jnz     short loc_180004DBD
0x180004daf  mov     r8, rbx; unsigned __int64
0x180004db2  mov     rdx, rbp; unsigned __int16 *
0x180004db5  mov     rcx, rsi; this
0x180004db8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004dbd  mov     rcx, rsi; lpOutputString
0x180004dc0  call    cs:__imp_OutputDebugStringW
0x180004dc6  test    byte ptr [rbx+4], 4
0x180004dca  jnz     short loc_180004DD5
0x180004dcc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004dd3  jz      short loc_180004DE7
0x180004dd5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004ddc  test    rax, rax
0x180004ddf  jz      short loc_180004DE7
0x180004de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de6  nop
0x180004de7  mov     rbx, [rsp+78h+arg_10]
0x180004def  add     rsp, 40h
0x180004df3  pop     r15
0x180004df5  pop     r14
0x180004df7  pop     r13
0x180004df9  pop     r12
0x180004dfb  pop     rdi
0x180004dfc  pop     rsi
0x180004dfd  pop     rbp
0x180004dfe  retn
0x180004dff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
