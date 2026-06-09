# MediaFrameHelpers::XVPConvertMFMediaBuffer(IMFMediaBuffer *,IMFMediaType *,tagRECT const &,IMFMediaBuffer *,IMFMediaType *,tagRECT const &,IMFDXGIDeviceManager *)

- ea: `0x180005940`
- end: `0x180005cc8`
- name: `?XVPConvertMFMediaBuffer@MediaFrameHelpers@@SAXPEAUIMFMediaBuffer@@PEAUIMFMediaType@@AEBUtagRECT@@012PEAUIMFDXGIDeviceManager@@@Z`
- size: `904`
- prototype: `void __fastcall(struct IMFMediaBuffer *, struct IMFMediaType *, const struct tagRECT *, struct IMFMediaBuffer *, struct IMFMediaType *, const struct tagRECT *, struct IMFDXGIDeviceManager *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002940`
- `0x180004300`

## callees

- `0x1800019c0`
- `0x180005940`
- `0x180005cd0`
- `0x180019884`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005a3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005a3d`
- `MFPlat!MFCreateSample` at `0x180005975`
- `MFPlat!MFCreateSample` at `0x1800059cc`
- `MFPlat!MFCreateSample` at `0x180005975`
- `MFPlat!MFCreateSample` at `0x1800059cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall MediaFrameHelpers::XVPConvertMFMediaBuffer(
        struct IMFMediaBuffer *a1,
        struct IMFMediaType *a2,
        const struct tagRECT *a3,
        struct IMFMediaBuffer *a4,
        struct IMFMediaType *a5,
        const struct tagRECT *a6,
        struct IMFDXGIDeviceManager *a7)
{
  unsigned int v11; // eax
  int v12; // edx
  unsigned int v13; // eax
  int v14; // edx
  unsigned int v15; // eax
  int v16; // edx
  unsigned int v17; // eax
  int v18; // edx
  unsigned int v19; // eax
  int v20; // edx
  unsigned int v21; // eax
  int v22; // edx
  unsigned int v23; // eax
  int v24; // edx
  LPVOID v25; // rdi
  __int64 (__fastcall *v26)(LPVOID, __int64 *); // rbx
  unsigned int v27; // eax
  int v28; // edx
  unsigned int v29; // eax
  int v30; // edx
  unsigned int v31; // eax
  int v32; // edx
  unsigned int v33; // eax
  int v34; // edx
  unsigned int v35; // eax
  int v36; // edx
  unsigned int v37; // eax
  int v38; // edx
  unsigned int v39; // eax
  int v40; // edx
  IMFSample *v41; // rax
  unsigned int v42; // eax
  int v43; // edx
  unsigned int v44; // eax
  int v45; // edx
  unsigned int v46; // eax
  int v47; // edx
  unsigned int v48; // eax
  int v49; // edx
  __int64 v50; // rcx
  __int64 v51; // rcx
  LPVOID v52; // rcx
  IMFSample *v53; // rcx
  IMFSample *v54; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-51h] BYREF
  IMFSample *v56; // [rsp+38h] [rbp-49h] BYREF
  IMFSample *ppIMFSample; // [rsp+40h] [rbp-41h] BYREF
  __int64 v58; // [rsp+48h] [rbp-39h] BYREF
  __int64 v59; // [rsp+50h] [rbp-31h] BYREF
  char v60; // [rsp+58h] [rbp-29h]
  __int64 *v61; // [rsp+60h] [rbp-21h]
  __int64 v62; // [rsp+68h] [rbp-19h] BYREF
  IMFSample *v63; // [rsp+70h] [rbp-11h]
  __int64 v64; // [rsp+78h] [rbp-9h]
  __int64 v65; // [rsp+80h] [rbp-1h]

  ppIMFSample = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppIMFSample);
  v11 = MFCreateSample(&ppIMFSample);
  MF::ThrowIfFailed((MF *)v11, v12);
  v13 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, a1);
  MF::ThrowIfFailed((MF *)v13, v14);
  v15 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, 0);
  MF::ThrowIfFailed((MF *)v15, v16);
  v56 = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v56);
  v17 = MFCreateSample(&v56);
  MF::ThrowIfFailed((MF *)v17, v18);
  v19 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))v56->lpVtbl->AddBuffer)(v56, a4);
  MF::ThrowIfFailed((MF *)v19, v20);
  v21 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))v56->lpVtbl->SetSampleTime)(v56, 0);
  MF::ThrowIfFailed((MF *)v21, v22);
  ppv = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppv);
  v23 = CoCreateInstance(&CLSID_VideoProcessorMFT, 0, 1u, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &ppv);
  MF::ThrowIfFailed((MF *)v23, v24);
  v58 = 0;
  v25 = ppv;
  v26 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 64LL);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v58);
  v27 = v26(v25, &v58);
  MF::ThrowIfFailed((MF *)v27, v28);
  v29 = (*(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)v58 + 168LL))(v58, &MF_XVP_DISABLE_FRC, 1);
  MF::ThrowIfFailed((MF *)v29, v30);
  v31 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v58 + 168LL))(
          v58,
          MF_XVP_CALLER_ALLOCATES_OUTPUT,
          1);
  MF::ThrowIfFailed((MF *)v31, v32);
  v33 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)ppv + 120LL))(
          ppv,
          0,
          a2,
          0);
  MF::ThrowIfFailed((MF *)v33, v34);
  v35 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)ppv + 128LL))(
          ppv,
          0,
          a5,
          0);
  MF::ThrowIfFailed((MF *)v35, v36);
  MF::As<IMFVideoProcessorControl,IMFTransform>(&v59, &ppv);
  v37 = (*(__int64 (__fastcall **)(__int64, const struct tagRECT *))(*(_QWORD *)v59 + 32LL))(v59, a3);
  MF::ThrowIfFailed((MF *)v37, v38);
  v39 = (*(__int64 (__fastcall **)(__int64, const struct tagRECT *))(*(_QWORD *)v59 + 40LL))(v59, a6);
  MF::ThrowIfFailed((MF *)v39, v40);
  LODWORD(a7) = 0;
  v62 = 0;
  v64 = 0;
  v65 = 0;
  v41 = v56;
  v56 = 0;
  v63 = v41;
  v60 = 0;
  v61 = &v62;
  v42 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 184LL))(ppv, 2, 0);
  MF::ThrowIfFailed((MF *)v42, v43);
  v44 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 184LL))(ppv, 0, 0);
  MF::ThrowIfFailed((MF *)v44, v45);
  v46 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, IMFSample *, _QWORD))(*(_QWORD *)ppv + 192LL))(
          ppv,
          0,
          ppIMFSample,
          0);
  MF::ThrowIfFailed((MF *)v46, v47);
  v48 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64 *, struct IMFDXGIDeviceManager **))(*(_QWORD *)ppv + 200LL))(
          ppv,
          0,
          1,
          &v62,
          &a7);
  MF::ThrowIfFailed((MF *)v48, v49);
  if ( v63 )
  {
    ((void (__fastcall *)(IMFSample *))v63->lpVtbl->Release)(v63);
    v63 = 0;
  }
  if ( v65 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    v65 = 0;
  }
  v50 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
  }
  v51 = v58;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  v52 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
  }
  v53 = v56;
  if ( v56 )
  {
    v56 = 0;
    ((void (__fastcall *)(IMFSample *))v53->lpVtbl->Release)(v53);
  }
  v54 = ppIMFSample;
  if ( ppIMFSample )
  {
    ppIMFSample = 0;
    ((void (__fastcall *)(IMFSample *))v54->lpVtbl->Release)(v54);
  }
}

```

## disassembly

```asm
0x180005940  push    rbp
0x180005942  push    rbx
0x180005943  push    rsi
0x180005944  push    rdi
0x180005945  push    r12
0x180005947  push    r14
0x180005949  lea     rbp, [rsp-17h]
0x18000594e  sub     rsp, 98h
0x180005955  mov     rdi, r9
0x180005958  mov     r14, r8
0x18000595b  mov     rsi, rdx
0x18000595e  mov     rbx, rcx
0x180005961  xor     r12d, r12d
0x180005964  mov     [rbp+3Fh+ppIMFSample], r12
0x180005968  lea     rcx, [rbp+3Fh+ppIMFSample]
0x18000596c  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180005971  lea     rcx, [rbp+3Fh+ppIMFSample]; ppIMFSample
0x180005975  call    cs:__imp_MFCreateSample
0x18000597b  mov     ecx, eax; this
0x18000597d  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005982  mov     rcx, [rbp+3Fh+ppIMFSample]
0x180005986  mov     rax, [rcx]
0x180005989  mov     rdx, rbx
0x18000598c  mov     rax, [rax+150h]
0x180005993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005998  mov     ecx, eax; this
0x18000599a  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x18000599f  mov     rcx, [rbp+3Fh+ppIMFSample]
0x1800059a3  mov     rax, [rcx]
0x1800059a6  xor     edx, edx
0x1800059a8  mov     rax, [rax+120h]
0x1800059af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b4  mov     ecx, eax; this
0x1800059b6  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800059bb  mov     [rbp+3Fh+var_88], r12
0x1800059bf  lea     rcx, [rbp+3Fh+var_88]
0x1800059c3  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800059c8  lea     rcx, [rbp+3Fh+var_88]; ppIMFSample
0x1800059cc  call    cs:__imp_MFCreateSample
0x1800059d2  mov     ecx, eax; this
0x1800059d4  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800059d9  mov     rcx, [rbp+3Fh+var_88]
0x1800059dd  mov     rax, [rcx]
0x1800059e0  mov     rdx, rdi
0x1800059e3  mov     rax, [rax+150h]
0x1800059ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ef  mov     ecx, eax; this
0x1800059f1  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x1800059f6  mov     rcx, [rbp+3Fh+var_88]
0x1800059fa  mov     rax, [rcx]
0x1800059fd  xor     edx, edx
0x1800059ff  mov     rax, [rax+120h]
0x180005a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a0b  mov     ecx, eax; this
0x180005a0d  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005a12  mov     [rbp+3Fh+var_90], r12
0x180005a16  lea     rcx, [rbp+3Fh+var_90]
0x180005a1a  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180005a1f  lea     rax, [rbp+3Fh+var_90]
0x180005a23  mov     [rsp+0C0h+ppv], rax; ppv
0x180005a28  lea     r9, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d; riid
0x180005a2f  xor     edx, edx; pUnkOuter
0x180005a31  lea     r8d, [r12+1]; dwClsContext
0x180005a36  lea     rcx, CLSID_VideoProcessorMFT; rclsid
0x180005a3d  call    cs:__imp_CoCreateInstance
0x180005a43  mov     ecx, eax; this
0x180005a45  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005a4a  mov     [rbp+3Fh+var_78], r12
0x180005a4e  mov     rdi, [rbp+3Fh+var_90]
0x180005a52  mov     rax, [rdi]
0x180005a55  mov     rbx, [rax+40h]
0x180005a59  lea     rcx, [rbp+3Fh+var_78]
0x180005a5d  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x180005a62  lea     rdx, [rbp+3Fh+var_78]
0x180005a66  mov     rcx, rdi
0x180005a69  mov     rax, rbx
0x180005a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a71  mov     ecx, eax; this
0x180005a73  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005a78  mov     rcx, [rbp+3Fh+var_78]
0x180005a7c  mov     rax, [rcx]
0x180005a7f  lea     r8d, [r12+1]
0x180005a84  lea     rdx, MF_XVP_DISABLE_FRC
0x180005a8b  mov     rax, [rax+0A8h]
0x180005a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a97  mov     ecx, eax; this
0x180005a99  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005a9e  mov     rcx, [rbp+3Fh+var_78]
0x180005aa2  mov     rax, [rcx]
0x180005aa5  lea     r8d, [r12+1]
0x180005aaa  lea     rdx, MF_XVP_CALLER_ALLOCATES_OUTPUT
0x180005ab1  mov     rax, [rax+0A8h]
0x180005ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005abd  mov     ecx, eax; this
0x180005abf  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005ac4  mov     rcx, [rbp+3Fh+var_90]
0x180005ac8  mov     rax, [rcx]
0x180005acb  xor     r9d, r9d
0x180005ace  mov     r8, rsi
0x180005ad1  xor     edx, edx
0x180005ad3  mov     rax, [rax+78h]
0x180005ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005adc  mov     ecx, eax; this
0x180005ade  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005ae3  mov     rcx, [rbp+3Fh+var_90]
0x180005ae7  mov     rax, [rcx]
0x180005aea  xor     r9d, r9d
0x180005aed  mov     r8, [rbp+3Fh+arg_20]
0x180005af1  xor     edx, edx
0x180005af3  mov     rax, [rax+80h]
0x180005afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aff  mov     ecx, eax; this
0x180005b01  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005b06  lea     rdx, [rbp+3Fh+var_90]
0x180005b0a  lea     rcx, [rbp+3Fh+var_70]
0x180005b0e  call    ??$As@UIMFVideoProcessorControl@@UIMFTransform@@@MF@@YA?AV?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@AEBV?$ComPtr@UIMFTransform@@@23@@Z; MF::As<IMFVideoProcessorControl,IMFTransform>(Microsoft::WRL::ComPtr<IMFTransform> const &)
0x180005b13  nop
0x180005b14  mov     rcx, [rbp+3Fh+var_70]
0x180005b18  mov     rax, [rcx]
0x180005b1b  mov     rdx, r14
0x180005b1e  mov     rax, [rax+20h]
0x180005b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b27  mov     ecx, eax; this
0x180005b29  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005b2e  mov     rcx, [rbp+3Fh+var_70]
0x180005b32  mov     rax, [rcx]
0x180005b35  mov     rdx, [rbp+3Fh+arg_28]
0x180005b39  mov     rax, [rax+28h]
0x180005b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b42  mov     ecx, eax; this
0x180005b44  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005b49  mov     dword ptr [rbp+3Fh+arg_30], r12d
0x180005b4d  mov     [rbp+3Fh+var_58], r12
0x180005b51  mov     [rbp+3Fh+var_48], r12
0x180005b55  mov     [rbp+3Fh+var_40], r12
0x180005b59  mov     rax, [rbp+3Fh+var_88]
0x180005b5d  mov     [rbp+3Fh+var_88], r12
0x180005b61  mov     [rbp+3Fh+var_50], rax
0x180005b65  mov     [rbp+3Fh+var_68], r12b
0x180005b69  lea     rax, [rbp+3Fh+var_58]
0x180005b6d  mov     [rbp+3Fh+var_60], rax
0x180005b71  mov     rcx, [rbp+3Fh+var_90]
0x180005b75  mov     rax, [rcx]
0x180005b78  xor     r8d, r8d
0x180005b7b  lea     edx, [r12+2]
0x180005b80  mov     rax, [rax+0B8h]
0x180005b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b8c  mov     ecx, eax; this
0x180005b8e  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005b93  mov     rcx, [rbp+3Fh+var_90]
0x180005b97  mov     rax, [rcx]
0x180005b9a  xor     r8d, r8d
0x180005b9d  xor     edx, edx
0x180005b9f  mov     rax, [rax+0B8h]
0x180005ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bab  mov     ecx, eax; this
0x180005bad  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005bb2  mov     rcx, [rbp+3Fh+var_90]
0x180005bb6  mov     rax, [rcx]
0x180005bb9  xor     r9d, r9d
0x180005bbc  mov     r8, [rbp+3Fh+ppIMFSample]
0x180005bc0  xor     edx, edx
0x180005bc2  mov     rax, [rax+0C0h]
0x180005bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bce  mov     ecx, eax; this
0x180005bd0  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005bd5  mov     rcx, [rbp+3Fh+var_90]
0x180005bd9  mov     rax, [rcx]
0x180005bdc  lea     rdx, [rbp+3Fh+arg_30]
0x180005be0  mov     [rsp+0C0h+ppv], rdx
0x180005be5  lea     r9, [rbp+3Fh+var_58]
0x180005be9  xor     edx, edx
0x180005beb  lea     r8d, [r12+1]
0x180005bf0  mov     rax, [rax+0C8h]
0x180005bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bfc  mov     ecx, eax; this
0x180005bfe  call    ?ThrowIfFailed@MF@@YAXJ@Z; MF::ThrowIfFailed(long)
0x180005c03  nop
0x180005c04  mov     rcx, [rbp+3Fh+var_50]
0x180005c08  test    rcx, rcx
0x180005c0b  jz      short loc_180005C1D
0x180005c0d  mov     rax, [rcx]
0x180005c10  mov     rax, [rax+10h]
0x180005c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c19  mov     [rbp+3Fh+var_50], r12
0x180005c1d  mov     rcx, [rbp+3Fh+var_40]
0x180005c21  test    rcx, rcx
0x180005c24  jz      short loc_180005C36
0x180005c26  mov     rax, [rcx]
0x180005c29  mov     rax, [rax+10h]
0x180005c2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c32  mov     [rbp+3Fh+var_40], r12
0x180005c36  mov     rcx, [rbp+3Fh+var_70]
0x180005c3a  test    rcx, rcx
0x180005c3d  jz      short loc_180005C50
0x180005c3f  mov     [rbp+3Fh+var_70], r12
0x180005c43  mov     rax, [rcx]
0x180005c46  mov     rax, [rax+10h]
0x180005c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4f  nop
0x180005c50  mov     rcx, [rbp+3Fh+var_78]
0x180005c54  test    rcx, rcx
0x180005c57  jz      short loc_180005C6A
0x180005c59  mov     [rbp+3Fh+var_78], r12
0x180005c5d  mov     rax, [rcx]
0x180005c60  mov     rax, [rax+10h]
0x180005c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c69  nop
0x180005c6a  mov     rcx, [rbp+3Fh+var_90]
0x180005c6e  test    rcx, rcx
0x180005c71  jz      short loc_180005C84
0x180005c73  mov     [rbp+3Fh+var_90], r12
0x180005c77  mov     rax, [rcx]
0x180005c7a  mov     rax, [rax+10h]
0x180005c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c83  nop
0x180005c84  mov     rcx, [rbp+3Fh+var_88]
0x180005c88  test    rcx, rcx
0x180005c8b  jz      short loc_180005C9E
0x180005c8d  mov     [rbp+3Fh+var_88], r12
0x180005c91  mov     rax, [rcx]
0x180005c94  mov     rax, [rax+10h]
0x180005c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c9d  nop
0x180005c9e  mov     rcx, [rbp+3Fh+ppIMFSample]
0x180005ca2  test    rcx, rcx
0x180005ca5  jz      short loc_180005CB8
0x180005ca7  mov     [rbp+3Fh+ppIMFSample], r12
0x180005cab  mov     rax, [rcx]
0x180005cae  mov     rax, [rax+10h]
0x180005cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cb7  nop
0x180005cb8  add     rsp, 98h
0x180005cbf  pop     r14
0x180005cc1  pop     r12
0x180005cc3  pop     rdi
0x180005cc4  pop     rsi
0x180005cc5  pop     rbx
0x180005cc6  pop     rbp
0x180005cc7  retn
```
