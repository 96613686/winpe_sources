# ControllerHostTelemetry::InputInjectionSession::StopActivity(void)

- ea: `0x1800179c0`
- end: `0x180018540`
- name: `?StopActivity@InputInjectionSession@ControllerHostTelemetry@@MEAAXXZ`
- size: `2944`
- prototype: `void __fastcall(ControllerHostTelemetry::InputInjectionSession *__hidden this)`
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
- `0x1800127d0`
- `0x1800179c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018428`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018428`

## pseudocode

```c
void __fastcall ControllerHostTelemetry::InputInjectionSession::StopActivity(
        ControllerHostTelemetry::InputInjectionSession *this)
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
  ControllerHostTelemetry::InputInjectionSession *v22; // [rsp+178h] [rbp-240h]
  ControllerHostTelemetry::InputInjectionSession *v23; // [rsp+188h] [rbp-230h]
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
        &`ControllerHostTelemetry::InputInjectionSession::StopActivity'::`10'::_tlgActivityPrivacyTag);
      v43 = v27;
      v44 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v22);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v19,
        (unsigned int)&word_1800210CA,
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
        &`ControllerHostTelemetry::InputInjectionSession::StopActivity'::`28'::_tlgActivityPrivacyTag);
      v49 = v46;
      v50 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v23);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v20,
        (unsigned int)&byte_180021347,
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
0x1800179c0  mov     [rsp+arg_0], rcx
0x1800179c5  sub     rsp, 3B8h
0x1800179cc  mov     rcx, [rsp+3B8h+arg_0]
0x1800179d4  call    ?GetFailureInfo@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x1800179d9  mov     [rsp+3B8h+var_248], rax
0x1800179e1  cmp     [rsp+3B8h+var_248], 0
0x1800179ea  jz      loc_180018394
0x1800179f0  mov     rax, [rsp+3B8h+var_248]
0x1800179f8  mov     [rsp+3B8h+var_2F8], rax
0x180017a00  xor     eax, eax
0x180017a02  cmp     eax, 1
0x180017a05  jz      loc_180017E6F
0x180017a0b  mov     rax, [rsp+3B8h+arg_0]
0x180017a13  mov     [rsp+3B8h+var_240], rax
0x180017a1b  mov     rcx, [rsp+3B8h+var_240]
0x180017a23  call    ?zInternalStop@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180017a28  nop
0x180017a29  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x180017a2e  mov     [rsp+3B8h+var_260], rax
0x180017a36  mov     rax, [rsp+3B8h+var_260]
0x180017a3e  mov     [rsp+3B8h+var_228], rax
0x180017a46  mov     [rsp+3B8h+var_2F0], 0
0x180017a51  mov     rax, [rsp+3B8h+var_228]
0x180017a59  mov     eax, [rax]
0x180017a5b  mov     [rsp+3B8h+var_2F0], eax
0x180017a62  mov     eax, [rsp+3B8h+var_2F0]
0x180017a69  mov     [rsp+3B8h+var_264], eax
0x180017a70  mov     eax, [rsp+3B8h+var_264]
0x180017a77  cmp     eax, 5
0x180017a7a  jbe     loc_180017E56
0x180017a80  mov     rdx, cs:qword_1800210CD
0x180017a87  mov     rcx, [rsp+3B8h+var_260]
0x180017a8f  call    _tlgKeywordOn
0x180017a94  movzx   eax, al
0x180017a97  test    eax, eax
0x180017a99  jz      loc_180017E56
0x180017a9f  mov     rax, [rsp+3B8h+var_2F8]
0x180017aa7  mov     rdx, [rax+78h]
0x180017aab  lea     rcx, [rsp+3B8h+var_90]
0x180017ab3  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017ab8  mov     [rsp+3B8h+var_208], rax
0x180017ac0  mov     rax, [rsp+3B8h+var_2F8]
0x180017ac8  mov     rdx, [rax+70h]
0x180017acc  lea     rcx, [rsp+3B8h+var_88]
0x180017ad4  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017ad9  mov     [rsp+3B8h+var_200], rax
0x180017ae1  mov     rax, [rsp+3B8h+var_2F8]
0x180017ae9  mov     eax, [rax+68h]
0x180017aec  mov     [rsp+3B8h+var_2E4], eax
0x180017af3  lea     rdx, [rsp+3B8h+var_2E4]
0x180017afb  lea     rcx, [rsp+3B8h+var_2E0]
0x180017b03  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017b08  nop
0x180017b09  lea     rax, [rsp+3B8h+var_2E0]
0x180017b11  mov     [rsp+3B8h+var_1F8], rax
0x180017b19  mov     rax, [rsp+3B8h+var_2F8]
0x180017b21  mov     rdx, [rax+60h]
0x180017b25  lea     rcx, [rsp+3B8h+var_80]
0x180017b2d  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017b32  mov     [rsp+3B8h+var_1F0], rax
0x180017b3a  mov     rax, [rsp+3B8h+var_2F8]
0x180017b42  mov     rdx, [rax+58h]
0x180017b46  lea     rcx, [rsp+3B8h+var_78]
0x180017b4e  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017b53  mov     [rsp+3B8h+var_1E8], rax
0x180017b5b  mov     rax, [rsp+3B8h+var_2F8]
0x180017b63  mov     eax, [rax+50h]
0x180017b66  mov     [rsp+3B8h+var_2DC], eax
0x180017b6d  lea     rdx, [rsp+3B8h+var_2DC]
0x180017b75  lea     rcx, [rsp+3B8h+var_2D8]
0x180017b7d  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017b82  nop
0x180017b83  lea     rax, [rsp+3B8h+var_2D8]
0x180017b8b  mov     [rsp+3B8h+var_1E0], rax
0x180017b93  mov     rax, [rsp+3B8h+var_2F8]
0x180017b9b  mov     rdx, [rax+48h]
0x180017b9f  lea     rcx, [rsp+3B8h+var_70]
0x180017ba7  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017bac  mov     [rsp+3B8h+var_1D8], rax
0x180017bb4  mov     rax, [rsp+3B8h+var_2F8]
0x180017bbc  mov     eax, [rax+20h]
0x180017bbf  mov     [rsp+3B8h+var_2D4], eax
0x180017bc6  lea     rdx, [rsp+3B8h+var_2D4]
0x180017bce  lea     rcx, [rsp+3B8h+var_2D0]
0x180017bd6  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017bdb  nop
0x180017bdc  lea     rax, [rsp+3B8h+var_2D0]
0x180017be4  mov     [rsp+3B8h+var_1D0], rax
0x180017bec  mov     rax, [rsp+3B8h+var_2F8]
0x180017bf4  mov     rdx, [rax+18h]
0x180017bf8  lea     rcx, [rsp+3B8h+var_68]
0x180017c00  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017c05  mov     [rsp+3B8h+var_1C8], rax
0x180017c0d  mov     rax, [rsp+3B8h+var_2F8]
0x180017c15  mov     eax, [rax]
0x180017c17  mov     [rsp+3B8h+var_2CC], eax
0x180017c1e  lea     rdx, [rsp+3B8h+var_2CC]
0x180017c26  lea     rcx, [rsp+3B8h+var_2C8]
0x180017c2e  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017c33  nop
0x180017c34  lea     rax, [rsp+3B8h+var_2C8]
0x180017c3c  mov     [rsp+3B8h+var_1C0], rax
0x180017c44  mov     rax, [rsp+3B8h+var_2F8]
0x180017c4c  mov     rdx, [rax+80h]
0x180017c53  lea     rcx, [rsp+3B8h+var_60]
0x180017c5b  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017c60  mov     [rsp+3B8h+var_1B8], rax
0x180017c68  mov     rax, [rsp+3B8h+var_2F8]
0x180017c70  add     rax, 40h ; '@'
0x180017c74  mov     rdx, rax
0x180017c77  lea     rcx, [rsp+3B8h+var_2C4]
0x180017c7f  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017c84  nop
0x180017c85  lea     rax, [rsp+3B8h+var_2C4]
0x180017c8d  mov     [rsp+3B8h+var_1B0], rax
0x180017c95  mov     rax, [rsp+3B8h+var_2F8]
0x180017c9d  mov     rdx, [rax+38h]
0x180017ca1  lea     rcx, [rsp+3B8h+var_58]
0x180017ca9  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017cae  mov     [rsp+3B8h+var_1A8], rax
0x180017cb6  mov     rax, [rsp+3B8h+var_2F8]
0x180017cbe  mov     eax, [rax+8]
0x180017cc1  mov     [rsp+3B8h+var_2C0], eax
0x180017cc8  lea     rdx, [rsp+3B8h+var_2C0]
0x180017cd0  lea     rcx, [rsp+3B8h+var_2BC]
0x180017cd8  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017cdd  nop
0x180017cde  lea     rax, [rsp+3B8h+var_2BC]
0x180017ce6  mov     [rsp+3B8h+var_1A0], rax
0x180017cee  mov     [rsp+3B8h+var_220], 1000000h
0x180017cfa  lea     rdx, [rsp+3B8h+var_220]
0x180017d02  lea     rcx, [rsp+3B8h+var_218]
0x180017d0a  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x180017d0f  nop
0x180017d10  lea     rax, [rsp+3B8h+var_218]
0x180017d18  mov     [rsp+3B8h+var_198], rax
0x180017d20  lea     rdx, ?_tlgActivityPrivacyTag@?9??StopActivity@InputInjectionSession@ControllerHostTelemetry@@MEAAXXZ@4_KB; unsigned __int64 const `ControllerHostTelemetry::InputInjectionSession::StopActivity(void)'::`10'::_tlgActivityPrivacyTag
0x180017d27  lea     rcx, [rsp+3B8h+var_210]
0x180017d2f  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x180017d34  nop
0x180017d35  lea     rax, [rsp+3B8h+var_210]
0x180017d3d  mov     [rsp+3B8h+var_190], rax
0x180017d45  mov     rcx, [rsp+3B8h+var_240]
0x180017d4d  call    ?Id@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180017d52  mov     [rsp+3B8h+var_188], rax
0x180017d5a  mov     rax, [rsp+3B8h+var_208]
0x180017d62  mov     [rsp+3B8h+var_320], rax
0x180017d6a  mov     rax, [rsp+3B8h+var_200]
0x180017d72  mov     [rsp+3B8h+var_328], rax
0x180017d7a  mov     rax, [rsp+3B8h+var_1F8]
0x180017d82  mov     [rsp+3B8h+var_330], rax
0x180017d8a  mov     rax, [rsp+3B8h+var_1F0]
0x180017d92  mov     [rsp+3B8h+var_338], rax
0x180017d9a  mov     rax, [rsp+3B8h+var_1E8]
0x180017da2  mov     [rsp+3B8h+var_340], rax
0x180017da7  mov     rax, [rsp+3B8h+var_1E0]
0x180017daf  mov     [rsp+3B8h+var_348], rax
0x180017db4  mov     rax, [rsp+3B8h+var_1D8]
0x180017dbc  mov     [rsp+3B8h+var_350], rax
0x180017dc1  mov     rax, [rsp+3B8h+var_1D0]
0x180017dc9  mov     [rsp+3B8h+var_358], rax
0x180017dce  mov     rax, [rsp+3B8h+var_1C8]
0x180017dd6  mov     [rsp+3B8h+var_360], rax
0x180017ddb  mov     rax, [rsp+3B8h+var_1C0]
0x180017de3  mov     [rsp+3B8h+var_368], rax
0x180017de8  mov     rax, [rsp+3B8h+var_1B8]
0x180017df0  mov     [rsp+3B8h+var_370], rax
0x180017df5  mov     rax, [rsp+3B8h+var_1B0]
0x180017dfd  mov     [rsp+3B8h+var_378], rax
0x180017e02  mov     rax, [rsp+3B8h+var_1A8]
0x180017e0a  mov     [rsp+3B8h+var_380], rax
0x180017e0f  mov     rax, [rsp+3B8h+var_1A0]
0x180017e17  mov     [rsp+3B8h+var_388], rax
0x180017e1c  mov     rax, [rsp+3B8h+var_198]
0x180017e24  mov     [rsp+3B8h+var_390], rax
0x180017e29  mov     rax, [rsp+3B8h+var_190]
0x180017e31  mov     [rsp+3B8h+var_398], rax
0x180017e36  xor     r9d, r9d
0x180017e39  mov     r8, [rsp+3B8h+var_188]
0x180017e41  lea     rdx, word_1800210CA
0x180017e48  mov     rcx, [rsp+3B8h+var_260]
0x180017e50  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180017e55  nop
0x180017e56  xor     eax, eax
0x180017e58  test    eax, eax
0x180017e5a  jnz     loc_180017A29
0x180017e60  xor     eax, eax
0x180017e62  test    eax, eax
0x180017e64  jnz     loc_180017A0B
0x180017e6a  jmp     loc_18001838F
0x180017e6f  mov     rax, [rsp+3B8h+arg_0]
0x180017e77  mov     [rsp+3B8h+var_238], rax
0x180017e7f  mov     rcx, [rsp+3B8h+var_238]
0x180017e87  call    ?zInternalStop@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180017e8c  nop
0x180017e8d  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x180017e92  mov     [rsp+3B8h+var_258], rax
0x180017e9a  mov     rax, [rsp+3B8h+var_258]
0x180017ea2  mov     [rsp+3B8h+var_180], rax
0x180017eaa  mov     [rsp+3B8h+var_2EC], 0
0x180017eb5  mov     rax, [rsp+3B8h+var_180]
0x180017ebd  mov     eax, [rax]
0x180017ebf  mov     [rsp+3B8h+var_2EC], eax
0x180017ec6  mov     eax, [rsp+3B8h+var_2EC]
0x180017ecd  mov     [rsp+3B8h+var_2B8], eax
0x180017ed4  mov     eax, [rsp+3B8h+var_2B8]
0x180017edb  cmp     eax, 5
0x180017ede  jbe     loc_18001837B
0x180017ee4  mov     rdx, cs:qword_1800211FA
0x180017eeb  mov     rcx, [rsp+3B8h+var_258]
0x180017ef3  call    _tlgKeywordOn
0x180017ef8  movzx   eax, al
0x180017efb  test    eax, eax
0x180017efd  jz      loc_18001837B
0x180017f03  mov     rax, [rsp+3B8h+var_2F8]
0x180017f0b  mov     rdx, [rax+30h]
0x180017f0f  lea     rcx, [rsp+3B8h+var_50]
0x180017f17  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017f1c  mov     [rsp+3B8h+var_160], rax
0x180017f24  mov     rax, [rsp+3B8h+var_2F8]
0x180017f2c  mov     eax, [rax+44h]
0x180017f2f  mov     [rsp+3B8h+var_2B4], eax
0x180017f36  lea     rdx, [rsp+3B8h+var_2B4]
0x180017f3e  lea     rcx, [rsp+3B8h+var_2B0]
0x180017f46  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017f4b  nop
0x180017f4c  lea     rax, [rsp+3B8h+var_2B0]
0x180017f54  mov     [rsp+3B8h+var_158], rax
0x180017f5c  mov     rax, [rsp+3B8h+var_2F8]
0x180017f64  mov     eax, [rax+10h]
0x180017f67  mov     [rsp+3B8h+var_2AC], eax
0x180017f6e  lea     rdx, [rsp+3B8h+var_2AC]
0x180017f76  lea     rcx, [rsp+3B8h+var_2A8]
0x180017f7e  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017f83  nop
0x180017f84  lea     rax, [rsp+3B8h+var_2A8]
0x180017f8c  mov     [rsp+3B8h+var_150], rax
0x180017f94  mov     rax, [rsp+3B8h+var_2F8]
0x180017f9c  mov     rdx, [rax+78h]
0x180017fa0  lea     rcx, [rsp+3B8h+var_48]
0x180017fa8  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017fad  mov     [rsp+3B8h+var_148], rax
0x180017fb5  mov     rax, [rsp+3B8h+var_2F8]
0x180017fbd  mov     rdx, [rax+70h]
0x180017fc1  lea     rcx, [rsp+3B8h+var_40]
0x180017fc9  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180017fce  mov     [rsp+3B8h+var_140], rax
0x180017fd6  mov     rax, [rsp+3B8h+var_2F8]
0x180017fde  mov     eax, [rax+68h]
0x180017fe1  mov     [rsp+3B8h+var_2A4], eax
0x180017fe8  lea     rdx, [rsp+3B8h+var_2A4]
0x180017ff0  lea     rcx, [rsp+3B8h+var_2A0]
0x180017ff8  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180017ffd  nop
0x180017ffe  lea     rax, [rsp+3B8h+var_2A0]
0x180018006  mov     [rsp+3B8h+var_138], rax
0x18001800e  mov     rax, [rsp+3B8h+var_2F8]
0x180018016  mov     rdx, [rax+60h]
0x18001801a  lea     rcx, [rsp+3B8h+var_38]
0x180018022  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180018027  mov     [rsp+3B8h+var_130], rax
0x18001802f  mov     rax, [rsp+3B8h+var_2F8]
0x180018037  mov     rdx, [rax+58h]
0x18001803b  lea     rcx, [rsp+3B8h+var_30]
0x180018043  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x180018048  mov     [rsp+3B8h+var_128], rax
0x180018050  mov     rax, [rsp+3B8h+var_2F8]
0x180018058  mov     eax, [rax+50h]
0x18001805b  mov     [rsp+3B8h+var_29C], eax
0x180018062  lea     rdx, [rsp+3B8h+var_29C]
0x18001806a  lea     rcx, [rsp+3B8h+var_298]
0x180018072  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x180018077  nop
0x180018078  lea     rax, [rsp+3B8h+var_298]
0x180018080  mov     [rsp+3B8h+var_120], rax
0x180018088  mov     rax, [rsp+3B8h+var_2F8]
0x180018090  mov     rdx, [rax+48h]
0x180018094  lea     rcx, [rsp+3B8h+var_28]
0x18001809c  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x1800180a1  mov     [rsp+3B8h+var_118], rax
0x1800180a9  mov     rax, [rsp+3B8h+var_2F8]
0x1800180b1  mov     eax, [rax+20h]
0x1800180b4  mov     [rsp+3B8h+var_294], eax
0x1800180bb  lea     rdx, [rsp+3B8h+var_294]
0x1800180c3  lea     rcx, [rsp+3B8h+var_290]
0x1800180cb  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800180d0  nop
0x1800180d1  lea     rax, [rsp+3B8h+var_290]
0x1800180d9  mov     [rsp+3B8h+var_110], rax
0x1800180e1  mov     rax, [rsp+3B8h+var_2F8]
0x1800180e9  mov     rdx, [rax+18h]
0x1800180ed  lea     rcx, [rsp+3B8h+var_20]
0x1800180f5  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x1800180fa  mov     [rsp+3B8h+var_108], rax
0x180018102  mov     rax, [rsp+3B8h+var_2F8]
0x18001810a  mov     eax, [rax]
0x18001810c  mov     [rsp+3B8h+var_28C], eax
0x180018113  lea     rdx, [rsp+3B8h+var_28C]
0x18001811b  lea     rcx, [rsp+3B8h+var_288]
0x180018123  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
  ... truncated ...
```
