# wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x1800189b4`
- end: `0x180018bf9`
- name: `?ReportStopActivity@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800183c8`
- `0x180018e10`

## callees

- `0x18000182c`
- `0x180001fb4`
- `0x1800020b0`
- `0x18000719c`
- `0x1800189b4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018b84`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  int v8; // r9d
  __int64 v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  __int64 v13; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v20; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v21; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v23; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v24; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v25; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v26; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v27; // [rsp+E0h] [rbp+27h] BYREF
  _QWORD v28[5]; // [rsp+E8h] [rbp+2Fh] BYREF
  int v29; // [rsp+120h] [rbp+67h] BYREF
  DWORD v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  __int64 v32; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = StateRepository::Tracing::Client::Provider();
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
      {
        v9 = *(_QWORD *)(v6 + 120);
        v10 = a1[34];
        v22 = *(_QWORD *)(v6 + 112);
        v30 = *(_DWORD *)(v6 + 104);
        v23 = *(_QWORD *)(v6 + 96);
        v24 = *(_QWORD *)(v6 + 88);
        v29 = *(_DWORD *)(v6 + 80);
        v25 = *(_QWORD *)(v6 + 72);
        LODWORD(v31) = *(_DWORD *)(v6 + 32);
        v26 = *(_QWORD *)(v6 + 24);
        LODWORD(v32) = *(_DWORD *)v6;
        v27 = *(_QWORD *)(v6 + 128);
        v18 = *(_DWORD *)(v6 + 64);
        v28[0] = *(_QWORD *)(v6 + 56);
        v19 = *(_DWORD *)(v6 + 8);
        v21 = v9;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v8,
          (unsigned int)word_1800305E2,
          v10 + 8,
          v8,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v28,
          (__int64)&v18,
          (__int64)&v27,
          (__int64)&v32,
          (__int64)&v26,
          (__int64)&v31,
          (__int64)&v25,
          (__int64)&v29,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v30,
          (__int64)&v22,
          (__int64)&v21);
      }
    }
    else
    {
      v11 = StateRepository::Tracing::Client::Provider();
      v12 = (int)v11;
      if ( *(_DWORD *)v11 > 2u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
      {
        v13 = a1[34];
        v31 = *(_QWORD *)(v13 + 56);
        v32 = *(_QWORD *)(v13 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v15 = a1[34];
        v30 = CurrentThreadId;
        v29 = a2;
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)byte_1800306F9,
          v15 + 8,
          v16,
          (__int64)&v20,
          (__int64)&v29,
          (__int64)&v30,
          (__int64)&v32,
          (__int64)&v31);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x1800189b4  push    rbp
0x1800189b6  push    rbx
0x1800189b7  push    rsi
0x1800189b8  push    rdi
0x1800189b9  lea     rbp, [rsp-3Fh]
0x1800189be  sub     rsp, 0F8h
0x1800189c5  mov     esi, edx
0x1800189c7  mov     rbx, rcx
0x1800189ca  test    edx, edx
0x1800189cc  jns     loc_180018BDF
0x1800189d2  mov     rdi, [rcx+110h]
0x1800189d9  mov     eax, [rdi+48h]
0x1800189dc  test    eax, eax
0x1800189de  jns     loc_180018B44
0x1800189e4  add     rdi, 50h ; 'P'
0x1800189e8  cmp     eax, [rdi+8]
0x1800189eb  jnz     loc_180018B44
0x1800189f1  test    rdi, rdi
0x1800189f4  jz      loc_180018B44
0x1800189fa  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x1800189ff  mov     r9, rax
0x180018a02  mov     ecx, [rax]
0x180018a04  cmp     ecx, 2
0x180018a07  jbe     loc_180018BDF
0x180018a0d  mov     rdx, 200000000000h
0x180018a17  mov     rcx, rax
0x180018a1a  call    _tlgKeywordOn
0x180018a1f  test    al, al
0x180018a21  jz      loc_180018BDF
0x180018a27  mov     rax, [rdi+70h]
0x180018a2b  lea     rdx, word_1800305E2
0x180018a32  mov     rcx, [rdi+78h]
0x180018a36  mov     r8, [rbx+110h]
0x180018a3d  mov     [rbp+57h+var_58], rax
0x180018a41  add     r8, 8
0x180018a45  mov     eax, [rdi+68h]
0x180018a48  mov     [rbp+57h+arg_8], eax
0x180018a4b  mov     rax, [rdi+60h]
0x180018a4f  mov     [rbp+57h+var_50], rax
0x180018a53  mov     rax, [rdi+58h]
0x180018a57  mov     [rbp+57h+var_48], rax
0x180018a5b  mov     eax, [rdi+50h]
0x180018a5e  mov     [rbp+57h+arg_0], eax
0x180018a61  mov     rax, [rdi+48h]
0x180018a65  mov     [rbp+57h+var_40], rax
0x180018a69  mov     eax, [rdi+20h]
0x180018a6c  mov     dword ptr [rbp+57h+arg_10], eax
0x180018a6f  mov     rax, [rdi+18h]
0x180018a73  mov     [rbp+57h+var_38], rax
0x180018a77  mov     eax, [rdi]
0x180018a79  mov     dword ptr [rbp+57h+arg_18], eax
0x180018a7c  mov     rax, [rdi+80h]
0x180018a83  mov     [rbp+57h+var_30], rax
0x180018a87  mov     eax, [rdi+40h]
0x180018a8a  mov     [rbp+57h+var_70], eax
0x180018a8d  mov     rax, [rdi+38h]
0x180018a91  mov     [rbp+57h+var_28], rax
0x180018a95  mov     eax, [rdi+8]
0x180018a98  mov     [rbp+57h+var_6C], eax
0x180018a9b  lea     rax, [rbp+57h+var_60]
0x180018a9f  mov     [rsp+110h+var_80], rax
0x180018aa7  lea     rax, [rbp+57h+var_58]
0x180018aab  mov     [rsp+110h+var_88], rax
0x180018ab3  lea     rax, [rbp+57h+arg_8]
0x180018ab7  mov     [rsp+110h+var_90], rax
0x180018abf  lea     rax, [rbp+57h+var_50]
0x180018ac3  mov     [rsp+110h+var_98], rax
0x180018ac8  lea     rax, [rbp+57h+var_48]
0x180018acc  mov     [rsp+110h+var_A0], rax
0x180018ad1  lea     rax, [rbp+57h+arg_0]
0x180018ad5  mov     [rsp+110h+var_A8], rax
0x180018ada  lea     rax, [rbp+57h+var_40]
0x180018ade  mov     [rsp+110h+var_B0], rax
0x180018ae3  lea     rax, [rbp+57h+arg_10]
0x180018ae7  mov     [rsp+110h+var_B8], rax
0x180018aec  lea     rax, [rbp+57h+var_38]
0x180018af0  mov     [rsp+110h+var_C0], rax
0x180018af5  lea     rax, [rbp+57h+arg_18]
0x180018af9  mov     [rsp+110h+var_C8], rax
0x180018afe  lea     rax, [rbp+57h+var_30]
0x180018b02  mov     [rsp+110h+var_D0], rax
0x180018b07  lea     rax, [rbp+57h+var_70]
0x180018b0b  mov     [rsp+110h+var_D8], rax
0x180018b10  lea     rax, [rbp+57h+var_28]
0x180018b14  mov     [rsp+110h+var_E0], rax
0x180018b19  lea     rax, [rbp+57h+var_6C]
0x180018b1d  mov     [rsp+110h+var_E8], rax
0x180018b22  lea     rax, [rbp+57h+var_68]
0x180018b26  mov     [rbp+57h+var_60], rcx
0x180018b2a  mov     rcx, r9
0x180018b2d  mov     [rsp+110h+var_F0], rax
0x180018b32  mov     [rbp+57h+var_68], 1000000h
0x180018b3a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180018b3f  jmp     loc_180018BDF
0x180018b44  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x180018b49  mov     rdi, rax
0x180018b4c  mov     ecx, [rax]
0x180018b4e  cmp     ecx, 2
0x180018b51  jbe     loc_180018BDF
0x180018b57  mov     rdx, 200000000000h
0x180018b61  mov     rcx, rax
0x180018b64  call    _tlgKeywordOn
0x180018b69  test    al, al
0x180018b6b  jz      short loc_180018BDF
0x180018b6d  mov     rcx, [rbx+110h]
0x180018b74  mov     rax, [rcx+38h]
0x180018b78  mov     [rbp+57h+arg_10], rax
0x180018b7c  mov     rax, [rcx+30h]
0x180018b80  mov     [rbp+57h+arg_18], rax
0x180018b84  call    cs:__imp_GetCurrentThreadId
0x180018b8a  mov     r8, [rbx+110h]
0x180018b91  lea     rdx, byte_1800306F9
0x180018b98  mov     [rbp+57h+arg_8], eax
0x180018b9b  add     r8, 8
0x180018b9f  lea     rax, [rbp+57h+arg_10]
0x180018ba3  mov     [rbp+57h+arg_0], esi
0x180018ba6  mov     [rsp+110h+var_D0], rax
0x180018bab  mov     rcx, rdi
0x180018bae  lea     rax, [rbp+57h+arg_18]
0x180018bb2  mov     [rbp+57h+var_68], 1000000h
0x180018bba  mov     [rsp+110h+var_D8], rax
0x180018bbf  lea     rax, [rbp+57h+arg_8]
0x180018bc3  mov     [rsp+110h+var_E0], rax
0x180018bc8  lea     rax, [rbp+57h+arg_0]
0x180018bcc  mov     [rsp+110h+var_E8], rax
0x180018bd1  lea     rax, [rbp+57h+var_68]
0x180018bd5  mov     [rsp+110h+var_F0], rax
0x180018bda  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180018bdf  mov     rax, [rbx]
0x180018be2  mov     rcx, rbx
0x180018be5  mov     rax, [rax+8]
0x180018be9  add     rsp, 0F8h
0x180018bf0  pop     rdi
0x180018bf1  pop     rsi
0x180018bf2  pop     rbx
0x180018bf3  pop     rbp
0x180018bf4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
