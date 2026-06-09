# TraceProvider::GetFileAttributesBrokerActivity::StopActivity(void)

- ea: `0x180019f50`
- end: `0x18001a17c`
- name: `?StopActivity@GetFileAttributesBrokerActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::GetFileAttributesBrokerActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x180019f50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a11d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a11d`

## pseudocode

```c
void __fastcall TraceProvider::GetFileAttributesBrokerActivity::StopActivity(
        TraceProvider::GetFileAttributesBrokerActivity *this)
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
        (__int64)&word_18002B16E,
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
        (__int64)&unk_18002B2C8,
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
0x180019f50  push    rbp
0x180019f52  push    rbx
0x180019f53  push    rdi
0x180019f54  lea     rbp, [rsp+10h]
0x180019f59  sub     rsp, 130h
0x180019f60  mov     rdi, [rcx+110h]
0x180019f67  mov     rbx, rcx
0x180019f6a  mov     eax, [rdi+48h]
0x180019f6d  test    eax, eax
0x180019f6f  jns     loc_18001A109
0x180019f75  add     rdi, 50h ; 'P'
0x180019f79  cmp     eax, [rdi+8]
0x180019f7c  jnz     loc_18001A109
0x180019f82  test    rdi, rdi
0x180019f85  jz      loc_18001A109
0x180019f8b  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180019f90  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180019f95  mov     r9, rax
0x180019f98  mov     ecx, [rax]
0x180019f9a  cmp     ecx, 5
0x180019f9d  jbe     loc_18001A16A
0x180019fa3  mov     rax, [rdi+70h]
0x180019fa7  lea     rdx, word_18002B16E
0x180019fae  mov     rcx, [rdi+30h]
0x180019fb2  mov     [rbp+var_60], rax
0x180019fb6  mov     eax, [rdi+68h]
0x180019fb9  mov     r8, [rbx+110h]
0x180019fc0  mov     dword ptr [rbp+arg_10], eax
0x180019fc3  add     r8, 8
0x180019fc7  mov     rax, [rdi+60h]
0x180019fcb  mov     [rbp+var_58], rax
0x180019fcf  mov     rax, [rdi+58h]
0x180019fd3  mov     [rbp+var_50], rax
0x180019fd7  mov     eax, [rdi+50h]
0x180019fda  mov     [rbp+arg_18], eax
0x180019fdd  mov     rax, [rdi+48h]
0x180019fe1  mov     [rbp+var_48], rax
0x180019fe5  mov     eax, [rdi+20h]
0x180019fe8  mov     [rbp+var_80], eax
0x180019feb  mov     rax, [rdi+18h]
0x180019fef  mov     [rbp+var_40], rax
0x180019ff3  mov     eax, [rdi]
0x180019ff5  mov     [rbp+var_7C], eax
0x180019ff8  mov     rax, [rdi+80h]
0x180019fff  mov     [rbp+var_38], rax
0x18001a003  mov     eax, [rdi+40h]
0x18001a006  mov     [rbp+var_78], eax
0x18001a009  mov     rax, [rdi+38h]
0x18001a00d  mov     [rbp+var_30], rax
0x18001a011  mov     eax, [rdi+8]
0x18001a014  mov     [rbp+var_74], eax
0x18001a017  lea     rax, [rbp+var_70]
0x18001a01b  mov     [rsp+140h+var_90], rax
0x18001a023  lea     rax, [rbp+arg_0]
0x18001a027  mov     [rsp+140h+var_98], rax
0x18001a02f  lea     rax, [rbp+arg_8]
0x18001a033  mov     [rsp+140h+var_A0], rax
0x18001a03b  lea     rax, [rbp+var_68]
0x18001a03f  mov     [rsp+140h+var_A8], rax
0x18001a047  lea     rax, [rbp+var_60]
0x18001a04b  mov     [rsp+140h+var_B0], rax
0x18001a053  lea     rax, [rbp+arg_10]
0x18001a057  mov     [rsp+140h+var_B8], rax
0x18001a05f  lea     rax, [rbp+var_58]
0x18001a063  mov     [rsp+140h+var_C0], rax
0x18001a06b  lea     rax, [rbp+var_50]
0x18001a06f  mov     [rsp+140h+var_C8], rax
0x18001a074  lea     rax, [rbp+arg_18]
0x18001a078  mov     [rsp+140h+var_D0], rax
0x18001a07d  lea     rax, [rbp+var_48]
0x18001a081  mov     [rsp+140h+var_D8], rax
0x18001a086  lea     rax, [rbp+var_80]
0x18001a08a  mov     [rsp+140h+var_E0], rax
0x18001a08f  lea     rax, [rbp+var_40]
0x18001a093  mov     [rsp+140h+var_E8], rax
0x18001a098  lea     rax, [rbp+var_7C]
0x18001a09c  mov     [rsp+140h+var_F0], rax
0x18001a0a1  lea     rax, [rbp+var_38]
0x18001a0a5  mov     [rsp+140h+var_F8], rax
0x18001a0aa  lea     rax, [rbp+var_78]
0x18001a0ae  mov     [rsp+140h+var_100], rax
0x18001a0b3  lea     rax, [rbp+var_30]
0x18001a0b7  mov     [rsp+140h+var_108], rax
0x18001a0bc  lea     rax, [rbp+var_74]
0x18001a0c0  mov     [rbp+var_70], rcx
0x18001a0c4  mov     ecx, [rdi+44h]
0x18001a0c7  mov     [rsp+140h+var_110], rax
0x18001a0cc  lea     rax, [rbp+var_28]
0x18001a0d0  mov     [rbp+arg_0], ecx
0x18001a0d3  mov     ecx, [rdi+10h]
0x18001a0d6  mov     [rbp+arg_8], ecx
0x18001a0d9  mov     rcx, [rdi+78h]
0x18001a0dd  mov     [rsp+140h+var_118], rax
0x18001a0e2  lea     rax, [rbp+var_20]
0x18001a0e6  mov     [rbp+var_68], rcx
0x18001a0ea  mov     rcx, r9
0x18001a0ed  mov     [rsp+140h+var_120], rax
0x18001a0f2  mov     [rbp+var_28], 1000000h
0x18001a0fa  mov     [rbp+var_20], 0
0x18001a102  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001a107  jmp     short loc_18001A16A
0x18001a109  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001a10e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001a113  mov     rdi, rax
0x18001a116  mov     ecx, [rax]
0x18001a118  cmp     ecx, 5
0x18001a11b  jbe     short loc_18001A16A
0x18001a11d  call    cs:__imp_GetCurrentThreadId
0x18001a123  mov     r8, [rbx+110h]
0x18001a12a  lea     rdx, unk_18002B2C8
0x18001a131  mov     [rbp+arg_0], eax
0x18001a134  lea     rax, [rbp+arg_0]
0x18001a138  mov     [rsp+140h+var_110], rax
0x18001a13d  lea     rax, [rbp+arg_8]
0x18001a141  mov     [rsp+140h+var_118], rax
0x18001a146  lea     rax, [rbp+arg_10]
0x18001a14a  mov     ecx, [r8+48h]
0x18001a14e  add     r8, 8
0x18001a152  mov     [rbp+arg_8], ecx
0x18001a155  mov     rcx, rdi
0x18001a158  mov     [rsp+140h+var_120], rax
0x18001a15d  mov     [rbp+arg_10], 0
0x18001a165  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a16a  mov     rcx, rbx
0x18001a16d  add     rsp, 130h
0x18001a174  pop     rdi
0x18001a175  pop     rbx
0x18001a176  pop     rbp
0x18001a177  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
