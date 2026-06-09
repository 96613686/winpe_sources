# TraceProvider::SetFileAttributesProxyActivity::StopActivity(void)

- ea: `0x180020cc0`
- end: `0x180020eec`
- name: `?StopActivity@SetFileAttributesProxyActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::SetFileAttributesProxyActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x180020cc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020e8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020e8d`

## pseudocode

```c
void __fastcall TraceProvider::SetFileAttributesProxyActivity::StopActivity(
        TraceProvider::SetFileAttributesProxyActivity *this)
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
        (__int64)byte_18002C0D1,
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
        (__int64)word_18002C22A,
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
0x180020cc0  push    rbp
0x180020cc2  push    rbx
0x180020cc3  push    rdi
0x180020cc4  lea     rbp, [rsp+10h]
0x180020cc9  sub     rsp, 130h
0x180020cd0  mov     rdi, [rcx+110h]
0x180020cd7  mov     rbx, rcx
0x180020cda  mov     eax, [rdi+48h]
0x180020cdd  test    eax, eax
0x180020cdf  jns     loc_180020E79
0x180020ce5  add     rdi, 50h ; 'P'
0x180020ce9  cmp     eax, [rdi+8]
0x180020cec  jnz     loc_180020E79
0x180020cf2  test    rdi, rdi
0x180020cf5  jz      loc_180020E79
0x180020cfb  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020d00  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180020d05  mov     r9, rax
0x180020d08  mov     ecx, [rax]
0x180020d0a  cmp     ecx, 5
0x180020d0d  jbe     loc_180020EDA
0x180020d13  mov     rax, [rdi+70h]
0x180020d17  lea     rdx, byte_18002C0D1
0x180020d1e  mov     rcx, [rdi+30h]
0x180020d22  mov     [rbp+var_60], rax
0x180020d26  mov     eax, [rdi+68h]
0x180020d29  mov     r8, [rbx+110h]
0x180020d30  mov     dword ptr [rbp+arg_10], eax
0x180020d33  add     r8, 8
0x180020d37  mov     rax, [rdi+60h]
0x180020d3b  mov     [rbp+var_58], rax
0x180020d3f  mov     rax, [rdi+58h]
0x180020d43  mov     [rbp+var_50], rax
0x180020d47  mov     eax, [rdi+50h]
0x180020d4a  mov     [rbp+arg_18], eax
0x180020d4d  mov     rax, [rdi+48h]
0x180020d51  mov     [rbp+var_48], rax
0x180020d55  mov     eax, [rdi+20h]
0x180020d58  mov     [rbp+var_80], eax
0x180020d5b  mov     rax, [rdi+18h]
0x180020d5f  mov     [rbp+var_40], rax
0x180020d63  mov     eax, [rdi]
0x180020d65  mov     [rbp+var_7C], eax
0x180020d68  mov     rax, [rdi+80h]
0x180020d6f  mov     [rbp+var_38], rax
0x180020d73  mov     eax, [rdi+40h]
0x180020d76  mov     [rbp+var_78], eax
0x180020d79  mov     rax, [rdi+38h]
0x180020d7d  mov     [rbp+var_30], rax
0x180020d81  mov     eax, [rdi+8]
0x180020d84  mov     [rbp+var_74], eax
0x180020d87  lea     rax, [rbp+var_70]
0x180020d8b  mov     [rsp+140h+var_90], rax
0x180020d93  lea     rax, [rbp+arg_0]
0x180020d97  mov     [rsp+140h+var_98], rax
0x180020d9f  lea     rax, [rbp+arg_8]
0x180020da3  mov     [rsp+140h+var_A0], rax
0x180020dab  lea     rax, [rbp+var_68]
0x180020daf  mov     [rsp+140h+var_A8], rax
0x180020db7  lea     rax, [rbp+var_60]
0x180020dbb  mov     [rsp+140h+var_B0], rax
0x180020dc3  lea     rax, [rbp+arg_10]
0x180020dc7  mov     [rsp+140h+var_B8], rax
0x180020dcf  lea     rax, [rbp+var_58]
0x180020dd3  mov     [rsp+140h+var_C0], rax
0x180020ddb  lea     rax, [rbp+var_50]
0x180020ddf  mov     [rsp+140h+var_C8], rax
0x180020de4  lea     rax, [rbp+arg_18]
0x180020de8  mov     [rsp+140h+var_D0], rax
0x180020ded  lea     rax, [rbp+var_48]
0x180020df1  mov     [rsp+140h+var_D8], rax
0x180020df6  lea     rax, [rbp+var_80]
0x180020dfa  mov     [rsp+140h+var_E0], rax
0x180020dff  lea     rax, [rbp+var_40]
0x180020e03  mov     [rsp+140h+var_E8], rax
0x180020e08  lea     rax, [rbp+var_7C]
0x180020e0c  mov     [rsp+140h+var_F0], rax
0x180020e11  lea     rax, [rbp+var_38]
0x180020e15  mov     [rsp+140h+var_F8], rax
0x180020e1a  lea     rax, [rbp+var_78]
0x180020e1e  mov     [rsp+140h+var_100], rax
0x180020e23  lea     rax, [rbp+var_30]
0x180020e27  mov     [rsp+140h+var_108], rax
0x180020e2c  lea     rax, [rbp+var_74]
0x180020e30  mov     [rbp+var_70], rcx
0x180020e34  mov     ecx, [rdi+44h]
0x180020e37  mov     [rsp+140h+var_110], rax
0x180020e3c  lea     rax, [rbp+var_28]
0x180020e40  mov     [rbp+arg_0], ecx
0x180020e43  mov     ecx, [rdi+10h]
0x180020e46  mov     [rbp+arg_8], ecx
0x180020e49  mov     rcx, [rdi+78h]
0x180020e4d  mov     [rsp+140h+var_118], rax
0x180020e52  lea     rax, [rbp+var_20]
0x180020e56  mov     [rbp+var_68], rcx
0x180020e5a  mov     rcx, r9
0x180020e5d  mov     [rsp+140h+var_120], rax
0x180020e62  mov     [rbp+var_28], 1000000h
0x180020e6a  mov     [rbp+var_20], 0
0x180020e72  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180020e77  jmp     short loc_180020EDA
0x180020e79  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020e7e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180020e83  mov     rdi, rax
0x180020e86  mov     ecx, [rax]
0x180020e88  cmp     ecx, 5
0x180020e8b  jbe     short loc_180020EDA
0x180020e8d  call    cs:__imp_GetCurrentThreadId
0x180020e93  mov     r8, [rbx+110h]
0x180020e9a  lea     rdx, word_18002C22A
0x180020ea1  mov     [rbp+arg_0], eax
0x180020ea4  lea     rax, [rbp+arg_0]
0x180020ea8  mov     [rsp+140h+var_110], rax
0x180020ead  lea     rax, [rbp+arg_8]
0x180020eb1  mov     [rsp+140h+var_118], rax
0x180020eb6  lea     rax, [rbp+arg_10]
0x180020eba  mov     ecx, [r8+48h]
0x180020ebe  add     r8, 8
0x180020ec2  mov     [rbp+arg_8], ecx
0x180020ec5  mov     rcx, rdi
0x180020ec8  mov     [rsp+140h+var_120], rax
0x180020ecd  mov     [rbp+arg_10], 0
0x180020ed5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020eda  mov     rcx, rbx
0x180020edd  add     rsp, 130h
0x180020ee4  pop     rdi
0x180020ee5  pop     rbx
0x180020ee6  pop     rbp
0x180020ee7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
