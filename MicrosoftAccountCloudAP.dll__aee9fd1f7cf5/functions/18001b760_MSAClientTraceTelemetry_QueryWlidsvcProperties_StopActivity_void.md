# MSAClientTraceTelemetry::QueryWlidsvcProperties::StopActivity(void)

- ea: `0x18001b760`
- end: `0x18001b98a`
- name: `?StopActivity@QueryWlidsvcProperties@MSAClientTraceTelemetry@@MEAAXXZ`
- size: `554`
- prototype: `void __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001b18`
- `0x180001fec`
- `0x18001a878`
- `0x18001acec`
- `0x18001b760`
- `0x1800230f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b92a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b92a`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::StopActivity(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // r9
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  int v11; // ecx
  __int64 v12; // r9
  int v13; // [rsp+C0h] [rbp-80h] BYREF
  int v14; // [rsp+C4h] [rbp-7Ch] BYREF
  int v15; // [rsp+C8h] [rbp-78h] BYREF
  int v16; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v17; // [rsp+D0h] [rbp-70h] BYREF
  const unsigned __int16 *v18; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v19; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v20; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v21; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v22; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v23; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v24; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v25; // [rsp+110h] [rbp-30h] BYREF
  __int64 v26; // [rsp+118h] [rbp-28h] BYREF
  __int64 v27[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v28; // [rsp+150h] [rbp+10h] BYREF
  int v29; // [rsp+158h] [rbp+18h] BYREF
  __int64 v30; // [rsp+160h] [rbp+20h] BYREF
  int v31; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = MSAClientTraceTelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u )
    {
      v6 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v30) = v4[26];
      v7 = *((_QWORD *)this + 34);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v13 = v4[8];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v14 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v26 = 0x1000000;
      v27[0] = 0x1000000;
      v17 = v6;
      v28 = v4[17];
      v29 = v4[4];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v5,
        (__int64)&byte_1800445A7,
        v7 + 8,
        (__int64)v5,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v13,
        &v22,
        (__int64)&v31,
        &v21,
        &v20,
        (__int64)&v30,
        &v19,
        &v18,
        (__int64)&v29,
        (__int64)&v28,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v8 = MSAClientTraceTelemetry::Provider();
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v10 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v11 = *(_DWORD *)(v10 + 72);
      v30 = 0x1000000;
      v29 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v8,
        (__int64)byte_180045305,
        v10 + 8,
        v12,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001b760  push    rbp
0x18001b762  push    rbx
0x18001b763  push    rdi
0x18001b764  lea     rbp, [rsp+10h]
0x18001b769  sub     rsp, 130h
0x18001b770  mov     rdi, [rcx+110h]
0x18001b777  mov     rbx, rcx
0x18001b77a  mov     eax, [rdi+48h]
0x18001b77d  test    eax, eax
0x18001b77f  jns     loc_18001B916
0x18001b785  add     rdi, 50h ; 'P'
0x18001b789  cmp     eax, [rdi+8]
0x18001b78c  jnz     loc_18001B916
0x18001b792  test    rdi, rdi
0x18001b795  jz      loc_18001B916
0x18001b79b  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001b7a0  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18001b7a5  mov     r9, rax
0x18001b7a8  mov     ecx, [rax]
0x18001b7aa  cmp     ecx, 5
0x18001b7ad  jbe     loc_18001B978
0x18001b7b3  mov     rax, [rdi+70h]
0x18001b7b7  lea     rdx, byte_1800445A7
0x18001b7be  mov     rcx, [rdi+30h]
0x18001b7c2  mov     [rbp+var_60], rax
0x18001b7c6  mov     eax, [rdi+68h]
0x18001b7c9  mov     dword ptr [rbp+arg_10], eax
0x18001b7cc  mov     rax, [rdi+60h]
0x18001b7d0  mov     r8, [rbx+110h]
0x18001b7d7  mov     [rbp+var_58], rax
0x18001b7db  add     r8, 8
0x18001b7df  mov     rax, [rdi+58h]
0x18001b7e3  mov     [rbp+var_50], rax
0x18001b7e7  mov     eax, [rdi+50h]
0x18001b7ea  mov     [rbp+arg_18], eax
0x18001b7ed  mov     rax, [rdi+48h]
0x18001b7f1  mov     [rbp+var_48], rax
0x18001b7f5  mov     eax, [rdi+20h]
0x18001b7f8  mov     [rbp+var_80], eax
0x18001b7fb  mov     rax, [rdi+18h]
0x18001b7ff  mov     [rbp+var_40], rax
0x18001b803  mov     eax, [rdi]
0x18001b805  mov     [rbp+var_7C], eax
0x18001b808  mov     rax, [rdi+80h]
0x18001b80f  mov     [rbp+var_38], rax
0x18001b813  mov     eax, [rdi+40h]
0x18001b816  mov     [rbp+var_78], eax
0x18001b819  mov     rax, [rdi+38h]
0x18001b81d  mov     [rbp+var_30], rax
0x18001b821  mov     eax, [rdi+8]
0x18001b824  mov     [rbp+var_74], eax
0x18001b827  mov     eax, 1000000h
0x18001b82c  mov     [rbp+var_28], rax
0x18001b830  mov     [rbp+var_20], rax
0x18001b834  lea     rax, [rbp+var_70]
0x18001b838  mov     [rsp+140h+var_90], rax
0x18001b840  lea     rax, [rbp+arg_0]
0x18001b844  mov     [rsp+140h+var_98], rax
0x18001b84c  lea     rax, [rbp+arg_8]
0x18001b850  mov     [rsp+140h+var_A0], rax
0x18001b858  lea     rax, [rbp+var_68]
0x18001b85c  mov     [rsp+140h+var_A8], rax
0x18001b864  lea     rax, [rbp+var_60]
0x18001b868  mov     [rsp+140h+var_B0], rax
0x18001b870  lea     rax, [rbp+arg_10]
0x18001b874  mov     [rsp+140h+var_B8], rax
0x18001b87c  lea     rax, [rbp+var_58]
0x18001b880  mov     [rsp+140h+var_C0], rax
0x18001b888  lea     rax, [rbp+var_50]
0x18001b88c  mov     [rsp+140h+var_C8], rax
0x18001b891  lea     rax, [rbp+arg_18]
0x18001b895  mov     [rsp+140h+var_D0], rax
0x18001b89a  lea     rax, [rbp+var_48]
0x18001b89e  mov     [rsp+140h+var_D8], rax
0x18001b8a3  lea     rax, [rbp+var_80]
0x18001b8a7  mov     [rsp+140h+var_E0], rax
0x18001b8ac  lea     rax, [rbp+var_40]
0x18001b8b0  mov     [rsp+140h+var_E8], rax
0x18001b8b5  lea     rax, [rbp+var_7C]
0x18001b8b9  mov     [rsp+140h+var_F0], rax
0x18001b8be  lea     rax, [rbp+var_38]
0x18001b8c2  mov     [rsp+140h+var_F8], rax
0x18001b8c7  lea     rax, [rbp+var_78]
0x18001b8cb  mov     [rsp+140h+var_100], rax
0x18001b8d0  lea     rax, [rbp+var_30]
0x18001b8d4  mov     [rsp+140h+var_108], rax
0x18001b8d9  lea     rax, [rbp+var_74]
0x18001b8dd  mov     [rbp+var_70], rcx
0x18001b8e1  mov     ecx, [rdi+44h]
0x18001b8e4  mov     [rsp+140h+var_110], rax
0x18001b8e9  lea     rax, [rbp+var_28]
0x18001b8ed  mov     [rbp+arg_0], ecx
0x18001b8f0  mov     ecx, [rdi+10h]
0x18001b8f3  mov     [rbp+arg_8], ecx
0x18001b8f6  mov     rcx, [rdi+78h]
0x18001b8fa  mov     [rsp+140h+var_118], rax
0x18001b8ff  lea     rax, [rbp+var_20]
0x18001b903  mov     [rbp+var_68], rcx
0x18001b907  mov     rcx, r9
0x18001b90a  mov     [rsp+140h+var_120], rax
0x18001b90f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001b914  jmp     short loc_18001B978
0x18001b916  call    ?zInternalStop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001b91b  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18001b920  mov     rdi, rax
0x18001b923  mov     ecx, [rax]
0x18001b925  cmp     ecx, 5
0x18001b928  jbe     short loc_18001B978
0x18001b92a  call    cs:__imp_GetCurrentThreadId
0x18001b930  mov     r8, [rbx+110h]
0x18001b937  lea     rdx, byte_180045305
0x18001b93e  mov     [rbp+arg_0], eax
0x18001b941  mov     eax, 1000000h
0x18001b946  mov     ecx, [r8+48h]
0x18001b94a  add     r8, 8
0x18001b94e  mov     [rbp+arg_10], rax
0x18001b952  lea     rax, [rbp+arg_0]
0x18001b956  mov     [rsp+140h+var_110], rax
0x18001b95b  lea     rax, [rbp+arg_8]
0x18001b95f  mov     [rsp+140h+var_118], rax
0x18001b964  lea     rax, [rbp+arg_10]
0x18001b968  mov     [rbp+arg_8], ecx
0x18001b96b  mov     rcx, rdi
0x18001b96e  mov     [rsp+140h+var_120], rax
0x18001b973  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001b978  mov     rcx, rbx
0x18001b97b  add     rsp, 130h
0x18001b982  pop     rdi
0x18001b983  pop     rbx
0x18001b984  pop     rbp
0x18001b985  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
