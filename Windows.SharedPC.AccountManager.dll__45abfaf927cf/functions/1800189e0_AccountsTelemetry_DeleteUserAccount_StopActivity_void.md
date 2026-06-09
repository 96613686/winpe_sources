# AccountsTelemetry::DeleteUserAccount::StopActivity(void)

- ea: `0x1800189e0`
- end: `0x180018c05`
- name: `?StopActivity@DeleteUserAccount@AccountsTelemetry@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(AccountsTelemetry::DeleteUserAccount *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180001010`
- `0x180001384`
- `0x180001b0c`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x1800189e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018ba2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018ba2`

## pseudocode

```c
void __fastcall AccountsTelemetry::DeleteUserAccount::StopActivity(AccountsTelemetry::DeleteUserAccount *this)
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
        (__int64)&dword_18002D9CC,
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
        (__int64)byte_18002D631,
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
0x1800189e0  push    rbp
0x1800189e2  push    rbx
0x1800189e3  push    rdi
0x1800189e4  lea     rbp, [rsp-47h]
0x1800189e9  sub     rsp, 100h
0x1800189f0  mov     rdi, [rcx+110h]
0x1800189f7  mov     rbx, rcx
0x1800189fa  mov     eax, [rdi+48h]
0x1800189fd  test    eax, eax
0x1800189ff  jns     loc_180018B78
0x180018a05  add     rdi, 50h ; 'P'
0x180018a09  cmp     eax, [rdi+8]
0x180018a0c  jnz     loc_180018B78
0x180018a12  test    rdi, rdi
0x180018a15  jz      loc_180018B78
0x180018a1b  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018a20  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180018a25  mov     r9, rax
0x180018a28  mov     ecx, [rax]
0x180018a2a  cmp     ecx, 5
0x180018a2d  jbe     loc_180018BF3
0x180018a33  mov     rdx, 400000000000h
0x180018a3d  mov     rcx, rax
0x180018a40  call    _tlgKeywordOn
0x180018a45  test    al, al
0x180018a47  jz      loc_180018BF3
0x180018a4d  mov     rax, [rdi+70h]
0x180018a51  lea     rdx, dword_18002D9CC
0x180018a58  mov     rcx, [rdi+78h]
0x180018a5c  mov     r8, [rbx+110h]
0x180018a63  mov     [rbp+57h+var_60], rax
0x180018a67  add     r8, 8
0x180018a6b  mov     eax, [rdi+68h]
0x180018a6e  mov     [rbp+57h+arg_0], eax
0x180018a71  mov     rax, [rdi+60h]
0x180018a75  mov     [rbp+57h+var_58], rax
0x180018a79  mov     rax, [rdi+58h]
0x180018a7d  mov     [rbp+57h+var_50], rax
0x180018a81  mov     eax, [rdi+50h]
0x180018a84  mov     [rbp+57h+arg_8], eax
0x180018a87  mov     rax, [rdi+48h]
0x180018a8b  mov     [rbp+57h+var_48], rax
0x180018a8f  mov     eax, [rdi+20h]
0x180018a92  mov     dword ptr [rbp+57h+arg_10], eax
0x180018a95  mov     rax, [rdi+18h]
0x180018a99  mov     [rbp+57h+var_40], rax
0x180018a9d  mov     eax, [rdi]
0x180018a9f  mov     [rbp+57h+arg_18], eax
0x180018aa2  mov     rax, [rdi+80h]
0x180018aa9  mov     [rbp+57h+var_38], rax
0x180018aad  mov     eax, [rdi+40h]
0x180018ab0  mov     [rbp+57h+var_70], eax
0x180018ab3  mov     rax, [rdi+38h]
0x180018ab7  mov     [rbp+57h+var_30], rax
0x180018abb  mov     eax, [rdi+8]
0x180018abe  mov     [rbp+57h+var_6C], eax
0x180018ac1  mov     eax, 1000000h
0x180018ac6  mov     [rbp+57h+var_28], rax
0x180018aca  mov     [rbp+57h+var_20], rax
0x180018ace  lea     rax, [rbp+57h+var_68]
0x180018ad2  mov     [rsp+110h+var_78], rax
0x180018ada  lea     rax, [rbp+57h+var_60]
0x180018ade  mov     [rsp+110h+var_80], rax
0x180018ae6  lea     rax, [rbp+57h+arg_0]
0x180018aea  mov     [rsp+110h+var_88], rax
0x180018af2  lea     rax, [rbp+57h+var_58]
0x180018af6  mov     [rsp+110h+var_90], rax
0x180018afe  lea     rax, [rbp+57h+var_50]
0x180018b02  mov     [rsp+110h+var_98], rax
0x180018b07  lea     rax, [rbp+57h+arg_8]
0x180018b0b  mov     [rsp+110h+var_A0], rax
0x180018b10  lea     rax, [rbp+57h+var_48]
0x180018b14  mov     [rsp+110h+var_A8], rax
0x180018b19  lea     rax, [rbp+57h+arg_10]
0x180018b1d  mov     [rsp+110h+var_B0], rax
0x180018b22  lea     rax, [rbp+57h+var_40]
0x180018b26  mov     [rsp+110h+var_B8], rax
0x180018b2b  lea     rax, [rbp+57h+arg_18]
0x180018b2f  mov     [rsp+110h+var_C0], rax
0x180018b34  lea     rax, [rbp+57h+var_38]
0x180018b38  mov     [rsp+110h+var_C8], rax
0x180018b3d  lea     rax, [rbp+57h+var_70]
0x180018b41  mov     [rsp+110h+var_D0], rax
0x180018b46  lea     rax, [rbp+57h+var_30]
0x180018b4a  mov     [rsp+110h+var_D8], rax
0x180018b4f  lea     rax, [rbp+57h+var_6C]
0x180018b53  mov     [rsp+110h+var_E0], rax
0x180018b58  lea     rax, [rbp+57h+var_28]
0x180018b5c  mov     [rsp+110h+var_E8], rax
0x180018b61  lea     rax, [rbp+57h+var_20]
0x180018b65  mov     [rbp+57h+var_68], rcx
0x180018b69  mov     rcx, r9
0x180018b6c  mov     [rsp+110h+var_F0], rax
0x180018b71  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180018b76  jmp     short loc_180018BF3
0x180018b78  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018b7d  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x180018b82  mov     rdi, rax
0x180018b85  mov     ecx, [rax]
0x180018b87  cmp     ecx, 5
0x180018b8a  jbe     short loc_180018BF3
0x180018b8c  mov     rdx, 400000000000h
0x180018b96  mov     rcx, rax
0x180018b99  call    _tlgKeywordOn
0x180018b9e  test    al, al
0x180018ba0  jz      short loc_180018BF3
0x180018ba2  call    cs:__imp_GetCurrentThreadId
0x180018ba8  mov     r8, [rbx+110h]
0x180018baf  lea     rdx, byte_18002D631
0x180018bb6  mov     [rbp+57h+arg_0], eax
0x180018bb9  xor     r9d, r9d
0x180018bbc  mov     rcx, rdi
0x180018bbf  mov     eax, [r8+48h]
0x180018bc3  add     r8, 8
0x180018bc7  mov     [rbp+57h+arg_8], eax
0x180018bca  mov     eax, 1000000h
0x180018bcf  mov     [rbp+57h+arg_10], rax
0x180018bd3  lea     rax, [rbp+57h+arg_0]
0x180018bd7  mov     [rsp+110h+var_E0], rax
0x180018bdc  lea     rax, [rbp+57h+arg_8]
0x180018be0  mov     [rsp+110h+var_E8], rax
0x180018be5  lea     rax, [rbp+57h+arg_10]
0x180018be9  mov     [rsp+110h+var_F0], rax
0x180018bee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180018bf3  mov     rcx, rbx
0x180018bf6  add     rsp, 100h
0x180018bfd  pop     rdi
0x180018bfe  pop     rbx
0x180018bff  pop     rbp
0x180018c00  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
