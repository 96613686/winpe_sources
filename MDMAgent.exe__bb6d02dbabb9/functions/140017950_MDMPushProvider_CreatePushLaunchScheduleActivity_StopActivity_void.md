# MDMPushProvider::CreatePushLaunchScheduleActivity::StopActivity(void)

- ea: `0x140017950`
- end: `0x140017b82`
- name: `?StopActivity@CreatePushLaunchScheduleActivity@MDMPushProvider@@MEAAXXZ`
- size: `562`
- prototype: `void __fastcall(MDMPushProvider::CreatePushLaunchScheduleActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001010`
- `0x14000169c`
- `0x140016a00`
- `0x140017078`
- `0x140017950`
- `0x14001823c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017b1d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017b1d`

## pseudocode

```c
void __fastcall MDMPushProvider::CreatePushLaunchScheduleActivity::StopActivity(
        MDMPushProvider::CreatePushLaunchScheduleActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // r9d
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v29; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v20 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)&dword_140020524,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = MDMPushProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v10,
        (unsigned int)word_14002046A,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
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
0x140017950  push    rbp
0x140017952  push    rbx
0x140017953  push    rdi
0x140017954  lea     rbp, [rsp+10h]
0x140017959  sub     rsp, 130h
0x140017960  mov     rdi, [rcx+110h]
0x140017967  mov     rbx, rcx
0x14001796a  mov     eax, [rdi+48h]
0x14001796d  test    eax, eax
0x14001796f  jns     loc_140017B09
0x140017975  add     rdi, 50h ; 'P'
0x140017979  cmp     eax, [rdi+8]
0x14001797c  jnz     loc_140017B09
0x140017982  test    rdi, rdi
0x140017985  jz      loc_140017B09
0x14001798b  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140017990  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140017995  mov     r9, rax
0x140017998  mov     ecx, [rax]
0x14001799a  cmp     ecx, 5
0x14001799d  jbe     loc_140017B70
0x1400179a3  mov     rax, [rdi+70h]
0x1400179a7  lea     rdx, dword_140020524
0x1400179ae  mov     rcx, [rdi+30h]
0x1400179b2  mov     [rbp+var_60], rax
0x1400179b6  mov     eax, [rdi+68h]
0x1400179b9  mov     r8, [rbx+110h]
0x1400179c0  mov     dword ptr [rbp+arg_10], eax
0x1400179c3  add     r8, 8
0x1400179c7  mov     rax, [rdi+60h]
0x1400179cb  mov     [rbp+var_58], rax
0x1400179cf  mov     rax, [rdi+58h]
0x1400179d3  mov     [rbp+var_50], rax
0x1400179d7  mov     eax, [rdi+50h]
0x1400179da  mov     [rbp+arg_18], eax
0x1400179dd  mov     rax, [rdi+48h]
0x1400179e1  mov     [rbp+var_48], rax
0x1400179e5  mov     eax, [rdi+20h]
0x1400179e8  mov     [rbp+var_80], eax
0x1400179eb  mov     rax, [rdi+18h]
0x1400179ef  mov     [rbp+var_40], rax
0x1400179f3  mov     eax, [rdi]
0x1400179f5  mov     [rbp+var_7C], eax
0x1400179f8  mov     rax, [rdi+80h]
0x1400179ff  mov     [rbp+var_38], rax
0x140017a03  mov     eax, [rdi+40h]
0x140017a06  mov     [rbp+var_78], eax
0x140017a09  mov     rax, [rdi+38h]
0x140017a0d  mov     [rbp+var_30], rax
0x140017a11  mov     eax, [rdi+8]
0x140017a14  mov     [rbp+var_74], eax
0x140017a17  lea     rax, [rbp+var_70]
0x140017a1b  mov     [rsp+140h+var_90], rax
0x140017a23  lea     rax, [rbp+arg_0]
0x140017a27  mov     [rsp+140h+var_98], rax
0x140017a2f  lea     rax, [rbp+arg_8]
0x140017a33  mov     [rsp+140h+var_A0], rax
0x140017a3b  lea     rax, [rbp+var_68]
0x140017a3f  mov     [rsp+140h+var_A8], rax
0x140017a47  lea     rax, [rbp+var_60]
0x140017a4b  mov     [rsp+140h+var_B0], rax
0x140017a53  lea     rax, [rbp+arg_10]
0x140017a57  mov     [rsp+140h+var_B8], rax
0x140017a5f  lea     rax, [rbp+var_58]
0x140017a63  mov     [rsp+140h+var_C0], rax
0x140017a6b  lea     rax, [rbp+var_50]
0x140017a6f  mov     [rsp+140h+var_C8], rax
0x140017a74  lea     rax, [rbp+arg_18]
0x140017a78  mov     [rsp+140h+var_D0], rax
0x140017a7d  lea     rax, [rbp+var_48]
0x140017a81  mov     [rsp+140h+var_D8], rax
0x140017a86  lea     rax, [rbp+var_80]
0x140017a8a  mov     [rsp+140h+var_E0], rax
0x140017a8f  lea     rax, [rbp+var_40]
0x140017a93  mov     [rsp+140h+var_E8], rax
0x140017a98  lea     rax, [rbp+var_7C]
0x140017a9c  mov     [rsp+140h+var_F0], rax
0x140017aa1  lea     rax, [rbp+var_38]
0x140017aa5  mov     [rsp+140h+var_F8], rax
0x140017aaa  lea     rax, [rbp+var_78]
0x140017aae  mov     [rsp+140h+var_100], rax
0x140017ab3  lea     rax, [rbp+var_30]
0x140017ab7  mov     [rsp+140h+var_108], rax
0x140017abc  lea     rax, [rbp+var_74]
0x140017ac0  mov     [rbp+var_70], rcx
0x140017ac4  mov     ecx, [rdi+44h]
0x140017ac7  mov     [rsp+140h+var_110], rax
0x140017acc  lea     rax, [rbp+var_28]
0x140017ad0  mov     [rbp+arg_0], ecx
0x140017ad3  mov     ecx, [rdi+10h]
0x140017ad6  mov     [rbp+arg_8], ecx
0x140017ad9  mov     rcx, [rdi+78h]
0x140017add  mov     [rsp+140h+var_118], rax
0x140017ae2  lea     rax, [rbp+var_20]
0x140017ae6  mov     [rbp+var_68], rcx
0x140017aea  mov     rcx, r9
0x140017aed  mov     [rsp+140h+var_120], rax
0x140017af2  mov     [rbp+var_28], 1000000h
0x140017afa  mov     [rbp+var_20], 0
0x140017b02  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140017b07  jmp     short loc_140017B70
0x140017b09  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140017b0e  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140017b13  mov     rdi, rax
0x140017b16  mov     ecx, [rax]
0x140017b18  cmp     ecx, 5
0x140017b1b  jbe     short loc_140017B70
0x140017b1d  call    cs:__imp_GetCurrentThreadId
0x140017b24  nop     dword ptr [rax+rax+00h]
0x140017b29  mov     r8, [rbx+110h]
0x140017b30  lea     rdx, word_14002046A
0x140017b37  mov     [rbp+arg_0], eax
0x140017b3a  lea     rax, [rbp+arg_0]
0x140017b3e  mov     [rsp+140h+var_110], rax
0x140017b43  lea     rax, [rbp+arg_8]
0x140017b47  mov     [rsp+140h+var_118], rax
0x140017b4c  lea     rax, [rbp+arg_10]
0x140017b50  mov     ecx, [r8+48h]
0x140017b54  add     r8, 8
0x140017b58  mov     [rbp+arg_8], ecx
0x140017b5b  mov     rcx, rdi
0x140017b5e  mov     [rsp+140h+var_120], rax
0x140017b63  mov     [rbp+arg_10], 0
0x140017b6b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140017b70  mov     rcx, rbx
0x140017b73  add     rsp, 130h
0x140017b7a  pop     rdi
0x140017b7b  pop     rbx
0x140017b7c  pop     rbp
0x140017b7d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
