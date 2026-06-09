# UserOperationsImpl::ResetPin(HWND__ *,ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x180017380`
- end: `0x1800176fa`
- name: `?ResetPin@UserOperationsImpl@@UEAAJPEAUHWND__@@PEBG1K1@Z`
- size: `890`
- prototype: `__int64 __fastcall(UserOperationsImpl *__hidden this, HWND, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x18000fae0`
- `0x1800122ac`
- `0x180017380`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800173cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001753f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800173cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001753f`

## string_xrefs

- `0x1800173e0`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180017458`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x1800174d7`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x180017552`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x1800175dc`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`
- `0x18001765c`: `shell\cloudexperiencehost\broker\lib\useroperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall UserOperationsImpl::ResetPin(
        UserOperationsImpl *this,
        HWND a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6)
{
  HRESULT v9; // eax
  unsigned int v10; // ebx
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, GUID *, GUID *, __int64 **); // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rcx
  _BYTE *v17; // rdx
  HRESULT v18; // eax
  __int64 v19; // rcx
  _BYTE *v20; // rdx
  LPVOID v21; // rdi
  __int64 (__fastcall *v22)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rcx
  _BYTE *v25; // rdx
  int v26; // eax
  __int64 v27; // rcx
  _BYTE *v28; // rdx
  __int64 v29; // rcx
  _BYTE *v30; // rdx
  int ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  _BYTE *v33; // [rsp+30h] [rbp-40h] BYREF
  LPVOID v34; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v35; // [rsp+40h] [rbp-30h] BYREF
  LPVOID v36; // [rsp+48h] [rbp-28h] BYREF
  __int64 v37; // [rsp+50h] [rbp-20h] BYREF
  _QWORD *v38; // [rsp+58h] [rbp-18h] BYREF
  __int64 v39; // [rsp+60h] [rbp-10h] BYREF
  char v40; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v33 = 0;
  v34 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v9 = CoCreateInstance(
         &GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e,
         0,
         1u,
         &GUID_10316cc3_d36e_46cd_8344_d85f12419862,
         &v34);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v33 = 0;
    return v10;
  }
  v35 = 0;
  v12 = v34;
  v13 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 **))(*(_QWORD *)v34 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  v14 = v13(v12, &GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2, &GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f, &v35);
  v10 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v14,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v33 = 0;
    return v10;
  }
  v15 = *v35;
  v38 = &v33;
  v39 = 0;
  v40 = 1;
  v10 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, const unsigned __int16 *, __int64 *))(v15 + 96))(
          v35,
          a4,
          a6,
          &v39);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>(&v38);
  if ( (v10 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)v10,
      ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v17 = v33;
    v33 = 0;
    if ( v17 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v16, v17);
    return v10;
  }
  v36 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  v18 = CoCreateInstance(
          &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
          0,
          1u,
          &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
          &v36);
  v10 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C6,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v18,
      ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v20 = v33;
    v33 = 0;
    if ( v20 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v19, v20);
    return v10;
  }
  v37 = 0;
  v21 = v36;
  v22 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v36 + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  v23 = v22(v21, &GUID_e19af835_9413_48a3_bdcc_28ba0286e348, &GUID_dee152d9_40a4_4bf9_8ac3_62cf1bb2203b, &v37);
  v10 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v23,
      ppva);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v25 = v33;
    v33 = 0;
    if ( v25 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v24, v25);
    return v10;
  }
  v26 = (*(__int64 (__fastcall **)(__int64, HWND, const unsigned __int16 *, _BYTE *))(*(_QWORD *)v37 + 40LL))(
          v37,
          a2,
          a3,
          v33);
  v10 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CB,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\useroperations.cpp",
      (const char *)(unsigned int)v26,
      a5);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v28 = v33;
    v33 = 0;
    if ( v28 )
      wil::cotaskmem_secure_deleter::operator()<unsigned short>(v27, v28);
    return v10;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  v30 = v33;
  v33 = 0;
  if ( v30 )
    wil::cotaskmem_secure_deleter::operator()<unsigned short>(v29, v30);
  return 0;
}

```

## disassembly

```asm
0x180017380  push    rbp
0x180017382  push    rbx
0x180017383  push    rsi
0x180017384  push    rdi
0x180017385  push    r12
0x180017387  push    r14
0x180017389  push    r15
0x18001738b  mov     rbp, rsp
0x18001738e  sub     rsp, 70h
0x180017392  mov     rsi, r9
0x180017395  mov     r14, r8
0x180017398  mov     r15, rdx
0x18001739b  xor     r12d, r12d
0x18001739e  mov     [rbp+var_40], r12
0x1800173a2  mov     [rbp+var_38], r12
0x1800173a6  lea     rcx, [rbp+var_38]
0x1800173aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800173af  lea     rax, [rbp+var_38]
0x1800173b3  mov     qword ptr [rsp+70h+ppv], rax; int
0x1800173b8  lea     r9, _GUID_10316cc3_d36e_46cd_8344_d85f12419862; riid
0x1800173bf  xor     edx, edx; pUnkOuter
0x1800173c1  lea     r8d, [r12+1]; dwClsContext
0x1800173c6  lea     rcx, _GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e; rclsid
0x1800173cd  call    cs:__imp_CoCreateInstance
0x1800173d3  mov     ebx, eax
0x1800173d5  test    eax, eax
0x1800173d7  jns     short loc_180017416
0x1800173d9  mov     rcx, [rbp+38h]; this
0x1800173dd  mov     r9d, eax; char *
0x1800173e0  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800173e7  mov     edx, 1BEh; void *
0x1800173ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173f1  nop
0x1800173f2  lea     rcx, [rbp+var_38]
0x1800173f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800173fb  nop
0x1800173fc  mov     rdx, [rbp+var_40]
0x180017400  mov     [rbp+var_40], r12
0x180017404  test    rdx, rdx
0x180017407  jz      short loc_18001740F
0x180017409  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18001740e  nop
0x18001740f  mov     eax, ebx
0x180017411  jmp     loc_1800176EB
0x180017416  mov     [rbp+var_30], r12
0x18001741a  mov     rdi, [rbp+var_38]
0x18001741e  mov     rax, [rdi]
0x180017421  mov     rbx, [rax+18h]
0x180017425  lea     rcx, [rbp+var_30]
0x180017429  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001742e  lea     r9, [rbp+var_30]
0x180017432  lea     r8, _GUID_381d73bb_f00c_42e2_9d9c_5b5b3d88d71f
0x180017439  lea     rdx, _GUID_e1f5aa5b_065c_4e29_b454_c1bbfe0819d2
0x180017440  mov     rcx, rdi
0x180017443  mov     rax, rbx
0x180017446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001744b  mov     ebx, eax
0x18001744d  test    eax, eax
0x18001744f  jns     short loc_180017496
0x180017451  mov     rcx, [rbp+38h]; this
0x180017455  mov     r9d, eax; char *
0x180017458  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x18001745f  mov     edx, 1C1h; void *
0x180017464  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017469  nop
0x18001746a  lea     rcx, [rbp+var_30]
0x18001746e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017473  nop
0x180017474  lea     rcx, [rbp+var_38]
0x180017478  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001747d  nop
0x18001747e  mov     rdx, [rbp+var_40]
0x180017482  mov     [rbp+var_40], r12
0x180017486  test    rdx, rdx
0x180017489  jz      short loc_180017491
0x18001748b  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180017490  nop
0x180017491  jmp     loc_18001740F
0x180017496  mov     rcx, [rbp+var_30]
0x18001749a  mov     rax, [rcx]
0x18001749d  lea     rdx, [rbp+var_40]
0x1800174a1  mov     [rbp+var_18], rdx
0x1800174a5  mov     [rbp+var_10], r12
0x1800174a9  mov     [rbp+var_8], 1
0x1800174ad  lea     r9, [rbp+var_10]
0x1800174b1  mov     r8, [rbp+arg_28]
0x1800174b5  mov     rdx, rsi
0x1800174b8  mov     rax, [rax+60h]
0x1800174bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174c1  mov     ebx, eax
0x1800174c3  lea     rcx, [rbp+var_18]
0x1800174c7  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUcotaskmem_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::cotaskmem_secure_deleter>>(void)
0x1800174cc  test    ebx, ebx
0x1800174ce  jns     short loc_180017515
0x1800174d0  mov     rcx, [rbp+38h]; this
0x1800174d4  mov     r9d, ebx; char *
0x1800174d7  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800174de  mov     edx, 1C3h; void *
0x1800174e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174e8  nop
0x1800174e9  lea     rcx, [rbp+var_30]
0x1800174ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800174f2  nop
0x1800174f3  lea     rcx, [rbp+var_38]
0x1800174f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800174fc  nop
0x1800174fd  mov     rdx, [rbp+var_40]
0x180017501  mov     [rbp+var_40], r12
0x180017505  test    rdx, rdx
0x180017508  jz      short loc_180017510
0x18001750a  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18001750f  nop
0x180017510  jmp     loc_18001740F
0x180017515  mov     [rbp+var_28], r12
0x180017519  lea     rcx, [rbp+var_28]
0x18001751d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017522  lea     rax, [rbp+var_28]
0x180017526  mov     qword ptr [rsp+70h+ppv], rax; int
0x18001752b  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x180017532  xor     edx, edx; pUnkOuter
0x180017534  lea     r8d, [rdx+1]; dwClsContext
0x180017538  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x18001753f  call    cs:__imp_CoCreateInstance
0x180017545  mov     ebx, eax
0x180017547  test    eax, eax
0x180017549  jns     short loc_18001759A
0x18001754b  mov     rcx, [rbp+38h]; this
0x18001754f  mov     r9d, eax; char *
0x180017552  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180017559  mov     edx, 1C6h; void *
0x18001755e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017563  nop
0x180017564  lea     rcx, [rbp+var_28]
0x180017568  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001756d  nop
0x18001756e  lea     rcx, [rbp+var_30]
0x180017572  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017577  nop
0x180017578  lea     rcx, [rbp+var_38]
0x18001757c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017581  nop
0x180017582  mov     rdx, [rbp+var_40]
0x180017586  mov     [rbp+var_40], r12
0x18001758a  test    rdx, rdx
0x18001758d  jz      short loc_180017595
0x18001758f  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180017594  nop
0x180017595  jmp     loc_18001740F
0x18001759a  mov     [rbp+var_20], r12
0x18001759e  mov     rdi, [rbp+var_28]
0x1800175a2  mov     rax, [rdi]
0x1800175a5  mov     rbx, [rax+20h]
0x1800175a9  lea     rcx, [rbp+var_20]
0x1800175ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800175b2  lea     r9, [rbp+var_20]
0x1800175b6  lea     r8, _GUID_dee152d9_40a4_4bf9_8ac3_62cf1bb2203b
0x1800175bd  lea     rdx, _GUID_e19af835_9413_48a3_bdcc_28ba0286e348
0x1800175c4  mov     rcx, rdi
0x1800175c7  mov     rax, rbx
0x1800175ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175cf  mov     ebx, eax
0x1800175d1  test    eax, eax
0x1800175d3  jns     short loc_18001762E
0x1800175d5  mov     rcx, [rbp+38h]; this
0x1800175d9  mov     r9d, eax; char *
0x1800175dc  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800175e3  mov     edx, 1C9h; void *
0x1800175e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800175ed  nop
0x1800175ee  lea     rcx, [rbp+var_20]
0x1800175f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800175f7  nop
0x1800175f8  lea     rcx, [rbp+var_28]
0x1800175fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017601  nop
0x180017602  lea     rcx, [rbp+var_30]
0x180017606  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001760b  nop
0x18001760c  lea     rcx, [rbp+var_38]
0x180017610  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017615  nop
0x180017616  mov     rdx, [rbp+var_40]
0x18001761a  mov     [rbp+var_40], r12
0x18001761e  test    rdx, rdx
0x180017621  jz      short loc_180017629
0x180017623  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180017628  nop
0x180017629  jmp     loc_18001740F
0x18001762e  mov     rcx, [rbp+var_20]
0x180017632  mov     rax, [rcx]
0x180017635  mov     edx, [rbp+arg_20]
0x180017638  mov     [rsp+70h+ppv], edx; int
0x18001763c  mov     r9, [rbp+var_40]
0x180017640  mov     r8, r14
0x180017643  mov     rdx, r15
0x180017646  mov     rax, [rax+28h]
0x18001764a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001764f  mov     ebx, eax
0x180017651  test    eax, eax
0x180017653  jns     short loc_1800176AE
0x180017655  mov     rcx, [rbp+38h]; this
0x180017659  mov     r9d, eax; char *
0x18001765c  lea     r8, aShellCloudexpe_2; "shell\\cloudexperiencehost\\broker\\lib"...
0x180017663  mov     edx, 1CBh; void *
0x180017668  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001766d  nop
0x18001766e  lea     rcx, [rbp+var_20]
0x180017672  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017677  nop
0x180017678  lea     rcx, [rbp+var_28]
0x18001767c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017681  nop
0x180017682  lea     rcx, [rbp+var_30]
0x180017686  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001768b  nop
0x18001768c  lea     rcx, [rbp+var_38]
0x180017690  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017695  nop
0x180017696  mov     rdx, [rbp+var_40]
0x18001769a  mov     [rbp+var_40], r12
0x18001769e  test    rdx, rdx
0x1800176a1  jz      short loc_1800176A9
0x1800176a3  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x1800176a8  nop
0x1800176a9  jmp     loc_18001740F
0x1800176ae  lea     rcx, [rbp+var_20]
0x1800176b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800176b7  nop
0x1800176b8  lea     rcx, [rbp+var_28]
0x1800176bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800176c1  nop
0x1800176c2  lea     rcx, [rbp+var_30]
0x1800176c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800176cb  nop
0x1800176cc  lea     rcx, [rbp+var_38]
0x1800176d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800176d5  nop
0x1800176d6  mov     rdx, [rbp+var_40]
0x1800176da  mov     [rbp+var_40], r12
0x1800176de  test    rdx, rdx
0x1800176e1  jz      short loc_1800176E9
0x1800176e3  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x1800176e8  nop
0x1800176e9  xor     eax, eax
0x1800176eb  add     rsp, 70h
0x1800176ef  pop     r15
0x1800176f1  pop     r14
0x1800176f3  pop     r12
0x1800176f5  pop     rdi
0x1800176f6  pop     rsi
0x1800176f7  pop     rbx
0x1800176f8  pop     rbp
0x1800176f9  retn
```
