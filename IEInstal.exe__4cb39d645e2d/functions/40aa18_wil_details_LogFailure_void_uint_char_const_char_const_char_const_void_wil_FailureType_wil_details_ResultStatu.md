# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x40aa18`
- end: `0x40aca9`
- name: `?LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@2@ABUResultStatus@12@PBG_NPAGIPADIW4FailureFlags@2@PAUFailureInfo@2@@Z`
- size: `657`
- prototype: `void __fastcall(int, int, int, int, int, int, int, int, _WORD *, int, WCHAR *lpOutputString, int, _BYTE *, int, int, wil *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x40c09d`

## callees

- `0x406790`
- `0x40a422`
- `0x40a736`
- `0x40a74f`
- `0x40a768`
- `0x40a7b1`
- `0x40aa18`
- `0x40ae65`
- `0x40bb71`
- `0x40d1d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40aaf9`
- `KERNEL32!GetCurrentThreadId` at `0x40aaf9`
- `KERNEL32!IsDebuggerPresent` at `0x40abff`
- `KERNEL32!IsDebuggerPresent` at `0x40abff`
- `KERNEL32!OutputDebugStringW` at `0x40ac72`
- `KERNEL32!OutputDebugStringW` at `0x40ac72`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        _WORD *a9,
        int a10,
        WCHAR *lpOutputString,
        int a12,
        _BYTE *a13,
        int a14,
        int a15,
        wil *a16)
{
  wil::details *v16; // edi
  int v17; // eax
  int v18; // edi
  _WORD *v19; // eax
  int ModuleName; // eax
  void (__thiscall *v21)(_DWORD, wil *); // edi
  int IsDebuggerPresent; // eax
  wil::details *v23; // [esp+0h] [ebp-18h]
  unsigned int v24; // [esp+4h] [ebp-14h]
  const struct wil::FailureInfo *v25; // [esp+8h] [ebp-10h]

  *lpOutputString = 0;
  *a13 = 0;
  v16 = *(wil::details **)a8;
  *((_DWORD *)a16 + 2) = *(_DWORD *)a8;
  *((_DWORD *)a16 + 3) = *(_DWORD *)(a8 + 4);
  switch ( a7 )
  {
    case 0:
      v17 = wil::details::RecordException(v23, v24);
      goto LABEL_10;
    case 1:
      v17 = wil::details::RecordReturn(v23, v24);
      goto LABEL_10;
    case 2:
      if ( (int)v16 >= 0 )
      {
        wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, -2147024228, a1);
        *((_DWORD *)a16 + 2) = -2147024228;
        *((_DWORD *)a16 + 3) = wil::details::HrToNtStatus(-2147024228);
      }
      v17 = wil::details::RecordLog(v23, v24);
      goto LABEL_10;
    case 3:
      v17 = wil::details::RecordFailFast(v16, (int)v23);
LABEL_10:
      v18 = v17;
      goto LABEL_13;
  }
  v18 = 0;
LABEL_13:
  *(_DWORD *)a16 = a7;
  *((_DWORD *)a16 + 1) = a15;
  if ( *(_DWORD *)(a8 + 8) == 1 )
    *((_DWORD *)a16 + 1) = a15 | 8;
  *((_DWORD *)a16 + 4) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v19 = a9;
  if ( !a9 || !*a9 )
    v19 = 0;
  *((_DWORD *)a16 + 5) = v19;
  *((_DWORD *)a16 + 6) = GetCurrentThreadId();
  *((_DWORD *)a16 + 9) = a3;
  *((_DWORD *)a16 + 10) = a2;
  *((_DWORD *)a16 + 7) = a5;
  *((_DWORD *)a16 + 8) = a4;
  *((_DWORD *)a16 + 20) = a6;
  *((_DWORD *)a16 + 11) = v18;
  *((_DWORD *)a16 + 21) = a1;
  *((_DWORD *)a16 + 12) = 0;
  *((_DWORD *)a16 + 16) = 0;
  *((_DWORD *)a16 + 17) = 0;
  *((_DWORD *)a16 + 18) = 0;
  *((_DWORD *)a16 + 13) = 0;
  *((_DWORD *)a16 + 14) = 0;
  *((_DWORD *)a16 + 15) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(wil::details::g_pfnGetModuleName);
  else
    ModuleName = 0;
  v21 = (void (__thiscall *)(_DWORD, wil *))wil::details::g_pfnNotifyFailure;
  *((_DWORD *)a16 + 19) = ModuleName;
  if ( v21 )
    v21(v21, a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(wil::details::g_pfnGetContextAndNotifyFailure, a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(wil::details::g_pfnLoggingCallback, a16);
  if ( wil::details::g_pfnOriginateCallback && (*((_BYTE *)a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(wil::details::g_pfnOriginateCallback, a16);
  if ( *((int *)a16 + 2) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *((_DWORD *)a16 + 2) = -2147418113;
    *((_DWORD *)a16 + 3) = wil::details::HrToNtStatus(-2147418113);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(wil::g_pfnIsDebuggerPresent)),
         IsDebuggerPresent))
    && (*((_BYTE *)a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, a16, lpOutputString, 2048);
    if ( !*lpOutputString )
      wil::GetFailureLogString(2048, lpOutputString, lpOutputString, a16, (unsigned __int16 *)v23, v24, v25);
    OutputDebugStringW(lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, a16, 0, 0);
  }
  if ( (*((_BYTE *)a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(wil::details::g_pfnDebugBreak);
  }
}

```

## disassembly

```asm
0x40aa18  mov     edi, edi
0x40aa1a  push    ebp
0x40aa1b  mov     ebp, esp
0x40aa1d  and     esp, 0FFFFFFF8h
0x40aa20  sub     esp, 0Ch
0x40aa23  push    ebx; struct wil::FailureInfo *
0x40aa24  mov     ebx, [ebp+lpOutputString]
0x40aa27  xor     eax, eax
0x40aa29  push    esi; unsigned int
0x40aa2a  mov     esi, [ebp+arg_34]
0x40aa2d  push    edi; this
0x40aa2e  mov     [ebx], ax
0x40aa31  mov     eax, [ebp+arg_28]
0x40aa34  mov     [esp+18h+var_8], edx
0x40aa38  mov     [esp+18h+var_4], ecx
0x40aa3c  mov     [esp+18h+var_C], 0
0x40aa44  mov     byte ptr [eax], 0
0x40aa47  mov     eax, [ebp+arg_14]
0x40aa4a  mov     edi, [eax]
0x40aa4c  mov     [esi+8], edi
0x40aa4f  mov     eax, [eax+4]
0x40aa52  mov     [esi+0Ch], eax
0x40aa55  mov     eax, [ebp+arg_10]
0x40aa58  sub     eax, 0
0x40aa5b  jz      short loc_40AAB1
0x40aa5d  sub     eax, 1
0x40aa60  jz      short loc_40AAA6
0x40aa62  sub     eax, 1
0x40aa65  jz      short loc_40AA74
0x40aa67  sub     eax, 1
0x40aa6a  jnz     short loc_40AABA
0x40aa6c  push    edi; this
0x40aa6d  call    ?RecordFailFast@details@wil@@YGHJ@Z; wil::details::RecordFailFast(long)
0x40aa72  jmp     short loc_40AAAD
0x40aa74  test    edi, edi
0x40aa76  js      short loc_40AA9D
0x40aa78  push    ecx
0x40aa79  mov     edi, 8007029Ch
0x40aa7e  push    edi
0x40aa7f  push    [ebp+arg_C]
0x40aa82  push    [ebp+arg_8]
0x40aa85  push    [ebp+arg_4]
0x40aa88  push    [ebp+arg_0]
0x40aa8b  call    ??$ReportFailure_Hr@$01@details@wil@@YGXPAXIPBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x40aa90  mov     ecx, edi
0x40aa92  mov     [esi+8], edi
0x40aa95  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x40aa9a  mov     [esi+0Ch], eax
0x40aa9d  mov     ecx, edi
0x40aa9f  call    ?RecordLog@details@wil@@YGHJ@Z; wil::details::RecordLog(long)
0x40aaa4  jmp     short loc_40AAAD
0x40aaa6  mov     ecx, edi
0x40aaa8  call    ?RecordReturn@details@wil@@YGHJ@Z; wil::details::RecordReturn(long)
0x40aaad  mov     edi, eax
0x40aaaf  jmp     short loc_40AABE
0x40aab1  mov     ecx, edi
0x40aab3  call    ?RecordException@details@wil@@YGHJ@Z; wil::details::RecordException(long)
0x40aab8  jmp     short loc_40AAAD
0x40aaba  mov     edi, [esp+18h+var_C]
0x40aabe  mov     eax, [ebp+arg_10]
0x40aac1  mov     edx, [ebp+arg_14]
0x40aac4  mov     ecx, [ebp+arg_30]
0x40aac7  mov     [esi], eax
0x40aac9  xor     eax, eax
0x40aacb  inc     eax
0x40aacc  mov     [esi+4], ecx
0x40aacf  cmp     [edx+8], eax
0x40aad2  jnz     short loc_40AADA
0x40aad4  or      ecx, 8
0x40aad7  mov     [esi+4], ecx
0x40aada  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x40aae2  inc     eax
0x40aae3  mov     [esi+10h], eax
0x40aae6  mov     eax, [ebp+arg_18]
0x40aae9  test    eax, eax
0x40aaeb  jz      short loc_40AAF4
0x40aaed  xor     ecx, ecx
0x40aaef  cmp     [eax], cx
0x40aaf2  jnz     short loc_40AAF6
0x40aaf4  xor     eax, eax
0x40aaf6  mov     [esi+14h], eax
0x40aaf9  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40aaff  mov     [esi+18h], eax
0x40ab02  xor     ecx, ecx
0x40ab04  mov     eax, [ebp+arg_0]
0x40ab07  mov     [esi+24h], eax
0x40ab0a  mov     eax, [esp+18h+var_8]
0x40ab0e  mov     [esi+28h], eax
0x40ab11  mov     eax, [ebp+arg_8]
0x40ab14  mov     [esi+1Ch], eax
0x40ab17  mov     eax, [ebp+arg_4]
0x40ab1a  mov     [esi+20h], eax
0x40ab1d  mov     eax, [ebp+arg_C]
0x40ab20  mov     [esi+50h], eax
0x40ab23  mov     eax, [esp+18h+var_4]
0x40ab27  mov     [esi+2Ch], edi
0x40ab2a  lea     edi, [esi+40h]
0x40ab2d  mov     [esi+54h], eax
0x40ab30  xor     eax, eax
0x40ab32  mov     [esi+30h], ecx
0x40ab35  stosd
0x40ab36  stosd
0x40ab37  stosd
0x40ab38  xor     eax, eax
0x40ab3a  lea     edi, [esi+34h]
0x40ab3d  stosd
0x40ab3e  stosd
0x40ab3f  stosd
0x40ab40  mov     edi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x40ab46  test    edi, edi
0x40ab48  jz      short loc_40AB56
0x40ab4a  mov     ecx, edi
0x40ab4c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40ab52  call    edi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x40ab54  jmp     short loc_40AB58
0x40ab56  mov     eax, ecx
0x40ab58  mov     edi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x40ab5e  mov     [esi+4Ch], eax
0x40ab61  test    edi, edi
0x40ab63  jz      short loc_40AB70
0x40ab65  push    esi
0x40ab66  mov     ecx, edi
0x40ab68  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40ab6e  call    edi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x40ab70  mov     edi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x40ab76  test    edi, edi
0x40ab78  jz      short loc_40AB8D
0x40ab7a  push    400h
0x40ab7f  push    [ebp+arg_28]
0x40ab82  mov     ecx, edi
0x40ab84  push    esi
0x40ab85  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40ab8b  call    edi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x40ab8d  mov     edi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40ab93  test    edi, edi
0x40ab95  jz      short loc_40ABA2
0x40ab97  push    esi
0x40ab98  mov     ecx, edi
0x40ab9a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40aba0  call    edi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40aba2  mov     edi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40aba8  test    edi, edi
0x40abaa  jz      short loc_40ABBD
0x40abac  test    byte ptr [esi+4], 2
0x40abb0  jnz     short loc_40ABBD
0x40abb2  push    esi
0x40abb3  mov     ecx, edi
0x40abb5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40abbb  call    edi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40abbd  cmp     dword ptr [esi+8], 0
0x40abc1  jl      short loc_40ABDD
0x40abc3  cmp     [ebp+arg_10], 3
0x40abc7  jnz     loc_40ACA4
0x40abcd  mov     ecx, 8000FFFFh
0x40abd2  mov     [esi+8], ecx
0x40abd5  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x40abda  mov     [esi+0Ch], eax
0x40abdd  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x40abe4  jnz     short loc_40AC0F
0x40abe6  mov     edi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x40abec  test    edi, edi
0x40abee  jz      short loc_40ABFF
0x40abf0  mov     ecx, edi
0x40abf2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40abf8  call    edi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x40abfa  movzx   eax, al
0x40abfd  jmp     short loc_40AC0B
0x40abff  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x40ac05  neg     eax
0x40ac07  sbb     eax, eax
0x40ac09  neg     eax
0x40ac0b  test    eax, eax
0x40ac0d  jz      short loc_40AC15
0x40ac0f  test    byte ptr [esi+4], 2
0x40ac13  jz      short loc_40AC39
0x40ac15  mov     edi, _g_pfnResultLoggingCallback
0x40ac1b  test    edi, edi
0x40ac1d  jz      short loc_40AC78
0x40ac1f  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x40ac26  jnz     short loc_40AC78
0x40ac28  xor     eax, eax
0x40ac2a  mov     ecx, edi
0x40ac2c  push    eax
0x40ac2d  push    eax
0x40ac2e  push    esi
0x40ac2f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40ac35  call    edi ; _g_pfnResultLoggingCallback
0x40ac37  jmp     short loc_40AC78
0x40ac39  mov     edi, _g_pfnResultLoggingCallback
0x40ac3f  test    edi, edi
0x40ac41  jz      short loc_40AC5D
0x40ac43  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x40ac4a  jnz     short loc_40AC5D
0x40ac4c  push    800h
0x40ac51  push    ebx
0x40ac52  push    esi
0x40ac53  mov     ecx, edi
0x40ac55  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40ac5b  call    edi ; _g_pfnResultLoggingCallback
0x40ac5d  xor     eax, eax
0x40ac5f  cmp     [ebx], ax
0x40ac62  jnz     short loc_40AC71
0x40ac64  push    esi; this
0x40ac65  mov     edx, 800h
0x40ac6a  mov     ecx, ebx
0x40ac6c  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x40ac71  push    ebx; lpOutputString
0x40ac72  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x40ac78  test    byte ptr [esi+4], 4
0x40ac7c  jnz     short loc_40AC87
0x40ac7e  cmp     ?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x40ac85  jz      short loc_40AC9B
0x40ac87  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x40ac8d  test    esi, esi
0x40ac8f  jz      short loc_40AC9B
0x40ac91  mov     ecx, esi
0x40ac93  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40ac99  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x40ac9b  pop     edi
0x40ac9c  pop     esi
0x40ac9d  pop     ebx
0x40ac9e  mov     esp, ebp
0x40aca0  pop     ebp
0x40aca1  retn    38h ; '8'
0x40aca4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
