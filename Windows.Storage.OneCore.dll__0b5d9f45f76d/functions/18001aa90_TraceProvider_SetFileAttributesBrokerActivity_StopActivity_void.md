# TraceProvider::SetFileAttributesBrokerActivity::StopActivity(void)

- ea: `0x18001aa90`
- end: `0x18001acbc`
- name: `?StopActivity@SetFileAttributesBrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::SetFileAttributesBrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x18001aa90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ac5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ac5d`

## pseudocode

```c
void __fastcall TraceProvider::SetFileAttributesBrokerActivity::StopActivity(
        TraceProvider::SetFileAttributesBrokerActivity *this)
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
        (__int64)&unk_18002AAA0,
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
        (__int64)word_18002ABFA,
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
0x18001aa90  push    rbp
0x18001aa92  push    rbx
0x18001aa93  push    rdi
0x18001aa94  lea     rbp, [rsp+10h]
0x18001aa99  sub     rsp, 130h
0x18001aaa0  mov     rdi, [rcx+110h]
0x18001aaa7  mov     rbx, rcx
0x18001aaaa  mov     eax, [rdi+48h]
0x18001aaad  test    eax, eax
0x18001aaaf  jns     loc_18001AC49
0x18001aab5  add     rdi, 50h ; 'P'
0x18001aab9  cmp     eax, [rdi+8]
0x18001aabc  jnz     loc_18001AC49
0x18001aac2  test    rdi, rdi
0x18001aac5  jz      loc_18001AC49
0x18001aacb  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001aad0  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001aad5  mov     r9, rax
0x18001aad8  mov     ecx, [rax]
0x18001aada  cmp     ecx, 5
0x18001aadd  jbe     loc_18001ACAA
0x18001aae3  mov     rax, [rdi+70h]
0x18001aae7  lea     rdx, unk_18002AAA0
0x18001aaee  mov     rcx, [rdi+30h]
0x18001aaf2  mov     [rbp+var_60], rax
0x18001aaf6  mov     eax, [rdi+68h]
0x18001aaf9  mov     r8, [rbx+110h]
0x18001ab00  mov     dword ptr [rbp+arg_10], eax
0x18001ab03  add     r8, 8
0x18001ab07  mov     rax, [rdi+60h]
0x18001ab0b  mov     [rbp+var_58], rax
0x18001ab0f  mov     rax, [rdi+58h]
0x18001ab13  mov     [rbp+var_50], rax
0x18001ab17  mov     eax, [rdi+50h]
0x18001ab1a  mov     [rbp+arg_18], eax
0x18001ab1d  mov     rax, [rdi+48h]
0x18001ab21  mov     [rbp+var_48], rax
0x18001ab25  mov     eax, [rdi+20h]
0x18001ab28  mov     [rbp+var_80], eax
0x18001ab2b  mov     rax, [rdi+18h]
0x18001ab2f  mov     [rbp+var_40], rax
0x18001ab33  mov     eax, [rdi]
0x18001ab35  mov     [rbp+var_7C], eax
0x18001ab38  mov     rax, [rdi+80h]
0x18001ab3f  mov     [rbp+var_38], rax
0x18001ab43  mov     eax, [rdi+40h]
0x18001ab46  mov     [rbp+var_78], eax
0x18001ab49  mov     rax, [rdi+38h]
0x18001ab4d  mov     [rbp+var_30], rax
0x18001ab51  mov     eax, [rdi+8]
0x18001ab54  mov     [rbp+var_74], eax
0x18001ab57  lea     rax, [rbp+var_70]
0x18001ab5b  mov     [rsp+140h+var_90], rax
0x18001ab63  lea     rax, [rbp+arg_0]
0x18001ab67  mov     [rsp+140h+var_98], rax
0x18001ab6f  lea     rax, [rbp+arg_8]
0x18001ab73  mov     [rsp+140h+var_A0], rax
0x18001ab7b  lea     rax, [rbp+var_68]
0x18001ab7f  mov     [rsp+140h+var_A8], rax
0x18001ab87  lea     rax, [rbp+var_60]
0x18001ab8b  mov     [rsp+140h+var_B0], rax
0x18001ab93  lea     rax, [rbp+arg_10]
0x18001ab97  mov     [rsp+140h+var_B8], rax
0x18001ab9f  lea     rax, [rbp+var_58]
0x18001aba3  mov     [rsp+140h+var_C0], rax
0x18001abab  lea     rax, [rbp+var_50]
0x18001abaf  mov     [rsp+140h+var_C8], rax
0x18001abb4  lea     rax, [rbp+arg_18]
0x18001abb8  mov     [rsp+140h+var_D0], rax
0x18001abbd  lea     rax, [rbp+var_48]
0x18001abc1  mov     [rsp+140h+var_D8], rax
0x18001abc6  lea     rax, [rbp+var_80]
0x18001abca  mov     [rsp+140h+var_E0], rax
0x18001abcf  lea     rax, [rbp+var_40]
0x18001abd3  mov     [rsp+140h+var_E8], rax
0x18001abd8  lea     rax, [rbp+var_7C]
0x18001abdc  mov     [rsp+140h+var_F0], rax
0x18001abe1  lea     rax, [rbp+var_38]
0x18001abe5  mov     [rsp+140h+var_F8], rax
0x18001abea  lea     rax, [rbp+var_78]
0x18001abee  mov     [rsp+140h+var_100], rax
0x18001abf3  lea     rax, [rbp+var_30]
0x18001abf7  mov     [rsp+140h+var_108], rax
0x18001abfc  lea     rax, [rbp+var_74]
0x18001ac00  mov     [rbp+var_70], rcx
0x18001ac04  mov     ecx, [rdi+44h]
0x18001ac07  mov     [rsp+140h+var_110], rax
0x18001ac0c  lea     rax, [rbp+var_28]
0x18001ac10  mov     [rbp+arg_0], ecx
0x18001ac13  mov     ecx, [rdi+10h]
0x18001ac16  mov     [rbp+arg_8], ecx
0x18001ac19  mov     rcx, [rdi+78h]
0x18001ac1d  mov     [rsp+140h+var_118], rax
0x18001ac22  lea     rax, [rbp+var_20]
0x18001ac26  mov     [rbp+var_68], rcx
0x18001ac2a  mov     rcx, r9
0x18001ac2d  mov     [rsp+140h+var_120], rax
0x18001ac32  mov     [rbp+var_28], 1000000h
0x18001ac3a  mov     [rbp+var_20], 0
0x18001ac42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001ac47  jmp     short loc_18001ACAA
0x18001ac49  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001ac4e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001ac53  mov     rdi, rax
0x18001ac56  mov     ecx, [rax]
0x18001ac58  cmp     ecx, 5
0x18001ac5b  jbe     short loc_18001ACAA
0x18001ac5d  call    cs:__imp_GetCurrentThreadId
0x18001ac63  mov     r8, [rbx+110h]
0x18001ac6a  lea     rdx, word_18002ABFA
0x18001ac71  mov     [rbp+arg_0], eax
0x18001ac74  lea     rax, [rbp+arg_0]
0x18001ac78  mov     [rsp+140h+var_110], rax
0x18001ac7d  lea     rax, [rbp+arg_8]
0x18001ac81  mov     [rsp+140h+var_118], rax
0x18001ac86  lea     rax, [rbp+arg_10]
0x18001ac8a  mov     ecx, [r8+48h]
0x18001ac8e  add     r8, 8
0x18001ac92  mov     [rbp+arg_8], ecx
0x18001ac95  mov     rcx, rdi
0x18001ac98  mov     [rsp+140h+var_120], rax
0x18001ac9d  mov     [rbp+arg_10], 0
0x18001aca5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001acaa  mov     rcx, rbx
0x18001acad  add     rsp, 130h
0x18001acb4  pop     rdi
0x18001acb5  pop     rbx
0x18001acb6  pop     rbp
0x18001acb7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
