# HostNameVerifierProvider::VerifyAllInstalled::StopActivity(void)

- ea: `0x14000e430`
- end: `0x14000e652`
- name: `?StopActivity@VerifyAllInstalled@HostNameVerifierProvider@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(HostNameVerifierProvider::VerifyAllInstalled *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140001010`
- `0x1400012cc`
- `0x140001b4c`
- `0x14000d438`
- `0x14000da38`
- `0x14000e430`
- `0x140010cf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e5f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e5f2`

## pseudocode

```c
void __fastcall HostNameVerifierProvider::VerifyAllInstalled::StopActivity(
        HostNameVerifierProvider::VerifyAllInstalled *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // [rsp+A0h] [rbp-19h] BYREF
  int v19; // [rsp+A4h] [rbp-15h] BYREF
  int *v20; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v21; // [rsp+B0h] [rbp-9h] BYREF
  int *v22; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v23; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v24; // [rsp+C8h] [rbp+Fh] BYREF
  int *v25; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v26; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v27; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v28; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v29[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v30; // [rsp+120h] [rbp+67h] BYREF
  int v31; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v32; // [rsp+130h] [rbp+77h] BYREF
  int v33; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = HostNameVerifierProvider::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7) )
    {
      v9 = (int *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v30 = v4[26];
      v22 = (int *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v31 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v32) = v4[8];
      v25 = (int *)*((_QWORD *)v4 + 3);
      v33 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v18 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v19 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v20 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_140016035,
        v10 + 8,
        v8,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v19,
        &v27,
        (__int64)&v18,
        &v26,
        (__int64)&v33,
        &v25,
        (__int64)&v32,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        (__int64)&v30,
        &v21,
        &v20);
    }
  }
  else
  {
    wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = HostNameVerifierProvider::Provider(v11);
    v14 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v16 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)word_140015FE2,
        v16 + 8,
        v17,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000e430  push    rbp
0x14000e432  push    rbx
0x14000e433  push    rdi
0x14000e434  lea     rbp, [rsp-47h]
0x14000e439  sub     rsp, 100h
0x14000e440  mov     rdi, [rcx+110h]
0x14000e447  mov     rbx, rcx
0x14000e44a  mov     eax, [rdi+48h]
0x14000e44d  test    eax, eax
0x14000e44f  jns     loc_14000E5C8
0x14000e455  add     rdi, 50h ; 'P'
0x14000e459  cmp     eax, [rdi+8]
0x14000e45c  jnz     loc_14000E5C8
0x14000e462  test    rdi, rdi
0x14000e465  jz      loc_14000E5C8
0x14000e46b  call    ?zInternalStop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000e470  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000e475  mov     r9, rax
0x14000e478  mov     ecx, [rax]
0x14000e47a  cmp     ecx, 5
0x14000e47d  jbe     loc_14000E640
0x14000e483  mov     rdx, 400000000000h
0x14000e48d  mov     rcx, rax
0x14000e490  call    _tlgKeywordOn
0x14000e495  test    al, al
0x14000e497  jz      loc_14000E640
0x14000e49d  mov     rax, [rdi+70h]
0x14000e4a1  lea     rdx, byte_140016035
0x14000e4a8  mov     rcx, [rdi+78h]
0x14000e4ac  mov     r8, [rbx+110h]
0x14000e4b3  mov     [rbp+57h+var_60], rax
0x14000e4b7  add     r8, 8
0x14000e4bb  mov     eax, [rdi+68h]
0x14000e4be  mov     [rbp+57h+arg_0], eax
0x14000e4c1  mov     rax, [rdi+60h]
0x14000e4c5  mov     [rbp+57h+var_58], rax
0x14000e4c9  mov     rax, [rdi+58h]
0x14000e4cd  mov     [rbp+57h+var_50], rax
0x14000e4d1  mov     eax, [rdi+50h]
0x14000e4d4  mov     [rbp+57h+arg_8], eax
0x14000e4d7  mov     rax, [rdi+48h]
0x14000e4db  mov     [rbp+57h+var_48], rax
0x14000e4df  mov     eax, [rdi+20h]
0x14000e4e2  mov     dword ptr [rbp+57h+arg_10], eax
0x14000e4e5  mov     rax, [rdi+18h]
0x14000e4e9  mov     [rbp+57h+var_40], rax
0x14000e4ed  mov     eax, [rdi]
0x14000e4ef  mov     [rbp+57h+arg_18], eax
0x14000e4f2  mov     rax, [rdi+80h]
0x14000e4f9  mov     [rbp+57h+var_38], rax
0x14000e4fd  mov     eax, [rdi+40h]
0x14000e500  mov     [rbp+57h+var_70], eax
0x14000e503  mov     rax, [rdi+38h]
0x14000e507  mov     [rbp+57h+var_30], rax
0x14000e50b  mov     eax, [rdi+8]
0x14000e50e  mov     [rbp+57h+var_6C], eax
0x14000e511  mov     eax, 1000000h
0x14000e516  mov     [rbp+57h+var_28], rax
0x14000e51a  mov     [rbp+57h+var_20], rax
0x14000e51e  lea     rax, [rbp+57h+var_68]
0x14000e522  mov     [rsp+110h+var_78], rax
0x14000e52a  lea     rax, [rbp+57h+var_60]
0x14000e52e  mov     [rsp+110h+var_80], rax
0x14000e536  lea     rax, [rbp+57h+arg_0]
0x14000e53a  mov     [rsp+110h+var_88], rax
0x14000e542  lea     rax, [rbp+57h+var_58]
0x14000e546  mov     [rsp+110h+var_90], rax
0x14000e54e  lea     rax, [rbp+57h+var_50]
0x14000e552  mov     [rsp+110h+var_98], rax
0x14000e557  lea     rax, [rbp+57h+arg_8]
0x14000e55b  mov     [rsp+110h+var_A0], rax
0x14000e560  lea     rax, [rbp+57h+var_48]
0x14000e564  mov     [rsp+110h+var_A8], rax
0x14000e569  lea     rax, [rbp+57h+arg_10]
0x14000e56d  mov     [rsp+110h+var_B0], rax
0x14000e572  lea     rax, [rbp+57h+var_40]
0x14000e576  mov     [rsp+110h+var_B8], rax
0x14000e57b  lea     rax, [rbp+57h+arg_18]
0x14000e57f  mov     [rsp+110h+var_C0], rax
0x14000e584  lea     rax, [rbp+57h+var_38]
0x14000e588  mov     [rsp+110h+var_C8], rax
0x14000e58d  lea     rax, [rbp+57h+var_70]
0x14000e591  mov     [rsp+110h+var_D0], rax
0x14000e596  lea     rax, [rbp+57h+var_30]
0x14000e59a  mov     [rsp+110h+var_D8], rax
0x14000e59f  lea     rax, [rbp+57h+var_6C]
0x14000e5a3  mov     [rsp+110h+var_E0], rax
0x14000e5a8  lea     rax, [rbp+57h+var_28]
0x14000e5ac  mov     [rsp+110h+var_E8], rax
0x14000e5b1  lea     rax, [rbp+57h+var_20]
0x14000e5b5  mov     [rbp+57h+var_68], rcx
0x14000e5b9  mov     rcx, r9
0x14000e5bc  mov     [rsp+110h+var_F0], rax
0x14000e5c1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000e5c6  jmp     short loc_14000E640
0x14000e5c8  call    ?zInternalStop@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000e5cd  call    ?Provider@HostNameVerifierProvider@@SAPEBU_tlgProvider_t@@XZ; HostNameVerifierProvider::Provider(void)
0x14000e5d2  mov     rdi, rax
0x14000e5d5  mov     ecx, [rax]
0x14000e5d7  cmp     ecx, 5
0x14000e5da  jbe     short loc_14000E640
0x14000e5dc  mov     rdx, 400000000000h
0x14000e5e6  mov     rcx, rax
0x14000e5e9  call    _tlgKeywordOn
0x14000e5ee  test    al, al
0x14000e5f0  jz      short loc_14000E640
0x14000e5f2  call    cs:__imp_GetCurrentThreadId
0x14000e5f8  mov     r8, [rbx+110h]
0x14000e5ff  lea     rdx, word_140015FE2
0x14000e606  mov     [rbp+57h+arg_0], eax
0x14000e609  mov     rcx, rdi
0x14000e60c  mov     eax, [r8+48h]
0x14000e610  add     r8, 8
0x14000e614  mov     [rbp+57h+arg_8], eax
0x14000e617  mov     eax, 1000000h
0x14000e61c  mov     [rbp+57h+arg_10], rax
0x14000e620  lea     rax, [rbp+57h+arg_0]
0x14000e624  mov     [rsp+110h+var_E0], rax
0x14000e629  lea     rax, [rbp+57h+arg_8]
0x14000e62d  mov     [rsp+110h+var_E8], rax
0x14000e632  lea     rax, [rbp+57h+arg_10]
0x14000e636  mov     [rsp+110h+var_F0], rax
0x14000e63b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000e640  mov     rcx, rbx
0x14000e643  add     rsp, 100h
0x14000e64a  pop     rdi
0x14000e64b  pop     rbx
0x14000e64c  pop     rbp
0x14000e64d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VHostNameVerifierProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<HostNameVerifierProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
