# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,long,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18001fba0`
- end: `0x18001fe30`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@JPEBG_NPEAG_KPEAD6PEAUFailureInfo@2@@Z`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001fe30`

## callees

- `0x18001eff0`
- `0x18001f320`
- `0x18001f338`
- `0x18001f350`
- `0x18001f370`
- `0x18001fba0`
- `0x18001ff34`
- `0x180020234`
- `0x180026f6c`
- `0x180027910`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18001fe13`
- `KERNEL32!OutputDebugStringW` at `0x18001fe13`
- `KERNEL32!GetCurrentThreadId` at `0x18001fcab`
- `KERNEL32!GetCurrentThreadId` at `0x18001fcab`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int a8,
        _WORD *a9,
        char a10,
        wil *lpOutputString,
        __int64 a12,
        char *a13,
        __int64 a14,
        unsigned __int64 a15)
{
  int v17; // edx
  int v19; // esi
  unsigned int v20; // edi
  int v21; // eax
  char v22; // di
  _WORD *v23; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  const char *ModuleName; // rax
  void (__fastcall *v28)(unsigned __int64, wil *, __int64); // rax

  v17 = a5;
  v19 = 0;
  v20 = a8;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  switch ( a7 )
  {
    case 0:
      v21 = wil::details::RecordException((wil::details *)a8, a5);
      goto LABEL_11;
    case 1:
      v21 = wil::details::RecordReturn((wil::details *)a8, a5);
      goto LABEL_11;
    case 2:
      if ( (a8 & 0x80000000) == 0 )
      {
        v20 = -2147024228;
        wil::details::ReportFailure_Hr(a1, a2, a3);
      }
      v21 = wil::details::RecordLog((wil::details *)v20, v17);
      goto LABEL_11;
    case 3:
      v21 = wil::details::RecordFailFast((wil::details *)a8, a5);
LABEL_11:
      v19 = v21;
      break;
  }
  *(_DWORD *)(a15 + 4) = v20;
  v22 = 1;
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 8) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v23 = a9;
  if ( !a9 || !*a9 )
    v23 = 0;
  *(_QWORD *)(a15 + 16) = v23;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a15 + 60) = v19;
  *(_DWORD *)(a15 + 24) = CurrentThreadId;
  *(_QWORD *)(a15 + 32) = a5;
  *(_QWORD *)(a15 + 40) = a4;
  *(_QWORD *)(a15 + 128) = a6;
  *(_QWORD *)(a15 + 48) = a3;
  *(_DWORD *)(a15 + 56) = a2;
  *(_QWORD *)(a15 + 136) = a1;
  *(_QWORD *)(a15 + 64) = 0;
  memset_0((void *)(a15 + 72), 0, 0x30u);
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 120) = ModuleName;
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure((struct wil::FailureInfo *)a15, a13, 0x400u);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback((const struct wil::FailureInfo *)a15);
  if ( *(int *)(a15 + 4) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a15 + 4) = -2147418113;
  }
  if ( wil::g_fResultOutputDebugString )
    goto LABEL_32;
  v28 = (void (__fastcall *)(unsigned __int64, wil *, __int64))g_pfnResultLoggingCallback;
  if ( wil::details::g_pfnTelemetryCallback || g_pfnResultLoggingCallback )
  {
    if ( !wil::g_pfnShouldOutputDebugString )
    {
LABEL_31:
      v22 = 0;
      goto LABEL_33;
    }
    if ( !wil::g_pfnShouldOutputDebugString() )
    {
      v28 = (void (__fastcall *)(unsigned __int64, wil *, __int64))g_pfnResultLoggingCallback;
      goto LABEL_31;
    }
LABEL_32:
    v28 = (void (__fastcall *)(unsigned __int64, wil *, __int64))g_pfnResultLoggingCallback;
  }
LABEL_33:
  if ( a10 || v22 )
  {
    if ( v28 && !wil::details::g_resultMessageCallbackSet )
      v28(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v26);
    if ( v22 )
      OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( v28 )
  {
    if ( !wil::details::g_resultMessageCallbackSet )
      v28(a15, 0, 0);
  }
}

```

## disassembly

```asm
0x18001fba0  push    rbx
0x18001fba2  push    rbp
0x18001fba3  push    rsi
0x18001fba4  push    rdi
0x18001fba5  push    r12
0x18001fba7  push    r13
0x18001fba9  push    r14
0x18001fbab  push    r15
0x18001fbad  sub     rsp, 68h
0x18001fbb1  mov     rax, [rsp+0A8h+arg_60]
0x18001fbb9  xor     r10d, r10d
0x18001fbbc  mov     ebp, [rsp+0A8h+arg_30]
0x18001fbc3  mov     r13, r8
0x18001fbc6  mov     r14, [rsp+0A8h+lpOutputString]
0x18001fbce  mov     r12d, edx
0x18001fbd1  mov     rdx, [rsp+0A8h+arg_20]; int
0x18001fbd9  mov     r15, rcx
0x18001fbdc  mov     r8, [rsp+0A8h+arg_28]
0x18001fbe4  mov     esi, r10d
0x18001fbe7  mov     rbx, [rsp+0A8h+arg_70]
0x18001fbef  mov     ecx, ebp
0x18001fbf1  mov     edi, dword ptr [rsp+0A8h+arg_38]
0x18001fbf8  mov     [r14], r10w
0x18001fbfc  mov     [rax], r10b
0x18001fbff  mov     [rsp+0A8h+var_60], r9
0x18001fc04  mov     [rsp+0A8h+var_68], rdx
0x18001fc09  mov     [rsp+0A8h+var_58], r8
0x18001fc0e  mov     [rsp+0A8h+var_50], rax
0x18001fc13  test    ebp, ebp
0x18001fc15  jz      short loc_18001FC6E
0x18001fc17  sub     ecx, 1
0x18001fc1a  jz      short loc_18001FC65
0x18001fc1c  sub     ecx, 1
0x18001fc1f  jz      short loc_18001FC2F
0x18001fc21  cmp     ecx, 1
0x18001fc24  jnz     short loc_18001FC77
0x18001fc26  mov     ecx, edi; this
0x18001fc28  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001fc2d  jmp     short loc_18001FC75
0x18001fc2f  test    edi, edi
0x18001fc31  js      short loc_18001FC5C
0x18001fc33  mov     edi, 8007029Ch
0x18001fc38  mov     rcx, r15
0x18001fc3b  mov     [rsp+0A8h+var_70], edi
0x18001fc3f  mov     [rsp+0A8h+var_78], 2
0x18001fc47  mov     [rsp+0A8h+var_80], r8
0x18001fc4c  mov     r8, r13
0x18001fc4f  mov     [rsp+0A8h+var_88], rdx
0x18001fc54  mov     edx, r12d
0x18001fc57  call    ?ReportFailure_Hr@details@wil@@YAXPEAXIPEBD110W4FailureType@2@J@Z; wil::details::ReportFailure_Hr(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,long)
0x18001fc5c  mov     ecx, edi; this
0x18001fc5e  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001fc63  jmp     short loc_18001FC75
0x18001fc65  mov     ecx, edi; this
0x18001fc67  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001fc6c  jmp     short loc_18001FC75
0x18001fc6e  mov     ecx, edi; this
0x18001fc70  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001fc75  mov     esi, eax
0x18001fc77  mov     [rbx+4], edi
0x18001fc7a  mov     edi, 1
0x18001fc7f  mov     eax, edi
0x18001fc81  mov     [rbx], ebp
0x18001fc83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@JPEBG_NPEAG_KPEAD6PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,long,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18001fc8b  add     eax, edi
0x18001fc8d  xor     ecx, ecx
0x18001fc8f  mov     [rbx+8], eax
0x18001fc92  mov     rax, [rsp+0A8h+arg_40]
0x18001fc9a  test    rax, rax
0x18001fc9d  jz      short loc_18001FCA4
0x18001fc9f  cmp     [rax], cx
0x18001fca2  jnz     short loc_18001FCA7
0x18001fca4  mov     rax, rcx
0x18001fca7  mov     [rbx+10h], rax
0x18001fcab  call    cs:__imp_GetCurrentThreadId
0x18001fcb1  mov     [rbx+3Ch], esi
0x18001fcb4  lea     rcx, [rbx+48h]; void *
0x18001fcb8  mov     [rbx+18h], eax
0x18001fcbb  xor     esi, esi
0x18001fcbd  mov     rax, [rsp+0A8h+var_68]
0x18001fcc2  xor     edx, edx; Val
0x18001fcc4  mov     [rbx+20h], rax
0x18001fcc8  mov     rax, [rsp+0A8h+var_60]
0x18001fccd  mov     [rbx+28h], rax
0x18001fcd1  lea     r8d, [rsi+30h]; Size
0x18001fcd5  mov     rax, [rsp+0A8h+var_58]
0x18001fcda  mov     [rbx+80h], rax
0x18001fce1  mov     [rbx+30h], r13
0x18001fce5  mov     [rbx+38h], r12d
0x18001fce9  mov     [rbx+88h], r15
0x18001fcf0  mov     [rbx+40h], rsi
0x18001fcf4  call    memset_0
0x18001fcf9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDXZEA; char const * (*wil::details::g_pfnGetModuleName)(void)
0x18001fd00  test    rax, rax
0x18001fd03  jz      short loc_18001FD0D
0x18001fd05  call    cs:__guard_dispatch_icall_fptr
0x18001fd0b  jmp     short loc_18001FD10
0x18001fd0d  mov     rax, rsi
0x18001fd10  mov     [rbx+78h], rax
0x18001fd14  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@ZEA; void (*wil::details::g_pfnGetContextAndNotifyFailure)(wil::FailureInfo *,char *,unsigned __int64)
0x18001fd1b  test    rax, rax
0x18001fd1e  jz      short loc_18001FD34
0x18001fd20  mov     rdx, [rsp+0A8h+var_50]
0x18001fd25  mov     r8d, 400h
0x18001fd2b  mov     rcx, rbx
0x18001fd2e  call    cs:__guard_dispatch_icall_fptr
0x18001fd34  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@ZEA; void (*wil::details::g_pfnLoggingCallback)(wil::FailureInfo const &)
0x18001fd3b  test    rax, rax
0x18001fd3e  jz      short loc_18001FD49
0x18001fd40  mov     rcx, rbx
0x18001fd43  call    cs:__guard_dispatch_icall_fptr
0x18001fd49  cmp     [rbx+4], esi
0x18001fd4c  jl      short loc_18001FD5E
0x18001fd4e  cmp     ebp, 3
0x18001fd51  jnz     loc_18001FE2A
0x18001fd57  mov     dword ptr [rbx+4], 8000FFFFh
0x18001fd5e  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, sil; bool wil::g_fResultOutputDebugString
0x18001fd65  jnz     short loc_18001FDA1
0x18001fd67  cmp     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@ZEA, rsi; void (*wil::details::g_pfnTelemetryCallback)(bool,wil::FailureInfo const &)
0x18001fd6e  mov     rax, cs:g_pfnResultLoggingCallback
0x18001fd75  jnz     short loc_18001FD7C
0x18001fd77  test    rax, rax
0x18001fd7a  jz      short loc_18001FDA8
0x18001fd7c  mov     rcx, cs:?g_pfnShouldOutputDebugString@wil@@3P6A_NXZEA; bool (*wil::g_pfnShouldOutputDebugString)(void)
0x18001fd83  test    rcx, rcx
0x18001fd86  jz      short loc_18001FD9C
0x18001fd88  mov     rax, rcx
0x18001fd8b  call    cs:__guard_dispatch_icall_fptr
0x18001fd91  test    al, al
0x18001fd93  jnz     short loc_18001FDA1
0x18001fd95  mov     rax, cs:g_pfnResultLoggingCallback
0x18001fd9c  mov     dil, sil
0x18001fd9f  jmp     short loc_18001FDA8
0x18001fda1  mov     rax, cs:g_pfnResultLoggingCallback
0x18001fda8  cmp     [rsp+0A8h+arg_48], sil
0x18001fdb0  jnz     short loc_18001FDD5
0x18001fdb2  test    dil, dil
0x18001fdb5  jnz     short loc_18001FDD5
0x18001fdb7  test    rax, rax
0x18001fdba  jz      short loc_18001FE19
0x18001fdbc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, sil; bool wil::details::g_resultMessageCallbackSet
0x18001fdc3  jnz     short loc_18001FE19
0x18001fdc5  xor     r8d, r8d
0x18001fdc8  xor     edx, edx
0x18001fdca  mov     rcx, rbx
0x18001fdcd  call    cs:__guard_dispatch_icall_fptr
0x18001fdd3  jmp     short loc_18001FE19
0x18001fdd5  mov     ebp, 800h
0x18001fdda  test    rax, rax
0x18001fddd  jz      short loc_18001FDF7
0x18001fddf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, sil; bool wil::details::g_resultMessageCallbackSet
0x18001fde6  jnz     short loc_18001FDF7
0x18001fde8  mov     r8d, ebp
0x18001fdeb  mov     rdx, r14
0x18001fdee  mov     rcx, rbx
0x18001fdf1  call    cs:__guard_dispatch_icall_fptr
0x18001fdf7  cmp     [r14], si
0x18001fdfb  jnz     short loc_18001FE0B
0x18001fdfd  mov     r8, rbx; unsigned __int64
0x18001fe00  mov     rdx, rbp; unsigned __int16 *
0x18001fe03  mov     rcx, r14; this
0x18001fe06  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001fe0b  test    dil, dil
0x18001fe0e  jz      short loc_18001FE19
0x18001fe10  mov     rcx, r14; lpOutputString
0x18001fe13  call    cs:__imp_OutputDebugStringW
0x18001fe19  add     rsp, 68h
0x18001fe1d  pop     r15
0x18001fe1f  pop     r14
0x18001fe21  pop     r13
0x18001fe23  pop     r12
0x18001fe25  pop     rdi
0x18001fe26  pop     rsi
0x18001fe27  pop     rbp
0x18001fe28  pop     rbx
0x18001fe29  retn
0x18001fe2a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
