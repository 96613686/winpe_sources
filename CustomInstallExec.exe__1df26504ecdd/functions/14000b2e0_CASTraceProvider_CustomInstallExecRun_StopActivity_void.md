# CASTraceProvider::CustomInstallExecRun::StopActivity(void)

- ea: `0x14000b2e0`
- end: `0x14000b502`
- name: `?StopActivity@CustomInstallExecRun@CASTraceProvider@@MEAAXXZ`
- size: `546`
- prototype: `void __fastcall(CASTraceProvider::CustomInstallExecRun *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140001010`
- `0x140001bcc`
- `0x14000258c`
- `0x140009730`
- `0x14000a594`
- `0x14000b2e0`
- `0x14000babc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b4a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b4a2`

## pseudocode

```c
void __fastcall CASTraceProvider::CustomInstallExecRun::StopActivity(CASTraceProvider::CustomInstallExecRun *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // rcx
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  int v19; // [rsp+A0h] [rbp-19h] BYREF
  int v20; // [rsp+A4h] [rbp-15h] BYREF
  const unsigned __int16 *v21; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v22; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v23; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v24; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v25; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v26; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v27; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v28; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v29; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v30[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v31; // [rsp+120h] [rbp+67h] BYREF
  int v32; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v33; // [rsp+130h] [rbp+77h] BYREF
  int v34; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = CASTraceProvider::Provider(v5);
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v7, v6) )
    {
      v9 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v31 = v4[26];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v33) = v4[8];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v34 = *v4;
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v19 = v4[16];
      v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v20 = v4[2];
      v29 = 0x1000000;
      v30[0] = 0x1000000;
      v21 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)&unk_140011F88,
        v10 + 8,
        v8,
        (__int64)v30,
        (__int64)&v29,
        (__int64)&v20,
        &v28,
        (__int64)&v19,
        &v27,
        (__int64)&v34,
        &v26,
        (__int64)&v33,
        &v25,
        (__int64)&v32,
        &v24,
        &v23,
        (__int64)&v31,
        &v22,
        &v21);
    }
  }
  else
  {
    wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v12 = CASTraceProvider::Provider(v11);
    v15 = (__int64)v12;
    if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13, v14) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      v31 = CurrentThreadId;
      v32 = *(_DWORD *)(v17 + 72);
      v33 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v15,
        (__int64)&dword_1400120B4,
        v17 + 8,
        v18,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x14000b2e0  push    rbp
0x14000b2e2  push    rbx
0x14000b2e3  push    rdi
0x14000b2e4  lea     rbp, [rsp-47h]
0x14000b2e9  sub     rsp, 100h
0x14000b2f0  mov     rdi, [rcx+110h]
0x14000b2f7  mov     rbx, rcx
0x14000b2fa  mov     eax, [rdi+48h]
0x14000b2fd  test    eax, eax
0x14000b2ff  jns     loc_14000B478
0x14000b305  add     rdi, 50h ; 'P'
0x14000b309  cmp     eax, [rdi+8]
0x14000b30c  jnz     loc_14000B478
0x14000b312  test    rdi, rdi
0x14000b315  jz      loc_14000B478
0x14000b31b  call    ?zInternalStop@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b320  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000b325  mov     r9, rax
0x14000b328  mov     ecx, [rax]
0x14000b32a  cmp     ecx, 5
0x14000b32d  jbe     loc_14000B4F0
0x14000b333  mov     rdx, 400000000000h
0x14000b33d  mov     rcx, rax
0x14000b340  call    _tlgKeywordOn
0x14000b345  test    al, al
0x14000b347  jz      loc_14000B4F0
0x14000b34d  mov     rax, [rdi+70h]
0x14000b351  lea     rdx, unk_140011F88
0x14000b358  mov     rcx, [rdi+78h]
0x14000b35c  mov     r8, [rbx+110h]
0x14000b363  mov     [rbp+57h+var_60], rax
0x14000b367  add     r8, 8
0x14000b36b  mov     eax, [rdi+68h]
0x14000b36e  mov     [rbp+57h+arg_0], eax
0x14000b371  mov     rax, [rdi+60h]
0x14000b375  mov     [rbp+57h+var_58], rax
0x14000b379  mov     rax, [rdi+58h]
0x14000b37d  mov     [rbp+57h+var_50], rax
0x14000b381  mov     eax, [rdi+50h]
0x14000b384  mov     [rbp+57h+arg_8], eax
0x14000b387  mov     rax, [rdi+48h]
0x14000b38b  mov     [rbp+57h+var_48], rax
0x14000b38f  mov     eax, [rdi+20h]
0x14000b392  mov     dword ptr [rbp+57h+arg_10], eax
0x14000b395  mov     rax, [rdi+18h]
0x14000b399  mov     [rbp+57h+var_40], rax
0x14000b39d  mov     eax, [rdi]
0x14000b39f  mov     [rbp+57h+arg_18], eax
0x14000b3a2  mov     rax, [rdi+80h]
0x14000b3a9  mov     [rbp+57h+var_38], rax
0x14000b3ad  mov     eax, [rdi+40h]
0x14000b3b0  mov     [rbp+57h+var_70], eax
0x14000b3b3  mov     rax, [rdi+38h]
0x14000b3b7  mov     [rbp+57h+var_30], rax
0x14000b3bb  mov     eax, [rdi+8]
0x14000b3be  mov     [rbp+57h+var_6C], eax
0x14000b3c1  mov     eax, 1000000h
0x14000b3c6  mov     [rbp+57h+var_28], rax
0x14000b3ca  mov     [rbp+57h+var_20], rax
0x14000b3ce  lea     rax, [rbp+57h+var_68]
0x14000b3d2  mov     [rsp+110h+var_78], rax
0x14000b3da  lea     rax, [rbp+57h+var_60]
0x14000b3de  mov     [rsp+110h+var_80], rax
0x14000b3e6  lea     rax, [rbp+57h+arg_0]
0x14000b3ea  mov     [rsp+110h+var_88], rax
0x14000b3f2  lea     rax, [rbp+57h+var_58]
0x14000b3f6  mov     [rsp+110h+var_90], rax
0x14000b3fe  lea     rax, [rbp+57h+var_50]
0x14000b402  mov     [rsp+110h+var_98], rax
0x14000b407  lea     rax, [rbp+57h+arg_8]
0x14000b40b  mov     [rsp+110h+var_A0], rax
0x14000b410  lea     rax, [rbp+57h+var_48]
0x14000b414  mov     [rsp+110h+var_A8], rax
0x14000b419  lea     rax, [rbp+57h+arg_10]
0x14000b41d  mov     [rsp+110h+var_B0], rax
0x14000b422  lea     rax, [rbp+57h+var_40]
0x14000b426  mov     [rsp+110h+var_B8], rax
0x14000b42b  lea     rax, [rbp+57h+arg_18]
0x14000b42f  mov     [rsp+110h+var_C0], rax
0x14000b434  lea     rax, [rbp+57h+var_38]
0x14000b438  mov     [rsp+110h+var_C8], rax
0x14000b43d  lea     rax, [rbp+57h+var_70]
0x14000b441  mov     [rsp+110h+var_D0], rax
0x14000b446  lea     rax, [rbp+57h+var_30]
0x14000b44a  mov     [rsp+110h+var_D8], rax
0x14000b44f  lea     rax, [rbp+57h+var_6C]
0x14000b453  mov     [rsp+110h+var_E0], rax
0x14000b458  lea     rax, [rbp+57h+var_28]
0x14000b45c  mov     [rsp+110h+var_E8], rax
0x14000b461  lea     rax, [rbp+57h+var_20]
0x14000b465  mov     [rbp+57h+var_68], rcx
0x14000b469  mov     rcx, r9
0x14000b46c  mov     [rsp+110h+var_F0], rax
0x14000b471  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000b476  jmp     short loc_14000B4F0
0x14000b478  call    ?zInternalStop@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x14000b47d  call    ?Provider@CASTraceProvider@@SAPEBU_tlgProvider_t@@XZ; CASTraceProvider::Provider(void)
0x14000b482  mov     rdi, rax
0x14000b485  mov     ecx, [rax]
0x14000b487  cmp     ecx, 5
0x14000b48a  jbe     short loc_14000B4F0
0x14000b48c  mov     rdx, 400000000000h
0x14000b496  mov     rcx, rax
0x14000b499  call    _tlgKeywordOn
0x14000b49e  test    al, al
0x14000b4a0  jz      short loc_14000B4F0
0x14000b4a2  call    cs:__imp_GetCurrentThreadId
0x14000b4a8  mov     r8, [rbx+110h]
0x14000b4af  lea     rdx, dword_1400120B4
0x14000b4b6  mov     [rbp+57h+arg_0], eax
0x14000b4b9  mov     rcx, rdi
0x14000b4bc  mov     eax, [r8+48h]
0x14000b4c0  add     r8, 8
0x14000b4c4  mov     [rbp+57h+arg_8], eax
0x14000b4c7  mov     eax, 1000000h
0x14000b4cc  mov     [rbp+57h+arg_10], rax
0x14000b4d0  lea     rax, [rbp+57h+arg_0]
0x14000b4d4  mov     [rsp+110h+var_E0], rax
0x14000b4d9  lea     rax, [rbp+57h+arg_8]
0x14000b4dd  mov     [rsp+110h+var_E8], rax
0x14000b4e2  lea     rax, [rbp+57h+arg_10]
0x14000b4e6  mov     [rsp+110h+var_F0], rax
0x14000b4eb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000b4f0  mov     rcx, rbx
0x14000b4f3  add     rsp, 100h
0x14000b4fa  pop     rdi
0x14000b4fb  pop     rbx
0x14000b4fc  pop     rbp
0x14000b4fd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
