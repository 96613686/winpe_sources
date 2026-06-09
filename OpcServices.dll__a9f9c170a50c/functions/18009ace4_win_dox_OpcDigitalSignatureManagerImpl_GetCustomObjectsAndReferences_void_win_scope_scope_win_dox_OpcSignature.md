# win_dox::OpcDigitalSignatureManagerImpl::GetCustomObjectsAndReferences(void *,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>> *,win_dox::OpcSignatureCustomObjectSet *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureReference,IOpcSignatureReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureReference>> *,win_scope::const_policies<win_scope::shared_policies>> *)

- ea: `0x18009ace4`
- end: `0x18009ae68`
- name: `?GetCustomObjectsAndReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXPEAV?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAVOpcSignatureCustomObjectSet@2@PEAV?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureReference@win_dox@@UIOpcSignatureReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@4@@Z`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a1ef4`

## callees

- `0x1800016b0`
- `0x180001abc`
- `0x180018c00`
- `0x180018c2c`
- `0x18005dce4`
- `0x18009ace4`
- `0x18009ae70`
- `0x18009b6b8`
- `0x18009b6f0`
- `0x18009b7b8`
- `0x1800ca8b8`
- `0x1800f87e8`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlGetSignature` at `0x18009ad11`
- `CRYPTXML!CryptXmlGetSignature` at `0x18009ad11`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall win_dox::OpcDigitalSignatureManagerImpl::GetCustomObjectsAndReferences(
        void *a1,
        void *a2,
        __m128i *a3,
        __int64 a4,
        __m128i *a5)
{
  HRESULT Signature; // eax
  const char *v8; // rdx
  const char *v9; // r8
  unsigned int v10; // r9d
  void *v11; // rax
  void *v12; // rbx
  const char *v13; // rdx
  unsigned int v14; // r8d
  void *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __m128i v19; // xmm1
  __int64 result; // rax
  CRYPT_XML_SIGNATURE *ppStruct[2]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v22[2]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-28h] BYREF
  __m128i v24; // [rsp+50h] [rbp-18h] BYREF
  void *v25; // [rsp+90h] [rbp+28h] BYREF

  v25 = a1;
  ppStruct[1] = (CRYPT_XML_SIGNATURE *)-2LL;
  ppStruct[0] = 0;
  Signature = CryptXmlGetSignature(a2, (const CRYPT_XML_SIGNATURE **)ppStruct);
  if ( Signature < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)Signature, (int)v8, v9, v10);
  v11 = operator new(0x10u, v8, (unsigned int)v9);
  v12 = v11;
  v25 = v11;
  if ( v11 )
    win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v11);
  else
    v12 = 0;
  win_scope::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>(
    v23,
    v12);
  LODWORD(v25) = 0;
  win_dox::SignatureXmlParser::ParseCustomObjects(ppStruct[0], v23, &v25);
  v15 = operator new(0x10u, v13, v14);
  v25 = v15;
  if ( v15 )
    v15 = (void *)win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(v15);
  win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(
    v22,
    v15);
  v16 = (_QWORD *)win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
                    &v24,
                    v22);
  win_dox::SignatureXmlParser::ParseSignatureReferences((__int64)ppStruct[0], a3, v16);
  v17 = win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
          &v24,
          v23);
  v18 = win_dox::CreateInstanceFromInner<IOpcSignatureCustomObjectSet,win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>>>(
          &v25,
          v17);
  win_dox::OpcRelationship::operator=(a4, v18);
  if ( v25 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 16LL))(v25);
  win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(
    &v24,
    v22);
  v19 = *a5;
  *a5 = v24;
  v24 = v19;
  result = v19.m128i_i64[0];
  if ( v19.m128i_i64[0] )
  {
    result = _mm_srli_si128(v19, 8).m128i_u64[0];
    if ( result )
      result = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(&v24);
  }
  if ( v22[0] && v22[1] )
    result = win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v22);
  if ( v23[0] )
  {
    if ( v23[1] )
      return win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(v23);
  }
  return result;
}

```

## disassembly

```asm
0x18009ace4  mov     [rsp-20h+arg_0], rcx
0x18009ace9  push    rbp
0x18009acea  push    rbx
0x18009aceb  push    rsi
0x18009acec  push    rdi
0x18009aced  mov     rbp, rsp
0x18009acf0  sub     rsp, 68h
0x18009acf4  mov     [rbp+var_40], 0FFFFFFFFFFFFFFFEh
0x18009acfc  mov     rdi, r9
0x18009acff  mov     rsi, r8
0x18009ad02  mov     rcx, rdx; hCryptXml
0x18009ad05  mov     [rbp+ppStruct], 0
0x18009ad0d  lea     rdx, [rbp+ppStruct]; ppStruct
0x18009ad11  call    cs:__imp_CryptXmlGetSignature
0x18009ad17  test    eax, eax
0x18009ad19  jns     short loc_18009AD23
0x18009ad1b  mov     ecx, eax; this
0x18009ad1d  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x18009ad23  mov     ecx, 10h; unsigned __int64
0x18009ad28  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18009ad2d  mov     rbx, rax
0x18009ad30  mov     [rbp+arg_0], rax
0x18009ad34  test    rax, rax
0x18009ad37  jz      short loc_18009AD43
0x18009ad39  mov     rcx, rax
0x18009ad3c  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x18009ad41  jmp     short loc_18009AD45
0x18009ad43  xor     ebx, ebx
0x18009ad45  mov     rdx, rbx
0x18009ad48  lea     rcx, [rbp+var_28]
0x18009ad4c  call    ??0?$scope@PEAVOpcSignatureCustomObjectImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVOpcSignatureCustomObjectImpl@win_dox@@@Z; win_scope::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::OpcSignatureCustomObjectImpl *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::OpcSignatureCustomObjectImpl *)
0x18009ad51  nop
0x18009ad52  mov     dword ptr [rbp+arg_0], 0
0x18009ad59  lea     r8, [rbp+arg_0]
0x18009ad5d  lea     rdx, [rbp+var_28]
0x18009ad61  mov     rcx, [rbp+ppStruct]
0x18009ad65  call    ?ParseCustomObjects@SignatureXmlParser@win_dox@@SAXPEBU_CRYPT_XML_SIGNATURE@@AEAV?$scope@PEAVOpcSignatureCustomObjectSetImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAK@Z; win_dox::SignatureXmlParser::ParseCustomObjects(_CRYPT_XML_SIGNATURE const *,win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>> &,ulong *)
0x18009ad6a  mov     ecx, 10h; unsigned __int64
0x18009ad6f  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18009ad74  mov     [rbp+arg_0], rax
0x18009ad78  test    rax, rax
0x18009ad7b  jz      short loc_18009AD86
0x18009ad7d  mov     rcx, rax
0x18009ad80  call    ??0?$OpcEnumerableSetImpl@VOpcRelationshipSelector@win_dox@@UIOpcRelationshipSelectorEnumerator@@U?$com_wrapper_less@VOpcRelationshipSelector@win_dox@@@2@@win_dox@@QEAA@XZ; win_dox::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>::OpcEnumerableSetImpl<win_dox::OpcRelationshipSelector,IOpcRelationshipSelectorEnumerator,win_dox::com_wrapper_less<win_dox::OpcRelationshipSelector>>(void)
0x18009ad85  nop
0x18009ad86  mov     rdx, rax
0x18009ad89  lea     rcx, [rbp+var_38]
0x18009ad8d  call    ??0?$scope@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAV?$SimpleEnumerator@V?$scope@PEAVStorage@?$OpcEnumerableSetImpl@VOpcSignatureRelationshipReference@win_dox@@UIOpcSignatureRelationshipReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@VOpcSignatureRelationshipReference@win_dox@@Vconst_iterator@?$_Tree@V?$_Tset_traits@VOpcSignatureRelationshipReference@win_dox@@U?$com_wrapper_less@VOpcSignatureRelationshipReference@win_dox@@@2@V?$allocator@VOpcSignatureRelationshipReference@win_dox@@@std@@$0A@@std@@@std@@@win_dox@@@Z; win_scope::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *,win_scope::const_policies<win_scope::shared_policies>>(win_dox::SimpleEnumerator<win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureRelationshipReference,IOpcSignatureRelationshipReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>>::Storage *,win_scope::const_policies<win_scope::shared_policies>>,win_dox::OpcSignatureRelationshipReference,std::_Tree<std::_Tset_traits<win_dox::OpcSignatureRelationshipReference,win_dox::com_wrapper_less<win_dox::OpcSignatureRelationshipReference>,std::allocator<win_dox::OpcSignatureRelationshipReference>,0>>::const_iterator> *)
0x18009ad92  nop
0x18009ad93  lea     rdx, [rbp+var_38]
0x18009ad97  lea     rcx, [rbp+var_18]
0x18009ad9b  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009ada0  mov     r8, rax
0x18009ada3  mov     rdx, rsi
0x18009ada6  mov     rcx, [rbp+ppStruct]
0x18009adaa  call    ?ParseSignatureReferences@SignatureXmlParser@win_dox@@SAXPEBU_CRYPT_XML_SIGNATURE@@PEAV?$scope@PEAVOpcSignatureReferenceImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAV?$OpcEnumerableSetImpl@VOpcSignatureReference@win_dox@@UIOpcSignatureReferenceEnumerator@@U?$com_wrapper_less@VOpcSignatureReference@win_dox@@@2@@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@5@@Z; win_dox::SignatureXmlParser::ParseSignatureReferences(_CRYPT_XML_SIGNATURE const *,win_scope::scope<win_dox::OpcSignatureReferenceImpl *,win_scope::const_policies<win_scope::shared_policies>> *,win_scope::scope<win_dox::OpcEnumerableSetImpl<win_dox::OpcSignatureReference,IOpcSignatureReferenceEnumerator,win_dox::com_wrapper_less<win_dox::OpcSignatureReference>> *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009adaf  lea     rdx, [rbp+var_28]
0x18009adb3  lea     rcx, [rbp+var_18]
0x18009adb7  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009adbc  mov     rdx, rax
0x18009adbf  lea     rcx, [rbp+arg_0]
0x18009adc3  call    ??$CreateInstanceFromInner@UIOpcSignatureCustomObjectSet@@V?$scope@PEAVOpcSignatureCustomObjectSetImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@win_dox@@YA?AVOpcSignatureCustomObjectSet@0@V?$scope@PEAVOpcSignatureCustomObjectSetImpl@win_dox@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::CreateInstanceFromInner<IOpcSignatureCustomObjectSet,win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_dox::OpcSignatureCustomObjectSetImpl *,win_scope::const_policies<win_scope::shared_policies>>)
0x18009adc8  nop
0x18009adc9  mov     rdx, rax
0x18009adcc  mov     rcx, rdi
0x18009adcf  call    ??4OpcRelationship@win_dox@@QEAAAEAV01@AEBV01@@Z; win_dox::OpcRelationship::operator=(win_dox::OpcRelationship const &)
0x18009add4  nop
0x18009add5  mov     rcx, [rbp+arg_0]
0x18009add9  test    rcx, rcx
0x18009addc  jz      short loc_18009ADEB
0x18009adde  mov     rax, [rcx]
0x18009ade1  mov     rax, [rax+10h]
0x18009ade5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009adea  nop
0x18009adeb  lea     rdx, [rbp+var_38]
0x18009adef  lea     rcx, [rbp+var_18]
0x18009adf3  call    ??0?$scope@PEBU_CERT_CONTEXT@@U?$const_policies@U?$shared_close_policies@U?$close_function@P6AHPEBU_CERT_CONTEXT@@@Z$1?CertFreeCertificateContext@@YAH0@Z@win_scope@@@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>>(win_scope::scope<_CERT_CONTEXT const *,win_scope::const_policies<win_scope::shared_close_policies<win_scope::close_function<int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *)>>>> const &)
0x18009adf8  mov     rcx, [rbp+arg_20]
0x18009adfc  movups  xmm1, xmmword ptr [rcx]
0x18009adff  movaps  xmm0, [rbp+var_18]
0x18009ae03  movdqu  xmmword ptr [rcx], xmm0
0x18009ae07  movdqa  [rbp+var_18], xmm1
0x18009ae0c  movq    rax, xmm1
0x18009ae11  test    rax, rax
0x18009ae14  jz      short loc_18009AE2F
0x18009ae16  psrldq  xmm1, 8
0x18009ae1b  movq    rax, xmm1
0x18009ae20  test    rax, rax
0x18009ae23  jz      short loc_18009AE2F
0x18009ae25  lea     rcx, [rbp+var_18]
0x18009ae29  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009ae2e  nop
0x18009ae2f  cmp     [rbp+var_38], 0
0x18009ae34  jz      short loc_18009AE47
0x18009ae36  cmp     [rbp+var_30], 0
0x18009ae3b  jz      short loc_18009AE47
0x18009ae3d  lea     rcx, [rbp+var_38]
0x18009ae41  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009ae46  nop
0x18009ae47  cmp     [rbp+var_28], 0
0x18009ae4c  jz      short loc_18009AE5F
0x18009ae4e  cmp     [rbp+var_20], 0
0x18009ae53  jz      short loc_18009AE5F
0x18009ae55  lea     rcx, [rbp+var_28]
0x18009ae59  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18009ae5e  nop
0x18009ae5f  add     rsp, 68h
0x18009ae63  pop     rdi
0x18009ae64  pop     rsi
0x18009ae65  pop     rbx
0x18009ae66  pop     rbp
0x18009ae67  retn
```
