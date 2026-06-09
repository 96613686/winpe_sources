# GetProposedConnectorFormatForProcessingMode(IMMDeviceEnumerator *,IPropertyStore *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)

- ea: `0x180039ae4`
- end: `0x180039f07`
- name: `?GetProposedConnectorFormatForProcessingMode@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(struct IMMDeviceEnumerator *, struct IPropertyStore *, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, struct _GUID *, struct tWAVEFORMATEX **)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038b64`
- `0x180038d14`
- `0x180038d4c`
- `0x180039650`
- `0x18003aa50`

## callees

- `0x180008a2c`
- `0x18000ae1c`
- `0x18001280c`
- `0x180039ae4`
- `0x18003d040`
- `0x1800cd8d0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039c3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039eb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039ec2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039c3d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039eb5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039ec2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039e36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039e7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039e36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039e7e`

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
0x180039ae4  push    rbp
0x180039ae6  push    rbx
0x180039ae7  push    rsi
0x180039ae8  push    rdi
0x180039ae9  push    r12
0x180039aeb  push    r14
0x180039aed  push    r15
0x180039aef  lea     rbp, [rsp-1Fh]
0x180039af4  sub     rsp, 0F0h
0x180039afb  mov     rax, cs:__security_cookie
0x180039b02  xor     rax, rsp
0x180039b05  mov     [rbp+4Fh+var_40], rax
0x180039b09  mov     r15, r9
0x180039b0c  mov     rdi, rdx
0x180039b0f  mov     rsi, rcx
0x180039b12  mov     r14, [rbp+4Fh+arg_20]
0x180039b16  xor     r12d, r12d
0x180039b19  mov     [r14], r12
0x180039b1c  mov     [rbp+4Fh+var_58], 233164C8h
0x180039b23  mov     [rbp+4Fh+var_54], 4C7D1B2Ch
0x180039b2a  mov     [rbp+4Fh+var_50], 71B668BCh
0x180039b31  mov     [rbp+4Fh+var_4C], 67257A68h
0x180039b38  mov     [rbp+4Fh+var_48], 1
0x180039b3f  test    r8d, 0FFFFFFF9h
0x180039b46  jnz     short loc_180039B73
0x180039b48  cmp     r8d, 6
0x180039b4c  jz      short loc_180039B73
0x180039b4e  mov     [rbp+4Fh+var_70], 9A82A7DBh
0x180039b55  mov     [rbp+4Fh+var_6C], 41B43EBBh
0x180039b5c  mov     [rbp+4Fh+var_68], 0B718BA83h
0x180039b63  mov     [rbp+4Fh+var_64], 0FC181731h
0x180039b6a  mov     [rbp+4Fh+var_60], 1
0x180039b71  jmp     short loc_180039BAF
0x180039b73  cmp     r8d, 1
0x180039b77  jnz     short loc_180039B82
0x180039b79  mov     [rbp+4Fh+var_60], 13h
0x180039b80  jmp     short loc_180039B93
0x180039b82  cmp     r8d, 3
0x180039b86  jnz     loc_180039ECA
0x180039b8c  mov     [rbp+4Fh+var_60], 1Dh
0x180039b93  mov     [rbp+4Fh+var_64], 0FC9B136Eh
0x180039b9a  mov     [rbp+4Fh+var_68], 0A4510390h
0x180039ba1  mov     [rbp+4Fh+var_6C], 438E0004h
0x180039ba8  mov     [rbp+4Fh+var_70], 0B3F8FA53h
0x180039baf  xorps   xmm0, xmm0
0x180039bb2  xor     eax, eax
0x180039bb4  movups  xmmword ptr [rbp+4Fh+var_98], xmm0
0x180039bb8  mov     [rbp+4Fh+var_88], rax
0x180039bbc  mov     rax, [rdx]
0x180039bbf  lea     r8, [rbp+4Fh+var_98]
0x180039bc3  lea     rdx, [rbp+4Fh+var_58]
0x180039bc7  mov     rcx, rdi
0x180039bca  mov     rax, [rax+28h]
0x180039bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039bd3  mov     ebx, eax
0x180039bd5  test    eax, eax
0x180039bd7  jns     short loc_180039BF6
0x180039bd9  mov     rcx, [rbp+57h]; this
0x180039bdd  mov     r9d, eax; char *
0x180039be0  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039be7  mov     edx, 415h; void *
0x180039bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039bf1  jmp     loc_180039EBE
0x180039bf6  xorps   xmm0, xmm0
0x180039bf9  xor     eax, eax
0x180039bfb  movups  xmmword ptr [rbp+4Fh+pvar], xmm0
0x180039bff  mov     [rbp+4Fh+var_B8], rax
0x180039c03  mov     rax, [rdi]
0x180039c06  lea     r8, [rbp+4Fh+pvar]
0x180039c0a  lea     rdx, [rbp+4Fh+var_70]
0x180039c0e  mov     rcx, rdi
0x180039c11  mov     rax, [rax+28h]
0x180039c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c1a  mov     ebx, eax
0x180039c1c  test    eax, eax
0x180039c1e  jns     short loc_180039C48
0x180039c20  mov     rcx, [rbp+57h]; this
0x180039c24  mov     r9d, eax; char *
0x180039c27  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039c2e  mov     edx, 418h; void *
0x180039c33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c38  nop
0x180039c39  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180039c3d  call    cs:__imp_PropVariantClear
0x180039c43  jmp     loc_180039EBE
0x180039c48  mov     rax, [rsi]
0x180039c4b  mov     [rsp+120h+var_E8], r12
0x180039c50  lea     r8, [rsp+120h+var_E8]
0x180039c55  mov     rdx, [rbp+4Fh+var_98+8]
0x180039c59  mov     rcx, rsi
0x180039c5c  mov     rax, [rax+28h]
0x180039c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c65  mov     ebx, eax
0x180039c67  test    eax, eax
0x180039c69  jns     short loc_180039C9D
0x180039c6b  mov     rcx, [rbp+57h]; this
0x180039c6f  mov     r9d, eax; char *
0x180039c72  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039c79  mov     edx, 41Bh; void *
0x180039c7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c83  nop
0x180039c84  mov     rcx, [rsp+120h+var_E8]
0x180039c89  test    rcx, rcx
0x180039c8c  jz      short loc_180039C9B
0x180039c8e  mov     rax, [rcx]
0x180039c91  mov     rax, [rax+10h]
0x180039c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039c9a  nop
0x180039c9b  jmp     short loc_180039C39
0x180039c9d  mov     qword ptr [rsp+120h+var_F0], r12
0x180039ca2  mov     rcx, [rsp+120h+var_E8]
0x180039ca7  mov     rax, [rcx]
0x180039caa  mov     qword ptr [rsp+120h+var_F0], r12
0x180039caf  lea     rdx, [rsp+120h+var_F0]
0x180039cb4  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180039cb9  xor     r9d, r9d
0x180039cbc  lea     edi, [r9+17h]
0x180039cc0  mov     r8d, edi
0x180039cc3  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180039cca  mov     rax, [rax+18h]
0x180039cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039cd3  mov     ebx, eax
0x180039cd5  test    eax, eax
0x180039cd7  jns     short loc_180039D25
0x180039cd9  mov     rcx, [rbp+57h]; this
0x180039cdd  mov     r9d, eax; char *
0x180039ce0  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039ce7  mov     edx, 41Eh; void *
0x180039cec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039cf1  nop
0x180039cf2  mov     rcx, qword ptr [rsp+120h+var_F0]
0x180039cf7  test    rcx, rcx
0x180039cfa  jz      short loc_180039D09
0x180039cfc  mov     rax, [rcx]
0x180039cff  mov     rax, [rax+10h]
0x180039d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d08  nop
0x180039d09  mov     rcx, [rsp+120h+var_E8]
0x180039d0e  test    rcx, rcx
0x180039d11  jz      short loc_180039D20
0x180039d13  mov     rax, [rcx]
0x180039d16  mov     rax, [rax+10h]
0x180039d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d1f  nop
0x180039d20  jmp     loc_180039C39
0x180039d25  mov     [rsp+120h+var_D8], r12
0x180039d2a  mov     rcx, qword ptr [rsp+120h+var_F0]
0x180039d2f  mov     rax, [rcx]
0x180039d32  mov     [rsp+120h+var_D8], r12
0x180039d37  lea     r8, [rsp+120h+var_D8]
0x180039d3c  mov     edx, dword ptr [rbp+4Fh+pvar+8]
0x180039d3f  mov     rax, [rax+38h]
0x180039d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d48  mov     ebx, eax
0x180039d4a  test    eax, eax
0x180039d4c  jns     short loc_180039D8C
0x180039d4e  mov     rcx, [rbp+57h]; this
0x180039d52  mov     r9d, eax; char *
0x180039d55  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039d5c  mov     edx, 421h; void *
0x180039d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039d66  nop
0x180039d67  lea     rcx, [rsp+120h+var_D8]
0x180039d6c  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039d71  nop
0x180039d72  lea     rcx, [rsp+120h+var_F0]
0x180039d77  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039d7c  nop
0x180039d7d  lea     rcx, [rsp+120h+var_E8]
0x180039d82  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039d87  jmp     loc_180039C39
0x180039d8c  mov     [rsp+120h+var_D0], r12
0x180039d91  mov     rcx, [rsp+120h+var_D8]
0x180039d96  mov     rax, [rcx]
0x180039d99  mov     [rsp+120h+var_D0], r12
0x180039d9e  lea     r9, [rsp+120h+var_D0]
0x180039da3  lea     r8, _GUID_e792f5ac_33a8_4f03_9840_cbee917b8f81
0x180039daa  mov     edx, edi
0x180039dac  mov     rax, [rax+68h]
0x180039db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039db5  mov     ebx, eax
0x180039db7  test    eax, eax
0x180039db9  jns     short loc_180039DE0
0x180039dbb  mov     rcx, [rbp+57h]; this
0x180039dbf  mov     r9d, eax; char *
0x180039dc2  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039dc9  mov     edx, 424h; void *
0x180039dce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039dd3  nop
0x180039dd4  lea     rcx, [rsp+120h+var_D0]
0x180039dd9  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039dde  jmp     short loc_180039D67
0x180039de0  mov     [rsp+120h+pv], r12
0x180039de5  mov     rcx, [rsp+120h+var_D0]
0x180039dea  mov     rax, [rcx]
0x180039ded  lea     rdx, [rsp+120h+pv]
0x180039df2  mov     [rbp+4Fh+var_B0], rdx
0x180039df6  mov     [rbp+4Fh+var_A8], r12
0x180039dfa  mov     [rbp+4Fh+var_A0], 1
0x180039dfe  movaps  xmm0, xmmword ptr [r15]
0x180039e02  movdqa  [rbp+4Fh+var_80], xmm0
0x180039e07  lea     r8, [rbp+4Fh+var_A8]
0x180039e0b  lea     rdx, [rbp+4Fh+var_80]
0x180039e0f  mov     rax, [rax+18h]
0x180039e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e18  mov     ebx, eax
0x180039e1a  lea     rcx, [rbp+4Fh+var_B0]
0x180039e1e  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180039e23  test    ebx, ebx
0x180039e25  jns     short loc_180039E3E
0x180039e27  mov     rcx, [rsp+120h+pv]; pv
0x180039e2c  mov     [rsp+120h+pv], r12
0x180039e31  test    rcx, rcx
0x180039e34  jz      short loc_180039DD4
0x180039e36  call    cs:__imp_CoTaskMemFree
0x180039e3c  jmp     short loc_180039DD4
0x180039e3e  mov     rcx, [rsp+120h+pv]
0x180039e43  add     rcx, 40h ; '@'; Src
0x180039e47  mov     rdx, r14; struct tWAVEFORMATEX **
0x180039e4a  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180039e4f  mov     ebx, eax
0x180039e51  test    eax, eax
0x180039e53  jns     short loc_180039E6F
0x180039e55  mov     rcx, [rbp+57h]; this
0x180039e59  mov     r9d, eax; char *
0x180039e5c  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039e63  mov     edx, 42Bh; void *
0x180039e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039e6d  jmp     short loc_180039E27
0x180039e6f  mov     rcx, [rsp+120h+pv]; pv
0x180039e74  mov     [rsp+120h+pv], r12
0x180039e79  test    rcx, rcx
0x180039e7c  jz      short loc_180039E85
0x180039e7e  call    cs:__imp_CoTaskMemFree
0x180039e84  nop
0x180039e85  lea     rcx, [rsp+120h+var_D0]
0x180039e8a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039e8f  nop
0x180039e90  lea     rcx, [rsp+120h+var_D8]
0x180039e95  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039e9a  nop
0x180039e9b  lea     rcx, [rsp+120h+var_F0]
0x180039ea0  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039ea5  nop
0x180039ea6  lea     rcx, [rsp+120h+var_E8]
0x180039eab  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180039eb0  nop
0x180039eb1  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180039eb5  call    cs:__imp_PropVariantClear
0x180039ebb  mov     ebx, r12d
0x180039ebe  lea     rcx, [rbp+4Fh+var_98]; pvar
0x180039ec2  call    cs:__imp_PropVariantClear
0x180039ec8  jmp     short loc_180039EE7
0x180039eca  mov     rcx, [rbp+57h]; this
0x180039ece  mov     ebx, 80070057h
0x180039ed3  mov     r9d, ebx; char *
0x180039ed6  lea     r8, aAvcoreAudiocor_78; "avcore\\audiocore\\server\\lib\\audioen"...
0x180039edd  mov     edx, 411h; void *
0x180039ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ee7  mov     eax, ebx
0x180039ee9  mov     rcx, [rbp+4Fh+var_40]
0x180039eed  xor     rcx, rsp; StackCookie
0x180039ef0  call    __security_check_cookie
0x180039ef5  add     rsp, 0F0h
0x180039efc  pop     r15
0x180039efe  pop     r14
0x180039f00  pop     r12
0x180039f02  pop     rdi
0x180039f03  pop     rsi
0x180039f04  pop     rbx
0x180039f05  pop     rbp
0x180039f06  retn
```
