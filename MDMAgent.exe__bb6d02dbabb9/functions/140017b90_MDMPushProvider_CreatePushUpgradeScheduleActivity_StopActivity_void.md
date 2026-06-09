# MDMPushProvider::CreatePushUpgradeScheduleActivity::StopActivity(void)

- ea: `0x140017b90`
- end: `0x140017dc2`
- name: `?StopActivity@CreatePushUpgradeScheduleActivity@MDMPushProvider@@MEAAXXZ`
- size: `562`
- prototype: `void __fastcall(MDMPushProvider::CreatePushUpgradeScheduleActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001010`
- `0x14000169c`
- `0x140016a00`
- `0x140017078`
- `0x140017b90`
- `0x14001823c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017d5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017d5d`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushUpgradeScheduleActivity::StopActivity(
        MDMPushProvider::CreatePushUpgradeScheduleActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // r9d
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v29[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v30; // [rsp+150h] [rbp+10h] BYREF
  int v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  int v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v21 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      v33 = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v8;
      v30 = v4[17];
      v31 = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)byte_1400206AB,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v32,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = MDMPushProvider::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v30 = CurrentThreadId;
      v31 = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_140020CC9,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x140017b90  push    rbp
0x140017b92  push    rbx
0x140017b93  push    rdi
0x140017b94  lea     rbp, [rsp+10h]
0x140017b99  sub     rsp, 130h
0x140017ba0  mov     rdi, [rcx+110h]
0x140017ba7  mov     rbx, rcx
0x140017baa  mov     eax, [rdi+48h]
0x140017bad  test    eax, eax
0x140017baf  jns     loc_140017D49
0x140017bb5  add     rdi, 50h ; 'P'
0x140017bb9  cmp     eax, [rdi+8]
0x140017bbc  jnz     loc_140017D49
0x140017bc2  test    rdi, rdi
0x140017bc5  jz      loc_140017D49
0x140017bcb  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140017bd0  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140017bd5  mov     r9, rax
0x140017bd8  mov     ecx, [rax]
0x140017bda  cmp     ecx, 5
0x140017bdd  jbe     loc_140017DB0
0x140017be3  mov     rax, [rdi+70h]
0x140017be7  lea     rdx, byte_1400206AB
0x140017bee  mov     rcx, [rdi+30h]
0x140017bf2  mov     [rbp+var_60], rax
0x140017bf6  mov     eax, [rdi+68h]
0x140017bf9  mov     r8, [rbx+110h]
0x140017c00  mov     dword ptr [rbp+arg_10], eax
0x140017c03  add     r8, 8
0x140017c07  mov     rax, [rdi+60h]
0x140017c0b  mov     [rbp+var_58], rax
0x140017c0f  mov     rax, [rdi+58h]
0x140017c13  mov     [rbp+var_50], rax
0x140017c17  mov     eax, [rdi+50h]
0x140017c1a  mov     [rbp+arg_18], eax
0x140017c1d  mov     rax, [rdi+48h]
0x140017c21  mov     [rbp+var_48], rax
0x140017c25  mov     eax, [rdi+20h]
0x140017c28  mov     [rbp+var_80], eax
0x140017c2b  mov     rax, [rdi+18h]
0x140017c2f  mov     [rbp+var_40], rax
0x140017c33  mov     eax, [rdi]
0x140017c35  mov     [rbp+var_7C], eax
0x140017c38  mov     rax, [rdi+80h]
0x140017c3f  mov     [rbp+var_38], rax
0x140017c43  mov     eax, [rdi+40h]
0x140017c46  mov     [rbp+var_78], eax
0x140017c49  mov     rax, [rdi+38h]
0x140017c4d  mov     [rbp+var_30], rax
0x140017c51  mov     eax, [rdi+8]
0x140017c54  mov     [rbp+var_74], eax
0x140017c57  lea     rax, [rbp+var_70]
0x140017c5b  mov     [rsp+140h+var_90], rax
0x140017c63  lea     rax, [rbp+arg_0]
0x140017c67  mov     [rsp+140h+var_98], rax
0x140017c6f  lea     rax, [rbp+arg_8]
0x140017c73  mov     [rsp+140h+var_A0], rax
0x140017c7b  lea     rax, [rbp+var_68]
0x140017c7f  mov     [rsp+140h+var_A8], rax
0x140017c87  lea     rax, [rbp+var_60]
0x140017c8b  mov     [rsp+140h+var_B0], rax
0x140017c93  lea     rax, [rbp+arg_10]
0x140017c97  mov     [rsp+140h+var_B8], rax
0x140017c9f  lea     rax, [rbp+var_58]
0x140017ca3  mov     [rsp+140h+var_C0], rax
0x140017cab  lea     rax, [rbp+var_50]
0x140017caf  mov     [rsp+140h+var_C8], rax
0x140017cb4  lea     rax, [rbp+arg_18]
0x140017cb8  mov     [rsp+140h+var_D0], rax
0x140017cbd  lea     rax, [rbp+var_48]
0x140017cc1  mov     [rsp+140h+var_D8], rax
0x140017cc6  lea     rax, [rbp+var_80]
0x140017cca  mov     [rsp+140h+var_E0], rax
0x140017ccf  lea     rax, [rbp+var_40]
0x140017cd3  mov     [rsp+140h+var_E8], rax
0x140017cd8  lea     rax, [rbp+var_7C]
0x140017cdc  mov     [rsp+140h+var_F0], rax
0x140017ce1  lea     rax, [rbp+var_38]
0x140017ce5  mov     [rsp+140h+var_F8], rax
0x140017cea  lea     rax, [rbp+var_78]
0x140017cee  mov     [rsp+140h+var_100], rax
0x140017cf3  lea     rax, [rbp+var_30]
0x140017cf7  mov     [rsp+140h+var_108], rax
0x140017cfc  lea     rax, [rbp+var_74]
0x140017d00  mov     [rbp+var_70], rcx
0x140017d04  mov     ecx, [rdi+44h]
0x140017d07  mov     [rsp+140h+var_110], rax
0x140017d0c  lea     rax, [rbp+var_28]
0x140017d10  mov     [rbp+arg_0], ecx
0x140017d13  mov     ecx, [rdi+10h]
0x140017d16  mov     [rbp+arg_8], ecx
0x140017d19  mov     rcx, [rdi+78h]
0x140017d1d  mov     [rsp+140h+var_118], rax
0x140017d22  lea     rax, [rbp+var_20]
0x140017d26  mov     [rbp+var_68], rcx
0x140017d2a  mov     rcx, r9
0x140017d2d  mov     [rsp+140h+var_120], rax
0x140017d32  mov     [rbp+var_28], 1000000h
0x140017d3a  mov     [rbp+var_20], 0
0x140017d42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140017d47  jmp     short loc_140017DB0
0x140017d49  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140017d4e  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140017d53  mov     rdi, rax
0x140017d56  mov     ecx, [rax]
0x140017d58  cmp     ecx, 5
0x140017d5b  jbe     short loc_140017DB0
0x140017d5d  call    cs:__imp_GetCurrentThreadId
0x140017d64  nop     dword ptr [rax+rax+00h]
0x140017d69  mov     r8, [rbx+110h]
0x140017d70  lea     rdx, byte_140020CC9
0x140017d77  mov     [rbp+arg_0], eax
0x140017d7a  lea     rax, [rbp+arg_0]
0x140017d7e  mov     [rsp+140h+var_110], rax
0x140017d83  lea     rax, [rbp+arg_8]
0x140017d87  mov     [rsp+140h+var_118], rax
0x140017d8c  lea     rax, [rbp+arg_10]
0x140017d90  mov     ecx, [r8+48h]
0x140017d94  add     r8, 8
0x140017d98  mov     [rbp+arg_8], ecx
0x140017d9b  mov     rcx, rdi
0x140017d9e  mov     [rsp+140h+var_120], rax
0x140017da3  mov     [rbp+arg_10], 0
0x140017dab  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140017db0  mov     rcx, rbx
0x140017db3  add     rsp, 130h
0x140017dba  pop     rdi
0x140017dbb  pop     rbx
0x140017dbc  pop     rbp
0x140017dbd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
