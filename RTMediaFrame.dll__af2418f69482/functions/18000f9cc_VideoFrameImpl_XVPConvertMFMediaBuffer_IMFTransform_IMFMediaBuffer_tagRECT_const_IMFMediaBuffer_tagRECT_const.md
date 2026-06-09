# VideoFrameImpl::XVPConvertMFMediaBuffer(IMFTransform *,IMFMediaBuffer *,tagRECT const &,IMFMediaBuffer *,tagRECT const &)

- ea: `0x18000f9cc`
- end: `0x18000fe49`
- name: `?XVPConvertMFMediaBuffer@VideoFrameImpl@@CAJPEAUIMFTransform@@PEAUIMFMediaBuffer@@AEBUtagRECT@@12@Z`
- size: `1149`
- prototype: `__int64 __fastcall(struct IMFTransform *, struct IMFMediaBuffer *, const struct tagRECT *, struct IMFMediaBuffer *, const struct tagRECT *)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000eef4`
- `0x1800227b4`
- `0x180022c1c`
- `0x1800231cc`

## callees

- `0x1800019c0`
- `0x18000f9cc`
- `0x1800134e0`
- `0x180035854`
- `0x180052010`

## import_xrefs

- `MFPlat!MFCreateSample` at `0x18000fa26`
- `MFPlat!MFCreateSample` at `0x18000fad6`
- `MFPlat!MFCreateSample` at `0x18000fa26`
- `MFPlat!MFCreateSample` at `0x18000fad6`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall VideoFrameImpl::XVPConvertMFMediaBuffer(
        struct IMFTransform *a1,
        struct IMFMediaBuffer *a2,
        const struct tagRECT *a3,
        struct IMFMediaBuffer *a4,
        const struct tagRECT *a5)
{
  __int64 v9; // rbx
  HRESULT v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 *v13; // rax
  IMFSample *v14; // rax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  IMFSample *v18; // rcx
  IMFSample *v19; // rcx
  IMFSample *v21; // [rsp+30h] [rbp-51h] BYREF
  IMFSample *ppIMFSample; // [rsp+38h] [rbp-49h] BYREF
  __int64 v23; // [rsp+40h] [rbp-41h] BYREF
  __int64 v24; // [rsp+48h] [rbp-39h]
  struct IMFTransform *v25; // [rsp+50h] [rbp-31h]
  char v26; // [rsp+58h] [rbp-29h]
  __int64 *v27; // [rsp+60h] [rbp-21h]
  __int64 v28; // [rsp+68h] [rbp-19h] BYREF
  IMFSample *v29; // [rsp+70h] [rbp-11h]
  __int64 v30; // [rsp+78h] [rbp-9h]
  __int64 v31; // [rsp+80h] [rbp-1h]
  int v32; // [rsp+E0h] [rbp+5Fh] BYREF

  ppIMFSample = 0;
  v25 = a1;
  if ( a1 )
    ((void (__fastcall *)(struct IMFTransform *))a1->lpVtbl->AddRef)(a1);
  v21 = 0;
  v9 = 0;
  v24 = 0;
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&ppIMFSample);
  v10 = MFCreateSample(&ppIMFSample);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_58;
    v12 = 38;
    goto LABEL_6;
  }
  v10 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(ppIMFSample, a2);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))ppIMFSample->lpVtbl->SetSampleTime)(ppIMFSample, 0);
    v11 = v10;
    if ( v10 >= 0 )
    {
      Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v21);
      v10 = MFCreateSample(&v21);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v10 = ((__int64 (__fastcall *)(IMFSample *, struct IMFMediaBuffer *))v21->lpVtbl->AddBuffer)(v21, a4);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v10 = ((__int64 (__fastcall *)(IMFSample *, _QWORD))v21->lpVtbl->SetSampleTime)(v21, 0);
          v11 = v10;
          if ( v10 >= 0 )
          {
            v13 = (__int64 *)MF::As<IMFVideoProcessorControl,IMFTransform>(&v32, a1);
            v9 = 0;
            if ( &v23 != v13 )
            {
              v9 = *v13;
              *v13 = 0;
            }
            v23 = 0;
            v24 = v9;
            Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v23);
            Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v32);
            v10 = (*(__int64 (__fastcall **)(__int64, const struct tagRECT *))(*(_QWORD *)v9 + 32LL))(v9, a3);
            v11 = v10;
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, const struct tagRECT *))(*(_QWORD *)v9 + 40LL))(v9, a5);
              v11 = v10;
              if ( v10 >= 0 )
              {
                v32 = 0;
                v28 = 0;
                v30 = 0;
                v31 = 0;
                v14 = v21;
                v21 = 0;
                v29 = v14;
                v26 = 0;
                v27 = &v28;
                v15 = ((__int64 (__fastcall *)(struct IMFTransform *, _QWORD, _QWORD))a1->lpVtbl->ProcessMessage)(
                        a1,
                        0,
                        0);
                v11 = v15;
                if ( v15 >= 0 )
                {
                  v16 = ((__int64 (__fastcall *)(struct IMFTransform *, _QWORD, IMFSample *, _QWORD))a1->lpVtbl->ProcessInput)(
                          a1,
                          0,
                          ppIMFSample,
                          0);
                  v11 = v16;
                  if ( v16 >= 0 )
                  {
                    v17 = ((__int64 (__fastcall *)(struct IMFTransform *, _QWORD, __int64, __int64 *, int *))a1->lpVtbl->ProcessOutput)(
                            a1,
                            0,
                            1,
                            &v28,
                            &v32);
                    v11 = v17;
                    if ( v17 >= 0 )
                    {
                      if ( v29 )
                      {
                        ((void (__fastcall *)(IMFSample *))v29->lpVtbl->Release)(v29);
                        v29 = 0;
                      }
                      if ( v31 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    }
                    else
                    {
                      if ( g_wppLevels )
                        WPP_SF_qd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          48,
                          &WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids,
                          0,
                          v17);
                      if ( v29 )
                      {
                        ((void (__fastcall *)(IMFSample *))v29->lpVtbl->Release)(v29);
                        v29 = 0;
                      }
                      if ( v31 )
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                    }
                  }
                  else
                  {
                    if ( g_wppLevels )
                      WPP_SF_qd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        47,
                        &WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids,
                        0,
                        v16);
                    if ( v29 )
                    {
                      ((void (__fastcall *)(IMFSample *))v29->lpVtbl->Release)(v29);
                      v29 = 0;
                    }
                    if ( v31 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                  }
                }
                else
                {
                  if ( g_wppLevels )
                    WPP_SF_qd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      46,
                      &WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids,
                      0,
                      v15);
                  if ( v29 )
                  {
                    ((void (__fastcall *)(IMFSample *))v29->lpVtbl->Release)(v29);
                    v29 = 0;
                  }
                  if ( v31 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
                }
              }
              else if ( g_wppLevels )
              {
                v12 = 45;
                goto LABEL_6;
              }
            }
            else if ( g_wppLevels )
            {
              v12 = 44;
              goto LABEL_6;
            }
          }
          else if ( g_wppLevels )
          {
            v12 = 43;
            goto LABEL_6;
          }
        }
        else if ( g_wppLevels )
        {
          v12 = 42;
          goto LABEL_6;
        }
      }
      else if ( g_wppLevels )
      {
        v12 = 41;
        goto LABEL_6;
      }
    }
    else if ( g_wppLevels )
    {
      v12 = 40;
      goto LABEL_6;
    }
  }
  else if ( g_wppLevels )
  {
    v12 = 39;
LABEL_6:
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids, 0, v10);
  }
LABEL_58:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v18 = v21;
  if ( v21 )
  {
    v21 = 0;
    ((void (__fastcall *)(IMFSample *))v18->lpVtbl->Release)(v18);
  }
  if ( a1 )
    ((void (__fastcall *)(struct IMFTransform *))a1->lpVtbl->Release)(a1);
  v19 = ppIMFSample;
  if ( ppIMFSample )
  {
    ppIMFSample = 0;
    ((void (__fastcall *)(IMFSample *))v19->lpVtbl->Release)(v19);
  }
  return v11;
}

```

## disassembly

```asm
0x18000f9cc  push    rbp
0x18000f9ce  push    rbx
0x18000f9cf  push    rsi
0x18000f9d0  push    rdi
0x18000f9d1  push    r12
0x18000f9d3  push    r13
0x18000f9d5  push    r14
0x18000f9d7  push    r15
0x18000f9d9  lea     rbp, [rsp-17h]
0x18000f9de  sub     rsp, 98h
0x18000f9e5  mov     r15, r9
0x18000f9e8  mov     r12, r8
0x18000f9eb  mov     r14, rdx
0x18000f9ee  mov     rsi, rcx
0x18000f9f1  xor     r13d, r13d
0x18000f9f4  mov     [rbp+4Fh+ppIMFSample], r13
0x18000f9f8  mov     [rbp+4Fh+var_80], rcx
0x18000f9fc  test    rcx, rcx
0x18000f9ff  jz      short loc_18000FA0E
0x18000fa01  mov     rax, [rcx]
0x18000fa04  mov     rax, [rax+8]
0x18000fa08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa0d  nop
0x18000fa0e  mov     [rbp+4Fh+var_A0], r13
0x18000fa12  mov     rbx, r13
0x18000fa15  mov     [rbp+4Fh+var_88], rbx
0x18000fa19  lea     rcx, [rbp+4Fh+ppIMFSample]
0x18000fa1d  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000fa22  lea     rcx, [rbp+4Fh+ppIMFSample]; ppIMFSample
0x18000fa26  call    cs:__imp_MFCreateSample
0x18000fa2c  mov     edi, eax
0x18000fa2e  test    eax, eax
0x18000fa30  jns     short loc_18000FA67
0x18000fa32  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fa39  jb      loc_18000FDD5
0x18000fa3f  mov     edx, 26h ; '&'
0x18000fa44  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000fa48  xor     r9d, r9d
0x18000fa4b  lea     r8, WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids
0x18000fa52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa59  mov     rcx, [rcx+10h]
0x18000fa5d  call    WPP_SF_qd
0x18000fa62  jmp     loc_18000FDD5
0x18000fa67  mov     rcx, [rbp+4Fh+ppIMFSample]
0x18000fa6b  mov     rax, [rcx]
0x18000fa6e  mov     rdx, r14
0x18000fa71  mov     rax, [rax+150h]
0x18000fa78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa7d  mov     edi, eax
0x18000fa7f  test    eax, eax
0x18000fa81  jns     short loc_18000FA97
0x18000fa83  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fa8a  jb      loc_18000FDD5
0x18000fa90  mov     edx, 27h ; '''
0x18000fa95  jmp     short loc_18000FA44
0x18000fa97  mov     rcx, [rbp+4Fh+ppIMFSample]
0x18000fa9b  mov     rax, [rcx]
0x18000fa9e  xor     edx, edx
0x18000faa0  mov     rax, [rax+120h]
0x18000faa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faac  mov     edi, eax
0x18000faae  test    eax, eax
0x18000fab0  jns     short loc_18000FAC9
0x18000fab2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fab9  jb      loc_18000FDD5
0x18000fabf  mov     edx, 28h ; '('
0x18000fac4  jmp     loc_18000FA44
0x18000fac9  lea     rcx, [rbp+4Fh+var_A0]
0x18000facd  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000fad2  lea     rcx, [rbp+4Fh+var_A0]; ppIMFSample
0x18000fad6  call    cs:__imp_MFCreateSample
0x18000fadc  mov     edi, eax
0x18000fade  test    eax, eax
0x18000fae0  jns     short loc_18000FAF9
0x18000fae2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fae9  jb      loc_18000FDD5
0x18000faef  mov     edx, 29h ; ')'
0x18000faf4  jmp     loc_18000FA44
0x18000faf9  mov     rcx, [rbp+4Fh+var_A0]
0x18000fafd  mov     rax, [rcx]
0x18000fb00  mov     rdx, r15
0x18000fb03  mov     rax, [rax+150h]
0x18000fb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb0f  mov     edi, eax
0x18000fb11  test    eax, eax
0x18000fb13  jns     short loc_18000FB2C
0x18000fb15  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fb1c  jb      loc_18000FDD5
0x18000fb22  mov     edx, 2Ah ; '*'
0x18000fb27  jmp     loc_18000FA44
0x18000fb2c  mov     rcx, [rbp+4Fh+var_A0]
0x18000fb30  mov     rax, [rcx]
0x18000fb33  xor     edx, edx
0x18000fb35  mov     rax, [rax+120h]
0x18000fb3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb41  mov     edi, eax
0x18000fb43  test    eax, eax
0x18000fb45  jns     short loc_18000FB5E
0x18000fb47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fb4e  jb      loc_18000FDD5
0x18000fb54  mov     edx, 2Bh ; '+'
0x18000fb59  jmp     loc_18000FA44
0x18000fb5e  mov     rdx, rsi
0x18000fb61  lea     rcx, [rbp+4Fh+arg_0]
0x18000fb65  call    ??$As@UIMFVideoProcessorControl@@UIMFTransform@@@MF@@YA?AV?$ComPtr@UIMFVideoProcessorControl@@@WRL@Microsoft@@PEAUIMFTransform@@@Z; MF::As<IMFVideoProcessorControl,IMFTransform>(IMFTransform *)
0x18000fb6a  mov     rbx, r13
0x18000fb6d  lea     rcx, [rbp+4Fh+var_90]
0x18000fb71  cmp     rcx, rax
0x18000fb74  jz      short loc_18000FB7C
0x18000fb76  mov     rbx, [rax]
0x18000fb79  mov     [rax], r13
0x18000fb7c  mov     [rbp+4Fh+var_90], r13
0x18000fb80  mov     [rbp+4Fh+var_88], rbx
0x18000fb84  lea     rcx, [rbp+4Fh+var_90]
0x18000fb88  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000fb8d  lea     rcx, [rbp+4Fh+arg_0]
0x18000fb91  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x18000fb96  mov     rax, [rbx]
0x18000fb99  mov     rdx, r12
0x18000fb9c  mov     rcx, rbx
0x18000fb9f  mov     rax, [rax+20h]
0x18000fba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fba8  mov     edi, eax
0x18000fbaa  test    eax, eax
0x18000fbac  jns     short loc_18000FBC5
0x18000fbae  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fbb5  jb      loc_18000FDD5
0x18000fbbb  mov     edx, 2Ch ; ','
0x18000fbc0  jmp     loc_18000FA44
0x18000fbc5  mov     rax, [rbx]
0x18000fbc8  mov     rdx, [rbp+4Fh+arg_20]
0x18000fbcc  mov     rcx, rbx
0x18000fbcf  mov     rax, [rax+28h]
0x18000fbd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbd8  mov     edi, eax
0x18000fbda  test    eax, eax
0x18000fbdc  jns     short loc_18000FBF5
0x18000fbde  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fbe5  jb      loc_18000FDD5
0x18000fbeb  mov     edx, 2Dh ; '-'
0x18000fbf0  jmp     loc_18000FA44
0x18000fbf5  mov     [rbp+4Fh+arg_0], r13d
0x18000fbf9  mov     [rbp+4Fh+var_68], r13
0x18000fbfd  mov     [rbp+4Fh+var_58], r13
0x18000fc01  mov     [rbp+4Fh+var_50], r13
0x18000fc05  mov     rax, [rbp+4Fh+var_A0]
0x18000fc09  mov     [rbp+4Fh+var_A0], r13
0x18000fc0d  mov     [rbp+4Fh+var_60], rax
0x18000fc11  mov     [rbp+4Fh+var_78], r13b
0x18000fc15  lea     rax, [rbp+4Fh+var_68]
0x18000fc19  mov     [rbp+4Fh+var_70], rax
0x18000fc1d  mov     rax, [rsi]
0x18000fc20  xor     r8d, r8d
0x18000fc23  xor     edx, edx
0x18000fc25  mov     rcx, rsi
0x18000fc28  mov     rax, [rax+0B8h]
0x18000fc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc34  mov     edi, eax
0x18000fc36  test    eax, eax
0x18000fc38  jns     short loc_18000FC9B
0x18000fc3a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fc41  jb      short loc_18000FC67
0x18000fc43  mov     edx, 2Eh ; '.'
0x18000fc48  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000fc4c  xor     r9d, r9d
0x18000fc4f  lea     r8, WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids
0x18000fc56  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc5d  mov     rcx, [rcx+10h]
0x18000fc61  call    WPP_SF_qd
0x18000fc66  nop
0x18000fc67  mov     rcx, [rbp+4Fh+var_60]
0x18000fc6b  test    rcx, rcx
0x18000fc6e  jz      short loc_18000FC80
0x18000fc70  mov     rax, [rcx]
0x18000fc73  mov     rax, [rax+10h]
0x18000fc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc7c  mov     [rbp+4Fh+var_60], r13
0x18000fc80  mov     rcx, [rbp+4Fh+var_50]
0x18000fc84  test    rcx, rcx
0x18000fc87  jz      short loc_18000FC96
0x18000fc89  mov     rax, [rcx]
0x18000fc8c  mov     rax, [rax+10h]
0x18000fc90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc95  nop
0x18000fc96  jmp     loc_18000FDD5
0x18000fc9b  mov     rax, [rsi]
0x18000fc9e  xor     r9d, r9d
0x18000fca1  mov     r8, [rbp+4Fh+ppIMFSample]
0x18000fca5  xor     edx, edx
0x18000fca7  mov     rcx, rsi
0x18000fcaa  mov     rax, [rax+0C0h]
0x18000fcb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcb6  mov     edi, eax
0x18000fcb8  test    eax, eax
0x18000fcba  jns     short loc_18000FD1D
0x18000fcbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fcc3  jb      short loc_18000FCE9
0x18000fcc5  mov     edx, 2Fh ; '/'
0x18000fcca  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000fcce  xor     r9d, r9d
0x18000fcd1  lea     r8, WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids
0x18000fcd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcdf  mov     rcx, [rcx+10h]
0x18000fce3  call    WPP_SF_qd
0x18000fce8  nop
0x18000fce9  mov     rcx, [rbp+4Fh+var_60]
0x18000fced  test    rcx, rcx
0x18000fcf0  jz      short loc_18000FD02
0x18000fcf2  mov     rax, [rcx]
0x18000fcf5  mov     rax, [rax+10h]
0x18000fcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fcfe  mov     [rbp+4Fh+var_60], r13
0x18000fd02  mov     rcx, [rbp+4Fh+var_50]
0x18000fd06  test    rcx, rcx
0x18000fd09  jz      short loc_18000FD18
0x18000fd0b  mov     rax, [rcx]
0x18000fd0e  mov     rax, [rax+10h]
0x18000fd12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd17  nop
0x18000fd18  jmp     loc_18000FDD5
0x18000fd1d  mov     rax, [rsi]
0x18000fd20  lea     rcx, [rbp+4Fh+arg_0]
0x18000fd24  mov     [rsp+0D0h+var_B0], rcx
0x18000fd29  lea     r9, [rbp+4Fh+var_68]
0x18000fd2d  xor     edx, edx
0x18000fd2f  lea     r8d, [rdx+1]
0x18000fd33  mov     rcx, rsi
0x18000fd36  mov     rax, [rax+0C8h]
0x18000fd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd42  mov     edi, eax
0x18000fd44  test    eax, eax
0x18000fd46  jns     short loc_18000FDA6
0x18000fd48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000fd4f  jb      short loc_18000FD75
0x18000fd51  mov     edx, 30h ; '0'
0x18000fd56  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000fd5a  xor     r9d, r9d
0x18000fd5d  lea     r8, WPP_6ae81c3b98e1373fe2e131cb6bf703fa_Traceguids
0x18000fd64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd6b  mov     rcx, [rcx+10h]
0x18000fd6f  call    WPP_SF_qd
0x18000fd74  nop
0x18000fd75  mov     rcx, [rbp+4Fh+var_60]
0x18000fd79  test    rcx, rcx
0x18000fd7c  jz      short loc_18000FD8E
0x18000fd7e  mov     rax, [rcx]
0x18000fd81  mov     rax, [rax+10h]
0x18000fd85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8a  mov     [rbp+4Fh+var_60], r13
0x18000fd8e  mov     rcx, [rbp+4Fh+var_50]
0x18000fd92  test    rcx, rcx
0x18000fd95  jz      short loc_18000FDA4
0x18000fd97  mov     rax, [rcx]
0x18000fd9a  mov     rax, [rax+10h]
0x18000fd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fda3  nop
0x18000fda4  jmp     short loc_18000FDD5
0x18000fda6  mov     rcx, [rbp+4Fh+var_60]
0x18000fdaa  test    rcx, rcx
0x18000fdad  jz      short loc_18000FDBF
0x18000fdaf  mov     rax, [rcx]
0x18000fdb2  mov     rax, [rax+10h]
0x18000fdb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdbb  mov     [rbp+4Fh+var_60], r13
0x18000fdbf  mov     rcx, [rbp+4Fh+var_50]
0x18000fdc3  test    rcx, rcx
0x18000fdc6  jz      short loc_18000FDD5
0x18000fdc8  mov     rax, [rcx]
0x18000fdcb  mov     rax, [rax+10h]
0x18000fdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd4  nop
0x18000fdd5  test    rbx, rbx
0x18000fdd8  jz      short loc_18000FDEA
0x18000fdda  mov     rax, [rbx]
0x18000fddd  mov     rcx, rbx
0x18000fde0  mov     rax, [rax+10h]
0x18000fde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fde9  nop
0x18000fdea  mov     rcx, [rbp+4Fh+var_A0]
0x18000fdee  test    rcx, rcx
0x18000fdf1  jz      short loc_18000FE04
0x18000fdf3  mov     [rbp+4Fh+var_A0], r13
0x18000fdf7  mov     rax, [rcx]
0x18000fdfa  mov     rax, [rax+10h]
0x18000fdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe03  nop
0x18000fe04  test    rsi, rsi
0x18000fe07  jz      short loc_18000FE19
0x18000fe09  mov     rax, [rsi]
0x18000fe0c  mov     rcx, rsi
0x18000fe0f  mov     rax, [rax+10h]
0x18000fe13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe18  nop
0x18000fe19  mov     rcx, [rbp+4Fh+ppIMFSample]
0x18000fe1d  test    rcx, rcx
0x18000fe20  jz      short loc_18000FE33
0x18000fe22  mov     [rbp+4Fh+ppIMFSample], r13
0x18000fe26  mov     rax, [rcx]
0x18000fe29  mov     rax, [rax+10h]
0x18000fe2d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
