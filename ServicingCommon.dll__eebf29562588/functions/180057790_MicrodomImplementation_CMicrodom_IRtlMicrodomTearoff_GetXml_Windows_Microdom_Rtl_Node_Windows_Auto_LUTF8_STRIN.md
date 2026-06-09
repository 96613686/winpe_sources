# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml(Windows::Microdom::Rtl::Node,Windows::Auto<_LUTF8_STRING> *)

- ea: `0x180057790`
- end: `0x1800579b1`
- name: `?GetXml@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUNode@Rtl@Microdom@Windows@@PEAV?$Auto@U_LUTF8_STRING@@@6@@Z`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003520`
- `0x180010c10`
- `0x18001f4ac`
- `0x1800293a0`
- `0x180051850`
- `0x180051950`
- `0x180057790`
- `0x180064d80`
- `0x180099cb0`
- `0x1800a0020`

## string_xrefs

- `0x1800577f8`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057834`: `onecore\base\xml\udom_microdom.cpp`
- `0x1800578a1`: `onecore\base\xml\udom_microdom.cpp`
- `0x180057812`: `MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml`
- `0x18005784e`: `MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml`
- `0x1800578b8`: `MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml`

## pseudocode

```c
__int64 __fastcall MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml(__int64 a1, __int64 a2, __int128 *a3)
{
  __int128 *v6; // rdx
  int DefaultMicrodomXmlWriter; // eax
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(__int64, __int128 *, __int128 *); // rax
  __int128 v10; // xmm2
  __int64 v11; // xmm3_8
  __int64 v12; // xmm1_8
  __int64 (__fastcall ***v14[2])(_QWORD); // [rsp+30h] [rbp-D0h] BYREF
  __int128 v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h]
  const char *v17; // [rsp+58h] [rbp-A8h]
  _QWORD v18[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v19[4]; // [rsp+80h] [rbp-80h] BYREF
  int v20; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v21; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+B8h] [rbp-48h]
  __int128 v23; // [rsp+C0h] [rbp-40h] BYREF
  void **v24; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v25[88]; // [rsp+D8h] [rbp-28h] BYREF

  v20 = 0;
  v22 = 0;
  v14[0] = 0;
  v24 = &MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::CTempOutputStream::`vftable';
  v21 = 0;
  v23 = 0;
  memset(v25, 0, sizeof(v25));
  if ( *(_DWORD *)(a2 + 8) == -1 )
  {
    v16 = 3094;
    *(_QWORD *)&v15 = "onecore\\base\\xml\\udom_microdom.cpp";
    v6 = &v15;
    *((_QWORD *)&v15 + 1) = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml";
    v17 = "Root != Root.InvalidValue()";
LABEL_9:
    DefaultMicrodomXmlWriter = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                                 &v20,
                                 v6);
    goto LABEL_5;
  }
  if ( a3 )
  {
    v9 = *(__int64 (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)a1 + 88LL);
    v15 = *(_OWORD *)a2;
    DefaultMicrodomXmlWriter = v9(a1, &v15, &v23);
    if ( DefaultMicrodomXmlWriter >= 0 )
    {
      if ( DWORD2(v23) == -1 )
      {
        v19[2] = 3098;
        v19[0] = "onecore\\base\\xml\\udom_microdom.cpp";
        v6 = (__int128 *)v19;
        v19[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml";
        v19[3] = "TheElement != TheElement.InvalidValue()";
        goto LABEL_9;
      }
      DefaultMicrodomXmlWriter = RtlCreateDefaultMicrodomXmlWriter(0, v14);
      if ( DefaultMicrodomXmlWriter >= 0 )
      {
        DefaultMicrodomXmlWriter = RtlInitializeSmartLBlobWritingContext(0, -1, 0, (unsigned int)&v21, 0, (__int64)v25);
        if ( DefaultMicrodomXmlWriter >= 0 )
        {
          v15 = *(_OWORD *)a2;
          DefaultMicrodomXmlWriter = RtlWriteMicrodomXml(
                                       0,
                                       (__int64)v14[0],
                                       (struct Windows::Microdom::Rtl::IRtlMicrodomXmlWriter *)(a1 & -(__int64)(a1 != 16)),
                                       &v15,
                                       (struct Windows::Microdom::Rtl::IRtlMicrodom *)&v24);
          if ( DefaultMicrodomXmlWriter >= 0 )
          {
            v10 = *a3;
            v11 = *((_QWORD *)a3 + 2);
            v12 = v22;
            *a3 = v21;
            *((_QWORD *)a3 + 2) = v12;
            v8 = 0;
            v21 = v10;
            v22 = v11;
            goto LABEL_14;
          }
        }
      }
    }
  }
  else
  {
    v18[2] = 3095;
    v18[0] = "onecore\\base\\xml\\udom_microdom.cpp";
    v18[1] = "MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml";
    v18[3] = "Not-null check failed: Result";
    DefaultMicrodomXmlWriter = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
                                 &v20,
                                 v18);
  }
LABEL_5:
  v8 = DefaultMicrodomXmlWriter;
LABEL_14:
  v24 = &Windows::Rtl::IRtlObject::`vftable';
  Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(v14);
  Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(&v21);
  return v8;
}

```

## disassembly

```asm
0x180057790  mov     [rsp-8+arg_18], rbx
0x180057795  push    rbp
0x180057796  push    rsi
0x180057797  push    rdi
0x180057798  lea     rbp, [rsp-40h]
0x18005779d  sub     rsp, 140h
0x1800577a4  mov     rax, cs:__security_cookie
0x1800577ab  xor     rax, rsp
0x1800577ae  mov     [rbp+50h+var_20], rax
0x1800577b2  xor     eax, eax
0x1800577b4  mov     [rbp+50h+var_B0], 0
0x1800577bb  xorps   xmm0, xmm0
0x1800577be  mov     [rbp+50h+var_98], rax
0x1800577c2  mov     rsi, rdx
0x1800577c5  mov     [rsp+150h+var_120], rax
0x1800577ca  xor     edx, edx; Val
0x1800577cc  lea     rax, ??_7CTempOutputStream@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@6B@; const MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::CTempOutputStream::`vftable'
0x1800577d3  mov     rbx, r8
0x1800577d6  mov     [rbp+50h+var_80], rax
0x1800577da  mov     rdi, rcx
0x1800577dd  lea     rcx, [rbp+50h+var_78]; void *
0x1800577e1  movups  [rbp+50h+var_A8], xmm0
0x1800577e5  lea     r8d, [rdx+58h]; Size
0x1800577e9  movups  [rbp+50h+var_90], xmm0
0x1800577ed  call    memset
0x1800577f2  cmp     dword ptr [rsi+8], 0FFFFFFFFh
0x1800577f6  jnz     short loc_18005782F
0x1800577f8  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800577ff  mov     [rsp+150h+var_100], 0C16h
0x180057808  mov     qword ptr [rsp+150h+var_110], rax
0x18005780d  lea     rdx, [rsp+150h+var_110]
0x180057812  lea     rax, aMicrodomimplem_12; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180057819  mov     qword ptr [rsp+150h+var_110+8], rax
0x18005781e  lea     rax, aRootRootInvali; "Root != Root.InvalidValue()"
0x180057825  mov     [rsp+150h+var_F8], rax
0x18005782a  jmp     loc_1800578CE
0x18005782f  test    rbx, rbx
0x180057832  jnz     short loc_180057876
0x180057834  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18005783b  mov     [rsp+150h+var_E0], 0C17h
0x180057844  mov     [rsp+150h+var_F0], rax
0x180057849  lea     rdx, [rsp+150h+var_F0]
0x18005784e  lea     rax, aMicrodomimplem_12; "MicrodomImplementation::CMicrodom_IRtlM"...
0x180057855  mov     [rsp+150h+var_E8], rax
0x18005785a  lea     rcx, [rbp+50h+var_B0]
0x18005785e  lea     rax, aNotNullCheckFa_0; "Not-null check failed: Result"
0x180057865  mov     [rsp+150h+var_D8], rax
0x18005786a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18005786f  mov     ebx, eax
0x180057871  jmp     loc_180057971
0x180057876  mov     rax, [rdi]
0x180057879  lea     r8, [rbp+50h+var_90]
0x18005787d  movups  xmm0, xmmword ptr [rsi]
0x180057880  lea     rdx, [rsp+150h+var_110]
0x180057885  mov     rcx, rdi
0x180057888  mov     rax, [rax+58h]
0x18005788c  movdqu  [rsp+150h+var_110], xmm0
0x180057892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057897  test    eax, eax
0x180057899  js      short loc_18005786F
0x18005789b  cmp     dword ptr [rbp+50h+var_90+8], 0FFFFFFFFh
0x18005789f  jnz     short loc_1800578D9
0x1800578a1  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x1800578a8  mov     [rbp+50h+var_C0], 0C1Ah
0x1800578b0  mov     [rbp+50h+var_D0], rax
0x1800578b4  lea     rdx, [rbp+50h+var_D0]
0x1800578b8  lea     rax, aMicrodomimplem_12; "MicrodomImplementation::CMicrodom_IRtlM"...
0x1800578bf  mov     [rbp+50h+var_C8], rax
0x1800578c3  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x1800578ca  mov     [rbp+50h+var_B8], rax
0x1800578ce  lea     rcx, [rbp+50h+var_B0]
0x1800578d2  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800578d7  jmp     short loc_18005786F
0x1800578d9  lea     rdx, [rsp+150h+var_120]
0x1800578de  xor     ecx, ecx
0x1800578e0  call    RtlCreateDefaultMicrodomXmlWriter
0x1800578e5  test    eax, eax
0x1800578e7  js      short loc_18005786F
0x1800578e9  lea     rax, [rbp+50h+var_78]
0x1800578ed  xor     r8d, r8d
0x1800578f0  mov     [rsp+150h+var_128], rax
0x1800578f5  lea     r9, [rbp+50h+var_A8]
0x1800578f9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800578fd  mov     [rsp+150h+var_130], 0
0x180057906  xor     ecx, ecx
0x180057908  call    RtlInitializeSmartLBlobWritingContext
0x18005790d  test    eax, eax
0x18005790f  js      loc_18005786F
0x180057915  movups  xmm0, xmmword ptr [rsi]
0x180057918  mov     rdx, [rsp+150h+var_120]
0x18005791d  lea     rax, [rdi-10h]
0x180057921  neg     rax
0x180057924  lea     r9, [rsp+150h+var_110]
0x180057929  lea     rax, [rbp+50h+var_80]
0x18005792d  sbb     r8, r8
0x180057930  mov     [rsp+150h+var_130], rax
0x180057935  and     r8, rdi
0x180057938  xor     ecx, ecx
0x18005793a  movdqu  [rsp+150h+var_110], xmm0
0x180057940  call    RtlWriteMicrodomXml
0x180057945  test    eax, eax
0x180057947  js      loc_18005786F
0x18005794d  movups  xmm2, xmmword ptr [rbx]
0x180057950  movsd   xmm3, qword ptr [rbx+10h]
0x180057955  movups  xmm0, [rbp+50h+var_A8]
0x180057959  movsd   xmm1, [rbp+50h+var_98]
0x18005795e  movups  xmmword ptr [rbx], xmm0
0x180057961  movsd   qword ptr [rbx+10h], xmm1
0x180057966  xor     ebx, ebx
0x180057968  movups  [rbp+50h+var_A8], xmm2
0x18005796c  movsd   [rbp+50h+var_98], xmm3
0x180057971  lea     rax, ??_7IRtlObject@Rtl@Windows@@6B@; const Windows::Rtl::IRtlObject::`vftable'
0x180057978  lea     rcx, [rsp+150h+var_120]
0x18005797d  mov     [rbp+50h+var_80], rax
0x180057981  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x180057986  lea     rcx, [rbp+50h+var_A8]
0x18005798a  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x18005798f  mov     eax, ebx
0x180057991  mov     rcx, [rbp+50h+var_20]
0x180057995  xor     rcx, rsp; StackCookie
0x180057998  call    __security_check_cookie
0x18005799d  mov     rbx, [rsp+150h+arg_18]
0x1800579a5  add     rsp, 140h
0x1800579ac  pop     rdi
0x1800579ad  pop     rsi
0x1800579ae  pop     rbp
0x1800579af  retn
```
