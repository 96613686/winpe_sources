# ControllerHostTelemetry::CreateVirtualTouchPad::StopActivity(void)

- ea: `0x1800117d0`
- end: `0x180012350`
- name: `?StopActivity@CreateVirtualTouchPad@ControllerHostTelemetry@@MEAAXXZ`
- size: `2944`
- prototype: `void __fastcall(ControllerHostTelemetry::CreateVirtualTouchPad *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x180001478`
- `0x180001a34`
- `0x180001a44`
- `0x180001a54`
- `0x180001c6c`
- `0x180002a48`
- `0x180002c84`
- `0x18000e028`
- `0x18000e3e4`
- `0x18000ea48`
- `0x18000ea88`
- `0x1800102f8`
- `0x1800117d0`
- `0x1800127d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012238`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012238`

## pseudocode

```c
void __fastcall ControllerHostTelemetry::CreateVirtualTouchPad::StopActivity(
        ControllerHostTelemetry::CreateVirtualTouchPad *this)
{
  __int64 v1; // [rsp+C0h] [rbp-2F8h]
  int v2; // [rsp+D4h] [rbp-2E4h] BYREF
  _BYTE v3[4]; // [rsp+D8h] [rbp-2E0h] BYREF
  int v4; // [rsp+DCh] [rbp-2DCh] BYREF
  _BYTE v5[4]; // [rsp+E0h] [rbp-2D8h] BYREF
  int v6; // [rsp+E4h] [rbp-2D4h] BYREF
  _BYTE v7[4]; // [rsp+E8h] [rbp-2D0h] BYREF
  int v8; // [rsp+ECh] [rbp-2CCh] BYREF
  _BYTE v9[4]; // [rsp+F0h] [rbp-2C8h] BYREF
  _BYTE v10[4]; // [rsp+F4h] [rbp-2C4h] BYREF
  int v11; // [rsp+F8h] [rbp-2C0h] BYREF
  _BYTE v12[4]; // [rsp+FCh] [rbp-2BCh] BYREF
  unsigned int v13; // [rsp+140h] [rbp-278h]
  DWORD CurrentThreadId; // [rsp+144h] [rbp-274h] BYREF
  _BYTE v15[4]; // [rsp+148h] [rbp-270h] BYREF
  int Result; // [rsp+14Ch] [rbp-26Ch] BYREF
  _BYTE v17[4]; // [rsp+150h] [rbp-268h] BYREF
  unsigned int v18; // [rsp+154h] [rbp-264h]
  const struct _tlgProvider_t *v19; // [rsp+158h] [rbp-260h]
  const struct _tlgProvider_t *v20; // [rsp+168h] [rbp-250h]
  __int64 FailureInfo; // [rsp+170h] [rbp-248h]
  ControllerHostTelemetry::CreateVirtualTouchPad *v22; // [rsp+178h] [rbp-240h]
  ControllerHostTelemetry::CreateVirtualTouchPad *v23; // [rsp+188h] [rbp-230h]
  const struct _tlgProvider_t *v24; // [rsp+190h] [rbp-228h]
  __int64 v25; // [rsp+198h] [rbp-220h] BYREF
  _BYTE v26[8]; // [rsp+1A0h] [rbp-218h] BYREF
  _BYTE v27[8]; // [rsp+1A8h] [rbp-210h] BYREF
  __int64 v28; // [rsp+1B0h] [rbp-208h]
  __int64 v29; // [rsp+1B8h] [rbp-200h]
  _BYTE *v30; // [rsp+1C0h] [rbp-1F8h]
  __int64 v31; // [rsp+1C8h] [rbp-1F0h]
  __int64 v32; // [rsp+1D0h] [rbp-1E8h]
  _BYTE *v33; // [rsp+1D8h] [rbp-1E0h]
  __int64 v34; // [rsp+1E0h] [rbp-1D8h]
  _BYTE *v35; // [rsp+1E8h] [rbp-1D0h]
  __int64 v36; // [rsp+1F0h] [rbp-1C8h]
  _BYTE *v37; // [rsp+1F8h] [rbp-1C0h]
  __int64 v38; // [rsp+200h] [rbp-1B8h]
  _BYTE *v39; // [rsp+208h] [rbp-1B0h]
  __int64 v40; // [rsp+210h] [rbp-1A8h]
  _BYTE *v41; // [rsp+218h] [rbp-1A0h]
  _BYTE *v42; // [rsp+220h] [rbp-198h]
  _BYTE *v43; // [rsp+228h] [rbp-190h]
  __int64 v44; // [rsp+230h] [rbp-188h]
  const struct _tlgProvider_t *v45; // [rsp+2F8h] [rbp-C0h]
  _BYTE v46[8]; // [rsp+300h] [rbp-B8h] BYREF
  _BYTE *v47; // [rsp+308h] [rbp-B0h]
  _BYTE *v48; // [rsp+310h] [rbp-A8h]
  _BYTE *v49; // [rsp+318h] [rbp-A0h]
  __int64 v50; // [rsp+320h] [rbp-98h]
  _BYTE v51[8]; // [rsp+328h] [rbp-90h] BYREF
  _BYTE v52[8]; // [rsp+330h] [rbp-88h] BYREF
  _BYTE v53[8]; // [rsp+338h] [rbp-80h] BYREF
  _BYTE v54[8]; // [rsp+340h] [rbp-78h] BYREF
  _BYTE v55[8]; // [rsp+348h] [rbp-70h] BYREF
  _BYTE v56[8]; // [rsp+350h] [rbp-68h] BYREF
  _BYTE v57[8]; // [rsp+358h] [rbp-60h] BYREF
  _BYTE v58[8]; // [rsp+360h] [rbp-58h] BYREF

  FailureInfo = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(this);
  if ( FailureInfo )
  {
    v1 = FailureInfo;
    v22 = this;
    wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v19 = ControllerHostLogging::Provider();
    v24 = v19;
    v18 = *(_DWORD *)v19;
    if ( v18 > 5 && (unsigned __int8)tlgKeywordOn(v19, 0x200000000000LL) )
    {
      v28 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v51, *(_QWORD *)(FailureInfo + 120));
      v29 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v52, *(_QWORD *)(FailureInfo + 112));
      v2 = *(_DWORD *)(FailureInfo + 104);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v3, &v2);
      v30 = v3;
      v31 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v53, *(_QWORD *)(v1 + 96));
      v32 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v54, *(_QWORD *)(v1 + 88));
      v4 = *(_DWORD *)(v1 + 80);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v5, &v4);
      v33 = v5;
      v34 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v55, *(_QWORD *)(v1 + 72));
      v6 = *(_DWORD *)(v1 + 32);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v7, &v6);
      v35 = v7;
      v36 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v56, *(_QWORD *)(v1 + 24));
      v8 = *(_DWORD *)v1;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v9, &v8);
      v37 = v9;
      v38 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v57, *(_QWORD *)(v1 + 128));
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v10, v1 + 64);
      v39 = v10;
      v40 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(v58, *(_QWORD *)(v1 + 56));
      v11 = *(_DWORD *)(v1 + 8);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v12, &v11);
      v41 = v12;
      v25 = 0x1000000;
      _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(v26, &v25);
      v42 = v26;
      _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(
        v27,
        &`ControllerHostTelemetry::CreateVirtualTouchPad::StopActivity'::`10'::_tlgActivityPrivacyTag);
      v43 = v27;
      v44 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v22);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v19,
        (unsigned int)byte_180020C39,
        v44,
        0,
        (__int64)v43,
        (__int64)v42,
        (__int64)v41,
        v40,
        (__int64)v39,
        v38,
        (__int64)v37,
        v36,
        (__int64)v35,
        v34,
        (__int64)v33,
        v32,
        v31,
        (__int64)v30,
        v29,
        v28);
    }
  }
  else
  {
    v23 = this;
    wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v20 = ControllerHostLogging::Provider();
    v45 = v20;
    v13 = *(_DWORD *)v20;
    if ( v13 > 5 && (unsigned __int8)tlgKeywordOn(v20, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v15, &CurrentThreadId);
      v47 = v15;
      Result = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v17, &Result);
      v48 = v17;
      _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(
        v46,
        `ControllerHostTelemetry::CreateVirtualTouchPad::StopActivity'::`28'::_tlgActivityPrivacyTag);
      v49 = v46;
      v50 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v23);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v20,
        (unsigned int)&word_180020EB6,
        v50,
        0,
        (__int64)v49,
        (__int64)v48,
        (__int64)v47);
    }
  }
  wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800117d0  mov     [rsp+arg_0], rcx
0x1800117d5  sub     rsp, 3B8h
0x1800117dc  mov     rcx, [rsp+3B8h+arg_0]
0x1800117e4  call    ?GetFailureInfo@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x1800117e9  mov     [rsp+3B8h+var_248], rax
0x1800117f1  cmp     [rsp+3B8h+var_248], 0
0x1800117fa  jz      loc_1800121A4
0x180011800  mov     rax, [rsp+3B8h+var_248]
0x180011808  mov     [rsp+3B8h+var_2F8], rax
0x180011810  xor     eax, eax
0x180011812  cmp     eax, 1
0x180011815  jz      loc_180011C7F
0x18001181b  mov     rax, [rsp+3B8h+arg_0]
0x180011823  mov     [rsp+3B8h+var_240], rax
0x18001182b  mov     rcx, [rsp+3B8h+var_240]
0x180011833  call    ?zInternalStop@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180011838  nop
0x180011839  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x18001183e  mov     [rsp+3B8h+var_260], rax
0x180011846  mov     rax, [rsp+3B8h+var_260]
0x18001184e  mov     [rsp+3B8h+var_228], rax
0x180011856  mov     [rsp+3B8h+var_2F0], 0
0x180011861  mov     rax, [rsp+3B8h+var_228]
0x180011869  mov     eax, [rax]
0x18001186b  mov     [rsp+3B8h+var_2F0], eax
0x180011872  mov     eax, [rsp+3B8h+var_2F0]
0x180011879  mov     [rsp+3B8h+var_264], eax
0x180011880  mov     eax, [rsp+3B8h+var_264]
0x180011887  cmp     eax, 5
0x18001188a  jbe     loc_180011C66
0x180011890  mov     rdx, cs:qword_180020C3C
0x180011897  mov     rcx, [rsp+3B8h+var_260]
0x18001189f  call    _tlgKeywordOn
0x1800118a4  movzx   eax, al
0x1800118a7  test    eax, eax
0x1800118a9  jz      loc_180011C66
0x1800118af  mov     rax, [rsp+3B8h+var_2F8]
0x1800118b7  mov     rdx, [rax+78h]
0x1800118bb  lea     rcx, [rsp+3B8h+var_90]
0x1800118c3  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x1800118c8  mov     [rsp+3B8h+var_208], rax
0x1800118d0  mov     rax, [rsp+3B8h+var_2F8]
0x1800118d8  mov     rdx, [rax+70h]
0x1800118dc  lea     rcx, [rsp+3B8h+var_88]
0x1800118e4  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x1800118e9  mov     [rsp+3B8h+var_200], rax
0x1800118f1  mov     rax, [rsp+3B8h+var_2F8]
0x1800118f9  mov     eax, [rax+68h]
0x1800118fc  mov     [rsp+3B8h+var_2E4], eax
0x180011903  lea     rdx, [rsp+3B8h+var_2E4]
0x18001190b  lea     rcx, [rsp+3B8h+var_2E0]
0x180011913  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011918  nop
0x180011919  lea     rax, [rsp+3B8h+var_2E0]
0x180011921  mov     [rsp+3B8h+var_1F8], rax
0x180011929  mov     rax, [rsp+3B8h+var_2F8]
0x180011931  mov     rdx, [rax+60h]
0x180011935  lea     rcx, [rsp+3B8h+var_80]
0x18001193d  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011942  mov     [rsp+3B8h+var_1F0], rax
0x18001194a  mov     rax, [rsp+3B8h+var_2F8]
0x180011952  mov     rdx, [rax+58h]
0x180011956  lea     rcx, [rsp+3B8h+var_78]
0x18001195e  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011963  mov     [rsp+3B8h+var_1E8], rax
0x18001196b  mov     rax, [rsp+3B8h+var_2F8]
0x180011973  mov     eax, [rax+50h]
0x180011976  mov     [rsp+3B8h+var_2DC], eax
0x18001197d  lea     rdx, [rsp+3B8h+var_2DC]
0x180011985  lea     rcx, [rsp+3B8h+var_2D8]
0x18001198d  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011992  nop
0x180011993  lea     rax, [rsp+3B8h+var_2D8]
0x18001199b  mov     [rsp+3B8h+var_1E0], rax
0x1800119a3  mov     rax, [rsp+3B8h+var_2F8]
0x1800119ab  mov     rdx, [rax+48h]
0x1800119af  lea     rcx, [rsp+3B8h+var_70]
0x1800119b7  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x1800119bc  mov     [rsp+3B8h+var_1D8], rax
0x1800119c4  mov     rax, [rsp+3B8h+var_2F8]
0x1800119cc  mov     eax, [rax+20h]
0x1800119cf  mov     [rsp+3B8h+var_2D4], eax
0x1800119d6  lea     rdx, [rsp+3B8h+var_2D4]
0x1800119de  lea     rcx, [rsp+3B8h+var_2D0]
0x1800119e6  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800119eb  nop
0x1800119ec  lea     rax, [rsp+3B8h+var_2D0]
0x1800119f4  mov     [rsp+3B8h+var_1D0], rax
0x1800119fc  mov     rax, [rsp+3B8h+var_2F8]
0x180011a04  mov     rdx, [rax+18h]
0x180011a08  lea     rcx, [rsp+3B8h+var_68]
0x180011a10  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011a15  mov     [rsp+3B8h+var_1C8], rax
0x180011a1d  mov     rax, [rsp+3B8h+var_2F8]
0x180011a25  mov     eax, [rax]
0x180011a27  mov     [rsp+3B8h+var_2CC], eax
0x180011a2e  lea     rdx, [rsp+3B8h+var_2CC]
0x180011a36  lea     rcx, [rsp+3B8h+var_2C8]
0x180011a3e  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011a43  nop
0x180011a44  lea     rax, [rsp+3B8h+var_2C8]
0x180011a4c  mov     [rsp+3B8h+var_1C0], rax
0x180011a54  mov     rax, [rsp+3B8h+var_2F8]
0x180011a5c  mov     rdx, [rax+80h]
0x180011a63  lea     rcx, [rsp+3B8h+var_60]
0x180011a6b  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011a70  mov     [rsp+3B8h+var_1B8], rax
0x180011a78  mov     rax, [rsp+3B8h+var_2F8]
0x180011a80  add     rax, 40h ; '@'
0x180011a84  mov     rdx, rax
0x180011a87  lea     rcx, [rsp+3B8h+var_2C4]
0x180011a8f  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011a94  nop
0x180011a95  lea     rax, [rsp+3B8h+var_2C4]
0x180011a9d  mov     [rsp+3B8h+var_1B0], rax
0x180011aa5  mov     rax, [rsp+3B8h+var_2F8]
0x180011aad  mov     rdx, [rax+38h]
0x180011ab1  lea     rcx, [rsp+3B8h+var_58]
0x180011ab9  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011abe  mov     [rsp+3B8h+var_1A8], rax
0x180011ac6  mov     rax, [rsp+3B8h+var_2F8]
0x180011ace  mov     eax, [rax+8]
0x180011ad1  mov     [rsp+3B8h+var_2C0], eax
0x180011ad8  lea     rdx, [rsp+3B8h+var_2C0]
0x180011ae0  lea     rcx, [rsp+3B8h+var_2BC]
0x180011ae8  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011aed  nop
0x180011aee  lea     rax, [rsp+3B8h+var_2BC]
0x180011af6  mov     [rsp+3B8h+var_1A0], rax
0x180011afe  mov     [rsp+3B8h+var_220], 1000000h
0x180011b0a  lea     rdx, [rsp+3B8h+var_220]
0x180011b12  lea     rcx, [rsp+3B8h+var_218]
0x180011b1a  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x180011b1f  nop
0x180011b20  lea     rax, [rsp+3B8h+var_218]
0x180011b28  mov     [rsp+3B8h+var_198], rax
0x180011b30  lea     rdx, ?_tlgActivityPrivacyTag@?9??StopActivity@CreateVirtualTouchPad@ControllerHostTelemetry@@MEAAXXZ@4_KB; unsigned __int64 const `ControllerHostTelemetry::CreateVirtualTouchPad::StopActivity(void)'::`10'::_tlgActivityPrivacyTag
0x180011b37  lea     rcx, [rsp+3B8h+var_210]
0x180011b3f  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x180011b44  nop
0x180011b45  lea     rax, [rsp+3B8h+var_210]
0x180011b4d  mov     [rsp+3B8h+var_190], rax
0x180011b55  mov     rcx, [rsp+3B8h+var_240]
0x180011b5d  call    ?Id@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180011b62  mov     [rsp+3B8h+var_188], rax
0x180011b6a  mov     rax, [rsp+3B8h+var_208]
0x180011b72  mov     [rsp+3B8h+var_320], rax
0x180011b7a  mov     rax, [rsp+3B8h+var_200]
0x180011b82  mov     [rsp+3B8h+var_328], rax
0x180011b8a  mov     rax, [rsp+3B8h+var_1F8]
0x180011b92  mov     [rsp+3B8h+var_330], rax
0x180011b9a  mov     rax, [rsp+3B8h+var_1F0]
0x180011ba2  mov     [rsp+3B8h+var_338], rax
0x180011baa  mov     rax, [rsp+3B8h+var_1E8]
0x180011bb2  mov     [rsp+3B8h+var_340], rax
0x180011bb7  mov     rax, [rsp+3B8h+var_1E0]
0x180011bbf  mov     [rsp+3B8h+var_348], rax
0x180011bc4  mov     rax, [rsp+3B8h+var_1D8]
0x180011bcc  mov     [rsp+3B8h+var_350], rax
0x180011bd1  mov     rax, [rsp+3B8h+var_1D0]
0x180011bd9  mov     [rsp+3B8h+var_358], rax
0x180011bde  mov     rax, [rsp+3B8h+var_1C8]
0x180011be6  mov     [rsp+3B8h+var_360], rax
0x180011beb  mov     rax, [rsp+3B8h+var_1C0]
0x180011bf3  mov     [rsp+3B8h+var_368], rax
0x180011bf8  mov     rax, [rsp+3B8h+var_1B8]
0x180011c00  mov     [rsp+3B8h+var_370], rax
0x180011c05  mov     rax, [rsp+3B8h+var_1B0]
0x180011c0d  mov     [rsp+3B8h+var_378], rax
0x180011c12  mov     rax, [rsp+3B8h+var_1A8]
0x180011c1a  mov     [rsp+3B8h+var_380], rax
0x180011c1f  mov     rax, [rsp+3B8h+var_1A0]
0x180011c27  mov     [rsp+3B8h+var_388], rax
0x180011c2c  mov     rax, [rsp+3B8h+var_198]
0x180011c34  mov     [rsp+3B8h+var_390], rax
0x180011c39  mov     rax, [rsp+3B8h+var_190]
0x180011c41  mov     [rsp+3B8h+var_398], rax
0x180011c46  xor     r9d, r9d
0x180011c49  mov     r8, [rsp+3B8h+var_188]
0x180011c51  lea     rdx, byte_180020C39
0x180011c58  mov     rcx, [rsp+3B8h+var_260]
0x180011c60  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180011c65  nop
0x180011c66  xor     eax, eax
0x180011c68  test    eax, eax
0x180011c6a  jnz     loc_180011839
0x180011c70  xor     eax, eax
0x180011c72  test    eax, eax
0x180011c74  jnz     loc_18001181B
0x180011c7a  jmp     loc_18001219F
0x180011c7f  mov     rax, [rsp+3B8h+arg_0]
0x180011c87  mov     [rsp+3B8h+var_238], rax
0x180011c8f  mov     rcx, [rsp+3B8h+var_238]
0x180011c97  call    ?zInternalStop@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180011c9c  nop
0x180011c9d  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x180011ca2  mov     [rsp+3B8h+var_258], rax
0x180011caa  mov     rax, [rsp+3B8h+var_258]
0x180011cb2  mov     [rsp+3B8h+var_180], rax
0x180011cba  mov     [rsp+3B8h+var_2EC], 0
0x180011cc5  mov     rax, [rsp+3B8h+var_180]
0x180011ccd  mov     eax, [rax]
0x180011ccf  mov     [rsp+3B8h+var_2EC], eax
0x180011cd6  mov     eax, [rsp+3B8h+var_2EC]
0x180011cdd  mov     [rsp+3B8h+var_2B8], eax
0x180011ce4  mov     eax, [rsp+3B8h+var_2B8]
0x180011ceb  cmp     eax, 5
0x180011cee  jbe     loc_18001218B
0x180011cf4  mov     rdx, cs:qword_180020D69
0x180011cfb  mov     rcx, [rsp+3B8h+var_258]
0x180011d03  call    _tlgKeywordOn
0x180011d08  movzx   eax, al
0x180011d0b  test    eax, eax
0x180011d0d  jz      loc_18001218B
0x180011d13  mov     rax, [rsp+3B8h+var_2F8]
0x180011d1b  mov     rdx, [rax+30h]
0x180011d1f  lea     rcx, [rsp+3B8h+var_50]
0x180011d27  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011d2c  mov     [rsp+3B8h+var_160], rax
0x180011d34  mov     rax, [rsp+3B8h+var_2F8]
0x180011d3c  mov     eax, [rax+44h]
0x180011d3f  mov     [rsp+3B8h+var_2B4], eax
0x180011d46  lea     rdx, [rsp+3B8h+var_2B4]
0x180011d4e  lea     rcx, [rsp+3B8h+var_2B0]
0x180011d56  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011d5b  nop
0x180011d5c  lea     rax, [rsp+3B8h+var_2B0]
0x180011d64  mov     [rsp+3B8h+var_158], rax
0x180011d6c  mov     rax, [rsp+3B8h+var_2F8]
0x180011d74  mov     eax, [rax+10h]
0x180011d77  mov     [rsp+3B8h+var_2AC], eax
0x180011d7e  lea     rdx, [rsp+3B8h+var_2AC]
0x180011d86  lea     rcx, [rsp+3B8h+var_2A8]
0x180011d8e  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011d93  nop
0x180011d94  lea     rax, [rsp+3B8h+var_2A8]
0x180011d9c  mov     [rsp+3B8h+var_150], rax
0x180011da4  mov     rax, [rsp+3B8h+var_2F8]
0x180011dac  mov     rdx, [rax+78h]
0x180011db0  lea     rcx, [rsp+3B8h+var_48]
0x180011db8  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011dbd  mov     [rsp+3B8h+var_148], rax
0x180011dc5  mov     rax, [rsp+3B8h+var_2F8]
0x180011dcd  mov     rdx, [rax+70h]
0x180011dd1  lea     rcx, [rsp+3B8h+var_40]
0x180011dd9  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011dde  mov     [rsp+3B8h+var_140], rax
0x180011de6  mov     rax, [rsp+3B8h+var_2F8]
0x180011dee  mov     eax, [rax+68h]
0x180011df1  mov     [rsp+3B8h+var_2A4], eax
0x180011df8  lea     rdx, [rsp+3B8h+var_2A4]
0x180011e00  lea     rcx, [rsp+3B8h+var_2A0]
0x180011e08  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011e0d  nop
0x180011e0e  lea     rax, [rsp+3B8h+var_2A0]
0x180011e16  mov     [rsp+3B8h+var_138], rax
0x180011e1e  mov     rax, [rsp+3B8h+var_2F8]
0x180011e26  mov     rdx, [rax+60h]
0x180011e2a  lea     rcx, [rsp+3B8h+var_38]
0x180011e32  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011e37  mov     [rsp+3B8h+var_130], rax
0x180011e3f  mov     rax, [rsp+3B8h+var_2F8]
0x180011e47  mov     rdx, [rax+58h]
0x180011e4b  lea     rcx, [rsp+3B8h+var_30]
0x180011e53  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011e58  mov     [rsp+3B8h+var_128], rax
0x180011e60  mov     rax, [rsp+3B8h+var_2F8]
0x180011e68  mov     eax, [rax+50h]
0x180011e6b  mov     [rsp+3B8h+var_29C], eax
0x180011e72  lea     rdx, [rsp+3B8h+var_29C]
0x180011e7a  lea     rcx, [rsp+3B8h+var_298]
0x180011e82  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011e87  nop
0x180011e88  lea     rax, [rsp+3B8h+var_298]
0x180011e90  mov     [rsp+3B8h+var_120], rax
0x180011e98  mov     rax, [rsp+3B8h+var_2F8]
0x180011ea0  mov     rdx, [rax+48h]
0x180011ea4  lea     rcx, [rsp+3B8h+var_28]
0x180011eac  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011eb1  mov     [rsp+3B8h+var_118], rax
0x180011eb9  mov     rax, [rsp+3B8h+var_2F8]
0x180011ec1  mov     eax, [rax+20h]
0x180011ec4  mov     [rsp+3B8h+var_294], eax
0x180011ecb  lea     rdx, [rsp+3B8h+var_294]
0x180011ed3  lea     rcx, [rsp+3B8h+var_290]
0x180011edb  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180011ee0  nop
0x180011ee1  lea     rax, [rsp+3B8h+var_290]
0x180011ee9  mov     [rsp+3B8h+var_110], rax
0x180011ef1  mov     rax, [rsp+3B8h+var_2F8]
0x180011ef9  mov     rdx, [rax+18h]
0x180011efd  lea     rcx, [rsp+3B8h+var_20]
0x180011f05  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180011f0a  mov     [rsp+3B8h+var_108], rax
0x180011f12  mov     rax, [rsp+3B8h+var_2F8]
0x180011f1a  mov     eax, [rax]
0x180011f1c  mov     [rsp+3B8h+var_28C], eax
0x180011f23  lea     rdx, [rsp+3B8h+var_28C]
0x180011f2b  lea     rcx, [rsp+3B8h+var_288]
0x180011f33  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
  ... truncated ...
```
