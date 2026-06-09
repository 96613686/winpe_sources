# DynamoUserLoginHandler(ushort const *)

- ea: `0x140039c30`
- end: `0x140039ec7`
- name: `?DynamoUserLoginHandler@@YAJPEBG@Z`
- size: `663`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400095b4`
- `0x14000a6a8`
- `0x140036398`
- `0x140036c90`
- `0x140036dd0`
- `0x1400389cc`
- `0x140039c30`
- `0x140039f28`
- `0x140039fe8`
- `0x14003a278`
- `0x14003bcc4`
- `0x14003bed0`
- `0x14005d010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x140039d03`
- `DMCmnUtils!DmGetActiveUserSid` at `0x140039d03`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140039e0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140039e0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140039d36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140039e4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140039d36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140039e4e`

## pseudocode

```c
__int64 __fastcall DynamoUserLoginHandler(unsigned __int16 *a1)
{
  __int64 result; // rax
  int ActiveUserSid; // eax
  unsigned int v4; // edi
  const char *v5; // r9
  struct Dynamo::IContextApplier *v6; // rcx
  __int64 v7; // r8
  const char *v8; // r9
  struct Dynamo::IDataStore *v9; // rcx
  int v10; // [rsp+20h] [rbp-238h]
  HLOCAL hMem; // [rsp+30h] [rbp-228h] BYREF
  struct Dynamo::IDataStore *v12; // [rsp+38h] [rbp-220h] BYREF
  struct Dynamo::IContextApplier *v13; // [rsp+40h] [rbp-218h] BYREF
  unsigned __int16 *v14; // [rsp+48h] [rbp-210h] BYREF
  HLOCAL v15; // [rsp+50h] [rbp-208h] BYREF
  HANDLE hMutex; // [rsp+58h] [rbp-200h] BYREF
  _QWORD v17[42]; // [rsp+60h] [rbp-1F8h] BYREF
  char v18[144]; // [rsp+1B0h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v14 = a1;
  memset_0(v18, 0, 0x81u);
  anonymous_namespace_::GetCorrelationVector(v18);
  wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v17,
    "UserLoginHandlerActivity");
  v17[0] = &DynamicManagementProvider::UserLoginHandlerActivity::`vftable';
  DynamicManagementProvider::UserLoginHandlerActivity::StartActivityWithCorrelationVector(
    (DynamicManagementProvider::UserLoginHandlerActivity *)v17,
    v18);
  if ( a1 )
  {
    try
    {
      hMem = 0;
      ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
      v4 = ActiveUserSid;
      if ( ActiveUserSid >= 0 )
      {
        Dynamo::DataStoreFactory_t<Dynamo::details::DataStore>::GetStore(&v12, a1, hMem);
        (*(void (__fastcall **)(struct Dynamo::IDataStore *, HANDLE *))(*(_QWORD *)v12 + 40LL))(v12, &hMutex);
        v15 = hMem;
        Dynamo::details::GenericFactory<Dynamo::IContextApplier,Dynamo::ContextApplier>::CreateUniqueInstance<unsigned short const * &,unsigned short const * &>(
          &v13,
          &v14,
          &v15);
        InternalEvaluation(v14, (const unsigned __int16 *)hMem, v12, v13, 0, 0);
        wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v17);
        v6 = v13;
        v13 = 0;
        if ( v6 )
          (**(void (__fastcall ***)(struct Dynamo::IContextApplier *, __int64))v6)(v6, 1);
        if ( hMutex && !ReleaseMutex(hMutex) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v7, v8);
        v9 = v12;
        v12 = 0;
        if ( v9 )
          (**(void (__fastcall ***)(struct Dynamo::IDataStore *, __int64))v9)(v9, 1);
        if ( hMem )
          LocalFree(hMem);
        v17[0] = &DynamicManagementProvider::UserLoginHandlerActivity::`vftable';
        wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
        wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
          (const char *)(unsigned int)ActiveUserSid,
          v10);
        if ( hMem )
          LocalFree(hMem);
        v17[0] = &DynamicManagementProvider::UserLoginHandlerActivity::`vftable';
        wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
        wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
        result = v4;
      }
    }
    catch ( ... )
    {
      LODWORD(hMem) = wil::details::in1diag3::Return_CaughtException(
                        retaddr,
                        (void *)0x28B,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
                        v5);
      v17[0] = &DynamicManagementProvider::UserLoginHandlerActivity::`vftable';
      wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
      wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
      return (unsigned int)hMem;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\dynamicmanagement.cpp",
      (const char *)0x80070057LL,
      v10);
    v17[0] = &DynamicManagementProvider::UserLoginHandlerActivity::`vftable';
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v17);
    wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(v17);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x140039c30  mov     [rsp+arg_8], rbx
0x140039c35  mov     [rsp+arg_10], rsi
0x140039c3a  push    rdi
0x140039c3b  sub     rsp, 250h
0x140039c42  mov     rax, cs:__security_cookie
0x140039c49  xor     rax, rsp
0x140039c4c  mov     [rsp+258h+var_18], rax
0x140039c54  mov     rsi, rcx
0x140039c57  mov     [rsp+258h+var_210], rcx
0x140039c5c  xor     edx, edx; Val
0x140039c5e  mov     r8d, 81h; Size
0x140039c64  lea     rcx, [rsp+258h+var_A8]; void *
0x140039c6c  call    memset_0
0x140039c71  lea     rcx, [rsp+258h+var_A8]; char *
0x140039c79  call    _anonymous_namespace___GetCorrelationVector
0x140039c7e  lea     rdx, aUserloginhandl; "UserLoginHandlerActivity"
0x140039c85  lea     rcx, [rsp+258h+var_1F8]
0x140039c8a  call    ??0?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140039c8f  lea     rbx, ??_7UserLoginHandlerActivity@DynamicManagementProvider@@6B@; const DynamicManagementProvider::UserLoginHandlerActivity::`vftable'
0x140039c96  mov     [rsp+258h+var_1F8], rbx
0x140039c9b  lea     rdx, [rsp+258h+var_A8]; char *
0x140039ca3  lea     rcx, [rsp+258h+var_1F8]; this
0x140039ca8  call    ?StartActivityWithCorrelationVector@UserLoginHandlerActivity@DynamicManagementProvider@@QEAAXPEBD@Z; DynamicManagementProvider::UserLoginHandlerActivity::StartActivityWithCorrelationVector(char const *)
0x140039cad  nop
0x140039cae  test    rsi, rsi
0x140039cb1  jnz     short loc_140039CF5
0x140039cb3  mov     rcx, [rsp+258h]; this
0x140039cbb  mov     edi, 80070057h
0x140039cc0  mov     r9d, edi; char *
0x140039cc3  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140039cca  mov     edx, 27Ah; void *
0x140039ccf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140039cd4  nop
0x140039cd5  mov     [rsp+258h+var_1F8], rbx
0x140039cda  lea     rcx, [rsp+258h+var_1F8]
0x140039cdf  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140039ce4  lea     rcx, [rsp+258h+var_1F8]
0x140039ce9  call    ??1?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039cee  mov     eax, edi
0x140039cf0  jmp     loc_140039E96
0x140039cf5  mov     [rsp+258h+hMem], 0
0x140039cfe  lea     rcx, [rsp+258h+hMem]
0x140039d03  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x140039d09  mov     edi, eax
0x140039d0b  test    eax, eax
0x140039d0d  jns     short loc_140039D5D
0x140039d0f  mov     rcx, [rsp+258h]; this
0x140039d17  mov     r9d, eax; char *
0x140039d1a  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x140039d21  mov     edx, 27Fh; void *
0x140039d26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140039d2b  nop
0x140039d2c  mov     rcx, [rsp+258h+hMem]; hMem
0x140039d31  test    rcx, rcx
0x140039d34  jz      short loc_140039D3D
0x140039d36  call    cs:__imp_LocalFree
0x140039d3c  nop
0x140039d3d  mov     [rsp+258h+var_1F8], rbx
0x140039d42  lea     rcx, [rsp+258h+var_1F8]
0x140039d47  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140039d4c  lea     rcx, [rsp+258h+var_1F8]
0x140039d51  call    ??1?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039d56  mov     eax, edi
0x140039d58  jmp     loc_140039E96
0x140039d5d  mov     r8, [rsp+258h+hMem]
0x140039d62  mov     rdx, rsi
0x140039d65  lea     rcx, [rsp+258h+var_220]
0x140039d6a  call    ?GetStore@?$DataStoreFactory_t@VDataStore@details@Dynamo@@@Dynamo@@SA?AV?$unique_ptr@VIDataStore@Dynamo@@U?$default_delete@VIDataStore@Dynamo@@@wistd@@@wistd@@PEBG0@Z; Dynamo::DataStoreFactory_t<Dynamo::details::DataStore>::GetStore(ushort const *,ushort const *)
0x140039d6f  nop
0x140039d70  mov     rcx, [rsp+258h+var_220]
0x140039d75  mov     rax, [rcx]
0x140039d78  lea     rdx, [rsp+258h+hMutex]
0x140039d7d  mov     rax, [rax+28h]
0x140039d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039d86  nop
0x140039d87  mov     rax, [rsp+258h+hMem]
0x140039d8c  mov     [rsp+258h+var_208], rax
0x140039d91  lea     r8, [rsp+258h+var_208]
0x140039d96  lea     rdx, [rsp+258h+var_210]
0x140039d9b  lea     rcx, [rsp+258h+var_218]
0x140039da0  call    ??$CreateUniqueInstance@AEAPEBGAEAPEBG@?$GenericFactory@VIContextApplier@Dynamo@@VContextApplier@2@@details@Dynamo@@SA?AV?$unique_ptr@VIContextApplier@Dynamo@@U?$default_delete@VIContextApplier@Dynamo@@@wistd@@@wistd@@AEAPEBG0@Z; Dynamo::details::GenericFactory<Dynamo::IContextApplier,Dynamo::ContextApplier>::CreateUniqueInstance<ushort const * &,ushort const * &>(ushort const * &,ushort const * &)
0x140039da5  nop
0x140039da6  mov     [rsp+258h+var_230], 0; bool *
0x140039daf  mov     [rsp+258h+var_238], 0; bool *
0x140039db8  mov     r9, [rsp+258h+var_218]; struct Dynamo::IContextApplier *
0x140039dbd  mov     r8, [rsp+258h+var_220]; struct Dynamo::IDataStore *
0x140039dc2  mov     rdx, [rsp+258h+hMem]; unsigned __int16 *
0x140039dc7  mov     rcx, [rsp+258h+var_210]; unsigned __int16 *
0x140039dcc  call    ?InternalEvaluation@@YAJPEBG0PEAVIDataStore@Dynamo@@PEAVIContextApplier@2@PEA_N3@Z; InternalEvaluation(ushort const *,ushort const *,Dynamo::IDataStore *,Dynamo::IContextApplier *,bool *,bool *)
0x140039dd1  lea     rcx, [rsp+258h+var_1F8]
0x140039dd6  call    ?Stop@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140039ddb  nop
0x140039ddc  mov     rcx, [rsp+258h+var_218]
0x140039de1  mov     [rsp+258h+var_218], 0
0x140039dea  test    rcx, rcx
0x140039ded  jz      short loc_140039E00
0x140039def  mov     rax, [rcx]
0x140039df2  mov     edx, 1
0x140039df7  mov     rax, [rax]
0x140039dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039dff  nop
0x140039e00  mov     rcx, [rsp+258h+hMutex]; hMutex
0x140039e05  test    rcx, rcx
0x140039e08  jz      short loc_140039E20
0x140039e0a  call    cs:__imp_ReleaseMutex
0x140039e10  mov     rcx, [rsp+258h]; this
0x140039e18  test    eax, eax
0x140039e1a  jz      loc_140039EBB
0x140039e20  mov     rcx, [rsp+258h+var_220]
0x140039e25  mov     [rsp+258h+var_220], 0
0x140039e2e  test    rcx, rcx
0x140039e31  jz      short loc_140039E44
0x140039e33  mov     rax, [rcx]
0x140039e36  mov     edx, 1
0x140039e3b  mov     rax, [rax]
0x140039e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039e43  nop
0x140039e44  mov     rcx, [rsp+258h+hMem]; hMem
0x140039e49  test    rcx, rcx
0x140039e4c  jz      short loc_140039E55
0x140039e4e  call    cs:__imp_LocalFree
0x140039e54  nop
0x140039e55  mov     [rsp+258h+var_1F8], rbx
0x140039e5a  lea     rcx, [rsp+258h+var_1F8]
0x140039e5f  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140039e64  lea     rcx, [rsp+258h+var_1F8]
0x140039e69  call    ??1?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039e6e  xor     eax, eax
0x140039e70  jmp     short loc_140039E96
0x140039e72  lea     rbx, ??_7UserLoginHandlerActivity@DynamicManagementProvider@@6B@; const DynamicManagementProvider::UserLoginHandlerActivity::`vftable'
0x140039e79  mov     [rsp+258h+var_1F8], rbx
0x140039e7e  lea     rcx, [rsp+258h+var_1F8]
0x140039e83  call    ?Destroy@?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140039e88  lea     rcx, [rsp+258h+var_1F8]
0x140039e8d  call    ??1?$ActivityBase@VDynamoProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DynamoProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x140039e92  mov     eax, dword ptr [rsp+258h+hMem]
0x140039e96  mov     rcx, [rsp+258h+var_18]
0x140039e9e  xor     rcx, rsp; StackCookie
0x140039ea1  call    __security_check_cookie
0x140039ea6  lea     r11, [rsp+258h+var_8]
0x140039eae  mov     rbx, [r11+18h]
0x140039eb2  mov     rsi, [r11+20h]
0x140039eb6  mov     rsp, r11
0x140039eb9  pop     rdi
0x140039eba  retn
0x140039ebb  mov     edx, 0A15h; void *
0x140039ec0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
