# CCoreMFT::ConfigureMjpgDecoder(IMFMediaType *,IMFMediaType *)

- ea: `0x180131c78`
- end: `0x180132007`
- name: `?ConfigureMjpgDecoder@CCoreMFT@@IEAAJPEAUIMFMediaType@@0@Z`
- size: `911`
- prototype: `__int64 __fastcall(CCoreMFT *__hidden this, struct IMFMediaType *, struct IMFMediaType *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b7f0`

## callees

- `0x180002420`
- `0x180009784`
- `0x18000b490`
- `0x18000c0f8`
- `0x18002bb98`
- `0x180131b88`
- `0x180131c78`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180131fd8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180131fd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180131f98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180131f98`
- `MFPlat!MFTEnumEx` at `0x180131d76`
- `MFPlat!MFTEnumEx` at `0x180131d76`

## pseudocode

```c
__int64 __fastcall CCoreMFT::ConfigureMjpgDecoder(CCoreMFT *this, struct IMFMediaType *a2, struct IMFMediaType *a3)
{
  HRESULT v6; // ebx
  int v7; // ecx
  __int64 v8; // rdx
  __int64 v9; // rdx
  UINT32 i; // r14d
  IMFActivate *v11; // rdi
  HRESULT (__stdcall *ActivateObject)(IMFActivate *, const IID *const, void **); // rbx
  IMFActivate *v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  char v17; // al
  UINT32 pnumMFTActivate; // [rsp+30h] [rbp-69h] BYREF
  IMFActivate **pppMFTActivate; // [rsp+38h] [rbp-61h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-59h] BYREF
  GUID guidCategory; // [rsp+50h] [rbp-49h] BYREF
  PSRWLOCK SRWLock; // [rsp+60h] [rbp-39h] BYREF
  __int64 v24; // [rsp+68h] [rbp-31h] BYREF
  int v25; // [rsp+70h] [rbp-29h]
  MFT_REGISTER_TYPE_INFO pOutputType; // [rsp+78h] [rbp-21h] BYREF
  MFT_REGISTER_TYPE_INFO pInputType; // [rsp+98h] [rbp-1h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 288);
  pppMFTActivate = 0;
  pInputType.guidSubtype = MFVideoFormat_MJPG;
  v21[0] = 0;
  pnumMFTActivate = 0;
  pInputType.guidMajorType = MFMediaType_Video;
  pOutputType.guidSubtype = MFVideoFormat_NV12;
  pOutputType.guidMajorType = MFMediaType_Video;
  CCoreMFT::CleanUpMjpgDecoder(this);
  if ( !a2 )
  {
    v6 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
LABEL_37:
      CCoreMFT::CleanUpMjpgDecoder(this);
      goto LABEL_39;
    }
    v8 = 183;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v7);
    goto LABEL_37;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v8 = 184;
    goto LABEL_4;
  }
  guidCategory = MFT_CATEGORY_VIDEO_DECODER;
  v6 = MFTEnumEx(&guidCategory, 0x10000000u, &pInputType, &pOutputType, &pppMFTActivate, &pnumMFTActivate);
  if ( v6 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v9 = 185;
LABEL_36:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v6);
    goto LABEL_37;
  }
  for ( i = 0; i < pnumMFTActivate; ++i )
  {
    if ( !*((_QWORD *)this + 27) )
    {
      v11 = pppMFTActivate[i];
      ActivateObject = v11->lpVtbl->ActivateObject;
      Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(v21);
      if ( ((int (__fastcall *)(IMFActivate *, GUID *, _QWORD *))ActivateObject)(
             v11,
             &GUID_bf94c121_5b05_4e6f_8000_ba598961414d,
             v21) >= 0 )
      {
        v13 = pppMFTActivate[i];
        if ( *((IMFActivate **)this + 28) != v13 )
        {
          if ( v13 )
            ((void (__fastcall *)(IMFActivate *))v13->lpVtbl->AddRef)(pppMFTActivate[i]);
          *(_QWORD *)&guidCategory.Data1 = *((_QWORD *)this + 28);
          *((_QWORD *)this + 28) = v13;
          Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&guidCategory);
        }
        v14 = v21[0];
        if ( *((_QWORD *)this + 27) != v21[0] )
        {
          if ( v21[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21[0] + 8LL))(v21[0]);
          *(_QWORD *)&guidCategory.Data1 = *((_QWORD *)this + 27);
          *((_QWORD *)this + 27) = v14;
          Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&guidCategory);
        }
      }
      Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(v21);
    }
    ((void (__fastcall *)(IMFActivate *))pppMFTActivate[i]->lpVtbl->Release)(pppMFTActivate[i]);
  }
  v15 = *((_QWORD *)this + 27);
  if ( !v15 )
  {
    v6 = -1072868846;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v9 = 186;
    goto LABEL_36;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IMFMediaType *, _QWORD))(*(_QWORD *)v15 + 120LL))(
         v15,
         0,
         a2,
         0);
  if ( v6 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v9 = 187;
    goto LABEL_36;
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFMediaType *, _QWORD))(**((_QWORD **)this + 27) + 128LL))(
         *((_QWORD *)this + 27),
         0,
         a3,
         0);
  if ( v6 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v9 = 188;
    goto LABEL_36;
  }
  v16 = *((_QWORD *)this + 27);
  v24 = 0;
  v25 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 56LL))(v16, 0, &v24);
  if ( v6 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_37;
    v9 = 189;
    goto LABEL_36;
  }
  v17 = ~BYTE1(v24);
  *((_BYTE *)this + 209) = 1;
  *((_BYTE *)this + 210) = v17 & 1;
LABEL_39:
  CoTaskMemFree(pppMFTActivate);
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v6);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(v21);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180131c78  mov     [rsp-8+arg_18], rbx
0x180131c7d  push    rbp
0x180131c7e  push    rsi
0x180131c7f  push    rdi
0x180131c80  push    r12
0x180131c82  push    r13
0x180131c84  push    r14
0x180131c86  push    r15
0x180131c88  lea     rbp, [rsp-27h]
0x180131c8d  sub     rsp, 0C0h
0x180131c94  mov     rax, cs:__security_cookie
0x180131c9b  xor     rax, rsp
0x180131c9e  mov     [rbp+57h+var_38], rax
0x180131ca2  mov     r13, rdx
0x180131ca5  mov     rsi, rcx
0x180131ca8  lea     rdx, [rcx+120h]
0x180131caf  mov     r12, r8
0x180131cb2  lea     rcx, [rbp+57h+SRWLock]
0x180131cb6  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180131cbb  movups  xmm0, xmmword ptr cs:MFVideoFormat_MJPG.Data1
0x180131cc2  xor     edi, edi
0x180131cc4  mov     rcx, rsi; this
0x180131cc7  movups  xmm1, xmmword ptr cs:MFMediaType_Video.Data1
0x180131cce  mov     [rbp+57h+var_B8], rdi
0x180131cd2  movdqu  xmmword ptr [rbp+57h+pInputType.guidSubtype.Data1], xmm0
0x180131cd7  mov     [rbp+57h+var_B0], rdi
0x180131cdb  movups  xmm0, xmmword ptr cs:MFVideoFormat_NV12.Data1
0x180131ce2  mov     [rbp+57h+var_C0], edi
0x180131ce5  movdqu  xmmword ptr [rbp+57h+pInputType.guidMajorType.Data1], xmm1
0x180131cea  movdqu  xmmword ptr [rbp+57h+pOutputType.guidSubtype.Data1], xmm0
0x180131cef  movdqu  xmmword ptr [rbp+57h+pOutputType.guidMajorType.Data1], xmm1
0x180131cf4  call    ?CleanUpMjpgDecoder@CCoreMFT@@IEAAXXZ; CCoreMFT::CleanUpMjpgDecoder(void)
0x180131cf9  lea     r15, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x180131d00  test    r13, r13
0x180131d03  jnz     short loc_180131D27
0x180131d05  mov     ecx, 80004003h
0x180131d0a  mov     ebx, ecx
0x180131d0c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180131d11  cmp     al, 1
0x180131d13  jb      loc_180131F73
0x180131d19  mov     edx, 0B7h
0x180131d1e  mov     dword ptr [rsp+0F0h+pppMFTActivate], ecx
0x180131d22  jmp     loc_180131F5D
0x180131d27  test    r12, r12
0x180131d2a  jnz     short loc_180131D47
0x180131d2c  mov     ecx, 80004003h
0x180131d31  mov     ebx, ecx
0x180131d33  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180131d38  cmp     al, 1
0x180131d3a  jb      loc_180131F73
0x180131d40  mov     edx, 0B8h
0x180131d45  jmp     short loc_180131D1E
0x180131d47  movups  xmm0, xmmword ptr cs:MFT_CATEGORY_VIDEO_DECODER.Data1
0x180131d4e  lea     rax, [rbp+57h+var_C0]
0x180131d52  mov     edx, 10000000h; Flags
0x180131d57  mov     [rsp+0F0h+pnumMFTActivate], rax; pnumMFTActivate
0x180131d5c  lea     r9, [rbp+57h+pOutputType]; pOutputType
0x180131d60  lea     rax, [rbp+57h+var_B8]
0x180131d64  lea     r8, [rbp+57h+pInputType]; pInputType
0x180131d68  mov     [rsp+0F0h+pppMFTActivate], rax; pppMFTActivate
0x180131d6d  lea     rcx, [rbp+57h+guidCategory]; guidCategory
0x180131d71  movdqu  xmmword ptr [rbp+57h+guidCategory.Data1], xmm0
0x180131d76  call    cs:__imp_MFTEnumEx
0x180131d7c  mov     ebx, eax
0x180131d7e  test    eax, eax
0x180131d80  jns     short loc_180131D99
0x180131d82  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180131d87  cmp     al, 1
0x180131d89  jb      loc_180131F73
0x180131d8f  mov     edx, 0B9h
0x180131d94  jmp     loc_180131F59
0x180131d99  mov     r14d, edi
0x180131d9c  cmp     [rbp+57h+var_C0], edi
0x180131d9f  jbe     loc_180131E99
0x180131da5  mov     r15d, r14d
0x180131da8  cmp     [rsi+0D8h], rdi
0x180131daf  jnz     loc_180131E71
0x180131db5  mov     rax, [rbp+57h+var_B8]
0x180131db9  lea     rcx, [rbp+57h+var_B0]
0x180131dbd  mov     rdi, [rax+r15*8]
0x180131dc1  mov     rax, [rdi]
0x180131dc4  mov     rbx, [rax+108h]
0x180131dcb  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180131dd0  lea     r8, [rbp+57h+var_B0]
0x180131dd4  mov     rcx, rdi
0x180131dd7  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x180131dde  mov     rax, rbx
0x180131de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131de6  xor     edi, edi
0x180131de8  test    eax, eax
0x180131dea  js      short loc_180131E68
0x180131dec  mov     rax, [rbp+57h+var_B8]
0x180131df0  mov     rbx, [rax+r15*8]
0x180131df4  cmp     [rsi+0E0h], rbx
0x180131dfb  jz      short loc_180131E2C
0x180131dfd  test    rbx, rbx
0x180131e00  jz      short loc_180131E11
0x180131e02  mov     rax, [rbx]
0x180131e05  mov     rcx, rbx
0x180131e08  mov     rax, [rax+8]
0x180131e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131e11  mov     rax, [rsi+0E0h]
0x180131e18  lea     rcx, [rbp+57h+guidCategory]
0x180131e1c  mov     qword ptr [rbp+57h+guidCategory.Data1], rax
0x180131e20  mov     [rsi+0E0h], rbx
0x180131e27  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180131e2c  mov     rbx, [rbp+57h+var_B0]
0x180131e30  cmp     [rsi+0D8h], rbx
0x180131e37  jz      short loc_180131E68
0x180131e39  test    rbx, rbx
0x180131e3c  jz      short loc_180131E4D
0x180131e3e  mov     rax, [rbx]
0x180131e41  mov     rcx, rbx
0x180131e44  mov     rax, [rax+8]
0x180131e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131e4d  mov     rax, [rsi+0D8h]
0x180131e54  lea     rcx, [rbp+57h+guidCategory]
0x180131e58  mov     qword ptr [rbp+57h+guidCategory.Data1], rax
0x180131e5c  mov     [rsi+0D8h], rbx
0x180131e63  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180131e68  lea     rcx, [rbp+57h+var_B0]
0x180131e6c  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180131e71  mov     rax, [rbp+57h+var_B8]
0x180131e75  mov     rcx, [rax+r15*8]
0x180131e79  mov     rax, [rcx]
0x180131e7c  mov     rax, [rax+10h]
0x180131e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131e85  inc     r14d
0x180131e88  cmp     r14d, [rbp+57h+var_C0]
0x180131e8c  jb      loc_180131DA5
0x180131e92  lea     r15, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x180131e99  mov     rcx, [rsi+0D8h]
0x180131ea0  test    rcx, rcx
0x180131ea3  jnz     short loc_180131EC1
0x180131ea5  mov     ebx, 0C00D5212h
0x180131eaa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180131eaf  cmp     al, 1
0x180131eb1  jb      loc_180131F73
0x180131eb7  mov     edx, 0BAh
0x180131ebc  jmp     loc_180131F59
0x180131ec1  mov     rax, [rcx]
0x180131ec4  xor     r9d, r9d
0x180131ec7  mov     r8, r13
0x180131eca  xor     edx, edx
0x180131ecc  mov     rax, [rax+78h]
0x180131ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131ed5  mov     ebx, eax
0x180131ed7  test    eax, eax
0x180131ed9  jns     short loc_180131EEF
0x180131edb  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180131ee0  cmp     al, 1
0x180131ee2  jb      loc_180131F73
0x180131ee8  mov     edx, 0BBh
0x180131eed  jmp     short loc_180131F59
0x180131eef  mov     rcx, [rsi+0D8h]
0x180131ef6  xor     r9d, r9d
0x180131ef9  mov     r8, r12
0x180131efc  xor     edx, edx
0x180131efe  mov     rax, [rcx]
0x180131f01  mov     rax, [rax+80h]
0x180131f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131f0d  mov     ebx, eax
0x180131f0f  test    eax, eax
0x180131f11  jns     short loc_180131F23
0x180131f13  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180131f18  cmp     al, 1
0x180131f1a  jb      short loc_180131F73
0x180131f1c  mov     edx, 0BCh
0x180131f21  jmp     short loc_180131F59
0x180131f23  mov     rcx, [rsi+0D8h]
0x180131f2a  lea     r8, [rbp+57h+var_88]
0x180131f2e  xor     eax, eax
0x180131f30  xor     edx, edx
0x180131f32  mov     [rbp+57h+var_88], rax
0x180131f36  mov     [rbp+57h+var_80], eax
0x180131f39  mov     rax, [rcx]
0x180131f3c  mov     rax, [rax+38h]
0x180131f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180131f45  mov     ebx, eax
0x180131f47  test    eax, eax
0x180131f49  jns     short loc_180131F7D
0x180131f4b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180131f50  cmp     al, 1
0x180131f52  jb      short loc_180131F73
0x180131f54  mov     edx, 0BDh
0x180131f59  mov     dword ptr [rsp+0F0h+pppMFTActivate], ebx
0x180131f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180131f64  mov     r9, rsi
0x180131f67  mov     r8, r15
0x180131f6a  mov     rcx, [rcx+10h]
0x180131f6e  call    WPP_SF_qD
0x180131f73  mov     rcx, rsi; this
0x180131f76  call    ?CleanUpMjpgDecoder@CCoreMFT@@IEAAXXZ; CCoreMFT::CleanUpMjpgDecoder(void)
0x180131f7b  jmp     short loc_180131F94
0x180131f7d  mov     eax, dword ptr [rbp+57h+var_88]
0x180131f80  shr     eax, 8
0x180131f83  not     al
0x180131f85  mov     byte ptr [rsi+0D1h], 1
0x180131f8c  and     al, 1
0x180131f8e  mov     [rsi+0D2h], al
0x180131f94  mov     rcx, [rbp+57h+var_B8]; pv
0x180131f98  call    cs:__imp_CoTaskMemFree
0x180131f9e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180131fa3  cmp     al, 20h ; ' '
0x180131fa5  jb      short loc_180131FC6
0x180131fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x180131fae  mov     edx, 0BEh
0x180131fb3  mov     r9, rsi
0x180131fb6  mov     dword ptr [rsp+0F0h+pppMFTActivate], ebx
0x180131fba  mov     r8, r15
0x180131fbd  mov     rcx, [rcx+10h]
0x180131fc1  call    WPP_SF_qD
0x180131fc6  lea     rcx, [rbp+57h+var_B0]
0x180131fca  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180131fcf  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180131fd3  test    rcx, rcx
0x180131fd6  jz      short loc_180131FDE
0x180131fd8  call    cs:__imp_ReleaseSRWLockExclusive
0x180131fde  mov     eax, ebx
0x180131fe0  mov     rcx, [rbp+57h+var_38]
0x180131fe4  xor     rcx, rsp; StackCookie
0x180131fe7  call    __security_check_cookie
0x180131fec  mov     rbx, [rsp+0F0h+arg_18]
0x180131ff4  add     rsp, 0C0h
0x180131ffb  pop     r15
0x180131ffd  pop     r14
0x180131fff  pop     r13
0x180132001  pop     r12
0x180132003  pop     rdi
0x180132004  pop     rsi
0x180132005  pop     rbp
0x180132006  retn
```
