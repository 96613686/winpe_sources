# PolicyTelemetry::ExemptionPolicyEvaluation::Stop(uint)

- ea: `0x1800210a0`
- end: `0x1800212ee`
- name: `?Stop@ExemptionPolicyEvaluation@PolicyTelemetry@@QEAAXI@Z`
- size: `590`
- prototype: `void __fastcall(PolicyTelemetry::ExemptionPolicyEvaluation *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180020e10`

## callees

- `0x180001b0c`
- `0x1800020c0`
- `0x180002384`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x1800210a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002127d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002127d`

## pseudocode

```c
void __fastcall PolicyTelemetry::ExemptionPolicyEvaluation::Stop(
        PolicyTelemetry::ExemptionPolicyEvaluation *this,
        int a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  int v19; // [rsp+B8h] [rbp-78h] BYREF
  int v20; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-70h] BYREF
  const WCHAR *v22; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-60h] BYREF
  const WCHAR *v24; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-48h] BYREF
  const WCHAR *v27; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v28; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-30h] BYREF
  __int64 v30[3]; // [rsp+108h] [rbp-28h] BYREF
  int v31; // [rsp+130h] [rbp+0h] BYREF
  DWORD v32; // [rsp+140h] [rbp+10h] BYREF
  int v33; // [rsp+148h] [rbp+18h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = SharedPCAccountManagerLogging::Provider();
    v10 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v9, v7) )
    {
      v22 = (const WCHAR *)*((_QWORD *)v6 + 15);
      v11 = *((_QWORD *)this + 34);
      v23 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v32 = v6[26];
      v24 = (const WCHAR *)*((_QWORD *)v6 + 12);
      v25 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v33 = v6[20];
      v26 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      v17 = v6[8];
      v27 = (const WCHAR *)*((_QWORD *)v6 + 3);
      v18 = *v6;
      v28 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      v19 = v6[16];
      v29 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      v20 = v6[2];
      v30[0] = 0x1000000;
      v21 = 0x1000000;
      v31 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v10,
        (__int64)&byte_18002F28F,
        v11 + 8,
        v10,
        (__int64)&v21,
        (__int64)v30,
        (__int64)&v20,
        &v29,
        (__int64)&v19,
        &v28,
        (__int64)&v18,
        &v27,
        (__int64)&v17,
        &v26,
        (__int64)&v33,
        &v25,
        &v24,
        (__int64)&v32,
        &v23,
        &v22,
        (__int64)&v31);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = SharedPCAccountManagerLogging::Provider();
    v13 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v9, v10) )
    {
      v31 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v32 = CurrentThreadId;
      v33 = *(_DWORD *)(v15 + 72);
      v21 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v13,
        (__int64)byte_18002F561,
        v15 + 8,
        v16,
        (__int64)&v21,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v8,
    v9,
    v10);
}

```

## disassembly

```asm
0x1800210a0  mov     [rsp-8+arg_8], rbx
0x1800210a5  push    rbp
0x1800210a6  push    rsi
0x1800210a7  push    rdi
0x1800210a8  lea     rbp, [rsp+20h]
0x1800210ad  sub     rsp, 110h
0x1800210b4  mov     rdi, [rcx+110h]
0x1800210bb  mov     esi, edx
0x1800210bd  mov     rbx, rcx
0x1800210c0  mov     eax, [rdi+48h]
0x1800210c3  test    eax, eax
0x1800210c5  jns     loc_180021250
0x1800210cb  add     rdi, 50h ; 'P'
0x1800210cf  cmp     eax, [rdi+8]
0x1800210d2  jnz     loc_180021250
0x1800210d8  test    rdi, rdi
0x1800210db  jz      loc_180021250
0x1800210e1  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800210e6  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x1800210eb  mov     r9, rax
0x1800210ee  mov     ecx, [rax]
0x1800210f0  cmp     ecx, 5
0x1800210f3  jbe     loc_1800212D4
0x1800210f9  mov     rdx, 400000000000h
0x180021103  mov     rcx, rax
0x180021106  call    _tlgKeywordOn
0x18002110b  test    al, al
0x18002110d  jz      loc_1800212D4
0x180021113  mov     rax, [rdi+78h]
0x180021117  lea     rdx, byte_18002F28F
0x18002111e  mov     [rbp-10h+var_58], rax
0x180021122  mov     rcx, r9
0x180021125  mov     rax, [rdi+70h]
0x180021129  mov     r8, [rbx+110h]
0x180021130  mov     [rbp-10h+var_50], rax
0x180021134  add     r8, 8
0x180021138  mov     eax, [rdi+68h]
0x18002113b  mov     [rbp-10h+arg_10], eax
0x18002113e  mov     rax, [rdi+60h]
0x180021142  mov     [rbp-10h+var_48], rax
0x180021146  mov     rax, [rdi+58h]
0x18002114a  mov     [rbp-10h+var_40], rax
0x18002114e  mov     eax, [rdi+50h]
0x180021151  mov     [rbp-10h+arg_18], eax
0x180021154  mov     rax, [rdi+48h]
0x180021158  mov     [rbp-10h+var_38], rax
0x18002115c  mov     eax, [rdi+20h]
0x18002115f  mov     [rbp-10h+var_70], eax
0x180021162  mov     rax, [rdi+18h]
0x180021166  mov     [rbp-10h+var_30], rax
0x18002116a  mov     eax, [rdi]
0x18002116c  mov     [rbp-10h+var_6C], eax
0x18002116f  mov     rax, [rdi+80h]
0x180021176  mov     [rbp-10h+var_28], rax
0x18002117a  mov     eax, [rdi+40h]
0x18002117d  mov     [rbp-10h+var_68], eax
0x180021180  mov     rax, [rdi+38h]
0x180021184  mov     [rbp-10h+var_20], rax
0x180021188  mov     eax, [rdi+8]
0x18002118b  mov     [rbp-10h+var_64], eax
0x18002118e  mov     eax, 1000000h
0x180021193  mov     [rbp-10h+var_18], rax
0x180021197  mov     [rbp-10h+var_60], rax
0x18002119b  lea     rax, [rbp-10h+arg_0]
0x18002119f  mov     [rsp+120h+var_80], rax
0x1800211a7  lea     rax, [rbp-10h+var_58]
0x1800211ab  mov     [rsp+120h+var_88], rax
0x1800211b3  lea     rax, [rbp-10h+var_50]
0x1800211b7  mov     [rsp+120h+var_90], rax
0x1800211bf  lea     rax, [rbp-10h+arg_10]
0x1800211c3  mov     [rsp+120h+var_98], rax
0x1800211cb  lea     rax, [rbp-10h+var_48]
0x1800211cf  mov     [rsp+120h+var_A0], rax
0x1800211d7  lea     rax, [rbp-10h+var_40]
0x1800211db  mov     [rsp+120h+var_A8], rax
0x1800211e0  lea     rax, [rbp-10h+arg_18]
0x1800211e4  mov     [rsp+120h+var_B0], rax
0x1800211e9  lea     rax, [rbp-10h+var_38]
0x1800211ed  mov     [rsp+120h+var_B8], rax
0x1800211f2  lea     rax, [rbp-10h+var_70]
0x1800211f6  mov     [rsp+120h+var_C0], rax
0x1800211fb  lea     rax, [rbp-10h+var_30]
0x1800211ff  mov     [rsp+120h+var_C8], rax
0x180021204  lea     rax, [rbp-10h+var_6C]
0x180021208  mov     [rsp+120h+var_D0], rax
0x18002120d  lea     rax, [rbp-10h+var_28]
0x180021211  mov     [rsp+120h+var_D8], rax
0x180021216  lea     rax, [rbp-10h+var_68]
0x18002121a  mov     [rsp+120h+var_E0], rax
0x18002121f  lea     rax, [rbp-10h+var_20]
0x180021223  mov     [rsp+120h+var_E8], rax
0x180021228  lea     rax, [rbp-10h+var_64]
0x18002122c  mov     [rsp+120h+var_F0], rax
0x180021231  lea     rax, [rbp-10h+var_18]
0x180021235  mov     [rsp+120h+var_F8], rax
0x18002123a  lea     rax, [rbp-10h+var_60]
0x18002123e  mov     [rsp+120h+var_100], rax
0x180021243  mov     [rbp-10h+arg_0], esi
0x180021246  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002124b  jmp     loc_1800212D4
0x180021250  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180021255  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18002125a  mov     rdi, rax
0x18002125d  mov     ecx, [rax]
0x18002125f  cmp     ecx, 5
0x180021262  jbe     short loc_1800212D4
0x180021264  mov     rdx, 400000000000h
0x18002126e  mov     rcx, rax
0x180021271  call    _tlgKeywordOn
0x180021276  test    al, al
0x180021278  jz      short loc_1800212D4
0x18002127a  mov     [rbp-10h+arg_0], esi
0x18002127d  call    cs:__imp_GetCurrentThreadId
0x180021283  mov     r8, [rbx+110h]
0x18002128a  lea     rdx, byte_18002F561
0x180021291  mov     [rbp-10h+arg_10], eax
0x180021294  mov     rcx, rdi
0x180021297  mov     eax, [r8+48h]
0x18002129b  add     r8, 8
0x18002129f  mov     [rbp-10h+arg_18], eax
0x1800212a2  mov     eax, 1000000h
0x1800212a7  mov     [rbp-10h+var_60], rax
0x1800212ab  lea     rax, [rbp-10h+arg_0]
0x1800212af  mov     [rsp+120h+var_E8], rax
0x1800212b4  lea     rax, [rbp-10h+arg_10]
0x1800212b8  mov     [rsp+120h+var_F0], rax
0x1800212bd  lea     rax, [rbp-10h+arg_18]
0x1800212c1  mov     [rsp+120h+var_F8], rax
0x1800212c6  lea     rax, [rbp-10h+var_60]
0x1800212ca  mov     [rsp+120h+var_100], rax
0x1800212cf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800212d4  mov     rcx, rbx
0x1800212d7  mov     rbx, [rsp+120h+arg_8]
0x1800212df  add     rsp, 110h
0x1800212e6  pop     rdi
0x1800212e7  pop     rsi
0x1800212e8  pop     rbp
0x1800212e9  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
