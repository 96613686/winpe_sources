# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800042cc`
- end: `0x1800045c4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180002a3c`
- `0x180002d80`

## callees

- `0x18000297c`
- `0x180003924`
- `0x180004108`
- `0x1800042cc`
- `0x180004a00`
- `0x180004a20`
- `0x180004a34`
- `0x180004a50`
- `0x180005434`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000450e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000450e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004580`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004580`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x1800042cc  mov     [rsp+arg_10], rbx
0x1800042d1  mov     [rsp+arg_8], edx
0x1800042d5  mov     [rsp+arg_0], rcx
0x1800042da  push    rbp
0x1800042db  push    rsi
0x1800042dc  push    rdi
0x1800042dd  push    r12
0x1800042df  push    r13
0x1800042e1  push    r14
0x1800042e3  push    r15
0x1800042e5  sub     rsp, 40h
0x1800042e9  mov     r14, [rsp+78h+arg_38]
0x1800042f1  xor     eax, eax
0x1800042f3  mov     rbx, [rsp+78h+arg_78]
0x1800042fb  xor     ebp, ebp
0x1800042fd  mov     r15d, [rsp+78h+arg_30]
0x180004305  mov     r10, rcx
0x180004308  mov     rsi, [rsp+78h+lpOutputString]
0x180004310  mov     r12, r9
0x180004313  mov     r13, r8
0x180004316  mov     ecx, r15d
0x180004319  mov     [rsi], ax
0x18000431c  mov     rax, [rsp+78h+arg_60]
0x180004324  mov     byte ptr [rax], 0
0x180004327  mov     edi, [r14]
0x18000432a  mov     [rbx+8], edi
0x18000432d  mov     eax, [r14+4]
0x180004331  mov     [rbx+0Ch], eax
0x180004334  test    r15d, r15d
0x180004337  jz      short loc_18000439F
0x180004339  sub     ecx, 1
0x18000433c  jz      short loc_180004396
0x18000433e  sub     ecx, 1
0x180004341  jz      short loc_180004351
0x180004343  cmp     ecx, 1
0x180004346  jnz     short loc_1800043A8
0x180004348  mov     ecx, edi; this
0x18000434a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000434f  jmp     short loc_1800043A6
0x180004351  test    edi, edi
0x180004353  js      short loc_18000438D
0x180004355  mov     rax, [rsp+78h+arg_28]
0x18000435d  mov     edi, 8007029Ch
0x180004362  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004366  mov     rcx, r10; int
0x180004369  mov     [rsp+78h+var_50], rax; __int64
0x18000436e  mov     rax, [rsp+78h+arg_20]
0x180004376  mov     [rsp+78h+var_58], rax; __int64
0x18000437b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004380  mov     ecx, edi; this
0x180004382  mov     [rbx+8], edi
0x180004385  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000438a  mov     [rbx+0Ch], eax
0x18000438d  mov     ecx, edi; this
0x18000438f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004394  jmp     short loc_1800043A6
0x180004396  mov     ecx, edi; this
0x180004398  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000439d  jmp     short loc_1800043A6
0x18000439f  mov     ecx, edi; this
0x1800043a1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800043a6  mov     ebp, eax
0x1800043a8  mov     eax, [rsp+78h+arg_70]
0x1800043af  mov     [rbx+4], eax
0x1800043b2  mov     [rbx], r15d
0x1800043b5  cmp     dword ptr [r14+8], 1
0x1800043ba  jnz     short loc_1800043C2
0x1800043bc  or      eax, 8
0x1800043bf  mov     [rbx+4], eax
0x1800043c2  mov     eax, 1
0x1800043c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800043cf  inc     eax
0x1800043d1  xor     edi, edi
0x1800043d3  mov     [rbx+10h], eax
0x1800043d6  mov     rax, [rsp+78h+arg_40]
0x1800043de  test    rax, rax
0x1800043e1  jz      short loc_1800043E8
0x1800043e3  cmp     [rax], di
0x1800043e6  jnz     short loc_1800043EB
0x1800043e8  mov     rax, rdi
0x1800043eb  mov     [rbx+18h], rax
0x1800043ef  call    cs:__imp_GetCurrentThreadId
0x1800043f5  mov     [rbx+38h], r13
0x1800043f9  xorps   xmm0, xmm0
0x1800043fc  mov     [rbx+20h], eax
0x1800043ff  mov     eax, [rsp+78h+arg_8]
0x180004406  mov     [rbx+40h], eax
0x180004409  mov     rax, [rsp+78h+arg_20]
0x180004411  mov     [rbx+28h], rax
0x180004415  mov     rax, [rsp+78h+arg_28]
0x18000441d  mov     [rbx+88h], rax
0x180004424  mov     rax, [rsp+78h+arg_0]
0x18000442c  mov     [rbx+90h], rax
0x180004433  xor     eax, eax
0x180004435  mov     [rbx+44h], ebp
0x180004438  mov     [rbx+30h], r12
0x18000443c  mov     [rbx+48h], rdi
0x180004440  movups  xmmword ptr [rbx+68h], xmm0
0x180004444  mov     [rbx+78h], rax
0x180004448  movups  xmmword ptr [rbx+50h], xmm0
0x18000444c  mov     [rbx+60h], rax
0x180004450  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004457  test    rax, rax
0x18000445a  jz      short loc_180004463
0x18000445c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004461  jmp     short loc_180004466
0x180004463  mov     rax, rdi
0x180004466  mov     [rbx+80h], rax
0x18000446d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004474  test    rax, rax
0x180004477  jz      short loc_180004481
0x180004479  mov     rcx, rbx
0x18000447c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004481  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004488  test    rax, rax
0x18000448b  jz      short loc_1800044A3
0x18000448d  mov     rdx, [rsp+78h+arg_60]
0x180004495  mov     r8d, 400h
0x18000449b  mov     rcx, rbx
0x18000449e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800044aa  test    rax, rax
0x1800044ad  jz      short loc_1800044B7
0x1800044af  mov     rcx, rbx
0x1800044b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800044be  test    rax, rax
0x1800044c1  jz      short loc_1800044D1
0x1800044c3  test    byte ptr [rbx+4], 2
0x1800044c7  jnz     short loc_1800044D1
0x1800044c9  mov     rcx, rbx
0x1800044cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d1  cmp     [rbx+8], edi
0x1800044d4  jl      short loc_1800044F0
0x1800044d6  cmp     r15d, 3
0x1800044da  jnz     loc_1800045BE
0x1800044e0  mov     ecx, 8000FFFFh; this
0x1800044e5  mov     [rbx+8], ecx
0x1800044e8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800044ed  mov     [rbx+0Ch], eax
0x1800044f0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800044f7  jnz     short loc_180004518
0x1800044f9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004500  test    rax, rax
0x180004503  jz      short loc_18000450E
0x180004505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000450a  test    al, al
0x18000450c  jmp     short loc_180004516
0x18000450e  call    cs:__imp_IsDebuggerPresent
0x180004514  test    eax, eax
0x180004516  jz      short loc_18000451E
0x180004518  test    byte ptr [rbx+4], 2
0x18000451c  jz      short loc_180004542
0x18000451e  mov     rax, cs:g_pfnResultLoggingCallback
0x180004525  test    rax, rax
0x180004528  jz      short loc_180004586
0x18000452a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004531  jnz     short loc_180004586
0x180004533  xor     r8d, r8d
0x180004536  xor     edx, edx
0x180004538  mov     rcx, rbx
0x18000453b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004540  jmp     short loc_180004586
0x180004542  mov     rax, cs:g_pfnResultLoggingCallback
0x180004549  mov     ebp, 800h
0x18000454e  test    rax, rax
0x180004551  jz      short loc_18000456A
0x180004553  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000455a  jnz     short loc_18000456A
0x18000455c  mov     r8d, ebp
0x18000455f  mov     rdx, rsi
0x180004562  mov     rcx, rbx
0x180004565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000456a  cmp     [rsi], di
0x18000456d  jnz     short loc_18000457D
0x18000456f  mov     r8, rbx; unsigned __int64
0x180004572  mov     rdx, rbp; unsigned __int16 *
0x180004575  mov     rcx, rsi; this
0x180004578  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000457d  mov     rcx, rsi; lpOutputString
0x180004580  call    cs:__imp_OutputDebugStringW
0x180004586  test    byte ptr [rbx+4], 4
0x18000458a  jnz     short loc_180004595
0x18000458c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004593  jz      short loc_1800045A6
0x180004595  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000459c  test    rax, rax
0x18000459f  jz      short loc_1800045A6
0x1800045a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a6  mov     rbx, [rsp+78h+arg_10]
0x1800045ae  add     rsp, 40h
0x1800045b2  pop     r15
0x1800045b4  pop     r14
0x1800045b6  pop     r13
0x1800045b8  pop     r12
0x1800045ba  pop     rdi
0x1800045bb  pop     rsi
0x1800045bc  pop     rbp
0x1800045bd  retn
0x1800045be  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
