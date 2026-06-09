# TraceProvider::CreateDirectoryProxyActivity::StopActivity(void)

- ea: `0x18001f880`
- end: `0x18001faac`
- name: `?StopActivity@CreateDirectoryProxyActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::CreateDirectoryProxyActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x18001f880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fa4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fa4d`

## pseudocode

```c
void __fastcall TraceProvider::CreateDirectoryProxyActivity::StopActivity(
        TraceProvider::CreateDirectoryProxyActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  const unsigned __int16 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v18; // [rsp+D0h] [rbp-70h] BYREF
  const unsigned __int16 *v19; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+E0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v22; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v24; // [rsp+100h] [rbp-40h] BYREF
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
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = TraceProvider::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v7,
        (__int64)byte_18002BF1D,
        v9 + 8,
        (__int64)v7,
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
    wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = TraceProvider::Provider();
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v12 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&dword_18002C074,
        v12 + 8,
        v13,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this, v5, v6, v7);
}

```

## disassembly

```asm
0x18001f880  push    rbp
0x18001f882  push    rbx
0x18001f883  push    rdi
0x18001f884  lea     rbp, [rsp+10h]
0x18001f889  sub     rsp, 130h
0x18001f890  mov     rdi, [rcx+110h]
0x18001f897  mov     rbx, rcx
0x18001f89a  mov     eax, [rdi+48h]
0x18001f89d  test    eax, eax
0x18001f89f  jns     loc_18001FA39
0x18001f8a5  add     rdi, 50h ; 'P'
0x18001f8a9  cmp     eax, [rdi+8]
0x18001f8ac  jnz     loc_18001FA39
0x18001f8b2  test    rdi, rdi
0x18001f8b5  jz      loc_18001FA39
0x18001f8bb  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001f8c0  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001f8c5  mov     r9, rax
0x18001f8c8  mov     ecx, [rax]
0x18001f8ca  cmp     ecx, 5
0x18001f8cd  jbe     loc_18001FA9A
0x18001f8d3  mov     rax, [rdi+70h]
0x18001f8d7  lea     rdx, byte_18002BF1D
0x18001f8de  mov     rcx, [rdi+30h]
0x18001f8e2  mov     [rbp+var_60], rax
0x18001f8e6  mov     eax, [rdi+68h]
0x18001f8e9  mov     r8, [rbx+110h]
0x18001f8f0  mov     dword ptr [rbp+arg_10], eax
0x18001f8f3  add     r8, 8
0x18001f8f7  mov     rax, [rdi+60h]
0x18001f8fb  mov     [rbp+var_58], rax
0x18001f8ff  mov     rax, [rdi+58h]
0x18001f903  mov     [rbp+var_50], rax
0x18001f907  mov     eax, [rdi+50h]
0x18001f90a  mov     [rbp+arg_18], eax
0x18001f90d  mov     rax, [rdi+48h]
0x18001f911  mov     [rbp+var_48], rax
0x18001f915  mov     eax, [rdi+20h]
0x18001f918  mov     [rbp+var_80], eax
0x18001f91b  mov     rax, [rdi+18h]
0x18001f91f  mov     [rbp+var_40], rax
0x18001f923  mov     eax, [rdi]
0x18001f925  mov     [rbp+var_7C], eax
0x18001f928  mov     rax, [rdi+80h]
0x18001f92f  mov     [rbp+var_38], rax
0x18001f933  mov     eax, [rdi+40h]
0x18001f936  mov     [rbp+var_78], eax
0x18001f939  mov     rax, [rdi+38h]
0x18001f93d  mov     [rbp+var_30], rax
0x18001f941  mov     eax, [rdi+8]
0x18001f944  mov     [rbp+var_74], eax
0x18001f947  lea     rax, [rbp+var_70]
0x18001f94b  mov     [rsp+140h+var_90], rax
0x18001f953  lea     rax, [rbp+arg_0]
0x18001f957  mov     [rsp+140h+var_98], rax
0x18001f95f  lea     rax, [rbp+arg_8]
0x18001f963  mov     [rsp+140h+var_A0], rax
0x18001f96b  lea     rax, [rbp+var_68]
0x18001f96f  mov     [rsp+140h+var_A8], rax
0x18001f977  lea     rax, [rbp+var_60]
0x18001f97b  mov     [rsp+140h+var_B0], rax
0x18001f983  lea     rax, [rbp+arg_10]
0x18001f987  mov     [rsp+140h+var_B8], rax
0x18001f98f  lea     rax, [rbp+var_58]
0x18001f993  mov     [rsp+140h+var_C0], rax
0x18001f99b  lea     rax, [rbp+var_50]
0x18001f99f  mov     [rsp+140h+var_C8], rax
0x18001f9a4  lea     rax, [rbp+arg_18]
0x18001f9a8  mov     [rsp+140h+var_D0], rax
0x18001f9ad  lea     rax, [rbp+var_48]
0x18001f9b1  mov     [rsp+140h+var_D8], rax
0x18001f9b6  lea     rax, [rbp+var_80]
0x18001f9ba  mov     [rsp+140h+var_E0], rax
0x18001f9bf  lea     rax, [rbp+var_40]
0x18001f9c3  mov     [rsp+140h+var_E8], rax
0x18001f9c8  lea     rax, [rbp+var_7C]
0x18001f9cc  mov     [rsp+140h+var_F0], rax
0x18001f9d1  lea     rax, [rbp+var_38]
0x18001f9d5  mov     [rsp+140h+var_F8], rax
0x18001f9da  lea     rax, [rbp+var_78]
0x18001f9de  mov     [rsp+140h+var_100], rax
0x18001f9e3  lea     rax, [rbp+var_30]
0x18001f9e7  mov     [rsp+140h+var_108], rax
0x18001f9ec  lea     rax, [rbp+var_74]
0x18001f9f0  mov     [rbp+var_70], rcx
0x18001f9f4  mov     ecx, [rdi+44h]
0x18001f9f7  mov     [rsp+140h+var_110], rax
0x18001f9fc  lea     rax, [rbp+var_28]
0x18001fa00  mov     [rbp+arg_0], ecx
0x18001fa03  mov     ecx, [rdi+10h]
0x18001fa06  mov     [rbp+arg_8], ecx
0x18001fa09  mov     rcx, [rdi+78h]
0x18001fa0d  mov     [rsp+140h+var_118], rax
0x18001fa12  lea     rax, [rbp+var_20]
0x18001fa16  mov     [rbp+var_68], rcx
0x18001fa1a  mov     rcx, r9
0x18001fa1d  mov     [rsp+140h+var_120], rax
0x18001fa22  mov     [rbp+var_28], 1000000h
0x18001fa2a  mov     [rbp+var_20], 0
0x18001fa32  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001fa37  jmp     short loc_18001FA9A
0x18001fa39  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001fa3e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x18001fa43  mov     rdi, rax
0x18001fa46  mov     ecx, [rax]
0x18001fa48  cmp     ecx, 5
0x18001fa4b  jbe     short loc_18001FA9A
0x18001fa4d  call    cs:__imp_GetCurrentThreadId
0x18001fa53  mov     r8, [rbx+110h]
0x18001fa5a  lea     rdx, dword_18002C074
0x18001fa61  mov     [rbp+arg_0], eax
0x18001fa64  lea     rax, [rbp+arg_0]
0x18001fa68  mov     [rsp+140h+var_110], rax
0x18001fa6d  lea     rax, [rbp+arg_8]
0x18001fa71  mov     [rsp+140h+var_118], rax
0x18001fa76  lea     rax, [rbp+arg_10]
0x18001fa7a  mov     ecx, [r8+48h]
0x18001fa7e  add     r8, 8
0x18001fa82  mov     [rbp+arg_8], ecx
0x18001fa85  mov     rcx, rdi
0x18001fa88  mov     [rsp+140h+var_120], rax
0x18001fa8d  mov     [rbp+arg_10], 0
0x18001fa95  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001fa9a  mov     rcx, rbx
0x18001fa9d  add     rsp, 130h
0x18001faa4  pop     rdi
0x18001faa5  pop     rbx
0x18001faa6  pop     rbp
0x18001faa7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
