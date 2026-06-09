# LogProvider::CounterStoreQueryCounter::Stop(unsigned __int64)

- ea: `0x14005ee88`
- end: `0x14005f0d9`
- name: `?Stop@CounterStoreQueryCounter@LogProvider@@QEAAX_K@Z`
- size: `593`
- prototype: `void __fastcall(LogProvider::CounterStoreQueryCounter *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14005e368`

## callees

- `0x140001fc0`
- `0x14000330c`
- `0x1400036d4`
- `0x14000c558`
- `0x14001648c`
- `0x1400174e8`
- `0x14005ee88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005f068`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005f068`

## pseudocode

```c
void __fastcall LogProvider::CounterStoreQueryCounter::Stop(LogProvider::CounterStoreQueryCounter *this, __int64 a2)
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
        (unsigned int)byte_14008E41B,
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
        (unsigned int)&byte_14008E367,
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
0x14005ee88  mov     [rsp-8+arg_8], rbx
0x14005ee8d  push    rbp
0x14005ee8e  push    rsi
0x14005ee8f  push    rdi
0x14005ee90  lea     rbp, [rsp+10h]
0x14005ee95  sub     rsp, 120h
0x14005ee9c  mov     rdi, [rcx+110h]
0x14005eea3  mov     rsi, rdx
0x14005eea6  mov     rbx, rcx
0x14005eea9  mov     eax, [rdi+48h]
0x14005eeac  test    eax, eax
0x14005eeae  jns     loc_14005F03A
0x14005eeb4  add     rdi, 50h ; 'P'
0x14005eeb8  cmp     eax, [rdi+8]
0x14005eebb  jnz     loc_14005F03A
0x14005eec1  test    rdi, rdi
0x14005eec4  jz      loc_14005F03A
0x14005eeca  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005eecf  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005eed4  mov     r9, rax
0x14005eed7  mov     ecx, [rax]
0x14005eed9  cmp     ecx, 4
0x14005eedc  jbe     loc_14005F0BF
0x14005eee2  mov     rdx, 400000000000h
0x14005eeec  mov     rcx, rax
0x14005eeef  call    _tlgKeywordOn
0x14005eef4  test    al, al
0x14005eef6  jz      loc_14005F0BF
0x14005eefc  mov     rax, [rdi+78h]
0x14005ef00  lea     rdx, byte_14008E41B
0x14005ef07  mov     [rbp+var_60], rax
0x14005ef0b  mov     rcx, r9
0x14005ef0e  mov     rax, [rdi+70h]
0x14005ef12  mov     r8, [rbx+110h]
0x14005ef19  mov     [rbp+var_58], rax
0x14005ef1d  add     r8, 8
0x14005ef21  mov     eax, [rdi+68h]
0x14005ef24  mov     [rbp+arg_0], eax
0x14005ef27  mov     rax, [rdi+60h]
0x14005ef2b  mov     [rbp+var_50], rax
0x14005ef2f  mov     rax, [rdi+58h]
0x14005ef33  mov     [rbp+var_48], rax
0x14005ef37  mov     eax, [rdi+50h]
0x14005ef3a  mov     [rbp+arg_10], eax
0x14005ef3d  mov     rax, [rdi+48h]
0x14005ef41  mov     [rbp+var_40], rax
0x14005ef45  mov     eax, [rdi+20h]
0x14005ef48  mov     dword ptr [rbp+arg_18], eax
0x14005ef4b  mov     rax, [rdi+18h]
0x14005ef4f  mov     [rbp+var_38], rax
0x14005ef53  mov     eax, [rdi]
0x14005ef55  mov     [rbp+var_80], eax
0x14005ef58  mov     rax, [rdi+80h]
0x14005ef5f  mov     [rbp+var_30], rax
0x14005ef63  mov     eax, [rdi+40h]
0x14005ef66  mov     [rbp+var_7C], eax
0x14005ef69  mov     rax, [rdi+38h]
0x14005ef6d  mov     [rbp+var_28], rax
0x14005ef71  mov     eax, [rdi+8]
0x14005ef74  mov     [rbp+var_78], eax
0x14005ef77  mov     eax, 1000000h
0x14005ef7c  mov     [rbp+var_20], rax
0x14005ef80  mov     [rbp+var_70], rax
0x14005ef84  lea     rax, [rbp+var_68]
0x14005ef88  mov     [rsp+130h+var_90], rax
0x14005ef90  lea     rax, [rbp+var_60]
0x14005ef94  mov     [rsp+130h+var_98], rax
0x14005ef9c  lea     rax, [rbp+var_58]
0x14005efa0  mov     [rsp+130h+var_A0], rax
0x14005efa8  lea     rax, [rbp+arg_0]
0x14005efac  mov     [rsp+130h+var_A8], rax
0x14005efb4  lea     rax, [rbp+var_50]
0x14005efb8  mov     [rsp+130h+var_B0], rax
0x14005efc0  lea     rax, [rbp+var_48]
0x14005efc4  mov     [rsp+130h+var_B8], rax
0x14005efc9  lea     rax, [rbp+arg_10]
0x14005efcd  mov     [rsp+130h+var_C0], rax
0x14005efd2  lea     rax, [rbp+var_40]
0x14005efd6  mov     [rsp+130h+var_C8], rax
0x14005efdb  lea     rax, [rbp+arg_18]
0x14005efdf  mov     [rsp+130h+var_D0], rax
0x14005efe4  lea     rax, [rbp+var_38]
0x14005efe8  mov     [rsp+130h+var_D8], rax
0x14005efed  lea     rax, [rbp+var_80]
0x14005eff1  mov     [rsp+130h+var_E0], rax
0x14005eff6  lea     rax, [rbp+var_30]
0x14005effa  mov     [rsp+130h+var_E8], rax
0x14005efff  lea     rax, [rbp+var_7C]
0x14005f003  mov     [rsp+130h+var_F0], rax
0x14005f008  lea     rax, [rbp+var_28]
0x14005f00c  mov     [rsp+130h+var_F8], rax
0x14005f011  lea     rax, [rbp+var_78]
0x14005f015  mov     [rsp+130h+var_100], rax
0x14005f01a  lea     rax, [rbp+var_20]
0x14005f01e  mov     [rsp+130h+var_108], rax
0x14005f023  lea     rax, [rbp+var_70]
0x14005f027  mov     [rsp+130h+var_110], rax
0x14005f02c  mov     [rbp+var_68], rsi
0x14005f030  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564563@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14005f035  jmp     loc_14005F0BF
0x14005f03a  call    ?zInternalStop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14005f03f  call    ?Provider@LogProvider@@SAPEBU_tlgProvider_t@@XZ; LogProvider::Provider(void)
0x14005f044  mov     rdi, rax
0x14005f047  mov     ecx, [rax]
0x14005f049  cmp     ecx, 4
0x14005f04c  jbe     short loc_14005F0BF
0x14005f04e  mov     rdx, 400000000000h
0x14005f058  mov     rcx, rax
0x14005f05b  call    _tlgKeywordOn
0x14005f060  test    al, al
0x14005f062  jz      short loc_14005F0BF
0x14005f064  mov     [rbp+arg_18], rsi
0x14005f068  call    cs:__imp_GetCurrentThreadId
0x14005f06e  mov     r8, [rbx+110h]
0x14005f075  lea     rdx, byte_14008E367
0x14005f07c  mov     [rbp+arg_0], eax
0x14005f07f  mov     rcx, rdi
0x14005f082  mov     eax, [r8+48h]
0x14005f086  add     r8, 8
0x14005f08a  mov     [rbp+arg_10], eax
0x14005f08d  mov     eax, 1000000h
0x14005f092  mov     [rbp+var_70], rax
0x14005f096  lea     rax, [rbp+arg_18]
0x14005f09a  mov     [rsp+130h+var_F8], rax
0x14005f09f  lea     rax, [rbp+arg_0]
0x14005f0a3  mov     [rsp+130h+var_100], rax
0x14005f0a8  lea     rax, [rbp+arg_10]
0x14005f0ac  mov     [rsp+130h+var_108], rax
0x14005f0b1  lea     rax, [rbp+var_70]
0x14005f0b5  mov     [rsp+130h+var_110], rax
0x14005f0ba  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@43@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14005f0bf  mov     rcx, rbx
0x14005f0c2  mov     rbx, [rsp+130h+arg_8]
0x14005f0ca  add     rsp, 120h
0x14005f0d1  pop     rdi
0x14005f0d2  pop     rsi
0x14005f0d3  pop     rbp
0x14005f0d4  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
