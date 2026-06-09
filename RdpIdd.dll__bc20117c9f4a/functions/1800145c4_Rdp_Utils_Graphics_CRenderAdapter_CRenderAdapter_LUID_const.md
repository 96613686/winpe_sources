# Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter(_LUID const &)

- ea: `0x1800145c4`
- end: `0x1800148f2`
- name: `??0CRenderAdapter@Graphics@Utils@Rdp@@QEAA@AEBU_LUID@@@Z`
- size: `814`
- prototype: `__int64 __fastcall(Rdp::Utils::Graphics::CRenderAdapter *__hidden this, const struct _LUID *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001638c`
- `0x18001d3fc`
- `0x180023308`

## callees

- `0x180002590`
- `0x180007b38`
- `0x18000d614`
- `0x18000ead8`
- `0x1800145c4`
- `0x18001ddf4`
- `0x180021570`
- `0x18003f010`

## import_xrefs

- `dxgi!CreateDXGIFactory2` at `0x18001461a`
- `dxgi!CreateDXGIFactory2` at `0x18001461a`

## string_xrefs

- `0x18001462a`: `Failed to create DXGI factory`
- `0x180014639`: `onecoreuap\termsrv\rdp_bin\win\common/inc/RenderAdapter.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Rdp::Utils::Graphics::CRenderAdapter *__fastcall Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter(
        Rdp::Utils::Graphics::CRenderAdapter *this,
        const struct _LUID *a2)
{
  char *v4; // r14
  unsigned int v5; // eax
  __int64 v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  _DWORD *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rcx
  char *v16; // [rsp+28h] [rbp-F8h]
  char *v17; // [rsp+28h] [rbp-F8h]
  char *v18; // [rsp+28h] [rbp-F8h]
  char *v19; // [rsp+28h] [rbp-F8h]
  DWORD LowPart; // [rsp+30h] [rbp-F0h]
  __int64 v21; // [rsp+A0h] [rbp-80h] BYREF
  void *ppFactory; // [rsp+A8h] [rbp-78h] BYREF
  int v23; // [rsp+B0h] [rbp-70h] BYREF
  int v24; // [rsp+B4h] [rbp-6Ch] BYREF
  int v25; // [rsp+B8h] [rbp-68h] BYREF
  int v26; // [rsp+BCh] [rbp-64h] BYREF
  int v27; // [rsp+C0h] [rbp-60h] BYREF
  int v28; // [rsp+C4h] [rbp-5Ch] BYREF
  int v29; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v30; // [rsp+D0h] [rbp-50h] BYREF
  char *v31; // [rsp+D8h] [rbp-48h] BYREF
  const char *v32; // [rsp+E0h] [rbp-40h] BYREF
  const char *v33; // [rsp+E8h] [rbp-38h] BYREF
  const char *v34; // [rsp+F0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+18h]
  int v36; // [rsp+148h] [rbp+28h] BYREF
  int v37; // [rsp+150h] [rbp+30h] BYREF
  int v38; // [rsp+158h] [rbp+38h] BYREF

  *(_BYTE *)this = 0;
  v4 = (char *)this + 8;
  memset_0((char *)this + 8, 0, 0x140u);
  *((_QWORD *)this + 41) = 0;
  ppFactory = 0;
  v5 = CreateDXGIFactory2(0, &GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a, &ppFactory);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xF8,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    (const char *)v5,
    (int)"Failed to create DXGI factory",
    v16);
  v21 = 0;
  v6 = *(_QWORD *)ppFactory;
  if ( *a2 )
  {
    v21 = 0;
    v8 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(v6 + 208))(
           ppFactory,
           *a2,
           &GUID_645967a4_1392_4310_a798_8053ce3e93fd,
           &v21);
    LowPart = a2->LowPart;
    LODWORD(v17) = a2->HighPart;
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x110,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
      (const char *)v8,
      (int)"Failed to enumerate render adapter by LUID: {%#x,%#x}",
      v17,
      LowPart);
  }
  else
  {
    v21 = 0;
    v7 = (*(__int64 (__fastcall **)(void *, GUID *, __int64 *))(v6 + 216))(
           ppFactory,
           &GUID_645967a4_1392_4310_a798_8053ce3e93fd,
           &v21);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
      (const char *)v7,
      (int)"Failed to enumerate WARP render adapter",
      v17);
  }
  v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v21 + 88LL))(v21, v4);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x117,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    (const char *)v9,
    (int)"Failed to get DXGI adapter description",
    v18);
  *(_BYTE *)this = (*((_DWORD *)this + 78) & 2) != 0;
  v10 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v10 > 4u )
  {
    v36 = *(unsigned __int8 *)this;
    v30 = *((_QWORD *)this + 38);
    v37 = *((_DWORD *)this + 78);
    v38 = *((_DWORD *)this + 74);
    v23 = *((_DWORD *)this + 72);
    v24 = *((_DWORD *)this + 70);
    v25 = *((_DWORD *)this + 69);
    v26 = *((_DWORD *)this + 68);
    v27 = *((_DWORD *)this + 67);
    v28 = *((_DWORD *)this + 66);
    v31 = v4;
    v32 = "Adapter description";
    v33 = "Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter";
    v29 = 295;
    v34 = "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v10,
      (unsigned int)&word_18004DDC6,
      v11,
      v12,
      (__int64)&v34,
      (__int64)&v29,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v23,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v30,
      (__int64)&v36);
  }
  LODWORD(v19) = *(unsigned __int8 *)this;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"RenderAdapter: IsWarp: %d",
    "Rdp::Utils::Graphics::CRenderAdapter::CRenderAdapter",
    "onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/RenderAdapter.h",
    0x128u,
    v19);
  v13 = v21;
  v21 = 0;
  v14 = *((_QWORD *)this + 41);
  *((_QWORD *)this + 41) = v13;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&v21);
  wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(&ppFactory);
  return this;
}

```

## disassembly

```asm
0x1800145c4  mov     [rsp-8+arg_0], rcx
0x1800145c9  push    rbp
0x1800145ca  push    rbx
0x1800145cb  push    rsi
0x1800145cc  push    rdi
0x1800145cd  push    r12
0x1800145cf  push    r14
0x1800145d1  lea     rbp, [rsp+18h]
0x1800145d6  sub     rsp, 108h
0x1800145dd  mov     rsi, rdx
0x1800145e0  mov     rbx, rcx
0x1800145e3  mov     byte ptr [rcx], 0
0x1800145e6  lea     r14, [rcx+8]
0x1800145ea  xor     edx, edx; Val
0x1800145ec  mov     r8d, 140h; Size
0x1800145f2  mov     rcx, r14; void *
0x1800145f5  call    memset_0
0x1800145fa  mov     qword ptr [rbx+148h], 0
0x180014605  mov     [rbp+10h+ppFactory], 0
0x18001460d  lea     r8, [rbp+10h+ppFactory]; ppFactory
0x180014611  lea     rdx, _GUID_1bc6ea02_ef36_464f_bf0c_21ca39e5168a; riid
0x180014618  xor     ecx, ecx; Flags
0x18001461a  call    cs:__imp_CreateDXGIFactory2
0x180014621  nop     dword ptr [rax+rax+00h]
0x180014626  mov     rcx, [rbp+18h]; this
0x18001462a  lea     rdx, aFailedToCreate_0; "Failed to create DXGI factory"
0x180014631  mov     qword ptr [rsp+130h+var_110], rdx; int
0x180014636  mov     r9d, eax; char *
0x180014639  lea     r12, aOnecoreuapTerm_2; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180014640  mov     r8, r12; unsigned int
0x180014643  mov     edx, 0F8h; void *
0x180014648  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001464d  mov     [rbp+10h+var_90], 0
0x180014655  mov     rax, qword ptr cs:stru_180046EE0.LowPart
0x18001465c  cmp     eax, [rsi]
0x18001465e  jnz     short loc_1800146B3
0x180014660  mov     eax, cs:stru_180046EE0.HighPart
0x180014666  cmp     eax, [rsi+4]
0x180014669  jnz     short loc_1800146B3
0x18001466b  mov     rcx, [rbp+10h+ppFactory]
0x18001466f  mov     rax, [rcx]
0x180014672  mov     [rbp+10h+var_90], 0
0x18001467a  lea     r8, [rbp+10h+var_90]
0x18001467e  lea     rdx, _GUID_645967a4_1392_4310_a798_8053ce3e93fd
0x180014685  mov     rax, [rax+0D8h]
0x18001468c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014691  mov     rcx, [rbp+18h]; this
0x180014695  lea     rdx, aFailedToEnumer_0; "Failed to enumerate WARP render adapter"
0x18001469c  mov     qword ptr [rsp+130h+var_110], rdx; int
0x1800146a1  mov     r9d, eax; char *
0x1800146a4  mov     r8, r12; unsigned int
0x1800146a7  mov     edx, 104h; void *
0x1800146ac  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800146b1  jmp     short loc_180014709
0x1800146b3  mov     rcx, [rbp+10h+ppFactory]
0x1800146b7  mov     rax, [rcx]
0x1800146ba  mov     [rbp+10h+var_90], 0
0x1800146c2  lea     r9, [rbp+10h+var_90]
0x1800146c6  lea     r8, _GUID_645967a4_1392_4310_a798_8053ce3e93fd
0x1800146cd  mov     rdx, [rsi]
0x1800146d0  mov     rax, [rax+0D0h]
0x1800146d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146dc  mov     rcx, [rbp+18h]; this
0x1800146e0  mov     edx, [rsi]
0x1800146e2  mov     dword ptr [rsp+130h+var_100], edx
0x1800146e6  mov     edx, [rsi+4]
0x1800146e9  mov     dword ptr [rsp+130h+var_108], edx; char *
0x1800146ed  lea     rdx, aFailedToEnumer; "Failed to enumerate render adapter by L"...
0x1800146f4  mov     qword ptr [rsp+130h+var_110], rdx; int
0x1800146f9  mov     r9d, eax; char *
0x1800146fc  mov     r8, r12; unsigned int
0x1800146ff  mov     edx, 110h; void *
0x180014704  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014709  mov     rcx, [rbp+10h+var_90]
0x18001470d  mov     rax, [rcx]
0x180014710  mov     rdx, r14
0x180014713  mov     rax, [rax+58h]
0x180014717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001471c  mov     rcx, [rbp+18h]; this
0x180014720  lea     rdx, aFailedToGetDxg; "Failed to get DXGI adapter description"
0x180014727  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18001472c  mov     r9d, eax; char *
0x18001472f  mov     r8, r12; unsigned int
0x180014732  mov     edx, 117h; void *
0x180014737  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001473c  mov     eax, [rbx+138h]
0x180014742  shr     eax, 1
0x180014744  and     al, 1
0x180014746  mov     [rbx], al
0x180014748  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001474d  mov     rcx, [rax+8]
0x180014751  mov     eax, [rcx]
0x180014753  lea     rdi, aRdpUtilsGraphi; "Rdp::Utils::Graphics::CRenderAdapter::C"...
0x18001475a  cmp     eax, 4
0x18001475d  jbe     loc_180014876
0x180014763  movzx   eax, byte ptr [rbx]
0x180014766  mov     [rbp+10h+arg_8], eax
0x180014769  mov     rax, [rbx+130h]
0x180014770  mov     [rbp+10h+var_60], rax
0x180014774  mov     eax, [rbx+138h]
0x18001477a  mov     [rbp+10h+arg_10], eax
0x18001477d  mov     eax, [rbx+128h]
0x180014783  mov     [rbp+10h+arg_18], eax
0x180014786  mov     eax, [rbx+120h]
0x18001478c  mov     [rbp+10h+var_80], eax
0x18001478f  mov     eax, [rbx+118h]
0x180014795  mov     [rbp+10h+var_7C], eax
0x180014798  mov     eax, [rbx+114h]
0x18001479e  mov     [rbp+10h+var_78], eax
0x1800147a1  mov     eax, [rbx+110h]
0x1800147a7  mov     [rbp+10h+var_74], eax
0x1800147aa  mov     eax, [rbx+10Ch]
0x1800147b0  mov     [rbp+10h+var_70], eax
0x1800147b3  mov     eax, [rbx+108h]
0x1800147b9  mov     [rbp+10h+var_6C], eax
0x1800147bc  mov     [rbp+10h+var_58], r14
0x1800147c0  lea     rax, aAdapterDescrip; "Adapter description"
0x1800147c7  mov     [rbp+10h+var_50], rax
0x1800147cb  mov     [rbp+10h+var_48], rdi
0x1800147cf  mov     [rbp+10h+var_68], 127h
0x1800147d6  mov     [rbp+10h+var_40], r12
0x1800147da  lea     rax, [rbp+10h+arg_8]
0x1800147de  mov     [rsp+130h+var_A0], rax
0x1800147e6  lea     rax, [rbp+10h+var_60]
0x1800147ea  mov     [rsp+130h+var_A8], rax
0x1800147f2  lea     rax, [rbp+10h+arg_10]
0x1800147f6  mov     [rsp+130h+var_B0], rax
0x1800147fe  lea     rax, [rbp+10h+arg_18]
0x180014802  mov     [rsp+130h+var_B8], rax
0x180014807  lea     rax, [rbp+10h+var_80]
0x18001480b  mov     [rsp+130h+var_C0], rax
0x180014810  lea     rax, [rbp+10h+var_7C]
0x180014814  mov     [rsp+130h+var_C8], rax
0x180014819  lea     rax, [rbp+10h+var_78]
0x18001481d  mov     [rsp+130h+var_D0], rax
0x180014822  lea     rax, [rbp+10h+var_74]
0x180014826  mov     [rsp+130h+var_D8], rax
0x18001482b  lea     rax, [rbp+10h+var_70]
0x18001482f  mov     [rsp+130h+var_E0], rax
0x180014834  lea     rax, [rbp+10h+var_6C]
0x180014838  mov     [rsp+130h+var_E8], rax
0x18001483d  lea     rax, [rbp+10h+var_58]
0x180014841  mov     [rsp+130h+var_F0], rax
0x180014846  lea     rax, [rbp+10h+var_50]
0x18001484a  mov     [rsp+130h+var_F8], rax
0x18001484f  lea     rax, [rbp+10h+var_48]
0x180014853  mov     [rsp+130h+var_100], rax
0x180014858  lea     rax, [rbp+10h+var_68]
0x18001485c  mov     [rsp+130h+var_108], rax
0x180014861  lea     rax, [rbp+10h+var_40]
0x180014865  mov     qword ptr [rsp+130h+var_110], rax
0x18001486a  lea     rdx, word_18004DDC6
0x180014871  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U?$_tlgWrapSz@G@@U2@U2@U2@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33AEBU?$_tlgWrapSz@G@@44444444AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180014876  movzx   eax, byte ptr [rbx]
0x180014879  mov     dword ptr [rsp+130h+var_108], eax
0x18001487d  mov     [rsp+130h+var_110], 128h; unsigned int
0x180014885  mov     r9, r12; char *
0x180014888  mov     r8, rdi; char *
0x18001488b  lea     rdx, aRenderadapterI; "RenderAdapter: IsWarp: %d"
0x180014892  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180014899  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001489e  mov     rax, [rbp+10h+var_90]
0x1800148a2  mov     [rbp+10h+var_90], 0
0x1800148aa  mov     rcx, [rbx+148h]
0x1800148b1  mov     [rbx+148h], rax
0x1800148b8  test    rcx, rcx
0x1800148bb  jz      short loc_1800148CA
0x1800148bd  mov     rax, [rcx]
0x1800148c0  mov     rax, [rax+10h]
0x1800148c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c9  nop
0x1800148ca  lea     rcx, [rbp+10h+var_90]
0x1800148ce  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x1800148d3  nop
0x1800148d4  lea     rcx, [rbp+10h+ppFactory]
0x1800148d8  call    ??1?$com_ptr_t@UIColorSpaceTransform@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>::~com_ptr_t<Rdp::Avenc::IColorSpaceTransform,wil::err_exception_policy>(void)
0x1800148dd  nop
0x1800148de  mov     rax, rbx
0x1800148e1  add     rsp, 108h
0x1800148e8  pop     r14
0x1800148ea  pop     r12
0x1800148ec  pop     rdi
0x1800148ed  pop     rsi
0x1800148ee  pop     rbx
0x1800148ef  pop     rbp
0x1800148f0  retn
```
