# TraceProvider::FindFirstFileExBrokerActivity::StopActivity(void)

- ea: `0x180019d10`
- end: `0x180019f3c`
- name: `?StopActivity@FindFirstFileExBrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::FindFirstFileExBrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x180019d10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019edd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019edd`

## pseudocode

```c
void __fastcall TraceProvider::FindFirstFileExBrokerActivity::StopActivity(
        TraceProvider::FindFirstFileExBrokerActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  const unsigned __int16 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const unsigned __int16 *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v24; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v29; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = TraceProvider::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v7,
        (__int64)&unk_18002B328,
        v9 + 8,
        (__int64)v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v32,
        &v22,
        &v21,
        (__int64)&v31,
        &v20,
        &v19,
        (__int64)&v30,
        (__int64)&v29,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = TraceProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&unk_18002B480,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this, v5, v6, v7);
}

```

## disassembly

```asm
0x180019d10  push    rbp
0x180019d12  push    rbx
0x180019d13  push    rdi
0x180019d14  lea     rbp, [rsp+10h]
0x180019d19  sub     rsp, 130h
0x180019d20  mov     rdi, [rcx+110h]
0x180019d27  mov     rbx, rcx
0x180019d2a  mov     eax, [rdi+48h]
0x180019d2d  test    eax, eax
0x180019d2f  jns     loc_180019EC9
0x180019d35  add     rdi, 50h ; 'P'
0x180019d39  cmp     eax, [rdi+8]
0x180019d3c  jnz     loc_180019EC9
0x180019d42  test    rdi, rdi
0x180019d45  jz      loc_180019EC9
0x180019d4b  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019d50  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019d55  mov     r9, rax
0x180019d58  mov     ecx, [rax]
0x180019d5a  cmp     ecx, 5
0x180019d5d  jbe     loc_180019F2A
0x180019d63  mov     rax, [rdi+70h]
0x180019d67  lea     rdx, unk_18002B328
0x180019d6e  mov     rcx, [rdi+30h]
0x180019d72  mov     [rbp+var_60], rax
0x180019d76  mov     eax, [rdi+68h]
0x180019d79  mov     r8, [rbx+110h]
0x180019d80  mov     dword ptr [rbp+arg_10], eax
0x180019d83  add     r8, 8
0x180019d87  mov     rax, [rdi+60h]
0x180019d8b  mov     [rbp+var_58], rax
0x180019d8f  mov     rax, [rdi+58h]
0x180019d93  mov     [rbp+var_50], rax
0x180019d97  mov     eax, [rdi+50h]
0x180019d9a  mov     [rbp+arg_18], eax
0x180019d9d  mov     rax, [rdi+48h]
0x180019da1  mov     [rbp+var_48], rax
0x180019da5  mov     eax, [rdi+20h]
0x180019da8  mov     [rbp+var_80], eax
0x180019dab  mov     rax, [rdi+18h]
0x180019daf  mov     [rbp+var_40], rax
0x180019db3  mov     eax, [rdi]
0x180019db5  mov     [rbp+var_7C], eax
0x180019db8  mov     rax, [rdi+80h]
0x180019dbf  mov     [rbp+var_38], rax
0x180019dc3  mov     eax, [rdi+40h]
0x180019dc6  mov     [rbp+var_78], eax
0x180019dc9  mov     rax, [rdi+38h]
0x180019dcd  mov     [rbp+var_30], rax
0x180019dd1  mov     eax, [rdi+8]
0x180019dd4  mov     [rbp+var_74], eax
0x180019dd7  lea     rax, [rbp+var_70]
0x180019ddb  mov     [rsp+140h+var_90], rax
0x180019de3  lea     rax, [rbp+arg_0]
0x180019de7  mov     [rsp+140h+var_98], rax
0x180019def  lea     rax, [rbp+arg_8]
0x180019df3  mov     [rsp+140h+var_A0], rax
0x180019dfb  lea     rax, [rbp+var_68]
0x180019dff  mov     [rsp+140h+var_A8], rax
0x180019e07  lea     rax, [rbp+var_60]
0x180019e0b  mov     [rsp+140h+var_B0], rax
0x180019e13  lea     rax, [rbp+arg_10]
0x180019e17  mov     [rsp+140h+var_B8], rax
0x180019e1f  lea     rax, [rbp+var_58]
0x180019e23  mov     [rsp+140h+var_C0], rax
0x180019e2b  lea     rax, [rbp+var_50]
0x180019e2f  mov     [rsp+140h+var_C8], rax
0x180019e34  lea     rax, [rbp+arg_18]
0x180019e38  mov     [rsp+140h+var_D0], rax
0x180019e3d  lea     rax, [rbp+var_48]
0x180019e41  mov     [rsp+140h+var_D8], rax
0x180019e46  lea     rax, [rbp+var_80]
0x180019e4a  mov     [rsp+140h+var_E0], rax
0x180019e4f  lea     rax, [rbp+var_40]
0x180019e53  mov     [rsp+140h+var_E8], rax
0x180019e58  lea     rax, [rbp+var_7C]
0x180019e5c  mov     [rsp+140h+var_F0], rax
0x180019e61  lea     rax, [rbp+var_38]
0x180019e65  mov     [rsp+140h+var_F8], rax
0x180019e6a  lea     rax, [rbp+var_78]
0x180019e6e  mov     [rsp+140h+var_100], rax
0x180019e73  lea     rax, [rbp+var_30]
0x180019e77  mov     [rsp+140h+var_108], rax
0x180019e7c  lea     rax, [rbp+var_74]
0x180019e80  mov     [rbp+var_70], rcx
0x180019e84  mov     ecx, [rdi+44h]
0x180019e87  mov     [rsp+140h+var_110], rax
0x180019e8c  lea     rax, [rbp+var_28]
0x180019e90  mov     [rbp+arg_0], ecx
0x180019e93  mov     ecx, [rdi+10h]
0x180019e96  mov     [rbp+arg_8], ecx
0x180019e99  mov     rcx, [rdi+78h]
0x180019e9d  mov     [rsp+140h+var_118], rax
0x180019ea2  lea     rax, [rbp+var_20]
0x180019ea6  mov     [rbp+var_68], rcx
0x180019eaa  mov     rcx, r9
0x180019ead  mov     [rsp+140h+var_120], rax
0x180019eb2  mov     [rbp+var_28], 1000000h
0x180019eba  mov     [rbp+var_20], 0
0x180019ec2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180019ec7  jmp     short loc_180019F2A
0x180019ec9  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019ece  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019ed3  mov     rdi, rax
0x180019ed6  mov     ecx, [rax]
0x180019ed8  cmp     ecx, 5
0x180019edb  jbe     short loc_180019F2A
0x180019edd  call    cs:__imp_GetCurrentThreadId
0x180019ee3  mov     r8, [rbx+110h]
0x180019eea  lea     rdx, unk_18002B480
0x180019ef1  mov     [rbp+arg_0], eax
0x180019ef4  lea     rax, [rbp+arg_0]
0x180019ef8  mov     [rsp+140h+var_110], rax
0x180019efd  lea     rax, [rbp+arg_8]
0x180019f01  mov     [rsp+140h+var_118], rax
0x180019f06  lea     rax, [rbp+arg_10]
0x180019f0a  mov     ecx, [r8+48h]
0x180019f0e  add     r8, 8
0x180019f12  mov     [rbp+arg_8], ecx
0x180019f15  mov     rcx, rdi
0x180019f18  mov     [rsp+140h+var_120], rax
0x180019f1d  mov     [rbp+arg_10], 0
0x180019f25  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019f2a  mov     rcx, rbx
0x180019f2d  add     rsp, 130h
0x180019f34  pop     rdi
0x180019f35  pop     rbx
0x180019f36  pop     rbp
0x180019f37  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
