# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800f0cac`
- end: `0x1800f0fad`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ef5b4`
- `0x1800ef910`

## callees

- `0x1800c69d0`
- `0x1800ef4fc`
- `0x1800f0494`
- `0x1800f0cac`
- `0x1800f1278`
- `0x1800f12a0`
- `0x1800f12b4`
- `0x1800f12d0`
- `0x1800f1de4`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f0dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f0dd7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f0f68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f0f68`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f0ef6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f0ef6`

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
0x1800f0cac  mov     rax, rsp
0x1800f0caf  mov     [rax+10h], edx
0x1800f0cb2  mov     [rax+8], rcx
0x1800f0cb6  push    rbp
0x1800f0cb7  push    rsi
0x1800f0cb8  push    rdi
0x1800f0cb9  push    r12
0x1800f0cbb  push    r13
0x1800f0cbd  push    r14
0x1800f0cbf  push    r15
0x1800f0cc1  sub     rsp, 50h
0x1800f0cc5  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1800f0ccd  mov     [rax+18h], rbx
0x1800f0cd1  mov     r12, r9
0x1800f0cd4  mov     r13, r8
0x1800f0cd7  mov     r10, rcx
0x1800f0cda  xor     eax, eax
0x1800f0cdc  mov     rsi, [rsp+88h+lpOutputString]
0x1800f0ce4  mov     [rsi], ax
0x1800f0ce7  mov     rax, [rsp+88h+arg_60]
0x1800f0cef  mov     byte ptr [rax], 0
0x1800f0cf2  mov     r14, [rsp+88h+arg_38]
0x1800f0cfa  mov     edi, [r14]
0x1800f0cfd  mov     rbx, [rsp+88h+arg_78]
0x1800f0d05  mov     [rbx+8], edi
0x1800f0d08  mov     eax, [r14+4]
0x1800f0d0c  mov     [rbx+0Ch], eax
0x1800f0d0f  xor     ebp, ebp
0x1800f0d11  mov     r15d, [rsp+88h+arg_30]
0x1800f0d19  mov     ecx, r15d
0x1800f0d1c  test    r15d, r15d
0x1800f0d1f  jz      short loc_1800F0D87
0x1800f0d21  sub     ecx, 1
0x1800f0d24  jz      short loc_1800F0D7E
0x1800f0d26  sub     ecx, 1
0x1800f0d29  jz      short loc_1800F0D39
0x1800f0d2b  cmp     ecx, 1
0x1800f0d2e  jnz     short loc_1800F0D90
0x1800f0d30  mov     ecx, edi; this
0x1800f0d32  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800f0d37  jmp     short loc_1800F0D8E
0x1800f0d39  test    edi, edi
0x1800f0d3b  js      short loc_1800F0D75
0x1800f0d3d  mov     edi, 8007029Ch
0x1800f0d42  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x1800f0d46  mov     rax, [rsp+88h+arg_28]
0x1800f0d4e  mov     [rsp+88h+var_60], rax; __int64
0x1800f0d53  mov     rax, [rsp+88h+arg_20]
0x1800f0d5b  mov     [rsp+88h+var_68], rax; __int64
0x1800f0d60  mov     rcx, r10; int
0x1800f0d63  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800f0d68  mov     [rbx+8], edi
0x1800f0d6b  mov     ecx, edi; this
0x1800f0d6d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800f0d72  mov     [rbx+0Ch], eax
0x1800f0d75  mov     ecx, edi; this
0x1800f0d77  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800f0d7c  jmp     short loc_1800F0D8E
0x1800f0d7e  mov     ecx, edi; this
0x1800f0d80  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800f0d85  jmp     short loc_1800F0D8E
0x1800f0d87  mov     ecx, edi; this
0x1800f0d89  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800f0d8e  mov     ebp, eax
0x1800f0d90  mov     [rbx], r15d
0x1800f0d93  mov     eax, [rsp+88h+arg_70]
0x1800f0d9a  mov     [rbx+4], eax
0x1800f0d9d  cmp     dword ptr [r14+8], 1
0x1800f0da2  jnz     short loc_1800F0DAA
0x1800f0da4  or      eax, 8
0x1800f0da7  mov     [rbx+4], eax
0x1800f0daa  mov     eax, 1
0x1800f0daf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800f0db7  inc     eax
0x1800f0db9  mov     [rbx+10h], eax
0x1800f0dbc  mov     rax, [rsp+88h+arg_40]
0x1800f0dc4  xor     edi, edi
0x1800f0dc6  test    rax, rax
0x1800f0dc9  jz      short loc_1800F0DD0
0x1800f0dcb  cmp     [rax], di
0x1800f0dce  jnz     short loc_1800F0DD3
0x1800f0dd0  mov     rax, rdi
0x1800f0dd3  mov     [rbx+18h], rax
0x1800f0dd7  call    cs:__imp_GetCurrentThreadId
0x1800f0ddd  mov     [rbx+20h], eax
0x1800f0de0  mov     [rbx+38h], r13
0x1800f0de4  mov     eax, [rsp+88h+arg_8]
0x1800f0deb  mov     [rbx+40h], eax
0x1800f0dee  mov     [rbx+44h], ebp
0x1800f0df1  mov     rax, [rsp+88h+arg_20]
0x1800f0df9  mov     [rbx+28h], rax
0x1800f0dfd  mov     [rbx+30h], r12
0x1800f0e01  mov     rax, [rsp+88h+arg_28]
0x1800f0e09  mov     [rbx+88h], rax
0x1800f0e10  mov     rax, [rsp+88h+arg_0]
0x1800f0e18  mov     [rbx+90h], rax
0x1800f0e1f  mov     [rbx+48h], rdi
0x1800f0e23  xorps   xmm0, xmm0
0x1800f0e26  xor     eax, eax
0x1800f0e28  movups  xmmword ptr [rbx+68h], xmm0
0x1800f0e2c  mov     [rbx+78h], rax
0x1800f0e30  movups  xmmword ptr [rbx+50h], xmm0
0x1800f0e34  mov     [rbx+60h], rax
0x1800f0e38  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800f0e3f  test    rax, rax
0x1800f0e42  jz      short loc_1800F0E4B
0x1800f0e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e49  jmp     short loc_1800F0E4E
0x1800f0e4b  mov     rax, rdi
0x1800f0e4e  mov     [rbx+80h], rax
0x1800f0e55  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800f0e5c  test    rax, rax
0x1800f0e5f  jz      short loc_1800F0E69
0x1800f0e61  mov     rcx, rbx
0x1800f0e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e69  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800f0e70  test    rax, rax
0x1800f0e73  jz      short loc_1800F0E8B
0x1800f0e75  mov     r8d, 400h
0x1800f0e7b  mov     rdx, [rsp+88h+arg_60]
0x1800f0e83  mov     rcx, rbx
0x1800f0e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e8b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f0e92  test    rax, rax
0x1800f0e95  jz      short loc_1800F0E9F
0x1800f0e97  mov     rcx, rbx
0x1800f0e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0e9f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f0ea6  test    rax, rax
0x1800f0ea9  jz      short loc_1800F0EB9
0x1800f0eab  test    byte ptr [rbx+4], 2
0x1800f0eaf  jnz     short loc_1800F0EB9
0x1800f0eb1  mov     rcx, rbx
0x1800f0eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0eb9  cmp     [rbx+8], edi
0x1800f0ebc  jl      short loc_1800F0ED8
0x1800f0ebe  cmp     r15d, 3
0x1800f0ec2  jnz     loc_1800F0FA7
0x1800f0ec8  mov     ecx, 8000FFFFh; this
0x1800f0ecd  mov     [rbx+8], ecx
0x1800f0ed0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800f0ed5  mov     [rbx+0Ch], eax
0x1800f0ed8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800f0edf  jnz     short loc_1800F0F00
0x1800f0ee1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800f0ee8  test    rax, rax
0x1800f0eeb  jz      short loc_1800F0EF6
0x1800f0eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0ef2  test    al, al
0x1800f0ef4  jmp     short loc_1800F0EFE
0x1800f0ef6  call    cs:__imp_IsDebuggerPresent
0x1800f0efc  test    eax, eax
0x1800f0efe  jz      short loc_1800F0F06
0x1800f0f00  test    byte ptr [rbx+4], 2
0x1800f0f04  jz      short loc_1800F0F2A
0x1800f0f06  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f0f0d  test    rax, rax
0x1800f0f10  jz      short loc_1800F0F6E
0x1800f0f12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800f0f19  jnz     short loc_1800F0F6E
0x1800f0f1b  xor     r8d, r8d
0x1800f0f1e  xor     edx, edx
0x1800f0f20  mov     rcx, rbx
0x1800f0f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0f28  jmp     short loc_1800F0F6E
0x1800f0f2a  mov     ebp, 800h
0x1800f0f2f  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f0f36  test    rax, rax
0x1800f0f39  jz      short loc_1800F0F52
0x1800f0f3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800f0f42  jnz     short loc_1800F0F52
0x1800f0f44  mov     r8d, ebp
0x1800f0f47  mov     rdx, rsi
0x1800f0f4a  mov     rcx, rbx
0x1800f0f4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0f52  cmp     [rsi], di
0x1800f0f55  jnz     short loc_1800F0F65
0x1800f0f57  mov     r8, rbx; unsigned __int64
0x1800f0f5a  mov     rdx, rbp; wchar_t *
0x1800f0f5d  mov     rcx, rsi; this
0x1800f0f60  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800f0f65  mov     rcx, rsi; lpOutputString
0x1800f0f68  call    cs:__imp_OutputDebugStringW
0x1800f0f6e  test    byte ptr [rbx+4], 4
0x1800f0f72  jnz     short loc_1800F0F7D
0x1800f0f74  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800f0f7b  jz      short loc_1800F0F8F
0x1800f0f7d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800f0f84  test    rax, rax
0x1800f0f87  jz      short loc_1800F0F8F
0x1800f0f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0f8e  nop
0x1800f0f8f  mov     rbx, [rsp+88h+arg_10]
0x1800f0f97  add     rsp, 50h
0x1800f0f9b  pop     r15
0x1800f0f9d  pop     r14
0x1800f0f9f  pop     r13
0x1800f0fa1  pop     r12
0x1800f0fa3  pop     rdi
0x1800f0fa4  pop     rsi
0x1800f0fa5  pop     rbp
0x1800f0fa6  retn
0x1800f0fa7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
