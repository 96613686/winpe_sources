# MDMPushProvider::InitializeActivity::StopActivity(void)

- ea: `0x140017110`
- end: `0x14001733c`
- name: `?StopActivity@InitializeActivity@MDMPushProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(MDMPushProvider::InitializeActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140001010`
- `0x140001698`
- `0x140015d70`
- `0x1400163d8`
- `0x140017110`
- `0x140017568`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400172dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400172dd`

## pseudocode

```c
void __fastcall MDMPushProvider::InitializeActivity::StopActivity(MDMPushProvider::InitializeActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v24; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+110h] [rbp-30h] BYREF
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
    v6 = MDMPushProvider::Provider(v5);
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v7;
      v29 = v4[17];
      v30 = v4[4];
      v19 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)word_14001F85A,
        v8 + 8,
        (__int64)v6,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v14,
        &v23,
        (__int64)&v32,
        &v22,
        &v21,
        (__int64)&v31,
        &v20,
        &v19,
        (__int64)&v30,
        (__int64)&v29,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = MDMPushProvider::Provider(v9);
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&byte_14001F807,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x140017110  push    rbp
0x140017112  push    rbx
0x140017113  push    rdi
0x140017114  lea     rbp, [rsp+10h]
0x140017119  sub     rsp, 130h
0x140017120  mov     rdi, [rcx+110h]
0x140017127  mov     rbx, rcx
0x14001712a  mov     eax, [rdi+48h]
0x14001712d  test    eax, eax
0x14001712f  jns     loc_1400172C9
0x140017135  add     rdi, 50h ; 'P'
0x140017139  cmp     eax, [rdi+8]
0x14001713c  jnz     loc_1400172C9
0x140017142  test    rdi, rdi
0x140017145  jz      loc_1400172C9
0x14001714b  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140017150  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x140017155  mov     r9, rax
0x140017158  mov     ecx, [rax]
0x14001715a  cmp     ecx, 5
0x14001715d  jbe     loc_14001732A
0x140017163  mov     rax, [rdi+70h]
0x140017167  lea     rdx, word_14001F85A
0x14001716e  mov     rcx, [rdi+30h]
0x140017172  mov     [rbp+var_60], rax
0x140017176  mov     eax, [rdi+68h]
0x140017179  mov     r8, [rbx+110h]
0x140017180  mov     dword ptr [rbp+arg_10], eax
0x140017183  add     r8, 8
0x140017187  mov     rax, [rdi+60h]
0x14001718b  mov     [rbp+var_58], rax
0x14001718f  mov     rax, [rdi+58h]
0x140017193  mov     [rbp+var_50], rax
0x140017197  mov     eax, [rdi+50h]
0x14001719a  mov     [rbp+arg_18], eax
0x14001719d  mov     rax, [rdi+48h]
0x1400171a1  mov     [rbp+var_48], rax
0x1400171a5  mov     eax, [rdi+20h]
0x1400171a8  mov     [rbp+var_80], eax
0x1400171ab  mov     rax, [rdi+18h]
0x1400171af  mov     [rbp+var_40], rax
0x1400171b3  mov     eax, [rdi]
0x1400171b5  mov     [rbp+var_7C], eax
0x1400171b8  mov     rax, [rdi+80h]
0x1400171bf  mov     [rbp+var_38], rax
0x1400171c3  mov     eax, [rdi+40h]
0x1400171c6  mov     [rbp+var_78], eax
0x1400171c9  mov     rax, [rdi+38h]
0x1400171cd  mov     [rbp+var_30], rax
0x1400171d1  mov     eax, [rdi+8]
0x1400171d4  mov     [rbp+var_74], eax
0x1400171d7  lea     rax, [rbp+var_70]
0x1400171db  mov     [rsp+140h+var_90], rax
0x1400171e3  lea     rax, [rbp+arg_0]
0x1400171e7  mov     [rsp+140h+var_98], rax
0x1400171ef  lea     rax, [rbp+arg_8]
0x1400171f3  mov     [rsp+140h+var_A0], rax
0x1400171fb  lea     rax, [rbp+var_68]
0x1400171ff  mov     [rsp+140h+var_A8], rax
0x140017207  lea     rax, [rbp+var_60]
0x14001720b  mov     [rsp+140h+var_B0], rax
0x140017213  lea     rax, [rbp+arg_10]
0x140017217  mov     [rsp+140h+var_B8], rax
0x14001721f  lea     rax, [rbp+var_58]
0x140017223  mov     [rsp+140h+var_C0], rax
0x14001722b  lea     rax, [rbp+var_50]
0x14001722f  mov     [rsp+140h+var_C8], rax
0x140017234  lea     rax, [rbp+arg_18]
0x140017238  mov     [rsp+140h+var_D0], rax
0x14001723d  lea     rax, [rbp+var_48]
0x140017241  mov     [rsp+140h+var_D8], rax
0x140017246  lea     rax, [rbp+var_80]
0x14001724a  mov     [rsp+140h+var_E0], rax
0x14001724f  lea     rax, [rbp+var_40]
0x140017253  mov     [rsp+140h+var_E8], rax
0x140017258  lea     rax, [rbp+var_7C]
0x14001725c  mov     [rsp+140h+var_F0], rax
0x140017261  lea     rax, [rbp+var_38]
0x140017265  mov     [rsp+140h+var_F8], rax
0x14001726a  lea     rax, [rbp+var_78]
0x14001726e  mov     [rsp+140h+var_100], rax
0x140017273  lea     rax, [rbp+var_30]
0x140017277  mov     [rsp+140h+var_108], rax
0x14001727c  lea     rax, [rbp+var_74]
0x140017280  mov     [rbp+var_70], rcx
0x140017284  mov     ecx, [rdi+44h]
0x140017287  mov     [rsp+140h+var_110], rax
0x14001728c  lea     rax, [rbp+var_28]
0x140017290  mov     [rbp+arg_0], ecx
0x140017293  mov     ecx, [rdi+10h]
0x140017296  mov     [rbp+arg_8], ecx
0x140017299  mov     rcx, [rdi+78h]
0x14001729d  mov     [rsp+140h+var_118], rax
0x1400172a2  lea     rax, [rbp+var_20]
0x1400172a6  mov     [rbp+var_68], rcx
0x1400172aa  mov     rcx, r9
0x1400172ad  mov     [rsp+140h+var_120], rax
0x1400172b2  mov     [rbp+var_28], 1000000h
0x1400172ba  mov     [rbp+var_20], 0
0x1400172c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1400172c7  jmp     short loc_14001732A
0x1400172c9  call    ?zInternalStop@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400172ce  call    ?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ; MDMPushProvider::Provider(void)
0x1400172d3  mov     rdi, rax
0x1400172d6  mov     ecx, [rax]
0x1400172d8  cmp     ecx, 5
0x1400172db  jbe     short loc_14001732A
0x1400172dd  call    cs:__imp_GetCurrentThreadId
0x1400172e3  mov     r8, [rbx+110h]
0x1400172ea  lea     rdx, byte_14001F807
0x1400172f1  mov     [rbp+arg_0], eax
0x1400172f4  lea     rax, [rbp+arg_0]
0x1400172f8  mov     [rsp+140h+var_110], rax
0x1400172fd  lea     rax, [rbp+arg_8]
0x140017301  mov     [rsp+140h+var_118], rax
0x140017306  lea     rax, [rbp+arg_10]
0x14001730a  mov     ecx, [r8+48h]
0x14001730e  add     r8, 8
0x140017312  mov     [rbp+arg_8], ecx
0x140017315  mov     rcx, rdi
0x140017318  mov     [rsp+140h+var_120], rax
0x14001731d  mov     [rbp+arg_10], 0
0x140017325  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001732a  mov     rcx, rbx
0x14001732d  add     rsp, 130h
0x140017334  pop     rdi
0x140017335  pop     rbx
0x140017336  pop     rbp
0x140017337  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMDMPushProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MDMPushProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
