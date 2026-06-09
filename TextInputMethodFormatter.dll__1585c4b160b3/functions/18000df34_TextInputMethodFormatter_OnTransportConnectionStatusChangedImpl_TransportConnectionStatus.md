# TextInputMethodFormatter::OnTransportConnectionStatusChangedImpl(TransportConnectionStatus)

- ea: `0x18000df34`
- end: `0x18000e580`
- name: `?OnTransportConnectionStatusChangedImpl@TextInputMethodFormatter@@AEAAJW4TransportConnectionStatus@@@Z`
- size: `1612`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000de80`
- `0x180011850`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x18000271c`
- `0x18000275c`
- `0x180006a14`
- `0x18000804c`
- `0x180008154`
- `0x18000825c`
- `0x180008368`
- `0x18000a830`
- `0x18000c454`
- `0x18000df34`
- `0x180010540`
- `0x180012030`
- `0x180012074`
- `0x1800121a4`
- `0x180037394`
- `0x180058010`

## string_xrefs

- `0x18000e0c2`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000e4d0`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000e4ec`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000e501`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000e516`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000e52b`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000e56e`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000e540`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18000e555`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TextInputMethodFormatter::OnTransportConnectionStatusChangedImpl(__int64 a1, int a2)
{
  __int64 v2; // rdi
  int v3; // edx
  PduIdHelper *v4; // rax
  PduIdHelper *v5; // rbx
  _DWORD *v6; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // r14d
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64); // rbx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rsi
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // r8d
  unsigned int v25; // ebx
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  void *v32; // rcx
  int v33; // [rsp+20h] [rbp-39h]
  __int64 v34; // [rsp+40h] [rbp-19h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-11h] BYREF
  _OWORD v36[2]; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v2 = a1;
  if ( *(_DWORD *)(a1 + 268) != a2 )
  {
    *(_DWORD *)(a1 + 268) = a2;
    if ( a2 )
    {
      v3 = a2 - 1;
      if ( v3 )
      {
        if ( v3 != 1 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x177,
            (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
            (const char *)0x8000FFFFLL,
            v33);
        if ( (unsigned int)dword_180082080 > 5
          && (qword_180082090 & 0x400000) != 0
          && (qword_180082098 & 0x400000) == qword_180082098 )
        {
          tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &byte_180074E57, 0, 0, 2, v36);
        }
        if ( *(_BYTE *)(v2 + 248) )
        {
          v4 = (PduIdHelper *)operator new(0x60u);
          v5 = PduIdHelper::PduIdHelper(v4);
          v6 = operator new(0x18u);
          v6[2] = 1;
          v6[3] = 1;
          *(_QWORD *)v6 = &std::_Ref_count<IVirtualizedTextDataSender>::`vftable';
          *((_QWORD *)v6 + 2) = v5;
          *(_QWORD *)(v2 + 176) = v5;
          v7 = *(volatile signed __int32 **)(v2 + 184);
          *(_QWORD *)(v2 + 184) = v6;
          if ( v7 )
          {
            if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
              if ( !_InterlockedDecrement(v7 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
            }
          }
          *(_QWORD *)&v36[0] = v2;
          v8 = *(_QWORD *)(v2 + 168);
          *(_QWORD *)(v2 + 168) = 0;
          if ( v8 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          v9 = Microsoft::WRL::Details::MakeAndInitialize<TextVirtualizationInternal,ITextVirtualizationInternal,std::shared_ptr<IVirtualizedTextDataSender> &,TextInputMethodFormatter *>(
                 v2 + 168,
                 v2 + 192,
                 v36);
          v10 = v9;
          if ( v9 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11A,
              (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
              (const char *)(unsigned int)v9,
              v33);
            return v10;
          }
          v34 = 0;
          v35 = 0;
          v12 = Microsoft::WRL::Details::MakeAndInitialize<IRemoteTextInputServer_ToPdu,IRemoteTextInputServer_ToPdu,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &>(
                  &v35,
                  v2 + 192,
                  v2 + 176);
          if ( v12 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x128,
              (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
              (const char *)(unsigned int)v12,
              v33);
          *(_QWORD *)&v36[0] = 0;
          v13 = Microsoft::WRL::Details::MakeAndInitialize<IRemoteCoreInputViewManager_ToPdu,IRemoteCoreInputViewManager_ToPdu,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &>(
                  v36,
                  v2 + 192,
                  v2 + 176);
          if ( v13 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x129,
              (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
              (const char *)(unsigned int)v13,
              v33);
          v34 = 0;
          v14 = Microsoft::WRL::Details::MakeAndInitialize<ITextVirtualizationClient_ToPdu,ITextVirtualizationClient,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &>(
                  &v34,
                  v2 + 192,
                  v2 + 176);
          if ( v14 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x12A,
              (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
              (const char *)(unsigned int)v14,
              v33);
          v15 = *(_QWORD *)(v2 + 144);
          *(_QWORD *)(v2 + 144) = 0;
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          v16 = v35;
          v17 = (**v35)(v35, &GUID_869e9b43_7e00_4f26_b722_f81b75205fb0, v2 + 144);
          if ( v17 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v17,
              v33);
          v18 = *(_QWORD *)(v2 + 152);
          *(_QWORD *)(v2 + 152) = 0;
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v19 = *(_QWORD *)&v36[0];
          v20 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v36[0])(
                  *(_QWORD *)&v36[0],
                  &GUID_91b84726_e24f_4db5_9a66_13eb7bca911c,
                  v2 + 152);
          if ( v20 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v20,
              v33);
          v21 = *(_QWORD *)(v2 + 160);
          *(_QWORD *)(v2 + 160) = 0;
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          v22 = v34;
          *(_QWORD *)(v2 + 160) = v34;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
          *(_BYTE *)(v2 + 248) = 0;
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v16 )
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v16)[2])(v16);
        }
        v23 = TextInputMethodFormatter::EnableRemoteKeyRouting((TextInputMethodFormatter *)v2, 0, 0, 0);
        if ( v23 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x133,
            (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
            (const char *)(unsigned int)v23,
            v33);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v2 + 160) + 24LL))(*(_QWORD *)(v2 + 160));
      }
      else
      {
        if ( (unsigned int)dword_180082080 > 5 )
        {
          a1 = 0x400000;
          if ( (qword_180082090 & 0x400000) != 0 && (qword_180082098 & 0x400000) == qword_180082098 )
            tlgWriteTransfer_EventWriteTransfer(&dword_180082080, word_180074DF2, 0, 0, 2, v36);
        }
        v24 = *(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor;
        if ( (*(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor & 4) == 0 )
        {
          *(_QWORD *)&v36[0] = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(
                                            a1,
                                            v36);
          v24 = v36[0];
        }
        LODWORD(v34) = 0;
        WORD2(v34) = 3;
        wil::details::ReportUsageToService(&qword_1800827F8, 42936120, (v24 >> 10) & 1, (v24 >> 11) & 1);
        v25 = 7;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoteTextIntegration_Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RemoteTextIntegration_Perf>::GetImpl'::`2'::impl) )
          v25 = 15;
        v26 = *(_QWORD *)(v2 + 144);
        v36[0] = GUID_NULL;
        (*(void (__fastcall **)(__int64, _OWORD *, __int64, _QWORD, __int64 *, int, int))(*(_QWORD *)v26 + 512LL))(
          v26,
          v36,
          1,
          v25,
          &v34,
          1,
          3);
      }
    }
    else
    {
      if ( (unsigned int)dword_180082080 > 5
        && (qword_180082090 & 0x400000) != 0
        && (qword_180082098 & 0x400000) == qword_180082098 )
      {
        tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &dword_180074DA4, 0, 0, 2, v36);
      }
      v27 = TextInputMethodFormatter::EnableRemoteKeyRouting((TextInputMethodFormatter *)v2, 0, 0, 0);
      if ( v27 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x168,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
          (const char *)(unsigned int)v27,
          v33);
      v28 = *(_QWORD *)(v2 + 56);
      *(_QWORD *)(v2 + 56) = 0;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      *(_BYTE *)(v2 + 248) = 1;
      v29 = *(_QWORD *)(v2 + 144);
      *(_QWORD *)(v2 + 144) = 0;
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      v30 = *(_QWORD *)(v2 + 152);
      *(_QWORD *)(v2 + 152) = 0;
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      v31 = *(_QWORD *)(v2 + 160);
      *(_QWORD *)(v2 + 160) = 0;
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      v32 = *(void **)(v2 + 128);
      *(_QWORD *)(v2 + 128) = 0;
      if ( v32 )
        operator delete(v32);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000df34  push    rbp
0x18000df36  push    rbx
0x18000df37  push    rsi
0x18000df38  push    rdi
0x18000df39  push    r14
0x18000df3b  push    r15
0x18000df3d  lea     rbp, [rsp-2Fh]
0x18000df42  sub     rsp, 88h
0x18000df49  mov     rax, cs:__security_cookie
0x18000df50  xor     rax, rsp
0x18000df53  mov     [rbp+57h+var_40], rax
0x18000df57  mov     rdi, rcx
0x18000df5a  cmp     [rcx+10Ch], edx
0x18000df60  jz      loc_18000E4AF
0x18000df66  mov     [rcx+10Ch], edx
0x18000df6c  xor     r15d, r15d
0x18000df6f  test    edx, edx
0x18000df71  jz      loc_18000E39D
0x18000df77  sub     edx, 1
0x18000df7a  jz      loc_18000E28E
0x18000df80  cmp     edx, 1
0x18000df83  jnz     loc_18000E4E2
0x18000df89  mov     eax, cs:dword_180082080
0x18000df8f  cmp     eax, 5
0x18000df92  jbe     short loc_18000DFE1
0x18000df94  mov     rdx, cs:qword_180082098
0x18000df9b  mov     rax, cs:qword_180082090
0x18000dfa2  mov     ecx, 400000h
0x18000dfa7  test    rcx, rax
0x18000dfaa  jz      short loc_18000DFE1
0x18000dfac  mov     rax, rdx
0x18000dfaf  and     rax, rcx
0x18000dfb2  cmp     rax, rdx
0x18000dfb5  jnz     short loc_18000DFE1
0x18000dfb7  lea     rax, [rbp+57h+var_60]
0x18000dfbb  mov     [rsp+0B0h+var_88], rax
0x18000dfc0  mov     [rsp+0B0h+var_90], 2; int
0x18000dfc8  xor     r9d, r9d
0x18000dfcb  xor     r8d, r8d
0x18000dfce  lea     rdx, byte_180074E57
0x18000dfd5  lea     rcx, dword_180082080
0x18000dfdc  call    _tlgWriteTransfer_EventWriteTransfer
0x18000dfe1  cmp     [rdi+0F8h], r15b
0x18000dfe8  jz      loc_18000E25E
0x18000dfee  mov     ecx, 60h ; '`'; Size
0x18000dff3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dff8  mov     rcx, rax; this
0x18000dffb  call    ??0PduIdHelper@@QEAA@XZ; PduIdHelper::PduIdHelper(void)
0x18000e000  mov     rbx, rax
0x18000e003  lea     rsi, [rdi+0B0h]
0x18000e00a  mov     ecx, 18h; Size
0x18000e00f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e014  mov     dword ptr [rax+8], 1
0x18000e01b  mov     dword ptr [rax+0Ch], 1
0x18000e022  lea     rcx, ??_7?$_Ref_count@UIVirtualizedTextDataSender@@@std@@6B@; const std::_Ref_count<IVirtualizedTextDataSender>::`vftable'
0x18000e029  mov     [rax], rcx
0x18000e02c  mov     [rax+10h], rbx
0x18000e030  mov     [rsi], rbx
0x18000e033  mov     rbx, [rsi+8]
0x18000e037  mov     [rsi+8], rax
0x18000e03b  test    rbx, rbx
0x18000e03e  jz      short loc_18000E07B
0x18000e040  or      r14d, 0FFFFFFFFh
0x18000e044  mov     eax, r14d
0x18000e047  lock xadd [rbx+8], eax
0x18000e04c  add     eax, r14d
0x18000e04f  jnz     short loc_18000E07B
0x18000e051  mov     rax, [rbx]
0x18000e054  mov     rcx, rbx
0x18000e057  mov     rax, [rax]
0x18000e05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e05f  mov     eax, r14d
0x18000e062  lock xadd [rbx+0Ch], eax
0x18000e067  add     eax, r14d
0x18000e06a  jnz     short loc_18000E07B
0x18000e06c  mov     rax, [rbx]
0x18000e06f  mov     rcx, rbx
0x18000e072  mov     rax, [rax+8]
0x18000e076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e07b  mov     qword ptr [rbp+57h+var_60], rdi
0x18000e07f  lea     r14, [rdi+0A8h]
0x18000e086  mov     rcx, [r14]
0x18000e089  mov     [r14], r15
0x18000e08c  test    rcx, rcx
0x18000e08f  jz      short loc_18000E09E
0x18000e091  mov     rax, [rcx]
0x18000e094  mov     rax, [rax+10h]
0x18000e098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e09d  nop
0x18000e09e  lea     rbx, [rdi+0C0h]
0x18000e0a5  lea     r8, [rbp+57h+var_60]
0x18000e0a9  mov     rdx, rbx
0x18000e0ac  mov     rcx, r14
0x18000e0af  call    ??$MakeAndInitialize@VTextVirtualizationInternal@@UITextVirtualizationInternal@@AEAV?$shared_ptr@UIVirtualizedTextDataSender@@@std@@PEAVTextInputMethodFormatter@@@Details@WRL@Microsoft@@YAJPEAPEAUITextVirtualizationInternal@@AEAV?$shared_ptr@UIVirtualizedTextDataSender@@@std@@$$QEAPEAVTextInputMethodFormatter@@@Z; Microsoft::WRL::Details::MakeAndInitialize<TextVirtualizationInternal,ITextVirtualizationInternal,std::shared_ptr<IVirtualizedTextDataSender> &,TextInputMethodFormatter *>(ITextVirtualizationInternal * *,std::shared_ptr<IVirtualizedTextDataSender> &,TextInputMethodFormatter * &&)
0x18000e0b4  mov     r14d, eax
0x18000e0b7  test    eax, eax
0x18000e0b9  jns     short loc_18000E0DB
0x18000e0bb  mov     rcx, [rbp+5Fh]; this
0x18000e0bf  mov     r9d, eax; char *
0x18000e0c2  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x18000e0c9  mov     edx, 11Ah; void *
0x18000e0ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e0d3  mov     eax, r14d
0x18000e0d6  jmp     loc_18000E4B1
0x18000e0db  mov     [rbp+57h+var_70], r15
0x18000e0df  mov     [rbp+57h+var_68], r15
0x18000e0e3  mov     r8, rsi
0x18000e0e6  mov     rdx, rbx
0x18000e0e9  lea     rcx, [rbp+57h+var_68]
0x18000e0ed  call    ??$MakeAndInitialize@VIRemoteTextInputServer_ToPdu@@V1@AEAV?$shared_ptr@UIVirtualizedTextDataSender@@@std@@AEAV?$shared_ptr@UIPduIdHelper@@@3@@Details@WRL@Microsoft@@YAJPEAPEAVIRemoteTextInputServer_ToPdu@@AEAV?$shared_ptr@UIVirtualizedTextDataSender@@@std@@AEAV?$shared_ptr@UIPduIdHelper@@@5@@Z; Microsoft::WRL::Details::MakeAndInitialize<IRemoteTextInputServer_ToPdu,IRemoteTextInputServer_ToPdu,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &>(IRemoteTextInputServer_ToPdu * *,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &)
0x18000e0f2  mov     rcx, [rbp+5Fh]; this
0x18000e0f6  test    eax, eax
0x18000e0f8  js      loc_18000E4FE
0x18000e0fe  mov     qword ptr [rbp+57h+var_60], r15
0x18000e102  mov     r8, rsi
0x18000e105  mov     rdx, rbx
0x18000e108  lea     rcx, [rbp+57h+var_60]
0x18000e10c  call    ??$MakeAndInitialize@VIRemoteCoreInputViewManager_ToPdu@@V1@AEAV?$shared_ptr@UIVirtualizedTextDataSender@@@std@@AEAV?$shared_ptr@UIPduIdHelper@@@3@@Details@WRL@Microsoft@@YAJPEAPEAVIRemoteCoreInputViewManager_ToPdu@@AEAV?$shared_ptr@UIVirtualizedTextDataSender@@@std@@AEAV?$shared_ptr@UIPduIdHelper@@@5@@Z; Microsoft::WRL::Details::MakeAndInitialize<IRemoteCoreInputViewManager_ToPdu,IRemoteCoreInputViewManager_ToPdu,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &>(IRemoteCoreInputViewManager_ToPdu * *,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &)
0x18000e111  mov     rcx, [rbp+5Fh]; this
0x18000e115  test    eax, eax
0x18000e117  js      loc_18000E513
0x18000e11d  mov     rcx, [rbp+57h+var_70]
0x18000e121  mov     [rbp+57h+var_70], r15
0x18000e125  test    rcx, rcx
0x18000e128  jz      short loc_18000E137
0x18000e12a  mov     rax, [rcx]
0x18000e12d  mov     rax, [rax+10h]
0x18000e131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e136  nop
0x18000e137  mov     r8, rsi
0x18000e13a  mov     rdx, rbx
0x18000e13d  lea     rcx, [rbp+57h+var_70]
0x18000e141  call    ??$MakeAndInitialize@VITextVirtualizationClient_ToPdu@@UITextVirtualizationClient@@AEAV?$shared_ptr@UIVirtualizedTextDataSender@@@std@@AEAV?$shared_ptr@UIPduIdHelper@@@4@@Details@WRL@Microsoft@@YAJPEAPEAUITextVirtualizationClient@@AEAV?$shared_ptr@UIVirtualizedTextDataSender@@@std@@AEAV?$shared_ptr@UIPduIdHelper@@@5@@Z; Microsoft::WRL::Details::MakeAndInitialize<ITextVirtualizationClient_ToPdu,ITextVirtualizationClient,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &>(ITextVirtualizationClient * *,std::shared_ptr<IVirtualizedTextDataSender> &,std::shared_ptr<IPduIdHelper> &)
0x18000e146  mov     rcx, [rbp+5Fh]; this
0x18000e14a  test    eax, eax
0x18000e14c  js      loc_18000E528
0x18000e152  lea     rsi, [rdi+90h]
0x18000e159  mov     rcx, [rsi]
0x18000e15c  mov     [rsi], r15
0x18000e15f  test    rcx, rcx
0x18000e162  jz      short loc_18000E171
0x18000e164  mov     rax, [rcx]
0x18000e167  mov     rax, [rax+10h]
0x18000e16b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e170  nop
0x18000e171  mov     rbx, [rbp+57h+var_68]
0x18000e175  mov     rax, [rbx]
0x18000e178  mov     r8, rsi
0x18000e17b  lea     rdx, _GUID_869e9b43_7e00_4f26_b722_f81b75205fb0
0x18000e182  mov     rcx, rbx
0x18000e185  mov     rax, [rax]
0x18000e188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e18d  mov     rcx, [rbp+5Fh]; this
0x18000e191  test    eax, eax
0x18000e193  js      loc_18000E53D
0x18000e199  lea     r14, [rdi+98h]
0x18000e1a0  mov     rcx, [r14]
0x18000e1a3  mov     [r14], r15
0x18000e1a6  test    rcx, rcx
0x18000e1a9  jz      short loc_18000E1B8
0x18000e1ab  mov     rax, [rcx]
0x18000e1ae  mov     rax, [rax+10h]
0x18000e1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1b7  nop
0x18000e1b8  mov     rsi, qword ptr [rbp+57h+var_60]
0x18000e1bc  mov     rax, [rsi]
0x18000e1bf  mov     r8, r14
0x18000e1c2  lea     rdx, _GUID_91b84726_e24f_4db5_9a66_13eb7bca911c
0x18000e1c9  mov     rcx, rsi
0x18000e1cc  mov     rax, [rax]
0x18000e1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1d4  mov     rcx, [rbp+5Fh]; this
0x18000e1d8  test    eax, eax
0x18000e1da  js      loc_18000E552
0x18000e1e0  mov     rcx, [rdi+0A0h]
0x18000e1e7  mov     [rdi+0A0h], r15
0x18000e1ee  test    rcx, rcx
0x18000e1f1  jz      short loc_18000E200
0x18000e1f3  mov     rax, [rcx]
0x18000e1f6  mov     rax, [rax+10h]
0x18000e1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ff  nop
0x18000e200  mov     rcx, [rbp+57h+var_70]
0x18000e204  mov     [rdi+0A0h], rcx
0x18000e20b  mov     rax, [rcx]
0x18000e20e  mov     rax, [rax+8]
0x18000e212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e217  mov     [rdi+0F8h], r15b
0x18000e21e  mov     rcx, [rbp+57h+var_70]
0x18000e222  test    rcx, rcx
0x18000e225  jz      short loc_18000E234
0x18000e227  mov     rax, [rcx]
0x18000e22a  mov     rax, [rax+10h]
0x18000e22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e233  nop
0x18000e234  test    rsi, rsi
0x18000e237  jz      short loc_18000E249
0x18000e239  mov     rax, [rsi]
0x18000e23c  mov     rcx, rsi
0x18000e23f  mov     rax, [rax+10h]
0x18000e243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e248  nop
0x18000e249  test    rbx, rbx
0x18000e24c  jz      short loc_18000E25E
0x18000e24e  mov     rax, [rbx]
0x18000e251  mov     rcx, rbx
0x18000e254  mov     rax, [rax+10h]
0x18000e258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e25d  nop
0x18000e25e  xor     r9d, r9d; unsigned int
0x18000e261  xor     r8d, r8d; unsigned int
0x18000e264  xor     edx, edx; bool
0x18000e266  mov     rcx, rdi; this
0x18000e269  call    ?EnableRemoteKeyRouting@TextInputMethodFormatter@@AEAAJ_NII@Z; TextInputMethodFormatter::EnableRemoteKeyRouting(bool,uint,uint)
0x18000e26e  test    eax, eax
0x18000e270  js      loc_18000E567
0x18000e276  mov     rcx, [rdi+0A0h]
0x18000e27d  mov     rax, [rcx]
0x18000e280  mov     rax, [rax+18h]
0x18000e284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e289  jmp     loc_18000E4AF
0x18000e28e  mov     eax, cs:dword_180082080
0x18000e294  cmp     eax, 5
0x18000e297  jbe     short loc_18000E2E6
0x18000e299  mov     rdx, cs:qword_180082098
0x18000e2a0  mov     rax, cs:qword_180082090
0x18000e2a7  mov     ecx, 400000h
0x18000e2ac  test    rcx, rax
0x18000e2af  jz      short loc_18000E2E6
0x18000e2b1  mov     rax, rdx
0x18000e2b4  and     rax, rcx
0x18000e2b7  cmp     rax, rdx
0x18000e2ba  jnz     short loc_18000E2E6
0x18000e2bc  lea     rax, [rbp+57h+var_60]
0x18000e2c0  mov     [rsp+0B0h+var_88], rax
0x18000e2c5  mov     [rsp+0B0h+var_90], 2
0x18000e2cd  xor     r9d, r9d
0x18000e2d0  xor     r8d, r8d
0x18000e2d3  lea     rdx, word_180074DF2
0x18000e2da  lea     rcx, dword_180082080
0x18000e2e1  call    _tlgWriteTransfer_EventWriteTransfer
0x18000e2e6  mov     rax, cs:Feature_TextVirtPostNiBugFix__descriptor
0x18000e2ed  mov     r8d, [rax]
0x18000e2f0  test    r8b, 4
0x18000e2f4  jnz     short loc_18000E309
0x18000e2f6  lea     rdx, [rbp+57h+var_60]
0x18000e2fa  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TextVirtPostNiBugFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(void)
0x18000e2ff  mov     rcx, [rax]
0x18000e302  mov     qword ptr [rbp+57h+var_60], rcx
0x18000e306  mov     r8d, ecx
0x18000e309  mov     dword ptr [rbp+57h+var_70], r15d
0x18000e30d  mov     word ptr [rbp+57h+var_70+4], 3
0x18000e313  mov     r9d, r8d
0x18000e316  shr     r9d, 0Bh
0x18000e31a  and     r9d, 1
0x18000e31e  shr     r8d, 0Ah
0x18000e322  and     r8d, 1
0x18000e326  mov     [rsp+0B0h+var_80], 3
0x18000e32e  mov     dword ptr [rsp+0B0h+var_88], 1
0x18000e336  lea     rax, [rbp+57h+var_70]
0x18000e33a  mov     qword ptr [rsp+0B0h+var_90], rax
0x18000e33f  mov     edx, 28F2738h
0x18000e344  lea     rcx, qword_1800827F8
0x18000e34b  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000e350  mov     ebx, 7
0x18000e355  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RemoteTextIntegration_Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RemoteTextIntegration_Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoteTextIntegration_Perf> `wil::Feature<__WilFeatureTraits_Feature_RemoteTextIntegration_Perf>::GetImpl(void)'::`2'::impl
0x18000e35c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RemoteTextIntegration_Perf@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RemoteTextIntegration_Perf>::__private_IsEnabled(void)
0x18000e361  lea     ecx, [rbx+8]
0x18000e364  test    al, al
0x18000e366  cmovnz  ebx, ecx
0x18000e369  mov     rcx, [rdi+90h]
0x18000e370  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000e377  movdqu  [rbp+57h+var_60], xmm0
0x18000e37c  mov     rax, [rcx]
0x18000e37f  mov     r9d, ebx
0x18000e382  mov     r8d, 1
0x18000e388  lea     rdx, [rbp+57h+var_60]
0x18000e38c  mov     rax, [rax+200h]
0x18000e393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e398  jmp     loc_18000E4AF
0x18000e39d  mov     eax, cs:dword_180082080
0x18000e3a3  cmp     eax, 5
0x18000e3a6  jbe     short loc_18000E3F5
0x18000e3a8  mov     rdx, cs:qword_180082098
0x18000e3af  mov     rax, cs:qword_180082090
0x18000e3b6  mov     ecx, 400000h
0x18000e3bb  test    rcx, rax
0x18000e3be  jz      short loc_18000E3F5
0x18000e3c0  mov     rax, rdx
0x18000e3c3  and     rax, rcx
0x18000e3c6  cmp     rax, rdx
0x18000e3c9  jnz     short loc_18000E3F5
0x18000e3cb  lea     rax, [rbp+57h+var_60]
0x18000e3cf  mov     [rsp+0B0h+var_88], rax
0x18000e3d4  mov     [rsp+0B0h+var_90], 2; int
0x18000e3dc  xor     r9d, r9d
0x18000e3df  xor     r8d, r8d
0x18000e3e2  lea     rdx, dword_180074DA4
0x18000e3e9  lea     rcx, dword_180082080
0x18000e3f0  call    _tlgWriteTransfer_EventWriteTransfer
  ... truncated ...
```
