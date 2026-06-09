# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18009c4b4`
- end: `0x18009c7db`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180098168`

## callees

- `0x180097b9c`
- `0x18009a62c`
- `0x18009bf50`
- `0x18009c4b4`
- `0x18009d0d0`
- `0x18009d0f0`
- `0x18009d104`
- `0x18009d124`
- `0x18009e6c0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c5ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009c5ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009c717`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18009c717`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18009c78f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18009c78f`

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
  unsigned int v17; // edi
  int v18; // ebp
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  int v22; // edx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-58h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v18 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v17, a2);
        break;
      case 2:
        if ( (v17 & 0x80000000) == 0 )
        {
          v17 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v17, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v17, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v17, a2);
  }
  v18 = v19;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v18;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v22);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
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
0x18009c4b4  mov     rax, rsp
0x18009c4b7  mov     [rax+18h], r8
0x18009c4bb  mov     [rax+10h], edx
0x18009c4be  mov     [rax+8], rcx
0x18009c4c2  push    rbp
0x18009c4c3  push    rsi
0x18009c4c4  push    rdi
0x18009c4c5  push    r12
0x18009c4c7  push    r13
0x18009c4c9  push    r14
0x18009c4cb  push    r15
0x18009c4cd  sub     rsp, 50h
0x18009c4d1  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18009c4d9  mov     [rax+20h], rbx
0x18009c4dd  mov     r13, r9
0x18009c4e0  mov     r10, rcx
0x18009c4e3  mov     r14d, [rsp+88h+arg_70]
0x18009c4eb  xor     r9d, r9d
0x18009c4ee  mov     rsi, [rsp+88h+lpOutputString]
0x18009c4f6  mov     [rsi], r9w
0x18009c4fa  mov     rax, [rsp+88h+arg_60]
0x18009c502  mov     [rax], r9b
0x18009c505  mov     r15, [rsp+88h+arg_38]
0x18009c50d  mov     edi, [r15]
0x18009c510  mov     rbx, [rsp+88h+arg_78]
0x18009c518  mov     [rbx+8], edi
0x18009c51b  mov     eax, [r15+4]
0x18009c51f  mov     [rbx+0Ch], eax
0x18009c522  mov     ebp, r9d
0x18009c525  mov     r12d, [rsp+88h+arg_30]
0x18009c52d  mov     ecx, r12d
0x18009c530  test    r12d, r12d
0x18009c533  jz      short loc_18009C59E
0x18009c535  sub     ecx, 1
0x18009c538  jz      short loc_18009C595
0x18009c53a  sub     ecx, 1
0x18009c53d  jz      short loc_18009C54D
0x18009c53f  cmp     ecx, 1
0x18009c542  jnz     short loc_18009C5A7
0x18009c544  mov     ecx, edi; this
0x18009c546  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18009c54b  jmp     short loc_18009C5A5
0x18009c54d  test    edi, edi
0x18009c54f  js      short loc_18009C58C
0x18009c551  mov     edi, 8007029Ch
0x18009c556  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18009c55a  mov     rax, [rsp+88h+arg_28]
0x18009c562  mov     [rsp+88h+var_60], rax; __int64
0x18009c567  mov     rax, [rsp+88h+arg_20]
0x18009c56f  mov     [rsp+88h+var_68], rax; __int64
0x18009c574  mov     r9, r13; int
0x18009c577  mov     rcx, r10; int
0x18009c57a  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18009c57f  mov     [rbx+8], edi
0x18009c582  mov     ecx, edi; this
0x18009c584  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18009c589  mov     [rbx+0Ch], eax
0x18009c58c  mov     ecx, edi; this
0x18009c58e  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18009c593  jmp     short loc_18009C5A5
0x18009c595  mov     ecx, edi; this
0x18009c597  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18009c59c  jmp     short loc_18009C5A5
0x18009c59e  mov     ecx, edi; this
0x18009c5a0  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18009c5a5  mov     ebp, eax
0x18009c5a7  mov     [rbx], r12d
0x18009c5aa  mov     [rbx+4], r14d
0x18009c5ae  cmp     dword ptr [r15+8], 1
0x18009c5b3  jnz     short loc_18009C5BD
0x18009c5b5  or      r14d, 8
0x18009c5b9  mov     [rbx+4], r14d
0x18009c5bd  mov     eax, 1
0x18009c5c2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18009c5ca  inc     eax
0x18009c5cc  mov     [rbx+10h], eax
0x18009c5cf  mov     rax, [rsp+88h+arg_40]
0x18009c5d7  xor     edi, edi
0x18009c5d9  test    rax, rax
0x18009c5dc  jz      short loc_18009C5E3
0x18009c5de  cmp     [rax], di
0x18009c5e1  jnz     short loc_18009C5E6
0x18009c5e3  mov     rax, rdi
0x18009c5e6  mov     [rbx+18h], rax
0x18009c5ea  call    cs:__imp_GetCurrentThreadId
0x18009c5f1  nop     dword ptr [rax+rax+00h]
0x18009c5f6  mov     [rbx+20h], eax
0x18009c5f9  mov     rax, [rsp+88h+arg_10]
0x18009c601  mov     [rbx+38h], rax
0x18009c605  mov     eax, [rsp+88h+arg_8]
0x18009c60c  mov     [rbx+40h], eax
0x18009c60f  mov     [rbx+44h], ebp
0x18009c612  mov     rax, [rsp+88h+arg_20]
0x18009c61a  mov     [rbx+28h], rax
0x18009c61e  mov     [rbx+30h], r13
0x18009c622  mov     rax, [rsp+88h+arg_28]
0x18009c62a  mov     [rbx+88h], rax
0x18009c631  mov     rax, [rsp+88h+arg_0]
0x18009c639  mov     [rbx+90h], rax
0x18009c640  mov     [rbx+48h], rdi
0x18009c644  xorps   xmm0, xmm0
0x18009c647  xor     eax, eax
0x18009c649  movups  xmmword ptr [rbx+68h], xmm0
0x18009c64d  mov     [rbx+78h], rax
0x18009c651  movups  xmmword ptr [rbx+50h], xmm0
0x18009c655  mov     [rbx+60h], rax
0x18009c659  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18009c660  test    rax, rax
0x18009c663  jz      short loc_18009C66C
0x18009c665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c66a  jmp     short loc_18009C66F
0x18009c66c  mov     rax, rdi
0x18009c66f  mov     [rbx+80h], rax
0x18009c676  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18009c67d  test    rax, rax
0x18009c680  jz      short loc_18009C68A
0x18009c682  mov     rcx, rbx
0x18009c685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c68a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18009c691  test    rax, rax
0x18009c694  jz      short loc_18009C6AC
0x18009c696  mov     r8d, 400h
0x18009c69c  mov     rdx, [rsp+88h+arg_60]
0x18009c6a4  mov     rcx, rbx
0x18009c6a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c6ac  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18009c6b3  test    rax, rax
0x18009c6b6  jz      short loc_18009C6C0
0x18009c6b8  mov     rcx, rbx
0x18009c6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c6c0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18009c6c7  test    rax, rax
0x18009c6ca  jz      short loc_18009C6DA
0x18009c6cc  test    byte ptr [rbx+4], 2
0x18009c6d0  jnz     short loc_18009C6DA
0x18009c6d2  mov     rcx, rbx
0x18009c6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c6da  cmp     [rbx+8], edi
0x18009c6dd  jl      short loc_18009C6F9
0x18009c6df  cmp     r12d, 3
0x18009c6e3  jnz     loc_18009C7D5
0x18009c6e9  mov     ecx, 8000FFFFh; this
0x18009c6ee  mov     [rbx+8], ecx
0x18009c6f1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18009c6f6  mov     [rbx+0Ch], eax
0x18009c6f9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18009c700  jnz     short loc_18009C727
0x18009c702  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18009c709  test    rax, rax
0x18009c70c  jz      short loc_18009C717
0x18009c70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c713  test    al, al
0x18009c715  jmp     short loc_18009C725
0x18009c717  call    cs:__imp_IsDebuggerPresent
0x18009c71e  nop     dword ptr [rax+rax+00h]
0x18009c723  test    eax, eax
0x18009c725  jz      short loc_18009C72D
0x18009c727  test    byte ptr [rbx+4], 2
0x18009c72b  jz      short loc_18009C751
0x18009c72d  mov     rax, cs:g_pfnResultLoggingCallback
0x18009c734  test    rax, rax
0x18009c737  jz      short loc_18009C79B
0x18009c739  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18009c740  jnz     short loc_18009C79B
0x18009c742  xor     r8d, r8d
0x18009c745  xor     edx, edx
0x18009c747  mov     rcx, rbx
0x18009c74a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c74f  jmp     short loc_18009C79B
0x18009c751  mov     ebp, 800h
0x18009c756  mov     rax, cs:g_pfnResultLoggingCallback
0x18009c75d  test    rax, rax
0x18009c760  jz      short loc_18009C779
0x18009c762  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18009c769  jnz     short loc_18009C779
0x18009c76b  mov     r8d, ebp
0x18009c76e  mov     rdx, rsi
0x18009c771  mov     rcx, rbx
0x18009c774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c779  cmp     [rsi], di
0x18009c77c  jnz     short loc_18009C78C
0x18009c77e  mov     r8, rbx; unsigned __int64
0x18009c781  mov     rdx, rbp; unsigned __int16 *
0x18009c784  mov     rcx, rsi; this
0x18009c787  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18009c78c  mov     rcx, rsi; lpOutputString
0x18009c78f  call    cs:__imp_OutputDebugStringW
0x18009c796  nop     dword ptr [rax+rax+00h]
0x18009c79b  test    byte ptr [rbx+4], 4
0x18009c79f  jnz     short loc_18009C7AA
0x18009c7a1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18009c7a8  jz      short loc_18009C7BC
0x18009c7aa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18009c7b1  test    rax, rax
0x18009c7b4  jz      short loc_18009C7BC
0x18009c7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c7bb  nop
0x18009c7bc  mov     rbx, [rsp+88h+arg_18]
0x18009c7c4  add     rsp, 50h
0x18009c7c8  pop     r15
0x18009c7ca  pop     r14
0x18009c7cc  pop     r13
0x18009c7ce  pop     r12
0x18009c7d0  pop     rdi
0x18009c7d1  pop     rsi
0x18009c7d2  pop     rbp
0x18009c7d3  retn
0x18009c7d5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
