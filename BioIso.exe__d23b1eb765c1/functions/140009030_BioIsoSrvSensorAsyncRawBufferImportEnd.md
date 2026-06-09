# BioIsoSrvSensorAsyncRawBufferImportEnd

- ea: `0x140009030`
- end: `0x14000931e`
- name: `BioIsoSrvSensorAsyncRawBufferImportEnd`
- size: `750`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x140009030`
- `0x140009324`
- `0x14000a2e4`
- `0x14000a31c`
- `0x14000a420`
- `0x140012974`
- `0x140013078`
- `0x14001bd40`
- `0x140042ff0`
- `0x14005841c`
- `0x140059830`
- `0x140085010`

## string_xrefs

- `0x140009093`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400090d2`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000911b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000917a`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400091dc`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400092bf`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall BioIsoSrvSensorAsyncRawBufferImportEnd(int *a1, __int64 a2, _DWORD *a3)
{
  int BiometricUnit; // eax
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // r8
  _QWORD *v11; // r10
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64, _QWORD, _QWORD, __int64); // rax
  int v14; // ebx
  __int64 *v15; // [rsp+20h] [rbp-1B8h]
  __int64 v16; // [rsp+30h] [rbp-1A8h] BYREF
  std::_Ref_count_base *v17[2]; // [rsp+38h] [rbp-1A0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-190h] BYREF
  std::_Ref_count_base *v19; // [rsp+50h] [rbp-188h]
  _QWORD v20[42]; // [rsp+60h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v20,
    (__int64)"AsyncRawBufferImportEnd");
  v20[0] = &BioIsoProvider::AsyncRawBufferImportEnd::`vftable';
  BioIsoProvider::AsyncRawBufferImportEnd::StartActivity((BioIsoProvider::AsyncRawBufferImportEnd *)v20);
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      (int)v15);
    BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd((BioIsoProvider::AsyncRawBufferImportEnd *)v20);
    return 2147500035LL;
  }
  if ( !HardwareManager::ContainsHandle((unsigned __int64)a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      (int)v15);
    BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd((BioIsoProvider::AsyncRawBufferImportEnd *)v20);
    return 2147942487LL;
  }
  *(_OWORD *)v17 = 0;
  BiometricUnit = HardwareManager::FindBiometricUnit(*a1, (__int64 *)v17);
  v8 = BiometricUnit;
  if ( BiometricUnit < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)BiometricUnit,
      (int)v15);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
LABEL_8:
    BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd((BioIsoProvider::AsyncRawBufferImportEnd *)v20);
    return v8;
  }
  BiometricUnit::PipelineObject(v17[0], &v18);
  if ( !v18 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15F,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070057LL,
      (int)v15);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
    BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd((BioIsoProvider::AsyncRawBufferImportEnd *)v20);
    return 2147942487LL;
  }
  v9 = CacheBuffer::ImportEnd((CacheBuffer *)(v18 + 1128));
  v8 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v9,
      (int)v15);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
    goto LABEL_8;
  }
  v16 = 0;
  if ( *(_QWORD *)(v10 + 24) == -32 || (v12 = *(_QWORD *)(*(_QWORD *)(v10 + 24) + 56LL)) == 0 )
  {
    v14 = -2147467261;
    goto LABEL_32;
  }
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(v12 + 224);
  if ( !v13 )
  {
    v14 = -2147467263;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)(unsigned int)v14,
      (int)v15);
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    if ( v17[1] )
      std::_Ref_count_base::_Decref(v17[1]);
    BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd((BioIsoProvider::AsyncRawBufferImportEnd *)v20);
    return (unsigned int)v14;
  }
  v15 = &v16;
  v14 = v13(*(_QWORD *)(v10 + 24) + 32LL, *v11, v11[1] - *v11, a2);
  if ( v14 < 0 )
    goto LABEL_32;
  *a3 = v16;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v20, 0);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  if ( v17[1] )
    std::_Ref_count_base::_Decref(v17[1]);
  BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd((BioIsoProvider::AsyncRawBufferImportEnd *)v20);
  return 0;
}

```

## disassembly

```asm
0x140009030  push    rbx
0x140009032  push    rsi
0x140009033  push    rdi
0x140009034  sub     rsp, 1C0h
0x14000903b  mov     rax, cs:__security_cookie
0x140009042  xor     rax, rsp
0x140009045  mov     [rsp+1D8h+var_28], rax
0x14000904d  mov     rdi, r8
0x140009050  mov     rsi, rdx
0x140009053  mov     rbx, rcx
0x140009056  lea     rdx, aAsyncrawbuffer_1; "AsyncRawBufferImportEnd"
0x14000905d  lea     rcx, [rsp+1D8h+var_178]
0x140009062  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140009067  lea     rax, ??_7AsyncRawBufferImportEnd@BioIsoProvider@@6B@; const BioIsoProvider::AsyncRawBufferImportEnd::`vftable'
0x14000906e  mov     [rsp+1D8h+var_178], rax
0x140009073  lea     rcx, [rsp+1D8h+var_178]; this
0x140009078  call    ?StartActivity@AsyncRawBufferImportEnd@BioIsoProvider@@QEAAXXZ; BioIsoProvider::AsyncRawBufferImportEnd::StartActivity(void)
0x14000907d  nop
0x14000907e  test    rbx, rbx
0x140009081  jnz     short loc_1400090B6
0x140009083  mov     rcx, [rsp+1D8h]; this
0x14000908b  mov     ebx, 80004003h
0x140009090  mov     r9d, ebx; char *
0x140009093  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000909a  mov     edx, 154h; void *
0x14000909f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400090a4  nop
0x1400090a5  lea     rcx, [rsp+1D8h+var_178]; this
0x1400090aa  call    ??1AsyncRawBufferImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd(void)
0x1400090af  mov     eax, ebx
0x1400090b1  jmp     loc_140009302
0x1400090b6  mov     rcx, rbx; void *
0x1400090b9  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x1400090be  test    al, al
0x1400090c0  jnz     short loc_1400090F5
0x1400090c2  mov     rcx, [rsp+1D8h]; this
0x1400090ca  mov     ebx, 80070057h
0x1400090cf  mov     r9d, ebx; char *
0x1400090d2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400090d9  mov     edx, 155h; void *
0x1400090de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400090e3  nop
0x1400090e4  lea     rcx, [rsp+1D8h+var_178]; this
0x1400090e9  call    ??1AsyncRawBufferImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd(void)
0x1400090ee  mov     eax, ebx
0x1400090f0  jmp     loc_140009302
0x1400090f5  xorps   xmm0, xmm0
0x1400090f8  movdqu  xmmword ptr [rsp+1D8h+var_1A0], xmm0
0x1400090fe  lea     rdx, [rsp+1D8h+var_1A0]
0x140009103  mov     ecx, [rbx]
0x140009105  call    ?FindBiometricUnit@HardwareManager@@SAJKPEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::FindBiometricUnit(ulong,std::shared_ptr<BiometricUnit> *)
0x14000910a  mov     ebx, eax
0x14000910c  test    eax, eax
0x14000910e  jns     short loc_14000914E
0x140009110  mov     rcx, [rsp+1D8h]; this
0x140009118  mov     r9d, eax; char *
0x14000911b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009122  mov     edx, 15Ah; void *
0x140009127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000912c  nop
0x14000912d  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x140009132  test    rcx, rcx
0x140009135  jz      short loc_14000913D
0x140009137  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000913c  nop
0x14000913d  lea     rcx, [rsp+1D8h+var_178]; this
0x140009142  call    ??1AsyncRawBufferImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd(void)
0x140009147  mov     eax, ebx
0x140009149  jmp     loc_140009302
0x14000914e  lea     rdx, [rsp+1D8h+var_190]
0x140009153  mov     r8, [rsp+1D8h+var_1A0]
0x140009158  mov     rcx, r8
0x14000915b  call    ?PipelineObject@BiometricUnit@@QEBA?AV?$shared_ptr@VPipeline@@@std@@XZ; BiometricUnit::PipelineObject(void)
0x140009160  mov     rcx, [rsp+1D8h+var_190]
0x140009165  test    rcx, rcx
0x140009168  jnz     short loc_1400091BC
0x14000916a  mov     rcx, [rsp+1D8h]; this
0x140009172  mov     ebx, 80070057h
0x140009177  mov     r9d, ebx; char *
0x14000917a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140009181  mov     edx, 15Fh; void *
0x140009186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000918b  mov     rcx, [rsp+1D8h+var_188]; this
0x140009190  test    rcx, rcx
0x140009193  jz      short loc_14000919B
0x140009195  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000919a  nop
0x14000919b  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x1400091a0  test    rcx, rcx
0x1400091a3  jz      short loc_1400091AB
0x1400091a5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400091aa  nop
0x1400091ab  lea     rcx, [rsp+1D8h+var_178]; this
0x1400091b0  call    ??1AsyncRawBufferImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd(void)
0x1400091b5  mov     eax, ebx
0x1400091b7  jmp     loc_140009302
0x1400091bc  lea     r10, [rcx+468h]
0x1400091c3  mov     rcx, r10; this
0x1400091c6  call    ?ImportEnd@CacheBuffer@@QEAAJXZ; CacheBuffer::ImportEnd(void)
0x1400091cb  mov     ebx, eax
0x1400091cd  test    eax, eax
0x1400091cf  jns     short loc_14000921E
0x1400091d1  mov     rcx, [rsp+1D8h]; this
0x1400091d9  mov     r9d, eax; char *
0x1400091dc  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400091e3  mov     edx, 162h; void *
0x1400091e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091ed  mov     rcx, [rsp+1D8h+var_188]; this
0x1400091f2  test    rcx, rcx
0x1400091f5  jz      short loc_1400091FD
0x1400091f7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400091fc  nop
0x1400091fd  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x140009202  test    rcx, rcx
0x140009205  jz      short loc_14000920D
0x140009207  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000920c  nop
0x14000920d  lea     rcx, [rsp+1D8h+var_178]; this
0x140009212  call    ??1AsyncRawBufferImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd(void)
0x140009217  mov     eax, ebx
0x140009219  jmp     loc_140009302
0x14000921e  mov     [rsp+1D8h+var_1A8], 0
0x140009227  mov     rcx, [r8+18h]
0x14000922b  add     rcx, 20h ; ' '
0x14000922f  jz      short loc_1400092AF
0x140009231  mov     rax, [rcx+18h]
0x140009235  test    rax, rax
0x140009238  jz      short loc_1400092AF
0x14000923a  mov     rax, [rax+0E0h]
0x140009241  test    rax, rax
0x140009244  jnz     short loc_14000924D
0x140009246  mov     ebx, 80004001h
0x14000924b  jmp     short loc_1400092B4
0x14000924d  mov     r8, [r10+8]
0x140009251  sub     r8, [r10]
0x140009254  lea     rdx, [rsp+1D8h+var_1A8]
0x140009259  mov     [rsp+1D8h+var_1B8], rdx
0x14000925e  mov     r9, rsi
0x140009261  mov     rdx, [r10]
0x140009264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009269  mov     ebx, eax
0x14000926b  test    eax, eax
0x14000926d  js      short loc_1400092B4
0x14000926f  mov     eax, dword ptr [rsp+1D8h+var_1A8]
0x140009273  mov     [rdi], eax
0x140009275  xor     edx, edx
0x140009277  lea     rcx, [rsp+1D8h+var_178]
0x14000927c  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140009281  mov     rcx, [rsp+1D8h+var_188]; this
0x140009286  test    rcx, rcx
0x140009289  jz      short loc_140009291
0x14000928b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140009290  nop
0x140009291  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x140009296  test    rcx, rcx
0x140009299  jz      short loc_1400092A1
0x14000929b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400092a0  nop
0x1400092a1  lea     rcx, [rsp+1D8h+var_178]; this
0x1400092a6  call    ??1AsyncRawBufferImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd(void)
0x1400092ab  xor     eax, eax
0x1400092ad  jmp     short loc_140009302
0x1400092af  mov     ebx, 80004003h
0x1400092b4  mov     rcx, [rsp+1D8h]; this
0x1400092bc  mov     r9d, ebx; char *
0x1400092bf  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400092c6  mov     edx, 16Bh; void *
0x1400092cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400092d0  mov     rcx, [rsp+1D8h+var_188]; this
0x1400092d5  test    rcx, rcx
0x1400092d8  jz      short loc_1400092E0
0x1400092da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400092df  nop
0x1400092e0  mov     rcx, [rsp+1D8h+var_1A0+8]; this
0x1400092e5  test    rcx, rcx
0x1400092e8  jz      short loc_1400092F0
0x1400092ea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400092ef  nop
0x1400092f0  lea     rcx, [rsp+1D8h+var_178]; this
0x1400092f5  call    ??1AsyncRawBufferImportEnd@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AsyncRawBufferImportEnd::~AsyncRawBufferImportEnd(void)
0x1400092fa  mov     eax, ebx
0x1400092fc  jmp     short loc_140009302
0x1400092fe  mov     eax, dword ptr [rsp+1D8h+var_1A8]
0x140009302  mov     rcx, [rsp+1D8h+var_28]
0x14000930a  xor     rcx, rsp; StackCookie
0x14000930d  call    __security_check_cookie
0x140009312  add     rsp, 1C0h
0x140009319  pop     rdi
0x14000931a  pop     rsi
0x14000931b  pop     rbx
0x14000931c  retn
```
