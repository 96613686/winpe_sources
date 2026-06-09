# PolicyTelemetry::UserRequestPolicyEvaluation::StopActivity(void)

- ea: `0x18001dc80`
- end: `0x18001dea5`
- name: `?StopActivity@UserRequestPolicyEvaluation@PolicyTelemetry@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(PolicyTelemetry::UserRequestPolicyEvaluation *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180001010`
- `0x180001384`
- `0x180001b0c`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x18001dc80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001de42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001de42`

## pseudocode

```c
void __fastcall PolicyTelemetry::UserRequestPolicyEvaluation::StopActivity(
        PolicyTelemetry::UserRequestPolicyEvaluation *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const WCHAR *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v27; // [rsp+120h] [rbp+67h] BYREF
  int v28; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+130h] [rbp+77h] BYREF
  int v30; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = SharedPCAccountManagerLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7, v5) )
    {
      v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v30 = *v4;
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v15 = v4[16];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v16 = v4[2];
      v25 = 0x1000000;
      v26[0] = 0x1000000;
      v17 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&byte_18002E28F,
        v10 + 8,
        v8,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v16,
        &v24,
        (__int64)&v15,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        &v19,
        (__int64)&v27,
        &v18,
        &v17);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = SharedPCAccountManagerLogging::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_18002E233,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x18001dc80  push    rbp
0x18001dc82  push    rbx
0x18001dc83  push    rdi
0x18001dc84  lea     rbp, [rsp-47h]
0x18001dc89  sub     rsp, 100h
0x18001dc90  mov     rdi, [rcx+110h]
0x18001dc97  mov     rbx, rcx
0x18001dc9a  mov     eax, [rdi+48h]
0x18001dc9d  test    eax, eax
0x18001dc9f  jns     loc_18001DE18
0x18001dca5  add     rdi, 50h ; 'P'
0x18001dca9  cmp     eax, [rdi+8]
0x18001dcac  jnz     loc_18001DE18
0x18001dcb2  test    rdi, rdi
0x18001dcb5  jz      loc_18001DE18
0x18001dcbb  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001dcc0  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001dcc5  mov     r9, rax
0x18001dcc8  mov     ecx, [rax]
0x18001dcca  cmp     ecx, 5
0x18001dccd  jbe     loc_18001DE93
0x18001dcd3  mov     rdx, 400000000000h
0x18001dcdd  mov     rcx, rax
0x18001dce0  call    _tlgKeywordOn
0x18001dce5  test    al, al
0x18001dce7  jz      loc_18001DE93
0x18001dced  mov     rax, [rdi+70h]
0x18001dcf1  lea     rdx, byte_18002E28F
0x18001dcf8  mov     rcx, [rdi+78h]
0x18001dcfc  mov     r8, [rbx+110h]
0x18001dd03  mov     [rbp+57h+var_60], rax
0x18001dd07  add     r8, 8
0x18001dd0b  mov     eax, [rdi+68h]
0x18001dd0e  mov     [rbp+57h+arg_0], eax
0x18001dd11  mov     rax, [rdi+60h]
0x18001dd15  mov     [rbp+57h+var_58], rax
0x18001dd19  mov     rax, [rdi+58h]
0x18001dd1d  mov     [rbp+57h+var_50], rax
0x18001dd21  mov     eax, [rdi+50h]
0x18001dd24  mov     [rbp+57h+arg_8], eax
0x18001dd27  mov     rax, [rdi+48h]
0x18001dd2b  mov     [rbp+57h+var_48], rax
0x18001dd2f  mov     eax, [rdi+20h]
0x18001dd32  mov     dword ptr [rbp+57h+arg_10], eax
0x18001dd35  mov     rax, [rdi+18h]
0x18001dd39  mov     [rbp+57h+var_40], rax
0x18001dd3d  mov     eax, [rdi]
0x18001dd3f  mov     [rbp+57h+arg_18], eax
0x18001dd42  mov     rax, [rdi+80h]
0x18001dd49  mov     [rbp+57h+var_38], rax
0x18001dd4d  mov     eax, [rdi+40h]
0x18001dd50  mov     [rbp+57h+var_70], eax
0x18001dd53  mov     rax, [rdi+38h]
0x18001dd57  mov     [rbp+57h+var_30], rax
0x18001dd5b  mov     eax, [rdi+8]
0x18001dd5e  mov     [rbp+57h+var_6C], eax
0x18001dd61  mov     eax, 1000000h
0x18001dd66  mov     [rbp+57h+var_28], rax
0x18001dd6a  mov     [rbp+57h+var_20], rax
0x18001dd6e  lea     rax, [rbp+57h+var_68]
0x18001dd72  mov     [rsp+110h+var_78], rax
0x18001dd7a  lea     rax, [rbp+57h+var_60]
0x18001dd7e  mov     [rsp+110h+var_80], rax
0x18001dd86  lea     rax, [rbp+57h+arg_0]
0x18001dd8a  mov     [rsp+110h+var_88], rax
0x18001dd92  lea     rax, [rbp+57h+var_58]
0x18001dd96  mov     [rsp+110h+var_90], rax
0x18001dd9e  lea     rax, [rbp+57h+var_50]
0x18001dda2  mov     [rsp+110h+var_98], rax
0x18001dda7  lea     rax, [rbp+57h+arg_8]
0x18001ddab  mov     [rsp+110h+var_A0], rax
0x18001ddb0  lea     rax, [rbp+57h+var_48]
0x18001ddb4  mov     [rsp+110h+var_A8], rax
0x18001ddb9  lea     rax, [rbp+57h+arg_10]
0x18001ddbd  mov     [rsp+110h+var_B0], rax
0x18001ddc2  lea     rax, [rbp+57h+var_40]
0x18001ddc6  mov     [rsp+110h+var_B8], rax
0x18001ddcb  lea     rax, [rbp+57h+arg_18]
0x18001ddcf  mov     [rsp+110h+var_C0], rax
0x18001ddd4  lea     rax, [rbp+57h+var_38]
0x18001ddd8  mov     [rsp+110h+var_C8], rax
0x18001dddd  lea     rax, [rbp+57h+var_70]
0x18001dde1  mov     [rsp+110h+var_D0], rax
0x18001dde6  lea     rax, [rbp+57h+var_30]
0x18001ddea  mov     [rsp+110h+var_D8], rax
0x18001ddef  lea     rax, [rbp+57h+var_6C]
0x18001ddf3  mov     [rsp+110h+var_E0], rax
0x18001ddf8  lea     rax, [rbp+57h+var_28]
0x18001ddfc  mov     [rsp+110h+var_E8], rax
0x18001de01  lea     rax, [rbp+57h+var_20]
0x18001de05  mov     [rbp+57h+var_68], rcx
0x18001de09  mov     rcx, r9
0x18001de0c  mov     [rsp+110h+var_F0], rax
0x18001de11  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001de16  jmp     short loc_18001DE93
0x18001de18  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001de1d  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001de22  mov     rdi, rax
0x18001de25  mov     ecx, [rax]
0x18001de27  cmp     ecx, 5
0x18001de2a  jbe     short loc_18001DE93
0x18001de2c  mov     rdx, 400000000000h
0x18001de36  mov     rcx, rax
0x18001de39  call    _tlgKeywordOn
0x18001de3e  test    al, al
0x18001de40  jz      short loc_18001DE93
0x18001de42  call    cs:__imp_GetCurrentThreadId
0x18001de48  mov     r8, [rbx+110h]
0x18001de4f  lea     rdx, byte_18002E233
0x18001de56  mov     [rbp+57h+arg_0], eax
0x18001de59  xor     r9d, r9d
0x18001de5c  mov     rcx, rdi
0x18001de5f  mov     eax, [r8+48h]
0x18001de63  add     r8, 8
0x18001de67  mov     [rbp+57h+arg_8], eax
0x18001de6a  mov     eax, 1000000h
0x18001de6f  mov     [rbp+57h+arg_10], rax
0x18001de73  lea     rax, [rbp+57h+arg_0]
0x18001de77  mov     [rsp+110h+var_E0], rax
0x18001de7c  lea     rax, [rbp+57h+arg_8]
0x18001de80  mov     [rsp+110h+var_E8], rax
0x18001de85  lea     rax, [rbp+57h+arg_10]
0x18001de89  mov     [rsp+110h+var_F0], rax
0x18001de8e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001de93  mov     rcx, rbx
0x18001de96  add     rsp, 100h
0x18001de9d  pop     rdi
0x18001de9e  pop     rbx
0x18001de9f  pop     rbp
0x18001dea0  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
