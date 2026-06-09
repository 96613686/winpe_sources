# LogProvider::NgcIsoGetIncrementedEphemeralCounter::StopActivity(void)

- ea: `0x140033c40`
- end: `0x140033e65`
- name: `?StopActivity@NgcIsoGetIncrementedEphemeralCounter@LogProvider@@MEAAXXZ`
- size: `549`
- prototype: `void __fastcall(LogProvider::NgcIsoGetIncrementedEphemeralCounter *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140002cc0`
- `0x140003124`
- `0x14000330c`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x140033c40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033e02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140033e02`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoGetIncrementedEphemeralCounter::StopActivity(
        LogProvider::NgcIsoGetIncrementedEphemeralCounter *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v22; // [rsp+D0h] [rbp+17h] BYREF
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
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = LogProvider::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 4u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = (__int64 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v27 = v4[26];
      v19 = (__int64 *)*((_QWORD *)v4 + 12);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v28 = v4[20];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v29) = v4[8];
      v22 = (__int64 *)*((_QWORD *)v4 + 3);
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
        (unsigned __int8 *)word_1400880BA,
        (const GUID *)(v10 + 8),
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
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LogProvider::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 4u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v27 = CurrentThreadId;
      v28 = *(_DWORD *)(v14 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&word_1400881F6,
        v14 + 8,
        0,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x140033c40  push    rbp
0x140033c42  push    rbx
0x140033c43  push    rdi
0x140033c44  lea     rbp, [rsp-47h]
0x140033c49  sub     rsp, 100h
0x140033c50  mov     rdi, [rcx+110h]
0x140033c57  mov     rbx, rcx
0x140033c5a  mov     eax, [rdi+48h]
0x140033c5d  test    eax, eax
0x140033c5f  jns     loc_140033DD8
0x140033c65  add     rdi, 50h ; 'P'
0x140033c69  cmp     eax, [rdi+8]
0x140033c6c  jnz     loc_140033DD8
0x140033c72  test    rdi, rdi
0x140033c75  jz      loc_140033DD8
0x140033c7b  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140033c80  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140033c85  mov     r9, rax
0x140033c88  mov     ecx, [rax]
0x140033c8a  cmp     ecx, 4
0x140033c8d  jbe     loc_140033E53
0x140033c93  mov     rdx, 400000000000h
0x140033c9d  mov     rcx, rax
0x140033ca0  call    _tlgKeywordOn
0x140033ca5  test    al, al
0x140033ca7  jz      loc_140033E53
0x140033cad  mov     rax, [rdi+70h]
0x140033cb1  lea     rdx, word_1400880BA
0x140033cb8  mov     rcx, [rdi+78h]
0x140033cbc  mov     r8, [rbx+110h]
0x140033cc3  mov     [rbp+57h+var_60], rax
0x140033cc7  add     r8, 8
0x140033ccb  mov     eax, [rdi+68h]
0x140033cce  mov     [rbp+57h+arg_0], eax
0x140033cd1  mov     rax, [rdi+60h]
0x140033cd5  mov     [rbp+57h+var_58], rax
0x140033cd9  mov     rax, [rdi+58h]
0x140033cdd  mov     [rbp+57h+var_50], rax
0x140033ce1  mov     eax, [rdi+50h]
0x140033ce4  mov     [rbp+57h+arg_8], eax
0x140033ce7  mov     rax, [rdi+48h]
0x140033ceb  mov     [rbp+57h+var_48], rax
0x140033cef  mov     eax, [rdi+20h]
0x140033cf2  mov     dword ptr [rbp+57h+arg_10], eax
0x140033cf5  mov     rax, [rdi+18h]
0x140033cf9  mov     [rbp+57h+var_40], rax
0x140033cfd  mov     eax, [rdi]
0x140033cff  mov     [rbp+57h+arg_18], eax
0x140033d02  mov     rax, [rdi+80h]
0x140033d09  mov     [rbp+57h+var_38], rax
0x140033d0d  mov     eax, [rdi+40h]
0x140033d10  mov     [rbp+57h+var_70], eax
0x140033d13  mov     rax, [rdi+38h]
0x140033d17  mov     [rbp+57h+var_30], rax
0x140033d1b  mov     eax, [rdi+8]
0x140033d1e  mov     [rbp+57h+var_6C], eax
0x140033d21  mov     eax, 1000000h
0x140033d26  mov     [rbp+57h+var_28], rax
0x140033d2a  mov     [rbp+57h+var_20], rax
0x140033d2e  lea     rax, [rbp+57h+var_68]
0x140033d32  mov     [rsp+110h+var_78], rax
0x140033d3a  lea     rax, [rbp+57h+var_60]
0x140033d3e  mov     [rsp+110h+var_80], rax
0x140033d46  lea     rax, [rbp+57h+arg_0]
0x140033d4a  mov     [rsp+110h+var_88], rax
0x140033d52  lea     rax, [rbp+57h+var_58]
0x140033d56  mov     [rsp+110h+var_90], rax
0x140033d5e  lea     rax, [rbp+57h+var_50]
0x140033d62  mov     [rsp+110h+var_98], rax
0x140033d67  lea     rax, [rbp+57h+arg_8]
0x140033d6b  mov     [rsp+110h+var_A0], rax
0x140033d70  lea     rax, [rbp+57h+var_48]
0x140033d74  mov     [rsp+110h+var_A8], rax
0x140033d79  lea     rax, [rbp+57h+arg_10]
0x140033d7d  mov     [rsp+110h+var_B0], rax
0x140033d82  lea     rax, [rbp+57h+var_40]
0x140033d86  mov     [rsp+110h+var_B8], rax
0x140033d8b  lea     rax, [rbp+57h+arg_18]
0x140033d8f  mov     [rsp+110h+var_C0], rax
0x140033d94  lea     rax, [rbp+57h+var_38]
0x140033d98  mov     [rsp+110h+var_C8], rax
0x140033d9d  lea     rax, [rbp+57h+var_70]
0x140033da1  mov     [rsp+110h+var_D0], rax
0x140033da6  lea     rax, [rbp+57h+var_30]
0x140033daa  mov     [rsp+110h+var_D8], rax
0x140033daf  lea     rax, [rbp+57h+var_6C]
0x140033db3  mov     [rsp+110h+var_E0], rax
0x140033db8  lea     rax, [rbp+57h+var_28]
0x140033dbc  mov     [rsp+110h+var_E8], rax
0x140033dc1  lea     rax, [rbp+57h+var_20]
0x140033dc5  mov     [rbp+57h+var_68], rcx
0x140033dc9  mov     rcx, r9
0x140033dcc  mov     [rsp+110h+var_F0], rax
0x140033dd1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140033dd6  jmp     short loc_140033E53
0x140033dd8  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140033ddd  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140033de2  mov     rdi, rax
0x140033de5  mov     ecx, [rax]
0x140033de7  cmp     ecx, 4
0x140033dea  jbe     short loc_140033E53
0x140033dec  mov     rdx, 400000000000h
0x140033df6  mov     rcx, rax
0x140033df9  call    _tlgKeywordOn
0x140033dfe  test    al, al
0x140033e00  jz      short loc_140033E53
0x140033e02  call    cs:__imp_GetCurrentThreadId
0x140033e08  mov     r8, [rbx+110h]
0x140033e0f  lea     rdx, word_1400881F6
0x140033e16  mov     [rbp+57h+arg_0], eax
0x140033e19  xor     r9d, r9d
0x140033e1c  mov     rcx, rdi
0x140033e1f  mov     eax, [r8+48h]
0x140033e23  add     r8, 8
0x140033e27  mov     [rbp+57h+arg_8], eax
0x140033e2a  mov     eax, 1000000h
0x140033e2f  mov     [rbp+57h+arg_10], rax
0x140033e33  lea     rax, [rbp+57h+arg_0]
0x140033e37  mov     [rsp+110h+var_E0], rax
0x140033e3c  lea     rax, [rbp+57h+arg_8]
0x140033e40  mov     [rsp+110h+var_E8], rax
0x140033e45  lea     rax, [rbp+57h+arg_10]
0x140033e49  mov     [rsp+110h+var_F0], rax
0x140033e4e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140033e53  mov     rcx, rbx
0x140033e56  add     rsp, 100h
0x140033e5d  pop     rdi
0x140033e5e  pop     rbx
0x140033e5f  pop     rbp
0x140033e60  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
