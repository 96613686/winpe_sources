# LogProvider::NgcIsoIsTicketAuthenticated::Stop(bool)

- ea: `0x14002f698`
- end: `0x14002f8f0`
- name: `?Stop@NgcIsoIsTicketAuthenticated@LogProvider@@QEAAX_N@Z`
- size: `600`
- prototype: `void __fastcall(LogProvider::NgcIsoIsTicketAuthenticated *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140028850`

## callees

- `0x140002890`
- `0x140003484`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14002f698`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002f880`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002f880`

## pseudocode

```c
void __fastcall LogProvider::NgcIsoIsTicketAuthenticated::Stop(LogProvider::NgcIsoIsTicketAuthenticated *this, char a2)
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
        (unsigned int)byte_140086AF5,
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
        (unsigned int)byte_140086C5B,
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
0x14002f698  mov     [rsp-8+arg_8], rbx
0x14002f69d  push    rbp
0x14002f69e  push    rsi
0x14002f69f  push    rdi
0x14002f6a0  lea     rbp, [rsp+10h]
0x14002f6a5  sub     rsp, 130h
0x14002f6ac  mov     rdi, [rcx+110h]
0x14002f6b3  mov     sil, dl
0x14002f6b6  mov     rbx, rcx
0x14002f6b9  mov     eax, [rdi+48h]
0x14002f6bc  test    eax, eax
0x14002f6be  jns     loc_14002F868
0x14002f6c4  add     rdi, 50h ; 'P'
0x14002f6c8  cmp     eax, [rdi+8]
0x14002f6cb  jnz     loc_14002F868
0x14002f6d1  test    rdi, rdi
0x14002f6d4  jz      loc_14002F868
0x14002f6da  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002f6df  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002f6e4  mov     r9, rax
0x14002f6e7  mov     ecx, [rax]
0x14002f6e9  cmp     ecx, 4
0x14002f6ec  jbe     loc_14002F8D6
0x14002f6f2  mov     rax, [rdi+70h]
0x14002f6f6  lea     rdx, byte_140086AF5
0x14002f6fd  mov     rcx, [rdi+30h]
0x14002f701  mov     [rbp+var_50], rax
0x14002f705  mov     eax, [rdi+68h]
0x14002f708  mov     [rbp+var_80], eax
0x14002f70b  mov     rax, [rdi+60h]
0x14002f70f  mov     r8, [rbx+110h]
0x14002f716  mov     [rbp+var_48], rax
0x14002f71a  add     r8, 8
0x14002f71e  mov     rax, [rdi+58h]
0x14002f722  mov     [rbp+var_40], rax
0x14002f726  mov     eax, [rdi+50h]
0x14002f729  mov     [rbp+var_7C], eax
0x14002f72c  mov     rax, [rdi+48h]
0x14002f730  mov     [rbp+var_38], rax
0x14002f734  mov     eax, [rdi+20h]
0x14002f737  mov     [rbp+var_78], eax
0x14002f73a  mov     rax, [rdi+18h]
0x14002f73e  mov     [rbp+var_30], rax
0x14002f742  mov     eax, [rdi]
0x14002f744  mov     [rbp+var_74], eax
0x14002f747  mov     rax, [rdi+80h]
0x14002f74e  mov     [rbp+var_28], rax
0x14002f752  mov     eax, [rdi+40h]
0x14002f755  mov     [rbp+var_70], eax
0x14002f758  mov     rax, [rdi+38h]
0x14002f75c  mov     [rbp+var_20], rax
0x14002f760  mov     eax, [rdi+8]
0x14002f763  mov     [rbp+var_6C], eax
0x14002f766  lea     rax, [rbp+arg_0]
0x14002f76a  mov     [rsp+140h+var_88], rax
0x14002f772  lea     rax, [rbp+var_60]
0x14002f776  mov     [rsp+140h+var_90], rax
0x14002f77e  lea     rax, [rbp+arg_10]
0x14002f782  mov     [rsp+140h+var_98], rax
0x14002f78a  lea     rax, [rbp+arg_18]
0x14002f78e  mov     [rsp+140h+var_A0], rax
0x14002f796  lea     rax, [rbp+var_58]
0x14002f79a  mov     [rsp+140h+var_A8], rax
0x14002f7a2  lea     rax, [rbp+var_50]
0x14002f7a6  mov     [rsp+140h+var_B0], rax
0x14002f7ae  lea     rax, [rbp+var_80]
0x14002f7b2  mov     [rsp+140h+var_B8], rax
0x14002f7ba  lea     rax, [rbp+var_48]
0x14002f7be  mov     [rsp+140h+var_C0], rax
0x14002f7c6  lea     rax, [rbp+var_40]
0x14002f7ca  mov     [rsp+140h+var_C8], rax
0x14002f7cf  lea     rax, [rbp+var_7C]
0x14002f7d3  mov     [rsp+140h+var_D0], rax
0x14002f7d8  lea     rax, [rbp+var_38]
0x14002f7dc  mov     [rsp+140h+var_D8], rax
0x14002f7e1  lea     rax, [rbp+var_78]
0x14002f7e5  mov     [rsp+140h+var_E0], rax
0x14002f7ea  lea     rax, [rbp+var_30]
0x14002f7ee  mov     [rsp+140h+var_E8], rax
0x14002f7f3  lea     rax, [rbp+var_74]
0x14002f7f7  mov     [rsp+140h+var_F0], rax
0x14002f7fc  lea     rax, [rbp+var_28]
0x14002f800  mov     [rsp+140h+var_F8], rax
0x14002f805  lea     rax, [rbp+var_70]
0x14002f809  mov     [rsp+140h+var_100], rax
0x14002f80e  lea     rax, [rbp+var_20]
0x14002f812  mov     [rsp+140h+var_108], rax
0x14002f817  lea     rax, [rbp+var_6C]
0x14002f81b  mov     [rbp+var_60], rcx
0x14002f81f  mov     ecx, [rdi+44h]
0x14002f822  mov     [rsp+140h+var_110], rax
0x14002f827  lea     rax, [rbp+var_18]
0x14002f82b  mov     [rbp+arg_10], ecx
0x14002f82e  mov     ecx, [rdi+10h]
0x14002f831  mov     [rbp+arg_18], ecx
0x14002f834  mov     rcx, [rdi+78h]
0x14002f838  mov     [rsp+140h+var_118], rax
0x14002f83d  lea     rax, [rbp+var_68]
0x14002f841  mov     [rbp+var_58], rcx
0x14002f845  mov     rcx, r9
0x14002f848  mov     [rsp+140h+var_120], rax
0x14002f84d  mov     [rbp+arg_0], sil
0x14002f851  mov     [rbp+var_18], 1000000h
0x14002f859  mov     [rbp+var_68], 0
0x14002f861  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &)
0x14002f866  jmp     short loc_14002F8D6
0x14002f868  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14002f86d  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14002f872  mov     rdi, rax
0x14002f875  mov     ecx, [rax]
0x14002f877  cmp     ecx, 4
0x14002f87a  jbe     short loc_14002F8D6
0x14002f87c  mov     [rbp+arg_0], sil
0x14002f880  call    cs:__imp_GetCurrentThreadId
0x14002f886  mov     r8, [rbx+110h]
0x14002f88d  lea     rdx, byte_140086C5B
0x14002f894  mov     [rbp+arg_10], eax
0x14002f897  lea     rax, [rbp+arg_0]
0x14002f89b  mov     [rsp+140h+var_108], rax
0x14002f8a0  lea     rax, [rbp+arg_10]
0x14002f8a4  mov     [rsp+140h+var_110], rax
0x14002f8a9  lea     rax, [rbp+arg_18]
0x14002f8ad  mov     ecx, [r8+48h]
0x14002f8b1  add     r8, 8
0x14002f8b5  mov     [rsp+140h+var_118], rax
0x14002f8ba  lea     rax, [rbp+var_68]
0x14002f8be  mov     [rbp+arg_18], ecx
0x14002f8c1  mov     rcx, rdi
0x14002f8c4  mov     [rsp+140h+var_120], rax
0x14002f8c9  mov     [rbp+var_68], 0
0x14002f8d1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x14002f8d6  mov     rcx, rbx
0x14002f8d9  mov     rbx, [rsp+140h+arg_8]
0x14002f8e1  add     rsp, 130h
0x14002f8e8  pop     rdi
0x14002f8e9  pop     rsi
0x14002f8ea  pop     rbp
0x14002f8eb  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
