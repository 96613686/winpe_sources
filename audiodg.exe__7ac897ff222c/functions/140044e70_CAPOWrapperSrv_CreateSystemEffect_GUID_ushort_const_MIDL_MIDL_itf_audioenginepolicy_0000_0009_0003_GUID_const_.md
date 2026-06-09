# CAPOWrapperSrv::CreateSystemEffect(_GUID,ushort const *,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,_GUID const &,IAudioProcessingObject * *)

- ea: `0x140044e70`
- end: `0x1400453b1`
- name: `?CreateSystemEffect@CAPOWrapperSrv@@UEAAJU_GUID@@PEBGW4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@AEBU2@PEAPEAUIAudioProcessingObject@@@Z`
- size: `1345`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140006e30`
- `0x140008124`
- `0x14000c33c`
- `0x14000e11c`
- `0x14000e200`
- `0x14000e280`
- `0x14000e404`
- `0x140019a00`
- `0x140044e70`
- `0x1400453b8`
- `0x140045658`
- `0x140045f08`
- `0x14005d0e0`
- `0x1400b5010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x140044edf`
- `ntdll!EtwEventActivityIdControl` at `0x14004537e`
- `ntdll!EtwEventActivityIdControl` at `0x140044edf`
- `ntdll!EtwEventActivityIdControl` at `0x14004537e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004502e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045363`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004502e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140045363`

## string_xrefs

- `0x140044fa6`: `SrvSystemEffect_Create`
- `0x1400450ef`: `APO CLSID {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAPOWrapperSrv::CreateSystemEffect(
        __int64 a1,
        __int128 *a2,
        unsigned __int16 *a3,
        int a4,
        struct _GUID *a5,
        __int64 *a6)
{
  int ApoDeviceId; // r15d
  const struct _tlgProvider_t *v9; // rax
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v11; // rdx
  void *v12; // rcx
  void *v13; // rcx
  unsigned __int16 *v14; // rbx
  int v15; // eax
  struct IUnknown *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  int APOProcessingHostInstance; // eax
  int v23; // eax
  void *v24; // rcx
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  char *v29; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+30h] [rbp-D0h]
  __int64 v31; // [rsp+38h] [rbp-C8h]
  __int64 v32; // [rsp+40h] [rbp-C0h]
  __int64 v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  __int64 v35; // [rsp+58h] [rbp-A8h]
  __int64 v36; // [rsp+60h] [rbp-A0h]
  __int64 v37; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v39; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v40; // [rsp+90h] [rbp-70h] BYREF
  __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  int v42; // [rsp+A0h] [rbp-60h]
  LPVOID *p_pv; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v44; // [rsp+B0h] [rbp-50h] BYREF
  char v45; // [rsp+B8h] [rbp-48h]
  __int64 *v46; // [rsp+C0h] [rbp-40h]
  __int128 v47; // [rsp+C8h] [rbp-38h]
  _QWORD v48[3]; // [rsp+D8h] [rbp-28h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v42 = a4;
  v40 = a3;
  v46 = a6;
  v47 = *a2;
  v48[0] = *(_QWORD *)a2;
  v48[1] = *((_QWORD *)a2 + 1);
  EtwEventActivityIdControl(4, v48);
  *a6 = 0;
  if ( !a4 )
  {
    ApoDeviceId = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
      (const char *)0x80070057LL,
      v26);
    goto LABEL_47;
  }
  StringCchPrintfA(
    (char *)(a1 + 140),
    0x27u,
    "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    a5->Data1,
    a5->Data2,
    a5->Data3,
    a5->Data4[0],
    a5->Data4[1],
    a5->Data4[2],
    a5->Data4[3],
    a5->Data4[4],
    a5->Data4[5],
    a5->Data4[6],
    a5->Data4[7]);
  v9 = AudioDgTelemetryProvider::Provider();
  CPerfTracker::CPerfTracker(&PerformanceCount, v9, "SrvSystemEffect_Create", (const char *const)(a1 + 140));
  pv = 0;
  p_pv = &pv;
  v44 = 0;
  v45 = 1;
  v10 = v40;
  ApoDeviceId = TryGetApoDeviceId(a5, v40, &v44);
  if ( v45 )
  {
    v12 = *p_pv;
    v11 = v44;
    *p_pv = v44;
    if ( v12 )
      CoTaskMemFree(v12);
  }
  if ( ApoDeviceId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
      (const char *)(unsigned int)ApoDeviceId,
      v27);
LABEL_8:
    v13 = pv;
    pv = 0;
LABEL_9:
    if ( v13 )
      CoTaskMemFree(v13);
    CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
    goto LABEL_47;
  }
  v40 = 0;
  ApoDeviceId = CSystemEffectWrapper::Create(
                  (__int64)a5,
                  (__int64)v11,
                  (__int64)v10,
                  v42,
                  0,
                  (__int64)pv,
                  (__int64)&v40);
  if ( ApoDeviceId < 0 )
  {
    LODWORD(v37) = a5->Data4[5];
    LODWORD(v36) = a5->Data4[4];
    LODWORD(v35) = a5->Data4[3];
    LODWORD(v34) = a5->Data4[2];
    LODWORD(v33) = a5->Data4[1];
    LODWORD(v32) = a5->Data4[0];
    LODWORD(v31) = a5->Data3;
    LODWORD(v30) = a5->Data2;
    LODWORD(v29) = a5->Data1;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x6A,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
      (const char *)(unsigned int)ApoDeviceId,
      (int)"APO CLSID {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
      v29,
      v30,
      v31,
      v32,
      v33,
      v34,
      v35,
      v36,
      v37,
      a5->Data4[6],
      a5->Data4[7]);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    v13 = pv;
    pv = 0;
    goto LABEL_9;
  }
  v39 = 0;
  v14 = v40;
  v15 = (**(__int64 (__fastcall ***)(unsigned __int16 *, GUID *, struct IUnknown **))v40)(
          v40,
          &GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10,
          &v39);
  ApoDeviceId = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
      (const char *)(unsigned int)v15,
      v28);
    if ( v39 )
      ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v14 + 16LL))(v14);
    goto LABEL_8;
  }
  v16 = v39;
  v17 = 0;
  v41 = 0;
  if ( v39 )
  {
    ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v39->lpVtbl->QueryInterface)(
      v39,
      &GUID_5fa00f27_add6_499a_8a9d_6b98521fa75b,
      &v41);
    v16 = v39;
    v17 = v41;
  }
  if ( !v17 )
  {
    ApoDeviceId = -2147467262;
    v18 = 2147500034LL;
    v19 = 112;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
      (const char *)v18,
      v28);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
    goto LABEL_8;
  }
  if ( *(struct IUnknown **)(a1 + 96) != v16 )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 96), v16);
  v20 = (a1 + 8) & -(__int64)(a1 != 0);
  *v46 = v20;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64))v39->lpVtbl->QueryInterface)(
         v39,
         &GUID_c58b31cd_fc6a_4255_bc1f_ad29bb0a4a17,
         a1 + 112) >= 0 )
  {
    v21 = *(_QWORD *)(a1 + 88);
    *(_QWORD *)(a1 + 88) = 0;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    APOProcessingHostInstance = GetAPOProcessingHostInstance((struct IAPOProcessingHost **)(a1 + 88));
    ApoDeviceId = APOProcessingHostInstance;
    if ( APOProcessingHostInstance < 0 )
    {
      v18 = (unsigned int)APOProcessingHostInstance;
      v19 = 120;
      goto LABEL_22;
    }
    v23 = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *))(**(_QWORD **)(a1 + 88) + 24LL))(
            *(_QWORD *)(a1 + 88),
            v39);
    ApoDeviceId = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apowrappersrv.cpp",
        (const char *)(unsigned int)v23,
        v28);
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      if ( v39 )
        ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
      if ( v14 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v14 + 16LL))(v14);
      goto LABEL_8;
    }
  }
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v39 )
    ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
  if ( v14 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v14 + 16LL))(v14);
  v24 = pv;
  pv = 0;
  if ( v24 )
    CoTaskMemFree(v24);
  CPerfTracker::~CPerfTracker((CPerfTracker *)&PerformanceCount);
  ApoDeviceId = 0;
LABEL_47:
  EtwEventActivityIdControl(4, v48);
  return (unsigned int)ApoDeviceId;
}

```

## disassembly

```asm
0x140044e70  mov     [rsp-8+arg_8], rbx
0x140044e75  push    rbp
0x140044e76  push    rsi
0x140044e77  push    rdi
0x140044e78  push    r12
0x140044e7a  push    r13
0x140044e7c  push    r14
0x140044e7e  push    r15
0x140044e80  lea     rbp, [rsp-0F0h]
0x140044e88  sub     rsp, 1F0h
0x140044e8f  mov     rax, cs:__security_cookie
0x140044e96  xor     rax, rsp
0x140044e99  mov     [rbp+120h+var_40], rax
0x140044ea0  mov     ebx, r9d
0x140044ea3  mov     [rbp+120h+var_180], ebx
0x140044ea6  mov     [rbp+120h+var_190], r8
0x140044eaa  mov     r13, rcx
0x140044ead  mov     r12, [rbp+120h+arg_20]
0x140044eb4  mov     rdi, [rbp+120h+arg_28]
0x140044ebb  mov     [rbp+120h+var_160], rdi
0x140044ebf  movups  xmm0, xmmword ptr [rdx]
0x140044ec2  movdqu  [rbp+120h+var_158], xmm0
0x140044ec7  mov     rax, [rdx]
0x140044eca  mov     [rbp+120h+var_148], rax
0x140044ece  mov     rax, [rdx+8]
0x140044ed2  mov     [rbp+120h+var_140], rax
0x140044ed6  lea     rdx, [rbp+120h+var_148]
0x140044eda  mov     ecx, 4
0x140044edf  call    cs:__imp_EtwEventActivityIdControl
0x140044ee5  mov     qword ptr [rdi], 0
0x140044eec  test    ebx, ebx
0x140044eee  jnz     short loc_140044F14
0x140044ef0  mov     rcx, [rbp+128h]; this
0x140044ef7  mov     r15d, 80070057h
0x140044efd  mov     r9d, r15d; char *
0x140044f00  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140044f07  lea     edx, [rbx+5Dh]; void *
0x140044f0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140044f0f  jmp     loc_140045375
0x140044f14  lea     r15, [r13+8Ch]
0x140044f1b  movzx   eax, byte ptr [r12+0Fh]
0x140044f21  movzx   ecx, byte ptr [r12+0Eh]
0x140044f27  movzx   edx, byte ptr [r12+0Dh]
0x140044f2d  movzx   r8d, byte ptr [r12+0Ch]
0x140044f33  movzx   r10d, byte ptr [r12+0Bh]
0x140044f39  movzx   r11d, byte ptr [r12+0Ah]
0x140044f3f  movzx   ebx, byte ptr [r12+9]
0x140044f45  movzx   edi, byte ptr [r12+8]
0x140044f4b  movzx   esi, word ptr [r12+6]
0x140044f51  movzx   r14d, word ptr [r12+4]
0x140044f57  mov     dword ptr [rsp+220h+var_1B8], eax
0x140044f5b  mov     dword ptr [rsp+220h+var_1C0], ecx
0x140044f5f  mov     dword ptr [rsp+220h+var_1C8], edx
0x140044f63  mov     dword ptr [rsp+220h+var_1D0], r8d
0x140044f68  mov     dword ptr [rsp+220h+var_1D8], r10d
0x140044f6d  mov     dword ptr [rsp+220h+var_1E0], r11d
0x140044f72  mov     dword ptr [rsp+220h+var_1E8], ebx
0x140044f76  mov     dword ptr [rsp+220h+var_1F0], edi
0x140044f7a  mov     dword ptr [rsp+220h+var_1F8], esi
0x140044f7e  mov     [rsp+220h+var_200], r14d; int
0x140044f83  mov     r9d, [r12]
0x140044f87  lea     r8, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x140044f8e  mov     edx, 27h ; '''; unsigned __int64
0x140044f93  mov     rcx, r15; char *
0x140044f96  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x140044f9b  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x140044fa0  mov     rdx, rax; struct _tlgProvider_t *
0x140044fa3  mov     r9, r15; char *
0x140044fa6  lea     r8, aSrvsystemeffec_4; "SrvSystemEffect_Create"
0x140044fad  lea     rcx, [rbp+120h+PerformanceCount]; lpPerformanceCount
0x140044fb1  call    ??0CPerfTracker@@QEAA@PEBU_tlgProvider_t@@QEBD1@Z; CPerfTracker::CPerfTracker(_tlgProvider_t const *,char const * const,char const * const)
0x140044fb6  xor     esi, esi
0x140044fb8  mov     [rbp+120h+pv], rsi
0x140044fbc  lea     rax, [rbp+120h+pv]
0x140044fc0  mov     [rbp+120h+var_178], rax
0x140044fc4  mov     [rbp+120h+var_170], rsi
0x140044fc8  mov     [rbp+120h+var_168], 1
0x140044fcc  lea     r8, [rbp+120h+var_170]; unsigned __int16 **
0x140044fd0  mov     rbx, [rbp+120h+var_190]
0x140044fd4  mov     rdx, rbx; unsigned __int16 *
0x140044fd7  mov     rcx, r12; struct _GUID *
0x140044fda  call    ?TryGetApoDeviceId@@YAJAEBU_GUID@@PEBGPEAPEAG@Z; TryGetApoDeviceId(_GUID const &,ushort const *,ushort * *)
0x140044fdf  mov     r15d, eax
0x140044fe2  cmp     [rbp+120h+var_168], sil
0x140044fe6  jz      short loc_140045001
0x140044fe8  mov     r8, [rbp+120h+var_178]
0x140044fec  mov     rcx, [r8]; pv
0x140044fef  mov     rdx, [rbp+120h+var_170]
0x140044ff3  mov     [r8], rdx
0x140044ff6  test    rcx, rcx
0x140044ff9  jz      short loc_140045001
0x140044ffb  call    cs:__imp_CoTaskMemFree
0x140045001  test    r15d, r15d
0x140045004  jns     short loc_140045042
0x140045006  mov     rcx, [rbp+128h]; this
0x14004500d  mov     r9d, r15d; char *
0x140045010  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045017  mov     edx, 63h ; 'c'; void *
0x14004501c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140045021  mov     rcx, [rbp+120h+pv]; pv
0x140045025  mov     [rbp+120h+pv], rsi
0x140045029  test    rcx, rcx
0x14004502c  jz      short loc_140045034
0x14004502e  call    cs:__imp_CoTaskMemFree
0x140045034  lea     rcx, [rbp+120h+PerformanceCount]; this
0x140045038  call    ??1CPerfTracker@@QEAA@XZ; CPerfTracker::~CPerfTracker(void)
0x14004503d  jmp     loc_140045375
0x140045042  mov     [rbp+120h+var_190], rsi
0x140045046  mov     rax, [rbp+120h+pv]
0x14004504a  lea     rcx, [rbp+120h+var_190]
0x14004504e  mov     [rsp+220h+var_1F0], rcx
0x140045053  mov     [rsp+220h+var_1F8], rax
0x140045058  mov     qword ptr [rsp+220h+var_200], rsi; int
0x14004505d  mov     r9d, [rbp+120h+var_180]
0x140045061  mov     r8, rbx
0x140045064  mov     rcx, r12
0x140045067  call    ?Create@CSystemEffectWrapper@@SAJAEBU_GUID@@PEAUIMMDevice@@PEBGW4__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003@@PEAUIUnknown@@2PEAPEAU5@@Z; CSystemEffectWrapper::Create(_GUID const &,IMMDevice *,ushort const *,__MIDL___MIDL_itf_audioenginepolicy_0000_0009_0003,IUnknown *,ushort const *,IUnknown * *)
0x14004506c  mov     r15d, eax
0x14004506f  test    eax, eax
0x140045071  jns     loc_140045129
0x140045077  movzx   eax, byte ptr [r12+0Fh]
0x14004507d  movzx   edx, byte ptr [r12+0Eh]
0x140045083  movzx   r8d, byte ptr [r12+0Dh]
0x140045089  movzx   r9d, byte ptr [r12+0Ch]
0x14004508f  movzx   r10d, byte ptr [r12+0Bh]
0x140045095  movzx   r11d, byte ptr [r12+0Ah]
0x14004509b  movzx   ebx, byte ptr [r12+9]
0x1400450a1  movzx   edi, byte ptr [r12+8]
0x1400450a7  movzx   esi, word ptr [r12+6]
0x1400450ad  movzx   r14d, word ptr [r12+4]
0x1400450b3  mov     rcx, [rbp+128h]; this
0x1400450ba  mov     [rsp+220h+var_1A8], eax
0x1400450be  mov     [rsp+220h+var_1B0], edx
0x1400450c2  mov     dword ptr [rsp+220h+var_1B8], r8d
0x1400450c7  mov     dword ptr [rsp+220h+var_1C0], r9d
0x1400450cc  mov     dword ptr [rsp+220h+var_1C8], r10d
0x1400450d1  mov     dword ptr [rsp+220h+var_1D0], r11d
0x1400450d6  mov     dword ptr [rsp+220h+var_1D8], ebx
0x1400450da  mov     dword ptr [rsp+220h+var_1E0], edi
0x1400450de  mov     dword ptr [rsp+220h+var_1E8], esi
0x1400450e2  mov     dword ptr [rsp+220h+var_1F0], r14d
0x1400450e7  mov     eax, [r12]
0x1400450eb  mov     dword ptr [rsp+220h+var_1F8], eax; char *
0x1400450ef  lea     rax, aApoClsid08x04x; "APO CLSID {%08x-%04x-%04x-%02x%02x-%02x"...
0x1400450f6  mov     qword ptr [rsp+220h+var_200], rax; int
0x1400450fb  mov     r9d, r15d; char *
0x1400450fe  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045105  mov     edx, 6Ah ; 'j'; void *
0x14004510a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14004510f  lea     rcx, [rbp+120h+var_190]
0x140045113  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140045118  mov     rcx, [rbp+120h+pv]
0x14004511c  mov     [rbp+120h+pv], 0
0x140045124  jmp     loc_140045029
0x140045129  mov     [rbp+120h+var_198], rsi
0x14004512d  mov     rbx, [rbp+120h+var_190]
0x140045131  mov     rax, [rbx]
0x140045134  lea     r8, [rbp+120h+var_198]
0x140045138  lea     rdx, _GUID_fd7f2b29_24d0_4b5c_b177_592c39f9ca10
0x14004513f  mov     rcx, rbx
0x140045142  mov     rax, [rax]
0x140045145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004514a  mov     r15d, eax
0x14004514d  test    eax, eax
0x14004514f  jns     short loc_140045198
0x140045151  mov     rcx, [rbp+128h]; this
0x140045158  mov     r9d, eax; char *
0x14004515b  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140045162  mov     edx, 6Dh ; 'm'; void *
0x140045167  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004516c  nop
0x14004516d  mov     rcx, [rbp+120h+var_198]
0x140045171  test    rcx, rcx
0x140045174  jz      short loc_140045183
0x140045176  mov     rax, [rcx]
0x140045179  mov     rax, [rax+10h]
0x14004517d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045182  nop
0x140045183  mov     rax, [rbx]
0x140045186  mov     rcx, rbx
0x140045189  mov     rax, [rax+10h]
0x14004518d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045192  nop
0x140045193  jmp     loc_140045021
0x140045198  mov     rcx, [rbp+120h+var_198]
0x14004519c  mov     rax, rsi
0x14004519f  mov     [rbp+120h+var_188], rax
0x1400451a3  test    rcx, rcx
0x1400451a6  jz      short loc_1400451C6
0x1400451a8  mov     rax, [rcx]
0x1400451ab  lea     r8, [rbp+120h+var_188]
0x1400451af  lea     rdx, _GUID_5fa00f27_add6_499a_8a9d_6b98521fa75b
0x1400451b6  mov     rax, [rax]
0x1400451b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400451be  mov     rcx, [rbp+120h+var_198]
0x1400451c2  mov     rax, [rbp+120h+var_188]
0x1400451c6  test    rax, rax
0x1400451c9  jnz     short loc_14004520A
0x1400451cb  mov     r15d, 80004002h
0x1400451d1  mov     r9d, r15d; char *
0x1400451d4  lea     edx, [rax+70h]; void *
0x1400451d7  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400451de  mov     rcx, [rbp+128h]; this
0x1400451e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400451ea  lea     rcx, [rbp+120h+var_188]
0x1400451ee  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400451f3  lea     rcx, [rbp+120h+var_198]
0x1400451f7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400451fc  lea     rcx, [rbp+120h+var_190]
0x140045200  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140045205  jmp     loc_140045021
0x14004520a  cmp     [r13+60h], rcx
0x14004520e  jz      short loc_14004521C
0x140045210  mov     rdx, rcx; struct IUnknown *
0x140045213  lea     rcx, [r13+60h]; struct IUnknown **
0x140045217  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x14004521c  mov     rax, r13
0x14004521f  lea     rdx, [r13+8]
0x140045223  neg     rax
0x140045226  sbb     rcx, rcx
0x140045229  and     rcx, rdx
0x14004522c  mov     rax, [rbp+120h+var_160]
0x140045230  mov     [rax], rcx
0x140045233  mov     rax, [rcx]
0x140045236  mov     rax, [rax+8]
0x14004523a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004523f  mov     rcx, [rbp+120h+var_198]
0x140045243  mov     rax, [rcx]
0x140045246  lea     r8, [r13+70h]
0x14004524a  lea     rdx, _GUID_c58b31cd_fc6a_4255_bc1f_ad29bb0a4a17
0x140045251  mov     rax, [rax]
0x140045254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045259  test    eax, eax
0x14004525b  js      loc_140045315
0x140045261  lea     rdi, [r13+58h]
0x140045265  mov     rcx, [rdi]
0x140045268  mov     [rdi], rsi
0x14004526b  test    rcx, rcx
0x14004526e  jz      short loc_14004527D
0x140045270  mov     rax, [rcx]
0x140045273  mov     rax, [rax+10h]
0x140045277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004527c  nop
0x14004527d  mov     rcx, rdi; struct IAPOProcessingHost **
0x140045280  call    ?GetAPOProcessingHostInstance@@YAJPEAPEAUIAPOProcessingHost@@@Z; GetAPOProcessingHostInstance(IAPOProcessingHost * *)
0x140045285  mov     r15d, eax
0x140045288  test    eax, eax
0x14004528a  jns     short loc_140045299
0x14004528c  mov     r9d, eax
0x14004528f  mov     edx, 78h ; 'x'
0x140045294  jmp     loc_1400451D7
0x140045299  mov     rcx, [rdi]
0x14004529c  mov     rax, [rcx]
0x14004529f  mov     rdx, [rbp+120h+var_198]
0x1400452a3  mov     rax, [rax+18h]
0x1400452a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400452ac  mov     r15d, eax
0x1400452af  test    eax, eax
0x1400452b1  jns     short loc_140045315
0x1400452b3  mov     rcx, [rbp+128h]; this
0x1400452ba  mov     r9d, eax; char *
0x1400452bd  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400452c4  mov     edx, 7Ah ; 'z'; void *
0x1400452c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400452ce  nop
0x1400452cf  mov     rcx, [rbp+120h+var_188]
0x1400452d3  test    rcx, rcx
0x1400452d6  jz      short loc_1400452E5
0x1400452d8  mov     rax, [rcx]
0x1400452db  mov     rax, [rax+10h]
0x1400452df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400452e4  nop
0x1400452e5  mov     rcx, [rbp+120h+var_198]
0x1400452e9  test    rcx, rcx
0x1400452ec  jz      short loc_1400452FB
0x1400452ee  mov     rax, [rcx]
0x1400452f1  mov     rax, [rax+10h]
0x1400452f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400452fa  nop
0x1400452fb  test    rbx, rbx
0x1400452fe  jz      short loc_140045310
0x140045300  mov     rax, [rbx]
0x140045303  mov     rcx, rbx
0x140045306  mov     rax, [rax+10h]
0x14004530a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004530f  nop
0x140045310  jmp     loc_140045021
0x140045315  mov     rcx, [rbp+120h+var_188]
0x140045319  test    rcx, rcx
0x14004531c  jz      short loc_14004532B
0x14004531e  mov     rax, [rcx]
0x140045321  mov     rax, [rax+10h]
0x140045325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004532a  nop
0x14004532b  mov     rcx, [rbp+120h+var_198]
0x14004532f  test    rcx, rcx
0x140045332  jz      short loc_140045341
0x140045334  mov     rax, [rcx]
0x140045337  mov     rax, [rax+10h]
0x14004533b  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
