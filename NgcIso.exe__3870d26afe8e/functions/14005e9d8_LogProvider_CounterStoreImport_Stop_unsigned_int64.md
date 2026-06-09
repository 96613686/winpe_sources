# LogProvider::CounterStoreImport::Stop(unsigned __int64)

- ea: `0x14005e9d8`
- end: `0x14005ec29`
- name: `?Stop@CounterStoreImport@LogProvider@@QEAAX_K@Z`
- size: `593`
- prototype: `void __fastcall(LogProvider::CounterStoreImport *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14005db3c`

## callees

- `0x140001fc0`
- `0x14000330c`
- `0x1400036d4`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14005e9d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005ebb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005ebb8`

## pseudocode

```c
void __fastcall LogProvider::CounterStoreImport::Stop(LogProvider::CounterStoreImport *this, __int64 a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // r9
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  int v19; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v20; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+100h] [rbp-30h] BYREF
  __int64 v29; // [rsp+108h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+110h] [rbp-20h] BYREF
  DWORD v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+150h] [rbp+20h] BYREF
  __int64 v33; // [rsp+158h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = LogProvider::Provider();
    v10 = v7;
    if ( *(_DWORD *)v7 > 4u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v22 = *((_QWORD *)v6 + 15);
      v11 = *((_QWORD *)this + 34);
      v23 = *((_QWORD *)v6 + 14);
      v31 = v6[26];
      v24 = *((_QWORD *)v6 + 12);
      v25 = *((_QWORD *)v6 + 11);
      v32 = v6[20];
      v26 = *((_QWORD *)v6 + 9);
      LODWORD(v33) = v6[8];
      v27 = *((_QWORD *)v6 + 3);
      v17 = *v6;
      v28 = *((_QWORD *)v6 + 16);
      v18 = v6[16];
      v29 = *((_QWORD *)v6 + 7);
      v19 = v6[2];
      v30[0] = 0x1000000;
      v20 = 0x1000000;
      v21 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        (_DWORD)v10,
        (unsigned int)&unk_14008F040,
        v11 + 8,
        (_DWORD)v10,
        (__int64)&v20,
        (__int64)v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v17,
        (__int64)&v27,
        (__int64)&v33,
        (__int64)&v26,
        (__int64)&v32,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LogProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 4u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
    {
      v33 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v31 = CurrentThreadId;
      v32 = *(_DWORD *)(v15 + 72);
      v20 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v13,
        (unsigned int)byte_14008EFE1,
        v15 + 8,
        v16,
        (__int64)&v20,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v33);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v8,
    v9,
    v10);
}

```

## disassembly

```asm
0x14005e9d8  mov     [rsp-8+arg_8], rbx
0x14005e9dd  push    rbp
0x14005e9de  push    rsi
0x14005e9df  push    rdi
0x14005e9e0  lea     rbp, [rsp+10h]
0x14005e9e5  sub     rsp, 120h
0x14005e9ec  mov     rdi, [rcx+110h]
0x14005e9f3  mov     rsi, rdx
0x14005e9f6  mov     rbx, rcx
0x14005e9f9  mov     eax, [rdi+48h]
0x14005e9fc  test    eax, eax
0x14005e9fe  jns     loc_14005EB8A
0x14005ea04  add     rdi, 50h ; 'P'
0x14005ea08  cmp     eax, [rdi+8]
0x14005ea0b  jnz     loc_14005EB8A
0x14005ea11  test    rdi, rdi
0x14005ea14  jz      loc_14005EB8A
0x14005ea1a  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005ea1f  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005ea24  mov     r9, rax
0x14005ea27  mov     ecx, [rax]
0x14005ea29  cmp     ecx, 4
0x14005ea2c  jbe     loc_14005EC0F
0x14005ea32  mov     rdx, 400000000000h
0x14005ea3c  mov     rcx, rax
0x14005ea3f  call    _tlgKeywordOn
0x14005ea44  test    al, al
0x14005ea46  jz      loc_14005EC0F
0x14005ea4c  mov     rax, [rdi+78h]
0x14005ea50  lea     rdx, unk_14008F040
0x14005ea57  mov     [rbp+var_60], rax
0x14005ea5b  mov     rcx, r9
0x14005ea5e  mov     rax, [rdi+70h]
0x14005ea62  mov     r8, [rbx+110h]
0x14005ea69  mov     [rbp+var_58], rax
0x14005ea6d  add     r8, 8
0x14005ea71  mov     eax, [rdi+68h]
0x14005ea74  mov     [rbp+arg_0], eax
0x14005ea77  mov     rax, [rdi+60h]
0x14005ea7b  mov     [rbp+var_50], rax
0x14005ea7f  mov     rax, [rdi+58h]
0x14005ea83  mov     [rbp+var_48], rax
0x14005ea87  mov     eax, [rdi+50h]
0x14005ea8a  mov     [rbp+arg_10], eax
0x14005ea8d  mov     rax, [rdi+48h]
0x14005ea91  mov     [rbp+var_40], rax
0x14005ea95  mov     eax, [rdi+20h]
0x14005ea98  mov     dword ptr [rbp+arg_18], eax
0x14005ea9b  mov     rax, [rdi+18h]
0x14005ea9f  mov     [rbp+var_38], rax
0x14005eaa3  mov     eax, [rdi]
0x14005eaa5  mov     [rbp+var_80], eax
0x14005eaa8  mov     rax, [rdi+80h]
0x14005eaaf  mov     [rbp+var_30], rax
0x14005eab3  mov     eax, [rdi+40h]
0x14005eab6  mov     [rbp+var_7C], eax
0x14005eab9  mov     rax, [rdi+38h]
0x14005eabd  mov     [rbp+var_28], rax
0x14005eac1  mov     eax, [rdi+8]
0x14005eac4  mov     [rbp+var_78], eax
0x14005eac7  mov     eax, 1000000h
0x14005eacc  mov     [rbp+var_20], rax
0x14005ead0  mov     [rbp+var_70], rax
0x14005ead4  lea     rax, [rbp+var_68]
0x14005ead8  mov     [rsp+130h+var_90], rax
0x14005eae0  lea     rax, [rbp+var_60]
0x14005eae4  mov     [rsp+130h+var_98], rax
0x14005eaec  lea     rax, [rbp+var_58]
0x14005eaf0  mov     [rsp+130h+var_A0], rax
0x14005eaf8  lea     rax, [rbp+arg_0]
0x14005eafc  mov     [rsp+130h+var_A8], rax
0x14005eb04  lea     rax, [rbp+var_50]
0x14005eb08  mov     [rsp+130h+var_B0], rax
0x14005eb10  lea     rax, [rbp+var_48]
0x14005eb14  mov     [rsp+130h+var_B8], rax
0x14005eb19  lea     rax, [rbp+arg_10]
0x14005eb1d  mov     [rsp+130h+var_C0], rax
0x14005eb22  lea     rax, [rbp+var_40]
0x14005eb26  mov     [rsp+130h+var_C8], rax
0x14005eb2b  lea     rax, [rbp+arg_18]
0x14005eb2f  mov     [rsp+130h+var_D0], rax
0x14005eb34  lea     rax, [rbp+var_38]
0x14005eb38  mov     [rsp+130h+var_D8], rax
0x14005eb3d  lea     rax, [rbp+var_80]
0x14005eb41  mov     [rsp+130h+var_E0], rax
0x14005eb46  lea     rax, [rbp+var_30]
0x14005eb4a  mov     [rsp+130h+var_E8], rax
0x14005eb4f  lea     rax, [rbp+var_7C]
0x14005eb53  mov     [rsp+130h+var_F0], rax
0x14005eb58  lea     rax, [rbp+var_28]
0x14005eb5c  mov     [rsp+130h+var_F8], rax
0x14005eb61  lea     rax, [rbp+var_78]
0x14005eb65  mov     [rsp+130h+var_100], rax
0x14005eb6a  lea     rax, [rbp+var_20]
0x14005eb6e  mov     [rsp+130h+var_108], rax
0x14005eb73  lea     rax, [rbp+var_70]
0x14005eb77  mov     [rsp+130h+var_110], rax
0x14005eb7c  mov     [rbp+var_68], rsi
0x14005eb80  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564563@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14005eb85  jmp     loc_14005EC0F
0x14005eb8a  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005eb8f  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005eb94  mov     rdi, rax
0x14005eb97  mov     ecx, [rax]
0x14005eb99  cmp     ecx, 4
0x14005eb9c  jbe     short loc_14005EC0F
0x14005eb9e  mov     rdx, 400000000000h
0x14005eba8  mov     rcx, rax
0x14005ebab  call    _tlgKeywordOn
0x14005ebb0  test    al, al
0x14005ebb2  jz      short loc_14005EC0F
0x14005ebb4  mov     [rbp+arg_18], rsi
0x14005ebb8  call    cs:__imp_GetCurrentThreadId
0x14005ebbe  mov     r8, [rbx+110h]
0x14005ebc5  lea     rdx, byte_14008EFE1
0x14005ebcc  mov     [rbp+arg_0], eax
0x14005ebcf  mov     rcx, rdi
0x14005ebd2  mov     eax, [r8+48h]
0x14005ebd6  add     r8, 8
0x14005ebda  mov     [rbp+arg_10], eax
0x14005ebdd  mov     eax, 1000000h
0x14005ebe2  mov     [rbp+var_70], rax
0x14005ebe6  lea     rax, [rbp+arg_18]
0x14005ebea  mov     [rsp+130h+var_F8], rax
0x14005ebef  lea     rax, [rbp+arg_0]
0x14005ebf3  mov     [rsp+130h+var_100], rax
0x14005ebf8  lea     rax, [rbp+arg_10]
0x14005ebfc  mov     [rsp+130h+var_108], rax
0x14005ec01  lea     rax, [rbp+var_70]
0x14005ec05  mov     [rsp+130h+var_110], rax
0x14005ec0a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14005ec0f  mov     rcx, rbx
0x14005ec12  mov     rbx, [rsp+130h+arg_8]
0x14005ec1a  add     rsp, 120h
0x14005ec21  pop     rdi
0x14005ec22  pop     rsi
0x14005ec23  pop     rbp
0x14005ec24  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
