# AuthHostWebInstance::DecodeAndMarshalImage(uchar *,uint)

- ea: `0x140008b30`
- end: `0x14000913e`
- name: `?DecodeAndMarshalImage@AuthHostWebInstance@@AEAAJPEAEI@Z`
- size: `1550`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000bb4c`

## callees

- `0x140002c98`
- `0x140003a8c`
- `0x140006a24`
- `0x140008624`
- `0x140008b30`
- `0x14000a858`
- `0x140012f60`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140008bbf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140008bbf`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::DecodeAndMarshalImage(
        AuthHostWebInstance *this,
        unsigned __int8 *a2,
        unsigned int a3)
{
  HRESULT v6; // ebx
  _QWORD *v7; // rax
  __int64 v8; // rdx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, __int64 *); // rbx
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, __int64, _QWORD, _QWORD, __int64 *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, __int64, _QWORD, __int64 *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64, __int64 *); // rbx
  __int64 v19; // rdi
  unsigned int v21; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-75h] BYREF
  __int64 v23; // [rsp+38h] [rbp-71h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-69h] BYREF
  int v25; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v26; // [rsp+4Ch] [rbp-5Dh] BYREF
  __int64 v27; // [rsp+50h] [rbp-59h] BYREF
  struct Windows::Storage::Streams::IBuffer *v28; // [rsp+58h] [rbp-51h] BYREF
  __int64 v29; // [rsp+60h] [rbp-49h] BYREF
  __int64 v30; // [rsp+68h] [rbp-41h] BYREF
  __int64 v31; // [rsp+70h] [rbp-39h] BYREF
  int v32; // [rsp+78h] [rbp-31h] BYREF
  int v33; // [rsp+80h] [rbp-29h] BYREF
  __int64 v34; // [rsp+88h] [rbp-21h] BYREF
  __int64 v35; // [rsp+90h] [rbp-19h] BYREF
  struct _GUID v36; // [rsp+A0h] [rbp-9h] BYREF
  struct _GUID v37; // [rsp+B0h] [rbp+7h] BYREF

  v28 = 0;
  ppv = 0;
  v27 = 0;
  v31 = 0;
  v30 = 0;
  v23 = 0;
  v29 = 0;
  v34 = 0;
  v25 = 0;
  v37 = 0;
  v22 = 0;
  v21 = 0;
  v26 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v6 = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  if ( v6 >= 0 )
  {
    v9 = ppv;
    v10 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 112LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v6 = v10(v9, &v27);
    if ( v6 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, _QWORD))(*(_QWORD *)v27 + 128LL))(v27, a2, a3);
      if ( v6 >= 0 )
      {
        v11 = ppv;
        v12 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        v6 = v12(v11, v27, 0, 0, &v31);
        if ( v6 >= 0 )
        {
          v13 = v31;
          v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 104LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          v6 = v14(v13, 0, &v30);
          if ( v6 >= 0 )
          {
            v15 = ppv;
            v16 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 144LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
            v6 = v16(v15, v30, 0, &v29);
            if ( v6 >= 0 )
            {
              v17 = v29;
              v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v29 + 64LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
              v6 = v18(v17, 0, 1, &v23);
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v23 + 48LL))(v23, &v37);
                if ( v6 >= 0 )
                {
                  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(*(_QWORD *)v23 + 24LL))(
                         v23,
                         &v22,
                         &v21);
                  if ( v6 >= 0 )
                  {
                    if ( v22 > 0x400 || v21 > 0x400 )
                    {
                      v6 = -2147024883;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                      {
                        WPP_SF_Dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 7),
                          81,
                          &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
                      }
                    }
                    else
                    {
                      v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 32LL))(v23, &v26);
                      if ( v6 >= 0 )
                      {
                        v6 = (*(__int64 (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v23 + 40LL))(
                               v23,
                               &v25,
                               &v34);
                        if ( v6 >= 0 )
                        {
                          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
                          v35 = v34;
                          v32 = v25;
                          v33 = v25;
                          v28 = 0;
                          Microsoft::WRL::Details::Make<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>,unsigned int &,unsigned int &,unsigned char * &,_lambda_8fcabb03306c9f8765c03020018d7da6_ &>(
                            &v36,
                            &v33,
                            &v32,
                            &v35);
                          v19 = *(_QWORD *)&v36.Data1;
                          if ( *(_QWORD *)&v36.Data1 )
                            v6 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct Windows::Storage::Streams::IBuffer **))&v36.Data1)(
                                   *(_QWORD *)&v36.Data1,
                                   &GUID_905a0fe0_bc53_11df_8c49_001e4fc686da,
                                   &v28);
                          else
                            v6 = -2147024882;
                          if ( v19 )
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
                          if ( v6 < 0
                            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 7),
                              84,
                              &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids,
                              (unsigned int)v6);
                          }
                          v36 = v37;
                          AuthHostWebInstance::OnLogoDownloaded(this, v22, v21, &v36, v26, v28);
                        }
                        else
                        {
                          v7 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                          {
                            v8 = 83;
                            goto LABEL_6;
                          }
                        }
                      }
                      else
                      {
                        v7 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                        {
                          v8 = 82;
                          goto LABEL_6;
                        }
                      }
                    }
                  }
                  else
                  {
                    v7 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                    {
                      v8 = 80;
                      goto LABEL_6;
                    }
                  }
                }
                else
                {
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                  {
                    v8 = 79;
                    goto LABEL_6;
                  }
                }
              }
              else
              {
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
                {
                  v8 = 78;
                  goto LABEL_6;
                }
              }
            }
            else
            {
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
              {
                v8 = 77;
                goto LABEL_6;
              }
            }
          }
          else
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
            {
              v8 = 76;
              goto LABEL_6;
            }
          }
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
          {
            v8 = 75;
            goto LABEL_6;
          }
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v8 = 74;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        v8 = 73;
        goto LABEL_6;
      }
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      v8 = 72;
LABEL_6:
      WPP_SF_d(v7[7], v8, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids, (unsigned int)v6);
    }
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140008b30  push    rbp
0x140008b32  push    rbx
0x140008b33  push    rsi
0x140008b34  push    rdi
0x140008b35  push    r12
0x140008b37  push    r14
0x140008b39  push    r15
0x140008b3b  lea     rbp, [rsp-27h]
0x140008b40  sub     rsp, 0D0h
0x140008b47  mov     rax, cs:__security_cookie
0x140008b4e  xor     rax, rsp
0x140008b51  mov     [rbp+57h+var_40], rax
0x140008b55  mov     r14d, r8d
0x140008b58  mov     rsi, rdx
0x140008b5b  mov     r15, rcx
0x140008b5e  xor     r12d, r12d
0x140008b61  mov     [rbp+57h+var_A8], r12
0x140008b65  mov     [rbp+57h+var_C0], r12
0x140008b69  mov     [rbp+57h+var_B0], r12
0x140008b6d  mov     [rbp+57h+var_90], r12
0x140008b71  mov     [rbp+57h+var_98], r12
0x140008b75  mov     [rbp+57h+var_C8], r12
0x140008b79  mov     [rbp+57h+var_A0], r12
0x140008b7d  mov     [rbp+57h+var_78], r12
0x140008b81  mov     [rbp+57h+var_B8], r12d
0x140008b85  xorps   xmm0, xmm0
0x140008b88  movups  [rbp+57h+var_50], xmm0
0x140008b8c  mov     [rbp+57h+var_CC], r12d
0x140008b90  mov     [rbp+57h+var_D0], r12d
0x140008b94  mov     [rbp+57h+var_B4], r12d
0x140008b98  lea     rcx, [rbp+57h+var_C0]
0x140008b9c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008ba1  lea     rax, [rbp+57h+var_C0]
0x140008ba5  mov     [rsp+100h+ppv], rax; ppv
0x140008baa  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x140008bb1  xor     edx, edx; pUnkOuter
0x140008bb3  lea     r8d, [r12+1]; dwClsContext
0x140008bb8  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x140008bbf  call    cs:__imp_CoCreateInstance
0x140008bc5  mov     ebx, eax
0x140008bc7  test    eax, eax
0x140008bc9  jns     short loc_140008C13
0x140008bcb  lea     rcx, WPP_GLOBAL_Control
0x140008bd2  mov     rax, cs:WPP_GLOBAL_Control
0x140008bd9  cmp     rax, rcx
0x140008bdc  jz      loc_1400090D9
0x140008be2  test    byte ptr [rax+44h], 4
0x140008be6  jz      loc_1400090D9
0x140008bec  cmp     byte ptr [rax+41h], 2
0x140008bf0  jb      loc_1400090D9
0x140008bf6  lea     edx, [r12+48h]
0x140008bfb  mov     r9d, ebx
0x140008bfe  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x140008c05  mov     rcx, [rax+38h]
0x140008c09  call    WPP_SF_d
0x140008c0e  jmp     loc_1400090D9
0x140008c13  mov     rdi, [rbp+57h+var_C0]
0x140008c17  mov     rax, [rdi]
0x140008c1a  mov     rbx, [rax+70h]
0x140008c1e  lea     rcx, [rbp+57h+var_B0]
0x140008c22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008c27  lea     rdx, [rbp+57h+var_B0]
0x140008c2b  mov     rcx, rdi
0x140008c2e  mov     rax, rbx
0x140008c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c36  mov     ebx, eax
0x140008c38  test    eax, eax
0x140008c3a  jns     short loc_140008C6E
0x140008c3c  lea     rcx, WPP_GLOBAL_Control
0x140008c43  mov     rax, cs:WPP_GLOBAL_Control
0x140008c4a  cmp     rax, rcx
0x140008c4d  jz      loc_1400090D9
0x140008c53  test    byte ptr [rax+44h], 4
0x140008c57  jz      loc_1400090D9
0x140008c5d  cmp     byte ptr [rax+41h], 2
0x140008c61  jb      loc_1400090D9
0x140008c67  mov     edx, 49h ; 'I'
0x140008c6c  jmp     short loc_140008BFB
0x140008c6e  mov     rcx, [rbp+57h+var_B0]
0x140008c72  mov     rax, [rcx]
0x140008c75  mov     r8d, r14d
0x140008c78  mov     rdx, rsi
0x140008c7b  mov     rax, [rax+80h]
0x140008c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c87  mov     ebx, eax
0x140008c89  test    eax, eax
0x140008c8b  jns     short loc_140008CC2
0x140008c8d  lea     rcx, WPP_GLOBAL_Control
0x140008c94  mov     rax, cs:WPP_GLOBAL_Control
0x140008c9b  cmp     rax, rcx
0x140008c9e  jz      loc_1400090D9
0x140008ca4  test    byte ptr [rax+44h], 4
0x140008ca8  jz      loc_1400090D9
0x140008cae  cmp     byte ptr [rax+41h], 2
0x140008cb2  jb      loc_1400090D9
0x140008cb8  mov     edx, 4Ah ; 'J'
0x140008cbd  jmp     loc_140008BFB
0x140008cc2  mov     rdi, [rbp+57h+var_C0]
0x140008cc6  mov     rax, [rdi]
0x140008cc9  mov     rbx, [rax+20h]
0x140008ccd  lea     rcx, [rbp+57h+var_90]
0x140008cd1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008cd6  lea     rax, [rbp+57h+var_90]
0x140008cda  mov     [rsp+100h+ppv], rax
0x140008cdf  xor     r9d, r9d
0x140008ce2  xor     r8d, r8d
0x140008ce5  mov     rdx, [rbp+57h+var_B0]
0x140008ce9  mov     rcx, rdi
0x140008cec  mov     rax, rbx
0x140008cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008cf4  mov     ebx, eax
0x140008cf6  test    eax, eax
0x140008cf8  jns     short loc_140008D2F
0x140008cfa  lea     rcx, WPP_GLOBAL_Control
0x140008d01  mov     rax, cs:WPP_GLOBAL_Control
0x140008d08  cmp     rax, rcx
0x140008d0b  jz      loc_1400090D9
0x140008d11  test    byte ptr [rax+44h], 4
0x140008d15  jz      loc_1400090D9
0x140008d1b  cmp     byte ptr [rax+41h], 2
0x140008d1f  jb      loc_1400090D9
0x140008d25  mov     edx, 4Bh ; 'K'
0x140008d2a  jmp     loc_140008BFB
0x140008d2f  mov     rdi, [rbp+57h+var_90]
0x140008d33  mov     rax, [rdi]
0x140008d36  mov     rbx, [rax+68h]
0x140008d3a  lea     rcx, [rbp+57h+var_98]
0x140008d3e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008d43  lea     r8, [rbp+57h+var_98]
0x140008d47  xor     edx, edx
0x140008d49  mov     rcx, rdi
0x140008d4c  mov     rax, rbx
0x140008d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d54  mov     ebx, eax
0x140008d56  test    eax, eax
0x140008d58  jns     short loc_140008D8F
0x140008d5a  lea     rcx, WPP_GLOBAL_Control
0x140008d61  mov     rax, cs:WPP_GLOBAL_Control
0x140008d68  cmp     rax, rcx
0x140008d6b  jz      loc_1400090D9
0x140008d71  test    byte ptr [rax+44h], 4
0x140008d75  jz      loc_1400090D9
0x140008d7b  cmp     byte ptr [rax+41h], 2
0x140008d7f  jb      loc_1400090D9
0x140008d85  mov     edx, 4Ch ; 'L'
0x140008d8a  jmp     loc_140008BFB
0x140008d8f  mov     rdi, [rbp+57h+var_C0]
0x140008d93  mov     rax, [rdi]
0x140008d96  mov     rbx, [rax+90h]
0x140008d9d  lea     rcx, [rbp+57h+var_A0]
0x140008da1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008da6  lea     r9, [rbp+57h+var_A0]
0x140008daa  xor     r8d, r8d
0x140008dad  mov     rdx, [rbp+57h+var_98]
0x140008db1  mov     rcx, rdi
0x140008db4  mov     rax, rbx
0x140008db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008dbc  mov     ebx, eax
0x140008dbe  test    eax, eax
0x140008dc0  jns     short loc_140008DF7
0x140008dc2  lea     rcx, WPP_GLOBAL_Control
0x140008dc9  mov     rax, cs:WPP_GLOBAL_Control
0x140008dd0  cmp     rax, rcx
0x140008dd3  jz      loc_1400090D9
0x140008dd9  test    byte ptr [rax+44h], 4
0x140008ddd  jz      loc_1400090D9
0x140008de3  cmp     byte ptr [rax+41h], 2
0x140008de7  jb      loc_1400090D9
0x140008ded  mov     edx, 4Dh ; 'M'
0x140008df2  jmp     loc_140008BFB
0x140008df7  mov     rdi, [rbp+57h+var_A0]
0x140008dfb  mov     rax, [rdi]
0x140008dfe  mov     rbx, [rax+40h]
0x140008e02  lea     rcx, [rbp+57h+var_C8]
0x140008e06  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008e0b  lea     r9, [rbp+57h+var_C8]
0x140008e0f  xor     edx, edx
0x140008e11  lea     r8d, [rdx+1]
0x140008e15  mov     rcx, rdi
0x140008e18  mov     rax, rbx
0x140008e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e20  mov     ebx, eax
0x140008e22  test    eax, eax
0x140008e24  jns     short loc_140008E5B
0x140008e26  lea     rcx, WPP_GLOBAL_Control
0x140008e2d  mov     rax, cs:WPP_GLOBAL_Control
0x140008e34  cmp     rax, rcx
0x140008e37  jz      loc_1400090D9
0x140008e3d  test    byte ptr [rax+44h], 4
0x140008e41  jz      loc_1400090D9
0x140008e47  cmp     byte ptr [rax+41h], 2
0x140008e4b  jb      loc_1400090D9
0x140008e51  mov     edx, 4Eh ; 'N'
0x140008e56  jmp     loc_140008BFB
0x140008e5b  mov     rcx, [rbp+57h+var_C8]
0x140008e5f  mov     rax, [rcx]
0x140008e62  lea     rdx, [rbp+57h+var_50]
0x140008e66  mov     rax, [rax+30h]
0x140008e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e6f  mov     ebx, eax
0x140008e71  test    eax, eax
0x140008e73  jns     short loc_140008EAA
0x140008e75  lea     rcx, WPP_GLOBAL_Control
0x140008e7c  mov     rax, cs:WPP_GLOBAL_Control
0x140008e83  cmp     rax, rcx
0x140008e86  jz      loc_1400090D9
0x140008e8c  test    byte ptr [rax+44h], 4
0x140008e90  jz      loc_1400090D9
0x140008e96  cmp     byte ptr [rax+41h], 2
0x140008e9a  jb      loc_1400090D9
0x140008ea0  mov     edx, 4Fh ; 'O'
0x140008ea5  jmp     loc_140008BFB
0x140008eaa  mov     rcx, [rbp+57h+var_C8]
0x140008eae  mov     rax, [rcx]
0x140008eb1  lea     r8, [rbp+57h+var_D0]
0x140008eb5  lea     rdx, [rbp+57h+var_CC]
0x140008eb9  mov     rax, [rax+18h]
0x140008ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ec2  mov     ebx, eax
0x140008ec4  test    eax, eax
0x140008ec6  jns     short loc_140008EFD
0x140008ec8  lea     rcx, WPP_GLOBAL_Control
0x140008ecf  mov     rax, cs:WPP_GLOBAL_Control
0x140008ed6  cmp     rax, rcx
0x140008ed9  jz      loc_1400090D9
0x140008edf  test    byte ptr [rax+44h], 4
0x140008ee3  jz      loc_1400090D9
0x140008ee9  cmp     byte ptr [rax+41h], 2
0x140008eed  jb      loc_1400090D9
0x140008ef3  mov     edx, 50h ; 'P'
0x140008ef8  jmp     loc_140008BFB
0x140008efd  mov     r8d, [rbp+57h+var_D0]
0x140008f01  mov     r9d, [rbp+57h+var_CC]
0x140008f05  mov     eax, 400h
0x140008f0a  cmp     r9d, eax
0x140008f0d  ja      loc_14000909A
0x140008f13  cmp     r8d, eax
0x140008f16  ja      loc_14000909A
0x140008f1c  mov     rcx, [rbp+57h+var_C8]
0x140008f20  mov     rax, [rcx]
0x140008f23  lea     rdx, [rbp+57h+var_B4]
0x140008f27  mov     rax, [rax+20h]
0x140008f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f30  mov     ebx, eax
0x140008f32  test    eax, eax
0x140008f34  jns     short loc_140008F6B
0x140008f36  lea     rcx, WPP_GLOBAL_Control
0x140008f3d  mov     rax, cs:WPP_GLOBAL_Control
0x140008f44  cmp     rax, rcx
0x140008f47  jz      loc_1400090D9
0x140008f4d  test    byte ptr [rax+44h], 4
0x140008f51  jz      loc_1400090D9
0x140008f57  cmp     byte ptr [rax+41h], 2
0x140008f5b  jb      loc_1400090D9
0x140008f61  mov     edx, 52h ; 'R'
0x140008f66  jmp     loc_140008BFB
0x140008f6b  mov     rcx, [rbp+57h+var_C8]
0x140008f6f  mov     rax, [rcx]
0x140008f72  lea     r8, [rbp+57h+var_78]
0x140008f76  lea     rdx, [rbp+57h+var_B8]
0x140008f7a  mov     rax, [rax+28h]
0x140008f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f83  mov     ebx, eax
0x140008f85  test    eax, eax
0x140008f87  jns     short loc_140008FBE
0x140008f89  lea     rcx, WPP_GLOBAL_Control
0x140008f90  mov     rax, cs:WPP_GLOBAL_Control
0x140008f97  cmp     rax, rcx
0x140008f9a  jz      loc_1400090D9
0x140008fa0  test    byte ptr [rax+44h], 4
0x140008fa4  jz      loc_1400090D9
0x140008faa  cmp     byte ptr [rax+41h], 2
0x140008fae  jb      loc_1400090D9
0x140008fb4  mov     edx, 53h ; 'S'
0x140008fb9  jmp     loc_140008BFB
0x140008fbe  lea     rcx, [rbp+57h+var_A8]
0x140008fc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008fc7  mov     rax, [rbp+57h+var_78]
0x140008fcb  mov     [rbp+57h+var_70], rax
0x140008fcf  mov     eax, [rbp+57h+var_B8]
0x140008fd2  mov     [rbp+57h+var_88], eax
0x140008fd5  mov     [rbp+57h+var_80], eax
0x140008fd8  mov     [rbp+57h+var_A8], r12
0x140008fdc  lea     r9, [rbp+57h+var_70]
0x140008fe0  lea     r8, [rbp+57h+var_88]
0x140008fe4  lea     rdx, [rbp+57h+var_80]
0x140008fe8  lea     rcx, [rbp+57h+var_60]
0x140008fec  call    ??$Make@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@AEAIAEAIAEAPEAEAEAV_lambda_8fcabb03306c9f8765c03020018d7da6_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@@12@AEAI0AEAPEAEAEAV_lambda_8fcabb03306c9f8765c03020018d7da6_@@@Z; Microsoft::WRL::Details::Make<Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>,uint &,uint &,uchar * &,_lambda_8fcabb03306c9f8765c03020018d7da6_ &>(uint &,uint &,uchar * &,_lambda_8fcabb03306c9f8765c03020018d7da6_ &)
0x140008ff1  mov     rdi, qword ptr [rbp+57h+var_60.Data1]
0x140008ff5  test    rdi, rdi
0x140008ff8  jnz     short loc_140009001
0x140008ffa  mov     ebx, 8007000Eh
0x140008fff  jmp     short loc_14000901C
0x140009001  mov     rax, [rdi]
0x140009004  lea     r8, [rbp+57h+var_A8]
0x140009008  lea     rdx, _GUID_905a0fe0_bc53_11df_8c49_001e4fc686da
0x14000900f  mov     rcx, rdi
0x140009012  mov     rax, [rax]
0x140009015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000901a  mov     ebx, eax
  ... truncated ...
```
