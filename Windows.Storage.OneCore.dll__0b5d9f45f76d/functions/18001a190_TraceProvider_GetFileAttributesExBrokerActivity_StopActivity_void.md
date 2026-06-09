# TraceProvider::GetFileAttributesExBrokerActivity::StopActivity(void)

- ea: `0x18001a190`
- end: `0x18001a3bc`
- name: `?StopActivity@GetFileAttributesExBrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::GetFileAttributesExBrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x18001a190`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a35d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a35d`

## pseudocode

```c
void __fastcall TraceProvider::GetFileAttributesExBrokerActivity::StopActivity(
        TraceProvider::GetFileAttributesExBrokerActivity *this)
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
        (__int64)&unk_18002AFB0,
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
        (__int64)&dword_18002B10C,
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
0x18001a190  push    rbp
0x18001a192  push    rbx
0x18001a193  push    rdi
0x18001a194  lea     rbp, [rsp+10h]
0x18001a199  sub     rsp, 130h
0x18001a1a0  mov     rdi, [rcx+110h]
0x18001a1a7  mov     rbx, rcx
0x18001a1aa  mov     eax, [rdi+48h]
0x18001a1ad  test    eax, eax
0x18001a1af  jns     loc_18001A349
0x18001a1b5  add     rdi, 50h ; 'P'
0x18001a1b9  cmp     eax, [rdi+8]
0x18001a1bc  jnz     loc_18001A349
0x18001a1c2  test    rdi, rdi
0x18001a1c5  jz      loc_18001A349
0x18001a1cb  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a1d0  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001a1d5  mov     r9, rax
0x18001a1d8  mov     ecx, [rax]
0x18001a1da  cmp     ecx, 5
0x18001a1dd  jbe     loc_18001A3AA
0x18001a1e3  mov     rax, [rdi+70h]
0x18001a1e7  lea     rdx, unk_18002AFB0
0x18001a1ee  mov     rcx, [rdi+30h]
0x18001a1f2  mov     [rbp+var_60], rax
0x18001a1f6  mov     eax, [rdi+68h]
0x18001a1f9  mov     r8, [rbx+110h]
0x18001a200  mov     dword ptr [rbp+arg_10], eax
0x18001a203  add     r8, 8
0x18001a207  mov     rax, [rdi+60h]
0x18001a20b  mov     [rbp+var_58], rax
0x18001a20f  mov     rax, [rdi+58h]
0x18001a213  mov     [rbp+var_50], rax
0x18001a217  mov     eax, [rdi+50h]
0x18001a21a  mov     [rbp+arg_18], eax
0x18001a21d  mov     rax, [rdi+48h]
0x18001a221  mov     [rbp+var_48], rax
0x18001a225  mov     eax, [rdi+20h]
0x18001a228  mov     [rbp+var_80], eax
0x18001a22b  mov     rax, [rdi+18h]
0x18001a22f  mov     [rbp+var_40], rax
0x18001a233  mov     eax, [rdi]
0x18001a235  mov     [rbp+var_7C], eax
0x18001a238  mov     rax, [rdi+80h]
0x18001a23f  mov     [rbp+var_38], rax
0x18001a243  mov     eax, [rdi+40h]
0x18001a246  mov     [rbp+var_78], eax
0x18001a249  mov     rax, [rdi+38h]
0x18001a24d  mov     [rbp+var_30], rax
0x18001a251  mov     eax, [rdi+8]
0x18001a254  mov     [rbp+var_74], eax
0x18001a257  lea     rax, [rbp+var_70]
0x18001a25b  mov     [rsp+140h+var_90], rax
0x18001a263  lea     rax, [rbp+arg_0]
0x18001a267  mov     [rsp+140h+var_98], rax
0x18001a26f  lea     rax, [rbp+arg_8]
0x18001a273  mov     [rsp+140h+var_A0], rax
0x18001a27b  lea     rax, [rbp+var_68]
0x18001a27f  mov     [rsp+140h+var_A8], rax
0x18001a287  lea     rax, [rbp+var_60]
0x18001a28b  mov     [rsp+140h+var_B0], rax
0x18001a293  lea     rax, [rbp+arg_10]
0x18001a297  mov     [rsp+140h+var_B8], rax
0x18001a29f  lea     rax, [rbp+var_58]
0x18001a2a3  mov     [rsp+140h+var_C0], rax
0x18001a2ab  lea     rax, [rbp+var_50]
0x18001a2af  mov     [rsp+140h+var_C8], rax
0x18001a2b4  lea     rax, [rbp+arg_18]
0x18001a2b8  mov     [rsp+140h+var_D0], rax
0x18001a2bd  lea     rax, [rbp+var_48]
0x18001a2c1  mov     [rsp+140h+var_D8], rax
0x18001a2c6  lea     rax, [rbp+var_80]
0x18001a2ca  mov     [rsp+140h+var_E0], rax
0x18001a2cf  lea     rax, [rbp+var_40]
0x18001a2d3  mov     [rsp+140h+var_E8], rax
0x18001a2d8  lea     rax, [rbp+var_7C]
0x18001a2dc  mov     [rsp+140h+var_F0], rax
0x18001a2e1  lea     rax, [rbp+var_38]
0x18001a2e5  mov     [rsp+140h+var_F8], rax
0x18001a2ea  lea     rax, [rbp+var_78]
0x18001a2ee  mov     [rsp+140h+var_100], rax
0x18001a2f3  lea     rax, [rbp+var_30]
0x18001a2f7  mov     [rsp+140h+var_108], rax
0x18001a2fc  lea     rax, [rbp+var_74]
0x18001a300  mov     [rbp+var_70], rcx
0x18001a304  mov     ecx, [rdi+44h]
0x18001a307  mov     [rsp+140h+var_110], rax
0x18001a30c  lea     rax, [rbp+var_28]
0x18001a310  mov     [rbp+arg_0], ecx
0x18001a313  mov     ecx, [rdi+10h]
0x18001a316  mov     [rbp+arg_8], ecx
0x18001a319  mov     rcx, [rdi+78h]
0x18001a31d  mov     [rsp+140h+var_118], rax
0x18001a322  lea     rax, [rbp+var_20]
0x18001a326  mov     [rbp+var_68], rcx
0x18001a32a  mov     rcx, r9
0x18001a32d  mov     [rsp+140h+var_120], rax
0x18001a332  mov     [rbp+var_28], 1000000h
0x18001a33a  mov     [rbp+var_20], 0
0x18001a342  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a347  jmp     short loc_18001A3AA
0x18001a349  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a34e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001a353  mov     rdi, rax
0x18001a356  mov     ecx, [rax]
0x18001a358  cmp     ecx, 5
0x18001a35b  jbe     short loc_18001A3AA
0x18001a35d  call    cs:__imp_GetCurrentThreadId
0x18001a363  mov     r8, [rbx+110h]
0x18001a36a  lea     rdx, dword_18002B10C
0x18001a371  mov     [rbp+arg_0], eax
0x18001a374  lea     rax, [rbp+arg_0]
0x18001a378  mov     [rsp+140h+var_110], rax
0x18001a37d  lea     rax, [rbp+arg_8]
0x18001a381  mov     [rsp+140h+var_118], rax
0x18001a386  lea     rax, [rbp+arg_10]
0x18001a38a  mov     ecx, [r8+48h]
0x18001a38e  add     r8, 8
0x18001a392  mov     [rbp+arg_8], ecx
0x18001a395  mov     rcx, rdi
0x18001a398  mov     [rsp+140h+var_120], rax
0x18001a39d  mov     [rbp+arg_10], 0
0x18001a3a5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a3aa  mov     rcx, rbx
0x18001a3ad  add     rsp, 130h
0x18001a3b4  pop     rdi
0x18001a3b5  pop     rbx
0x18001a3b6  pop     rbp
0x18001a3b7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
