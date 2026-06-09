# LUATelemetry::GetElevatedTokenActivity::Stop(ulong,ushort const *,ulong,int,int,int,int)

- ea: `0x180021ed8`
- end: `0x180022224`
- name: `?Stop@GetElevatedTokenActivity@LUATelemetry@@QEAAXKPEBGKHHHH@Z`
- size: `844`
- prototype: `void(LUATelemetry::GetElevatedTokenActivity *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, int, int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800230e0`

## callees

- `0x18000110c`
- `0x18000148c`
- `0x18000cb30`
- `0x180018d70`
- `0x18001fd6c`
- `0x18001fd94`
- `0x180021ed8`
- `0x1800225cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002216f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002216f`

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
        (unsigned int)&unk_18005097A,
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
        (unsigned int)&unk_180050B65,
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
0x180021ed8  mov     [rsp-8+arg_8], rbx
0x180021edd  mov     [rsp-8+arg_10], rsi
0x180021ee2  push    rbp
0x180021ee3  push    rdi
0x180021ee4  push    r12
0x180021ee6  push    r14
0x180021ee8  push    r15
0x180021eea  lea     rbp, [rsp-10h]
0x180021eef  sub     rsp, 170h
0x180021ef6  mov     rax, [rcx+110h]
0x180021efd  mov     rbx, rcx
0x180021f00  mov     r14d, r9d
0x180021f03  mov     r15, r8
0x180021f06  mov     r12d, edx
0x180021f09  mov     ecx, [rax+48h]
0x180021f0c  test    ecx, ecx
0x180021f0e  jns     loc_18002210F
0x180021f14  cmp     ecx, [rax+58h]
0x180021f17  jnz     loc_18002210F
0x180021f1d  lea     rdi, [rax+50h]
0x180021f21  test    rdi, rdi
0x180021f24  jz      loc_18002210F
0x180021f2a  mov     rcx, rbx
0x180021f2d  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180021f32  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180021f37  mov     rsi, [rax+8]
0x180021f3b  cmp     dword ptr [rsi], 5
0x180021f3e  jbe     loc_180022201
0x180021f44  mov     rdx, 400000000000h
0x180021f4e  mov     rcx, rsi
0x180021f51  call    _tlgKeywordOn
0x180021f56  test    al, al
0x180021f58  jz      loc_180022201
0x180021f5e  mov     eax, [rbp+30h+arg_38]
0x180021f61  mov     rcx, r15; unsigned __int16 *
0x180021f64  mov     [rbp+30h+arg_0], eax
0x180021f67  mov     eax, [rbp+30h+arg_30]
0x180021f6a  mov     [rbp+30h+var_94], eax
0x180021f6d  mov     eax, [rbp+30h+arg_28]
0x180021f70  mov     [rbp+30h+var_90], eax
0x180021f73  mov     eax, [rbp+30h+arg_20]
0x180021f76  mov     [rbp+30h+var_8C], eax
0x180021f79  mov     [rbp+30h+var_88], r14d
0x180021f7d  call    ?TelemetryRemovePIIfromFilePath_LUA@LUATelemetry@@CAPEBGPEBG@Z; LUATelemetry::TelemetryRemovePIIfromFilePath_LUA(ushort const *)
0x180021f82  mov     [rbp+30h+var_70], rax
0x180021f86  mov     rax, [rdi+78h]
0x180021f8a  mov     [rbp+30h+var_68], rax
0x180021f8e  mov     rax, [rdi+70h]
0x180021f92  mov     r8, [rbx+110h]
0x180021f99  mov     [rbp+30h+var_60], rax
0x180021f9d  add     r8, 8
0x180021fa1  mov     eax, [rdi+68h]
0x180021fa4  mov     [rbp+30h+var_AC], eax
0x180021fa7  mov     rax, [rdi+60h]
0x180021fab  mov     [rbp+30h+var_58], rax
0x180021faf  mov     rax, [rdi+58h]
0x180021fb3  mov     [rbp+30h+var_50], rax
0x180021fb7  mov     eax, [rdi+50h]
0x180021fba  mov     [rbp+30h+var_A8], eax
0x180021fbd  mov     rax, [rdi+48h]
0x180021fc1  mov     [rbp+30h+var_48], rax
0x180021fc5  mov     eax, [rdi+20h]
0x180021fc8  mov     [rbp+30h+var_A4], eax
0x180021fcb  mov     rax, [rdi+18h]
0x180021fcf  mov     [rbp+30h+var_40], rax
0x180021fd3  mov     eax, [rdi]
0x180021fd5  mov     [rbp+30h+var_A0], eax
0x180021fd8  mov     rax, [rdi+80h]
0x180021fdf  mov     [rbp+30h+var_38], rax
0x180021fe3  mov     eax, [rdi+40h]
0x180021fe6  mov     [rbp+30h+var_9C], eax
0x180021fe9  mov     rax, [rdi+38h]
0x180021fed  mov     [rbp+30h+var_30], rax
0x180021ff1  mov     eax, [rdi+8]
0x180021ff4  mov     [rbp+30h+var_98], eax
0x180021ff7  lea     rax, [rbp+30h+arg_0]
0x180021ffb  mov     [rsp+190h+var_C0], rax
0x180022003  lea     rax, [rbp+30h+var_94]
0x180022007  mov     [rsp+190h+var_C8], rax
0x18002200f  lea     rax, [rbp+30h+var_90]
0x180022013  mov     [rsp+190h+var_D0], rax
0x18002201b  lea     rax, [rbp+30h+var_8C]
0x18002201f  mov     [rsp+190h+var_D8], rax
0x180022027  lea     rax, [rbp+30h+var_88]
0x18002202b  mov     [rsp+190h+var_E0], rax
0x180022033  lea     rax, [rbp+30h+var_70]
0x180022037  mov     [rsp+190h+var_E8], rax
0x18002203f  lea     rax, [rbp+30h+var_B0]
0x180022043  mov     [rsp+190h+var_F0], rax
0x18002204b  lea     rax, [rbp+30h+var_68]
0x18002204f  mov     [rsp+190h+var_F8], rax
0x180022057  lea     rax, [rbp+30h+var_60]
0x18002205b  mov     [rsp+190h+var_100], rax
0x180022063  lea     rax, [rbp+30h+var_AC]
0x180022067  mov     [rsp+190h+var_108], rax
0x18002206f  lea     rax, [rbp+30h+var_58]
0x180022073  mov     [rsp+190h+var_110], rax
0x18002207b  lea     rax, [rbp+30h+var_50]
0x18002207f  mov     [rsp+190h+var_118], rax
0x180022084  lea     rax, [rbp+30h+var_A8]
0x180022088  mov     [rsp+190h+var_120], rax
0x18002208d  lea     rax, [rbp+30h+var_48]
0x180022091  mov     [rsp+190h+var_128], rax
0x180022096  lea     rax, [rbp+30h+var_A4]
0x18002209a  mov     [rsp+190h+var_130], rax
0x18002209f  lea     rax, [rbp+30h+var_40]
0x1800220a3  mov     [rsp+190h+var_138], rax
0x1800220a8  lea     rax, [rbp+30h+var_A0]
0x1800220ac  mov     [rsp+190h+var_140], rax
0x1800220b1  lea     rax, [rbp+30h+var_38]
0x1800220b5  mov     [rsp+190h+var_148], rax
0x1800220ba  mov     [rbp+30h+var_B0], r12d
0x1800220be  mov     [rbp+30h+var_80], 1000000h
0x1800220c6  mov     [rbp+30h+var_78], 3000000h
0x1800220ce  lea     rax, [rbp+30h+var_9C]
0x1800220d2  mov     rcx, rsi
0x1800220d5  mov     [rsp+190h+var_150], rax
0x1800220da  lea     rdx, unk_180050B65
0x1800220e1  lea     rax, [rbp+30h+var_30]
0x1800220e5  mov     [rsp+190h+var_158], rax
0x1800220ea  lea     rax, [rbp+30h+var_98]
0x1800220ee  mov     [rsp+190h+var_160], rax
0x1800220f3  lea     rax, [rbp+30h+var_80]
0x1800220f7  mov     [rsp+190h+var_168], rax
0x1800220fc  lea     rax, [rbp+30h+var_78]
0x180022100  mov     [rsp+190h+var_170], rax
0x180022105  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U4@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564644444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002210a  jmp     loc_180022201
0x18002210f  mov     rcx, rbx
0x180022112  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180022117  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18002211c  mov     rdi, [rax+8]
0x180022120  cmp     dword ptr [rdi], 5
0x180022123  jbe     loc_180022201
0x180022129  mov     rdx, 400000000000h
0x180022133  mov     rcx, rdi
0x180022136  call    _tlgKeywordOn
0x18002213b  test    al, al
0x18002213d  jz      loc_180022201
0x180022143  mov     eax, [rbp+30h+arg_38]
0x180022146  mov     rcx, r15; unsigned __int16 *
0x180022149  mov     [rbp+30h+arg_0], eax
0x18002214c  mov     eax, [rbp+30h+arg_30]
0x18002214f  mov     [rbp+30h+var_98], eax
0x180022152  mov     eax, [rbp+30h+arg_28]
0x180022155  mov     [rbp+30h+var_9C], eax
0x180022158  mov     eax, [rbp+30h+arg_20]
0x18002215b  mov     [rbp+30h+var_A0], eax
0x18002215e  mov     [rbp+30h+var_A4], r14d
0x180022162  call    ?TelemetryRemovePIIfromFilePath_LUA@LUATelemetry@@CAPEBGPEBG@Z; LUATelemetry::TelemetryRemovePIIfromFilePath_LUA(ushort const *)
0x180022167  mov     [rbp+30h+var_78], rax
0x18002216b  mov     [rbp+30h+var_A8], r12d
0x18002216f  call    cs:__imp_GetCurrentThreadId
0x180022176  nop     dword ptr [rax+rax+00h]
0x18002217b  mov     r8, [rbx+110h]
0x180022182  lea     rdx, unk_18005097A
0x180022189  mov     [rbp+30h+var_AC], eax
0x18002218c  mov     rcx, rdi
0x18002218f  mov     eax, [r8+48h]
0x180022193  add     r8, 8
0x180022197  mov     [rbp+30h+var_B0], eax
0x18002219a  lea     rax, [rbp+30h+arg_0]
0x18002219e  mov     [rsp+190h+var_128], rax
0x1800221a3  lea     rax, [rbp+30h+var_98]
0x1800221a7  mov     [rsp+190h+var_130], rax
0x1800221ac  lea     rax, [rbp+30h+var_9C]
0x1800221b0  mov     [rsp+190h+var_138], rax
0x1800221b5  lea     rax, [rbp+30h+var_A0]
0x1800221b9  mov     [rsp+190h+var_140], rax
0x1800221be  lea     rax, [rbp+30h+var_A4]
0x1800221c2  mov     [rsp+190h+var_148], rax
0x1800221c7  lea     rax, [rbp+30h+var_78]
0x1800221cb  mov     [rsp+190h+var_150], rax
0x1800221d0  lea     rax, [rbp+30h+var_A8]
0x1800221d4  mov     [rsp+190h+var_158], rax
0x1800221d9  lea     rax, [rbp+30h+var_AC]
0x1800221dd  mov     [rsp+190h+var_160], rax
0x1800221e2  lea     rax, [rbp+30h+var_B0]
0x1800221e6  mov     [rsp+190h+var_168], rax
0x1800221eb  lea     rax, [rbp+30h+var_80]
0x1800221ef  mov     [rsp+190h+var_170], rax
0x1800221f4  mov     [rbp+30h+var_80], 3000000h
0x1800221fc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapSz@G@@44444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180022201  mov     rcx, rbx
0x180022204  lea     r11, [rsp+190h+var_20]
0x18002220c  mov     rbx, [r11+38h]
0x180022210  mov     rsi, [r11+40h]
0x180022214  mov     rsp, r11
0x180022217  pop     r15
0x180022219  pop     r14
0x18002221b  pop     r12
0x18002221d  pop     rdi
0x18002221e  pop     rbp
0x18002221f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
