# LUATelemetry::AppXSyncActivity::Stop(int)

- ea: `0x180041290`
- end: `0x1800414e4`
- name: `?Stop@AppXSyncActivity@LUATelemetry@@QEAAXH@Z`
- size: `596`
- prototype: `void __fastcall(LUATelemetry::AppXSyncActivity *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180040844`

## callees

- `0x180003ddc`
- `0x1800040a4`
- `0x18000cb30`
- `0x180018d70`
- `0x18001fd6c`
- `0x18001fd94`
- `0x180041290`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004146e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004146e`

## pseudocode

```c
void __fastcall LUATelemetry::AppXSyncActivity::Stop(LUATelemetry::AppXSyncActivity *this, int a2)
{
  int *v2; // rax
  int v5; // ecx
  int *v6; // rdi
  __int64 v7; // rdx
  _DWORD *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // ecx
  __int64 v12; // r8
  struct LUATelemetry *v13; // rax
  _DWORD *v14; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  int v17; // r9d
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  int v20; // [rsp+B8h] [rbp-78h] BYREF
  int v21; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v30; // [rsp+100h] [rbp-30h] BYREF
  __int64 v31[3]; // [rsp+108h] [rbp-28h] BYREF
  int v32; // [rsp+130h] [rbp+0h] BYREF
  DWORD v33; // [rsp+140h] [rbp+10h] BYREF
  int v34; // [rsp+148h] [rbp+18h] BYREF

  v2 = (int *)*((_QWORD *)this + 34);
  v5 = v2[18];
  if ( v5 >= 0 || v5 != v2[22] || (v6 = v2 + 20, v2 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v13 = LUATelemetry::Instance();
    v14 = (_DWORD *)*((_QWORD *)v13 + 1);
    if ( *v14 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v13 + 1), 0x400000000000LL) )
    {
      v32 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      v33 = CurrentThreadId;
      v34 = *(_DWORD *)(v16 + 72);
      v22 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v14,
        (unsigned int)&unk_180054E06,
        v16 + 8,
        v17,
        (__int64)&v22,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v8 = (_DWORD *)*((_QWORD *)LUATelemetry::Instance() + 1);
    if ( *v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
    {
      v12 = *((_QWORD *)this + 34);
      v23 = *((_QWORD *)v6 + 15);
      v24 = *((_QWORD *)v6 + 14);
      v33 = v6[26];
      v25 = *((_QWORD *)v6 + 12);
      v26 = *((_QWORD *)v6 + 11);
      v34 = v6[20];
      v27 = *((_QWORD *)v6 + 9);
      v18 = v6[8];
      v28 = *((_QWORD *)v6 + 3);
      v19 = *v6;
      v29 = *((_QWORD *)v6 + 16);
      v20 = v6[16];
      v30 = *((_QWORD *)v6 + 7);
      v21 = v6[2];
      v32 = a2;
      v31[0] = 0x1000000;
      v22 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)&unk_1800549BF,
        v12 + 8,
        v10,
        (__int64)&v22,
        (__int64)v31,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v20,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v34,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&v33,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v32);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v9,
    v10);
}

```

## disassembly

```asm
0x180041290  mov     [rsp-8+arg_8], rbx
0x180041295  push    rbp
0x180041296  push    rsi
0x180041297  push    rdi
0x180041298  lea     rbp, [rsp+20h]
0x18004129d  sub     rsp, 110h
0x1800412a4  mov     rax, [rcx+110h]
0x1800412ab  mov     rbx, rcx
0x1800412ae  mov     esi, edx
0x1800412b0  mov     ecx, [rax+48h]
0x1800412b3  test    ecx, ecx
0x1800412b5  jns     loc_18004143F
0x1800412bb  cmp     ecx, [rax+58h]
0x1800412be  jnz     loc_18004143F
0x1800412c4  lea     rdi, [rax+50h]
0x1800412c8  test    rdi, rdi
0x1800412cb  jz      loc_18004143F
0x1800412d1  mov     rcx, rbx
0x1800412d4  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800412d9  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x1800412de  mov     rcx, [rax+8]
0x1800412e2  cmp     dword ptr [rcx], 5
0x1800412e5  jbe     loc_1800414CA
0x1800412eb  mov     rdx, 400000000000h
0x1800412f5  call    _tlgKeywordOn
0x1800412fa  test    al, al
0x1800412fc  jz      loc_1800414CA
0x180041302  mov     rax, [rdi+78h]
0x180041306  lea     rdx, unk_1800549BF
0x18004130d  mov     r8, [rbx+110h]
0x180041314  mov     [rbp-10h+var_58], rax
0x180041318  add     r8, 8
0x18004131c  mov     rax, [rdi+70h]
0x180041320  mov     [rbp-10h+var_50], rax
0x180041324  mov     eax, [rdi+68h]
0x180041327  mov     [rbp-10h+arg_10], eax
0x18004132a  mov     rax, [rdi+60h]
0x18004132e  mov     [rbp-10h+var_48], rax
0x180041332  mov     rax, [rdi+58h]
0x180041336  mov     [rbp-10h+var_40], rax
0x18004133a  mov     eax, [rdi+50h]
0x18004133d  mov     [rbp-10h+arg_18], eax
0x180041340  mov     rax, [rdi+48h]
0x180041344  mov     [rbp-10h+var_38], rax
0x180041348  mov     eax, [rdi+20h]
0x18004134b  mov     [rbp-10h+var_70], eax
0x18004134e  mov     rax, [rdi+18h]
0x180041352  mov     [rbp-10h+var_30], rax
0x180041356  mov     eax, [rdi]
0x180041358  mov     [rbp-10h+var_6C], eax
0x18004135b  mov     rax, [rdi+80h]
0x180041362  mov     [rbp-10h+var_28], rax
0x180041366  mov     eax, [rdi+40h]
0x180041369  mov     [rbp-10h+var_68], eax
0x18004136c  mov     rax, [rdi+38h]
0x180041370  mov     [rbp-10h+var_20], rax
0x180041374  mov     eax, [rdi+8]
0x180041377  mov     [rbp-10h+var_64], eax
0x18004137a  lea     rax, [rbp-10h+arg_0]
0x18004137e  mov     [rsp+120h+var_80], rax
0x180041386  lea     rax, [rbp-10h+var_58]
0x18004138a  mov     [rsp+120h+var_88], rax
0x180041392  lea     rax, [rbp-10h+var_50]
0x180041396  mov     [rsp+120h+var_90], rax
0x18004139e  lea     rax, [rbp-10h+arg_10]
0x1800413a2  mov     [rsp+120h+var_98], rax
0x1800413aa  lea     rax, [rbp-10h+var_48]
0x1800413ae  mov     [rsp+120h+var_A0], rax
0x1800413b6  lea     rax, [rbp-10h+var_40]
0x1800413ba  mov     [rsp+120h+var_A8], rax
0x1800413bf  lea     rax, [rbp-10h+arg_18]
0x1800413c3  mov     [rsp+120h+var_B0], rax
0x1800413c8  lea     rax, [rbp-10h+var_38]
0x1800413cc  mov     [rsp+120h+var_B8], rax
0x1800413d1  lea     rax, [rbp-10h+var_70]
0x1800413d5  mov     [rsp+120h+var_C0], rax
0x1800413da  lea     rax, [rbp-10h+var_30]
0x1800413de  mov     [rsp+120h+var_C8], rax
0x1800413e3  lea     rax, [rbp-10h+var_6C]
0x1800413e7  mov     [rsp+120h+var_D0], rax
0x1800413ec  lea     rax, [rbp-10h+var_28]
0x1800413f0  mov     [rsp+120h+var_D8], rax
0x1800413f5  lea     rax, [rbp-10h+var_68]
0x1800413f9  mov     [rsp+120h+var_E0], rax
0x1800413fe  lea     rax, [rbp-10h+var_20]
0x180041402  mov     [rsp+120h+var_E8], rax
0x180041407  lea     rax, [rbp-10h+var_64]
0x18004140b  mov     [rsp+120h+var_F0], rax
0x180041410  lea     rax, [rbp-10h+var_18]
0x180041414  mov     [rsp+120h+var_F8], rax
0x180041419  lea     rax, [rbp-10h+var_60]
0x18004141d  mov     [rsp+120h+var_100], rax
0x180041422  mov     [rbp-10h+arg_0], esi
0x180041425  mov     [rbp-10h+var_18], 1000000h
0x18004142d  mov     [rbp-10h+var_60], 3000000h
0x180041435  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18004143a  jmp     loc_1800414CA
0x18004143f  mov     rcx, rbx
0x180041442  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180041447  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18004144c  mov     rdi, [rax+8]
0x180041450  cmp     dword ptr [rdi], 5
0x180041453  jbe     short loc_1800414CA
0x180041455  mov     rdx, 400000000000h
0x18004145f  mov     rcx, rdi
0x180041462  call    _tlgKeywordOn
0x180041467  test    al, al
0x180041469  jz      short loc_1800414CA
0x18004146b  mov     [rbp-10h+arg_0], esi
0x18004146e  call    cs:__imp_GetCurrentThreadId
0x180041475  nop     dword ptr [rax+rax+00h]
0x18004147a  mov     r8, [rbx+110h]
0x180041481  lea     rdx, unk_180054E06
0x180041488  mov     [rbp-10h+arg_10], eax
0x18004148b  mov     rcx, rdi
0x18004148e  mov     eax, [r8+48h]
0x180041492  add     r8, 8
0x180041496  mov     [rbp-10h+arg_18], eax
0x180041499  lea     rax, [rbp-10h+arg_0]
0x18004149d  mov     [rsp+120h+var_E8], rax
0x1800414a2  lea     rax, [rbp-10h+arg_10]
0x1800414a6  mov     [rsp+120h+var_F0], rax
0x1800414ab  lea     rax, [rbp-10h+arg_18]
0x1800414af  mov     [rsp+120h+var_F8], rax
0x1800414b4  lea     rax, [rbp-10h+var_60]
0x1800414b8  mov     [rsp+120h+var_100], rax
0x1800414bd  mov     [rbp-10h+var_60], 3000000h
0x1800414c5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800414ca  mov     rcx, rbx
0x1800414cd  mov     rbx, [rsp+120h+arg_8]
0x1800414d5  add     rsp, 110h
0x1800414dc  pop     rdi
0x1800414dd  pop     rsi
0x1800414de  pop     rbp
0x1800414df  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
