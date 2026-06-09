# Wns::ConnectionProviderLoader::ConnectionProviderLoader(Wns::ConnectionStateMachine *)

- ea: `0x1800214d0`
- end: `0x180021748`
- name: `??0ConnectionProviderLoader@Wns@@QEAA@PEAVConnectionStateMachine@1@@Z`
- size: `632`
- prototype: `Wns::ConnectionProviderLoader *__fastcall(Wns::ConnectionProviderLoader **this, struct Wns::ConnectionStateMachine *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021468`

## callees

- `0x180003190`
- `0x180013394`
- `0x180014260`
- `0x180014950`
- `0x180018164`
- `0x180021048`
- `0x1800214d0`
- `0x180021750`
- `0x18002179c`
- `0x180026200`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021598`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800215de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180021598`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800215de`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
Wns::ConnectionProviderLoader *__fastcall Wns::ConnectionProviderLoader::ConnectionProviderLoader(
        Wns::ConnectionProviderLoader **this,
        struct Wns::ConnectionStateMachine *a2)
{
  WpnConnectionProviderSink **v3; // rsi
  LPVOID *v4; // rbx
  int *v5; // r14
  HRESULT Instance; // eax
  LPVOID *v7; // rax
  HRESULT v8; // eax
  int v9; // eax
  int v10; // r14d
  LPVOID v11; // rbx
  int v12; // eax
  int v13; // eax
  struct IConnectionProvider *v14; // rcx
  int ppv; // [rsp+20h] [rbp-39h]
  int ppva; // [rsp+20h] [rbp-39h]
  struct IConnectionProvider *v18; // [rsp+30h] [rbp-29h] BYREF
  Wns::ConnectionProviderLoader *v19; // [rsp+38h] [rbp-21h] BYREF
  LPVOID v20; // [rsp+40h] [rbp-19h] BYREF
  LPVOID v21; // [rsp+48h] [rbp-11h] BYREF
  int v22; // [rsp+50h] [rbp-9h]
  char v23; // [rsp+58h] [rbp-1h]
  __int64 v24; // [rsp+60h] [rbp+7h] BYREF
  int v25; // [rsp+68h] [rbp+Fh]
  IID rclsid; // [rsp+70h] [rbp+17h] BYREF
  DWORD dwClsContext; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v19 = (Wns::ConnectionProviderLoader *)this;
  *this = (Wns::ConnectionProviderLoader *)&Wns::ConnectionProviderLoader::`vftable';
  this[1] = a2;
  v3 = this + 2;
  this[2] = 0;
  v4 = (LPVOID *)(this + 3);
  this[3] = 0;
  this[4] = 0;
  v5 = (int *)(this + 5);
  *((_DWORD *)this + 10) = 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x70,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
    (const char *)0x80070057LL,
    a2 == 0,
    (bool)"Owner object must not be null",
    (const char *)v18);
  Wns::ConnectionProviderConfig::Load(&rclsid);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4);
  Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, v4);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v18 = 0;
  v7 = (LPVOID *)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IConnectionProvider>>(&v18);
  v8 = CoCreateInstance(&rclsid, 0, dwClsContext, &GUID_78f5febc_30ff_450e_a2bf_911ff25df1df, v7);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
      (const char *)(unsigned int)v8,
      ppva);
  v9 = (*(__int64 (__fastcall **)(LPVOID, struct IConnectionProvider *, GUID *, int *))(*(_QWORD *)*v4 + 24LL))(
         *v4,
         v18,
         &GUID_78f5febc_30ff_450e_a2bf_911ff25df1df,
         v5);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
      (const char *)(unsigned int)v9,
      ppva);
  v10 = *v5;
  v11 = *v4;
  v20 = v11;
  if ( v11 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 8LL))(v11);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 8LL))(v11);
  }
  v25 = v10;
  v21 = v11;
  v24 = 0;
  v22 = v10;
  v23 = 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v3);
  v12 = Microsoft::WRL::Details::MakeAndInitialize<WpnConnectionProviderSink,WpnConnectionProviderSink,Wns::ConnectionStateMachine * const &>(
          v3,
          this + 1);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
      (const char *)(unsigned int)v12,
      ppva);
  v13 = WpnConnectionProviderSink::AdviseConnectionProvider(*v3, v18);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionproviderloader.cpp",
      (const char *)(unsigned int)v13,
      ppva);
  v14 = v18;
  v18 = 0;
  v19 = this[4];
  this[4] = v14;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v23 = 0;
  wil::details::ScopeExitFn__lambda_be243681f2be4c14840a019fdeb2ef07___::_ScopeExitFn__lambda_be243681f2be4c14840a019fdeb2ef07___(&v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  return (Wns::ConnectionProviderLoader *)this;
}

```

## disassembly

```asm
0x1800214d0  mov     [rsp-8+arg_8], rbx
0x1800214d5  mov     [rsp-8+arg_10], rsi
0x1800214da  push    rbp
0x1800214db  push    rdi
0x1800214dc  push    r13
0x1800214de  push    r14
0x1800214e0  push    r15
0x1800214e2  lea     rbp, [rsp-37h]
0x1800214e7  sub     rsp, 90h
0x1800214ee  mov     rax, cs:__security_cookie
0x1800214f5  xor     rax, rsp
0x1800214f8  mov     [rbp+57h+var_28], rax
0x1800214fc  mov     rdi, rcx
0x1800214ff  mov     [rbp+57h+var_78], rcx
0x180021503  lea     rax, ??_7ConnectionProviderLoader@Wns@@6B@; const Wns::ConnectionProviderLoader::`vftable'
0x18002150a  mov     [rcx], rax
0x18002150d  mov     [rcx+8], rdx
0x180021511  lea     rsi, [rcx+10h]
0x180021515  mov     qword ptr [rsi], 0
0x18002151c  lea     rbx, [rcx+18h]
0x180021520  mov     qword ptr [rbx], 0
0x180021527  mov     qword ptr [rcx+20h], 0
0x18002152f  lea     r14, [rcx+28h]
0x180021533  mov     dword ptr [r14], 0
0x18002153a  test    rdx, rdx
0x18002153d  setz    al
0x180021540  mov     rcx, [rbp+5Fh]; this
0x180021544  lea     rdx, aOwnerObjectMus; "Owner object must not be null"
0x18002154b  mov     qword ptr [rsp+0B0h+var_88], rdx; bool
0x180021550  mov     byte ptr [rsp+0B0h+ppv], al; char
0x180021554  mov     r9d, 80070057h; char *
0x18002155a  lea     r13, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180021561  mov     r8, r13; unsigned int
0x180021564  mov     edx, 70h ; 'p'; void *
0x180021569  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002156e  lea     rcx, [rbp+57h+rclsid]
0x180021572  call    ?Load@ConnectionProviderConfig@Wns@@SA?AV12@XZ; Wns::ConnectionProviderConfig::Load(void)
0x180021577  mov     rcx, rbx
0x18002157a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002157f  mov     [rsp+0B0h+ppv], rbx; int
0x180021584  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18002158b  xor     edx, edx; pUnkOuter
0x18002158d  lea     r8d, [rdx+1]; dwClsContext
0x180021591  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180021598  call    cs:__imp_CoCreateInstance
0x18002159e  mov     rcx, [rbp+5Fh]; this
0x1800215a2  test    eax, eax
0x1800215a4  jns     short loc_1800215B7
0x1800215a6  mov     r9d, eax; char *
0x1800215a9  mov     r8, r13; unsigned int
0x1800215ac  mov     edx, 78h ; 'x'; void *
0x1800215b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800215b7  mov     [rbp+57h+var_80], 0
0x1800215bf  lea     rcx, [rbp+57h+var_80]
0x1800215c3  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIConnectionProvider@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIConnectionProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IConnectionProvider>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IConnectionProvider>>)
0x1800215c8  mov     [rsp+0B0h+ppv], rax; int
0x1800215cd  lea     r9, _GUID_78f5febc_30ff_450e_a2bf_911ff25df1df; riid
0x1800215d4  mov     r8d, [rbp+57h+dwClsContext]; dwClsContext
0x1800215d8  xor     edx, edx; pUnkOuter
0x1800215da  lea     rcx, [rbp+57h+rclsid]; rclsid
0x1800215de  call    cs:__imp_CoCreateInstance
0x1800215e4  mov     rcx, [rbp+5Fh]; this
0x1800215e8  test    eax, eax
0x1800215ea  jns     short loc_1800215FD
0x1800215ec  mov     r9d, eax; char *
0x1800215ef  mov     r8, r13; unsigned int
0x1800215f2  mov     edx, 80h; void *
0x1800215f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800215fd  mov     rcx, [rbx]
0x180021600  mov     rax, [rcx]
0x180021603  mov     r9, r14
0x180021606  lea     r8, _GUID_78f5febc_30ff_450e_a2bf_911ff25df1df
0x18002160d  mov     rdx, [rbp+57h+var_80]
0x180021611  mov     rax, [rax+18h]
0x180021615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002161a  mov     rcx, [rbp+5Fh]; this
0x18002161e  test    eax, eax
0x180021620  jns     short loc_180021633
0x180021622  mov     r9d, eax; char *
0x180021625  mov     r8, r13; unsigned int
0x180021628  mov     edx, 85h; void *
0x18002162d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180021633  mov     r14d, [r14]
0x180021636  mov     rbx, [rbx]
0x180021639  mov     [rbp+57h+var_70], rbx
0x18002163d  test    rbx, rbx
0x180021640  jz      short loc_180021652
0x180021642  mov     rax, [rbx]
0x180021645  mov     rcx, rbx
0x180021648  mov     rax, [rax+8]
0x18002164c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021651  nop
0x180021652  test    rbx, rbx
0x180021655  jz      short loc_180021667
0x180021657  mov     rax, [rbx]
0x18002165a  mov     rcx, rbx
0x18002165d  mov     rax, [rax+8]
0x180021661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021666  nop
0x180021667  mov     [rbp+57h+var_48], r14d
0x18002166b  mov     [rbp+57h+var_68], rbx
0x18002166f  mov     [rbp+57h+var_50], 0
0x180021677  mov     [rbp+57h+var_60], r14d
0x18002167b  mov     [rbp+57h+var_58], 1
0x18002167f  lea     rcx, [rbp+57h+var_50]
0x180021683  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021688  mov     rcx, rsi
0x18002168b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021690  lea     rdx, [rdi+8]
0x180021694  mov     rcx, rsi
0x180021697  call    ??$MakeAndInitialize@VWpnConnectionProviderSink@@V1@AEBQEAVConnectionStateMachine@Wns@@@Details@WRL@Microsoft@@YAJPEAPEAVWpnConnectionProviderSink@@AEBQEAVConnectionStateMachine@Wns@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WpnConnectionProviderSink,WpnConnectionProviderSink,Wns::ConnectionStateMachine * const &>(WpnConnectionProviderSink * *,Wns::ConnectionStateMachine * const &)
0x18002169c  mov     rcx, [rbp+5Fh]; this
0x1800216a0  test    eax, eax
0x1800216a2  jns     short loc_1800216B5
0x1800216a4  mov     r9d, eax; char *
0x1800216a7  mov     r8, r13; unsigned int
0x1800216aa  mov     edx, 8Dh; void *
0x1800216af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800216b5  mov     rdx, [rbp+57h+var_80]; struct IConnectionProvider *
0x1800216b9  mov     rcx, [rsi]; this
0x1800216bc  call    ?AdviseConnectionProvider@WpnConnectionProviderSink@@QEAAJPEAUIConnectionProvider@@@Z; WpnConnectionProviderSink::AdviseConnectionProvider(IConnectionProvider *)
0x1800216c1  mov     rcx, [rbp+5Fh]; this
0x1800216c5  test    eax, eax
0x1800216c7  jns     short loc_1800216DA
0x1800216c9  mov     r9d, eax; char *
0x1800216cc  mov     r8, r13; unsigned int
0x1800216cf  mov     edx, 8Fh; void *
0x1800216d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800216da  mov     rcx, [rbp+57h+var_80]
0x1800216de  mov     [rbp+57h+var_80], 0
0x1800216e6  mov     rax, [rdi+20h]
0x1800216ea  mov     [rbp+57h+var_78], rax
0x1800216ee  mov     [rdi+20h], rcx
0x1800216f2  lea     rcx, [rbp+57h+var_78]
0x1800216f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800216fb  mov     [rbp+57h+var_58], 0
0x1800216ff  lea     rcx, [rbp+57h+var_68]
0x180021703  call    wil__details__ScopeExitFn__lambda_be243681f2be4c14840a019fdeb2ef07______ScopeExitFn__lambda_be243681f2be4c14840a019fdeb2ef07___
0x180021708  nop
0x180021709  lea     rcx, [rbp+57h+var_70]
0x18002170d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021712  nop
0x180021713  lea     rcx, [rbp+57h+var_80]
0x180021717  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002171c  nop
0x18002171d  mov     rax, rdi
0x180021720  mov     rcx, [rbp+57h+var_28]
0x180021724  xor     rcx, rsp; StackCookie
0x180021727  call    __security_check_cookie
0x18002172c  lea     r11, [rsp+0B0h+var_20]
0x180021734  mov     rbx, [r11+38h]
0x180021738  mov     rsi, [r11+40h]
0x18002173c  mov     rsp, r11
0x18002173f  pop     r15
0x180021741  pop     r14
0x180021743  pop     r13
0x180021745  pop     rdi
0x180021746  pop     rbp
0x180021747  retn
```
