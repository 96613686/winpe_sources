# NetworkLegacyUxTelemetry::NetworkExplorerOpen::StopActivity(void)

- ea: `0x18000bb90`
- end: `0x18000bdb4`
- name: `?StopActivity@NetworkExplorerOpen@NetworkLegacyUxTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(NetworkLegacyUxTelemetry::NetworkExplorerOpen *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800010a8`
- `0x18000135c`
- `0x1800019ac`
- `0x18000a1b4`
- `0x18000ac88`
- `0x18000bb90`
- `0x18000db10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bd55`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bd55`

## pseudocode

```c
void __fastcall NetworkLegacyUxTelemetry::NetworkExplorerOpen::StopActivity(
        NetworkLegacyUxTelemetry::NetworkExplorerOpen *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // r9
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v18; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v20; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v21; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = NetworkLegacyUxLogging::Provider();
    v8 = v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v9 = *((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = *((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = *((_QWORD *)v4 + 12);
      v21 = *((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = *((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = *((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v8,
        (unsigned int)word_180014BD2,
        v10 + 8,
        (_DWORD)v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        (__int64)&v25,
        (__int64)&v16,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = NetworkLegacyUxLogging::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&word_180014B7E,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x18000bb90  push    rbp
0x18000bb92  push    rbx
0x18000bb93  push    rdi
0x18000bb94  lea     rbp, [rsp-47h]
0x18000bb99  sub     rsp, 100h
0x18000bba0  mov     rdi, [rcx+110h]
0x18000bba7  mov     rbx, rcx
0x18000bbaa  mov     eax, [rdi+48h]
0x18000bbad  test    eax, eax
0x18000bbaf  jns     loc_18000BD2B
0x18000bbb5  add     rdi, 50h ; 'P'
0x18000bbb9  cmp     eax, [rdi+8]
0x18000bbbc  jnz     loc_18000BD2B
0x18000bbc2  test    rdi, rdi
0x18000bbc5  jz      loc_18000BD2B
0x18000bbcb  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000bbd0  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000bbd5  mov     r9, rax
0x18000bbd8  mov     ecx, [rax]
0x18000bbda  cmp     ecx, 5
0x18000bbdd  jbe     loc_18000BDA2
0x18000bbe3  mov     rdx, 400000000000h
0x18000bbed  mov     rcx, rax
0x18000bbf0  call    _tlgKeywordOn
0x18000bbf5  test    al, al
0x18000bbf7  jz      loc_18000BDA2
0x18000bbfd  mov     rax, [rdi+70h]
0x18000bc01  lea     rdx, word_180014BD2
0x18000bc08  mov     rcx, [rdi+78h]
0x18000bc0c  mov     r8, [rbx+110h]
0x18000bc13  mov     [rbp+57h+var_60], rax
0x18000bc17  add     r8, 8
0x18000bc1b  mov     eax, [rdi+68h]
0x18000bc1e  mov     [rbp+57h+arg_0], eax
0x18000bc21  mov     rax, [rdi+60h]
0x18000bc25  mov     [rbp+57h+var_58], rax
0x18000bc29  mov     rax, [rdi+58h]
0x18000bc2d  mov     [rbp+57h+var_50], rax
0x18000bc31  mov     eax, [rdi+50h]
0x18000bc34  mov     [rbp+57h+arg_8], eax
0x18000bc37  mov     rax, [rdi+48h]
0x18000bc3b  mov     [rbp+57h+var_48], rax
0x18000bc3f  mov     eax, [rdi+20h]
0x18000bc42  mov     dword ptr [rbp+57h+arg_10], eax
0x18000bc45  mov     rax, [rdi+18h]
0x18000bc49  mov     [rbp+57h+var_40], rax
0x18000bc4d  mov     eax, [rdi]
0x18000bc4f  mov     [rbp+57h+arg_18], eax
0x18000bc52  mov     rax, [rdi+80h]
0x18000bc59  mov     [rbp+57h+var_38], rax
0x18000bc5d  mov     eax, [rdi+40h]
0x18000bc60  mov     [rbp+57h+var_70], eax
0x18000bc63  mov     rax, [rdi+38h]
0x18000bc67  mov     [rbp+57h+var_30], rax
0x18000bc6b  mov     eax, [rdi+8]
0x18000bc6e  mov     [rbp+57h+var_6C], eax
0x18000bc71  lea     rax, [rbp+57h+var_68]
0x18000bc75  mov     [rsp+110h+var_78], rax
0x18000bc7d  lea     rax, [rbp+57h+var_60]
0x18000bc81  mov     [rsp+110h+var_80], rax
0x18000bc89  lea     rax, [rbp+57h+arg_0]
0x18000bc8d  mov     [rsp+110h+var_88], rax
0x18000bc95  lea     rax, [rbp+57h+var_58]
0x18000bc99  mov     [rsp+110h+var_90], rax
0x18000bca1  lea     rax, [rbp+57h+var_50]
0x18000bca5  mov     [rsp+110h+var_98], rax
0x18000bcaa  lea     rax, [rbp+57h+arg_8]
0x18000bcae  mov     [rsp+110h+var_A0], rax
0x18000bcb3  lea     rax, [rbp+57h+var_48]
0x18000bcb7  mov     [rsp+110h+var_A8], rax
0x18000bcbc  lea     rax, [rbp+57h+arg_10]
0x18000bcc0  mov     [rsp+110h+var_B0], rax
0x18000bcc5  lea     rax, [rbp+57h+var_40]
0x18000bcc9  mov     [rsp+110h+var_B8], rax
0x18000bcce  lea     rax, [rbp+57h+arg_18]
0x18000bcd2  mov     [rsp+110h+var_C0], rax
0x18000bcd7  lea     rax, [rbp+57h+var_38]
0x18000bcdb  mov     [rsp+110h+var_C8], rax
0x18000bce0  lea     rax, [rbp+57h+var_70]
0x18000bce4  mov     [rsp+110h+var_D0], rax
0x18000bce9  lea     rax, [rbp+57h+var_30]
0x18000bced  mov     [rsp+110h+var_D8], rax
0x18000bcf2  lea     rax, [rbp+57h+var_6C]
0x18000bcf6  mov     [rsp+110h+var_E0], rax
0x18000bcfb  lea     rax, [rbp+57h+var_28]
0x18000bcff  mov     [rsp+110h+var_E8], rax
0x18000bd04  lea     rax, [rbp+57h+var_20]
0x18000bd08  mov     [rbp+57h+var_68], rcx
0x18000bd0c  mov     rcx, r9
0x18000bd0f  mov     [rsp+110h+var_F0], rax
0x18000bd14  mov     [rbp+57h+var_28], 1000000h
0x18000bd1c  mov     [rbp+57h+var_20], 0
0x18000bd24  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000bd29  jmp     short loc_18000BDA2
0x18000bd2b  call    ?zInternalStop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000bd30  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000bd35  mov     rdi, rax
0x18000bd38  mov     ecx, [rax]
0x18000bd3a  cmp     ecx, 5
0x18000bd3d  jbe     short loc_18000BDA2
0x18000bd3f  mov     rdx, 400000000000h
0x18000bd49  mov     rcx, rax
0x18000bd4c  call    _tlgKeywordOn
0x18000bd51  test    al, al
0x18000bd53  jz      short loc_18000BDA2
0x18000bd55  call    cs:__imp_GetCurrentThreadId
0x18000bd5b  mov     r8, [rbx+110h]
0x18000bd62  lea     rdx, word_180014B7E
0x18000bd69  mov     [rbp+57h+arg_0], eax
0x18000bd6c  mov     rcx, rdi
0x18000bd6f  mov     eax, [r8+48h]
0x18000bd73  add     r8, 8
0x18000bd77  mov     [rbp+57h+arg_8], eax
0x18000bd7a  lea     rax, [rbp+57h+arg_0]
0x18000bd7e  mov     [rsp+110h+var_E0], rax
0x18000bd83  lea     rax, [rbp+57h+arg_8]
0x18000bd87  mov     [rsp+110h+var_E8], rax
0x18000bd8c  lea     rax, [rbp+57h+arg_10]
0x18000bd90  mov     [rsp+110h+var_F0], rax
0x18000bd95  mov     [rbp+57h+arg_10], 0
0x18000bd9d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000bda2  mov     rcx, rbx
0x18000bda5  add     rsp, 100h
0x18000bdac  pop     rdi
0x18000bdad  pop     rbx
0x18000bdae  pop     rbp
0x18000bdaf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
