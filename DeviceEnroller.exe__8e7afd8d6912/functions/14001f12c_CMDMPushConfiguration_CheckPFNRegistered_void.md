# CMDMPushConfiguration::CheckPFNRegistered(void)

- ea: `0x14001f12c`
- end: `0x14001f6ba`
- name: `?CheckPFNRegistered@CMDMPushConfiguration@@AEAAJXZ`
- size: `1422`
- prototype: `__int64 __fastcall(CMDMPushConfiguration *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400249a4`

## callees

- `0x1400042f0`
- `0x1400095b4`
- `0x14001f12c`
- `0x14002478c`
- `0x140025eb0`
- `0x1400261c0`
- `0x140028450`
- `0x14005d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14001f3bf`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f440`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f4d6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f4e6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f5c0`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f5cf`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f630`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f63f`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f3bf`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f440`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f4d6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f4e6`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f5c0`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f5cf`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f630`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f63f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001f24f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001f24f`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CheckPFNRegistered(CMDMPushConfiguration *this)
{
  int IsDeviceChannel; // eax
  unsigned int v3; // ebx
  int v5; // eax
  LPVOID v6; // rcx
  LPVOID v7; // rcx
  HRESULT v8; // eax
  LPVOID v9; // rcx
  int v10; // eax
  __int64 (__fastcall ***v11)(_QWORD, GUID *, _QWORD *); // rcx
  LPVOID v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // rcx
  LPVOID v16; // rcx
  int PFN; // eax
  __int64 v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, GUID *, _QWORD *); // rcx
  LPVOID v20; // rdx
  __int64 v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, GUID *, _QWORD *); // rcx
  LPVOID v23; // rcx
  int AppId; // eax
  __int64 v25; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, _QWORD *); // rcx
  LPVOID v27; // rcx
  OLECHAR *v28; // rax
  OLECHAR *v29; // rdi
  OLECHAR *v30; // rbx
  int v31; // eax
  unsigned int v32; // esi
  __int64 v33; // rcx
  __int64 (__fastcall ***v34)(_QWORD, GUID *, _QWORD *); // rcx
  LPVOID v35; // rcx
  __int64 v36; // rcx
  __int64 (__fastcall ***v37)(_QWORD, GUID *, _QWORD *); // rcx
  LPVOID v38; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  LPVOID v40; // [rsp+40h] [rbp-40h] BYREF
  __int64 (__fastcall ***v41)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-38h] BYREF
  __int64 v42; // [rsp+50h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-28h] BYREF
  BSTR v44[2]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v40 = 0;
  IsDeviceChannel = CMDMPushConfiguration::SaveIsDeviceChannel(this, 1);
  v3 = IsDeviceChannel;
  if ( IsDeviceChannel < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)(unsigned int)IsDeviceChannel,
      ppv);
    return v3;
  }
  if ( (int)GetSystemOrDefaultWpnPlatform(&v40) < 0 )
  {
    v5 = CMDMPushConfiguration::SaveIsDeviceChannel(this, 0);
    v3 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73D,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)v5,
        ppv);
      v6 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
      }
      return v3;
    }
    v7 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = CoCreateInstance(
           &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
           0,
           4u,
           &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
           &v40);
    v3 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x742,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)v8,
        ppv);
      v9 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
      }
      return v3;
    }
  }
  v41 = 0;
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v40 + 40LL))(
          v40,
          &v41);
  v3 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x746,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)(unsigned int)v10,
      ppv);
    v11 = v41;
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v11)[2])(v11);
    }
    v12 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v3;
  }
  v42 = 0;
  v13 = (**v41)(v41, &GUID_7d85494e_d99e_493a_bf51_80d2c9feab49, &v42);
  v3 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x749,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)(unsigned int)v13,
      ppv);
    v14 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    v15 = v41;
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v15)[2])(v15);
    }
    v16 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v3;
  }
  bstrString = 0;
  PFN = CMDMPushConfiguration::GetPFN(this, &bstrString);
  v3 = PFN;
  if ( PFN >= 0 )
  {
    v44[0] = 0;
    AppId = CMDMPushConfiguration::GetAppId(this, v44);
    v3 = AppId;
    if ( AppId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)AppId,
        ppv);
      if ( v44[0] )
        SysFreeString(v44[0]);
      if ( bstrString )
        SysFreeString(bstrString);
      v25 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
      v26 = v41;
      if ( v41 )
      {
        v41 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v26)[2])(v26);
      }
      v27 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
      }
      return v3;
    }
    v28 = (OLECHAR *)WNF_ENTR_PUSH_RECEIVED;
    if ( ((1LL << *((_DWORD *)this + 4)) & 0xD000000) != 0 )
      v28 = (OLECHAR *)WNF_ENTR_PUSH_RECEIVED_MMPC;
    v44[1] = v28;
    v29 = v44[0];
    v30 = bstrString;
    v31 = (*(__int64 (__fastcall **)(__int64, BSTR, BSTR, __int64))(*(_QWORD *)v42 + 24LL))(
            v42,
            bstrString,
            v44[0],
            3855);
    v32 = v31;
    if ( v31 >= 0 )
    {
      if ( v29 )
        SysFreeString(v29);
      if ( v30 )
        SysFreeString(v30);
      v36 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      v37 = v41;
      if ( v41 )
      {
        v41 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v37)[2])(v37);
      }
      v38 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x758,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)v31,
        8);
      if ( v29 )
        SysFreeString(v29);
      if ( v30 )
        SysFreeString(v30);
      v33 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      v34 = v41;
      if ( v41 )
      {
        v41 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v34)[2])(v34);
      }
      v35 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v35 + 16LL))(v35);
      }
      return v32;
    }
  }
  else
  {
    if ( PFN != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
        (const char *)(unsigned int)PFN,
        ppv);
      if ( bstrString )
        SysFreeString(bstrString);
      v21 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      v22 = v41;
      if ( v41 )
      {
        v41 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v22)[2])(v22);
      }
      v23 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
      }
      return v3;
    }
    if ( bstrString )
      SysFreeString(bstrString);
    v18 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v41;
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v19)[2])(v19);
    }
    v20 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x14001f12c  mov     [rsp-18h+arg_8], rbx
0x14001f131  mov     [rsp-18h+arg_10], rsi
0x14001f136  push    rbp
0x14001f137  push    rdi
0x14001f138  push    r14
0x14001f13a  mov     rbp, rsp
0x14001f13d  sub     rsp, 80h
0x14001f144  mov     rax, cs:__security_cookie
0x14001f14b  xor     rax, rsp
0x14001f14e  mov     [rbp+var_10], rax
0x14001f152  mov     rdi, rcx
0x14001f155  xor     r14d, r14d
0x14001f158  mov     [rbp+var_40], r14
0x14001f15c  lea     esi, [r14+1]
0x14001f160  mov     dl, sil; bool
0x14001f163  call    ?SaveIsDeviceChannel@CMDMPushConfiguration@@AEAAJ_N@Z; CMDMPushConfiguration::SaveIsDeviceChannel(bool)
0x14001f168  mov     ebx, eax
0x14001f16a  test    eax, eax
0x14001f16c  jns     short loc_14001F1A8
0x14001f16e  mov     rcx, [rbp+18h]; this
0x14001f172  mov     r9d, eax; char *
0x14001f175  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x14001f17c  mov     edx, 73Ah; void *
0x14001f181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f186  nop
0x14001f187  mov     rcx, [rbp+var_40]
0x14001f18b  test    rcx, rcx
0x14001f18e  jz      short loc_14001F1A1
0x14001f190  mov     [rbp+var_40], r14
0x14001f194  mov     rax, [rcx]
0x14001f197  mov     rax, [rax+10h]
0x14001f19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f1a0  nop
0x14001f1a1  mov     eax, ebx
0x14001f1a3  jmp     loc_14001F696
0x14001f1a8  mov     rcx, [rbp+var_40]
0x14001f1ac  test    rcx, rcx
0x14001f1af  jz      short loc_14001F1C2
0x14001f1b1  mov     [rbp+var_40], r14
0x14001f1b5  mov     rax, [rcx]
0x14001f1b8  mov     rax, [rax+10h]
0x14001f1bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f1c1  nop
0x14001f1c2  lea     rcx, [rbp+var_40]; ppv
0x14001f1c6  call    ?GetSystemOrDefaultWpnPlatform@@YAJPEAPEAUIWpnPlatform@@@Z; GetSystemOrDefaultWpnPlatform(IWpnPlatform * *)
0x14001f1cb  test    eax, eax
0x14001f1cd  jns     loc_14001F293
0x14001f1d3  xor     edx, edx; bool
0x14001f1d5  mov     rcx, rdi; this
0x14001f1d8  call    ?SaveIsDeviceChannel@CMDMPushConfiguration@@AEAAJ_N@Z; CMDMPushConfiguration::SaveIsDeviceChannel(bool)
0x14001f1dd  mov     ebx, eax
0x14001f1df  test    eax, eax
0x14001f1e1  jns     short loc_14001F218
0x14001f1e3  mov     rcx, [rbp+18h]; this
0x14001f1e7  mov     r9d, eax; char *
0x14001f1ea  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x14001f1f1  mov     edx, 73Dh; void *
0x14001f1f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f1fb  nop
0x14001f1fc  mov     rcx, [rbp+var_40]
0x14001f200  test    rcx, rcx
0x14001f203  jz      short loc_14001F216
0x14001f205  mov     [rbp+var_40], r14
0x14001f209  mov     rax, [rcx]
0x14001f20c  mov     rax, [rax+10h]
0x14001f210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f215  nop
0x14001f216  jmp     short loc_14001F1A1
0x14001f218  mov     rcx, [rbp+var_40]
0x14001f21c  test    rcx, rcx
0x14001f21f  jz      short loc_14001F232
0x14001f221  mov     [rbp+var_40], r14
0x14001f225  mov     rax, [rcx]
0x14001f228  mov     rax, [rax+10h]
0x14001f22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f231  nop
0x14001f232  lea     rax, [rbp+var_40]
0x14001f236  mov     [rsp+80h+ppv], rax; int
0x14001f23b  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x14001f242  xor     edx, edx; pUnkOuter
0x14001f244  lea     r8d, [rdx+4]; dwClsContext
0x14001f248  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x14001f24f  call    cs:__imp_CoCreateInstance
0x14001f255  mov     ebx, eax
0x14001f257  test    eax, eax
0x14001f259  jns     short loc_14001F293
0x14001f25b  mov     rcx, [rbp+18h]; this
0x14001f25f  mov     r9d, eax; char *
0x14001f262  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x14001f269  mov     edx, 742h; void *
0x14001f26e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f273  nop
0x14001f274  mov     rcx, [rbp+var_40]
0x14001f278  test    rcx, rcx
0x14001f27b  jz      short loc_14001F28E
0x14001f27d  mov     [rbp+var_40], r14
0x14001f281  mov     rax, [rcx]
0x14001f284  mov     rax, [rax+10h]
0x14001f288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f28d  nop
0x14001f28e  jmp     loc_14001F1A1
0x14001f293  mov     [rbp+var_38], r14
0x14001f297  mov     rcx, [rbp+var_40]
0x14001f29b  mov     rax, [rcx]
0x14001f29e  lea     rdx, [rbp+var_38]
0x14001f2a2  mov     rax, [rax+28h]
0x14001f2a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f2ab  mov     ebx, eax
0x14001f2ad  test    eax, eax
0x14001f2af  jns     short loc_14001F303
0x14001f2b1  mov     rcx, [rbp+18h]; this
0x14001f2b5  mov     r9d, eax; char *
0x14001f2b8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x14001f2bf  mov     edx, 746h; void *
0x14001f2c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f2c9  nop
0x14001f2ca  mov     rcx, [rbp+var_38]
0x14001f2ce  test    rcx, rcx
0x14001f2d1  jz      short loc_14001F2E4
0x14001f2d3  mov     [rbp+var_38], r14
0x14001f2d7  mov     rax, [rcx]
0x14001f2da  mov     rax, [rax+10h]
0x14001f2de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f2e3  nop
0x14001f2e4  mov     rcx, [rbp+var_40]
0x14001f2e8  test    rcx, rcx
0x14001f2eb  jz      short loc_14001F2FE
0x14001f2ed  mov     [rbp+var_40], r14
0x14001f2f1  mov     rax, [rcx]
0x14001f2f4  mov     rax, [rax+10h]
0x14001f2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f2fd  nop
0x14001f2fe  jmp     loc_14001F1A1
0x14001f303  mov     [rbp+var_30], r14
0x14001f307  mov     rcx, [rbp+var_38]
0x14001f30b  mov     rax, [rcx]
0x14001f30e  lea     r8, [rbp+var_30]
0x14001f312  lea     rdx, _GUID_7d85494e_d99e_493a_bf51_80d2c9feab49
0x14001f319  mov     rax, [rax]
0x14001f31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f321  mov     ebx, eax
0x14001f323  test    eax, eax
0x14001f325  jns     short loc_14001F393
0x14001f327  mov     rcx, [rbp+18h]; this
0x14001f32b  mov     r9d, eax; char *
0x14001f32e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x14001f335  mov     edx, 749h; void *
0x14001f33a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f33f  nop
0x14001f340  mov     rcx, [rbp+var_30]
0x14001f344  test    rcx, rcx
0x14001f347  jz      short loc_14001F35A
0x14001f349  mov     [rbp+var_30], r14
0x14001f34d  mov     rax, [rcx]
0x14001f350  mov     rax, [rax+10h]
0x14001f354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f359  nop
0x14001f35a  mov     rcx, [rbp+var_38]
0x14001f35e  test    rcx, rcx
0x14001f361  jz      short loc_14001F374
0x14001f363  mov     [rbp+var_38], r14
0x14001f367  mov     rax, [rcx]
0x14001f36a  mov     rax, [rax+10h]
0x14001f36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f373  nop
0x14001f374  mov     rcx, [rbp+var_40]
0x14001f378  test    rcx, rcx
0x14001f37b  jz      short loc_14001F38E
0x14001f37d  mov     [rbp+var_40], r14
0x14001f381  mov     rax, [rcx]
0x14001f384  mov     rax, [rax+10h]
0x14001f388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f38d  nop
0x14001f38e  jmp     loc_14001F1A1
0x14001f393  mov     [rbp+bstrString], r14
0x14001f397  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x14001f39b  mov     rcx, rdi; this
0x14001f39e  call    ?GetPFN@CMDMPushConfiguration@@QEAAJPEAPEAG@Z; CMDMPushConfiguration::GetPFN(ushort * *)
0x14001f3a3  mov     ebx, eax
0x14001f3a5  test    eax, eax
0x14001f3a7  jns     loc_14001F49A
0x14001f3ad  mov     edi, 80070002h
0x14001f3b2  cmp     eax, edi
0x14001f3b4  jnz     short loc_14001F41E
0x14001f3b6  mov     rcx, [rbp+bstrString]; bstrString
0x14001f3ba  test    rcx, rcx
0x14001f3bd  jz      short loc_14001F3C6
0x14001f3bf  call    cs:__imp_SysFreeString
0x14001f3c5  nop
0x14001f3c6  mov     rcx, [rbp+var_30]
0x14001f3ca  test    rcx, rcx
0x14001f3cd  jz      short loc_14001F3E0
0x14001f3cf  mov     [rbp+var_30], r14
0x14001f3d3  mov     rax, [rcx]
0x14001f3d6  mov     rax, [rax+10h]
0x14001f3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f3df  nop
0x14001f3e0  mov     rcx, [rbp+var_38]
0x14001f3e4  test    rcx, rcx
0x14001f3e7  jz      short loc_14001F3FA
0x14001f3e9  mov     [rbp+var_38], r14
0x14001f3ed  mov     rax, [rcx]
0x14001f3f0  mov     rax, [rax+10h]
0x14001f3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f3f9  nop
0x14001f3fa  mov     rdx, [rbp+var_40]
0x14001f3fe  test    rdx, rdx
0x14001f401  jz      short loc_14001F417
0x14001f403  mov     [rbp+var_40], r14
0x14001f407  mov     rcx, [rdx]
0x14001f40a  mov     rax, [rcx+10h]
0x14001f40e  mov     rcx, rdx
0x14001f411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f416  nop
0x14001f417  mov     eax, edi
0x14001f419  jmp     loc_14001F696
0x14001f41e  mov     rcx, [rbp+18h]; this
0x14001f422  mov     r9d, ebx; char *
0x14001f425  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x14001f42c  mov     edx, 74Ch; void *
0x14001f431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f436  nop
0x14001f437  mov     rcx, [rbp+bstrString]; bstrString
0x14001f43b  test    rcx, rcx
0x14001f43e  jz      short loc_14001F447
0x14001f440  call    cs:__imp_SysFreeString
0x14001f446  nop
0x14001f447  mov     rcx, [rbp+var_30]
0x14001f44b  test    rcx, rcx
0x14001f44e  jz      short loc_14001F461
0x14001f450  mov     [rbp+var_30], r14
0x14001f454  mov     rax, [rcx]
0x14001f457  mov     rax, [rax+10h]
0x14001f45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f460  nop
0x14001f461  mov     rcx, [rbp+var_38]
0x14001f465  test    rcx, rcx
0x14001f468  jz      short loc_14001F47B
0x14001f46a  mov     [rbp+var_38], r14
0x14001f46e  mov     rax, [rcx]
0x14001f471  mov     rax, [rax+10h]
0x14001f475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f47a  nop
0x14001f47b  mov     rcx, [rbp+var_40]
0x14001f47f  test    rcx, rcx
0x14001f482  jz      short loc_14001F495
0x14001f484  mov     [rbp+var_40], r14
0x14001f488  mov     rax, [rcx]
0x14001f48b  mov     rax, [rax+10h]
0x14001f48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f494  nop
0x14001f495  jmp     loc_14001F1A1
0x14001f49a  mov     [rbp+var_20], r14
0x14001f49e  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x14001f4a2  mov     rcx, rdi; this
0x14001f4a5  call    ?GetAppId@CMDMPushConfiguration@@QEAAJPEAPEAG@Z; CMDMPushConfiguration::GetAppId(ushort * *)
0x14001f4aa  mov     ebx, eax
0x14001f4ac  test    eax, eax
0x14001f4ae  jns     loc_14001F540
0x14001f4b4  mov     rcx, [rbp+18h]; this
0x14001f4b8  mov     r9d, eax; char *
0x14001f4bb  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x14001f4c2  mov     edx, 74Fh; void *
0x14001f4c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f4cc  nop
0x14001f4cd  mov     rcx, [rbp+var_20]; bstrString
0x14001f4d1  test    rcx, rcx
0x14001f4d4  jz      short loc_14001F4DD
0x14001f4d6  call    cs:__imp_SysFreeString
0x14001f4dc  nop
0x14001f4dd  mov     rcx, [rbp+bstrString]; bstrString
0x14001f4e1  test    rcx, rcx
0x14001f4e4  jz      short loc_14001F4ED
0x14001f4e6  call    cs:__imp_SysFreeString
0x14001f4ec  nop
0x14001f4ed  mov     rcx, [rbp+var_30]
0x14001f4f1  test    rcx, rcx
0x14001f4f4  jz      short loc_14001F507
0x14001f4f6  mov     [rbp+var_30], r14
0x14001f4fa  mov     rax, [rcx]
0x14001f4fd  mov     rax, [rax+10h]
0x14001f501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f506  nop
0x14001f507  mov     rcx, [rbp+var_38]
0x14001f50b  test    rcx, rcx
0x14001f50e  jz      short loc_14001F521
0x14001f510  mov     [rbp+var_38], r14
0x14001f514  mov     rax, [rcx]
0x14001f517  mov     rax, [rax+10h]
0x14001f51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f520  nop
0x14001f521  mov     rcx, [rbp+var_40]
0x14001f525  test    rcx, rcx
0x14001f528  jz      short loc_14001F53B
0x14001f52a  mov     [rbp+var_40], r14
0x14001f52e  mov     rax, [rcx]
0x14001f531  mov     rax, [rax+10h]
0x14001f535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f53a  nop
0x14001f53b  jmp     loc_14001F1A1
  ... truncated ...
```
