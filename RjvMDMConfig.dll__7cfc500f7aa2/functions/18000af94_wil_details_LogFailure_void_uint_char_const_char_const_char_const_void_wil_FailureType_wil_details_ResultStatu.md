# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000af94`
- end: `0x18000b29f`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006a88`
- `0x180006ddc`
- `0x180015ca4`

## callees

- `0x180003be4`
- `0x180003fa4`
- `0x180004b90`
- `0x1800069c8`
- `0x18000af94`
- `0x18000be64`
- `0x18000bfd0`
- `0x18000bff0`
- `0x18001132c`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b0b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b254`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b254`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b1dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b1dc`

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
0x18000af94  mov     [rsp+arg_10], rbx
0x18000af99  mov     [rsp+arg_8], edx
0x18000af9d  mov     [rsp+arg_0], rcx
0x18000afa2  push    rbp
0x18000afa3  push    rsi
0x18000afa4  push    rdi
0x18000afa5  push    r12
0x18000afa7  push    r13
0x18000afa9  push    r14
0x18000afab  push    r15
0x18000afad  sub     rsp, 40h
0x18000afb1  mov     r14, [rsp+78h+arg_38]
0x18000afb9  xor     eax, eax
0x18000afbb  mov     rbx, [rsp+78h+arg_78]
0x18000afc3  xor     ebp, ebp
0x18000afc5  mov     r15d, [rsp+78h+arg_30]
0x18000afcd  mov     r10, rcx
0x18000afd0  mov     rsi, [rsp+78h+lpOutputString]
0x18000afd8  mov     r12, r9
0x18000afdb  mov     r13, r8
0x18000afde  mov     ecx, r15d
0x18000afe1  mov     [rsi], ax
0x18000afe4  mov     rax, [rsp+78h+arg_60]
0x18000afec  mov     byte ptr [rax], 0
0x18000afef  mov     edi, [r14]
0x18000aff2  mov     [rbx+8], edi
0x18000aff5  mov     eax, [r14+4]
0x18000aff9  mov     [rbx+0Ch], eax
0x18000affc  test    r15d, r15d
0x18000afff  jz      short loc_18000B067
0x18000b001  sub     ecx, 1
0x18000b004  jz      short loc_18000B05E
0x18000b006  sub     ecx, 1
0x18000b009  jz      short loc_18000B019
0x18000b00b  cmp     ecx, 1
0x18000b00e  jnz     short loc_18000B070
0x18000b010  mov     ecx, edi; this
0x18000b012  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000b017  jmp     short loc_18000B06E
0x18000b019  test    edi, edi
0x18000b01b  js      short loc_18000B055
0x18000b01d  mov     rax, [rsp+78h+arg_28]
0x18000b025  mov     edi, 8007029Ch
0x18000b02a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000b02e  mov     rcx, r10; int
0x18000b031  mov     [rsp+78h+var_50], rax; __int64
0x18000b036  mov     rax, [rsp+78h+arg_20]
0x18000b03e  mov     [rsp+78h+var_58], rax; __int64
0x18000b043  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000b048  mov     ecx, edi; this
0x18000b04a  mov     [rbx+8], edi
0x18000b04d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b052  mov     [rbx+0Ch], eax
0x18000b055  mov     ecx, edi; this
0x18000b057  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000b05c  jmp     short loc_18000B06E
0x18000b05e  mov     ecx, edi; this
0x18000b060  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b065  jmp     short loc_18000B06E
0x18000b067  mov     ecx, edi; this
0x18000b069  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b06e  mov     ebp, eax
0x18000b070  mov     eax, [rsp+78h+arg_70]
0x18000b077  mov     [rbx+4], eax
0x18000b07a  mov     [rbx], r15d
0x18000b07d  cmp     dword ptr [r14+8], 1
0x18000b082  jnz     short loc_18000B08A
0x18000b084  or      eax, 8
0x18000b087  mov     [rbx+4], eax
0x18000b08a  mov     eax, 1
0x18000b08f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b097  inc     eax
0x18000b099  xor     edi, edi
0x18000b09b  mov     [rbx+10h], eax
0x18000b09e  mov     rax, [rsp+78h+arg_40]
0x18000b0a6  test    rax, rax
0x18000b0a9  jz      short loc_18000B0B0
0x18000b0ab  cmp     [rax], di
0x18000b0ae  jnz     short loc_18000B0B3
0x18000b0b0  mov     rax, rdi
0x18000b0b3  mov     [rbx+18h], rax
0x18000b0b7  call    cs:__imp_GetCurrentThreadId
0x18000b0be  nop     dword ptr [rax+rax+00h]
0x18000b0c3  mov     [rbx+38h], r13
0x18000b0c7  xorps   xmm0, xmm0
0x18000b0ca  mov     [rbx+20h], eax
0x18000b0cd  mov     eax, [rsp+78h+arg_8]
0x18000b0d4  mov     [rbx+40h], eax
0x18000b0d7  mov     rax, [rsp+78h+arg_20]
0x18000b0df  mov     [rbx+28h], rax
0x18000b0e3  mov     rax, [rsp+78h+arg_28]
0x18000b0eb  mov     [rbx+88h], rax
0x18000b0f2  mov     rax, [rsp+78h+arg_0]
0x18000b0fa  mov     [rbx+90h], rax
0x18000b101  xor     eax, eax
0x18000b103  mov     [rbx+44h], ebp
0x18000b106  mov     [rbx+30h], r12
0x18000b10a  mov     [rbx+48h], rdi
0x18000b10e  movups  xmmword ptr [rbx+68h], xmm0
0x18000b112  mov     [rbx+78h], rax
0x18000b116  movups  xmmword ptr [rbx+50h], xmm0
0x18000b11a  mov     [rbx+60h], rax
0x18000b11e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b125  test    rax, rax
0x18000b128  jz      short loc_18000B131
0x18000b12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b12f  jmp     short loc_18000B134
0x18000b131  mov     rax, rdi
0x18000b134  mov     [rbx+80h], rax
0x18000b13b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b142  test    rax, rax
0x18000b145  jz      short loc_18000B14F
0x18000b147  mov     rcx, rbx
0x18000b14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b14f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b156  test    rax, rax
0x18000b159  jz      short loc_18000B171
0x18000b15b  mov     rdx, [rsp+78h+arg_60]
0x18000b163  mov     r8d, 400h
0x18000b169  mov     rcx, rbx
0x18000b16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b171  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b178  test    rax, rax
0x18000b17b  jz      short loc_18000B185
0x18000b17d  mov     rcx, rbx
0x18000b180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b185  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b18c  test    rax, rax
0x18000b18f  jz      short loc_18000B19F
0x18000b191  test    byte ptr [rbx+4], 2
0x18000b195  jnz     short loc_18000B19F
0x18000b197  mov     rcx, rbx
0x18000b19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b19f  cmp     [rbx+8], edi
0x18000b1a2  jl      short loc_18000B1BE
0x18000b1a4  cmp     r15d, 3
0x18000b1a8  jnz     loc_18000B299
0x18000b1ae  mov     ecx, 8000FFFFh; this
0x18000b1b3  mov     [rbx+8], ecx
0x18000b1b6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b1bb  mov     [rbx+0Ch], eax
0x18000b1be  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000b1c5  jnz     short loc_18000B1EC
0x18000b1c7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b1ce  test    rax, rax
0x18000b1d1  jz      short loc_18000B1DC
0x18000b1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1d8  test    al, al
0x18000b1da  jmp     short loc_18000B1EA
0x18000b1dc  call    cs:__imp_IsDebuggerPresent
0x18000b1e3  nop     dword ptr [rax+rax+00h]
0x18000b1e8  test    eax, eax
0x18000b1ea  jz      short loc_18000B1F2
0x18000b1ec  test    byte ptr [rbx+4], 2
0x18000b1f0  jz      short loc_18000B216
0x18000b1f2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b1f9  test    rax, rax
0x18000b1fc  jz      short loc_18000B260
0x18000b1fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b205  jnz     short loc_18000B260
0x18000b207  xor     r8d, r8d
0x18000b20a  xor     edx, edx
0x18000b20c  mov     rcx, rbx
0x18000b20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b214  jmp     short loc_18000B260
0x18000b216  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b21d  mov     ebp, 800h
0x18000b222  test    rax, rax
0x18000b225  jz      short loc_18000B23E
0x18000b227  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000b22e  jnz     short loc_18000B23E
0x18000b230  mov     r8d, ebp
0x18000b233  mov     rdx, rsi
0x18000b236  mov     rcx, rbx
0x18000b239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b23e  cmp     [rsi], di
0x18000b241  jnz     short loc_18000B251
0x18000b243  mov     r8, rbx; unsigned __int64
0x18000b246  mov     rdx, rbp; unsigned __int16 *
0x18000b249  mov     rcx, rsi; this
0x18000b24c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b251  mov     rcx, rsi; lpOutputString
0x18000b254  call    cs:__imp_OutputDebugStringW
0x18000b25b  nop     dword ptr [rax+rax+00h]
0x18000b260  test    byte ptr [rbx+4], 4
0x18000b264  jnz     short loc_18000B26F
0x18000b266  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000b26d  jz      short loc_18000B280
0x18000b26f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b276  test    rax, rax
0x18000b279  jz      short loc_18000B280
0x18000b27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b280  mov     rbx, [rsp+78h+arg_10]
0x18000b288  add     rsp, 40h
0x18000b28c  pop     r15
0x18000b28e  pop     r14
0x18000b290  pop     r13
0x18000b292  pop     r12
0x18000b294  pop     rdi
0x18000b295  pop     rsi
0x18000b296  pop     rbp
0x18000b297  retn
0x18000b299  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
