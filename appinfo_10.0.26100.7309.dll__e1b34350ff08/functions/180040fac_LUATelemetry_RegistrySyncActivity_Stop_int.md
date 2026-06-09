# LUATelemetry::RegistrySyncActivity::Stop(int)

- ea: `0x180040fac`
- end: `0x180041200`
- name: `?Stop@RegistrySyncActivity@LUATelemetry@@QEAAXH@Z`
- size: `596`
- prototype: `void __fastcall(LUATelemetry::RegistrySyncActivity *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180040730`

## callees

- `0x180003ddc`
- `0x1800040a4`
- `0x18000cb30`
- `0x180018d70`
- `0x18001fd6c`
- `0x18001fd94`
- `0x180040fac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004118a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004118a`

## pseudocode

```c
void __fastcall LUATelemetry::RegistrySyncActivity::Stop(LUATelemetry::RegistrySyncActivity *this, int a2)
{
  int *v2; // rax
  int v5; // ecx
  int *v6; // rdi
  _DWORD *v7; // rcx
  int v8; // ecx
  int v9; // r9d
  __int64 v10; // r8
  struct LUATelemetry *v11; // rax
  _DWORD *v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+B0h] [rbp-80h] BYREF
  int v17; // [rsp+B4h] [rbp-7Ch] BYREF
  int v18; // [rsp+B8h] [rbp-78h] BYREF
  int v19; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v20; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+100h] [rbp-30h] BYREF
  __int64 v29[3]; // [rsp+108h] [rbp-28h] BYREF
  int v30; // [rsp+130h] [rbp+0h] BYREF
  DWORD v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+148h] [rbp+18h] BYREF

  v2 = (int *)*((_QWORD *)this + 34);
  v5 = v2[18];
  if ( v5 >= 0 || v5 != v2[22] || (v6 = v2 + 20, v2 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v11 = LUATelemetry::Instance();
    v12 = (_DWORD *)*((_QWORD *)v11 + 1);
    if ( *v12 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v11 + 1), 0x400000000000LL) )
    {
      v30 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v31 = CurrentThreadId;
      v32 = *(_DWORD *)(v14 + 72);
      v20 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v12,
        (unsigned int)&unk_180053D8B,
        v14 + 8,
        v15,
        (__int64)&v20,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v7 = (_DWORD *)*((_QWORD *)LUATelemetry::Instance() + 1);
    if ( *v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL) )
    {
      v10 = *((_QWORD *)this + 34);
      v21 = *((_QWORD *)v6 + 15);
      v22 = *((_QWORD *)v6 + 14);
      v31 = v6[26];
      v23 = *((_QWORD *)v6 + 12);
      v24 = *((_QWORD *)v6 + 11);
      v32 = v6[20];
      v25 = *((_QWORD *)v6 + 9);
      v16 = v6[8];
      v26 = *((_QWORD *)v6 + 3);
      v17 = *v6;
      v27 = *((_QWORD *)v6 + 16);
      v18 = v6[16];
      v28 = *((_QWORD *)v6 + 7);
      v19 = v6[2];
      v30 = a2;
      v29[0] = 0x1000000;
      v20 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)&unk_180053B25,
        v10 + 8,
        v9,
        (__int64)&v20,
        (__int64)v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v31,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v30);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180040fac  mov     [rsp-8+arg_8], rbx
0x180040fb1  push    rbp
0x180040fb2  push    rsi
0x180040fb3  push    rdi
0x180040fb4  lea     rbp, [rsp+20h]
0x180040fb9  sub     rsp, 110h
0x180040fc0  mov     rax, [rcx+110h]
0x180040fc7  mov     rbx, rcx
0x180040fca  mov     esi, edx
0x180040fcc  mov     ecx, [rax+48h]
0x180040fcf  test    ecx, ecx
0x180040fd1  jns     loc_18004115B
0x180040fd7  cmp     ecx, [rax+58h]
0x180040fda  jnz     loc_18004115B
0x180040fe0  lea     rdi, [rax+50h]
0x180040fe4  test    rdi, rdi
0x180040fe7  jz      loc_18004115B
0x180040fed  mov     rcx, rbx
0x180040ff0  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180040ff5  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180040ffa  mov     rcx, [rax+8]
0x180040ffe  cmp     dword ptr [rcx], 5
0x180041001  jbe     loc_1800411E6
0x180041007  mov     rdx, 400000000000h
0x180041011  call    _tlgKeywordOn
0x180041016  test    al, al
0x180041018  jz      loc_1800411E6
0x18004101e  mov     rax, [rdi+78h]
0x180041022  lea     rdx, unk_180053B25
0x180041029  mov     r8, [rbx+110h]
0x180041030  mov     [rbp-10h+var_58], rax
0x180041034  add     r8, 8
0x180041038  mov     rax, [rdi+70h]
0x18004103c  mov     [rbp-10h+var_50], rax
0x180041040  mov     eax, [rdi+68h]
0x180041043  mov     [rbp-10h+arg_10], eax
0x180041046  mov     rax, [rdi+60h]
0x18004104a  mov     [rbp-10h+var_48], rax
0x18004104e  mov     rax, [rdi+58h]
0x180041052  mov     [rbp-10h+var_40], rax
0x180041056  mov     eax, [rdi+50h]
0x180041059  mov     [rbp-10h+arg_18], eax
0x18004105c  mov     rax, [rdi+48h]
0x180041060  mov     [rbp-10h+var_38], rax
0x180041064  mov     eax, [rdi+20h]
0x180041067  mov     [rbp-10h+var_70], eax
0x18004106a  mov     rax, [rdi+18h]
0x18004106e  mov     [rbp-10h+var_30], rax
0x180041072  mov     eax, [rdi]
0x180041074  mov     [rbp-10h+var_6C], eax
0x180041077  mov     rax, [rdi+80h]
0x18004107e  mov     [rbp-10h+var_28], rax
0x180041082  mov     eax, [rdi+40h]
0x180041085  mov     [rbp-10h+var_68], eax
0x180041088  mov     rax, [rdi+38h]
0x18004108c  mov     [rbp-10h+var_20], rax
0x180041090  mov     eax, [rdi+8]
0x180041093  mov     [rbp-10h+var_64], eax
0x180041096  lea     rax, [rbp-10h+arg_0]
0x18004109a  mov     [rsp+120h+var_80], rax
0x1800410a2  lea     rax, [rbp-10h+var_58]
0x1800410a6  mov     [rsp+120h+var_88], rax
0x1800410ae  lea     rax, [rbp-10h+var_50]
0x1800410b2  mov     [rsp+120h+var_90], rax
0x1800410ba  lea     rax, [rbp-10h+arg_10]
0x1800410be  mov     [rsp+120h+var_98], rax
0x1800410c6  lea     rax, [rbp-10h+var_48]
0x1800410ca  mov     [rsp+120h+var_A0], rax
0x1800410d2  lea     rax, [rbp-10h+var_40]
0x1800410d6  mov     [rsp+120h+var_A8], rax
0x1800410db  lea     rax, [rbp-10h+arg_18]
0x1800410df  mov     [rsp+120h+var_B0], rax
0x1800410e4  lea     rax, [rbp-10h+var_38]
0x1800410e8  mov     [rsp+120h+var_B8], rax
0x1800410ed  lea     rax, [rbp-10h+var_70]
0x1800410f1  mov     [rsp+120h+var_C0], rax
0x1800410f6  lea     rax, [rbp-10h+var_30]
0x1800410fa  mov     [rsp+120h+var_C8], rax
0x1800410ff  lea     rax, [rbp-10h+var_6C]
0x180041103  mov     [rsp+120h+var_D0], rax
0x180041108  lea     rax, [rbp-10h+var_28]
0x18004110c  mov     [rsp+120h+var_D8], rax
0x180041111  lea     rax, [rbp-10h+var_68]
0x180041115  mov     [rsp+120h+var_E0], rax
0x18004111a  lea     rax, [rbp-10h+var_20]
0x18004111e  mov     [rsp+120h+var_E8], rax
0x180041123  lea     rax, [rbp-10h+var_64]
0x180041127  mov     [rsp+120h+var_F0], rax
0x18004112c  lea     rax, [rbp-10h+var_18]
0x180041130  mov     [rsp+120h+var_F8], rax
0x180041135  lea     rax, [rbp-10h+var_60]
0x180041139  mov     [rsp+120h+var_100], rax
0x18004113e  mov     [rbp-10h+arg_0], esi
0x180041141  mov     [rbp-10h+var_18], 1000000h
0x180041149  mov     [rbp-10h+var_60], 3000000h
0x180041151  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180041156  jmp     loc_1800411E6
0x18004115b  mov     rcx, rbx
0x18004115e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180041163  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180041168  mov     rdi, [rax+8]
0x18004116c  cmp     dword ptr [rdi], 5
0x18004116f  jbe     short loc_1800411E6
0x180041171  mov     rdx, 400000000000h
0x18004117b  mov     rcx, rdi
0x18004117e  call    _tlgKeywordOn
0x180041183  test    al, al
0x180041185  jz      short loc_1800411E6
0x180041187  mov     [rbp-10h+arg_0], esi
0x18004118a  call    cs:__imp_GetCurrentThreadId
0x180041191  nop     dword ptr [rax+rax+00h]
0x180041196  mov     r8, [rbx+110h]
0x18004119d  lea     rdx, unk_180053D8B
0x1800411a4  mov     [rbp-10h+arg_10], eax
0x1800411a7  mov     rcx, rdi
0x1800411aa  mov     eax, [r8+48h]
0x1800411ae  add     r8, 8
0x1800411b2  mov     [rbp-10h+arg_18], eax
0x1800411b5  lea     rax, [rbp-10h+arg_0]
0x1800411b9  mov     [rsp+120h+var_E8], rax
0x1800411be  lea     rax, [rbp-10h+arg_10]
0x1800411c2  mov     [rsp+120h+var_F0], rax
0x1800411c7  lea     rax, [rbp-10h+arg_18]
0x1800411cb  mov     [rsp+120h+var_F8], rax
0x1800411d0  lea     rax, [rbp-10h+var_60]
0x1800411d4  mov     [rsp+120h+var_100], rax
0x1800411d9  mov     [rbp-10h+var_60], 3000000h
0x1800411e1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800411e6  mov     rcx, rbx
0x1800411e9  mov     rbx, [rsp+120h+arg_8]
0x1800411f1  add     rsp, 110h
0x1800411f8  pop     rdi
0x1800411f9  pop     rsi
0x1800411fa  pop     rbp
0x1800411fb  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
