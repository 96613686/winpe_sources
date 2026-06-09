# _anonymous_namespace_::I_s_NgcIsoCreateSoftwareKey

- ea: `0x140024cc0`
- end: `0x140024f84`
- name: `_anonymous_namespace_::I_s_NgcIsoCreateSoftwareKey`
- size: `708`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x140009fa0`
- `0x14000ac7c`
- `0x14000b3a0`
- `0x14000b678`
- `0x14000d490`
- `0x14000e034`
- `0x14000f6a0`
- `0x140017adc`
- `0x1400184c0`
- `0x140019568`
- `0x14001ca34`
- `0x14001d3cc`
- `0x14001e0e4`
- `0x14002032c`
- `0x140024cc0`
- `0x14002bdf0`
- `0x14002c600`
- `0x14002e3fc`
- `0x1400389ec`
- `0x140047528`
- `0x140071010`

## string_xrefs

- `0x140024d61`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140024dc2`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140024e44`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140024e95`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140024efc`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140024d10`: `NgcIsoCreateSoftwareKey`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall anonymous_namespace_::I_s_NgcIsoCreateSoftwareKey(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        __int64 a6,
        _DWORD *a7,
        _QWORD *a8)
{
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rsi
  int KeyMaterial; // eax
  int v15; // eax
  _BYTE *v16; // rcx
  int v17; // eax
  int v18; // eax
  int v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  std::_Ref_count_base *v22; // [rsp+38h] [rbp-C8h]
  _BYTE v23[24]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[24]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[32]; // [rsp+70h] [rbp-90h] BYREF
  int v26[28]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[112]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v28[48]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v29[42]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v29);
  v29[0] = &LogProvider::NgcIsoCreateSoftwareKey::`vftable';
  LogProvider::NgcIsoCreateSoftwareKey::StartActivity((LogProvider::NgcIsoCreateSoftwareKey *)v29);
  *a7 = 0;
  *a8 = 0;
  if ( a4 != 1 )
  {
    v11 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x238,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)0x80004001LL,
      v20);
    goto LABEL_19;
  }
  std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(&v21, a2);
  Properties::SoftwareKeyMaterial::SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v26);
  v12 = a3;
  v13 = v21;
  KeyMaterial = NgcIsoContainerImpl::SoftwareCreateKeyMaterial(v21, v12, a5, a6);
  v11 = KeyMaterial;
  if ( KeyMaterial < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x241,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)KeyMaterial,
      (int)v26);
    goto LABEL_5;
  }
  if ( *(_DWORD *)(a6 + 20) )
  {
    std::vector<unsigned char>::vector<unsigned char>(
      v24,
      *(_QWORD *)(a6 + 24),
      *(_QWORD *)(a6 + 24) + *(unsigned int *)(a6 + 20));
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v23);
    v15 = ClientAuth::SetClientAttestation(v27, v24, v23);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x247,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)(unsigned int)v15,
        (int)v26);
      std::vector<unsigned char>::_Tidy(v23);
      v16 = v24;
LABEL_10:
      std::vector<unsigned char>::_Tidy(v16);
LABEL_5:
      Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v26);
      if ( v22 )
        std::_Ref_count_base::_Decref(v22);
      goto LABEL_19;
    }
    std::vector<unsigned char>::operator=(v28, v23);
    v17 = ClientAuth::AddKeyRefCount(v27);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
        (const char *)(unsigned int)v17,
        (int)v26);
    std::vector<unsigned char>::_Tidy(v23);
    std::vector<unsigned char>::_Tidy(v24);
  }
  Properties::ToCbor<Properties::SoftwareKeyMaterial>(v25, v26);
  v18 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, _DWORD *))(*(_QWORD *)v13 + 24LL))(v13, 2, v25, a7);
  v11 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v18,
      (int)a8);
    v16 = v25;
    goto LABEL_10;
  }
  wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v29);
  std::vector<unsigned char>::_Tidy(v25);
  Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v26);
  if ( v22 )
    std::_Ref_count_base::_Decref(v22);
  v11 = 0;
LABEL_19:
  LogProvider::NgcIsoCreateSoftwareKey::~NgcIsoCreateSoftwareKey((LogProvider::NgcIsoCreateSoftwareKey *)v29);
  return v11;
}

```

## disassembly

```asm
0x140024cc0  mov     [rsp-8+arg_0], rbx
0x140024cc5  mov     [rsp-8+arg_10], rsi
0x140024cca  push    rbp
0x140024ccb  push    rdi
0x140024ccc  push    r12
0x140024cce  push    r14
0x140024cd0  push    r15
0x140024cd2  lea     rbp, [rsp-200h]
0x140024cda  sub     rsp, 300h
0x140024ce1  mov     rax, cs:__security_cookie
0x140024ce8  xor     rax, rsp
0x140024ceb  mov     [rbp+220h+var_30], rax
0x140024cf2  mov     ebx, r9d
0x140024cf5  mov     rsi, r8
0x140024cf8  mov     r14, rdx
0x140024cfb  mov     rdi, [rbp+220h+arg_28]
0x140024d02  mov     r15, [rbp+220h+arg_30]
0x140024d09  mov     r12, qword ptr [rbp+220h+arg_38]
0x140024d10  lea     rdx, aNgcisocreateso; "NgcIsoCreateSoftwareKey"
0x140024d17  lea     rcx, [rbp+220h+var_180]; struct wil::details::IFailureCallback *
0x140024d1e  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140024d23  lea     rax, ??_7NgcIsoCreateSoftwareKey@LogProvider@@6B@; const LogProvider::NgcIsoCreateSoftwareKey::`vftable'
0x140024d2a  mov     [rbp+220h+var_180], rax
0x140024d31  lea     rcx, [rbp+220h+var_180]; this
0x140024d38  call    ?StartActivity@NgcIsoCreateSoftwareKey@LogProvider@@QEAAXXZ; LogProvider::NgcIsoCreateSoftwareKey::StartActivity(void)
0x140024d3d  nop
0x140024d3e  mov     dword ptr [r15], 0
0x140024d45  mov     qword ptr [r12], 0
0x140024d4d  cmp     ebx, 1
0x140024d50  jz      short loc_140024D77
0x140024d52  mov     rcx, [rbp+228h]; this
0x140024d59  mov     ebx, 80004001h
0x140024d5e  mov     r9d, ebx; char *
0x140024d61  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024d68  mov     edx, 238h; void *
0x140024d6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024d72  jmp     loc_140024F4B
0x140024d77  mov     rdx, r14
0x140024d7a  lea     rcx, [rsp+320h+var_2F0]
0x140024d7f  call    ??0?$shared_ptr@VNgcIsoContainerImpl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(std::shared_ptr<NgcIsoContainerImpl> const &)
0x140024d84  nop
0x140024d85  lea     rcx, [rbp+220h+var_290]; this
0x140024d89  call    ??0SoftwareKeyMaterial@Properties@@QEAA@XZ; Properties::SoftwareKeyMaterial::SoftwareKeyMaterial(void)
0x140024d8e  nop
0x140024d8f  lea     rax, [rbp+220h+var_290]
0x140024d93  mov     qword ptr [rsp+320h+var_300], rax; int
0x140024d98  mov     r9, rdi
0x140024d9b  mov     r8d, [rbp+220h+arg_20]
0x140024da2  mov     rdx, rsi
0x140024da5  mov     rsi, [rsp+320h+var_2F0]
0x140024daa  mov     rcx, rsi
0x140024dad  call    ?SoftwareCreateKeyMaterial@NgcIsoContainerImpl@@QEAAJ_KW4Algorithm@@PEBU_NGC_RPC_KEY_CREATION_PARAMS@@PEAUSoftwareKeyMaterial@Properties@@@Z; NgcIsoContainerImpl::SoftwareCreateKeyMaterial(unsigned __int64,Algorithm,_NGC_RPC_KEY_CREATION_PARAMS const *,Properties::SoftwareKeyMaterial *)
0x140024db2  mov     ebx, eax
0x140024db4  test    eax, eax
0x140024db6  jns     short loc_140024DF6
0x140024db8  mov     rcx, [rbp+228h]; this
0x140024dbf  mov     r9d, eax; char *
0x140024dc2  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024dc9  mov     edx, 241h; void *
0x140024dce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024dd3  nop
0x140024dd4  lea     rcx, [rbp+220h+var_290]; this
0x140024dd8  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x140024ddd  nop
0x140024dde  mov     rcx, [rsp+320h+var_2E8]; this
0x140024de3  test    rcx, rcx
0x140024de6  jz      loc_140024F4B
0x140024dec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140024df1  jmp     loc_140024F4B
0x140024df6  cmp     dword ptr [rdi+14h], 0
0x140024dfa  jz      loc_140024EBC
0x140024e00  mov     rdx, [rdi+18h]
0x140024e04  mov     r8d, [rdi+14h]
0x140024e08  add     r8, rdx
0x140024e0b  lea     rcx, [rsp+320h+var_2C8]
0x140024e10  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x140024e15  nop
0x140024e16  lea     rcx, [rsp+320h+var_2E0]
0x140024e1b  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140024e20  nop
0x140024e21  lea     r8, [rsp+320h+var_2E0]
0x140024e26  lea     rdx, [rsp+320h+var_2C8]
0x140024e2b  lea     rcx, [rbp+220h+var_220]
0x140024e2f  call    ?SetClientAttestation@ClientAuth@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@0AEAV23@@Z; ClientAuth::SetClientAttestation(std::vector<uchar> const &,std::vector<uchar> const &,std::vector<uchar> &)
0x140024e34  mov     ebx, eax
0x140024e36  test    eax, eax
0x140024e38  jns     short loc_140024E70
0x140024e3a  mov     rcx, [rbp+228h]; this
0x140024e41  mov     r9d, eax; char *
0x140024e44  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024e4b  mov     edx, 247h; void *
0x140024e50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024e55  nop
0x140024e56  lea     rcx, [rsp+320h+var_2E0]
0x140024e5b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024e60  nop
0x140024e61  lea     rcx, [rsp+320h+var_2C8]
0x140024e66  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024e6b  jmp     loc_140024DD4
0x140024e70  lea     rdx, [rsp+320h+var_2E0]
0x140024e75  lea     rcx, [rbp+220h+var_1B0]
0x140024e79  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140024e7e  lea     rcx, [rbp+220h+var_220]
0x140024e82  call    ?AddKeyRefCount@ClientAuth@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; ClientAuth::AddKeyRefCount(std::vector<uchar> const &)
0x140024e87  mov     rcx, [rbp+228h]; this
0x140024e8e  test    eax, eax
0x140024e90  jns     short loc_140024EA7
0x140024e92  mov     r9d, eax; char *
0x140024e95  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024e9c  mov     edx, 249h; void *
0x140024ea1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140024ea6  nop
0x140024ea7  lea     rcx, [rsp+320h+var_2E0]
0x140024eac  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024eb1  nop
0x140024eb2  lea     rcx, [rsp+320h+var_2C8]
0x140024eb7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024ebc  lea     rdx, [rbp+220h+var_290]
0x140024ec0  lea     rcx, [rsp+320h+var_2B0]
0x140024ec5  call    ??$ToCbor@USoftwareKeyMaterial@Properties@@@Properties@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUSoftwareKeyMaterial@0@@Z; Properties::ToCbor<Properties::SoftwareKeyMaterial>(Properties::SoftwareKeyMaterial const &)
0x140024eca  nop
0x140024ecb  mov     rax, [rsi]
0x140024ece  mov     qword ptr [rsp+320h+var_300], r12; int
0x140024ed3  mov     r9, r15
0x140024ed6  lea     r8, [rsp+320h+var_2B0]
0x140024edb  mov     edx, 2
0x140024ee0  mov     rcx, rsi
0x140024ee3  mov     rax, [rax+18h]
0x140024ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024eec  mov     ebx, eax
0x140024eee  test    eax, eax
0x140024ef0  jns     short loc_140024F18
0x140024ef2  mov     rcx, [rbp+228h]; this
0x140024ef9  mov     r9d, eax; char *
0x140024efc  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024f03  mov     edx, 24Fh; void *
0x140024f08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024f0d  nop
0x140024f0e  lea     rcx, [rsp+320h+var_2B0]
0x140024f13  jmp     loc_140024E66
0x140024f18  lea     rcx, [rbp+220h+var_180]
0x140024f1f  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140024f24  nop
0x140024f25  lea     rcx, [rsp+320h+var_2B0]
0x140024f2a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024f2f  nop
0x140024f30  lea     rcx, [rbp+220h+var_290]; this
0x140024f34  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x140024f39  nop
0x140024f3a  mov     rcx, [rsp+320h+var_2E8]; this
0x140024f3f  test    rcx, rcx
0x140024f42  jz      short loc_140024F49
0x140024f44  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140024f49  xor     ebx, ebx
0x140024f4b  lea     rcx, [rbp+220h+var_180]; this
0x140024f52  call    ??1NgcIsoCreateSoftwareKey@LogProvider@@QEAA@XZ; LogProvider::NgcIsoCreateSoftwareKey::~NgcIsoCreateSoftwareKey(void)
0x140024f57  mov     eax, ebx
0x140024f59  mov     rcx, [rbp+220h+var_30]
0x140024f60  xor     rcx, rsp; StackCookie
0x140024f63  call    __security_check_cookie
0x140024f68  lea     r11, [rsp+320h+var_20]
0x140024f70  mov     rbx, [r11+30h]
0x140024f74  mov     rsi, [r11+40h]
0x140024f78  mov     rsp, r11
0x140024f7b  pop     r15
0x140024f7d  pop     r14
0x140024f7f  pop     r12
0x140024f81  pop     rdi
0x140024f82  pop     rbp
0x140024f83  retn
```
