# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004ef8`
- end: `0x1800051f0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002898`

## callees

- `0x1800022d4`
- `0x1800044b4`
- `0x180004c4c`
- `0x180004ef8`
- `0x180005b40`
- `0x180005b60`
- `0x180005c88`
- `0x180005ca4`
- `0x180007c4c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000501b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000501b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000513a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000513a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800051ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800051ac`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180004ef8  mov     [rsp+arg_10], rbx
0x180004efd  mov     [rsp+arg_8], edx
0x180004f01  mov     [rsp+arg_0], rcx
0x180004f06  push    rbp
0x180004f07  push    rsi
0x180004f08  push    rdi
0x180004f09  push    r12
0x180004f0b  push    r13
0x180004f0d  push    r14
0x180004f0f  push    r15
0x180004f11  sub     rsp, 40h
0x180004f15  mov     r14, [rsp+78h+arg_38]
0x180004f1d  xor     eax, eax
0x180004f1f  mov     rbx, [rsp+78h+arg_78]
0x180004f27  xor     ebp, ebp
0x180004f29  mov     r15d, [rsp+78h+arg_30]
0x180004f31  mov     r10, rcx
0x180004f34  mov     rsi, [rsp+78h+lpOutputString]
0x180004f3c  mov     r12, r9
0x180004f3f  mov     r13, r8
0x180004f42  mov     ecx, r15d
0x180004f45  mov     [rsi], ax
0x180004f48  mov     rax, [rsp+78h+arg_60]
0x180004f50  mov     byte ptr [rax], 0
0x180004f53  mov     edi, [r14]
0x180004f56  mov     [rbx+8], edi
0x180004f59  mov     eax, [r14+4]
0x180004f5d  mov     [rbx+0Ch], eax
0x180004f60  test    r15d, r15d
0x180004f63  jz      short loc_180004FCB
0x180004f65  sub     ecx, 1
0x180004f68  jz      short loc_180004FC2
0x180004f6a  sub     ecx, 1
0x180004f6d  jz      short loc_180004F7D
0x180004f6f  cmp     ecx, 1
0x180004f72  jnz     short loc_180004FD4
0x180004f74  mov     ecx, edi; this
0x180004f76  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004f7b  jmp     short loc_180004FD2
0x180004f7d  test    edi, edi
0x180004f7f  js      short loc_180004FB9
0x180004f81  mov     rax, [rsp+78h+arg_28]
0x180004f89  mov     edi, 8007029Ch
0x180004f8e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004f92  mov     rcx, r10; int
0x180004f95  mov     [rsp+78h+var_50], rax; __int64
0x180004f9a  mov     rax, [rsp+78h+arg_20]
0x180004fa2  mov     [rsp+78h+var_58], rax; __int64
0x180004fa7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004fac  mov     ecx, edi; this
0x180004fae  mov     [rbx+8], edi
0x180004fb1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004fb6  mov     [rbx+0Ch], eax
0x180004fb9  mov     ecx, edi; this
0x180004fbb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004fc0  jmp     short loc_180004FD2
0x180004fc2  mov     ecx, edi; this
0x180004fc4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004fc9  jmp     short loc_180004FD2
0x180004fcb  mov     ecx, edi; this
0x180004fcd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004fd2  mov     ebp, eax
0x180004fd4  mov     eax, [rsp+78h+arg_70]
0x180004fdb  mov     [rbx+4], eax
0x180004fde  mov     [rbx], r15d
0x180004fe1  cmp     dword ptr [r14+8], 1
0x180004fe6  jnz     short loc_180004FEE
0x180004fe8  or      eax, 8
0x180004feb  mov     [rbx+4], eax
0x180004fee  mov     eax, 1
0x180004ff3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004ffb  inc     eax
0x180004ffd  xor     edi, edi
0x180004fff  mov     [rbx+10h], eax
0x180005002  mov     rax, [rsp+78h+arg_40]
0x18000500a  test    rax, rax
0x18000500d  jz      short loc_180005014
0x18000500f  cmp     [rax], di
0x180005012  jnz     short loc_180005017
0x180005014  mov     rax, rdi
0x180005017  mov     [rbx+18h], rax
0x18000501b  call    cs:__imp_GetCurrentThreadId
0x180005021  mov     [rbx+38h], r13
0x180005025  xorps   xmm0, xmm0
0x180005028  mov     [rbx+20h], eax
0x18000502b  mov     eax, [rsp+78h+arg_8]
0x180005032  mov     [rbx+40h], eax
0x180005035  mov     rax, [rsp+78h+arg_20]
0x18000503d  mov     [rbx+28h], rax
0x180005041  mov     rax, [rsp+78h+arg_28]
0x180005049  mov     [rbx+88h], rax
0x180005050  mov     rax, [rsp+78h+arg_0]
0x180005058  mov     [rbx+90h], rax
0x18000505f  xor     eax, eax
0x180005061  mov     [rbx+44h], ebp
0x180005064  mov     [rbx+30h], r12
0x180005068  mov     [rbx+48h], rdi
0x18000506c  movups  xmmword ptr [rbx+68h], xmm0
0x180005070  mov     [rbx+78h], rax
0x180005074  movups  xmmword ptr [rbx+50h], xmm0
0x180005078  mov     [rbx+60h], rax
0x18000507c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005083  test    rax, rax
0x180005086  jz      short loc_18000508F
0x180005088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000508d  jmp     short loc_180005092
0x18000508f  mov     rax, rdi
0x180005092  mov     [rbx+80h], rax
0x180005099  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800050a0  test    rax, rax
0x1800050a3  jz      short loc_1800050AD
0x1800050a5  mov     rcx, rbx
0x1800050a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800050b4  test    rax, rax
0x1800050b7  jz      short loc_1800050CF
0x1800050b9  mov     rdx, [rsp+78h+arg_60]
0x1800050c1  mov     r8d, 400h
0x1800050c7  mov     rcx, rbx
0x1800050ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050cf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800050d6  test    rax, rax
0x1800050d9  jz      short loc_1800050E3
0x1800050db  mov     rcx, rbx
0x1800050de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800050ea  test    rax, rax
0x1800050ed  jz      short loc_1800050FD
0x1800050ef  test    byte ptr [rbx+4], 2
0x1800050f3  jnz     short loc_1800050FD
0x1800050f5  mov     rcx, rbx
0x1800050f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050fd  cmp     [rbx+8], edi
0x180005100  jl      short loc_18000511C
0x180005102  cmp     r15d, 3
0x180005106  jnz     loc_1800051EA
0x18000510c  mov     ecx, 8000FFFFh; this
0x180005111  mov     [rbx+8], ecx
0x180005114  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005119  mov     [rbx+0Ch], eax
0x18000511c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005123  jnz     short loc_180005144
0x180005125  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000512c  test    rax, rax
0x18000512f  jz      short loc_18000513A
0x180005131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005136  test    al, al
0x180005138  jmp     short loc_180005142
0x18000513a  call    cs:__imp_IsDebuggerPresent
0x180005140  test    eax, eax
0x180005142  jz      short loc_18000514A
0x180005144  test    byte ptr [rbx+4], 2
0x180005148  jz      short loc_18000516E
0x18000514a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005151  test    rax, rax
0x180005154  jz      short loc_1800051B2
0x180005156  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000515d  jnz     short loc_1800051B2
0x18000515f  xor     r8d, r8d
0x180005162  xor     edx, edx
0x180005164  mov     rcx, rbx
0x180005167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000516c  jmp     short loc_1800051B2
0x18000516e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005175  mov     ebp, 800h
0x18000517a  test    rax, rax
0x18000517d  jz      short loc_180005196
0x18000517f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005186  jnz     short loc_180005196
0x180005188  mov     r8d, ebp
0x18000518b  mov     rdx, rsi
0x18000518e  mov     rcx, rbx
0x180005191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005196  cmp     [rsi], di
0x180005199  jnz     short loc_1800051A9
0x18000519b  mov     r8, rbx; unsigned __int64
0x18000519e  mov     rdx, rbp; unsigned __int16 *
0x1800051a1  mov     rcx, rsi; this
0x1800051a4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800051a9  mov     rcx, rsi; lpOutputString
0x1800051ac  call    cs:__imp_OutputDebugStringW
0x1800051b2  test    byte ptr [rbx+4], 4
0x1800051b6  jnz     short loc_1800051C1
0x1800051b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800051bf  jz      short loc_1800051D2
0x1800051c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800051c8  test    rax, rax
0x1800051cb  jz      short loc_1800051D2
0x1800051cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d2  mov     rbx, [rsp+78h+arg_10]
0x1800051da  add     rsp, 40h
0x1800051de  pop     r15
0x1800051e0  pop     r14
0x1800051e2  pop     r13
0x1800051e4  pop     r12
0x1800051e6  pop     rdi
0x1800051e7  pop     rsi
0x1800051e8  pop     rbp
0x1800051e9  retn
0x1800051ea  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
