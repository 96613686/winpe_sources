# FsStMuxFactory::InitializeFactory(ulong,IMFCollection *,IMFAttributes *)

- ea: `0x1800c7fe0`
- end: `0x1800c86e6`
- name: `?InitializeFactory@FsStMuxFactory@@UEAAJKPEAUIMFCollection@@PEAUIMFAttributes@@@Z`
- size: `1798`
- prototype: `__int64 __fastcall(FsStMuxFactory *__hidden this, unsigned int, struct IMFCollection *, struct IMFAttributes *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003e20`
- `0x180009608`
- `0x180018e9c`
- `0x1800c7fe0`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorStream` at `0x1800c8604`
- `MFSENSORGROUP!MFCreateSensorStream` at `0x1800c8604`
- `MFPlat!MFCreateMuxStreamMediaType` at `0x1800c852e`
- `MFPlat!MFCreateMuxStreamMediaType` at `0x1800c852e`
- `MFPlat!MFCreateCollection` at `0x1800c807d`
- `MFPlat!MFCreateCollection` at `0x1800c80ad`
- `MFPlat!MFCreateCollection` at `0x1800c862f`
- `MFPlat!MFCreateCollection` at `0x1800c807d`
- `MFPlat!MFCreateCollection` at `0x1800c80ad`
- `MFPlat!MFCreateCollection` at `0x1800c862f`
- `MFPlat!MFCreateMuxStreamAttributes` at `0x1800c8482`
- `MFPlat!MFCreateMuxStreamAttributes` at `0x1800c8482`

## pseudocode

```c
__int64 __fastcall FsStMuxFactory::InitializeFactory(
        FsStMuxFactory *this,
        __int64 a2,
        struct IMFCollection *a3,
        struct IMFAttributes *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v9; // r12d
  struct IMFCollectionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetElement)(IMFCollection *, DWORD, IUnknown **); // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int i; // r15d
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, _QWORD, __int64 *); // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r9
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v62; // [rsp+30h] [rbp-59h] BYREF
  __int64 (__fastcall ***v63)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-51h] BYREF
  __int64 v64; // [rsp+40h] [rbp-49h] BYREF
  __int64 v65; // [rsp+48h] [rbp-41h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-39h] BYREF
  unsigned int v67; // [rsp+58h] [rbp-31h] BYREF
  __int64 v68; // [rsp+60h] [rbp-29h] BYREF
  __int64 v69; // [rsp+68h] [rbp-21h] BYREF
  __int64 v70; // [rsp+70h] [rbp-19h] BYREF
  unsigned int v71; // [rsp+78h] [rbp-11h] BYREF
  __int64 v72; // [rsp+80h] [rbp-9h] BYREF
  __int64 v73; // [rsp+88h] [rbp-1h] BYREF
  __int128 Buf1; // [rsp+90h] [rbp+7h] BYREF

  v67 = 0;
  v70 = 0;
  v68 = 0;
  v73 = 0;
  v69 = 0;
  v72 = 0;
  if ( !(_DWORD)a2 )
  {
    v6 = -2147024809;
    v7 = -2147024809;
    if ( g_wppLevels )
    {
      v8 = 12;
LABEL_91:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_b2200331732b36aeb792ebd91562d69a_Traceguids, this, v6);
      goto LABEL_92;
    }
    goto LABEL_92;
  }
  if ( a3 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70, a2, a3, a4);
    v6 = MFCreateCollection(&v70);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 14;
        goto LABEL_91;
      }
      goto LABEL_92;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68, a2, a3, a4);
    v6 = MFCreateCollection(&v68);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 15;
        goto LABEL_91;
      }
      goto LABEL_92;
    }
    v6 = ((__int64 (__fastcall *)(struct IMFCollection *, unsigned int *))a3->lpVtbl->GetElementCount)(a3, &v67);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v8 = 16;
        goto LABEL_91;
      }
      goto LABEL_92;
    }
    v9 = 0;
LABEL_17:
    if ( v9 >= v67 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v70 + 24LL))(v70, &v67);
      v7 = v6;
      if ( v6 >= 0 )
      {
        if ( v67 >= 2 )
        {
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69, a2, a3, a4);
          v6 = MFCreateMuxStreamAttributes(v70, &v69);
          v7 = v6;
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(__int64, const IID *, GUID *))(*(_QWORD *)v69 + 192LL))(
                   v69,
                   &MF_DEVICESTREAM_STREAM_CATEGORY,
                   &GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba);
            v7 = v6;
            if ( v6 >= 0 )
            {
              v6 = (*(__int64 (__fastcall **)(__int64, const IID *, _QWORD))(*(_QWORD *)v69 + 168LL))(
                     v69,
                     &MF_DEVICESTREAM_STREAM_ID,
                     0);
              v7 = v6;
              if ( v6 >= 0 )
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72, a2, a3, a4);
                v6 = MFCreateMuxStreamMediaType(v68, &v72);
                v7 = v6;
                if ( v6 >= 0 )
                {
                  v6 = (*(__int64 (__fastcall **)(__int64, const GUID *, void *))(*(_QWORD *)v72 + 192LL))(
                         v72,
                         &MF_MT_SUBTYPE,
                         &MFMultiplexFormat_TimeCorrelation);
                  v7 = v6;
                  if ( v6 >= 0 )
                  {
                    v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 64LL))(v68);
                    v7 = v6;
                    if ( v6 >= 0 )
                    {
                      v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 40LL))(v68, v72);
                      v7 = v6;
                      if ( v6 >= 0 )
                      {
                        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73, a2, a3, a4);
                        v6 = MFCreateSensorStream(0, v69, v68, &v73);
                        v7 = v6;
                        if ( v6 >= 0 )
                        {
                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 56, a2, a3, a4);
                          v6 = MFCreateCollection((char *)this + 56);
                          v7 = v6;
                          if ( v6 >= 0 )
                          {
                            v6 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 7) + 40LL))(
                                   *((_QWORD *)this + 7),
                                   v73);
                            v7 = v6;
                            if ( v6 < 0 && g_wppLevels )
                            {
                              v8 = 37;
                              goto LABEL_91;
                            }
                          }
                          else if ( g_wppLevels )
                          {
                            v8 = 36;
                            goto LABEL_91;
                          }
                        }
                        else if ( g_wppLevels )
                        {
                          v8 = 35;
                          goto LABEL_91;
                        }
                      }
                      else if ( g_wppLevels )
                      {
                        v8 = 34;
                        goto LABEL_91;
                      }
                    }
                    else if ( g_wppLevels )
                    {
                      v8 = 33;
                      goto LABEL_91;
                    }
                  }
                  else if ( g_wppLevels )
                  {
                    v8 = 32;
                    goto LABEL_91;
                  }
                }
                else if ( g_wppLevels )
                {
                  v8 = 31;
                  goto LABEL_91;
                }
              }
              else if ( g_wppLevels )
              {
                v8 = 30;
                goto LABEL_91;
              }
            }
            else if ( g_wppLevels )
            {
              v8 = 29;
              goto LABEL_91;
            }
          }
          else if ( g_wppLevels )
          {
            v8 = 28;
            goto LABEL_91;
          }
        }
        else
        {
          v7 = -1072875819;
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              27,
              &WPP_b2200331732b36aeb792ebd91562d69a_Traceguids,
              this,
              -1072875819);
        }
      }
      else if ( g_wppLevels )
      {
        v8 = 26;
        goto LABEL_91;
      }
      goto LABEL_92;
    }
    lpVtbl = a3->lpVtbl;
    v63 = 0;
    v62 = 0;
    v71 = 0;
    GetElement = lpVtbl->GetElement;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63, a2, a3, a4);
    v12 = ((__int64 (__fastcall *)(struct IMFCollection *, _QWORD, _QWORD))GetElement)(a3, v9, &v63);
    v7 = v12;
    if ( v12 < 0 )
    {
      if ( g_wppLevels )
      {
        v45 = 17;
        goto LABEL_53;
      }
    }
    else
    {
      v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v63;
      v17 = **v63;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62, v13, v14, v15);
      v12 = v17(v16, &GUID_fb9f48f2_2a18_4e28_9730_786f30f04dc4, &v62);
      v7 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v45 = 18;
          goto LABEL_53;
        }
      }
      else
      {
        v12 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v62 + 64LL))(v62, 2, &v71);
        v7 = v12;
        if ( v12 >= 0 )
        {
          for ( i = 0; ; ++i )
          {
            if ( i >= v71 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62, v13, v14, v15);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63, v35, v36, v37);
              ++v9;
              goto LABEL_17;
            }
            v64 = 0;
            v66 = 0;
            v65 = 0;
            v19 = v62;
            Buf1 = 0;
            v20 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v62 + 72LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v13, v14, v15);
            v21 = v20(v19, 2, i, &v66);
            v7 = v21;
            if ( v21 < 0 )
              break;
            v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
            v26 = **v66;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64, v22, v23, v24);
            v21 = v26(v25, &GUID_e9a42171_c56e_498a_8b39_eda5a070b7fc, &v64);
            v7 = v21;
            if ( v21 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_46;
              v38 = 21;
              goto LABEL_45;
            }
            v21 = (*(__int64 (__fastcall **)(__int64, const IID *, __int128 *))(*(_QWORD *)v64 + 80LL))(
                    v64,
                    &MF_DEVICESTREAM_STREAM_CATEGORY,
                    &Buf1);
            v7 = v21;
            if ( v21 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_46;
              v38 = 22;
              goto LABEL_45;
            }
            if ( !memcmp_0(&Buf1, &GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba, 0x10u)
              || !memcmp_0(&Buf1, &GUID_fb6c4282_0353_11d1_905f_0000c0cc16ba, 0x10u) )
            {
              v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 40LL))(v70, v64);
              v7 = v21;
              if ( v21 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_46;
                v38 = 23;
                goto LABEL_45;
              }
              v27 = v64;
              v28 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v64 + 272LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65, v22, v23, v24);
              v21 = v28(v27, 0, &v65);
              v7 = v21;
              if ( v21 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_46;
                v38 = 24;
                goto LABEL_45;
              }
              v21 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 40LL))(v68, v65);
              v7 = v21;
              if ( v21 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_46;
                v38 = 25;
                goto LABEL_45;
              }
            }
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65, v22, v23, v24);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v29, v30, v31);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64, v32, v33, v34);
          }
          if ( !g_wppLevels )
            goto LABEL_46;
          v38 = 20;
LABEL_45:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v38,
            &WPP_b2200331732b36aeb792ebd91562d69a_Traceguids,
            this,
            v21);
LABEL_46:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v65, v22, v23, v24);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v39, v40, v41);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v64, v42, v43, v44);
          goto LABEL_54;
        }
        if ( g_wppLevels )
        {
          v45 = 19;
LABEL_53:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v45,
            &WPP_b2200331732b36aeb792ebd91562d69a_Traceguids,
            this,
            v12);
        }
      }
    }
LABEL_54:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v62, v13, v14, v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v63, v46, v47, v48);
    goto LABEL_92;
  }
  v6 = -2147024809;
  v7 = -2147024809;
  if ( g_wppLevels )
  {
    v8 = 13;
    goto LABEL_91;
  }
LABEL_92:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v72, a2, a3, a4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v69, v49, v50, v51);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73, v52, v53, v54);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v68, v55, v56, v57);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70, v58, v59, v60);
  return v7;
}

```

## disassembly

```asm
0x1800c7fe0  mov     [rsp-8+arg_8], rbx
0x1800c7fe5  push    rbp
0x1800c7fe6  push    rsi
0x1800c7fe7  push    rdi
0x1800c7fe8  push    r12
0x1800c7fea  push    r13
0x1800c7fec  push    r14
0x1800c7fee  push    r15
0x1800c7ff0  lea     rbp, [rsp-27h]
0x1800c7ff5  sub     rsp, 0B0h
0x1800c7ffc  mov     rax, cs:__security_cookie
0x1800c8003  xor     rax, rsp
0x1800c8006  mov     [rbp+57h+var_40], rax
0x1800c800a  xor     edi, edi
0x1800c800c  mov     r14, r8
0x1800c800f  mov     rsi, rcx
0x1800c8012  mov     [rbp+57h+var_88], edi
0x1800c8015  mov     [rbp+57h+var_70], rdi
0x1800c8019  mov     [rbp+57h+var_80], rdi
0x1800c801d  lea     r13d, [rdi+1]
0x1800c8021  mov     [rbp+57h+var_58], rdi
0x1800c8025  mov     [rbp+57h+var_78], rdi
0x1800c8029  mov     [rbp+57h+var_60], rdi
0x1800c802d  cmp     edx, r13d
0x1800c8030  jnb     short loc_1800C804E
0x1800c8032  mov     eax, 80070057h
0x1800c8037  mov     ebx, eax
0x1800c8039  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8040  jb      loc_1800C8690
0x1800c8046  lea     edx, [rdi+0Ch]
0x1800c8049  jmp     loc_1800C8672
0x1800c804e  test    r14, r14
0x1800c8051  jnz     short loc_1800C8070
0x1800c8053  mov     eax, 80070057h
0x1800c8058  mov     ebx, eax
0x1800c805a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8061  jb      loc_1800C8690
0x1800c8067  lea     edx, [r14+0Dh]
0x1800c806b  jmp     loc_1800C8672
0x1800c8070  lea     rcx, [rbp+57h+var_70]
0x1800c8074  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8079  lea     rcx, [rbp+57h+var_70]
0x1800c807d  call    cs:__imp_MFCreateCollection
0x1800c8083  mov     ebx, eax
0x1800c8085  test    eax, eax
0x1800c8087  jns     short loc_1800C80A0
0x1800c8089  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8090  jb      loc_1800C8690
0x1800c8096  mov     edx, 0Eh
0x1800c809b  jmp     loc_1800C8672
0x1800c80a0  lea     rcx, [rbp+57h+var_80]
0x1800c80a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c80a9  lea     rcx, [rbp+57h+var_80]
0x1800c80ad  call    cs:__imp_MFCreateCollection
0x1800c80b3  mov     ebx, eax
0x1800c80b5  test    eax, eax
0x1800c80b7  jns     short loc_1800C80D0
0x1800c80b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c80c0  jb      loc_1800C8690
0x1800c80c6  mov     edx, 0Fh
0x1800c80cb  jmp     loc_1800C8672
0x1800c80d0  mov     rax, [r14]
0x1800c80d3  lea     rdx, [rbp+57h+var_88]
0x1800c80d7  mov     rcx, r14
0x1800c80da  mov     rax, [rax+18h]
0x1800c80de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c80e3  mov     ebx, eax
0x1800c80e5  test    eax, eax
0x1800c80e7  jns     short loc_1800C8100
0x1800c80e9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c80f0  jb      loc_1800C8690
0x1800c80f6  mov     edx, 10h
0x1800c80fb  jmp     loc_1800C8672
0x1800c8100  mov     r12d, edi
0x1800c8103  cmp     r12d, [rbp+57h+var_88]
0x1800c8107  jnb     loc_1800C841A
0x1800c810d  mov     rax, [r14]
0x1800c8110  lea     rcx, [rbp+57h+var_A8]
0x1800c8114  mov     [rbp+57h+var_A8], rdi
0x1800c8118  mov     [rbp+57h+var_B0], rdi
0x1800c811c  mov     [rbp+57h+var_68], edi
0x1800c811f  mov     rbx, [rax+20h]
0x1800c8123  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8128  lea     r8, [rbp+57h+var_A8]
0x1800c812c  mov     edx, r12d
0x1800c812f  mov     rcx, r14
0x1800c8132  mov     rax, rbx
0x1800c8135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c813a  mov     ebx, eax
0x1800c813c  test    eax, eax
0x1800c813e  js      loc_1800C83D7
0x1800c8144  mov     rdi, [rbp+57h+var_A8]
0x1800c8148  lea     rcx, [rbp+57h+var_B0]
0x1800c814c  mov     rax, [rdi]
0x1800c814f  mov     rbx, [rax]
0x1800c8152  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8157  lea     r8, [rbp+57h+var_B0]
0x1800c815b  mov     rcx, rdi
0x1800c815e  lea     rdx, _GUID_fb9f48f2_2a18_4e28_9730_786f30f04dc4
0x1800c8165  mov     rax, rbx
0x1800c8168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c816d  xor     edi, edi
0x1800c816f  mov     ebx, eax
0x1800c8171  test    eax, eax
0x1800c8173  js      loc_1800C83C7
0x1800c8179  mov     rcx, [rbp+57h+var_B0]
0x1800c817d  lea     r8, [rbp+57h+var_68]
0x1800c8181  lea     edx, [rdi+2]
0x1800c8184  mov     rax, [rcx]
0x1800c8187  mov     rax, [rax+40h]
0x1800c818b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8190  mov     ebx, eax
0x1800c8192  test    eax, eax
0x1800c8194  js      loc_1800C83B7
0x1800c819a  mov     r15d, edi
0x1800c819d  cmp     r15d, [rbp+57h+var_68]
0x1800c81a1  jnb     loc_1800C8304
0x1800c81a7  mov     [rbp+57h+var_A0], rdi
0x1800c81ab  lea     rcx, [rbp+57h+var_90]
0x1800c81af  mov     [rbp+57h+var_90], rdi
0x1800c81b3  xorps   xmm0, xmm0
0x1800c81b6  mov     [rbp+57h+var_98], rdi
0x1800c81ba  mov     rdi, [rbp+57h+var_B0]
0x1800c81be  movups  [rbp+57h+Buf1], xmm0
0x1800c81c2  mov     rax, [rdi]
0x1800c81c5  mov     rbx, [rax+48h]
0x1800c81c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c81ce  lea     r9, [rbp+57h+var_90]
0x1800c81d2  mov     r8d, r15d
0x1800c81d5  mov     edx, 2
0x1800c81da  mov     rcx, rdi
0x1800c81dd  mov     rax, rbx
0x1800c81e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c81e5  mov     ebx, eax
0x1800c81e7  test    eax, eax
0x1800c81e9  js      loc_1800C836E
0x1800c81ef  mov     rdi, [rbp+57h+var_90]
0x1800c81f3  lea     rcx, [rbp+57h+var_A0]
0x1800c81f7  mov     rax, [rdi]
0x1800c81fa  mov     rbx, [rax]
0x1800c81fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8202  lea     r8, [rbp+57h+var_A0]
0x1800c8206  mov     rcx, rdi
0x1800c8209  lea     rdx, _GUID_e9a42171_c56e_498a_8b39_eda5a070b7fc
0x1800c8210  mov     rax, rbx
0x1800c8213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8218  xor     edi, edi
0x1800c821a  mov     ebx, eax
0x1800c821c  test    eax, eax
0x1800c821e  js      loc_1800C835E
0x1800c8224  mov     rcx, [rbp+57h+var_A0]
0x1800c8228  lea     r8, [rbp+57h+Buf1]
0x1800c822c  lea     rdx, MF_DEVICESTREAM_STREAM_CATEGORY
0x1800c8233  mov     rax, [rcx]
0x1800c8236  mov     rax, [rax+50h]
0x1800c823a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c823f  mov     ebx, eax
0x1800c8241  test    eax, eax
0x1800c8243  js      loc_1800C834E
0x1800c8249  lea     r8d, [rdi+10h]; Size
0x1800c824d  lea     rdx, _GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba; Buf2
0x1800c8254  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800c8258  call    memcmp_0
0x1800c825d  test    eax, eax
0x1800c825f  jz      short loc_1800C8279
0x1800c8261  lea     r8d, [rdi+10h]; Size
0x1800c8265  lea     rdx, _GUID_fb6c4282_0353_11d1_905f_0000c0cc16ba; Buf2
0x1800c826c  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800c8270  call    memcmp_0
0x1800c8275  test    eax, eax
0x1800c8277  jnz     short loc_1800C82E1
0x1800c8279  mov     rcx, [rbp+57h+var_70]
0x1800c827d  mov     rdx, [rbp+57h+var_A0]
0x1800c8281  mov     rax, [rcx]
0x1800c8284  mov     rax, [rax+28h]
0x1800c8288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c828d  mov     ebx, eax
0x1800c828f  test    eax, eax
0x1800c8291  js      loc_1800C833E
0x1800c8297  mov     rdi, [rbp+57h+var_A0]
0x1800c829b  lea     rcx, [rbp+57h+var_98]
0x1800c829f  mov     rax, [rdi]
0x1800c82a2  mov     rbx, [rax+110h]
0x1800c82a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c82ae  lea     r8, [rbp+57h+var_98]
0x1800c82b2  xor     edx, edx
0x1800c82b4  mov     rcx, rdi
0x1800c82b7  mov     rax, rbx
0x1800c82ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c82bf  xor     edi, edi
0x1800c82c1  mov     ebx, eax
0x1800c82c3  test    eax, eax
0x1800c82c5  js      short loc_1800C832E
0x1800c82c7  mov     rcx, [rbp+57h+var_80]
0x1800c82cb  mov     rdx, [rbp+57h+var_98]
0x1800c82cf  mov     rax, [rcx]
0x1800c82d2  mov     rax, [rax+28h]
0x1800c82d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c82db  mov     ebx, eax
0x1800c82dd  test    eax, eax
0x1800c82df  js      short loc_1800C831E
0x1800c82e1  lea     rcx, [rbp+57h+var_98]
0x1800c82e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c82ea  lea     rcx, [rbp+57h+var_90]
0x1800c82ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c82f3  lea     rcx, [rbp+57h+var_A0]
0x1800c82f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c82fc  add     r15d, r13d
0x1800c82ff  jmp     loc_1800C819D
0x1800c8304  lea     rcx, [rbp+57h+var_B0]
0x1800c8308  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c830d  lea     rcx, [rbp+57h+var_A8]
0x1800c8311  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8316  add     r12d, r13d
0x1800c8319  jmp     loc_1800C8103
0x1800c831e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8325  jb      short loc_1800C839A
0x1800c8327  mov     edx, 19h
0x1800c832c  jmp     short loc_1800C837C
0x1800c832e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8335  jb      short loc_1800C839A
0x1800c8337  mov     edx, 18h
0x1800c833c  jmp     short loc_1800C837C
0x1800c833e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8345  jb      short loc_1800C839A
0x1800c8347  mov     edx, 17h
0x1800c834c  jmp     short loc_1800C837C
0x1800c834e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8355  jb      short loc_1800C839A
0x1800c8357  mov     edx, 16h
0x1800c835c  jmp     short loc_1800C837C
0x1800c835e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8365  jb      short loc_1800C839A
0x1800c8367  mov     edx, 15h
0x1800c836c  jmp     short loc_1800C837C
0x1800c836e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c8375  jb      short loc_1800C839A
0x1800c8377  mov     edx, 14h
0x1800c837c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8383  lea     r8, WPP_b2200331732b36aeb792ebd91562d69a_Traceguids
0x1800c838a  mov     r9, rsi
0x1800c838d  mov     [rsp+0E0h+var_C0], eax
0x1800c8391  mov     rcx, [rcx+10h]
0x1800c8395  call    WPP_SF_qD
0x1800c839a  lea     rcx, [rbp+57h+var_98]
0x1800c839e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c83a3  lea     rcx, [rbp+57h+var_90]
0x1800c83a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c83ac  lea     rcx, [rbp+57h+var_A0]
0x1800c83b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c83b5  jmp     short loc_1800C8403
0x1800c83b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c83be  jb      short loc_1800C8403
0x1800c83c0  mov     edx, 13h
0x1800c83c5  jmp     short loc_1800C83E5
0x1800c83c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c83ce  jb      short loc_1800C8403
0x1800c83d0  mov     edx, 12h
0x1800c83d5  jmp     short loc_1800C83E5
0x1800c83d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c83de  jb      short loc_1800C8403
0x1800c83e0  mov     edx, 11h
0x1800c83e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c83ec  lea     r8, WPP_b2200331732b36aeb792ebd91562d69a_Traceguids
0x1800c83f3  mov     r9, rsi
0x1800c83f6  mov     [rsp+0E0h+var_C0], eax
0x1800c83fa  mov     rcx, [rcx+10h]
0x1800c83fe  call    WPP_SF_qD
0x1800c8403  lea     rcx, [rbp+57h+var_B0]
0x1800c8407  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c840c  lea     rcx, [rbp+57h+var_A8]
0x1800c8410  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c8415  jmp     loc_1800C8690
0x1800c841a  mov     rcx, [rbp+57h+var_70]
0x1800c841e  lea     rdx, [rbp+57h+var_88]
0x1800c8422  mov     rax, [rcx]
0x1800c8425  mov     rax, [rax+18h]
0x1800c8429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c842e  mov     ebx, eax
0x1800c8430  test    eax, eax
0x1800c8432  jns     short loc_1800C844B
0x1800c8434  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c843b  jb      loc_1800C8690
0x1800c8441  mov     edx, 1Ah
0x1800c8446  jmp     loc_1800C8672
0x1800c844b  cmp     [rbp+57h+var_88], 2
0x1800c844f  jnb     short loc_1800C8471
0x1800c8451  mov     ebx, 0C00D36D5h
0x1800c8456  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800c845d  jb      loc_1800C8690
0x1800c8463  mov     edx, 1Bh
0x1800c8468  mov     [rsp+0E0h+var_C0], ebx
0x1800c846c  jmp     loc_1800C8676
0x1800c8471  lea     rcx, [rbp+57h+var_78]
0x1800c8475  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c847a  mov     rcx, [rbp+57h+var_70]
0x1800c847e  lea     rdx, [rbp+57h+var_78]
0x1800c8482  call    cs:__imp_MFCreateMuxStreamAttributes
0x1800c8488  mov     ebx, eax
0x1800c848a  test    eax, eax
  ... truncated ...
```
