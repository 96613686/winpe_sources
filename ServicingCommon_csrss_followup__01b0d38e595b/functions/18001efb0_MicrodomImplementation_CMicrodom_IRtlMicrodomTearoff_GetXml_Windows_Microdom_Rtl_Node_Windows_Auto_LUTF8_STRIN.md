# MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml(Windows::Microdom::Rtl::Node,Windows::Auto<_LUTF8_STRING> *)

- ea: `0x18001efb0`
- end: `0x18001f1d1`
- name: `?GetXml@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@UEAAJUNode@Rtl@Microdom@Windows@@PEAV?$Auto@U_LUTF8_STRING@@@6@@Z`
- size: `545`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005258`
- `0x18001af00`
- `0x18001dbc0`
- `0x18001efb0`
- `0x18001f1d8`
- `0x18002d2b0`
- `0x180054500`
- `0x180065690`
- `0x180097e20`
- `0x18009e020`

## string_xrefs

- `0x18001f018`: `onecore\base\xml\udom_microdom.cpp`
- `0x18001f054`: `onecore\base\xml\udom_microdom.cpp`
- `0x18001f0c1`: `onecore\base\xml\udom_microdom.cpp`
- `0x18001f032`: `MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml`
- `0x18001f06e`: `MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml`
- `0x18001f0d8`: `MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::GetXml`

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
  __int64 v14[2]; // [rsp+30h] [rbp-D0h] BYREF
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
                                       v14[0],
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
0x18001efb0  mov     [rsp-8+arg_18], rbx
0x18001efb5  push    rbp
0x18001efb6  push    rsi
0x18001efb7  push    rdi
0x18001efb8  lea     rbp, [rsp-40h]
0x18001efbd  sub     rsp, 140h
0x18001efc4  mov     rax, cs:__security_cookie
0x18001efcb  xor     rax, rsp
0x18001efce  mov     [rbp+50h+var_20], rax
0x18001efd2  xor     eax, eax
0x18001efd4  mov     [rbp+50h+var_B0], 0
0x18001efdb  xorps   xmm0, xmm0
0x18001efde  mov     [rbp+50h+var_98], rax
0x18001efe2  mov     rsi, rdx
0x18001efe5  mov     [rsp+150h+var_120], rax
0x18001efea  xor     edx, edx; Val
0x18001efec  lea     rax, ??_7CTempOutputStream@CMicrodom_IRtlMicrodomTearoff@MicrodomImplementation@@6B@; const MicrodomImplementation::CMicrodom_IRtlMicrodomTearoff::CTempOutputStream::`vftable'
0x18001eff3  mov     rbx, r8
0x18001eff6  mov     [rbp+50h+var_80], rax
0x18001effa  mov     rdi, rcx
0x18001effd  lea     rcx, [rbp+50h+var_78]; void *
0x18001f001  movups  [rbp+50h+var_A8], xmm0
0x18001f005  lea     r8d, [rdx+58h]; Size
0x18001f009  movups  [rbp+50h+var_90], xmm0
0x18001f00d  call    memset
0x18001f012  cmp     dword ptr [rsi+8], 0FFFFFFFFh
0x18001f016  jnz     short loc_18001F04F
0x18001f018  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18001f01f  mov     [rsp+150h+var_100], 0C16h
0x18001f028  mov     qword ptr [rsp+150h+var_110], rax
0x18001f02d  lea     rdx, [rsp+150h+var_110]
0x18001f032  lea     rax, aMicrodomimplem_12; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18001f039  mov     qword ptr [rsp+150h+var_110+8], rax
0x18001f03e  lea     rax, aRootRootInvali; "Root != Root.InvalidValue()"
0x18001f045  mov     [rsp+150h+var_F8], rax
0x18001f04a  jmp     loc_18001F0EE
0x18001f04f  test    rbx, rbx
0x18001f052  jnz     short loc_18001F096
0x18001f054  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18001f05b  mov     [rsp+150h+var_E0], 0C17h
0x18001f064  mov     [rsp+150h+var_F0], rax
0x18001f069  lea     rdx, [rsp+150h+var_F0]
0x18001f06e  lea     rax, aMicrodomimplem_12; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18001f075  mov     [rsp+150h+var_E8], rax
0x18001f07a  lea     rcx, [rbp+50h+var_B0]
0x18001f07e  lea     rax, aNotNullCheckFa_0; "Not-null check failed: Result"
0x18001f085  mov     [rsp+150h+var_D8], rax
0x18001f08a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001f08f  mov     ebx, eax
0x18001f091  jmp     loc_18001F191
0x18001f096  mov     rax, [rdi]
0x18001f099  lea     r8, [rbp+50h+var_90]
0x18001f09d  movups  xmm0, xmmword ptr [rsi]
0x18001f0a0  lea     rdx, [rsp+150h+var_110]
0x18001f0a5  mov     rcx, rdi
0x18001f0a8  mov     rax, [rax+58h]
0x18001f0ac  movdqu  [rsp+150h+var_110], xmm0
0x18001f0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b7  test    eax, eax
0x18001f0b9  js      short loc_18001F08F
0x18001f0bb  cmp     dword ptr [rbp+50h+var_90+8], 0FFFFFFFFh
0x18001f0bf  jnz     short loc_18001F0F9
0x18001f0c1  lea     rax, aOnecoreBaseXml_1; "onecore\\base\\xml\\udom_microdom.cpp"
0x18001f0c8  mov     [rbp+50h+var_C0], 0C1Ah
0x18001f0d0  mov     [rbp+50h+var_D0], rax
0x18001f0d4  lea     rdx, [rbp+50h+var_D0]
0x18001f0d8  lea     rax, aMicrodomimplem_12; "MicrodomImplementation::CMicrodom_IRtlM"...
0x18001f0df  mov     [rbp+50h+var_C8], rax
0x18001f0e3  lea     rax, aTheelementThee; "TheElement != TheElement.InvalidValue()"
0x18001f0ea  mov     [rbp+50h+var_B8], rax
0x18001f0ee  lea     rcx, [rbp+50h+var_B0]
0x18001f0f2  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18001f0f7  jmp     short loc_18001F08F
0x18001f0f9  lea     rdx, [rsp+150h+var_120]
0x18001f0fe  xor     ecx, ecx
0x18001f100  call    RtlCreateDefaultMicrodomXmlWriter
0x18001f105  test    eax, eax
0x18001f107  js      short loc_18001F08F
0x18001f109  lea     rax, [rbp+50h+var_78]
0x18001f10d  xor     r8d, r8d
0x18001f110  mov     [rsp+150h+var_128], rax
0x18001f115  lea     r9, [rbp+50h+var_A8]
0x18001f119  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001f11d  mov     [rsp+150h+var_130], 0
0x18001f126  xor     ecx, ecx
0x18001f128  call    RtlInitializeSmartLBlobWritingContext
0x18001f12d  test    eax, eax
0x18001f12f  js      loc_18001F08F
0x18001f135  movups  xmm0, xmmword ptr [rsi]
0x18001f138  mov     rdx, [rsp+150h+var_120]
0x18001f13d  lea     rax, [rdi-10h]
0x18001f141  neg     rax
0x18001f144  lea     r9, [rsp+150h+var_110]
0x18001f149  lea     rax, [rbp+50h+var_80]
0x18001f14d  sbb     r8, r8
0x18001f150  mov     [rsp+150h+var_130], rax
0x18001f155  and     r8, rdi
0x18001f158  xor     ecx, ecx
0x18001f15a  movdqu  [rsp+150h+var_110], xmm0
0x18001f160  call    RtlWriteMicrodomXml
0x18001f165  test    eax, eax
0x18001f167  js      loc_18001F08F
0x18001f16d  movups  xmm2, xmmword ptr [rbx]
0x18001f170  movsd   xmm3, qword ptr [rbx+10h]
0x18001f175  movups  xmm0, [rbp+50h+var_A8]
0x18001f179  movsd   xmm1, [rbp+50h+var_98]
0x18001f17e  movups  xmmword ptr [rbx], xmm0
0x18001f181  movsd   qword ptr [rbx+10h], xmm1
0x18001f186  xor     ebx, ebx
0x18001f188  movups  [rbp+50h+var_A8], xmm2
0x18001f18c  movsd   [rbp+50h+var_98], xmm3
0x18001f191  lea     rax, ??_7IRtlObject@Rtl@Windows@@6B@; const Windows::Rtl::IRtlObject::`vftable'
0x18001f198  lea     rcx, [rsp+150h+var_120]
0x18001f19d  mov     [rbp+50h+var_80], rax
0x18001f1a1  call    ??1?$Auto@PEAUIRtlMicrodom@Rtl@Microdom@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Microdom::Rtl::IRtlMicrodom *>::~Auto<Windows::Microdom::Rtl::IRtlMicrodom *>(void)
0x18001f1a6  lea     rcx, [rbp+50h+var_A8]
0x18001f1aa  call    ?Close@?$AutoBlob@V?$Auto@U_LBLOB@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoBlob<Windows::Auto<_LBLOB>>::Close(void)
0x18001f1af  mov     eax, ebx
0x18001f1b1  mov     rcx, [rbp+50h+var_20]
0x18001f1b5  xor     rcx, rsp; StackCookie
0x18001f1b8  call    __security_check_cookie
0x18001f1bd  mov     rbx, [rsp+150h+arg_18]
0x18001f1c5  add     rsp, 140h
0x18001f1cc  pop     rdi
0x18001f1cd  pop     rsi
0x18001f1ce  pop     rbp
0x18001f1cf  retn
```
