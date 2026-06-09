# LogProvider::NgcIsoIsTicketCacheEmpty::Stop(bool)

- ea: `0x14002f8f8`
- end: `0x14002fb50`
- name: `?Stop@NgcIsoIsTicketCacheEmpty@LogProvider@@QEAAX_N@Z`
- size: `600`
- prototype: `void __fastcall(LogProvider::NgcIsoIsTicketCacheEmpty *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140028950`

## callees

- `0x140002890`
- `0x140003484`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14002f8f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002fae0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002fae0`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoIsTicketCacheEmpty::Stop(LogProvider::NgcIsoIsTicketCacheEmpty *this, char a2)
{
  __int64 v2; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+C0h] [rbp-80h] BYREF
  int v18; // [rsp+C4h] [rbp-7Ch] BYREF
  int v19; // [rsp+C8h] [rbp-78h] BYREF
  int v20; // [rsp+CCh] [rbp-74h] BYREF
  int v21; // [rsp+D0h] [rbp-70h] BYREF
  int v22; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v23; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+100h] [rbp-40h] BYREF
  __int64 v29; // [rsp+108h] [rbp-38h] BYREF
  __int64 v30; // [rsp+110h] [rbp-30h] BYREF
  __int64 v31; // [rsp+118h] [rbp-28h] BYREF
  __int64 v32; // [rsp+120h] [rbp-20h] BYREF
  __int64 v33[3]; // [rsp+128h] [rbp-18h] BYREF
  char v34; // [rsp+150h] [rbp+10h] BYREF
  DWORD v35; // [rsp+160h] [rbp+20h] BYREF
  int v36; // [rsp+168h] [rbp+28h] BYREF

  v2 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = LogProvider::Provider();
    if ( *(_DWORD *)v9 > 4u )
    {
      v10 = *((_QWORD *)v6 + 6);
      v26 = *((_QWORD *)v6 + 14);
      v17 = v6[26];
      v11 = *((_QWORD *)this + 34);
      v27 = *((_QWORD *)v6 + 12);
      v28 = *((_QWORD *)v6 + 11);
      v18 = v6[20];
      v29 = *((_QWORD *)v6 + 9);
      v19 = v6[8];
      v30 = *((_QWORD *)v6 + 3);
      v20 = *v6;
      v31 = *((_QWORD *)v6 + 16);
      v21 = v6[16];
      v32 = *((_QWORD *)v6 + 7);
      v22 = v6[2];
      v24 = v10;
      v35 = v6[17];
      v36 = v6[4];
      v25 = *((_QWORD *)v6 + 15);
      v34 = a2;
      v33[0] = 0x1000000;
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
        (_DWORD)v9,
        (unsigned int)byte_140086E79,
        v11 + 8,
        (_DWORD)v9,
        (__int64)&v23,
        (__int64)v33,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v19,
        (__int64)&v29,
        (__int64)&v18,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v24,
        (__int64)&v34);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = LogProvider::Provider();
    v13 = (int)v12;
    if ( *(_DWORD *)v12 > 4u )
    {
      v34 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v35 = CurrentThreadId;
      v36 = *(_DWORD *)(v15 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        v13,
        (unsigned int)&dword_140086FD4,
        v15 + 8,
        v16,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v8,
    v9);
}

```

## disassembly

```asm
0x14002f8f8  mov     [rsp-8+arg_8], rbx
0x14002f8fd  push    rbp
0x14002f8fe  push    rsi
0x14002f8ff  push    rdi
0x14002f900  lea     rbp, [rsp+10h]
0x14002f905  sub     rsp, 130h
0x14002f90c  mov     rdi, [rcx+110h]
0x14002f913  mov     sil, dl
0x14002f916  mov     rbx, rcx
0x14002f919  mov     eax, [rdi+48h]
0x14002f91c  test    eax, eax
0x14002f91e  jns     loc_14002FAC8
0x14002f924  add     rdi, 50h ; 'P'
0x14002f928  cmp     eax, [rdi+8]
0x14002f92b  jnz     loc_14002FAC8
0x14002f931  test    rdi, rdi
0x14002f934  jz      loc_14002FAC8
0x14002f93a  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002f93f  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002f944  mov     r9, rax
0x14002f947  mov     ecx, [rax]
0x14002f949  cmp     ecx, 4
0x14002f94c  jbe     loc_14002FB36
0x14002f952  mov     rax, [rdi+70h]
0x14002f956  lea     rdx, byte_140086E79
0x14002f95d  mov     rcx, [rdi+30h]
0x14002f961  mov     [rbp+var_50], rax
0x14002f965  mov     eax, [rdi+68h]
0x14002f968  mov     [rbp+var_80], eax
0x14002f96b  mov     rax, [rdi+60h]
0x14002f96f  mov     r8, [rbx+110h]
0x14002f976  mov     [rbp+var_48], rax
0x14002f97a  add     r8, 8
0x14002f97e  mov     rax, [rdi+58h]
0x14002f982  mov     [rbp+var_40], rax
0x14002f986  mov     eax, [rdi+50h]
0x14002f989  mov     [rbp+var_7C], eax
0x14002f98c  mov     rax, [rdi+48h]
0x14002f990  mov     [rbp+var_38], rax
0x14002f994  mov     eax, [rdi+20h]
0x14002f997  mov     [rbp+var_78], eax
0x14002f99a  mov     rax, [rdi+18h]
0x14002f99e  mov     [rbp+var_30], rax
0x14002f9a2  mov     eax, [rdi]
0x14002f9a4  mov     [rbp+var_74], eax
0x14002f9a7  mov     rax, [rdi+80h]
0x14002f9ae  mov     [rbp+var_28], rax
0x14002f9b2  mov     eax, [rdi+40h]
0x14002f9b5  mov     [rbp+var_70], eax
0x14002f9b8  mov     rax, [rdi+38h]
0x14002f9bc  mov     [rbp+var_20], rax
0x14002f9c0  mov     eax, [rdi+8]
0x14002f9c3  mov     [rbp+var_6C], eax
0x14002f9c6  lea     rax, [rbp+arg_0]
0x14002f9ca  mov     [rsp+140h+var_88], rax
0x14002f9d2  lea     rax, [rbp+var_60]
0x14002f9d6  mov     [rsp+140h+var_90], rax
0x14002f9de  lea     rax, [rbp+arg_10]
0x14002f9e2  mov     [rsp+140h+var_98], rax
0x14002f9ea  lea     rax, [rbp+arg_18]
0x14002f9ee  mov     [rsp+140h+var_A0], rax
0x14002f9f6  lea     rax, [rbp+var_58]
0x14002f9fa  mov     [rsp+140h+var_A8], rax
0x14002fa02  lea     rax, [rbp+var_50]
0x14002fa06  mov     [rsp+140h+var_B0], rax
0x14002fa0e  lea     rax, [rbp+var_80]
0x14002fa12  mov     [rsp+140h+var_B8], rax
0x14002fa1a  lea     rax, [rbp+var_48]
0x14002fa1e  mov     [rsp+140h+var_C0], rax
0x14002fa26  lea     rax, [rbp+var_40]
0x14002fa2a  mov     [rsp+140h+var_C8], rax
0x14002fa2f  lea     rax, [rbp+var_7C]
0x14002fa33  mov     [rsp+140h+var_D0], rax
0x14002fa38  lea     rax, [rbp+var_38]
0x14002fa3c  mov     [rsp+140h+var_D8], rax
0x14002fa41  lea     rax, [rbp+var_78]
0x14002fa45  mov     [rsp+140h+var_E0], rax
0x14002fa4a  lea     rax, [rbp+var_30]
0x14002fa4e  mov     [rsp+140h+var_E8], rax
0x14002fa53  lea     rax, [rbp+var_74]
0x14002fa57  mov     [rsp+140h+var_F0], rax
0x14002fa5c  lea     rax, [rbp+var_28]
0x14002fa60  mov     [rsp+140h+var_F8], rax
0x14002fa65  lea     rax, [rbp+var_70]
0x14002fa69  mov     [rsp+140h+var_100], rax
0x14002fa6e  lea     rax, [rbp+var_20]
0x14002fa72  mov     [rsp+140h+var_108], rax
0x14002fa77  lea     rax, [rbp+var_6C]
0x14002fa7b  mov     [rbp+var_60], rcx
0x14002fa7f  mov     ecx, [rdi+44h]
0x14002fa82  mov     [rsp+140h+var_110], rax
0x14002fa87  lea     rax, [rbp+var_18]
0x14002fa8b  mov     [rbp+arg_10], ecx
0x14002fa8e  mov     ecx, [rdi+10h]
0x14002fa91  mov     [rbp+arg_18], ecx
0x14002fa94  mov     rcx, [rdi+78h]
0x14002fa98  mov     [rsp+140h+var_118], rax
0x14002fa9d  lea     rax, [rbp+var_68]
0x14002faa1  mov     [rbp+var_58], rcx
0x14002faa5  mov     rcx, r9
0x14002faa8  mov     [rsp+140h+var_120], rax
0x14002faad  mov     [rbp+arg_0], sil
0x14002fab1  mov     [rbp+var_18], 1000000h
0x14002fab9  mov     [rbp+var_68], 0
0x14002fac1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &)
0x14002fac6  jmp     short loc_14002FB36
0x14002fac8  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002facd  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002fad2  mov     rdi, rax
0x14002fad5  mov     ecx, [rax]
0x14002fad7  cmp     ecx, 4
0x14002fada  jbe     short loc_14002FB36
0x14002fadc  mov     [rbp+arg_0], sil
0x14002fae0  call    cs:__imp_GetCurrentThreadId
0x14002fae6  mov     r8, [rbx+110h]
0x14002faed  lea     rdx, dword_140086FD4
0x14002faf4  mov     [rbp+arg_10], eax
0x14002faf7  lea     rax, [rbp+arg_0]
0x14002fafb  mov     [rsp+140h+var_108], rax
0x14002fb00  lea     rax, [rbp+arg_10]
0x14002fb04  mov     [rsp+140h+var_110], rax
0x14002fb09  lea     rax, [rbp+arg_18]
0x14002fb0d  mov     ecx, [r8+48h]
0x14002fb11  add     r8, 8
0x14002fb15  mov     [rsp+140h+var_118], rax
0x14002fb1a  lea     rax, [rbp+var_68]
0x14002fb1e  mov     [rbp+arg_18], ecx
0x14002fb21  mov     rcx, rdi
0x14002fb24  mov     [rsp+140h+var_120], rax
0x14002fb29  mov     [rbp+var_68], 0
0x14002fb31  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14002fb36  mov     rcx, rbx
0x14002fb39  mov     rbx, [rsp+140h+arg_8]
0x14002fb41  add     rsp, 130h
0x14002fb48  pop     rdi
0x14002fb49  pop     rsi
0x14002fb4a  pop     rbp
0x14002fb4b  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
