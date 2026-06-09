# PolicyTelemetry::DiskPolicyEvaluation::Stop(uint,unsigned __int64,unsigned __int64,unsigned __int64,double,double)

- ea: `0x180021c80`
- end: `0x180021f8c`
- name: `?Stop@DiskPolicyEvaluation@PolicyTelemetry@@QEAAXI_K00NN@Z`
- size: `780`
- prototype: `void __fastcall(PolicyTelemetry::DiskPolicyEvaluation *__hidden this, unsigned int, unsigned __int64, unsigned __int64, unsigned __int64, double, double)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800218d0`

## callees

- `0x180001b0c`
- `0x180002a60`
- `0x180002dac`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x180021c80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021ef1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021ef1`

## pseudocode

```c
void __fastcall PolicyTelemetry::DiskPolicyEvaluation::Stop(
        PolicyTelemetry::DiskPolicyEvaluation *this,
        int a2,
        const WCHAR *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        double a6,
        double a7)
{
  __int64 v7; // rdi
  int v12; // eax
  int *v13; // rdi
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // [rsp+D0h] [rbp-80h] BYREF
  DWORD v25; // [rsp+D4h] [rbp-7Ch] BYREF
  int v26; // [rsp+D8h] [rbp-78h] BYREF
  int v27; // [rsp+DCh] [rbp-74h] BYREF
  int v28; // [rsp+E0h] [rbp-70h] BYREF
  int v29; // [rsp+E4h] [rbp-6Ch] BYREF
  __int64 v30; // [rsp+E8h] [rbp-68h] BYREF
  const WCHAR *v31; // [rsp+F0h] [rbp-60h] BYREF
  const unsigned __int16 *v32; // [rsp+F8h] [rbp-58h] BYREF
  const unsigned __int16 *v33; // [rsp+100h] [rbp-50h] BYREF
  __int64 v34; // [rsp+108h] [rbp-48h] BYREF
  __int64 v35; // [rsp+110h] [rbp-40h] BYREF
  double v36; // [rsp+118h] [rbp-38h] BYREF
  double v37; // [rsp+120h] [rbp-30h] BYREF
  const unsigned __int16 *v38; // [rsp+128h] [rbp-28h] BYREF
  const unsigned __int16 *v39; // [rsp+130h] [rbp-20h] BYREF
  const WCHAR *v40; // [rsp+138h] [rbp-18h] BYREF
  const WCHAR *v41; // [rsp+140h] [rbp-10h] BYREF
  const unsigned __int16 *v42; // [rsp+148h] [rbp-8h] BYREF
  const WCHAR *v43; // [rsp+150h] [rbp+0h] BYREF
  const unsigned __int16 *v44; // [rsp+158h] [rbp+8h] BYREF
  int v45; // [rsp+1A0h] [rbp+50h] BYREF

  v7 = *((_QWORD *)this + 34);
  v12 = *(_DWORD *)(v7 + 72);
  if ( v12 < 0 && (v13 = (int *)(v7 + 80), v12 == v13[2]) && v13 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = SharedPCAccountManagerLogging::Provider();
    v17 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x400000000000LL, v16, v14) )
    {
      v37 = a6;
      v38 = a5;
      v41 = (const WCHAR *)*((_QWORD *)v13 + 15);
      v42 = (const unsigned __int16 *)*((_QWORD *)v13 + 14);
      v26 = v13[26];
      v43 = (const WCHAR *)*((_QWORD *)v13 + 12);
      v18 = *((_QWORD *)this + 34);
      v44 = (const unsigned __int16 *)*((_QWORD *)v13 + 11);
      v27 = v13[20];
      v30 = *((_QWORD *)v13 + 9);
      v28 = v13[8];
      v31 = (const WCHAR *)*((_QWORD *)v13 + 3);
      v29 = *v13;
      v32 = (const unsigned __int16 *)*((_QWORD *)v13 + 16);
      v24 = v13[16];
      v33 = (const unsigned __int16 *)*((_QWORD *)v13 + 7);
      v25 = v13[2];
      v34 = 0x1000000;
      v35 = 0x1000000;
      v36 = a7;
      v39 = a4;
      v40 = a3;
      v45 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v17,
        (__int64)&word_18002F626,
        v18 + 8,
        v17,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v25,
        &v33,
        (__int64)&v24,
        &v32,
        (__int64)&v29,
        &v31,
        (__int64)&v28,
        (const unsigned __int16 **)&v30,
        (__int64)&v27,
        &v44,
        &v43,
        (__int64)&v26,
        &v42,
        &v41,
        (__int64)&v45,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v36);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v19 = SharedPCAccountManagerLogging::Provider();
    v20 = (__int64)v19;
    if ( *(_DWORD *)v19 > 5u && (unsigned __int8)tlgKeywordOn(v19, 0x400000000000LL, v16, v17) )
    {
      v34 = *(_QWORD *)&a6;
      v33 = a5;
      v35 = *(_QWORD *)&a7;
      v32 = a4;
      v31 = a3;
      v45 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v22 = *((_QWORD *)this + 34);
      v25 = CurrentThreadId;
      v24 = *(_DWORD *)(v22 + 72);
      v30 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v20,
        (__int64)byte_18002F7CD,
        v22 + 8,
        v23,
        (__int64)&v30,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v45,
        (__int64)&v31,
        (__int64)&v32,
        (__int64)&v33,
        (__int64)&v34,
        (__int64)&v35);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v15,
    v16,
    v17);
}

```

## disassembly

```asm
0x180021c80  push    rbp
0x180021c82  push    rbx
0x180021c83  push    rsi
0x180021c84  push    rdi
0x180021c85  push    r14
0x180021c87  push    r15
0x180021c89  lea     rbp, [rsp-18h]
0x180021c8e  sub     rsp, 168h
0x180021c95  mov     rdi, [rcx+110h]
0x180021c9c  mov     rsi, r9
0x180021c9f  mov     r14, r8
0x180021ca2  mov     r15d, edx
0x180021ca5  mov     rbx, rcx
0x180021ca8  mov     eax, [rdi+48h]
0x180021cab  test    eax, eax
0x180021cad  jns     loc_180021E98
0x180021cb3  add     rdi, 50h ; 'P'
0x180021cb7  cmp     eax, [rdi+8]
0x180021cba  jnz     loc_180021E98
0x180021cc0  test    rdi, rdi
0x180021cc3  jz      loc_180021E98
0x180021cc9  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180021cce  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180021cd3  mov     r9, rax
0x180021cd6  mov     ecx, [rax]
0x180021cd8  cmp     ecx, 5
0x180021cdb  jbe     loc_180021F75
0x180021ce1  mov     rdx, 400000000000h
0x180021ceb  mov     rcx, rax
0x180021cee  call    _tlgKeywordOn
0x180021cf3  test    al, al
0x180021cf5  jz      loc_180021F75
0x180021cfb  mov     rax, [rbp+40h+arg_28]
0x180021cff  mov     [rbp+40h+var_70], rax
0x180021d03  mov     rax, [rbp+40h+arg_20]
0x180021d07  mov     [rbp+40h+var_68], rax
0x180021d0b  mov     rax, [rdi+78h]
0x180021d0f  mov     [rbp+40h+var_50], rax
0x180021d13  mov     rax, [rdi+70h]
0x180021d17  mov     [rbp+40h+var_48], rax
0x180021d1b  mov     eax, [rdi+68h]
0x180021d1e  mov     [rbp+40h+var_B8], eax
0x180021d21  mov     rax, [rdi+60h]
0x180021d25  mov     [rbp+40h+var_40], rax
0x180021d29  mov     rax, [rdi+58h]
0x180021d2d  mov     rcx, [rbp+40h+arg_30]
0x180021d34  mov     r8, [rbx+110h]
0x180021d3b  mov     [rbp+40h+var_38], rax
0x180021d3f  add     r8, 8
0x180021d43  mov     eax, [rdi+50h]
0x180021d46  mov     [rbp+40h+var_B4], eax
0x180021d49  mov     rax, [rdi+48h]
0x180021d4d  mov     [rbp+40h+var_A8], rax
0x180021d51  mov     eax, [rdi+20h]
0x180021d54  mov     [rbp+40h+var_B0], eax
0x180021d57  mov     rax, [rdi+18h]
0x180021d5b  mov     [rbp+40h+var_A0], rax
0x180021d5f  mov     eax, [rdi]
0x180021d61  mov     [rbp+40h+var_AC], eax
0x180021d64  mov     rax, [rdi+80h]
0x180021d6b  mov     [rbp+40h+var_98], rax
0x180021d6f  mov     eax, [rdi+40h]
0x180021d72  mov     [rbp+40h+var_C0], eax
0x180021d75  mov     rax, [rdi+38h]
0x180021d79  mov     [rbp+40h+var_90], rax
0x180021d7d  mov     eax, [rdi+8]
0x180021d80  mov     [rbp+40h+var_BC], eax
0x180021d83  mov     eax, 1000000h
0x180021d88  mov     [rbp+40h+var_88], rax
0x180021d8c  mov     [rbp+40h+var_80], rax
0x180021d90  lea     rax, [rbp+40h+var_78]
0x180021d94  mov     [rsp+190h+var_C8], rax
0x180021d9c  lea     rax, [rbp+40h+var_70]
0x180021da0  mov     [rsp+190h+var_D0], rax
0x180021da8  lea     rax, [rbp+40h+var_68]
0x180021dac  mov     [rsp+190h+var_D8], rax
0x180021db4  lea     rax, [rbp+40h+var_60]
0x180021db8  mov     [rsp+190h+var_E0], rax
0x180021dc0  lea     rax, [rbp+40h+var_58]
0x180021dc4  mov     [rsp+190h+var_E8], rax
0x180021dcc  lea     rax, [rbp+40h+arg_0]
0x180021dd0  mov     [rsp+190h+var_F0], rax
0x180021dd8  lea     rax, [rbp+40h+var_50]
0x180021ddc  mov     [rsp+190h+var_F8], rax
0x180021de4  lea     rax, [rbp+40h+var_48]
0x180021de8  mov     [rsp+190h+var_100], rax
0x180021df0  lea     rax, [rbp+40h+var_B8]
0x180021df4  mov     [rsp+190h+var_108], rax
0x180021dfc  lea     rax, [rbp+40h+var_40]
0x180021e00  mov     [rsp+190h+var_110], rax
0x180021e08  lea     rax, [rbp+40h+var_38]
0x180021e0c  mov     [rsp+190h+var_118], rax
0x180021e11  lea     rax, [rbp+40h+var_B4]
0x180021e15  mov     [rsp+190h+var_120], rax
0x180021e1a  lea     rax, [rbp+40h+var_A8]
0x180021e1e  mov     [rsp+190h+var_128], rax
0x180021e23  lea     rax, [rbp+40h+var_B0]
0x180021e27  mov     [rsp+190h+var_130], rax
0x180021e2c  lea     rax, [rbp+40h+var_A0]
0x180021e30  mov     [rsp+190h+var_138], rax
0x180021e35  lea     rax, [rbp+40h+var_AC]
0x180021e39  mov     [rsp+190h+var_140], rax
0x180021e3e  lea     rax, [rbp+40h+var_98]
0x180021e42  mov     [rsp+190h+var_148], rax
0x180021e47  lea     rax, [rbp+40h+var_C0]
0x180021e4b  mov     [rsp+190h+var_150], rax
0x180021e50  lea     rax, [rbp+40h+var_90]
0x180021e54  mov     [rsp+190h+var_158], rax
0x180021e59  lea     rax, [rbp+40h+var_BC]
0x180021e5d  mov     [rbp+40h+var_78], rcx
0x180021e61  mov     [rbp+40h+var_60], rsi
0x180021e65  mov     [rbp+40h+var_58], r14
0x180021e69  mov     [rbp+40h+arg_0], r15d
0x180021e6d  mov     [rsp+190h+var_160], rax
0x180021e72  lea     rdx, word_18002F626
0x180021e79  lea     rax, [rbp+40h+var_88]
0x180021e7d  mov     rcx, r9
0x180021e80  mov     [rsp+190h+var_168], rax
0x180021e85  lea     rax, [rbp+40h+var_80]
0x180021e89  mov     [rsp+190h+var_170], rax
0x180021e8e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456433333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180021e93  jmp     loc_180021F75
0x180021e98  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180021e9d  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180021ea2  mov     rdi, rax
0x180021ea5  mov     ecx, [rax]
0x180021ea7  cmp     ecx, 5
0x180021eaa  jbe     loc_180021F75
0x180021eb0  mov     rdx, 400000000000h
0x180021eba  mov     rcx, rax
0x180021ebd  call    _tlgKeywordOn
0x180021ec2  test    al, al
0x180021ec4  jz      loc_180021F75
0x180021eca  mov     rax, [rbp+40h+arg_28]
0x180021ece  mov     rcx, [rbp+40h+arg_30]
0x180021ed5  mov     [rbp+40h+var_88], rax
0x180021ed9  mov     rax, [rbp+40h+arg_20]
0x180021edd  mov     [rbp+40h+var_90], rax
0x180021ee1  mov     [rbp+40h+var_80], rcx
0x180021ee5  mov     [rbp+40h+var_98], rsi
0x180021ee9  mov     [rbp+40h+var_A0], r14
0x180021eed  mov     [rbp+40h+arg_0], r15d
0x180021ef1  call    cs:__imp_GetCurrentThreadId
0x180021ef7  mov     r8, [rbx+110h]
0x180021efe  lea     rdx, byte_18002F7CD
0x180021f05  mov     [rbp+40h+var_BC], eax
0x180021f08  mov     rcx, rdi
0x180021f0b  mov     eax, [r8+48h]
0x180021f0f  add     r8, 8
0x180021f13  mov     [rbp+40h+var_C0], eax
0x180021f16  mov     eax, 1000000h
0x180021f1b  mov     [rbp+40h+var_A8], rax
0x180021f1f  lea     rax, [rbp+40h+var_80]
0x180021f23  mov     [rsp+190h+var_130], rax
0x180021f28  lea     rax, [rbp+40h+var_88]
0x180021f2c  mov     [rsp+190h+var_138], rax
0x180021f31  lea     rax, [rbp+40h+var_90]
0x180021f35  mov     [rsp+190h+var_140], rax
0x180021f3a  lea     rax, [rbp+40h+var_98]
0x180021f3e  mov     [rsp+190h+var_148], rax
0x180021f43  lea     rax, [rbp+40h+var_A0]
0x180021f47  mov     [rsp+190h+var_150], rax
0x180021f4c  lea     rax, [rbp+40h+arg_0]
0x180021f50  mov     [rsp+190h+var_158], rax
0x180021f55  lea     rax, [rbp+40h+var_BC]
0x180021f59  mov     [rsp+190h+var_160], rax
0x180021f5e  lea     rax, [rbp+40h+var_C0]
0x180021f62  mov     [rsp+190h+var_168], rax
0x180021f67  lea     rax, [rbp+40h+var_A8]
0x180021f6b  mov     [rsp+190h+var_170], rax
0x180021f70  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U1@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4433333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180021f75  mov     rcx, rbx
0x180021f78  add     rsp, 168h
0x180021f7f  pop     r15
0x180021f81  pop     r14
0x180021f83  pop     rdi
0x180021f84  pop     rsi
0x180021f85  pop     rbx
0x180021f86  pop     rbp
0x180021f87  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
