# CProgressPage::DisplayProgress(uint)

- ea: `0x18000c754`
- end: `0x18000c869`
- name: `?DisplayProgress@CProgressPage@@QEAAJI@Z`
- size: `277`
- prototype: `__int64 __fastcall(CProgressPage *this, unsigned int, __int64, void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c870`
- `0x18000cf20`

## callees

- `0x180007970`
- `0x1800090dc`
- `0x180009480`
- `0x180009a28`
- `0x18000c1c0`
- `0x18000c310`
- `0x18000c55c`
- `0x18000c754`
- `0x180017d2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c84e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c84e`
- `USER32!NotifyWinEvent` at `0x18000c839`
- `USER32!NotifyWinEvent` at `0x18000c839`
- `USER32!GetForegroundWindow` at `0x18000c81f`
- `USER32!GetForegroundWindow` at `0x18000c81f`

## pseudocode

```c
__int64 __fastcall CProgressPage::DisplayProgress(CProgressPage *this, unsigned int a2, __int64 a3, void *a4)
{
  int v6; // eax
  void *v7; // rsi
  unsigned int v8; // ebx
  int v9; // r8d
  HWND ForegroundWindow; // rax
  int v12; // [rsp+20h] [rbp-28h]
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  pv = 0;
  v6 = TResourceStringAllocCopyEx<unsigned short *>(*((HMODULE *)this + 5), 48, a3, a4, v12, &pv);
  v7 = pv;
  v8 = v6;
  if ( v6 < 0 )
    goto LABEL_2;
  v6 = StringCchPrintfW((unsigned __int16 *)this + 36, 0x104u, L"%d%% %s", a2, pv);
  v8 = v6;
  if ( v6 < 0
    || (v6 = CChangePKUtil::HideElement(*((struct DirectUI::Element **)this + 6), L"ProgressLabel"), v8 = v6, v6 < 0)
    || (v6 = CChangePKUtil::SetElementContent(
               *((struct DirectUI::Element **)this + 6),
               L"ProgressLabel",
               (const unsigned __int16 *)this + 36),
        v8 = v6,
        v6 < 0)
    || (v6 = CChangePKUtil::ShowElement(*((struct DirectUI::Element **)this + 6), L"ProgressLabel", v9), v8 = v6, v6 < 0) )
  {
LABEL_2:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
  }
  else if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::GetImpl'::`2'::impl) )
  {
    ForegroundWindow = (HWND)*((_QWORD *)this + 7);
    if ( ForegroundWindow || (ForegroundWindow = GetForegroundWindow()) != 0 )
      NotifyWinEvent(0x8019u, ForegroundWindow, -4, 0);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v7 )
    CoTaskMemFree(v7);
  return v8;
}

```

## disassembly

```asm
0x18000c754  mov     r11, rsp
0x18000c757  mov     [r11+10h], rbx
0x18000c75b  mov     [r11+18h], rbp
0x18000c75f  push    rsi
0x18000c760  push    rdi
0x18000c761  push    r14
0x18000c763  sub     rsp, 30h
0x18000c767  mov     r14d, edx
0x18000c76a  mov     qword ptr [r11+8], 0
0x18000c772  mov     rdi, rcx
0x18000c775  lea     rax, [r11+8]
0x18000c779  mov     rcx, [rcx+28h]; int
0x18000c77d  mov     edx, 30h ; '0'; int
0x18000c782  mov     [r11-20h], rax
0x18000c786  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18000c78b  mov     rsi, [rsp+48h+pv]
0x18000c790  mov     ebx, eax
0x18000c792  test    eax, eax
0x18000c794  jns     short loc_18000C7A2
0x18000c796  mov     ecx, eax
0x18000c798  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c79d  jmp     loc_18000C83F
0x18000c7a2  mov     r9d, r14d
0x18000c7a5  mov     qword ptr [rsp+48h+var_28], rsi
0x18000c7aa  lea     r8, aDS; "%d%% %s"
0x18000c7b1  mov     edx, 104h; unsigned __int64
0x18000c7b6  lea     rcx, [rdi+48h]; unsigned __int16 *
0x18000c7ba  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c7bf  mov     ebx, eax
0x18000c7c1  test    eax, eax
0x18000c7c3  js      short loc_18000C796
0x18000c7c5  mov     rcx, [rdi+30h]; struct DirectUI::Element *
0x18000c7c9  lea     r14, aProgresslabel; "ProgressLabel"
0x18000c7d0  mov     rdx, r14; unsigned __int16 *
0x18000c7d3  call    ?HideElement@CChangePKUtil@@SAJPEAVElement@DirectUI@@PEBG@Z; CChangePKUtil::HideElement(DirectUI::Element *,ushort const *)
0x18000c7d8  mov     ebx, eax
0x18000c7da  test    eax, eax
0x18000c7dc  js      short loc_18000C796
0x18000c7de  mov     rcx, [rdi+30h]; struct DirectUI::Element *
0x18000c7e2  lea     r8, [rdi+48h]; unsigned __int16 *
0x18000c7e6  mov     rdx, r14; unsigned __int16 *
0x18000c7e9  call    ?SetElementContent@CChangePKUtil@@SAJPEAVElement@DirectUI@@PEBG1@Z; CChangePKUtil::SetElementContent(DirectUI::Element *,ushort const *,ushort const *)
0x18000c7ee  mov     ebx, eax
0x18000c7f0  test    eax, eax
0x18000c7f2  js      short loc_18000C796
0x18000c7f4  mov     rcx, [rdi+30h]; struct DirectUI::Element *
0x18000c7f8  mov     rdx, r14; unsigned __int16 *
0x18000c7fb  call    ?ShowElement@CChangePKUtil@@SAJPEAVElement@DirectUI@@PEBGH@Z; CChangePKUtil::ShowElement(DirectUI::Element *,ushort const *,int)
0x18000c800  mov     ebx, eax
0x18000c802  test    eax, eax
0x18000c804  js      short loc_18000C796
0x18000c806  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ClipWindowsUpgrade@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ClipWindowsUpgrade@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade> `wil::Feature<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::GetImpl(void)'::`2'::impl
0x18000c80d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ClipWindowsUpgrade@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ClipWindowsUpgrade>::__private_IsEnabled(void)
0x18000c812  test    al, al
0x18000c814  jz      short loc_18000C83F
0x18000c816  mov     rax, [rdi+38h]
0x18000c81a  test    rax, rax
0x18000c81d  jnz     short loc_18000C82A
0x18000c81f  call    cs:__imp_GetForegroundWindow
0x18000c825  test    rax, rax
0x18000c828  jz      short loc_18000C83F
0x18000c82a  xor     r9d, r9d; idChild
0x18000c82d  mov     rdx, rax; hwnd
0x18000c830  mov     ecx, 8019h; event
0x18000c835  lea     r8d, [r9-4]; idObject
0x18000c839  call    cs:__imp_NotifyWinEvent
0x18000c83f  mov     ecx, ebx
0x18000c841  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c846  test    rsi, rsi
0x18000c849  jz      short loc_18000C854
0x18000c84b  mov     rcx, rsi; pv
0x18000c84e  call    cs:__imp_CoTaskMemFree
0x18000c854  mov     rbp, [rsp+48h+arg_10]
0x18000c859  mov     eax, ebx
0x18000c85b  mov     rbx, [rsp+48h+arg_8]
0x18000c860  add     rsp, 30h
0x18000c864  pop     r14
0x18000c866  pop     rdi
0x18000c867  pop     rsi
0x18000c868  retn
```
