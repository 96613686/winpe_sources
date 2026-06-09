# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x40c146`
- end: `0x40c3b3`
- name: `??$ReportFailure_Return@$00@details@wil@@YGXPAXIPBD110ABUResultStatus@01@PBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `621`
- prototype: `void __fastcall(int, int, int, int, int, int, int *, int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x40bf19`

## callees

- `0x40a422`
- `0x40a74f`
- `0x40acb0`
- `0x40ae65`
- `0x40c146`
- `0x40cb60`
- `0x40d1d0`
- `0x40eb40`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x40c1c6`
- `KERNEL32!GetCurrentThreadId` at `0x40c1c6`
- `KERNEL32!IsDebuggerPresent` at `0x40c2ce`
- `KERNEL32!IsDebuggerPresent` at `0x40c2ce`
- `KERNEL32!OutputDebugStringW` at `0x40c35e`
- `KERNEL32!OutputDebugStringW` at `0x40c35e`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int *a7,
        int a8,
        int a9,
        int a10)
{
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // edi
  int IsDebuggerPresent; // eax
  wil::details *v16; // [esp+Ch] [ebp-1478h]
  wil::details::in1diag3 *v17; // [esp+Ch] [ebp-1478h]
  int v18; // [esp+10h] [ebp-1474h]
  const struct wil::FailureInfo *v19; // [esp+10h] [ebp-1474h]
  const struct wil::FailureInfo *v20; // [esp+14h] [ebp-1470h]
  int v22; // [esp+24h] [ebp-1460h] BYREF
  int v23; // [esp+28h] [ebp-145Ch]
  int v24; // [esp+2Ch] [ebp-1458h]
  int v25; // [esp+30h] [ebp-1454h]
  signed __int32 v26; // [esp+34h] [ebp-1450h]
  int v27; // [esp+38h] [ebp-144Ch]
  DWORD CurrentThreadId; // [esp+3Ch] [ebp-1448h]
  int v29; // [esp+40h] [ebp-1444h]
  int v30; // [esp+44h] [ebp-1440h]
  const char *v31; // [esp+48h] [ebp-143Ch]
  int v32; // [esp+4Ch] [ebp-1438h]
  int v33; // [esp+50h] [ebp-1434h]
  int v34; // [esp+54h] [ebp-1430h]
  int v35; // [esp+58h] [ebp-142Ch]
  int v36; // [esp+5Ch] [ebp-1428h]
  int v37; // [esp+60h] [ebp-1424h]
  int v38; // [esp+64h] [ebp-1420h]
  int v39; // [esp+68h] [ebp-141Ch]
  int v40; // [esp+6Ch] [ebp-1418h]
  int ModuleName; // [esp+70h] [ebp-1414h]
  int v42; // [esp+74h] [ebp-1410h]
  int v43; // [esp+78h] [ebp-140Ch]
  char v44[1024]; // [esp+7Ch] [ebp-1408h] BYREF
  WCHAR OutputString[2050]; // [esp+47Ch] [ebp-1008h] BYREF

  OutputString[0] = 0;
  v44[0] = 0;
  v11 = a7[1];
  v24 = *a7;
  v25 = v11;
  v12 = wil::details::RecordReturn(v16, v18);
  v13 = 0;
  v14 = v12;
  if ( a7[2] == 1 )
    v13 = 8;
  v22 = 1;
  v23 = v13;
  v26 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v27 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v42 = a6;
  v32 = a2;
  v33 = v14;
  v43 = a1;
  v31 = "wil";
  v29 = 0;
  v30 = 0;
  v34 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(wil::details::g_pfnGetModuleName);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(wil::details::g_pfnNotifyFailure, &v22);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(wil::details::g_pfnGetContextAndNotifyFailure, &v22, v44, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(wil::details::g_pfnLoggingCallback, &v22);
  if ( wil::details::g_pfnOriginateCallback && (v23 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(wil::details::g_pfnOriginateCallback, &v22);
  if ( v24 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(wil::g_pfnIsDebuggerPresent)),
         IsDebuggerPresent))
    && (v23 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, &v22, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)&v22, (unsigned __int16 *)v17, (unsigned int)v19, v20);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(g_pfnResultLoggingCallback, &v22, 0, 0);
  }
  if ( ((v23 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(wil::details::g_pfnDebugBreak);
  if ( (v23 & 1) != 0 )
    wil::details::WilFailFast(v17, v19);
}

```

## disassembly

```asm
0x40c146  mov     edi, edi
0x40c148  push    ebp
0x40c149  mov     ebp, esp
0x40c14b  and     esp, 0FFFFFFF8h
0x40c14e  mov     eax, 146Ch
0x40c153  call    __chkstk
0x40c158  mov     eax, ___security_cookie
0x40c15d  xor     eax, esp
0x40c15f  mov     [esp+146Ch+var_4], eax
0x40c166  mov     eax, [ebp+arg_C]
0x40c169  push    ebx; struct wil::FailureInfo *
0x40c16a  push    esi; struct wil::FailureInfo *
0x40c16b  mov     esi, [ebp+arg_10]
0x40c16e  mov     ebx, edx
0x40c170  mov     [esp+1474h+var_1468], eax
0x40c174  xor     eax, eax
0x40c176  mov     [esp+1474h+OutputString], ax
0x40c17e  mov     [esp+1474h+var_1408], al
0x40c182  mov     eax, [esi+4]
0x40c185  mov     [esp+1474h+var_1464], ecx
0x40c189  mov     ecx, [esi]
0x40c18b  push    edi; this
0x40c18c  mov     [esp+1478h+var_1458], ecx
0x40c190  mov     [esp+1478h+var_1454], eax
0x40c194  call    ?RecordReturn@details@wil@@YGHJ@Z; wil::details::RecordReturn(long)
0x40c199  xor     edx, edx
0x40c19b  xor     ecx, ecx
0x40c19d  inc     edx
0x40c19e  mov     edi, eax
0x40c1a0  cmp     [esi+8], edx
0x40c1a3  push    8
0x40c1a5  pop     eax
0x40c1a6  cmovz   ecx, eax
0x40c1a9  mov     [esp+1478h+var_1460], edx
0x40c1ad  mov     [esp+1478h+var_145C], ecx
0x40c1b1  lock xadd ?s_failureId@?1??LogFailure@details@wil@@YGXPAXIPBD110W4FailureType@3@ABUResultStatus@23@PBG_NPAGIPADIW4FailureFlags@3@PAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,uint,char *,uint,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x40c1b9  inc     edx
0x40c1ba  mov     [esp+1478h+var_1450], edx
0x40c1be  mov     [esp+1478h+var_144C], 0
0x40c1c6  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x40c1cc  mov     [esp+1478h+var_1448], eax
0x40c1d0  mov     eax, [esp+1478h+var_1468]
0x40c1d4  mov     [esp+1478h+var_1410], eax
0x40c1d8  mov     eax, [esp+1478h+var_1464]
0x40c1dc  mov     [esp+1478h+var_1438], ebx
0x40c1e0  xor     ebx, ebx
0x40c1e2  mov     [esp+1478h+var_1434], edi
0x40c1e6  lea     edi, [esp+1478h+var_1420]
0x40c1ea  mov     [esp+1478h+var_140C], eax
0x40c1ee  xor     eax, eax
0x40c1f0  mov     esi, ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x40c1f6  mov     [esp+1478h+var_143C], offset aWil; "wil"
0x40c1fe  mov     [esp+1478h+var_1444], ebx
0x40c202  mov     [esp+1478h+var_1440], ebx
0x40c206  mov     [esp+1478h+var_1430], ebx
0x40c20a  stosd
0x40c20b  stosd
0x40c20c  stosd
0x40c20d  xor     eax, eax
0x40c20f  lea     edi, [esp+1478h+var_142C]
0x40c213  stosd
0x40c214  stosd
0x40c215  stosd
0x40c216  test    esi, esi
0x40c218  jz      short loc_40C22A
0x40c21a  mov     ecx, esi
0x40c21c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c222  call    esi ; ?g_pfnGetModuleName@details@wil@@3P6GPBDX_EA
0x40c224  mov     [esp+1478h+var_1414], eax
0x40c228  jmp     short loc_40C22E
0x40c22a  mov     [esp+1478h+var_1414], ebx
0x40c22e  mov     esi, ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x40c234  test    esi, esi
0x40c236  jz      short loc_40C247
0x40c238  lea     eax, [esp+1478h+var_1460]
0x40c23c  mov     ecx, esi
0x40c23e  push    eax
0x40c23f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c245  call    esi ; ?g_pfnNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@@_EA
0x40c247  mov     esi, ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x40c24d  test    esi, esi
0x40c24f  jz      short loc_40C26A
0x40c251  push    400h
0x40c256  lea     eax, [esp+147Ch+var_1408]
0x40c25a  mov     ecx, esi
0x40c25c  push    eax
0x40c25d  lea     eax, [esp+1480h+var_1460]
0x40c261  push    eax
0x40c262  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c268  call    esi ; ?g_pfnGetContextAndNotifyFailure@details@wil@@3P6GXPAUFailureInfo@2@PADI@_EA
0x40c26a  mov     esi, ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40c270  test    esi, esi
0x40c272  jz      short loc_40C283
0x40c274  lea     eax, [esp+1478h+var_1460]
0x40c278  mov     ecx, esi
0x40c27a  push    eax
0x40c27b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c281  call    esi ; ?g_pfnLoggingCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40c283  mov     esi, ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40c289  test    esi, esi
0x40c28b  jz      short loc_40C2A3
0x40c28d  test    byte ptr [esp+1478h+var_145C], 2
0x40c292  jnz     short loc_40C2A3
0x40c294  lea     eax, [esp+1478h+var_1460]
0x40c298  mov     ecx, esi
0x40c29a  push    eax
0x40c29b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c2a1  call    esi ; ?g_pfnOriginateCallback@details@wil@@3P6GXABUFailureInfo@2@@_EA
0x40c2a3  cmp     [esp+1478h+var_1458], ebx
0x40c2a7  jge     loc_40C3A5
0x40c2ad  cmp     ?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x40c2b3  jnz     short loc_40C2DE
0x40c2b5  mov     esi, ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x40c2bb  test    esi, esi
0x40c2bd  jz      short loc_40C2CE
0x40c2bf  mov     ecx, esi
0x40c2c1  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c2c7  call    esi ; ?g_pfnIsDebuggerPresent@wil@@3P6G_NX_EA
0x40c2c9  movzx   eax, al
0x40c2cc  jmp     short loc_40C2DA
0x40c2ce  call    ds:__imp__IsDebuggerPresent@0; IsDebuggerPresent()
0x40c2d4  neg     eax
0x40c2d6  sbb     eax, eax
0x40c2d8  neg     eax
0x40c2da  test    eax, eax
0x40c2dc  jz      short loc_40C2E5
0x40c2de  test    byte ptr [esp+1478h+var_145C], 2
0x40c2e3  jz      short loc_40C30A
0x40c2e5  mov     esi, _g_pfnResultLoggingCallback
0x40c2eb  test    esi, esi
0x40c2ed  jz      short loc_40C364
0x40c2ef  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x40c2f5  jnz     short loc_40C364
0x40c2f7  push    ebx
0x40c2f8  push    ebx
0x40c2f9  lea     eax, [esp+1480h+var_1460]
0x40c2fd  mov     ecx, esi
0x40c2ff  push    eax
0x40c300  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c306  call    esi ; _g_pfnResultLoggingCallback
0x40c308  jmp     short loc_40C364
0x40c30a  mov     esi, _g_pfnResultLoggingCallback
0x40c310  mov     edi, 800h
0x40c315  test    esi, esi
0x40c317  jz      short loc_40C339
0x40c319  cmp     ?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x40c31f  jnz     short loc_40C339
0x40c321  push    edi
0x40c322  lea     eax, [esp+147Ch+OutputString]
0x40c329  mov     ecx, esi
0x40c32b  push    eax
0x40c32c  lea     eax, [esp+1480h+var_1460]
0x40c330  push    eax
0x40c331  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c337  call    esi ; _g_pfnResultLoggingCallback
0x40c339  cmp     [esp+1478h+OutputString], bx
0x40c341  jnz     short loc_40C356
0x40c343  lea     eax, [esp+1478h+var_1460]
0x40c347  mov     edx, edi
0x40c349  push    eax; this
0x40c34a  lea     ecx, [esp+147Ch+OutputString]
0x40c351  call    ?GetFailureLogString@wil@@YGJPAGIABUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,uint,wil::FailureInfo const &)
0x40c356  lea     eax, [esp+1478h+OutputString]
0x40c35d  push    eax; lpOutputString
0x40c35e  call    ds:__imp__OutputDebugStringW@4; OutputDebugStringW(x)
0x40c364  test    byte ptr [esp+1478h+var_145C], 4
0x40c369  jnz     short loc_40C373
0x40c36b  cmp     ?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x40c371  jz      short loc_40C387
0x40c373  mov     esi, ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x40c379  test    esi, esi
0x40c37b  jz      short loc_40C387
0x40c37d  mov     ecx, esi
0x40c37f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x40c385  call    esi ; ?g_pfnDebugBreak@details@wil@@3P6GXX_EA
0x40c387  test    byte ptr [esp+1478h+var_145C], 1
0x40c38c  jnz     short loc_40C3AA
0x40c38e  mov     ecx, [esp+1478h+var_4]
0x40c395  pop     edi
0x40c396  pop     esi
0x40c397  pop     ebx
0x40c398  xor     ecx, esp; StackCookie
0x40c39a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40c39f  mov     esp, ebp
0x40c3a1  pop     ebp
0x40c3a2  retn    20h ; ' '
0x40c3a5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YGXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x40c3aa  lea     ecx, [esp+1478h+var_1460]
0x40c3ae  call    ?WilFailFast@details@wil@@YGXABUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
