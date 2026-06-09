# LogProvider::ClientAuthRemoveKeyRefCount::Stop(uchar,unsigned __int64)

- ea: `0x140042190`
- end: `0x140042411`
- name: `?Stop@ClientAuthRemoveKeyRefCount@LogProvider@@QEAAXE_K@Z`
- size: `641`
- prototype: `void __fastcall(LogProvider::ClientAuthRemoveKeyRefCount *__hidden this, unsigned __int8, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140041500`

## callees

- `0x14000131c`
- `0x140003634`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x140042190`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140042393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140042393`

## pseudocode

```c
void __fastcall LogProvider::ClientAuthRemoveKeyRefCount::Stop(
        LogProvider::ClientAuthRemoveKeyRefCount *this,
        char a2,
        __int64 a3)
{
  __int64 v3; // rdi
  int v7; // eax
  int *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  const struct _tlgProvider_t *v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  int v17; // r9d
  int v18; // [rsp+D0h] [rbp-80h] BYREF
  int v19; // [rsp+D4h] [rbp-7Ch] BYREF
  int v20; // [rsp+D8h] [rbp-78h] BYREF
  int v21; // [rsp+DCh] [rbp-74h] BYREF
  int v22; // [rsp+E0h] [rbp-70h] BYREF
  int v23; // [rsp+E4h] [rbp-6Ch] BYREF
  int v24; // [rsp+E8h] [rbp-68h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-60h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+100h] [rbp-50h] BYREF
  __int64 v28; // [rsp+108h] [rbp-48h] BYREF
  __int64 v29; // [rsp+110h] [rbp-40h] BYREF
  __int64 v30; // [rsp+118h] [rbp-38h] BYREF
  __int64 v31; // [rsp+120h] [rbp-30h] BYREF
  __int64 v32; // [rsp+128h] [rbp-28h] BYREF
  __int64 v33; // [rsp+130h] [rbp-20h] BYREF
  __int64 v34; // [rsp+138h] [rbp-18h] BYREF
  __int64 v35; // [rsp+140h] [rbp-10h] BYREF
  __int64 v36; // [rsp+148h] [rbp-8h] BYREF
  char v37; // [rsp+170h] [rbp+20h] BYREF
  DWORD v38; // [rsp+188h] [rbp+38h] BYREF

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = LogProvider::Provider();
    if ( *(_DWORD *)v11 > 4u )
    {
      v29 = *((_QWORD *)v8 + 15);
      v30 = *((_QWORD *)v8 + 14);
      v20 = v8[26];
      v12 = *((_QWORD *)v8 + 6);
      v31 = *((_QWORD *)v8 + 12);
      v13 = *((_QWORD *)this + 34);
      v32 = *((_QWORD *)v8 + 11);
      v21 = v8[20];
      v33 = *((_QWORD *)v8 + 9);
      v22 = v8[8];
      v34 = *((_QWORD *)v8 + 3);
      v23 = *v8;
      v35 = *((_QWORD *)v8 + 16);
      v24 = v8[16];
      v36 = *((_QWORD *)v8 + 7);
      v18 = v8[2];
      v28 = v12;
      v38 = v8[17];
      LODWORD(v12) = v8[4];
      v27 = a3;
      v37 = a2;
      v19 = v12;
      v25 = 0x1000000;
      v26 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        (_DWORD)v11,
        (unsigned int)byte_14008CE83,
        v13 + 8,
        (_DWORD)v11,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v18,
        (__int64)&v36,
        (__int64)&v24,
        (__int64)&v35,
        (__int64)&v23,
        (__int64)&v34,
        (__int64)&v22,
        (__int64)&v33,
        (__int64)&v21,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v38,
        (__int64)&v28,
        (__int64)&v37,
        (__int64)&v27);
    }
  }
  else
  {
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = LogProvider::Provider();
    if ( *(_DWORD *)v14 > 4u )
    {
      v26 = a3;
      v37 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v38 = CurrentThreadId;
      v18 = *(_DWORD *)(v16 + 72);
      v25 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        (_DWORD)v14,
        (unsigned int)byte_14008CFEB,
        v16 + 8,
        v17,
        (__int64)&v25,
        (__int64)&v18,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v26);
    }
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v9,
    v10,
    v11);
}

```

## disassembly

```asm
0x140042190  mov     [rsp-18h+arg_8], rbx
0x140042195  mov     [rsp-18h+arg_10], rsi
0x14004219a  push    rbp
0x14004219b  push    rdi
0x14004219c  push    r14
0x14004219e  mov     rbp, rsp
0x1400421a1  sub     rsp, 150h
0x1400421a8  mov     rdi, [rcx+110h]
0x1400421af  mov     rsi, r8
0x1400421b2  mov     r14b, dl
0x1400421b5  mov     rbx, rcx
0x1400421b8  mov     eax, [rdi+48h]
0x1400421bb  test    eax, eax
0x1400421bd  jns     loc_140042377
0x1400421c3  add     rdi, 50h ; 'P'
0x1400421c7  cmp     eax, [rdi+8]
0x1400421ca  jnz     loc_140042377
0x1400421d0  test    rdi, rdi
0x1400421d3  jz      loc_140042377
0x1400421d9  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400421de  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x1400421e3  mov     r9, rax
0x1400421e6  mov     ecx, [rax]
0x1400421e8  cmp     ecx, 4
0x1400421eb  jbe     loc_1400423F2
0x1400421f1  mov     rax, [rdi+78h]
0x1400421f5  mov     [rbp+var_40], rax
0x1400421f9  mov     rax, [rdi+70h]
0x1400421fd  mov     [rbp+var_38], rax
0x140042201  mov     eax, [rdi+68h]
0x140042204  mov     [rbp+var_78], eax
0x140042207  mov     rax, [rdi+60h]
0x14004220b  mov     rcx, [rdi+30h]
0x14004220f  mov     [rbp+var_30], rax
0x140042213  mov     rax, [rdi+58h]
0x140042217  mov     r8, [rbx+110h]
0x14004221e  mov     [rbp+var_28], rax
0x140042222  add     r8, 8
0x140042226  mov     eax, [rdi+50h]
0x140042229  mov     [rbp+var_74], eax
0x14004222c  mov     rax, [rdi+48h]
0x140042230  mov     [rbp+var_20], rax
0x140042234  mov     eax, [rdi+20h]
0x140042237  mov     [rbp+var_70], eax
0x14004223a  mov     rax, [rdi+18h]
0x14004223e  mov     [rbp+var_18], rax
0x140042242  mov     eax, [rdi]
0x140042244  mov     [rbp+var_6C], eax
0x140042247  mov     rax, [rdi+80h]
0x14004224e  mov     [rbp+var_10], rax
0x140042252  mov     eax, [rdi+40h]
0x140042255  mov     [rbp+var_68], eax
0x140042258  mov     rax, [rdi+38h]
0x14004225c  mov     [rbp+var_8], rax
0x140042260  mov     eax, [rdi+8]
0x140042263  mov     [rbp+var_80], eax
0x140042266  lea     rax, [rbp+var_50]
0x14004226a  mov     [rsp+150h+var_90], rax
0x140042272  lea     rax, [rbp+arg_0]
0x140042276  mov     [rsp+150h+var_98], rax
0x14004227e  lea     rax, [rbp+var_48]
0x140042282  mov     [rsp+150h+var_A0], rax
0x14004228a  lea     rax, [rbp+arg_18]
0x14004228e  mov     [rsp+150h+var_A8], rax
0x140042296  lea     rax, [rbp+var_7C]
0x14004229a  mov     [rsp+150h+var_B0], rax
0x1400422a2  lea     rax, [rbp+var_40]
0x1400422a6  mov     [rsp+150h+var_B8], rax
0x1400422ae  lea     rax, [rbp+var_38]
0x1400422b2  mov     [rsp+150h+var_C0], rax
0x1400422ba  lea     rax, [rbp+var_78]
0x1400422be  mov     [rsp+150h+var_C8], rax
0x1400422c6  lea     rax, [rbp+var_30]
0x1400422ca  mov     [rsp+150h+var_D0], rax
0x1400422d2  lea     rax, [rbp+var_28]
0x1400422d6  mov     [rsp+150h+var_D8], rax
0x1400422db  lea     rax, [rbp+var_74]
0x1400422df  mov     [rsp+150h+var_E0], rax
0x1400422e4  lea     rax, [rbp+var_20]
0x1400422e8  mov     [rsp+150h+var_E8], rax
0x1400422ed  lea     rax, [rbp+var_70]
0x1400422f1  mov     [rsp+150h+var_F0], rax
0x1400422f6  lea     rax, [rbp+var_18]
0x1400422fa  mov     [rsp+150h+var_F8], rax
0x1400422ff  lea     rax, [rbp+var_6C]
0x140042303  mov     [rsp+150h+var_100], rax
0x140042308  lea     rax, [rbp+var_10]
0x14004230c  mov     [rsp+150h+var_108], rax
0x140042311  lea     rax, [rbp+var_68]
0x140042315  mov     [rsp+150h+var_110], rax
0x14004231a  lea     rax, [rbp+var_8]
0x14004231e  mov     [rsp+150h+var_118], rax
0x140042323  lea     rax, [rbp+var_80]
0x140042327  mov     [rsp+150h+var_120], rax
0x14004232c  lea     rax, [rbp+var_60]
0x140042330  mov     [rbp+var_48], rcx
0x140042334  mov     ecx, [rdi+44h]
0x140042337  mov     [rbp+arg_18], ecx
0x14004233a  mov     ecx, [rdi+10h]
0x14004233d  mov     [rsp+150h+var_128], rax
0x140042342  lea     rax, [rbp+var_58]
0x140042346  mov     [rbp+var_50], rsi
0x14004234a  mov     [rbp+arg_0], r14b
0x14004234e  mov     [rbp+var_7C], ecx
0x140042351  mov     [rbp+var_60], 1000000h
0x140042359  mov     [rbp+var_58], 0
0x140042361  lea     rdx, byte_14008CE83
0x140042368  mov     [rsp+150h+var_130], rax
0x14004236d  mov     rcx, r9
0x140042370  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x140042375  jmp     short loc_1400423F2
0x140042377  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14004237c  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x140042381  mov     rdi, rax
0x140042384  mov     ecx, [rax]
0x140042386  cmp     ecx, 4
0x140042389  jbe     short loc_1400423F2
0x14004238b  mov     [rbp+var_58], rsi
0x14004238f  mov     [rbp+arg_0], r14b
0x140042393  call    cs:__imp_GetCurrentThreadId
0x140042399  mov     r8, [rbx+110h]
0x1400423a0  lea     rdx, byte_14008CFEB
0x1400423a7  mov     [rbp+arg_18], eax
0x1400423aa  lea     rax, [rbp+var_58]
0x1400423ae  mov     [rsp+150h+var_110], rax
0x1400423b3  lea     rax, [rbp+arg_0]
0x1400423b7  mov     [rsp+150h+var_118], rax
0x1400423bc  lea     rax, [rbp+arg_18]
0x1400423c0  mov     ecx, [r8+48h]
0x1400423c4  add     r8, 8
0x1400423c8  mov     [rsp+150h+var_120], rax
0x1400423cd  lea     rax, [rbp+var_80]
0x1400423d1  mov     [rsp+150h+var_128], rax
0x1400423d6  lea     rax, [rbp+var_60]
0x1400423da  mov     [rbp+var_80], ecx
0x1400423dd  mov     rcx, rdi
0x1400423e0  mov     [rsp+150h+var_130], rax
0x1400423e5  mov     [rbp+var_60], 0
0x1400423ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x1400423f2  mov     rcx, rbx
0x1400423f5  lea     r11, [rsp+150h+var_s0]
0x1400423fd  mov     rbx, [r11+28h]
0x140042401  mov     rsi, [r11+30h]
0x140042405  mov     rsp, r11
0x140042408  pop     r14
0x14004240a  pop     rdi
0x14004240b  pop     rbp
0x14004240c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
