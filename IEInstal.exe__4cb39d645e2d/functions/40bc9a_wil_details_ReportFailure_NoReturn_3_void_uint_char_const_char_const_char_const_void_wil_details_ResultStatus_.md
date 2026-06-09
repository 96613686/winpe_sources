# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x40bc9a`
- end: `0x40bee9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@@Z`
- size: `591`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x40ad3d`

## callees

- `0x406790`
- `0x40a422`
- `0x40a7b1`
- `0x40acb0`
- `0x40bc9a`
- `0x40d1d0`
- `0x40eb40`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40bd11`
- `KERNEL32!GetCurrentThreadId` at `0x40bd11`
- `KERNEL32!IsDebuggerPresent` at `0x40be27`
- `KERNEL32!IsDebuggerPresent` at `0x40be27`
- `KERNEL32!OutputDebugStringW` at `0x40beb7`
- `KERNEL32!OutputDebugStringW` at `0x40beb7`

## string_xrefs

- `0x40bd41`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7)
{
  wil::details *v8; // ecx
  int v9; // eax
  int v10; // eax
  int v11; // ecx
  int v12; // edi
  int IsDebuggerPresent; // eax
  int v14; // [esp+Ch] [ebp-1470h]
  wil::details *v15; // [esp+Ch] [ebp-1470h]
  const struct wil::FailureInfo *v16; // [esp+10h] [ebp-146Ch]
  const struct wil::FailureInfo *v17; // [esp+14h] [ebp-1468h]
  int v19; // [esp+24h] [ebp-1458h] BYREF
  int v20; // [esp+28h] [ebp-1454h]
  int v21; // [esp+2Ch] [ebp-1450h]
  int v22; // [esp+30h] [ebp-144Ch]
  signed __int32 v23; // [esp+34h] [ebp-1448h]
  int v24; // [esp+38h] [ebp-1444h]
  DWORD CurrentThreadId; // [esp+3Ch] [ebp-1440h]
  int v26; // [esp+40h] [ebp-143Ch]
  int v27; // [esp+44h] [ebp-1438h]
  const char *v28; // [esp+48h] [ebp-1434h]
  int v29; // [esp+4Ch] [ebp-1430h]
  int v30; // [esp+50h] [ebp-142Ch]
  int v31; // [esp+54h] [ebp-1428h]
  int v32; // [esp+58h] [ebp-1424h]
  int v33; // [esp+5Ch] [ebp-1420h]
  int v34; // [esp+60h] [ebp-141Ch]
  int v35; // [esp+64h] [ebp-1418h]
  int v36; // [esp+68h] [ebp-1414h]
  int v37; // [esp+6Ch] [ebp-1410h]
  int ModuleName; // [esp+70h] [ebp-140Ch]
  int v39; // [esp+74h] [ebp-1408h]
  int v40; // [esp+78h] [ebp-1404h]
  char v41[1024]; // [esp+7Ch] [ebp-1400h] BYREF
  WCHAR OutputString[2048]; // [esp+47Ch] [ebp-1000h] BYREF

  v8 = *(wil::details **)a7;
  OutputString[0] = 0;
  v41[0] = 0;
  v9 = *(_DWORD *)(a7 + 4);
  v21 = (int)v8;
  v22 = v9;
  v10 = wil::details::RecordFailFast(v8, v14);
  v19 = 3;
  v11 = 0;
  v12 = v10;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v39 = a6;
  v29 = a2;
  v30 = v12;
  v40 = a1;
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = 0;
  v27 = 0;
  v31 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(wil::details::g_pfnGetModuleName);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(wil::details::g_pfnNotifyFailure, &v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(wil::details::g_pfnGetContextAndNotifyFailure, &v19, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(wil::details::g_pfnLoggingCallback, &v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(wil::details::g_pfnOriginateCallback, &v19);
  if ( v21 >= 0 )
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus(v15, (int)v16);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(wil::g_pfnIsDebuggerPresent)),
         IsDebuggerPresent))
    && (v20 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, &v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)&v19, (unsigned __int16 *)v15, (unsigned int)v16, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, &v19, 0, 0);
  }
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(wil::details::g_pfnDebugBreak);
  }
  wil::details::WilFailFast(v15, v16);
}

```

## disassembly

```asm
0x40bc9a  mov     edi, edi
0x40bc9c  push    ebp
0x40bc9d  mov     ebp, esp
0x40bc9f  and     esp, 0FFFFFFF8h
0x40bca2  mov     eax, 1464h
0x40bca7  call    __chkstk
0x40bcac  mov     eax, [ebp+arg_C]
0x40bcaf  push    ebx; struct wil::FailureInfo *
0x40bcb0  push    esi; struct wil::FailureInfo *
0x40bcb1  mov     esi, [ebp+arg_10]
0x40bcb4  mov     ebx, edx
0x40bcb6  mov     [esp+146Ch+var_1460], eax
0x40bcba  xor     eax, eax
0x40bcbc  push    edi; this
0x40bcbd  mov     [esp+1470h+var_145C], ecx
0x40bcc1  mov     ecx, [esi]
0x40bcc3  mov     [esp+1470h+OutputString], ax
0x40bccb  mov     [esp+1470h+var_1400], al
0x40bccf  mov     eax, [esi+4]
0x40bcd2  push    ecx; this
0x40bcd3  mov     [esp+1474h+var_1450], ecx
0x40bcd7  mov     [esp+1474h+var_144C], eax
0x40bcdb  call    ?RecordFailFast@details@wil@@YGHJ@Z; wil::details::RecordFailFast(long)
0x40bce0  xor     edx, edx
0x40bce2  mov     [esp+1470h+var_1458], 3
0x40bcea  xor     ecx, ecx
0x40bcec  inc     edx
0x40bced  cmp     [esi+8], edx
0x40bcf0  mov     edi, eax
0x40bcf2  push    8
0x40bcf4  pop     eax
0x40bcf5  cmovz   ecx, eax
0x40bcf8  mov     [esp+1470h+var_1454], ecx
0x40bcfc  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x40bd04  inc     edx
0x40bd05  mov     [esp+1470h+var_1448], edx
0x40bd09  mov     [esp+1470h+var_1444], 0
0x40bd11  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40bd17  mov     [esp+1470h+var_1440], eax
0x40bd1b  mov     eax, [esp+1470h+var_1460]
0x40bd1f  mov     [esp+1470h+var_1408], eax
0x40bd23  mov     eax, [esp+1470h+var_145C]
0x40bd27  mov     [esp+1470h+var_1430], ebx
0x40bd2b  xor     ebx, ebx
0x40bd2d  mov     [esp+1470h+var_142C], edi
0x40bd31  lea     edi, [esp+1470h+var_1418]
0x40bd35  mov     [esp+1470h+var_1404], eax
0x40bd39  xor     eax, eax
0x40bd3b  mov     esi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x40bd41  mov     [esp+1470h+var_1434], offset aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x40bd49  mov     [esp+1470h+var_143C], ebx
0x40bd4d  mov     [esp+1470h+var_1438], ebx
0x40bd51  mov     [esp+1470h+var_1428], ebx
0x40bd55  stosd
0x40bd56  stosd
0x40bd57  stosd
0x40bd58  xor     eax, eax
0x40bd5a  lea     edi, [esp+1470h+var_1424]
0x40bd5e  stosd
0x40bd5f  stosd
0x40bd60  stosd
0x40bd61  test    esi, esi
0x40bd63  jz      short loc_40BD75
0x40bd65  mov     ecx, esi
0x40bd67  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40bd6d  call    esi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x40bd6f  mov     [esp+1470h+var_140C], eax
0x40bd73  jmp     short loc_40BD79
0x40bd75  mov     [esp+1470h+var_140C], ebx
0x40bd79  mov     esi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x40bd7f  test    esi, esi
0x40bd81  jz      short loc_40BD92
0x40bd83  lea     eax, [esp+1470h+var_1458]
0x40bd87  mov     ecx, esi
0x40bd89  push    eax
0x40bd8a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40bd90  call    esi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x40bd92  mov     esi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x40bd98  test    esi, esi
0x40bd9a  jz      short loc_40BDB5
0x40bd9c  push    400h
0x40bda1  lea     eax, [esp+1474h+var_1400]
0x40bda5  mov     ecx, esi
0x40bda7  push    eax
0x40bda8  lea     eax, [esp+1478h+var_1458]
0x40bdac  push    eax
0x40bdad  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40bdb3  call    esi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x40bdb5  mov     esi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40bdbb  test    esi, esi
0x40bdbd  jz      short loc_40BDCE
0x40bdbf  lea     eax, [esp+1470h+var_1458]
0x40bdc3  mov     ecx, esi
0x40bdc5  push    eax
0x40bdc6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40bdcc  call    esi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40bdce  mov     esi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40bdd4  test    esi, esi
0x40bdd6  jz      short loc_40BDEE
0x40bdd8  test    byte ptr [esp+1470h+var_1454], 2
0x40bddd  jnz     short loc_40BDEE
0x40bddf  lea     eax, [esp+1470h+var_1458]
0x40bde3  mov     ecx, esi
0x40bde5  push    eax
0x40bde6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40bdec  call    esi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40bdee  cmp     [esp+1470h+var_1450], ebx
0x40bdf2  jl      short loc_40BE06
0x40bdf4  mov     ecx, 8000FFFFh
0x40bdf9  mov     [esp+1470h+var_1450], ecx
0x40bdfd  call    ?HrToNtStatus@details@wil@@YGJJ@Z; wil::details::HrToNtStatus(long)
0x40be02  mov     [esp+1470h+var_144C], eax
0x40be06  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x40be0c  jnz     short loc_40BE37
0x40be0e  mov     esi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x40be14  test    esi, esi
0x40be16  jz      short loc_40BE27
0x40be18  mov     ecx, esi
0x40be1a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40be20  call    esi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x40be22  movzx   eax, al
0x40be25  jmp     short loc_40BE33
0x40be27  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x40be2d  neg     eax
0x40be2f  sbb     eax, eax
0x40be31  neg     eax
0x40be33  test    eax, eax
0x40be35  jz      short loc_40BE3E
0x40be37  test    byte ptr [esp+1470h+var_1454], 2
0x40be3c  jz      short loc_40BE63
0x40be3e  mov     esi, _g_pfnResultLoggingCallback
0x40be44  test    esi, esi
0x40be46  jz      short loc_40BEBD
0x40be48  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x40be4e  jnz     short loc_40BEBD
0x40be50  push    ebx
0x40be51  push    ebx
0x40be52  lea     eax, [esp+1478h+var_1458]
0x40be56  mov     ecx, esi
0x40be58  push    eax
0x40be59  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40be5f  call    esi ; _g_pfnResultLoggingCallback
0x40be61  jmp     short loc_40BEBD
0x40be63  mov     esi, _g_pfnResultLoggingCallback
0x40be69  mov     edi, 800h
0x40be6e  test    esi, esi
0x40be70  jz      short loc_40BE92
0x40be72  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x40be78  jnz     short loc_40BE92
0x40be7a  push    edi
0x40be7b  lea     eax, [esp+1474h+OutputString]
0x40be82  mov     ecx, esi
0x40be84  push    eax
0x40be85  lea     eax, [esp+1478h+var_1458]
0x40be89  push    eax
0x40be8a  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40be90  call    esi ; _g_pfnResultLoggingCallback
0x40be92  cmp     [esp+1470h+OutputString], bx
0x40be9a  jnz     short loc_40BEAF
0x40be9c  lea     eax, [esp+1470h+var_1458]
0x40bea0  mov     edx, edi
0x40bea2  push    eax; this
0x40bea3  lea     ecx, [esp+1474h+OutputString]
0x40beaa  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x40beaf  lea     eax, [esp+1470h+OutputString]
0x40beb6  push    eax; lpOutputString
0x40beb7  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x40bebd  test    byte ptr [esp+1470h+var_1454], 4
0x40bec2  jnz     short loc_40BECC
0x40bec4  cmp     ?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x40beca  jz      short loc_40BEE0
0x40becc  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x40bed2  test    esi, esi
0x40bed4  jz      short loc_40BEE0
0x40bed6  mov     ecx, esi
0x40bed8  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40bede  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x40bee0  lea     ecx, [esp+1470h+var_1458]
0x40bee4  call    ?WilFailFast@details@wil@@YGXABUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
