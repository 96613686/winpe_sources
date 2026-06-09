# TraceProvider::AccessCheckActivity::StopActivity(void)

- ea: `0x180015e70`
- end: `0x18001609c`
- name: `?StopActivity@AccessCheckActivity@TraceProvider@@MEAAXXZ`
- size: `556`
- prototype: `void __fastcall(TraceProvider::AccessCheckActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180001010`
- `0x180001650`
- `0x18000e2d8`
- `0x18000e964`
- `0x1800115cc`
- `0x180015e70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001603d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001603d`

## pseudocode

```c
void __fastcall TraceProvider::AccessCheckActivity::StopActivity(TraceProvider::AccessCheckActivity *this)
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
        (__int64)&word_18002A1FE,
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
        (__int64)&dword_18002A34C,
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
0x180015e70  push    rbp
0x180015e72  push    rbx
0x180015e73  push    rdi
0x180015e74  lea     rbp, [rsp+10h]
0x180015e79  sub     rsp, 130h
0x180015e80  mov     rdi, [rcx+110h]
0x180015e87  mov     rbx, rcx
0x180015e8a  mov     eax, [rdi+48h]
0x180015e8d  test    eax, eax
0x180015e8f  jns     loc_180016029
0x180015e95  add     rdi, 50h ; 'P'
0x180015e99  cmp     eax, [rdi+8]
0x180015e9c  jnz     loc_180016029
0x180015ea2  test    rdi, rdi
0x180015ea5  jz      loc_180016029
0x180015eab  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015eb0  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180015eb5  mov     r9, rax
0x180015eb8  mov     ecx, [rax]
0x180015eba  cmp     ecx, 5
0x180015ebd  jbe     loc_18001608A
0x180015ec3  mov     rax, [rdi+70h]
0x180015ec7  lea     rdx, word_18002A1FE
0x180015ece  mov     rcx, [rdi+30h]
0x180015ed2  mov     [rbp+var_60], rax
0x180015ed6  mov     eax, [rdi+68h]
0x180015ed9  mov     r8, [rbx+110h]
0x180015ee0  mov     dword ptr [rbp+arg_10], eax
0x180015ee3  add     r8, 8
0x180015ee7  mov     rax, [rdi+60h]
0x180015eeb  mov     [rbp+var_58], rax
0x180015eef  mov     rax, [rdi+58h]
0x180015ef3  mov     [rbp+var_50], rax
0x180015ef7  mov     eax, [rdi+50h]
0x180015efa  mov     [rbp+arg_18], eax
0x180015efd  mov     rax, [rdi+48h]
0x180015f01  mov     [rbp+var_48], rax
0x180015f05  mov     eax, [rdi+20h]
0x180015f08  mov     [rbp+var_80], eax
0x180015f0b  mov     rax, [rdi+18h]
0x180015f0f  mov     [rbp+var_40], rax
0x180015f13  mov     eax, [rdi]
0x180015f15  mov     [rbp+var_7C], eax
0x180015f18  mov     rax, [rdi+80h]
0x180015f1f  mov     [rbp+var_38], rax
0x180015f23  mov     eax, [rdi+40h]
0x180015f26  mov     [rbp+var_78], eax
0x180015f29  mov     rax, [rdi+38h]
0x180015f2d  mov     [rbp+var_30], rax
0x180015f31  mov     eax, [rdi+8]
0x180015f34  mov     [rbp+var_74], eax
0x180015f37  lea     rax, [rbp+var_70]
0x180015f3b  mov     [rsp+140h+var_90], rax
0x180015f43  lea     rax, [rbp+arg_0]
0x180015f47  mov     [rsp+140h+var_98], rax
0x180015f4f  lea     rax, [rbp+arg_8]
0x180015f53  mov     [rsp+140h+var_A0], rax
0x180015f5b  lea     rax, [rbp+var_68]
0x180015f5f  mov     [rsp+140h+var_A8], rax
0x180015f67  lea     rax, [rbp+var_60]
0x180015f6b  mov     [rsp+140h+var_B0], rax
0x180015f73  lea     rax, [rbp+arg_10]
0x180015f77  mov     [rsp+140h+var_B8], rax
0x180015f7f  lea     rax, [rbp+var_58]
0x180015f83  mov     [rsp+140h+var_C0], rax
0x180015f8b  lea     rax, [rbp+var_50]
0x180015f8f  mov     [rsp+140h+var_C8], rax
0x180015f94  lea     rax, [rbp+arg_18]
0x180015f98  mov     [rsp+140h+var_D0], rax
0x180015f9d  lea     rax, [rbp+var_48]
0x180015fa1  mov     [rsp+140h+var_D8], rax
0x180015fa6  lea     rax, [rbp+var_80]
0x180015faa  mov     [rsp+140h+var_E0], rax
0x180015faf  lea     rax, [rbp+var_40]
0x180015fb3  mov     [rsp+140h+var_E8], rax
0x180015fb8  lea     rax, [rbp+var_7C]
0x180015fbc  mov     [rsp+140h+var_F0], rax
0x180015fc1  lea     rax, [rbp+var_38]
0x180015fc5  mov     [rsp+140h+var_F8], rax
0x180015fca  lea     rax, [rbp+var_78]
0x180015fce  mov     [rsp+140h+var_100], rax
0x180015fd3  lea     rax, [rbp+var_30]
0x180015fd7  mov     [rsp+140h+var_108], rax
0x180015fdc  lea     rax, [rbp+var_74]
0x180015fe0  mov     [rbp+var_70], rcx
0x180015fe4  mov     ecx, [rdi+44h]
0x180015fe7  mov     [rsp+140h+var_110], rax
0x180015fec  lea     rax, [rbp+var_28]
0x180015ff0  mov     [rbp+arg_0], ecx
0x180015ff3  mov     ecx, [rdi+10h]
0x180015ff6  mov     [rbp+arg_8], ecx
0x180015ff9  mov     rcx, [rdi+78h]
0x180015ffd  mov     [rsp+140h+var_118], rax
0x180016002  lea     rax, [rbp+var_20]
0x180016006  mov     [rbp+var_68], rcx
0x18001600a  mov     rcx, r9
0x18001600d  mov     [rsp+140h+var_120], rax
0x180016012  mov     [rbp+var_28], 1000000h
0x18001601a  mov     [rbp+var_20], 0
0x180016022  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180016027  jmp     short loc_18001608A
0x180016029  call    ?zInternalStop@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001602e  call    ?Provider@TraceProvider@@SAPEBU_tlgProvider_t@@XZ; TraceProvider::Provider(void)
0x180016033  mov     rdi, rax
0x180016036  mov     ecx, [rax]
0x180016038  cmp     ecx, 5
0x18001603b  jbe     short loc_18001608A
0x18001603d  call    cs:__imp_GetCurrentThreadId
0x180016043  mov     r8, [rbx+110h]
0x18001604a  lea     rdx, dword_18002A34C
0x180016051  mov     [rbp+arg_0], eax
0x180016054  lea     rax, [rbp+arg_0]
0x180016058  mov     [rsp+140h+var_110], rax
0x18001605d  lea     rax, [rbp+arg_8]
0x180016061  mov     [rsp+140h+var_118], rax
0x180016066  lea     rax, [rbp+arg_10]
0x18001606a  mov     ecx, [r8+48h]
0x18001606e  add     r8, 8
0x180016072  mov     [rbp+arg_8], ecx
0x180016075  mov     rcx, rdi
0x180016078  mov     [rsp+140h+var_120], rax
0x18001607d  mov     [rbp+arg_10], 0
0x180016085  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001608a  mov     rcx, rbx
0x18001608d  add     rsp, 130h
0x180016094  pop     rdi
0x180016095  pop     rbx
0x180016096  pop     rbp
0x180016097  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TraceProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
