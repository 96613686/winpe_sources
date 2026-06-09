# TraceProvider::RemoveDirectoryProxyActivity::StopActivity(void)

- ea: `0x180020840`
- end: `0x180020a6c`
- name: `?StopActivity@RemoveDirectoryProxyActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::RemoveDirectoryProxyActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x180020840`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020a0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020a0d`

## pseudocode

```c
void __fastcall TraceProvider::RemoveDirectoryProxyActivity::StopActivity(
        TraceProvider::RemoveDirectoryProxyActivity *this)
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
        (__int64)byte_18002BD69,
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
        (__int64)&unk_18002BEC0,
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
0x180020840  push    rbp
0x180020842  push    rbx
0x180020843  push    rdi
0x180020844  lea     rbp, [rsp+10h]
0x180020849  sub     rsp, 130h
0x180020850  mov     rdi, [rcx+110h]
0x180020857  mov     rbx, rcx
0x18002085a  mov     eax, [rdi+48h]
0x18002085d  test    eax, eax
0x18002085f  jns     loc_1800209F9
0x180020865  add     rdi, 50h ; 'P'
0x180020869  cmp     eax, [rdi+8]
0x18002086c  jnz     loc_1800209F9
0x180020872  test    rdi, rdi
0x180020875  jz      loc_1800209F9
0x18002087b  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180020880  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180020885  mov     r9, rax
0x180020888  mov     ecx, [rax]
0x18002088a  cmp     ecx, 5
0x18002088d  jbe     loc_180020A5A
0x180020893  mov     rax, [rdi+70h]
0x180020897  lea     rdx, byte_18002BD69
0x18002089e  mov     rcx, [rdi+30h]
0x1800208a2  mov     [rbp+var_60], rax
0x1800208a6  mov     eax, [rdi+68h]
0x1800208a9  mov     r8, [rbx+110h]
0x1800208b0  mov     dword ptr [rbp+arg_10], eax
0x1800208b3  add     r8, 8
0x1800208b7  mov     rax, [rdi+60h]
0x1800208bb  mov     [rbp+var_58], rax
0x1800208bf  mov     rax, [rdi+58h]
0x1800208c3  mov     [rbp+var_50], rax
0x1800208c7  mov     eax, [rdi+50h]
0x1800208ca  mov     [rbp+arg_18], eax
0x1800208cd  mov     rax, [rdi+48h]
0x1800208d1  mov     [rbp+var_48], rax
0x1800208d5  mov     eax, [rdi+20h]
0x1800208d8  mov     [rbp+var_80], eax
0x1800208db  mov     rax, [rdi+18h]
0x1800208df  mov     [rbp+var_40], rax
0x1800208e3  mov     eax, [rdi]
0x1800208e5  mov     [rbp+var_7C], eax
0x1800208e8  mov     rax, [rdi+80h]
0x1800208ef  mov     [rbp+var_38], rax
0x1800208f3  mov     eax, [rdi+40h]
0x1800208f6  mov     [rbp+var_78], eax
0x1800208f9  mov     rax, [rdi+38h]
0x1800208fd  mov     [rbp+var_30], rax
0x180020901  mov     eax, [rdi+8]
0x180020904  mov     [rbp+var_74], eax
0x180020907  lea     rax, [rbp+var_70]
0x18002090b  mov     [rsp+140h+var_90], rax
0x180020913  lea     rax, [rbp+arg_0]
0x180020917  mov     [rsp+140h+var_98], rax
0x18002091f  lea     rax, [rbp+arg_8]
0x180020923  mov     [rsp+140h+var_A0], rax
0x18002092b  lea     rax, [rbp+var_68]
0x18002092f  mov     [rsp+140h+var_A8], rax
0x180020937  lea     rax, [rbp+var_60]
0x18002093b  mov     [rsp+140h+var_B0], rax
0x180020943  lea     rax, [rbp+arg_10]
0x180020947  mov     [rsp+140h+var_B8], rax
0x18002094f  lea     rax, [rbp+var_58]
0x180020953  mov     [rsp+140h+var_C0], rax
0x18002095b  lea     rax, [rbp+var_50]
0x18002095f  mov     [rsp+140h+var_C8], rax
0x180020964  lea     rax, [rbp+arg_18]
0x180020968  mov     [rsp+140h+var_D0], rax
0x18002096d  lea     rax, [rbp+var_48]
0x180020971  mov     [rsp+140h+var_D8], rax
0x180020976  lea     rax, [rbp+var_80]
0x18002097a  mov     [rsp+140h+var_E0], rax
0x18002097f  lea     rax, [rbp+var_40]
0x180020983  mov     [rsp+140h+var_E8], rax
0x180020988  lea     rax, [rbp+var_7C]
0x18002098c  mov     [rsp+140h+var_F0], rax
0x180020991  lea     rax, [rbp+var_38]
0x180020995  mov     [rsp+140h+var_F8], rax
0x18002099a  lea     rax, [rbp+var_78]
0x18002099e  mov     [rsp+140h+var_100], rax
0x1800209a3  lea     rax, [rbp+var_30]
0x1800209a7  mov     [rsp+140h+var_108], rax
0x1800209ac  lea     rax, [rbp+var_74]
0x1800209b0  mov     [rbp+var_70], rcx
0x1800209b4  mov     ecx, [rdi+44h]
0x1800209b7  mov     [rsp+140h+var_110], rax
0x1800209bc  lea     rax, [rbp+var_28]
0x1800209c0  mov     [rbp+arg_0], ecx
0x1800209c3  mov     ecx, [rdi+10h]
0x1800209c6  mov     [rbp+arg_8], ecx
0x1800209c9  mov     rcx, [rdi+78h]
0x1800209cd  mov     [rsp+140h+var_118], rax
0x1800209d2  lea     rax, [rbp+var_20]
0x1800209d6  mov     [rbp+var_68], rcx
0x1800209da  mov     rcx, r9
0x1800209dd  mov     [rsp+140h+var_120], rax
0x1800209e2  mov     [rbp+var_28], 1000000h
0x1800209ea  mov     [rbp+var_20], 0
0x1800209f2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800209f7  jmp     short loc_180020A5A
0x1800209f9  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800209fe  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180020a03  mov     rdi, rax
0x180020a06  mov     ecx, [rax]
0x180020a08  cmp     ecx, 5
0x180020a0b  jbe     short loc_180020A5A
0x180020a0d  call    cs:__imp_GetCurrentThreadId
0x180020a13  mov     r8, [rbx+110h]
0x180020a1a  lea     rdx, unk_18002BEC0
0x180020a21  mov     [rbp+arg_0], eax
0x180020a24  lea     rax, [rbp+arg_0]
0x180020a28  mov     [rsp+140h+var_110], rax
0x180020a2d  lea     rax, [rbp+arg_8]
0x180020a31  mov     [rsp+140h+var_118], rax
0x180020a36  lea     rax, [rbp+arg_10]
0x180020a3a  mov     ecx, [r8+48h]
0x180020a3e  add     r8, 8
0x180020a42  mov     [rbp+arg_8], ecx
0x180020a45  mov     rcx, rdi
0x180020a48  mov     [rsp+140h+var_120], rax
0x180020a4d  mov     [rbp+arg_10], 0
0x180020a55  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020a5a  mov     rcx, rbx
0x180020a5d  add     rsp, 130h
0x180020a64  pop     rdi
0x180020a65  pop     rbx
0x180020a66  pop     rbp
0x180020a67  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
