# CCoreMFT::XVPConvertSample(IMFSample *,IMFSample * *,tagRECT *,tagRECT *)

- ea: `0x1801358a8`
- end: `0x180135f6b`
- name: `?XVPConvertSample@CCoreMFT@@IEAAJPEAUIMFSample@@PEAPEAU2@PEAUtagRECT@@2@Z`
- size: `1731`
- prototype: `__int64 __fastcall(CCoreMFT *this, struct IMFSample *, struct IMFSample **, struct tagRECT *)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180010fb0`
- `0x1800b00f0`

## callees

- `0x180002420`
- `0x180005660`
- `0x180009784`
- `0x18000b490`
- `0x18000c0f8`
- `0x18001d784`
- `0x18002bb98`
- `0x18002cadc`
- `0x1801358a8`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180135f3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180135f3c`
- `MFPlat!MFCreate2DMediaBuffer` at `0x180135c9e`
- `MFPlat!MFCreate2DMediaBuffer` at `0x180135c9e`
- `MFPlat!MFCreateSample` at `0x180135d55`
- `MFPlat!MFCreateSample` at `0x180135d55`

## pseudocode

```c
__int64 __fastcall CCoreMFT::XVPConvertSample(
        CCoreMFT *this,
        struct IMFSample *a2,
        struct IMFSample **a3,
        struct tagRECT *a4)
{
  HRESULT v7; // esi
  int v8; // ecx
  __int64 v9; // rdx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v11; // rdx
  __int64 (__fastcall *v12)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v15; // rcx
  struct IMFSample *v16; // rax
  IMFSample *ppIMFSample; // [rsp+30h] [rbp-81h] BYREF
  __int64 v19; // [rsp+38h] [rbp-79h] BYREF
  DWORD dwHeight; // [rsp+40h] [rbp-71h] BYREF
  DWORD dwWidth; // [rsp+44h] [rbp-6Dh] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+48h] [rbp-69h] BYREF
  int (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-61h] BYREF
  __int64 v24; // [rsp+58h] [rbp-59h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-51h] BYREF
  __int64 v26; // [rsp+70h] [rbp-41h]
  int v27; // [rsp+78h] [rbp-39h] BYREF
  __int64 v28; // [rsp+80h] [rbp-31h] BYREF
  __int64 v29; // [rsp+88h] [rbp-29h] BYREF
  __int64 v30; // [rsp+90h] [rbp-21h] BYREF
  __int64 v31; // [rsp+98h] [rbp-19h] BYREF
  __int64 v32; // [rsp+A0h] [rbp-11h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-9h] BYREF
  DWORD dwFourCC[4]; // [rsp+B0h] [rbp-1h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 288);
  v27 = 0;
  v24 = 0;
  v25[1] = 0;
  v26 = 0;
  v25[0] = 0;
  v23 = 0;
  ppBuffer = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  ppIMFSample = 0;
  v19 = 0;
  *(_OWORD *)dwFourCC = 0;
  if ( !a2 )
  {
    v7 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_85;
    v9 = 215;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v8);
    goto LABEL_81;
  }
  if ( !a3 )
  {
    v7 = -2147467261;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_85;
    v9 = 216;
    goto LABEL_4;
  }
  *a3 = 0;
  if ( !*((_BYTE *)this + 232) )
  {
    v7 = -1072875850;
    goto LABEL_85;
  }
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 30);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v19);
  v7 = (**v10)(v10, &GUID_a3f675d5_6119_4f7f_a100_1d8b280f0efb, &v19);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 32LL))(v19, 0);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 218;
      goto LABEL_14;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 40LL))(v19, 0);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 219;
      goto LABEL_14;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 34) + 48LL))(*((_QWORD *)this + 34), v25);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 220;
      goto LABEL_14;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 30) + 184LL))(
           *((_QWORD *)this + 30),
           0,
           0);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 221;
      goto LABEL_14;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IMFSample *, _QWORD))(**((_QWORD **)this + 30) + 192LL))(
           *((_QWORD *)this + 30),
           0,
           a2,
           0);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 222;
      goto LABEL_14;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *, int *))(**((_QWORD **)this + 30) + 200LL))(
           *((_QWORD *)this + 30),
           0,
           1,
           &v24,
           &v27);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 223;
      goto LABEL_14;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 32LL))(v19, 0);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 224;
      goto LABEL_14;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 40LL))(v19, 0);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 225;
      goto LABEL_14;
    }
    v12 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v25[0] + 320LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v7 = v12(v25[0], 0, &v23);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_81;
      v11 = 226;
      goto LABEL_14;
    }
    v13 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v23;
    v14 = **v23;
    Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v28);
    if ( v14(v13, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v28) < 0 )
    {
      v16 = (struct IMFSample *)v25[0];
      v25[0] = 0;
    }
    else
    {
      v15 = *((_QWORD *)this + 37);
      dwWidth = 0;
      dwHeight = 0;
      v7 = MFGetAttribute2UINT32asUINT64(v15, &MF_MT_FRAME_SIZE, &dwWidth, &dwHeight);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 227;
        goto LABEL_14;
      }
      v7 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, DWORD *))(**((_QWORD **)this + 37) + 80LL))(
             *((_QWORD *)this + 37),
             &MF_MT_SUBTYPE,
             dwFourCC);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 228;
        goto LABEL_14;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
      v7 = MFCreate2DMediaBuffer(dwWidth, dwHeight, dwFourCC[0], 0, &ppBuffer);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 229;
        goto LABEL_14;
      }
      v7 = Microsoft::WRL::ComPtr<IMFMediaBuffer>::As<IMF2DBuffer2>(&v23, &v30);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 230;
        goto LABEL_14;
      }
      v7 = Microsoft::WRL::ComPtr<IMFMediaBuffer>::As<IMF2DBuffer2>(&ppBuffer, &v29);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 231;
        goto LABEL_14;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 88LL))(v30, v29);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 232;
        goto LABEL_14;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
      v7 = MFCreateSample(&ppIMFSample);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 233;
        goto LABEL_14;
      }
      v7 = (*(__int64 (__fastcall **)(_QWORD, IMFSample *))(*(_QWORD *)v25[0] + 256LL))(v25[0], ppIMFSample);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 234;
        goto LABEL_14;
      }
      v7 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
             ppIMFSample,
             ppBuffer);
      if ( v7 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_81;
        v11 = 235;
        goto LABEL_14;
      }
      v31 = 0;
      if ( (*(int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v25[0] + 280LL))(v25[0], &v31) >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, v31);
        if ( v7 < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_81;
          v11 = 236;
          goto LABEL_14;
        }
      }
      v32 = 0;
      if ( (*(int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v25[0] + 296LL))(v25[0], &v32) >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(IMFSample *, __int64))ppIMFSample->lpVtbl->SetSampleDuration)(ppIMFSample, v32);
        if ( v7 < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_81;
          v11 = 237;
          goto LABEL_14;
        }
      }
      v16 = ppIMFSample;
      ppIMFSample = 0;
    }
    *a3 = v16;
    goto LABEL_81;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v11 = 217;
LABEL_14:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v7);
  }
LABEL_81:
  if ( v25[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v25[0] + 16LL))(v25[0]);
    v25[0] = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
LABEL_85:
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() >= 0x20u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 238, &WPP_55bf114490c93d008a53f926557b4d05_Traceguids, this, v7);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppIMFSample);
  Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppBuffer);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801358a8  mov     [rsp-8+arg_18], rbx
0x1801358ad  push    rbp
0x1801358ae  push    rsi
0x1801358af  push    rdi
0x1801358b0  push    r12
0x1801358b2  push    r13
0x1801358b4  push    r14
0x1801358b6  push    r15
0x1801358b8  lea     rbp, [rsp-1Fh]
0x1801358bd  sub     rsp, 0D0h
0x1801358c4  mov     rax, cs:__security_cookie
0x1801358cb  xor     rax, rsp
0x1801358ce  mov     [rbp+4Fh+var_40], rax
0x1801358d2  mov     rdi, rdx
0x1801358d5  mov     r14, rcx
0x1801358d8  lea     rdx, [rcx+120h]
0x1801358df  mov     r15, r8
0x1801358e2  lea     rcx, [rbp+4Fh+SRWLock]
0x1801358e6  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1801358eb  xor     r12d, r12d
0x1801358ee  lea     r13, WPP_55bf114490c93d008a53f926557b4d05_Traceguids
0x1801358f5  mov     [rbp+4Fh+var_88], r12d
0x1801358f9  xorps   xmm0, xmm0
0x1801358fc  mov     [rbp+4Fh+var_A8], r12
0x180135900  mov     [rbp+4Fh+var_98], r12
0x180135904  mov     [rbp+4Fh+var_90], r12
0x180135908  mov     [rbp+4Fh+var_A0], r12
0x18013590c  mov     [rbp+4Fh+var_B0], r12
0x180135910  mov     [rbp+4Fh+var_B8], r12
0x180135914  mov     [rbp+4Fh+var_70], r12
0x180135918  mov     [rbp+4Fh+var_78], r12
0x18013591c  mov     [rbp+4Fh+var_80], r12
0x180135920  mov     [rsp+100h+ppIMFSample], r12
0x180135925  mov     [rbp+4Fh+var_C8], r12
0x180135929  movups  xmmword ptr [rbp+4Fh+dwFourCC], xmm0
0x18013592d  test    rdi, rdi
0x180135930  jnz     short loc_18013596A
0x180135932  mov     ecx, 80004003h
0x180135937  mov     esi, ecx
0x180135939  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013593e  cmp     al, 1
0x180135940  jb      loc_180135ECB
0x180135946  mov     edx, 0D7h
0x18013594b  mov     dword ptr [rsp+100h+ppBuffer], ecx
0x18013594f  mov     rcx, cs:WPP_GLOBAL_Control
0x180135956  mov     r9, r14
0x180135959  mov     r8, r13
0x18013595c  mov     rcx, [rcx+10h]
0x180135960  call    WPP_SF_qD
0x180135965  jmp     loc_180135E99
0x18013596a  test    r15, r15
0x18013596d  jnz     short loc_18013598A
0x18013596f  mov     ecx, 80004003h
0x180135974  mov     esi, ecx
0x180135976  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18013597b  cmp     al, 1
0x18013597d  jb      loc_180135ECB
0x180135983  mov     edx, 0D8h
0x180135988  jmp     short loc_18013594B
0x18013598a  mov     [r15], r12
0x18013598d  cmp     [r14+0E8h], r12b
0x180135994  jnz     short loc_1801359A0
0x180135996  mov     esi, 0C00D36B6h
0x18013599b  jmp     loc_180135ECB
0x1801359a0  mov     rbx, [r14+0F0h]
0x1801359a7  lea     rcx, [rbp+4Fh+var_C8]
0x1801359ab  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x1801359b0  mov     rax, [rbx]
0x1801359b3  lea     r8, [rbp+4Fh+var_C8]
0x1801359b7  lea     rdx, _GUID_a3f675d5_6119_4f7f_a100_1d8b280f0efb
0x1801359be  mov     rcx, rbx
0x1801359c1  mov     rax, [rax]
0x1801359c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801359c9  mov     esi, eax
0x1801359cb  test    eax, eax
0x1801359cd  jns     short loc_1801359EA
0x1801359cf  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1801359d4  cmp     al, 1
0x1801359d6  jb      loc_180135E99
0x1801359dc  mov     edx, 0D9h
0x1801359e1  mov     dword ptr [rsp+100h+ppBuffer], esi
0x1801359e5  jmp     loc_18013594F
0x1801359ea  mov     rcx, [rbp+4Fh+var_C8]
0x1801359ee  xor     edx, edx
0x1801359f0  mov     rax, [rcx]
0x1801359f3  mov     rax, [rax+20h]
0x1801359f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801359fc  mov     esi, eax
0x1801359fe  test    eax, eax
0x180135a00  jns     short loc_180135A16
0x180135a02  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135a07  cmp     al, 1
0x180135a09  jb      loc_180135E99
0x180135a0f  mov     edx, 0DAh
0x180135a14  jmp     short loc_1801359E1
0x180135a16  mov     rcx, [rbp+4Fh+var_C8]
0x180135a1a  xor     edx, edx
0x180135a1c  mov     rax, [rcx]
0x180135a1f  mov     rax, [rax+28h]
0x180135a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a28  mov     esi, eax
0x180135a2a  test    eax, eax
0x180135a2c  jns     short loc_180135A42
0x180135a2e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135a33  cmp     al, 1
0x180135a35  jb      loc_180135E99
0x180135a3b  mov     edx, 0DBh
0x180135a40  jmp     short loc_1801359E1
0x180135a42  mov     rcx, [r14+110h]
0x180135a49  lea     rdx, [rbp+4Fh+var_A0]
0x180135a4d  mov     rax, [rcx]
0x180135a50  mov     rax, [rax+30h]
0x180135a54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a59  mov     esi, eax
0x180135a5b  test    eax, eax
0x180135a5d  jns     short loc_180135A76
0x180135a5f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135a64  cmp     al, 1
0x180135a66  jb      loc_180135E99
0x180135a6c  mov     edx, 0DCh
0x180135a71  jmp     loc_1801359E1
0x180135a76  mov     rcx, [r14+0F0h]
0x180135a7d  xor     r8d, r8d
0x180135a80  xor     edx, edx
0x180135a82  mov     rax, [rcx]
0x180135a85  mov     rax, [rax+0B8h]
0x180135a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a91  mov     esi, eax
0x180135a93  test    eax, eax
0x180135a95  jns     short loc_180135AAE
0x180135a97  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135a9c  cmp     al, 1
0x180135a9e  jb      loc_180135E99
0x180135aa4  mov     edx, 0DDh
0x180135aa9  jmp     loc_1801359E1
0x180135aae  mov     rcx, [r14+0F0h]
0x180135ab5  xor     r9d, r9d
0x180135ab8  mov     r8, rdi
0x180135abb  xor     edx, edx
0x180135abd  mov     rax, [rcx]
0x180135ac0  mov     rax, [rax+0C0h]
0x180135ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135acc  mov     esi, eax
0x180135ace  test    eax, eax
0x180135ad0  jns     short loc_180135AE9
0x180135ad2  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135ad7  cmp     al, 1
0x180135ad9  jb      loc_180135E99
0x180135adf  mov     edx, 0DEh
0x180135ae4  jmp     loc_1801359E1
0x180135ae9  mov     rcx, [r14+0F0h]
0x180135af0  lea     rdx, [rbp+4Fh+var_88]
0x180135af4  mov     [rsp+100h+ppBuffer], rdx
0x180135af9  lea     r9, [rbp+4Fh+var_A8]
0x180135afd  xor     edx, edx
0x180135aff  mov     rax, [rcx]
0x180135b02  lea     r8d, [rdx+1]
0x180135b06  mov     rax, [rax+0C8h]
0x180135b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135b12  mov     esi, eax
0x180135b14  test    eax, eax
0x180135b16  jns     short loc_180135B2F
0x180135b18  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135b1d  cmp     al, 1
0x180135b1f  jb      loc_180135E99
0x180135b25  mov     edx, 0DFh
0x180135b2a  jmp     loc_1801359E1
0x180135b2f  mov     rcx, [rbp+4Fh+var_C8]
0x180135b33  xor     edx, edx
0x180135b35  mov     rax, [rcx]
0x180135b38  mov     rax, [rax+20h]
0x180135b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135b41  mov     esi, eax
0x180135b43  test    eax, eax
0x180135b45  jns     short loc_180135B5E
0x180135b47  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135b4c  cmp     al, 1
0x180135b4e  jb      loc_180135E99
0x180135b54  mov     edx, 0E0h
0x180135b59  jmp     loc_1801359E1
0x180135b5e  mov     rcx, [rbp+4Fh+var_C8]
0x180135b62  xor     edx, edx
0x180135b64  mov     rax, [rcx]
0x180135b67  mov     rax, [rax+28h]
0x180135b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135b70  mov     esi, eax
0x180135b72  test    eax, eax
0x180135b74  jns     short loc_180135B8D
0x180135b76  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135b7b  cmp     al, 1
0x180135b7d  jb      loc_180135E99
0x180135b83  mov     edx, 0E1h
0x180135b88  jmp     loc_1801359E1
0x180135b8d  mov     rax, [rbp+4Fh+var_A0]
0x180135b91  mov     rcx, [rax]
0x180135b94  mov     rbx, [rcx+140h]
0x180135b9b  lea     rcx, [rbp+4Fh+var_B0]
0x180135b9f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180135ba4  mov     rcx, [rbp+4Fh+var_A0]
0x180135ba8  lea     r8, [rbp+4Fh+var_B0]
0x180135bac  xor     edx, edx
0x180135bae  mov     rax, rbx
0x180135bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135bb6  mov     esi, eax
0x180135bb8  test    eax, eax
0x180135bba  jns     short loc_180135BD3
0x180135bbc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135bc1  cmp     al, 1
0x180135bc3  jb      loc_180135E99
0x180135bc9  mov     edx, 0E2h
0x180135bce  jmp     loc_1801359E1
0x180135bd3  mov     rbx, [rbp+4Fh+var_B0]
0x180135bd7  lea     rcx, [rbp+4Fh+var_80]
0x180135bdb  mov     rax, [rbx]
0x180135bde  mov     rdi, [rax]
0x180135be1  call    ?InternalRelease@?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IMFVideoProcessorControl>::InternalRelease(void)
0x180135be6  lea     r8, [rbp+4Fh+var_80]
0x180135bea  mov     rcx, rbx
0x180135bed  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x180135bf4  mov     rax, rdi
0x180135bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135bfc  test    eax, eax
0x180135bfe  js      loc_180135E8E
0x180135c04  mov     rcx, [r14+128h]
0x180135c0b  lea     r9, [rbp+4Fh+dwHeight]
0x180135c0f  lea     r8, [rbp+4Fh+dwWidth]
0x180135c13  mov     [rbp+4Fh+dwWidth], r12d
0x180135c17  lea     rdx, MF_MT_FRAME_SIZE
0x180135c1e  mov     [rbp+4Fh+dwHeight], r12d
0x180135c22  call    MFGetAttribute2UINT32asUINT64
0x180135c27  mov     esi, eax
0x180135c29  test    eax, eax
0x180135c2b  jns     short loc_180135C44
0x180135c2d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135c32  cmp     al, 1
0x180135c34  jb      loc_180135E99
0x180135c3a  mov     edx, 0E3h
0x180135c3f  jmp     loc_1801359E1
0x180135c44  mov     rcx, [r14+128h]
0x180135c4b  lea     r8, [rbp+4Fh+dwFourCC]
0x180135c4f  lea     rdx, MF_MT_SUBTYPE
0x180135c56  mov     rax, [rcx]
0x180135c59  mov     rax, [rax+50h]
0x180135c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135c62  mov     esi, eax
0x180135c64  test    eax, eax
0x180135c66  jns     short loc_180135C7F
0x180135c68  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135c6d  cmp     al, 1
0x180135c6f  jb      loc_180135E99
0x180135c75  mov     edx, 0E4h
0x180135c7a  jmp     loc_1801359E1
0x180135c7f  lea     rcx, [rbp+4Fh+var_B8]
0x180135c83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180135c88  mov     r8d, [rbp+4Fh+dwFourCC]; dwFourCC
0x180135c8c  lea     rax, [rbp+4Fh+var_B8]
0x180135c90  mov     edx, [rbp+4Fh+dwHeight]; dwHeight
0x180135c93  xor     r9d, r9d; fBottomUp
0x180135c96  mov     ecx, [rbp+4Fh+dwWidth]; dwWidth
0x180135c99  mov     [rsp+100h+ppBuffer], rax; ppBuffer
0x180135c9e  call    cs:__imp_MFCreate2DMediaBuffer
0x180135ca4  mov     esi, eax
0x180135ca6  test    eax, eax
0x180135ca8  jns     short loc_180135CC1
0x180135caa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135caf  cmp     al, 1
0x180135cb1  jb      loc_180135E99
0x180135cb7  mov     edx, 0E5h
0x180135cbc  jmp     loc_1801359E1
0x180135cc1  lea     rdx, [rbp+4Fh+var_70]
0x180135cc5  lea     rcx, [rbp+4Fh+var_B0]
0x180135cc9  call    ??$As@UIMF2DBuffer2@@@?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IMFMediaBuffer>::As<IMF2DBuffer2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMF2DBuffer2>>)
0x180135cce  mov     esi, eax
0x180135cd0  test    eax, eax
0x180135cd2  jns     short loc_180135CEB
0x180135cd4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135cd9  cmp     al, 1
0x180135cdb  jb      loc_180135E99
0x180135ce1  mov     edx, 0E6h
0x180135ce6  jmp     loc_1801359E1
0x180135ceb  lea     rdx, [rbp+4Fh+var_78]
0x180135cef  lea     rcx, [rbp+4Fh+var_B8]
0x180135cf3  call    ??$As@UIMF2DBuffer2@@@?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMF2DBuffer2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IMFMediaBuffer>::As<IMF2DBuffer2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMF2DBuffer2>>)
0x180135cf8  mov     esi, eax
0x180135cfa  test    eax, eax
0x180135cfc  jns     short loc_180135D15
0x180135cfe  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180135d03  cmp     al, 1
0x180135d05  jb      loc_180135E99
0x180135d0b  mov     edx, 0E7h
0x180135d10  jmp     loc_1801359E1
0x180135d15  mov     rcx, [rbp+4Fh+var_70]
0x180135d19  mov     rdx, [rbp+4Fh+var_78]
0x180135d1d  mov     rax, [rcx]
0x180135d20  mov     rax, [rax+58h]
0x180135d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135d29  mov     esi, eax
0x180135d2b  test    eax, eax
0x180135d2d  jns     short loc_180135D46
0x180135d2f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
  ... truncated ...
```
