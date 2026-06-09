# CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::StopActivity(void)

- ea: `0x18001ad30`
- end: `0x18001af54`
- name: `?StopActivity@UpdateCultureSettingsActivity@CoreGlobConfigTraceLogging@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x180001010`
- `0x18000133c`
- `0x180001acc`
- `0x180015bf0`
- `0x180016fcc`
- `0x18001ad30`
- `0x18001f06c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001aef5`

## pseudocode

```c
void __fastcall CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity::StopActivity(
        CoreGlobConfigTraceLogging::UpdateCultureSettingsActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CoreGlobConfigTraceLogging::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
    {
      v8 = (__int64 *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (__int64 *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (__int64 *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      v27[0] = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v7,
        (__int64)byte_18002A5B3,
        v9 + 8,
        v7,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = CoreGlobConfigTraceLogging::Provider();
    v12 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 16779264;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&unk_18002A6E8,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18001ad30  push    rbp
0x18001ad32  push    rbx
0x18001ad33  push    rdi
0x18001ad34  lea     rbp, [rsp-47h]
0x18001ad39  sub     rsp, 100h
0x18001ad40  mov     rdi, [rcx+110h]
0x18001ad47  mov     rbx, rcx
0x18001ad4a  mov     eax, [rdi+48h]
0x18001ad4d  test    eax, eax
0x18001ad4f  jns     loc_18001AECB
0x18001ad55  add     rdi, 50h ; 'P'
0x18001ad59  cmp     eax, [rdi+8]
0x18001ad5c  jnz     loc_18001AECB
0x18001ad62  test    rdi, rdi
0x18001ad65  jz      loc_18001AECB
0x18001ad6b  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001ad70  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001ad75  mov     r9, rax
0x18001ad78  mov     ecx, [rax]
0x18001ad7a  cmp     ecx, 5
0x18001ad7d  jbe     loc_18001AF42
0x18001ad83  mov     rdx, 200000000000h
0x18001ad8d  mov     rcx, rax
0x18001ad90  call    _tlgKeywordOn
0x18001ad95  test    al, al
0x18001ad97  jz      loc_18001AF42
0x18001ad9d  mov     rax, [rdi+70h]
0x18001ada1  lea     rdx, byte_18002A5B3
0x18001ada8  mov     rcx, [rdi+78h]
0x18001adac  mov     r8, [rbx+110h]
0x18001adb3  mov     [rbp+57h+var_60], rax
0x18001adb7  add     r8, 8
0x18001adbb  mov     eax, [rdi+68h]
0x18001adbe  mov     [rbp+57h+arg_0], eax
0x18001adc1  mov     rax, [rdi+60h]
0x18001adc5  mov     [rbp+57h+var_58], rax
0x18001adc9  mov     rax, [rdi+58h]
0x18001adcd  mov     [rbp+57h+var_50], rax
0x18001add1  mov     eax, [rdi+50h]
0x18001add4  mov     [rbp+57h+arg_8], eax
0x18001add7  mov     rax, [rdi+48h]
0x18001addb  mov     [rbp+57h+var_48], rax
0x18001addf  mov     eax, [rdi+20h]
0x18001ade2  mov     dword ptr [rbp+57h+arg_10], eax
0x18001ade5  mov     rax, [rdi+18h]
0x18001ade9  mov     [rbp+57h+var_40], rax
0x18001aded  mov     eax, [rdi]
0x18001adef  mov     [rbp+57h+arg_18], eax
0x18001adf2  mov     rax, [rdi+80h]
0x18001adf9  mov     [rbp+57h+var_38], rax
0x18001adfd  mov     eax, [rdi+40h]
0x18001ae00  mov     [rbp+57h+var_70], eax
0x18001ae03  mov     rax, [rdi+38h]
0x18001ae07  mov     [rbp+57h+var_30], rax
0x18001ae0b  mov     eax, [rdi+8]
0x18001ae0e  mov     [rbp+57h+var_6C], eax
0x18001ae11  lea     rax, [rbp+57h+var_68]
0x18001ae15  mov     [rsp+110h+var_78], rax
0x18001ae1d  lea     rax, [rbp+57h+var_60]
0x18001ae21  mov     [rsp+110h+var_80], rax
0x18001ae29  lea     rax, [rbp+57h+arg_0]
0x18001ae2d  mov     [rsp+110h+var_88], rax
0x18001ae35  lea     rax, [rbp+57h+var_58]
0x18001ae39  mov     [rsp+110h+var_90], rax
0x18001ae41  lea     rax, [rbp+57h+var_50]
0x18001ae45  mov     [rsp+110h+var_98], rax
0x18001ae4a  lea     rax, [rbp+57h+arg_8]
0x18001ae4e  mov     [rsp+110h+var_A0], rax
0x18001ae53  lea     rax, [rbp+57h+var_48]
0x18001ae57  mov     [rsp+110h+var_A8], rax
0x18001ae5c  lea     rax, [rbp+57h+arg_10]
0x18001ae60  mov     [rsp+110h+var_B0], rax
0x18001ae65  lea     rax, [rbp+57h+var_40]
0x18001ae69  mov     [rsp+110h+var_B8], rax
0x18001ae6e  lea     rax, [rbp+57h+arg_18]
0x18001ae72  mov     [rsp+110h+var_C0], rax
0x18001ae77  lea     rax, [rbp+57h+var_38]
0x18001ae7b  mov     [rsp+110h+var_C8], rax
0x18001ae80  lea     rax, [rbp+57h+var_70]
0x18001ae84  mov     [rsp+110h+var_D0], rax
0x18001ae89  lea     rax, [rbp+57h+var_30]
0x18001ae8d  mov     [rsp+110h+var_D8], rax
0x18001ae92  lea     rax, [rbp+57h+var_6C]
0x18001ae96  mov     [rsp+110h+var_E0], rax
0x18001ae9b  lea     rax, [rbp+57h+var_28]
0x18001ae9f  mov     [rsp+110h+var_E8], rax
0x18001aea4  lea     rax, [rbp+57h+var_20]
0x18001aea8  mov     [rbp+57h+var_68], rcx
0x18001aeac  mov     rcx, r9
0x18001aeaf  mov     [rsp+110h+var_F0], rax
0x18001aeb4  mov     [rbp+57h+var_28], 1000000h
0x18001aebc  mov     [rbp+57h+var_20], 1000800h
0x18001aec4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001aec9  jmp     short loc_18001AF42
0x18001aecb  call    ?zInternalStop@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001aed0  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001aed5  mov     rdi, rax
0x18001aed8  mov     ecx, [rax]
0x18001aeda  cmp     ecx, 5
0x18001aedd  jbe     short loc_18001AF42
0x18001aedf  mov     rdx, 200000000000h
0x18001aee9  mov     rcx, rax
0x18001aeec  call    _tlgKeywordOn
0x18001aef1  test    al, al
0x18001aef3  jz      short loc_18001AF42
0x18001aef5  call    cs:__imp_GetCurrentThreadId
0x18001aefb  mov     r8, [rbx+110h]
0x18001af02  lea     rdx, unk_18002A6E8
0x18001af09  mov     [rbp+57h+arg_0], eax
0x18001af0c  mov     rcx, rdi
0x18001af0f  mov     eax, [r8+48h]
0x18001af13  add     r8, 8
0x18001af17  mov     [rbp+57h+arg_8], eax
0x18001af1a  lea     rax, [rbp+57h+arg_0]
0x18001af1e  mov     [rsp+110h+var_E0], rax
0x18001af23  lea     rax, [rbp+57h+arg_8]
0x18001af27  mov     [rsp+110h+var_E8], rax
0x18001af2c  lea     rax, [rbp+57h+arg_10]
0x18001af30  mov     [rsp+110h+var_F0], rax
0x18001af35  mov     [rbp+57h+arg_10], 1000800h
0x18001af3d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001af42  mov     rcx, rbx
0x18001af45  add     rsp, 100h
0x18001af4c  pop     rdi
0x18001af4d  pop     rbx
0x18001af4e  pop     rbp
0x18001af4f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
