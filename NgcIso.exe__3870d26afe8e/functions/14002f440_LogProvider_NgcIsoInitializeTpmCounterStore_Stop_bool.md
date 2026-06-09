# LogProvider::NgcIsoInitializeTpmCounterStore::Stop(bool)

- ea: `0x14002f440`
- end: `0x14002f691`
- name: `?Stop@NgcIsoInitializeTpmCounterStore@LogProvider@@QEAAX_N@Z`
- size: `593`
- prototype: `void __fastcall(LogProvider::NgcIsoInitializeTpmCounterStore *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400286d0`

## callees

- `0x140002284`
- `0x14000330c`
- `0x140003484`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14002f440`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002f620`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002f620`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoInitializeTpmCounterStore::Stop(
        LogProvider::NgcIsoInitializeTpmCounterStore *this,
        char a2)
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
  int v20; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v21; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v22; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v25; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v26; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v27; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v29; // [rsp+100h] [rbp-30h] BYREF
  __int64 v30[3]; // [rsp+108h] [rbp-28h] BYREF
  char v31; // [rsp+130h] [rbp+0h] BYREF
  DWORD v32; // [rsp+140h] [rbp+10h] BYREF
  int v33; // [rsp+148h] [rbp+18h] BYREF

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
      v32 = v6[26];
      v24 = *((_QWORD *)v6 + 12);
      v25 = *((_QWORD *)v6 + 11);
      v33 = v6[20];
      v26 = *((_QWORD *)v6 + 9);
      v17 = v6[8];
      v27 = *((_QWORD *)v6 + 3);
      v18 = *v6;
      v28 = *((_QWORD *)v6 + 16);
      v19 = v6[16];
      v29 = *((_QWORD *)v6 + 7);
      v20 = v6[2];
      v30[0] = 0x1000000;
      v21 = 0x1000000;
      v31 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
        (_DWORD)v10,
        (unsigned int)byte_140085D79,
        v11 + 8,
        (_DWORD)v10,
        (__int64)&v21,
        (__int64)v30,
        (__int64)&v20,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v33,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v32,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v31);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LogProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 4u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL) )
    {
      v31 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v32 = CurrentThreadId;
      v33 = *(_DWORD *)(v15 + 72);
      v21 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        v13,
        (unsigned int)byte_140085ECD,
        v15 + 8,
        v16,
        (__int64)&v21,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
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
0x14002f440  mov     [rsp-8+arg_8], rbx
0x14002f445  push    rbp
0x14002f446  push    rsi
0x14002f447  push    rdi
0x14002f448  lea     rbp, [rsp+20h]
0x14002f44d  sub     rsp, 110h
0x14002f454  mov     rdi, [rcx+110h]
0x14002f45b  mov     sil, dl
0x14002f45e  mov     rbx, rcx
0x14002f461  mov     eax, [rdi+48h]
0x14002f464  test    eax, eax
0x14002f466  jns     loc_14002F5F2
0x14002f46c  add     rdi, 50h ; 'P'
0x14002f470  cmp     eax, [rdi+8]
0x14002f473  jnz     loc_14002F5F2
0x14002f479  test    rdi, rdi
0x14002f47c  jz      loc_14002F5F2
0x14002f482  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002f487  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002f48c  mov     r9, rax
0x14002f48f  mov     ecx, [rax]
0x14002f491  cmp     ecx, 4
0x14002f494  jbe     loc_14002F677
0x14002f49a  mov     rdx, 400000000000h
0x14002f4a4  mov     rcx, rax
0x14002f4a7  call    _tlgKeywordOn
0x14002f4ac  test    al, al
0x14002f4ae  jz      loc_14002F677
0x14002f4b4  mov     rax, [rdi+78h]
0x14002f4b8  lea     rdx, byte_140085D79
0x14002f4bf  mov     [rbp-10h+var_58], rax
0x14002f4c3  mov     rcx, r9
0x14002f4c6  mov     rax, [rdi+70h]
0x14002f4ca  mov     r8, [rbx+110h]
0x14002f4d1  mov     [rbp-10h+var_50], rax
0x14002f4d5  add     r8, 8
0x14002f4d9  mov     eax, [rdi+68h]
0x14002f4dc  mov     [rbp-10h+arg_10], eax
0x14002f4df  mov     rax, [rdi+60h]
0x14002f4e3  mov     [rbp-10h+var_48], rax
0x14002f4e7  mov     rax, [rdi+58h]
0x14002f4eb  mov     [rbp-10h+var_40], rax
0x14002f4ef  mov     eax, [rdi+50h]
0x14002f4f2  mov     [rbp-10h+arg_18], eax
0x14002f4f5  mov     rax, [rdi+48h]
0x14002f4f9  mov     [rbp-10h+var_38], rax
0x14002f4fd  mov     eax, [rdi+20h]
0x14002f500  mov     [rbp-10h+var_70], eax
0x14002f503  mov     rax, [rdi+18h]
0x14002f507  mov     [rbp-10h+var_30], rax
0x14002f50b  mov     eax, [rdi]
0x14002f50d  mov     [rbp-10h+var_6C], eax
0x14002f510  mov     rax, [rdi+80h]
0x14002f517  mov     [rbp-10h+var_28], rax
0x14002f51b  mov     eax, [rdi+40h]
0x14002f51e  mov     [rbp-10h+var_68], eax
0x14002f521  mov     rax, [rdi+38h]
0x14002f525  mov     [rbp-10h+var_20], rax
0x14002f529  mov     eax, [rdi+8]
0x14002f52c  mov     [rbp-10h+var_64], eax
0x14002f52f  mov     eax, 1000000h
0x14002f534  mov     [rbp-10h+var_18], rax
0x14002f538  mov     [rbp-10h+var_60], rax
0x14002f53c  lea     rax, [rbp-10h+arg_0]
0x14002f540  mov     [rsp+120h+var_80], rax
0x14002f548  lea     rax, [rbp-10h+var_58]
0x14002f54c  mov     [rsp+120h+var_88], rax
0x14002f554  lea     rax, [rbp-10h+var_50]
0x14002f558  mov     [rsp+120h+var_90], rax
0x14002f560  lea     rax, [rbp-10h+arg_10]
0x14002f564  mov     [rsp+120h+var_98], rax
0x14002f56c  lea     rax, [rbp-10h+var_48]
0x14002f570  mov     [rsp+120h+var_A0], rax
0x14002f578  lea     rax, [rbp-10h+var_40]
0x14002f57c  mov     [rsp+120h+var_A8], rax
0x14002f581  lea     rax, [rbp-10h+arg_18]
0x14002f585  mov     [rsp+120h+var_B0], rax
0x14002f58a  lea     rax, [rbp-10h+var_38]
0x14002f58e  mov     [rsp+120h+var_B8], rax
0x14002f593  lea     rax, [rbp-10h+var_70]
0x14002f597  mov     [rsp+120h+var_C0], rax
0x14002f59c  lea     rax, [rbp-10h+var_30]
0x14002f5a0  mov     [rsp+120h+var_C8], rax
0x14002f5a5  lea     rax, [rbp-10h+var_6C]
0x14002f5a9  mov     [rsp+120h+var_D0], rax
0x14002f5ae  lea     rax, [rbp-10h+var_28]
0x14002f5b2  mov     [rsp+120h+var_D8], rax
0x14002f5b7  lea     rax, [rbp-10h+var_68]
0x14002f5bb  mov     [rsp+120h+var_E0], rax
0x14002f5c0  lea     rax, [rbp-10h+var_20]
0x14002f5c4  mov     [rsp+120h+var_E8], rax
0x14002f5c9  lea     rax, [rbp-10h+var_64]
0x14002f5cd  mov     [rsp+120h+var_F0], rax
0x14002f5d2  lea     rax, [rbp-10h+var_18]
0x14002f5d6  mov     [rsp+120h+var_F8], rax
0x14002f5db  lea     rax, [rbp-10h+var_60]
0x14002f5df  mov     [rsp+120h+var_100], rax
0x14002f5e4  mov     [rbp-10h+arg_0], sil
0x14002f5e8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x14002f5ed  jmp     loc_14002F677
0x14002f5f2  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002f5f7  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002f5fc  mov     rdi, rax
0x14002f5ff  mov     ecx, [rax]
0x14002f601  cmp     ecx, 4
0x14002f604  jbe     short loc_14002F677
0x14002f606  mov     rdx, 400000000000h
0x14002f610  mov     rcx, rax
0x14002f613  call    _tlgKeywordOn
0x14002f618  test    al, al
0x14002f61a  jz      short loc_14002F677
0x14002f61c  mov     [rbp-10h+arg_0], sil
0x14002f620  call    cs:__imp_GetCurrentThreadId
0x14002f626  mov     r8, [rbx+110h]
0x14002f62d  lea     rdx, byte_140085ECD
0x14002f634  mov     [rbp-10h+arg_10], eax
0x14002f637  mov     rcx, rdi
0x14002f63a  mov     eax, [r8+48h]
0x14002f63e  add     r8, 8
0x14002f642  mov     [rbp-10h+arg_18], eax
0x14002f645  mov     eax, 1000000h
0x14002f64a  mov     [rbp-10h+var_60], rax
0x14002f64e  lea     rax, [rbp-10h+arg_0]
0x14002f652  mov     [rsp+120h+var_E8], rax
0x14002f657  lea     rax, [rbp-10h+arg_10]
0x14002f65b  mov     [rsp+120h+var_F0], rax
0x14002f660  lea     rax, [rbp-10h+arg_18]
0x14002f664  mov     [rsp+120h+var_F8], rax
0x14002f669  lea     rax, [rbp-10h+var_60]
0x14002f66d  mov     [rsp+120h+var_100], rax
0x14002f672  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14002f677  mov     rcx, rbx
0x14002f67a  mov     rbx, [rsp+120h+arg_8]
0x14002f682  add     rsp, 110h
0x14002f689  pop     rdi
0x14002f68a  pop     rsi
0x14002f68b  pop     rbp
0x14002f68c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
