# GetProposedConnectorFormatForProcessingMode(IMMDeviceEnumerator *,IPropertyStore *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)

- ea: `0x180039984`
- end: `0x180039da7`
- name: `?GetProposedConnectorFormatForProcessingMode@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(struct IMMDeviceEnumerator *, struct IPropertyStore *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct _GUID *, struct tWAVEFORMATEX **)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038a04`
- `0x180038bb4`
- `0x180038bec`
- `0x1800394f0`
- `0x18003a8f0`

## callees

- `0x1800088dc`
- `0x18000accc`
- `0x1800126bc`
- `0x180039984`
- `0x18003cee0`
- `0x1800cf8c0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039add`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039d55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039d62`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039add`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039d55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039d62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039cd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039d1e`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall GetProposedConnectorFormatForProcessingMode(
        struct IMMDeviceEnumerator *a1,
        struct IPropertyStore *a2,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a3,
        struct _GUID *a4,
        struct tWAVEFORMATEX **a5)
{
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  struct IMMDeviceEnumeratorVtbl *lpVtbl; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  void *v20; // rcx
  int v21; // eax
  void *v22; // rcx
  int v24; // [rsp+20h] [rbp-B1h]
  int v25[2]; // [rsp+30h] [rbp-A1h] BYREF
  __int64 *v26; // [rsp+38h] [rbp-99h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-91h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-89h] BYREF
  __int64 *v29; // [rsp+50h] [rbp-81h] BYREF
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-79h] BYREF
  __int64 v31; // [rsp+68h] [rbp-69h]
  LPVOID *p_pv; // [rsp+70h] [rbp-61h] BYREF
  __int64 v33; // [rsp+78h] [rbp-59h] BYREF
  char v34; // [rsp+80h] [rbp-51h]
  PROPVARIANT v35[2]; // [rsp+88h] [rbp-49h] BYREF
  __int64 v36; // [rsp+98h] [rbp-39h]
  __int128 v37; // [rsp+A0h] [rbp-31h] BYREF
  int v38; // [rsp+B0h] [rbp-21h] BYREF
  int v39; // [rsp+B4h] [rbp-1Dh]
  int v40; // [rsp+B8h] [rbp-19h]
  int v41; // [rsp+BCh] [rbp-15h]
  int v42; // [rsp+C0h] [rbp-11h]
  _DWORD v43[6]; // [rsp+C8h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  *a5 = 0;
  v43[0] = 590439624;
  v43[1] = 1283267372;
  v43[2] = 1907779772;
  v43[3] = 1730509416;
  v43[4] = 1;
  if ( (a3 & 0xFFFFFFF9) != 0 || a3 == (eConnectorCount|eLoopbackConnector) )
  {
    if ( a3 == eOffloadConnector )
    {
      v42 = 19;
    }
    else
    {
      if ( a3 != eKeywordDetectorConnector )
      {
        v9 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x411,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
          (const char *)0x80070057LL,
          v24);
        return (unsigned int)v9;
      }
      v42 = 29;
    }
    v41 = -56945810;
    v40 = -1538194544;
    v39 = 1133379588;
    v38 = -1275528621;
  }
  else
  {
    v38 = -1702713381;
    v39 = 1102331579;
    v40 = -1223116157;
    v41 = -65530063;
    v42 = 1;
  }
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, _DWORD *, PROPVARIANT *))a2->lpVtbl->GetValue)(a2, v43, v35);
  v9 = v8;
  if ( v8 >= 0 )
  {
    *(_OWORD *)pvar = 0;
    v31 = 0;
    v10 = ((__int64 (__fastcall *)(struct IPropertyStore *, int *, PROPVARIANT *))a2->lpVtbl->GetValue)(a2, &v38, pvar);
    v9 = v10;
    if ( v10 >= 0 )
    {
      lpVtbl = a1->lpVtbl;
      v26 = 0;
      v12 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, PROPVARIANT, __int64 **))lpVtbl->GetDevice)(
              a1,
              v35[1],
              &v26);
      v9 = v12;
      if ( v12 >= 0 )
      {
        *(_QWORD *)v25 = 0;
        v13 = *v26;
        *(_QWORD *)v25 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v13 + 24))(
                v26,
                &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
                23);
        v9 = v14;
        if ( v14 >= 0 )
        {
          v28 = 0;
          v15 = **(_QWORD **)v25;
          v28 = 0;
          v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v15 + 56))(
                  *(_QWORD *)v25,
                  LODWORD(pvar[1]),
                  &v28);
          v9 = v16;
          if ( v16 >= 0 )
          {
            v29 = 0;
            v17 = *v28;
            v29 = 0;
            v18 = (*(__int64 (__fastcall **)(__int64 *, __int64, GUID *, __int64 **))(v17 + 104))(
                    v28,
                    23,
                    &GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81,
                    &v29);
            v9 = v18;
            if ( v18 >= 0 )
            {
              pv = 0;
              v19 = *v29;
              p_pv = &pv;
              v33 = 0;
              v34 = 1;
              v37 = (__int128)*a4;
              v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64 *))(v19 + 24))(v29, &v37, &v33);
              wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
              if ( v9 >= 0 )
              {
                v21 = CloneWaveFormat((const struct tWAVEFORMATEX *)((char *)pv + 64), a5);
                v9 = v21;
                if ( v21 >= 0 )
                {
                  v22 = pv;
                  pv = 0;
                  if ( v22 )
                    CoTaskMemFree(v22);
                  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
                  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
                  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v25);
                  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v26);
                  PropVariantClear(pvar);
                  v9 = 0;
                  goto LABEL_38;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x42B,
                  (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
                  (const char *)(unsigned int)v21,
                  (int)v25);
              }
              v20 = pv;
              pv = 0;
              if ( v20 )
                CoTaskMemFree(v20);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x424,
                (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
                (const char *)(unsigned int)v18,
                (int)v25);
            }
            wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x421,
              (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
              (const char *)(unsigned int)v16,
              (int)v25);
          }
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v25);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v26);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x41E,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
            (const char *)(unsigned int)v14,
            (int)v25);
          if ( *(_QWORD *)v25 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 16LL))(*(_QWORD *)v25);
          if ( v26 )
            (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x41B,
          (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
          (const char *)(unsigned int)v12,
          v24);
        if ( v26 )
          (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x418,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
        (const char *)(unsigned int)v10,
        v24);
    }
    PropVariantClear(pvar);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x415,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)(unsigned int)v8,
      v24);
  }
LABEL_38:
  PropVariantClear(v35);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180039984  push    rbp
0x180039986  push    rbx
0x180039987  push    rsi
0x180039988  push    rdi
0x180039989  push    r12
0x18003998b  push    r14
0x18003998d  push    r15
0x18003998f  lea     rbp, [rsp-1Fh]
0x180039994  sub     rsp, 0F0h
0x18003999b  mov     rax, cs:__security_cookie
0x1800399a2  xor     rax, rsp
0x1800399a5  mov     [rbp+4Fh+var_40], rax
0x1800399a9  mov     r15, r9
0x1800399ac  mov     rdi, rdx
0x1800399af  mov     rsi, rcx
0x1800399b2  mov     r14, [rbp+4Fh+arg_20]
0x1800399b6  xor     r12d, r12d
0x1800399b9  mov     [r14], r12
0x1800399bc  mov     [rbp+4Fh+var_58], 233164C8h
0x1800399c3  mov     [rbp+4Fh+var_54], 4C7D1B2Ch
0x1800399ca  mov     [rbp+4Fh+var_50], 71B668BCh
0x1800399d1  mov     [rbp+4Fh+var_4C], 67257A68h
0x1800399d8  mov     [rbp+4Fh+var_48], 1
0x1800399df  test    r8d, 0FFFFFFF9h
0x1800399e6  jnz     short loc_180039A13
0x1800399e8  cmp     r8d, 6
0x1800399ec  jz      short loc_180039A13
0x1800399ee  mov     [rbp+4Fh+var_70], 9A82A7DBh
0x1800399f5  mov     [rbp+4Fh+var_6C], 41B43EBBh
0x1800399fc  mov     [rbp+4Fh+var_68], 0B718BA83h
0x180039a03  mov     [rbp+4Fh+var_64], 0FC181731h
0x180039a0a  mov     [rbp+4Fh+var_60], 1
0x180039a11  jmp     short loc_180039A4F
0x180039a13  cmp     r8d, 1
0x180039a17  jnz     short loc_180039A22
0x180039a19  mov     [rbp+4Fh+var_60], 13h
0x180039a20  jmp     short loc_180039A33
0x180039a22  cmp     r8d, 3
0x180039a26  jnz     loc_180039D6A
0x180039a2c  mov     [rbp+4Fh+var_60], 1Dh
0x180039a33  mov     [rbp+4Fh+var_64], 0FC9B136Eh
0x180039a3a  mov     [rbp+4Fh+var_68], 0A4510390h
0x180039a41  mov     [rbp+4Fh+var_6C], 438E0004h
0x180039a48  mov     [rbp+4Fh+var_70], 0B3F8FA53h
0x180039a4f  xorps   xmm0, xmm0
0x180039a52  xor     eax, eax
0x180039a54  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x180039a58  mov     [rbp+4Fh+var_88], rax
0x180039a5c  mov     rax, [rdx]
0x180039a5f  lea     r8, [rbp+4Fh+var_98]
0x180039a63  lea     rdx, [rbp+4Fh+var_58]
0x180039a67  mov     rcx, rdi
0x180039a6a  mov     rax, [rax+28h]
0x180039a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a73  mov     ebx, eax
0x180039a75  test    eax, eax
0x180039a77  jns     short loc_180039A96
0x180039a79  mov     rcx, [rbp+57h]; this
0x180039a7d  mov     r9d, eax; char *
0x180039a80  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039a87  mov     edx, 415h; void *
0x180039a8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a91  jmp     loc_180039D5E
0x180039a96  xorps   xmm0, xmm0
0x180039a99  xor     eax, eax
0x180039a9b  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180039a9f  mov     [rbp+4Fh+var_B8], rax
0x180039aa3  mov     rax, [rdi]
0x180039aa6  lea     r8, [rbp+4Fh+pvar]
0x180039aaa  lea     rdx, [rbp+4Fh+var_70]
0x180039aae  mov     rcx, rdi
0x180039ab1  mov     rax, [rax+28h]
0x180039ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039aba  mov     ebx, eax
0x180039abc  test    eax, eax
0x180039abe  jns     short loc_180039AE8
0x180039ac0  mov     rcx, [rbp+57h]; this
0x180039ac4  mov     r9d, eax; char *
0x180039ac7  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039ace  mov     edx, 418h; void *
0x180039ad3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ad8  nop
0x180039ad9  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180039add  call    cs:__imp_PropVariantClear
0x180039ae3  jmp     loc_180039D5E
0x180039ae8  mov     rax, [rsi]
0x180039aeb  mov     [rsp+120h+var_E8], r12
0x180039af0  lea     r8, [rsp+120h+var_E8]
0x180039af5  mov     rdx, [rbp+4Fh+var_98+8]
0x180039af9  mov     rcx, rsi
0x180039afc  mov     rax, [rax+28h]
0x180039b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b05  mov     ebx, eax
0x180039b07  test    eax, eax
0x180039b09  jns     short loc_180039B3D
0x180039b0b  mov     rcx, [rbp+57h]; this
0x180039b0f  mov     r9d, eax; char *
0x180039b12  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039b19  mov     edx, 41Bh; void *
0x180039b1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039b23  nop
0x180039b24  mov     rcx, [rsp+120h+var_E8]
0x180039b29  test    rcx, rcx
0x180039b2c  jz      short loc_180039B3B
0x180039b2e  mov     rax, [rcx]
0x180039b31  mov     rax, [rax+10h]
0x180039b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b3a  nop
0x180039b3b  jmp     short loc_180039AD9
0x180039b3d  mov     qword ptr [rsp+120h+var_F0], r12
0x180039b42  mov     rcx, [rsp+120h+var_E8]
0x180039b47  mov     rax, [rcx]
0x180039b4a  mov     qword ptr [rsp+120h+var_F0], r12
0x180039b4f  lea     rdx, [rsp+120h+var_F0]
0x180039b54  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180039b59  xor     r9d, r9d
0x180039b5c  lea     edi, [r9+17h]
0x180039b60  mov     r8d, edi
0x180039b63  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180039b6a  mov     rax, [rax+18h]
0x180039b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039b73  mov     ebx, eax
0x180039b75  test    eax, eax
0x180039b77  jns     short loc_180039BC5
0x180039b79  mov     rcx, [rbp+57h]; this
0x180039b7d  mov     r9d, eax; char *
0x180039b80  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039b87  mov     edx, 41Eh; void *
0x180039b8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039b91  nop
0x180039b92  mov     rcx, qword ptr [rsp+120h+var_F0]
0x180039b97  test    rcx, rcx
0x180039b9a  jz      short loc_180039BA9
0x180039b9c  mov     rax, [rcx]
0x180039b9f  mov     rax, [rax+10h]
0x180039ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ba8  nop
0x180039ba9  mov     rcx, [rsp+120h+var_E8]
0x180039bae  test    rcx, rcx
0x180039bb1  jz      short loc_180039BC0
0x180039bb3  mov     rax, [rcx]
0x180039bb6  mov     rax, [rax+10h]
0x180039bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bbf  nop
0x180039bc0  jmp     loc_180039AD9
0x180039bc5  mov     [rsp+120h+var_D8], r12
0x180039bca  mov     rcx, qword ptr [rsp+120h+var_F0]
0x180039bcf  mov     rax, [rcx]
0x180039bd2  mov     [rsp+120h+var_D8], r12
0x180039bd7  lea     r8, [rsp+120h+var_D8]
0x180039bdc  mov     edx, dword ptr [rbp+4Fh+pvar+8]
0x180039bdf  mov     rax, [rax+38h]
0x180039be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039be8  mov     ebx, eax
0x180039bea  test    eax, eax
0x180039bec  jns     short loc_180039C2C
0x180039bee  mov     rcx, [rbp+57h]; this
0x180039bf2  mov     r9d, eax; char *
0x180039bf5  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039bfc  mov     edx, 421h; void *
0x180039c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c06  nop
0x180039c07  lea     rcx, [rsp+120h+var_D8]
0x180039c0c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039c11  nop
0x180039c12  lea     rcx, [rsp+120h+var_F0]
0x180039c17  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039c1c  nop
0x180039c1d  lea     rcx, [rsp+120h+var_E8]
0x180039c22  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039c27  jmp     loc_180039AD9
0x180039c2c  mov     [rsp+120h+var_D0], r12
0x180039c31  mov     rcx, [rsp+120h+var_D8]
0x180039c36  mov     rax, [rcx]
0x180039c39  mov     [rsp+120h+var_D0], r12
0x180039c3e  lea     r9, [rsp+120h+var_D0]
0x180039c43  lea     r8, _GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81
0x180039c4a  mov     edx, edi
0x180039c4c  mov     rax, [rax+68h]
0x180039c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c55  mov     ebx, eax
0x180039c57  test    eax, eax
0x180039c59  jns     short loc_180039C80
0x180039c5b  mov     rcx, [rbp+57h]; this
0x180039c5f  mov     r9d, eax; char *
0x180039c62  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039c69  mov     edx, 424h; void *
0x180039c6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c73  nop
0x180039c74  lea     rcx, [rsp+120h+var_D0]
0x180039c79  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039c7e  jmp     short loc_180039C07
0x180039c80  mov     [rsp+120h+pv], r12
0x180039c85  mov     rcx, [rsp+120h+var_D0]
0x180039c8a  mov     rax, [rcx]
0x180039c8d  lea     rdx, [rsp+120h+pv]
0x180039c92  mov     [rbp+4Fh+var_B0], rdx
0x180039c96  mov     [rbp+4Fh+var_A8], r12
0x180039c9a  mov     [rbp+4Fh+var_A0], 1
0x180039c9e  movaps  xmm0, xmmword ptr [r15]
0x180039ca2  movdqa  [rbp+4Fh+var_80], xmm0
0x180039ca7  lea     r8, [rbp+4Fh+var_A8]
0x180039cab  lea     rdx, [rbp+4Fh+var_80]
0x180039caf  mov     rax, [rax+18h]
0x180039cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cb8  mov     ebx, eax
0x180039cba  lea     rcx, [rbp+4Fh+var_B0]
0x180039cbe  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180039cc3  test    ebx, ebx
0x180039cc5  jns     short loc_180039CDE
0x180039cc7  mov     rcx, [rsp+120h+pv]; pv
0x180039ccc  mov     [rsp+120h+pv], r12
0x180039cd1  test    rcx, rcx
0x180039cd4  jz      short loc_180039C74
0x180039cd6  call    cs:__imp_CoTaskMemFree
0x180039cdc  jmp     short loc_180039C74
0x180039cde  mov     rcx, [rsp+120h+pv]
0x180039ce3  add     rcx, 40h ; '@'; Src
0x180039ce7  mov     rdx, r14; struct tWAVEFORMATEX **
0x180039cea  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180039cef  mov     ebx, eax
0x180039cf1  test    eax, eax
0x180039cf3  jns     short loc_180039D0F
0x180039cf5  mov     rcx, [rbp+57h]; this
0x180039cf9  mov     r9d, eax; char *
0x180039cfc  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039d03  mov     edx, 42Bh; void *
0x180039d08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d0d  jmp     short loc_180039CC7
0x180039d0f  mov     rcx, [rsp+120h+pv]; pv
0x180039d14  mov     [rsp+120h+pv], r12
0x180039d19  test    rcx, rcx
0x180039d1c  jz      short loc_180039D25
0x180039d1e  call    cs:__imp_CoTaskMemFree
0x180039d24  nop
0x180039d25  lea     rcx, [rsp+120h+var_D0]
0x180039d2a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039d2f  nop
0x180039d30  lea     rcx, [rsp+120h+var_D8]
0x180039d35  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039d3a  nop
0x180039d3b  lea     rcx, [rsp+120h+var_F0]
0x180039d40  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039d45  nop
0x180039d46  lea     rcx, [rsp+120h+var_E8]
0x180039d4b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039d50  nop
0x180039d51  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180039d55  call    cs:__imp_PropVariantClear
0x180039d5b  mov     ebx, r12d
0x180039d5e  lea     rcx, [rbp+4Fh+var_98]; pvar
0x180039d62  call    cs:__imp_PropVariantClear
0x180039d68  jmp     short loc_180039D87
0x180039d6a  mov     rcx, [rbp+57h]; this
0x180039d6e  mov     ebx, 80070057h
0x180039d73  mov     r9d, ebx; char *
0x180039d76  lea     r8, aAvcoreAudiocor_77; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039d7d  mov     edx, 411h; void *
0x180039d82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d87  mov     eax, ebx
0x180039d89  mov     rcx, [rbp+4Fh+var_40]
0x180039d8d  xor     rcx, rsp; StackCookie
0x180039d90  call    __security_check_cookie
0x180039d95  add     rsp, 0F0h
0x180039d9c  pop     r15
0x180039d9e  pop     r14
0x180039da0  pop     r12
0x180039da2  pop     rdi
0x180039da3  pop     rsi
0x180039da4  pop     rbx
0x180039da5  pop     rbp
0x180039da6  retn
```
