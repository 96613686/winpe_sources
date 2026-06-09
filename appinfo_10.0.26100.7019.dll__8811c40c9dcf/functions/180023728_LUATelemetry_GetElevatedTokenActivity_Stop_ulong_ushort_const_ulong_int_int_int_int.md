# LUATelemetry::GetElevatedTokenActivity::Stop(ulong,ushort const *,ulong,int,int,int,int)

- ea: `0x180023728`
- end: `0x180023a74`
- name: `?Stop@GetElevatedTokenActivity@LUATelemetry@@QEAAXKPEBGKHHHH@Z`
- size: `844`
- prototype: `void(LUATelemetry::GetElevatedTokenActivity *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, int, int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800249f0`

## callees

- `0x18000110c`
- `0x18000148c`
- `0x18000cb30`
- `0x180018ac0`
- `0x180020fe0`
- `0x180021008`
- `0x180023728`
- `0x180023e1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800239bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800239bf`

## pseudocode

```c
void __fastcall LUATelemetry::GetElevatedTokenActivity::Stop(
        LUATelemetry::GetElevatedTokenActivity *this,
        int a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8)
{
  __int64 v8; // rax
  int v13; // ecx
  __int64 v14; // rdi
  struct LUATelemetry *v15; // rax
  _DWORD *v16; // rsi
  __int64 v17; // r8
  int v18; // r9d
  struct LUATelemetry *v19; // rax
  _DWORD *v20; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v22; // r8
  int v23; // r9d
  int v24; // [rsp+E0h] [rbp-80h] BYREF
  DWORD v25; // [rsp+E4h] [rbp-7Ch] BYREF
  int v26; // [rsp+E8h] [rbp-78h] BYREF
  int v27; // [rsp+ECh] [rbp-74h] BYREF
  int v28; // [rsp+F0h] [rbp-70h] BYREF
  int v29; // [rsp+F4h] [rbp-6Ch] BYREF
  int v30; // [rsp+F8h] [rbp-68h] BYREF
  int v31; // [rsp+FCh] [rbp-64h] BYREF
  int v32; // [rsp+100h] [rbp-60h] BYREF
  int v33; // [rsp+104h] [rbp-5Ch] BYREF
  int v34; // [rsp+108h] [rbp-58h] BYREF
  __int64 v35; // [rsp+110h] [rbp-50h] BYREF
  __int64 v36; // [rsp+118h] [rbp-48h] BYREF
  const unsigned __int16 *v37; // [rsp+120h] [rbp-40h] BYREF
  __int64 v38; // [rsp+128h] [rbp-38h] BYREF
  __int64 v39; // [rsp+130h] [rbp-30h] BYREF
  __int64 v40; // [rsp+138h] [rbp-28h] BYREF
  __int64 v41; // [rsp+140h] [rbp-20h] BYREF
  __int64 v42; // [rsp+148h] [rbp-18h] BYREF
  __int64 v43; // [rsp+150h] [rbp-10h] BYREF
  __int64 v44; // [rsp+158h] [rbp-8h] BYREF
  __int64 v45; // [rsp+160h] [rbp+0h] BYREF
  int v46; // [rsp+1A0h] [rbp+40h] BYREF

  v8 = *((_QWORD *)this + 34);
  v13 = *(_DWORD *)(v8 + 72);
  if ( v13 >= 0 || v13 != *(_DWORD *)(v8 + 88) || (v14 = v8 + 80, v8 == -80) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v19 = LUATelemetry::Instance();
    v20 = (_DWORD *)*((_QWORD *)v19 + 1);
    if ( *v20 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v19 + 1), 0x400000000000LL) )
    {
      v46 = a8;
      v30 = a7;
      v29 = a6;
      v28 = a5;
      v27 = a4;
      v36 = (__int64)LUATelemetry::TelemetryRemovePIIfromFilePath_LUA(a3);
      v26 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v22 = *((_QWORD *)this + 34);
      v25 = CurrentThreadId;
      v24 = *(_DWORD *)(v22 + 72);
      v35 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v20,
        (unsigned int)&unk_18004E8E2,
        v22 + 8,
        v23,
        (__int64)&v35,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v36,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v46);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v15 = LUATelemetry::Instance();
    v16 = (_DWORD *)*((_QWORD *)v15 + 1);
    if ( *v16 > 5u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)v15 + 1), 0x400000000000LL) )
    {
      v46 = a8;
      v31 = a7;
      v32 = a6;
      v33 = a5;
      v34 = a4;
      v37 = LUATelemetry::TelemetryRemovePIIfromFilePath_LUA(a3);
      v38 = *(_QWORD *)(v14 + 120);
      v17 = *((_QWORD *)this + 34);
      v39 = *(_QWORD *)(v14 + 112);
      v25 = *(_DWORD *)(v14 + 104);
      v40 = *(_QWORD *)(v14 + 96);
      v41 = *(_QWORD *)(v14 + 88);
      v26 = *(_DWORD *)(v14 + 80);
      v42 = *(_QWORD *)(v14 + 72);
      v27 = *(_DWORD *)(v14 + 32);
      v43 = *(_QWORD *)(v14 + 24);
      v28 = *(_DWORD *)v14;
      v44 = *(_QWORD *)(v14 + 128);
      v29 = *(_DWORD *)(v14 + 64);
      v45 = *(_QWORD *)(v14 + 56);
      v30 = *(_DWORD *)(v14 + 8);
      v24 = a2;
      v35 = 0x1000000;
      v36 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v16,
        (unsigned int)&unk_18004EACD,
        v17 + 8,
        v18,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v30,
        (__int64)&v45,
        (__int64)&v29,
        (__int64)&v44,
        (__int64)&v28,
        (__int64)&v43,
        (__int64)&v27,
        (__int64)&v42,
        (__int64)&v26,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v25,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v24,
        (__int64)&v37,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v46);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180023728  mov     [rsp-8+arg_8], rbx
0x18002372d  mov     [rsp-8+arg_10], rsi
0x180023732  push    rbp
0x180023733  push    rdi
0x180023734  push    r12
0x180023736  push    r14
0x180023738  push    r15
0x18002373a  lea     rbp, [rsp-10h]
0x18002373f  sub     rsp, 170h
0x180023746  mov     rax, [rcx+110h]
0x18002374d  mov     rbx, rcx
0x180023750  mov     r14d, r9d
0x180023753  mov     r15, r8
0x180023756  mov     r12d, edx
0x180023759  mov     ecx, [rax+48h]
0x18002375c  test    ecx, ecx
0x18002375e  jns     loc_18002395F
0x180023764  cmp     ecx, [rax+58h]
0x180023767  jnz     loc_18002395F
0x18002376d  lea     rdi, [rax+50h]
0x180023771  test    rdi, rdi
0x180023774  jz      loc_18002395F
0x18002377a  mov     rcx, rbx
0x18002377d  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180023782  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180023787  mov     rsi, [rax+8]
0x18002378b  cmp     dword ptr [rsi], 5
0x18002378e  jbe     loc_180023A51
0x180023794  mov     rdx, 400000000000h
0x18002379e  mov     rcx, rsi
0x1800237a1  call    _tlgKeywordOn
0x1800237a6  test    al, al
0x1800237a8  jz      loc_180023A51
0x1800237ae  mov     eax, [rbp+30h+arg_38]
0x1800237b1  mov     rcx, r15; unsigned __int16 *
0x1800237b4  mov     [rbp+30h+arg_0], eax
0x1800237b7  mov     eax, [rbp+30h+arg_30]
0x1800237ba  mov     [rbp+30h+var_94], eax
0x1800237bd  mov     eax, [rbp+30h+arg_28]
0x1800237c0  mov     [rbp+30h+var_90], eax
0x1800237c3  mov     eax, [rbp+30h+arg_20]
0x1800237c6  mov     [rbp+30h+var_8C], eax
0x1800237c9  mov     [rbp+30h+var_88], r14d
0x1800237cd  call    ?TelemetryRemovePIIfromFilePath_LUA@LUATelemetry@@CAPEBGPEBG@Z; LUATelemetry::TelemetryRemovePIIfromFilePath_LUA(ushort const *)
0x1800237d2  mov     [rbp+30h+var_70], rax
0x1800237d6  mov     rax, [rdi+78h]
0x1800237da  mov     [rbp+30h+var_68], rax
0x1800237de  mov     rax, [rdi+70h]
0x1800237e2  mov     r8, [rbx+110h]
0x1800237e9  mov     [rbp+30h+var_60], rax
0x1800237ed  add     r8, 8
0x1800237f1  mov     eax, [rdi+68h]
0x1800237f4  mov     [rbp+30h+var_AC], eax
0x1800237f7  mov     rax, [rdi+60h]
0x1800237fb  mov     [rbp+30h+var_58], rax
0x1800237ff  mov     rax, [rdi+58h]
0x180023803  mov     [rbp+30h+var_50], rax
0x180023807  mov     eax, [rdi+50h]
0x18002380a  mov     [rbp+30h+var_A8], eax
0x18002380d  mov     rax, [rdi+48h]
0x180023811  mov     [rbp+30h+var_48], rax
0x180023815  mov     eax, [rdi+20h]
0x180023818  mov     [rbp+30h+var_A4], eax
0x18002381b  mov     rax, [rdi+18h]
0x18002381f  mov     [rbp+30h+var_40], rax
0x180023823  mov     eax, [rdi]
0x180023825  mov     [rbp+30h+var_A0], eax
0x180023828  mov     rax, [rdi+80h]
0x18002382f  mov     [rbp+30h+var_38], rax
0x180023833  mov     eax, [rdi+40h]
0x180023836  mov     [rbp+30h+var_9C], eax
0x180023839  mov     rax, [rdi+38h]
0x18002383d  mov     [rbp+30h+var_30], rax
0x180023841  mov     eax, [rdi+8]
0x180023844  mov     [rbp+30h+var_98], eax
0x180023847  lea     rax, [rbp+30h+arg_0]
0x18002384b  mov     [rsp+190h+var_C0], rax
0x180023853  lea     rax, [rbp+30h+var_94]
0x180023857  mov     [rsp+190h+var_C8], rax
0x18002385f  lea     rax, [rbp+30h+var_90]
0x180023863  mov     [rsp+190h+var_D0], rax
0x18002386b  lea     rax, [rbp+30h+var_8C]
0x18002386f  mov     [rsp+190h+var_D8], rax
0x180023877  lea     rax, [rbp+30h+var_88]
0x18002387b  mov     [rsp+190h+var_E0], rax
0x180023883  lea     rax, [rbp+30h+var_70]
0x180023887  mov     [rsp+190h+var_E8], rax
0x18002388f  lea     rax, [rbp+30h+var_B0]
0x180023893  mov     [rsp+190h+var_F0], rax
0x18002389b  lea     rax, [rbp+30h+var_68]
0x18002389f  mov     [rsp+190h+var_F8], rax
0x1800238a7  lea     rax, [rbp+30h+var_60]
0x1800238ab  mov     [rsp+190h+var_100], rax
0x1800238b3  lea     rax, [rbp+30h+var_AC]
0x1800238b7  mov     [rsp+190h+var_108], rax
0x1800238bf  lea     rax, [rbp+30h+var_58]
0x1800238c3  mov     [rsp+190h+var_110], rax
0x1800238cb  lea     rax, [rbp+30h+var_50]
0x1800238cf  mov     [rsp+190h+var_118], rax
0x1800238d4  lea     rax, [rbp+30h+var_A8]
0x1800238d8  mov     [rsp+190h+var_120], rax
0x1800238dd  lea     rax, [rbp+30h+var_48]
0x1800238e1  mov     [rsp+190h+var_128], rax
0x1800238e6  lea     rax, [rbp+30h+var_A4]
0x1800238ea  mov     [rsp+190h+var_130], rax
0x1800238ef  lea     rax, [rbp+30h+var_40]
0x1800238f3  mov     [rsp+190h+var_138], rax
0x1800238f8  lea     rax, [rbp+30h+var_A0]
0x1800238fc  mov     [rsp+190h+var_140], rax
0x180023901  lea     rax, [rbp+30h+var_38]
0x180023905  mov     [rsp+190h+var_148], rax
0x18002390a  mov     [rbp+30h+var_B0], r12d
0x18002390e  mov     [rbp+30h+var_80], 1000000h
0x180023916  mov     [rbp+30h+var_78], 3000000h
0x18002391e  lea     rax, [rbp+30h+var_9C]
0x180023922  mov     rcx, rsi
0x180023925  mov     [rsp+190h+var_150], rax
0x18002392a  lea     rdx, unk_18004EACD
0x180023931  lea     rax, [rbp+30h+var_30]
0x180023935  mov     [rsp+190h+var_158], rax
0x18002393a  lea     rax, [rbp+30h+var_98]
0x18002393e  mov     [rsp+190h+var_160], rax
0x180023943  lea     rax, [rbp+30h+var_80]
0x180023947  mov     [rsp+190h+var_168], rax
0x18002394c  lea     rax, [rbp+30h+var_78]
0x180023950  mov     [rsp+190h+var_170], rax
0x180023955  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U4@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564644444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002395a  jmp     loc_180023A51
0x18002395f  mov     rcx, rbx
0x180023962  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180023967  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18002396c  mov     rdi, [rax+8]
0x180023970  cmp     dword ptr [rdi], 5
0x180023973  jbe     loc_180023A51
0x180023979  mov     rdx, 400000000000h
0x180023983  mov     rcx, rdi
0x180023986  call    _tlgKeywordOn
0x18002398b  test    al, al
0x18002398d  jz      loc_180023A51
0x180023993  mov     eax, [rbp+30h+arg_38]
0x180023996  mov     rcx, r15; unsigned __int16 *
0x180023999  mov     [rbp+30h+arg_0], eax
0x18002399c  mov     eax, [rbp+30h+arg_30]
0x18002399f  mov     [rbp+30h+var_98], eax
0x1800239a2  mov     eax, [rbp+30h+arg_28]
0x1800239a5  mov     [rbp+30h+var_9C], eax
0x1800239a8  mov     eax, [rbp+30h+arg_20]
0x1800239ab  mov     [rbp+30h+var_A0], eax
0x1800239ae  mov     [rbp+30h+var_A4], r14d
0x1800239b2  call    ?TelemetryRemovePIIfromFilePath_LUA@LUATelemetry@@CAPEBGPEBG@Z; LUATelemetry::TelemetryRemovePIIfromFilePath_LUA(ushort const *)
0x1800239b7  mov     [rbp+30h+var_78], rax
0x1800239bb  mov     [rbp+30h+var_A8], r12d
0x1800239bf  call    cs:__imp_GetCurrentThreadId
0x1800239c6  nop     dword ptr [rax+rax+00h]
0x1800239cb  mov     r8, [rbx+110h]
0x1800239d2  lea     rdx, unk_18004E8E2
0x1800239d9  mov     [rbp+30h+var_AC], eax
0x1800239dc  mov     rcx, rdi
0x1800239df  mov     eax, [r8+48h]
0x1800239e3  add     r8, 8
0x1800239e7  mov     [rbp+30h+var_B0], eax
0x1800239ea  lea     rax, [rbp+30h+arg_0]
0x1800239ee  mov     [rsp+190h+var_128], rax
0x1800239f3  lea     rax, [rbp+30h+var_98]
0x1800239f7  mov     [rsp+190h+var_130], rax
0x1800239fc  lea     rax, [rbp+30h+var_9C]
0x180023a00  mov     [rsp+190h+var_138], rax
0x180023a05  lea     rax, [rbp+30h+var_A0]
0x180023a09  mov     [rsp+190h+var_140], rax
0x180023a0e  lea     rax, [rbp+30h+var_A4]
0x180023a12  mov     [rsp+190h+var_148], rax
0x180023a17  lea     rax, [rbp+30h+var_78]
0x180023a1b  mov     [rsp+190h+var_150], rax
0x180023a20  lea     rax, [rbp+30h+var_A8]
0x180023a24  mov     [rsp+190h+var_158], rax
0x180023a29  lea     rax, [rbp+30h+var_AC]
0x180023a2d  mov     [rsp+190h+var_160], rax
0x180023a32  lea     rax, [rbp+30h+var_B0]
0x180023a36  mov     [rsp+190h+var_168], rax
0x180023a3b  lea     rax, [rbp+30h+var_80]
0x180023a3f  mov     [rsp+190h+var_170], rax
0x180023a44  mov     [rbp+30h+var_80], 3000000h
0x180023a4c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180023a51  mov     rcx, rbx
0x180023a54  lea     r11, [rsp+190h+var_20]
0x180023a5c  mov     rbx, [r11+38h]
0x180023a60  mov     rsi, [r11+40h]
0x180023a64  mov     rsp, r11
0x180023a67  pop     r15
0x180023a69  pop     r14
0x180023a6b  pop     r12
0x180023a6d  pop     rdi
0x180023a6e  pop     rbp
0x180023a6f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
