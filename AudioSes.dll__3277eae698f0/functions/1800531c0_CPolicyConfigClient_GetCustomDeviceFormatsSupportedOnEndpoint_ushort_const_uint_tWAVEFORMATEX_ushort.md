# CPolicyConfigClient::GetCustomDeviceFormatsSupportedOnEndpoint(ushort const *,uint *,tWAVEFORMATEX * * *,ushort * * *)

- ea: `0x1800531c0`
- end: `0x180053601`
- name: `?GetCustomDeviceFormatsSupportedOnEndpoint@CPolicyConfigClient@@UEAAJPEBGPEAIPEAPEAPEAUtWAVEFORMATEX@@PEAPEAPEAG@Z`
- size: `1089`
- prototype: `__int64 __fastcall(CPolicyConfigClient *__hidden this, const unsigned __int16 *, unsigned int *, struct tWAVEFORMATEX ***, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000da68`
- `0x18000f700`
- `0x180010a90`
- `0x180011d0c`
- `0x180011e7c`
- `0x180020400`
- `0x1800531c0`
- `0x180053608`
- `0x180071a84`
- `0x180077248`
- `0x180088ce8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800532c4`
- `RPCRT4!RpcBindingFree` at `0x180053319`
- `RPCRT4!RpcBindingFree` at `0x180053413`
- `RPCRT4!RpcBindingFree` at `0x1800532c4`
- `RPCRT4!RpcBindingFree` at `0x180053319`
- `RPCRT4!RpcBindingFree` at `0x180053413`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005334e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005334e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005344c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005345d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800534d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800534e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005344c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005345d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800534d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800534e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800535ee`

## string_xrefs

- `0x180053293`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x1800532f2`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x180053367`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x180053427`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x1800534b2`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x180053543`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPolicyConfigClient::GetCustomDeviceFormatsSupportedOnEndpoint(
        CPolicyConfigClient *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        struct tWAVEFORMATEX ***a4,
        unsigned __int16 ***a5)
{
  int AudioServerBindingHandle; // eax
  unsigned int v8; // ebx
  int v9; // eax
  void *v10; // rax
  void *v12; // rax
  unsigned int i; // ebx
  unsigned int n; // ebx
  unsigned int ii; // ebx
  unsigned int jj; // edi
  unsigned int j; // ebx
  unsigned int k; // ebx
  unsigned int m; // edi
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // esi
  int v24; // eax
  void *v25; // [rsp+28h] [rbp-61h] BYREF
  void *v26; // [rsp+30h] [rbp-59h] BYREF
  LPVOID v27; // [rsp+38h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-49h] BYREF
  void *v29; // [rsp+48h] [rbp-41h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-39h] BYREF
  void **v31; // [rsp+58h] [rbp-31h] BYREF
  void **v32; // [rsp+60h] [rbp-29h]
  void **v33; // [rsp+68h] [rbp-21h]
  void **v34; // [rsp+70h] [rbp-19h]
  void **v35; // [rsp+78h] [rbp-11h]
  _QWORD v36[2]; // [rsp+80h] [rbp-9h] BYREF
  char v37; // [rsp+90h] [rbp+7h]
  unsigned int *v38; // [rsp+98h] [rbp+Fh]
  LPVOID *p_pv; // [rsp+A0h] [rbp+17h]
  char v40; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+57h]
  const unsigned __int16 *v42; // [rsp+F0h] [rbp+67h] BYREF
  unsigned int v43; // [rsp+F8h] [rbp+6Fh] BYREF

  v42 = a2;
  v26 = 0;
  v25 = 0;
  v43 = 0;
  *a3 = 0;
  v29 = 0;
  AudioServerBindingHandle = GetAudioServerBindingHandle((const unsigned __int16 *)this, L"Audiosrv", &v29);
  v8 = AudioServerBindingHandle;
  if ( AudioServerBindingHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A8,
      (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
      (const char *)(unsigned int)AudioServerBindingHandle,
      (int)v25);
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v29);
    return v8;
  }
  v31 = &v29;
  v32 = (void **)&v42;
  v33 = (void **)&v43;
  v34 = &v26;
  v35 = &v25;
  v9 = lambda_fde01ebb8183a1f02858741bba0a1e62_::operator()(&v31);
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B1,
      (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
      (const char *)(unsigned int)v9,
      (int)v25);
    if ( v29 )
    {
      Binding = v29;
      RpcBindingFree(&Binding);
    }
    return v8;
  }
  v31 = (void **)&v43;
  v32 = &v25;
  v33 = &v26;
  LOBYTE(v34) = 1;
  v10 = CoTaskMemAlloc(8LL * v43);
  v27 = v10;
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BE,
      (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
      (const char *)0x8007000ELL,
      (int)v25);
    LOBYTE(v34) = 0;
    lambda_d5ec5dc934c77e5aa62a06f9f058ea4d_::operator()(&v31);
    if ( !v29 )
      return 2147942414LL;
    Binding = v29;
LABEL_6:
    RpcBindingFree(&Binding);
    return 2147942414LL;
  }
  memset_0(v10, 0, 8LL * v43);
  v36[0] = &v43;
  v36[1] = &v27;
  v37 = 1;
  v12 = CoTaskMemAlloc(8LL * v43);
  pv = v12;
  if ( !v12 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5CA,
      (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
      (const char *)0x8007000ELL,
      (int)v25);
    v37 = 0;
    lambda_a8e4987fc1a745b4ca7aef4c69d8b4c7_::operator()(v36);
    LOBYTE(v34) = 0;
    lambda_d5ec5dc934c77e5aa62a06f9f058ea4d_::operator()(&v31);
    if ( !v29 )
      return 2147942414LL;
    Binding = v29;
    goto LABEL_6;
  }
  memset_0(v12, 0, 8LL * v43);
  v38 = &v43;
  p_pv = &pv;
  v40 = 1;
  for ( i = 0; i < v43; ++i )
  {
    v20 = CloneWaveFormat(*((const struct tWAVEFORMATEX **)v26 + i), (struct tWAVEFORMATEX **)v27 + i);
    v23 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D7,
        (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
        (const char *)(unsigned int)v20,
        (int)v25);
      for ( j = 0; j < v43; ++j )
        CoTaskMemFree(*((LPVOID *)pv + j));
      CoTaskMemFree(pv);
      for ( k = 0; k < v43; ++k )
        CoTaskMemFree(*((LPVOID *)v27 + k));
      CoTaskMemFree(v27);
      for ( m = 0; m < v43; ++m )
      {
        operator delete(*((void **)v25 + m));
        operator delete(*((void **)v26 + m));
      }
      goto LABEL_23;
    }
    v24 = _AllocString<CTCoAllocPolicy>(v22, v21, *((_QWORD *)v25 + i), (char *)pv + 8 * i);
    v23 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D9,
        (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
        (const char *)(unsigned int)v24,
        (int)v25);
      for ( n = 0; n < v43; ++n )
        CoTaskMemFree(*((LPVOID *)pv + n));
      CoTaskMemFree(pv);
      for ( ii = 0; ii < v43; ++ii )
        CoTaskMemFree(*((LPVOID *)v27 + ii));
      CoTaskMemFree(v27);
      for ( jj = 0; jj < v43; ++jj )
      {
        operator delete(*((void **)v25 + jj));
        operator delete(*((void **)v26 + jj));
      }
LABEL_23:
      operator delete(v25);
      operator delete(v26);
      v8 = v23;
      goto LABEL_24;
    }
  }
  *a3 = v43;
  *a4 = (struct tWAVEFORMATEX **)v27;
  *a5 = (unsigned __int16 **)pv;
  LOBYTE(v34) = 0;
  lambda_d5ec5dc934c77e5aa62a06f9f058ea4d_::operator()(&v31);
  if ( v29 )
  {
    Binding = v29;
    RpcBindingFree(&Binding);
  }
  return 0;
}

```

## disassembly

```asm
0x1800531c0  mov     rax, rsp
0x1800531c3  mov     [rax+8], rbx
0x1800531c7  mov     [rax+20h], rsi
0x1800531cb  mov     [rax+10h], rdx
0x1800531cf  push    rbp
0x1800531d0  push    rdi
0x1800531d1  push    r12
0x1800531d3  push    r14
0x1800531d5  push    r15
0x1800531d7  lea     rbp, [rax-57h]
0x1800531db  sub     rsp, 0B0h
0x1800531e2  mov     r15, r9
0x1800531e5  mov     r14, r8
0x1800531e8  xor     r12d, r12d
0x1800531eb  mov     [rbp+4Fh+var_A8], r12
0x1800531ef  mov     [rbp+4Fh+var_B0], r12
0x1800531f3  mov     [rbp+4Fh+arg_10], r12d
0x1800531f7  mov     [r8], r12d
0x1800531fa  mov     [rbp+4Fh+var_90], r12
0x1800531fe  lea     r8, [rbp+4Fh+var_90]; void **
0x180053202  lea     rdx, aAudiosrv_0; "Audiosrv"
0x180053209  call    ?GetAudioServerBindingHandle@@YAJPEBG0PEAPEAX@Z; GetAudioServerBindingHandle(ushort const *,ushort const *,void * *)
0x18005320e  mov     ebx, eax
0x180053210  test    eax, eax
0x180053212  js      loc_18005353C
0x180053218  lea     rax, [rbp+4Fh+var_90]
0x18005321c  mov     [rbp+4Fh+var_80], rax
0x180053220  lea     rax, [rbp+4Fh+arg_8]
0x180053224  mov     [rbp+4Fh+var_78], rax
0x180053228  lea     rax, [rbp+4Fh+arg_10]
0x18005322c  mov     [rbp+4Fh+var_70], rax
0x180053230  lea     rax, [rbp+4Fh+var_A8]
0x180053234  mov     [rbp+4Fh+var_68], rax
0x180053238  lea     rax, [rbp+4Fh+var_B0]
0x18005323c  mov     [rbp+4Fh+var_60], rax
0x180053240  lea     rcx, [rbp+4Fh+var_80]
0x180053244  call    _lambda_fde01ebb8183a1f02858741bba0a1e62___operator__
0x180053249  mov     ebx, eax
0x18005324b  test    eax, eax
0x18005324d  js      loc_1800532EB
0x180053253  lea     rax, [rbp+4Fh+arg_10]
0x180053257  mov     [rbp+4Fh+var_80], rax
0x18005325b  lea     rax, [rbp+4Fh+var_B0]
0x18005325f  mov     [rbp+4Fh+var_78], rax
0x180053263  lea     rax, [rbp+4Fh+var_A8]
0x180053267  mov     [rbp+4Fh+var_70], rax
0x18005326b  mov     byte ptr [rbp+4Fh+var_68], 1
0x18005326f  mov     ecx, [rbp+4Fh+arg_10]
0x180053272  shl     rcx, 3; cb
0x180053276  call    cs:__imp_CoTaskMemAlloc
0x18005327c  mov     [rbp+4Fh+var_A0], rax
0x180053280  test    rax, rax
0x180053283  jnz     loc_180053321
0x180053289  mov     rcx, [rbp+57h]; this
0x18005328d  mov     r9d, 8007000Eh; char *
0x180053293  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x18005329a  mov     edx, 5BEh; void *
0x18005329f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800532a4  nop
0x1800532a5  mov     byte ptr [rbp+4Fh+var_68], r12b
0x1800532a9  lea     rcx, [rbp+4Fh+var_80]
0x1800532ad  call    _lambda_d5ec5dc934c77e5aa62a06f9f058ea4d___operator__
0x1800532b2  nop
0x1800532b3  mov     rax, [rbp+4Fh+var_90]
0x1800532b7  test    rax, rax
0x1800532ba  jz      short loc_1800532CA
0x1800532bc  mov     [rbp+4Fh+Binding], rax
0x1800532c0  lea     rcx, [rbp+4Fh+Binding]; Binding
0x1800532c4  call    cs:__imp_RpcBindingFree
0x1800532ca  mov     eax, 8007000Eh
0x1800532cf  lea     r11, [rsp+0D0h+var_20]
0x1800532d7  mov     rbx, [r11+30h]
0x1800532db  mov     rsi, [r11+48h]
0x1800532df  mov     rsp, r11
0x1800532e2  pop     r15
0x1800532e4  pop     r14
0x1800532e6  pop     r12
0x1800532e8  pop     rdi
0x1800532e9  pop     rbp
0x1800532ea  retn
0x1800532eb  mov     rcx, [rbp+57h]; this
0x1800532ef  mov     r9d, ebx; char *
0x1800532f2  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x1800532f9  mov     edx, 5B1h; void *
0x1800532fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053303  nop
0x180053304  mov     rcx, [rbp+4Fh+var_90]
0x180053308  test    rcx, rcx
0x18005330b  jnz     short loc_180053311
0x18005330d  mov     eax, ebx
0x18005330f  jmp     short loc_1800532CF
0x180053311  mov     [rbp+4Fh+Binding], rcx
0x180053315  lea     rcx, [rbp+4Fh+Binding]; Binding
0x180053319  call    cs:__imp_RpcBindingFree
0x18005331f  jmp     short loc_18005330D
0x180053321  mov     r8d, [rbp+4Fh+arg_10]
0x180053325  shl     r8, 3; Size
0x180053329  xor     edx, edx; Val
0x18005332b  mov     rcx, rax; void *
0x18005332e  call    memset_0
0x180053333  lea     rax, [rbp+4Fh+arg_10]
0x180053337  mov     [rbp+4Fh+var_58], rax
0x18005333b  lea     rax, [rbp+4Fh+var_A0]
0x18005333f  mov     [rbp+4Fh+var_50], rax
0x180053343  mov     [rbp+4Fh+var_48], 1
0x180053347  mov     ecx, [rbp+4Fh+arg_10]
0x18005334a  shl     rcx, 3; cb
0x18005334e  call    cs:__imp_CoTaskMemAlloc
0x180053354  mov     [rbp+4Fh+pv], rax
0x180053358  test    rax, rax
0x18005335b  jnz     short loc_1800533AB
0x18005335d  mov     rcx, [rbp+57h]; this
0x180053361  mov     r9d, 8007000Eh; char *
0x180053367  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x18005336e  mov     edx, 5CAh; void *
0x180053373  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053378  nop
0x180053379  mov     [rbp+4Fh+var_48], r12b
0x18005337d  lea     rcx, [rbp+4Fh+var_58]
0x180053381  call    _lambda_a8e4987fc1a745b4ca7aef4c69d8b4c7___operator__
0x180053386  nop
0x180053387  mov     byte ptr [rbp+4Fh+var_68], r12b
0x18005338b  lea     rcx, [rbp+4Fh+var_80]
0x18005338f  call    _lambda_d5ec5dc934c77e5aa62a06f9f058ea4d___operator__
0x180053394  nop
0x180053395  mov     rcx, [rbp+4Fh+var_90]
0x180053399  test    rcx, rcx
0x18005339c  jz      loc_1800532CA
0x1800533a2  mov     [rbp+4Fh+Binding], rcx
0x1800533a6  jmp     loc_1800532C0
0x1800533ab  mov     r8d, [rbp+4Fh+arg_10]
0x1800533af  shl     r8, 3; Size
0x1800533b3  xor     edx, edx; Val
0x1800533b5  mov     rcx, rax; void *
0x1800533b8  call    memset_0
0x1800533bd  lea     rax, [rbp+4Fh+arg_10]
0x1800533c1  mov     [rbp+4Fh+var_40], rax
0x1800533c5  lea     rax, [rbp+4Fh+pv]
0x1800533c9  mov     [rbp+4Fh+var_38], rax
0x1800533cd  mov     [rbp+4Fh+var_30], 1
0x1800533d1  mov     ebx, r12d
0x1800533d4  mov     eax, [rbp+4Fh+arg_10]
0x1800533d7  cmp     ebx, eax
0x1800533d9  jb      loc_180053559
0x1800533df  mov     [r14], eax
0x1800533e2  mov     rax, [rbp+4Fh+var_A0]
0x1800533e6  mov     [r15], rax
0x1800533e9  mov     rcx, [rbp+4Fh+arg_20]
0x1800533ed  mov     rax, [rbp+4Fh+pv]
0x1800533f1  mov     [rcx], rax
0x1800533f4  mov     byte ptr [rbp+4Fh+var_68], r12b
0x1800533f8  lea     rcx, [rbp+4Fh+var_80]
0x1800533fc  call    _lambda_d5ec5dc934c77e5aa62a06f9f058ea4d___operator__
0x180053401  nop
0x180053402  mov     rax, [rbp+4Fh+var_90]
0x180053406  test    rax, rax
0x180053409  jz      short loc_180053419
0x18005340b  mov     [rbp+4Fh+Binding], rax
0x18005340f  lea     rcx, [rbp+4Fh+Binding]; Binding
0x180053413  call    cs:__imp_RpcBindingFree
0x180053419  xor     eax, eax
0x18005341b  jmp     loc_1800532CF
0x180053420  mov     rcx, [rbp+57h]; this
0x180053424  mov     r9d, esi; char *
0x180053427  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x18005342e  mov     edx, 5D9h; void *
0x180053433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053438  nop
0x180053439  mov     ebx, r12d
0x18005343c  cmp     [rbp+4Fh+arg_10], r12d
0x180053440  jbe     short loc_180053459
0x180053442  mov     eax, ebx
0x180053444  mov     rcx, [rbp+4Fh+pv]
0x180053448  mov     rcx, [rcx+rax*8]; pv
0x18005344c  call    cs:__imp_CoTaskMemFree
0x180053452  inc     ebx
0x180053454  cmp     ebx, [rbp+4Fh+arg_10]
0x180053457  jb      short loc_180053442
0x180053459  mov     rcx, [rbp+4Fh+pv]; pv
0x18005345d  call    cs:__imp_CoTaskMemFree
0x180053463  nop
0x180053464  mov     ebx, r12d
0x180053467  cmp     [rbp+4Fh+arg_10], r12d
0x18005346b  ja      loc_1800535A0
0x180053471  mov     rcx, [rbp+4Fh+var_A0]; pv
0x180053475  call    cs:__imp_CoTaskMemFree
0x18005347b  nop
0x18005347c  mov     edi, r12d
0x18005347f  cmp     [rbp+4Fh+arg_10], r12d
0x180053483  ja      loc_1800535BC
0x180053489  mov     rcx, [rbp+4Fh+var_B0]; void *
0x18005348d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053492  mov     rcx, [rbp+4Fh+var_A8]; void *
0x180053496  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005349b  mov     ebx, esi
0x18005349d  lea     rcx, [rbp+4Fh+var_90]
0x1800534a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800534a6  jmp     loc_18005330D
0x1800534ab  mov     rcx, [rbp+57h]; this
0x1800534af  mov     r9d, esi; char *
0x1800534b2  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x1800534b9  mov     edx, 5D7h; void *
0x1800534be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800534c3  nop
0x1800534c4  mov     ebx, r12d
0x1800534c7  cmp     [rbp+4Fh+arg_10], r12d
0x1800534cb  jbe     short loc_1800534E4
0x1800534cd  mov     eax, ebx
0x1800534cf  mov     rcx, [rbp+4Fh+pv]
0x1800534d3  mov     rcx, [rcx+rax*8]; pv
0x1800534d7  call    cs:__imp_CoTaskMemFree
0x1800534dd  inc     ebx
0x1800534df  cmp     ebx, [rbp+4Fh+arg_10]
0x1800534e2  jb      short loc_1800534CD
0x1800534e4  mov     rcx, [rbp+4Fh+pv]; pv
0x1800534e8  call    cs:__imp_CoTaskMemFree
0x1800534ee  nop
0x1800534ef  mov     ebx, r12d
0x1800534f2  cmp     [rbp+4Fh+arg_10], r12d
0x1800534f6  ja      loc_1800535E4
0x1800534fc  mov     rcx, [rbp+4Fh+var_A0]; pv
0x180053500  call    cs:__imp_CoTaskMemFree
0x180053506  nop
0x180053507  mov     edi, r12d
0x18005350a  cmp     [rbp+4Fh+arg_10], r12d
0x18005350e  jbe     loc_180053489
0x180053514  mov     ebx, edi
0x180053516  mov     rcx, [rbp+4Fh+var_B0]
0x18005351a  mov     rcx, [rcx+rbx*8]; void *
0x18005351e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053523  mov     rcx, [rbp+4Fh+var_A8]
0x180053527  mov     rcx, [rcx+rbx*8]; void *
0x18005352b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180053530  inc     edi
0x180053532  cmp     edi, [rbp+4Fh+arg_10]
0x180053535  jb      short loc_180053514
0x180053537  jmp     loc_180053489
0x18005353c  mov     rcx, [rbp+57h]; this
0x180053540  mov     r9d, eax; char *
0x180053543  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x18005354a  mov     edx, 5A8h; void *
0x18005354f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053554  jmp     loc_18005349D
0x180053559  mov     edi, ebx
0x18005355b  mov     rax, [rbp+4Fh+var_A0]
0x18005355f  lea     rdx, [rax+rdi*8]; struct tWAVEFORMATEX **
0x180053563  mov     rcx, [rbp+4Fh+var_A8]
0x180053567  mov     rcx, [rcx+rdi*8]; Src
0x18005356b  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180053570  mov     esi, eax
0x180053572  test    eax, eax
0x180053574  js      loc_1800534AB
0x18005357a  mov     rax, [rbp+4Fh+pv]
0x18005357e  lea     r9, [rax+rdi*8]
0x180053582  mov     r8, [rbp+4Fh+var_B0]
0x180053586  mov     r8, [r8+rdi*8]
0x18005358a  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18005358f  mov     esi, eax
0x180053591  test    eax, eax
0x180053593  js      loc_180053420
0x180053599  inc     ebx
0x18005359b  jmp     loc_1800533D4
0x1800535a0  mov     eax, ebx
0x1800535a2  mov     rcx, [rbp+4Fh+var_A0]
0x1800535a6  mov     rcx, [rcx+rax*8]; pv
0x1800535aa  call    cs:__imp_CoTaskMemFree
0x1800535b0  inc     ebx
0x1800535b2  cmp     ebx, [rbp+4Fh+arg_10]
0x1800535b5  jb      short loc_1800535A0
0x1800535b7  jmp     loc_180053471
0x1800535bc  mov     ebx, edi
0x1800535be  mov     rcx, [rbp+4Fh+var_B0]
0x1800535c2  mov     rcx, [rcx+rbx*8]; void *
0x1800535c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800535cb  mov     rcx, [rbp+4Fh+var_A8]
0x1800535cf  mov     rcx, [rcx+rbx*8]; void *
0x1800535d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800535d8  inc     edi
0x1800535da  cmp     edi, [rbp+4Fh+arg_10]
0x1800535dd  jb      short loc_1800535BC
0x1800535df  jmp     loc_180053489
0x1800535e4  mov     eax, ebx
0x1800535e6  mov     rcx, [rbp+4Fh+var_A0]
0x1800535ea  mov     rcx, [rcx+rax*8]; pv
0x1800535ee  call    cs:__imp_CoTaskMemFree
0x1800535f4  inc     ebx
0x1800535f6  cmp     ebx, [rbp+4Fh+arg_10]
0x1800535f9  jb      short loc_1800535E4
0x1800535fb  jmp     loc_1800534FC
```
