# _anonymous_namespace_::I_s_NgcIsoCreateMonotonicCounter

- ea: `0x140024860`
- end: `0x140024cab`
- name: `_anonymous_namespace_::I_s_NgcIsoCreateMonotonicCounter`
- size: `1099`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

## callees

- `0x140009fa0`
- `0x14000ac7c`
- `0x14000b3a0`
- `0x14000b678`
- `0x14000d490`
- `0x14000e034`
- `0x14000f6a0`
- `0x1400104f0`
- `0x140015fa8`
- `0x140016eb8`
- `0x140017adc`
- `0x14001850c`
- `0x140018828`
- `0x140018884`
- `0x1400188c4`
- `0x140019568`
- `0x1400195b4`
- `0x14001e0b8`
- `0x14001e944`
- `0x140020350`
- `0x140024860`
- `0x14002a6b0`
- `0x14002bdcc`
- `0x14002c554`
- `0x14005d534`
- `0x140071010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x14002499b`
- `bcrypt!BCryptGenRandom` at `0x14002499b`

## string_xrefs

- `0x14002496f`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x1400249af`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140024a2f`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140024b35`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x140024c28`: `onecore\ds\security\ngc\ctnrsvc\iso\trustlet\exe\ngcisosrv.cpp`
- `0x1400248b2`: `NgcIsoCreateMonotonicCounter`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall anonymous_namespace_::I_s_NgcIsoCreateMonotonicCounter(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  __int64 v9; // rdi
  unsigned int v11; // r14d
  __int64 v12; // r12
  int v13; // eax
  unsigned int v14; // ebx
  NTSTATUS v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  CounterStore *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  CounterStore *v24; // rax
  __int64 v25; // rax
  int v26; // eax
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v31; // [rsp+40h] [rbp-C0h]
  struct _GUID Buf2[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v34[24]; // [rsp+88h] [rbp-78h] BYREF
  int v35[2]; // [rsp+A0h] [rbp-60h]
  _BYTE v36[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v37[32]; // [rsp+B0h] [rbp-50h] BYREF
  UCHAR pbBuffer[16]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v39[64]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD Buf1[26]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v41[64]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v42[36]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v43[42]; // [rsp+350h] [rbp+250h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  v9 = a3;
  *(_QWORD *)v35 = a8;
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v43);
  v43[0] = &LogProvider::NgcIsoCreateMonotonicCounter::`vftable';
  LogProvider::NgcIsoCreateMonotonicCounter::StartActivity((LogProvider::NgcIsoCreateMonotonicCounter *)v43);
  std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(&v30, a2);
  std::vector<unsigned char>::vector<unsigned char>(Buf2, a4, a4 + v9);
  v11 = *(_DWORD *)(Properties::FromCbor<Properties::EncryptedStruct>((Properties::EncryptedStruct *)v36) + 4);
  std::vector<unsigned char>::_Tidy(v37);
  std::vector<unsigned char>::_Tidy(Buf2);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v33);
  LOBYTE(v29) = 0;
  v12 = v30;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(*(_QWORD *)v30 + 32LL))(
          v30,
          (unsigned int)v9,
          a4,
          v33);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E9,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v13,
      (int)&v29);
    goto LABEL_5;
  }
  *(_OWORD *)pbBuffer = 0;
  v15 = BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
  if ( v15 < 0 )
  {
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x9F0,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
            (const char *)(unsigned int)v15,
            (int)&v29);
    goto LABEL_5;
  }
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v34);
  if ( v11 != 2 )
  {
    if ( v11 != 3 )
      goto LABEL_28;
    Properties::FromCbor<Properties::TpmKeyMaterial>(v41, v33);
    v21 = anonymous_namespace_::AuthenticateCounterOperationIfNecessary(v41, a5, a6);
    v14 = v21;
    if ( v21 >= 0 )
    {
      Buf2[0] = 0;
      if ( memcmp_0(v42, Buf2, 0x10u) )
      {
        v14 = -2146893809;
        v23 = 2148073487LL;
        v22 = 2566;
        goto LABEL_22;
      }
      v24 = CounterStore::Instance();
      Buf2[0] = *(struct _GUID *)pbBuffer;
      v21 = CounterStore::AddCounter(v24, Buf2);
      v14 = v21;
      if ( v21 >= 0 )
      {
        v42[0] = *(_QWORD *)pbBuffer;
        v42[1] = *(_QWORD *)&pbBuffer[8];
        v25 = Properties::ToCbor<Properties::TpmKeyMaterial>(Buf2, v41);
        std::vector<unsigned char>::operator=(v34, v25);
        std::vector<unsigned char>::_Tidy(Buf2);
        Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v41);
        goto LABEL_28;
      }
      v22 = 2568;
    }
    else
    {
      v22 = 2565;
    }
    v23 = (unsigned int)v21;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)v23,
      (int)&v29);
    Properties::TpmKeyMaterial::~TpmKeyMaterial((Properties::TpmKeyMaterial *)v41);
    goto LABEL_12;
  }
  Properties::FromCbor<Properties::SoftwareKeyMaterial>(v39, v33);
  v16 = anonymous_namespace_::AuthenticateCounterOperationIfNecessary(v39, a5, a6);
  v14 = v16;
  if ( v16 < 0 )
  {
    v17 = 2552;
LABEL_10:
    v18 = (unsigned int)v16;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)v18,
      (int)&v29);
    Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v39);
LABEL_12:
    std::vector<unsigned char>::_Tidy(v34);
LABEL_5:
    std::vector<unsigned char>::_Tidy(v33);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    goto LABEL_33;
  }
  Buf2[0] = 0;
  if ( memcmp_0(Buf1, Buf2, 0x10u) )
  {
    v14 = -2146893809;
    v18 = 2148073487LL;
    v17 = 2553;
    goto LABEL_11;
  }
  v19 = CounterStore::Instance();
  Buf2[0] = *(struct _GUID *)pbBuffer;
  v16 = CounterStore::AddCounter(v19, Buf2);
  v14 = v16;
  if ( v16 < 0 )
  {
    v17 = 2555;
    goto LABEL_10;
  }
  Buf1[0] = *(_QWORD *)pbBuffer;
  Buf1[1] = *(_QWORD *)&pbBuffer[8];
  v20 = Properties::ToCbor<Properties::SoftwareKeyMaterial>(Buf2, v39);
  std::vector<unsigned char>::operator=(v34, v20);
  std::vector<unsigned char>::_Tidy(Buf2);
  Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial((Properties::SoftwareKeyMaterial *)v39);
LABEL_28:
  v28 = v35[0];
  v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *, __int64))(*(_QWORD *)v12 + 24LL))(v12, v11, v34, a7);
  v14 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0F,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\trustlet\\exe\\ngcisosrv.cpp",
      (const char *)(unsigned int)v26,
      v28);
    goto LABEL_12;
  }
  wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v43, 0);
  std::vector<unsigned char>::_Tidy(v34);
  std::vector<unsigned char>::_Tidy(v33);
  if ( v31 )
    std::_Ref_count_base::_Decref(v31);
  v14 = 0;
LABEL_33:
  LogProvider::NgcIsoCreateMonotonicCounter::~NgcIsoCreateMonotonicCounter((LogProvider::NgcIsoCreateMonotonicCounter *)v43);
  return v14;
}

```

## disassembly

```asm
0x140024860  mov     [rsp-8+arg_0], rbx
0x140024865  push    rbp
0x140024866  push    rsi
0x140024867  push    rdi
0x140024868  push    r12
0x14002486a  push    r13
0x14002486c  push    r14
0x14002486e  push    r15
0x140024870  lea     rbp, [rsp-3B0h]
0x140024878  sub     rsp, 4B0h
0x14002487f  mov     rax, cs:__security_cookie
0x140024886  xor     rax, rsp
0x140024889  mov     [rbp+3E0h+var_40], rax
0x140024890  mov     rsi, r9
0x140024893  mov     edi, r8d
0x140024896  mov     rbx, rdx
0x140024899  mov     r15, [rbp+3E0h+arg_28]
0x1400248a0  mov     r13, [rbp+3E0h+arg_30]
0x1400248a7  mov     rax, [rbp+3E0h+arg_38]
0x1400248ae  mov     qword ptr [rbp+3E0h+var_440], rax
0x1400248b2  lea     rdx, aNgcisocreatemo; "NgcIsoCreateMonotonicCounter"
0x1400248b9  lea     rcx, [rbp+3E0h+var_190]; struct wil::details::IFailureCallback *
0x1400248c0  call    ??0?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400248c5  lea     rax, ??_7NgcIsoCreateMonotonicCounter@LogProvider@@6B@; const LogProvider::NgcIsoCreateMonotonicCounter::`vftable'
0x1400248cc  mov     [rbp+3E0h+var_190], rax
0x1400248d3  lea     rcx, [rbp+3E0h+var_190]; this
0x1400248da  call    ?StartActivity@NgcIsoCreateMonotonicCounter@LogProvider@@QEAAXXZ; LogProvider::NgcIsoCreateMonotonicCounter::StartActivity(void)
0x1400248df  nop
0x1400248e0  mov     rdx, rbx
0x1400248e3  lea     rcx, [rsp+4E0h+var_4A8]
0x1400248e8  call    ??0?$shared_ptr@VNgcIsoContainerImpl@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<NgcIsoContainerImpl>::shared_ptr<NgcIsoContainerImpl>(std::shared_ptr<NgcIsoContainerImpl> const &)
0x1400248ed  nop
0x1400248ee  lea     r8, [rsi+rdi]
0x1400248f2  mov     rdx, rsi
0x1400248f5  lea     rcx, [rsp+4E0h+Buf2]
0x1400248fa  call    ??$?0V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<uchar> const &)
0x1400248ff  nop
0x140024900  lea     rdx, [rsp+4E0h+Buf2]
0x140024905  lea     rcx, [rbp+3E0h+var_438]; this
0x140024909  call    ??$FromCbor@UEncryptedStruct@Properties@@@Properties@@YA?AUEncryptedStruct@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::EncryptedStruct>(std::vector<uchar> const &)
0x14002490e  mov     r14d, [rax+4]
0x140024912  lea     rcx, [rbp+3E0h+var_430]
0x140024916  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14002491b  nop
0x14002491c  lea     rcx, [rsp+4E0h+Buf2]
0x140024921  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024926  lea     rcx, [rsp+4E0h+var_470]
0x14002492b  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140024930  nop
0x140024931  mov     byte ptr [rsp+4E0h+var_4B0], 0
0x140024936  mov     r12, [rsp+4E0h+var_4A8]
0x14002493b  mov     rax, [r12]
0x14002493f  lea     rcx, [rsp+4E0h+var_4B0]
0x140024944  mov     qword ptr [rsp+4E0h+var_4C0], rcx; int
0x140024949  lea     r9, [rsp+4E0h+var_470]
0x14002494e  mov     r8, rsi
0x140024951  mov     edx, edi
0x140024953  mov     rcx, r12
0x140024956  mov     rax, [rax+20h]
0x14002495a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002495f  mov     ebx, eax
0x140024961  test    eax, eax
0x140024963  jns     short loc_140024982
0x140024965  mov     rcx, [rbp+3E8h]; this
0x14002496c  mov     r9d, eax; char *
0x14002496f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024976  mov     edx, 9E9h; void *
0x14002497b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024980  jmp     short loc_1400249C2
0x140024982  xorps   xmm0, xmm0
0x140024985  movups  xmmword ptr [rbp+3E0h+pbBuffer], xmm0
0x140024989  mov     edi, 10h
0x14002498e  lea     r9d, [rdi-0Eh]; dwFlags
0x140024992  mov     r8d, edi; cbBuffer
0x140024995  lea     rdx, [rbp+3E0h+pbBuffer]; pbBuffer
0x140024999  xor     ecx, ecx; hAlgorithm
0x14002499b  call    cs:__imp_BCryptGenRandom
0x1400249a1  test    eax, eax
0x1400249a3  jns     short loc_1400249E5
0x1400249a5  mov     rcx, [rbp+3E8h]; this
0x1400249ac  mov     r9d, eax; char *
0x1400249af  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1400249b6  mov     edx, 9F0h; void *
0x1400249bb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1400249c0  mov     ebx, eax
0x1400249c2  lea     rcx, [rsp+4E0h+var_470]
0x1400249c7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400249cc  nop
0x1400249cd  mov     rcx, [rsp+4E0h+var_4A0]; this
0x1400249d2  test    rcx, rcx
0x1400249d5  jz      loc_140024C73
0x1400249db  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400249e0  jmp     loc_140024C73
0x1400249e5  lea     rcx, [rbp+3E0h+var_458]
0x1400249e9  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1400249ee  nop
0x1400249ef  cmp     r14d, 2
0x1400249f3  jnz     loc_140024AEF
0x1400249f9  lea     rdx, [rsp+4E0h+var_470]
0x1400249fe  lea     rcx, [rbp+3E0h+var_400]
0x140024a02  call    ??$FromCbor@USoftwareKeyMaterial@Properties@@@Properties@@YA?AUSoftwareKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::SoftwareKeyMaterial>(std::vector<uchar> const &)
0x140024a07  nop
0x140024a08  mov     r8, r15
0x140024a0b  mov     edx, [rbp+3E0h+arg_20]
0x140024a11  lea     rcx, [rbp+3E0h+var_400]
0x140024a15  call    _anonymous_namespace___AuthenticateCounterOperationIfNecessary
0x140024a1a  mov     ebx, eax
0x140024a1c  test    eax, eax
0x140024a1e  jns     short loc_140024A54
0x140024a20  mov     edx, 9F8h; void *
0x140024a25  mov     r9d, eax; char *
0x140024a28  mov     rcx, [rbp+3E8h]; this
0x140024a2f  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024a36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024a3b  nop
0x140024a3c  lea     rcx, [rbp+3E0h+var_400]; this
0x140024a40  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x140024a45  nop
0x140024a46  lea     rcx, [rbp+3E0h+var_458]
0x140024a4a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024a4f  jmp     loc_1400249C2
0x140024a54  xorps   xmm0, xmm0
0x140024a57  movups  [rsp+4E0h+Buf2], xmm0
0x140024a5c  mov     r8, rdi; Size
0x140024a5f  lea     rdx, [rsp+4E0h+Buf2]; Buf2
0x140024a64  lea     rcx, [rbp+3E0h+Buf1]; Buf1
0x140024a68  call    memcmp_0
0x140024a6d  test    eax, eax
0x140024a6f  jz      short loc_140024A80
0x140024a71  mov     ebx, 8009000Fh
0x140024a76  mov     r9d, ebx
0x140024a79  mov     edx, 9F9h
0x140024a7e  jmp     short loc_140024A28
0x140024a80  call    ?Instance@CounterStore@@SAAEAV1@XZ; CounterStore::Instance(void)
0x140024a85  movaps  xmm0, xmmword ptr [rbp+3E0h+pbBuffer]
0x140024a89  movdqa  [rsp+4E0h+Buf2], xmm0
0x140024a8f  lea     rdx, [rsp+4E0h+Buf2]; struct _GUID
0x140024a94  mov     rcx, rax; this
0x140024a97  call    ?AddCounter@CounterStore@@QEAAJU_GUID@@@Z; CounterStore::AddCounter(_GUID)
0x140024a9c  mov     ebx, eax
0x140024a9e  test    eax, eax
0x140024aa0  jns     short loc_140024AAC
0x140024aa2  mov     edx, 9FBh
0x140024aa7  jmp     loc_140024A25
0x140024aac  mov     rax, qword ptr [rbp+3E0h+pbBuffer]
0x140024ab0  mov     [rbp+3E0h+Buf1], rax
0x140024ab4  mov     rax, qword ptr [rbp+3E0h+pbBuffer+8]
0x140024ab8  mov     [rbp+3E0h+var_3B8], rax
0x140024abc  lea     rdx, [rbp+3E0h+var_400]
0x140024ac0  lea     rcx, [rsp+4E0h+Buf2]
0x140024ac5  call    ??$ToCbor@USoftwareKeyMaterial@Properties@@@Properties@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUSoftwareKeyMaterial@0@@Z; Properties::ToCbor<Properties::SoftwareKeyMaterial>(Properties::SoftwareKeyMaterial const &)
0x140024aca  mov     rdx, rax
0x140024acd  lea     rcx, [rbp+3E0h+var_458]
0x140024ad1  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140024ad6  lea     rcx, [rsp+4E0h+Buf2]
0x140024adb  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024ae0  nop
0x140024ae1  lea     rcx, [rbp+3E0h+var_400]; this
0x140024ae5  call    ??1SoftwareKeyMaterial@Properties@@UEAA@XZ; Properties::SoftwareKeyMaterial::~SoftwareKeyMaterial(void)
0x140024aea  jmp     loc_140024BF5
0x140024aef  cmp     r14d, 3
0x140024af3  jnz     loc_140024BF5
0x140024af9  lea     rdx, [rsp+4E0h+var_470]
0x140024afe  lea     rcx, [rbp+3E0h+var_2F0]
0x140024b05  call    ??$FromCbor@UTpmKeyMaterial@Properties@@@Properties@@YA?AUTpmKeyMaterial@0@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Properties::FromCbor<Properties::TpmKeyMaterial>(std::vector<uchar> const &)
0x140024b0a  nop
0x140024b0b  mov     r8, r15
0x140024b0e  mov     edx, [rbp+3E0h+arg_20]
0x140024b14  lea     rcx, [rbp+3E0h+var_2F0]
0x140024b1b  call    _anonymous_namespace___AuthenticateCounterOperationIfNecessary
0x140024b20  mov     ebx, eax
0x140024b22  test    eax, eax
0x140024b24  jns     short loc_140024B53
0x140024b26  mov     edx, 0A05h; void *
0x140024b2b  mov     r9d, eax; char *
0x140024b2e  mov     rcx, [rbp+3E8h]; this
0x140024b35  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024b3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024b41  nop
0x140024b42  lea     rcx, [rbp+3E0h+var_2F0]; this
0x140024b49  call    ??1TpmKeyMaterial@Properties@@UEAA@XZ; Properties::TpmKeyMaterial::~TpmKeyMaterial(void)
0x140024b4e  jmp     loc_140024A46
0x140024b53  xorps   xmm0, xmm0
0x140024b56  movups  [rsp+4E0h+Buf2], xmm0
0x140024b5b  mov     r8, rdi; Size
0x140024b5e  lea     rdx, [rsp+4E0h+Buf2]; Buf2
0x140024b63  lea     rcx, [rbp+3E0h+var_2B0]; Buf1
0x140024b6a  call    memcmp_0
0x140024b6f  test    eax, eax
0x140024b71  jz      short loc_140024B82
0x140024b73  mov     ebx, 8009000Fh
0x140024b78  mov     r9d, ebx
0x140024b7b  mov     edx, 0A06h
0x140024b80  jmp     short loc_140024B2E
0x140024b82  call    ?Instance@CounterStore@@SAAEAV1@XZ; CounterStore::Instance(void)
0x140024b87  movaps  xmm0, xmmword ptr [rbp+3E0h+pbBuffer]
0x140024b8b  movdqa  [rsp+4E0h+Buf2], xmm0
0x140024b91  lea     rdx, [rsp+4E0h+Buf2]; struct _GUID
0x140024b96  mov     rcx, rax; this
0x140024b99  call    ?AddCounter@CounterStore@@QEAAJU_GUID@@@Z; CounterStore::AddCounter(_GUID)
0x140024b9e  mov     ebx, eax
0x140024ba0  test    eax, eax
0x140024ba2  jns     short loc_140024BAB
0x140024ba4  mov     edx, 0A08h
0x140024ba9  jmp     short loc_140024B2B
0x140024bab  mov     rax, qword ptr [rbp+3E0h+pbBuffer]
0x140024baf  mov     [rbp+3E0h+var_2B0], rax
0x140024bb6  mov     rax, qword ptr [rbp+3E0h+pbBuffer+8]
0x140024bba  mov     [rbp+3E0h+var_2A8], rax
0x140024bc1  lea     rdx, [rbp+3E0h+var_2F0]
0x140024bc8  lea     rcx, [rsp+4E0h+Buf2]
0x140024bcd  call    ??$ToCbor@UTpmKeyMaterial@Properties@@@Properties@@YA?AV?$vector@EV?$allocator@E@std@@@std@@AEBUTpmKeyMaterial@0@@Z; Properties::ToCbor<Properties::TpmKeyMaterial>(Properties::TpmKeyMaterial const &)
0x140024bd2  mov     rdx, rax
0x140024bd5  lea     rcx, [rbp+3E0h+var_458]
0x140024bd9  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x140024bde  lea     rcx, [rsp+4E0h+Buf2]
0x140024be3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024be8  nop
0x140024be9  lea     rcx, [rbp+3E0h+var_2F0]; this
0x140024bf0  call    ??1TpmKeyMaterial@Properties@@UEAA@XZ; Properties::TpmKeyMaterial::~TpmKeyMaterial(void)
0x140024bf5  mov     rax, [r12]
0x140024bf9  mov     rcx, qword ptr [rbp+3E0h+var_440]
0x140024bfd  mov     qword ptr [rsp+4E0h+var_4C0], rcx; int
0x140024c02  mov     r9, r13
0x140024c05  lea     r8, [rbp+3E0h+var_458]
0x140024c09  mov     edx, r14d
0x140024c0c  mov     rcx, r12
0x140024c0f  mov     rax, [rax+18h]
0x140024c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024c18  mov     ebx, eax
0x140024c1a  test    eax, eax
0x140024c1c  jns     short loc_140024C3E
0x140024c1e  mov     rcx, [rbp+3E8h]; this
0x140024c25  mov     r9d, eax; char *
0x140024c28  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x140024c2f  mov     edx, 0A0Fh; void *
0x140024c34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140024c39  jmp     loc_140024A46
0x140024c3e  xor     edx, edx
0x140024c40  lea     rcx, [rbp+3E0h+var_190]
0x140024c47  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140024c4c  nop
0x140024c4d  lea     rcx, [rbp+3E0h+var_458]
0x140024c51  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024c56  nop
0x140024c57  lea     rcx, [rsp+4E0h+var_470]
0x140024c5c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140024c61  nop
0x140024c62  mov     rcx, [rsp+4E0h+var_4A0]; this
0x140024c67  test    rcx, rcx
0x140024c6a  jz      short loc_140024C71
0x140024c6c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140024c71  xor     ebx, ebx
0x140024c73  lea     rcx, [rbp+3E0h+var_190]; this
0x140024c7a  call    ??1NgcIsoCreateMonotonicCounter@LogProvider@@QEAA@XZ; LogProvider::NgcIsoCreateMonotonicCounter::~NgcIsoCreateMonotonicCounter(void)
0x140024c7f  mov     eax, ebx
0x140024c81  mov     rcx, [rbp+3E0h+var_40]
0x140024c88  xor     rcx, rsp; StackCookie
0x140024c8b  call    __security_check_cookie
0x140024c90  mov     rbx, [rsp+4E0h+arg_0]
0x140024c98  add     rsp, 4B0h
0x140024c9f  pop     r15
0x140024ca1  pop     r14
0x140024ca3  pop     r13
0x140024ca5  pop     r12
0x140024ca7  pop     rdi
0x140024ca8  pop     rsi
0x140024ca9  pop     rbp
0x140024caa  retn
```
