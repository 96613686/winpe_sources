# wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)

- ea: `0x1400163f8`
- end: `0x14001663d`
- name: `?ReportStopActivity@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z`
- size: `581`
- prototype: `__int64 __fastcall(_QWORD *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140015ad4`
- `0x140016bbc`

## callees

- `0x140001728`
- `0x140001824`
- `0x140001f1c`
- `0x1400163d8`
- `0x1400163f8`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400165c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400165c8`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
        _QWORD *a1,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  __int64 v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // r9
  const WCHAR *v10; // rcx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  int v21; // [rsp+A0h] [rbp-19h] BYREF
  int v22; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v23; // [rsp+A8h] [rbp-11h] BYREF
  const WCHAR *v24; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v25; // [rsp+B8h] [rbp-1h] BYREF
  const WCHAR *v26; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v27; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v28; // [rsp+D0h] [rbp+17h] BYREF
  const WCHAR *v29; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v30; // [rsp+E0h] [rbp+27h] BYREF
  const unsigned __int16 *v31; // [rsp+E8h] [rbp+2Fh] BYREF
  int v32; // [rsp+120h] [rbp+67h] BYREF
  DWORD v33; // [rsp+128h] [rbp+6Fh] BYREF
  const WCHAR *v34; // [rsp+130h] [rbp+77h] BYREF
  const unsigned __int16 *v35; // [rsp+138h] [rbp+7Fh] BYREF

  if ( a2 < 0 )
  {
    v4 = a1[34];
    v5 = *(_DWORD *)(v4 + 72);
    if ( v5 < 0 && (v6 = v4 + 80, v5 == *(_DWORD *)(v6 + 8)) && v6 )
    {
      v7 = MDMPushProvider::Provider((__int64)a1);
      if ( *(_DWORD *)v7 > 2u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL, v8, v7) )
      {
        v10 = *(const WCHAR **)(v6 + 120);
        v11 = a1[34];
        v25 = *(const unsigned __int16 **)(v6 + 112);
        v33 = *(_DWORD *)(v6 + 104);
        v26 = *(const WCHAR **)(v6 + 96);
        v27 = *(const unsigned __int16 **)(v6 + 88);
        v32 = *(_DWORD *)(v6 + 80);
        v28 = *(const unsigned __int16 **)(v6 + 72);
        LODWORD(v34) = *(_DWORD *)(v6 + 32);
        v29 = *(const WCHAR **)(v6 + 24);
        LODWORD(v35) = *(_DWORD *)v6;
        v30 = *(const unsigned __int16 **)(v6 + 128);
        v21 = *(_DWORD *)(v6 + 64);
        v31 = *(const unsigned __int16 **)(v6 + 56);
        v22 = *(_DWORD *)(v6 + 8);
        v24 = v10;
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v9,
          (__int64)&byte_14001FB37,
          v11 + 8,
          v9,
          (__int64)&v23,
          (__int64)&v22,
          &v31,
          (__int64)&v21,
          &v30,
          (__int64)&v35,
          &v29,
          (__int64)&v34,
          &v28,
          (__int64)&v32,
          &v27,
          &v26,
          (__int64)&v33,
          &v25,
          &v24);
      }
    }
    else
    {
      v12 = MDMPushProvider::Provider((__int64)a1);
      v15 = (__int64)v12;
      if ( *(_DWORD *)v12 > 2u && (unsigned __int8)tlgKeywordOn(v12, 0x200000000000LL, v13, v14) )
      {
        v16 = a1[34];
        v34 = *(const WCHAR **)(v16 + 56);
        v35 = *(const unsigned __int16 **)(v16 + 48);
        CurrentThreadId = GetCurrentThreadId();
        v18 = a1[34];
        v33 = CurrentThreadId;
        v32 = a2;
        v23 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v15,
          (__int64)&word_14001FC4E,
          v18 + 8,
          v19,
          (__int64)&v23,
          (__int64)&v32,
          (__int64)&v33,
          &v35,
          &v34);
      }
    }
  }
  return (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
}

```

## disassembly

```asm
0x1400163f8  push    rbp
0x1400163fa  push    rbx
0x1400163fb  push    rsi
0x1400163fc  push    rdi
0x1400163fd  lea     rbp, [rsp-3Fh]
0x140016402  sub     rsp, 0F8h
0x140016409  mov     esi, edx
0x14001640b  mov     rbx, rcx
0x14001640e  test    edx, edx
0x140016410  jns     loc_140016623
0x140016416  mov     rdi, [rcx+110h]
0x14001641d  mov     eax, [rdi+48h]
0x140016420  test    eax, eax
0x140016422  jns     loc_140016588
0x140016428  add     rdi, 50h ; 'P'
0x14001642c  cmp     eax, [rdi+8]
0x14001642f  jnz     loc_140016588
0x140016435  test    rdi, rdi
0x140016438  jz      loc_140016588
0x14001643e  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140016443  mov     r9, rax
0x140016446  mov     ecx, [rax]
0x140016448  cmp     ecx, 2
0x14001644b  jbe     loc_140016623
0x140016451  mov     rdx, 200000000000h
0x14001645b  mov     rcx, rax
0x14001645e  call    _tlgKeywordOn
0x140016463  test    al, al
0x140016465  jz      loc_140016623
0x14001646b  mov     rax, [rdi+70h]
0x14001646f  lea     rdx, byte_14001FB37
0x140016476  mov     rcx, [rdi+78h]
0x14001647a  mov     r8, [rbx+110h]
0x140016481  mov     [rbp+57h+var_58], rax
0x140016485  add     r8, 8
0x140016489  mov     eax, [rdi+68h]
0x14001648c  mov     [rbp+57h+arg_8], eax
0x14001648f  mov     rax, [rdi+60h]
0x140016493  mov     [rbp+57h+var_50], rax
0x140016497  mov     rax, [rdi+58h]
0x14001649b  mov     [rbp+57h+var_48], rax
0x14001649f  mov     eax, [rdi+50h]
0x1400164a2  mov     [rbp+57h+arg_0], eax
0x1400164a5  mov     rax, [rdi+48h]
0x1400164a9  mov     [rbp+57h+var_40], rax
0x1400164ad  mov     eax, [rdi+20h]
0x1400164b0  mov     dword ptr [rbp+57h+arg_10], eax
0x1400164b3  mov     rax, [rdi+18h]
0x1400164b7  mov     [rbp+57h+var_38], rax
0x1400164bb  mov     eax, [rdi]
0x1400164bd  mov     dword ptr [rbp+57h+arg_18], eax
0x1400164c0  mov     rax, [rdi+80h]
0x1400164c7  mov     [rbp+57h+var_30], rax
0x1400164cb  mov     eax, [rdi+40h]
0x1400164ce  mov     [rbp+57h+var_70], eax
0x1400164d1  mov     rax, [rdi+38h]
0x1400164d5  mov     [rbp+57h+var_28], rax
0x1400164d9  mov     eax, [rdi+8]
0x1400164dc  mov     [rbp+57h+var_6C], eax
0x1400164df  lea     rax, [rbp+57h+var_60]
0x1400164e3  mov     [rsp+110h+var_80], rax
0x1400164eb  lea     rax, [rbp+57h+var_58]
0x1400164ef  mov     [rsp+110h+var_88], rax
0x1400164f7  lea     rax, [rbp+57h+arg_8]
0x1400164fb  mov     [rsp+110h+var_90], rax
0x140016503  lea     rax, [rbp+57h+var_50]
0x140016507  mov     [rsp+110h+var_98], rax
0x14001650c  lea     rax, [rbp+57h+var_48]
0x140016510  mov     [rsp+110h+var_A0], rax
0x140016515  lea     rax, [rbp+57h+arg_0]
0x140016519  mov     [rsp+110h+var_A8], rax
0x14001651e  lea     rax, [rbp+57h+var_40]
0x140016522  mov     [rsp+110h+var_B0], rax
0x140016527  lea     rax, [rbp+57h+arg_10]
0x14001652b  mov     [rsp+110h+var_B8], rax
0x140016530  lea     rax, [rbp+57h+var_38]
0x140016534  mov     [rsp+110h+var_C0], rax
0x140016539  lea     rax, [rbp+57h+arg_18]
0x14001653d  mov     [rsp+110h+var_C8], rax
0x140016542  lea     rax, [rbp+57h+var_30]
0x140016546  mov     [rsp+110h+var_D0], rax
0x14001654b  lea     rax, [rbp+57h+var_70]
0x14001654f  mov     [rsp+110h+var_D8], rax
0x140016554  lea     rax, [rbp+57h+var_28]
0x140016558  mov     [rsp+110h+var_E0], rax
0x14001655d  lea     rax, [rbp+57h+var_6C]
0x140016561  mov     [rsp+110h+var_E8], rax
0x140016566  lea     rax, [rbp+57h+var_68]
0x14001656a  mov     [rbp+57h+var_60], rcx
0x14001656e  mov     rcx, r9
0x140016571  mov     [rsp+110h+var_F0], rax
0x140016576  mov     [rbp+57h+var_68], 1000000h
0x14001657e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140016583  jmp     loc_140016623
0x140016588  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x14001658d  mov     rdi, rax
0x140016590  mov     ecx, [rax]
0x140016592  cmp     ecx, 2
0x140016595  jbe     loc_140016623
0x14001659b  mov     rdx, 200000000000h
0x1400165a5  mov     rcx, rax
0x1400165a8  call    _tlgKeywordOn
0x1400165ad  test    al, al
0x1400165af  jz      short loc_140016623
0x1400165b1  mov     rcx, [rbx+110h]
0x1400165b8  mov     rax, [rcx+38h]
0x1400165bc  mov     [rbp+57h+arg_10], rax
0x1400165c0  mov     rax, [rcx+30h]
0x1400165c4  mov     [rbp+57h+arg_18], rax
0x1400165c8  call    cs:__imp_GetCurrentThreadId
0x1400165ce  mov     r8, [rbx+110h]
0x1400165d5  lea     rdx, word_14001FC4E
0x1400165dc  mov     [rbp+57h+arg_8], eax
0x1400165df  add     r8, 8
0x1400165e3  lea     rax, [rbp+57h+arg_10]
0x1400165e7  mov     [rbp+57h+arg_0], esi
0x1400165ea  mov     [rsp+110h+var_D0], rax
0x1400165ef  mov     rcx, rdi
0x1400165f2  lea     rax, [rbp+57h+arg_18]
0x1400165f6  mov     [rbp+57h+var_68], 1000000h
0x1400165fe  mov     [rsp+110h+var_D8], rax
0x140016603  lea     rax, [rbp+57h+arg_8]
0x140016607  mov     [rsp+110h+var_E0], rax
0x14001660c  lea     rax, [rbp+57h+arg_0]
0x140016610  mov     [rsp+110h+var_E8], rax
0x140016615  lea     rax, [rbp+57h+var_68]
0x140016619  mov     [rsp+110h+var_F0], rax
0x14001661e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140016623  mov     rax, [rbx]
0x140016626  mov     rcx, rbx
0x140016629  mov     rax, [rax+8]
0x14001662d  add     rsp, 0F8h
0x140016634  pop     rdi
0x140016635  pop     rsi
0x140016636  pop     rbx
0x140016637  pop     rbp
0x140016638  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
