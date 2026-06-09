# MDMPushProvider::InitializeActivity::StopActivity(void)

- ea: `0x140017dd0`
- end: `0x140018002`
- name: `?StopActivity@InitializeActivity@MDMPushProvider@@MEAAXXZ`
- size: `562`
- prototype: `void __fastcall(MDMPushProvider::InitializeActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001010`
- `0x14000169c`
- `0x140016a00`
- `0x140017078`
- `0x140017dd0`
- `0x14001823c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017f9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140017f9d`

## pseudocode

```c
void __fastcall MDMPushProvider::InitializeActivity::StopActivity(MDMPushProvider::InitializeActivity *this)
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
        (unsigned int)word_14002085A,
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
        (unsigned int)&byte_140020807,
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
0x140017dd0  push    rbp
0x140017dd2  push    rbx
0x140017dd3  push    rdi
0x140017dd4  lea     rbp, [rsp+10h]
0x140017dd9  sub     rsp, 130h
0x140017de0  mov     rdi, [rcx+110h]
0x140017de7  mov     rbx, rcx
0x140017dea  mov     eax, [rdi+48h]
0x140017ded  test    eax, eax
0x140017def  jns     loc_140017F89
0x140017df5  add     rdi, 50h ; 'P'
0x140017df9  cmp     eax, [rdi+8]
0x140017dfc  jnz     loc_140017F89
0x140017e02  test    rdi, rdi
0x140017e05  jz      loc_140017F89
0x140017e0b  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140017e10  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140017e15  mov     r9, rax
0x140017e18  mov     ecx, [rax]
0x140017e1a  cmp     ecx, 5
0x140017e1d  jbe     loc_140017FF0
0x140017e23  mov     rax, [rdi+70h]
0x140017e27  lea     rdx, word_14002085A
0x140017e2e  mov     rcx, [rdi+30h]
0x140017e32  mov     [rbp+var_60], rax
0x140017e36  mov     eax, [rdi+68h]
0x140017e39  mov     r8, [rbx+110h]
0x140017e40  mov     dword ptr [rbp+arg_10], eax
0x140017e43  add     r8, 8
0x140017e47  mov     rax, [rdi+60h]
0x140017e4b  mov     [rbp+var_58], rax
0x140017e4f  mov     rax, [rdi+58h]
0x140017e53  mov     [rbp+var_50], rax
0x140017e57  mov     eax, [rdi+50h]
0x140017e5a  mov     [rbp+arg_18], eax
0x140017e5d  mov     rax, [rdi+48h]
0x140017e61  mov     [rbp+var_48], rax
0x140017e65  mov     eax, [rdi+20h]
0x140017e68  mov     [rbp+var_80], eax
0x140017e6b  mov     rax, [rdi+18h]
0x140017e6f  mov     [rbp+var_40], rax
0x140017e73  mov     eax, [rdi]
0x140017e75  mov     [rbp+var_7C], eax
0x140017e78  mov     rax, [rdi+80h]
0x140017e7f  mov     [rbp+var_38], rax
0x140017e83  mov     eax, [rdi+40h]
0x140017e86  mov     [rbp+var_78], eax
0x140017e89  mov     rax, [rdi+38h]
0x140017e8d  mov     [rbp+var_30], rax
0x140017e91  mov     eax, [rdi+8]
0x140017e94  mov     [rbp+var_74], eax
0x140017e97  lea     rax, [rbp+var_70]
0x140017e9b  mov     [rsp+140h+var_90], rax
0x140017ea3  lea     rax, [rbp+arg_0]
0x140017ea7  mov     [rsp+140h+var_98], rax
0x140017eaf  lea     rax, [rbp+arg_8]
0x140017eb3  mov     [rsp+140h+var_A0], rax
0x140017ebb  lea     rax, [rbp+var_68]
0x140017ebf  mov     [rsp+140h+var_A8], rax
0x140017ec7  lea     rax, [rbp+var_60]
0x140017ecb  mov     [rsp+140h+var_B0], rax
0x140017ed3  lea     rax, [rbp+arg_10]
0x140017ed7  mov     [rsp+140h+var_B8], rax
0x140017edf  lea     rax, [rbp+var_58]
0x140017ee3  mov     [rsp+140h+var_C0], rax
0x140017eeb  lea     rax, [rbp+var_50]
0x140017eef  mov     [rsp+140h+var_C8], rax
0x140017ef4  lea     rax, [rbp+arg_18]
0x140017ef8  mov     [rsp+140h+var_D0], rax
0x140017efd  lea     rax, [rbp+var_48]
0x140017f01  mov     [rsp+140h+var_D8], rax
0x140017f06  lea     rax, [rbp+var_80]
0x140017f0a  mov     [rsp+140h+var_E0], rax
0x140017f0f  lea     rax, [rbp+var_40]
0x140017f13  mov     [rsp+140h+var_E8], rax
0x140017f18  lea     rax, [rbp+var_7C]
0x140017f1c  mov     [rsp+140h+var_F0], rax
0x140017f21  lea     rax, [rbp+var_38]
0x140017f25  mov     [rsp+140h+var_F8], rax
0x140017f2a  lea     rax, [rbp+var_78]
0x140017f2e  mov     [rsp+140h+var_100], rax
0x140017f33  lea     rax, [rbp+var_30]
0x140017f37  mov     [rsp+140h+var_108], rax
0x140017f3c  lea     rax, [rbp+var_74]
0x140017f40  mov     [rbp+var_70], rcx
0x140017f44  mov     ecx, [rdi+44h]
0x140017f47  mov     [rsp+140h+var_110], rax
0x140017f4c  lea     rax, [rbp+var_28]
0x140017f50  mov     [rbp+arg_0], ecx
0x140017f53  mov     ecx, [rdi+10h]
0x140017f56  mov     [rbp+arg_8], ecx
0x140017f59  mov     rcx, [rdi+78h]
0x140017f5d  mov     [rsp+140h+var_118], rax
0x140017f62  lea     rax, [rbp+var_20]
0x140017f66  mov     [rbp+var_68], rcx
0x140017f6a  mov     rcx, r9
0x140017f6d  mov     [rsp+140h+var_120], rax
0x140017f72  mov     [rbp+var_28], 1000000h
0x140017f7a  mov     [rbp+var_20], 0
0x140017f82  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140017f87  jmp     short loc_140017FF0
0x140017f89  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140017f8e  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140017f93  mov     rdi, rax
0x140017f96  mov     ecx, [rax]
0x140017f98  cmp     ecx, 5
0x140017f9b  jbe     short loc_140017FF0
0x140017f9d  call    cs:__imp_GetCurrentThreadId
0x140017fa4  nop     dword ptr [rax+rax+00h]
0x140017fa9  mov     r8, [rbx+110h]
0x140017fb0  lea     rdx, byte_140020807
0x140017fb7  mov     [rbp+arg_0], eax
0x140017fba  lea     rax, [rbp+arg_0]
0x140017fbe  mov     [rsp+140h+var_110], rax
0x140017fc3  lea     rax, [rbp+arg_8]
0x140017fc7  mov     [rsp+140h+var_118], rax
0x140017fcc  lea     rax, [rbp+arg_10]
0x140017fd0  mov     ecx, [r8+48h]
0x140017fd4  add     r8, 8
0x140017fd8  mov     [rbp+arg_8], ecx
0x140017fdb  mov     rcx, rdi
0x140017fde  mov     [rsp+140h+var_120], rax
0x140017fe3  mov     [rbp+arg_10], 0
0x140017feb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140017ff0  mov     rcx, rbx
0x140017ff3  add     rsp, 130h
0x140017ffa  pop     rdi
0x140017ffb  pop     rbx
0x140017ffc  pop     rbp
0x140017ffd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
