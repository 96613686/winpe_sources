# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(void)

- ea: `0x1800155e0`
- end: `0x180015804`
- name: `?StopActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800011d0`
- `0x180001a84`
- `0x18000254c`
- `0x180011f74`
- `0x180013130`
- `0x1800155e0`
- `0x1800189ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800157a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800157a5`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  __int64 *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  __int64 *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7, v5) )
    {
      v9 = (__int64 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (__int64 *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (__int64 *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)byte_180028985,
        v10 + 8,
        v8,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_180028AB9,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x1800155e0  push    rbp
0x1800155e2  push    rbx
0x1800155e3  push    rdi
0x1800155e4  lea     rbp, [rsp-47h]
0x1800155e9  sub     rsp, 100h
0x1800155f0  mov     rdi, [rcx+110h]
0x1800155f7  mov     rbx, rcx
0x1800155fa  mov     eax, [rdi+48h]
0x1800155fd  test    eax, eax
0x1800155ff  jns     loc_18001577B
0x180015605  add     rdi, 50h ; 'P'
0x180015609  cmp     eax, [rdi+8]
0x18001560c  jnz     loc_18001577B
0x180015612  test    rdi, rdi
0x180015615  jz      loc_18001577B
0x18001561b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015620  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180015625  mov     r9, rax
0x180015628  mov     ecx, [rax]
0x18001562a  cmp     ecx, 5
0x18001562d  jbe     loc_1800157F2
0x180015633  mov     rdx, 400000000000h
0x18001563d  mov     rcx, rax
0x180015640  call    _tlgKeywordOn
0x180015645  test    al, al
0x180015647  jz      loc_1800157F2
0x18001564d  mov     rax, [rdi+70h]
0x180015651  lea     rdx, byte_180028985
0x180015658  mov     rcx, [rdi+78h]
0x18001565c  mov     r8, [rbx+110h]
0x180015663  mov     [rbp+57h+var_60], rax
0x180015667  add     r8, 8
0x18001566b  mov     eax, [rdi+68h]
0x18001566e  mov     [rbp+57h+arg_0], eax
0x180015671  mov     rax, [rdi+60h]
0x180015675  mov     [rbp+57h+var_58], rax
0x180015679  mov     rax, [rdi+58h]
0x18001567d  mov     [rbp+57h+var_50], rax
0x180015681  mov     eax, [rdi+50h]
0x180015684  mov     [rbp+57h+arg_8], eax
0x180015687  mov     rax, [rdi+48h]
0x18001568b  mov     [rbp+57h+var_48], rax
0x18001568f  mov     eax, [rdi+20h]
0x180015692  mov     dword ptr [rbp+57h+arg_10], eax
0x180015695  mov     rax, [rdi+18h]
0x180015699  mov     [rbp+57h+var_40], rax
0x18001569d  mov     eax, [rdi]
0x18001569f  mov     [rbp+57h+arg_18], eax
0x1800156a2  mov     rax, [rdi+80h]
0x1800156a9  mov     [rbp+57h+var_38], rax
0x1800156ad  mov     eax, [rdi+40h]
0x1800156b0  mov     [rbp+57h+var_70], eax
0x1800156b3  mov     rax, [rdi+38h]
0x1800156b7  mov     [rbp+57h+var_30], rax
0x1800156bb  mov     eax, [rdi+8]
0x1800156be  mov     [rbp+57h+var_6C], eax
0x1800156c1  lea     rax, [rbp+57h+var_68]
0x1800156c5  mov     [rsp+110h+var_78], rax
0x1800156cd  lea     rax, [rbp+57h+var_60]
0x1800156d1  mov     [rsp+110h+var_80], rax
0x1800156d9  lea     rax, [rbp+57h+arg_0]
0x1800156dd  mov     [rsp+110h+var_88], rax
0x1800156e5  lea     rax, [rbp+57h+var_58]
0x1800156e9  mov     [rsp+110h+var_90], rax
0x1800156f1  lea     rax, [rbp+57h+var_50]
0x1800156f5  mov     [rsp+110h+var_98], rax
0x1800156fa  lea     rax, [rbp+57h+arg_8]
0x1800156fe  mov     [rsp+110h+var_A0], rax
0x180015703  lea     rax, [rbp+57h+var_48]
0x180015707  mov     [rsp+110h+var_A8], rax
0x18001570c  lea     rax, [rbp+57h+arg_10]
0x180015710  mov     [rsp+110h+var_B0], rax
0x180015715  lea     rax, [rbp+57h+var_40]
0x180015719  mov     [rsp+110h+var_B8], rax
0x18001571e  lea     rax, [rbp+57h+arg_18]
0x180015722  mov     [rsp+110h+var_C0], rax
0x180015727  lea     rax, [rbp+57h+var_38]
0x18001572b  mov     [rsp+110h+var_C8], rax
0x180015730  lea     rax, [rbp+57h+var_70]
0x180015734  mov     [rsp+110h+var_D0], rax
0x180015739  lea     rax, [rbp+57h+var_30]
0x18001573d  mov     [rsp+110h+var_D8], rax
0x180015742  lea     rax, [rbp+57h+var_6C]
0x180015746  mov     [rsp+110h+var_E0], rax
0x18001574b  lea     rax, [rbp+57h+var_28]
0x18001574f  mov     [rsp+110h+var_E8], rax
0x180015754  lea     rax, [rbp+57h+var_20]
0x180015758  mov     [rbp+57h+var_68], rcx
0x18001575c  mov     rcx, r9
0x18001575f  mov     [rsp+110h+var_F0], rax
0x180015764  mov     [rbp+57h+var_28], 1000000h
0x18001576c  mov     [rbp+57h+var_20], 0
0x180015774  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180015779  jmp     short loc_1800157F2
0x18001577b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180015780  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180015785  mov     rdi, rax
0x180015788  mov     ecx, [rax]
0x18001578a  cmp     ecx, 5
0x18001578d  jbe     short loc_1800157F2
0x18001578f  mov     rdx, 400000000000h
0x180015799  mov     rcx, rax
0x18001579c  call    _tlgKeywordOn
0x1800157a1  test    al, al
0x1800157a3  jz      short loc_1800157F2
0x1800157a5  call    cs:__imp_GetCurrentThreadId
0x1800157ab  mov     r8, [rbx+110h]
0x1800157b2  lea     rdx, byte_180028AB9
0x1800157b9  mov     [rbp+57h+arg_0], eax
0x1800157bc  mov     rcx, rdi
0x1800157bf  mov     eax, [r8+48h]
0x1800157c3  add     r8, 8
0x1800157c7  mov     [rbp+57h+arg_8], eax
0x1800157ca  lea     rax, [rbp+57h+arg_0]
0x1800157ce  mov     [rsp+110h+var_E0], rax
0x1800157d3  lea     rax, [rbp+57h+arg_8]
0x1800157d7  mov     [rsp+110h+var_E8], rax
0x1800157dc  lea     rax, [rbp+57h+arg_10]
0x1800157e0  mov     [rsp+110h+var_F0], rax
0x1800157e5  mov     [rbp+57h+arg_10], 0
0x1800157ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800157f2  mov     rcx, rbx
0x1800157f5  add     rsp, 100h
0x1800157fc  pop     rdi
0x1800157fd  pop     rbx
0x1800157fe  pop     rbp
0x1800157ff  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
