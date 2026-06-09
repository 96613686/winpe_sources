# NgcIsoContainer::InternalGetKeyAikCertificate(_GUID,ushort const *,uchar * *,ulong *)

- ea: `0x180023590`
- end: `0x180023894`
- name: `?InternalGetKeyAikCertificate@NgcIsoContainer@@AEAAJU_GUID@@PEBGPEAPEAEPEAK@Z`
- size: `772`
- prototype: `__int64 __fastcall(NgcIsoContainer *__hidden this, struct _GUID *Buf1, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180007670`
- `0x1800084a4`
- `0x18000a188`
- `0x18000d62c`
- `0x18000fa2c`
- `0x180010360`
- `0x180011c1c`
- `0x180011c9c`
- `0x18001cbe8`
- `0x18001cf64`
- `0x18001e120`
- `0x180023590`
- `0x180023a48`
- `0x18002ba68`
- `0x1800528c0`
- `0x18006fd00`
- `0x180070e3c`
- `0x1800727a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023608`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023608`
- `webauthn!WebAuthNDecodeAccountInformation` at `0x180023711`
- `webauthn!WebAuthNDecodeAccountInformation` at `0x180023711`

## string_xrefs

- `0x1800235eb`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180023657`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800236ab`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x180023724`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x1800237d7`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`
- `0x18002381a`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_keyoperations.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NgcIsoContainer::InternalGetKeyAikCertificate(
        RTL_SRWLOCK *this,
        struct _GUID *Buf1,
        const unsigned __int16 *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int v8; // ebx
  int KeyObject; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  struct Properties::UserIdKey *v12; // rbx
  int v13; // eax
  unsigned int v14; // edi
  int v15; // eax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // r10
  int AikCertificate; // eax
  void **v20; // r9
  unsigned int v21; // ebx
  int v22; // eax
  struct Properties::UserIdKey *v24; // [rsp+20h] [rbp-61h] BYREF
  NgcUtils *v25; // [rsp+28h] [rbp-59h] BYREF
  __int64 v26; // [rsp+30h] [rbp-51h]
  RTL_SRWLOCK *v27; // [rsp+40h] [rbp-41h] BYREF
  _BYTE v28[32]; // [rsp+48h] [rbp-39h] BYREF
  _BYTE v29[16]; // [rsp+68h] [rbp-19h] BYREF
  __int64 v30; // [rsp+78h] [rbp-9h]
  _BYTE v31[32]; // [rsp+88h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  if ( !memcmp_0(Buf1, qword_1800947A8, 0x10u) )
  {
    AcquireSRWLockShared(this + 2);
    v27 = this + 2;
    v24 = 0;
    KeyObject = NgcIsoContainer::InternalGetKeyObject((NgcIsoContainer *)this, a3, &v24);
    v8 = KeyObject;
    if ( KeyObject < 0 )
    {
      v10 = (unsigned int)KeyObject;
      v11 = 2275;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)v10,
        (int)v24);
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v27);
      return v8;
    }
    v12 = v24;
    if ( (unsigned int)Properties::Key::GetImplementationType(v24) != 2 )
    {
      v8 = -2146893783;
      v10 = 2148073513LL;
      v11 = 2279;
      goto LABEL_7;
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v28);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v29);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v31);
    v13 = NgcUtils::NgcContainerKeyName::ParseKeyNameString(v12, v28, v29, v31);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F0,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)v13,
        (int)v24);
LABEL_10:
      std::wstring::_Tidy_deallocate(v31);
      std::wstring::_Tidy_deallocate(v29);
      std::wstring::_Tidy_deallocate(v28);
      v8 = v14;
      goto LABEL_23;
    }
    if ( (unsigned __int8)std::wstring::_Equal(v28, L"FIDO_AUTHENTICATOR") )
    {
      v24 = 0;
      v15 = WebAuthNDecodeAccountInformation(
              *((_DWORD *)v12 + 32) - (unsigned int)*((_QWORD *)v12 + 15),
              *((_QWORD *)v12 + 15),
              &v24);
      v8 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8F9,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
          (const char *)(unsigned int)v15,
          (int)v24);
        wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(&v24);
        goto LABEL_14;
      }
      std::wstring::assign(v28, *(_QWORD *)(*((_QWORD *)v24 + 1) + 8LL));
      wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&void WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(&v24);
    }
    std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&v25);
    if ( v30 )
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&this[19]);
    v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    AikCertificate = NgcCtnrCommon::GetAikCertificate(v18, v16, v17, (__int64)&v25);
    v8 = AikCertificate;
    if ( AikCertificate >= 0 )
    {
      v21 = v26 - (_DWORD)v25;
      v22 = NgcUtils::CoMemAllocCopy(v25, v26 - (_QWORD)v25, (unsigned __int64)a4, v20);
      v14 = v22;
      if ( v22 >= 0 )
      {
        *a5 = v21;
        std::vector<unsigned char>::_Tidy(&v25);
        std::wstring::_Tidy_deallocate(v31);
        std::wstring::_Tidy_deallocate(v29);
        std::wstring::_Tidy_deallocate(v28);
        v8 = 0;
        goto LABEL_23;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x908,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
        (const char *)(unsigned int)v22,
        (int)v24);
      std::vector<unsigned char>::_Tidy(&v25);
      goto LABEL_10;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x903,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
      (const char *)(unsigned int)AikCertificate,
      (int)v24);
    std::vector<unsigned char>::_Tidy(&v25);
LABEL_14:
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(v29);
    std::wstring::_Tidy_deallocate(v28);
    goto LABEL_23;
  }
  v8 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8DC,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_keyoperations.cpp",
    (const char *)0x80070057LL,
    (int)v24);
  return v8;
}

```

## disassembly

```asm
0x180023590  mov     [rsp-8+arg_8], rbx
0x180023595  push    rbp
0x180023596  push    rsi
0x180023597  push    rdi
0x180023598  push    r14
0x18002359a  push    r15
0x18002359c  lea     rbp, [rsp-2Fh]
0x1800235a1  sub     rsp, 0B0h
0x1800235a8  mov     rax, cs:__security_cookie
0x1800235af  xor     rax, rsp
0x1800235b2  mov     [rbp+4Fh+var_28], rax
0x1800235b6  mov     r15, r9
0x1800235b9  mov     rdi, r8
0x1800235bc  mov     rax, rdx
0x1800235bf  mov     rsi, rcx
0x1800235c2  mov     r14, [rbp+4Fh+arg_20]
0x1800235c6  mov     r8d, 10h; Size
0x1800235cc  lea     rdx, qword_1800947A8; Buf2
0x1800235d3  mov     rcx, rax; Buf1
0x1800235d6  call    memcmp_0
0x1800235db  test    eax, eax
0x1800235dd  jz      short loc_180023601
0x1800235df  mov     rcx, [rbp+57h]; this
0x1800235e3  mov     ebx, 80070057h
0x1800235e8  mov     r9d, ebx; char *
0x1800235eb  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800235f2  mov     edx, 8DCh; void *
0x1800235f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800235fc  jmp     loc_18002386F
0x180023601  lea     rbx, [rsi+10h]
0x180023605  mov     rcx, rbx; SRWLock
0x180023608  call    cs:__imp_AcquireSRWLockShared
0x18002360e  mov     [rbp+4Fh+var_90], rbx
0x180023612  mov     [rbp+4Fh+var_B0], 0
0x18002361a  lea     r8, [rbp+4Fh+var_B0]; struct Properties::UserIdKey **
0x18002361e  mov     rdx, rdi; unsigned __int16 *
0x180023621  mov     rcx, rsi; this
0x180023624  call    ?InternalGetKeyObject@NgcIsoContainer@@AEAAJPEBGPEAPEAUUserIdKey@Properties@@@Z; NgcIsoContainer::InternalGetKeyObject(ushort const *,Properties::UserIdKey * *)
0x180023629  mov     ebx, eax
0x18002362b  test    eax, eax
0x18002362d  jns     short loc_180023639
0x18002362f  mov     r9d, eax
0x180023632  mov     edx, 8E3h
0x180023637  jmp     short loc_180023657
0x180023639  mov     rbx, [rbp+4Fh+var_B0]
0x18002363d  mov     rcx, rbx
0x180023640  call    ?GetImplementationType@Key@Properties@@QEBA?AW4ImplementationType@12@XZ; Properties::Key::GetImplementationType(void)
0x180023645  cmp     eax, 2
0x180023648  jz      short loc_18002366C
0x18002364a  mov     ebx, 80090029h
0x18002364f  mov     r9d, ebx; char *
0x180023652  mov     edx, 8E7h; void *
0x180023657  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002365e  mov     rcx, [rbp+57h]; this
0x180023662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023667  jmp     loc_180023866
0x18002366c  lea     rcx, [rbp+4Fh+var_88]
0x180023670  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180023675  nop
0x180023676  lea     rcx, [rbp+4Fh+var_68]
0x18002367a  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002367f  nop
0x180023680  lea     rcx, [rbp+4Fh+var_48]
0x180023684  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x180023689  nop
0x18002368a  lea     r9, [rbp+4Fh+var_48]
0x18002368e  lea     r8, [rbp+4Fh+var_68]
0x180023692  lea     rdx, [rbp+4Fh+var_88]
0x180023696  mov     rcx, rbx
0x180023699  call    ?ParseKeyNameString@NgcContainerKeyName@NgcUtils@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@11@Z; NgcUtils::NgcContainerKeyName::ParseKeyNameString(std::wstring const &,std::wstring *,std::wstring *,std::wstring *)
0x18002369e  mov     edi, eax
0x1800236a0  test    eax, eax
0x1800236a2  jns     short loc_1800236E1
0x1800236a4  mov     rcx, [rbp+57h]; this
0x1800236a8  mov     r9d, eax; char *
0x1800236ab  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800236b2  mov     edx, 8F0h; void *
0x1800236b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800236bc  nop
0x1800236bd  lea     rcx, [rbp+4Fh+var_48]
0x1800236c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800236c6  nop
0x1800236c7  lea     rcx, [rbp+4Fh+var_68]
0x1800236cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800236d0  nop
0x1800236d1  lea     rcx, [rbp+4Fh+var_88]
0x1800236d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800236da  mov     ebx, edi
0x1800236dc  jmp     loc_180023866
0x1800236e1  lea     rdx, aFidoAuthentica; "FIDO_AUTHENTICATOR"
0x1800236e8  lea     rcx, [rbp+4Fh+var_88]
0x1800236ec  call    ?_Equal@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_NQEBG@Z; std::wstring::_Equal(ushort const * const)
0x1800236f1  test    al, al
0x1800236f3  jz      loc_180023781
0x1800236f9  mov     [rbp+4Fh+var_B0], 0
0x180023701  mov     rdx, [rbx+78h]
0x180023705  mov     ecx, [rbx+80h]
0x18002370b  sub     ecx, edx
0x18002370d  lea     r8, [rbp+4Fh+var_B0]
0x180023711  call    cs:__imp_WebAuthNDecodeAccountInformation
0x180023717  mov     ebx, eax
0x180023719  test    eax, eax
0x18002371b  jns     short loc_180023762
0x18002371d  mov     rcx, [rbp+57h]; this
0x180023721  mov     r9d, eax; char *
0x180023724  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18002372b  mov     edx, 8F9h; void *
0x180023730  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023735  nop
0x180023736  lea     rcx, [rbp+4Fh+var_B0]
0x18002373a  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_CBOR_ACCOUNT_INFORMATION@@P6AXPEAU1@@Z$1?WebAuthNFreeDecodedAccountInformation@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(void)
0x18002373f  nop
0x180023740  lea     rcx, [rbp+4Fh+var_48]
0x180023744  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023749  nop
0x18002374a  lea     rcx, [rbp+4Fh+var_68]
0x18002374e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023753  nop
0x180023754  lea     rcx, [rbp+4Fh+var_88]
0x180023758  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002375d  jmp     loc_180023866
0x180023762  mov     rax, [rbp+4Fh+var_B0]
0x180023766  mov     rdx, [rax+8]
0x18002376a  mov     rdx, [rdx+8]
0x18002376e  lea     rcx, [rbp+4Fh+var_88]
0x180023772  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180023777  nop
0x180023778  lea     rcx, [rbp+4Fh+var_B0]
0x18002377c  call    ??1?$unique_storage@U?$resource_policy@PEAU_WEBAUTHN_CBOR_ACCOUNT_INFORMATION@@P6AXPEAU1@@Z$1?WebAuthNFreeDecodedAccountInformation@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,void (*)(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),&WebAuthNFreeDecodedAccountInformation(_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *),wistd::integral_constant<unsigned __int64,0>,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,_WEBAUTHN_CBOR_ACCOUNT_INFORMATION *,0,std::nullptr_t>>(void)
0x180023781  lea     rcx, [rbp+4Fh+var_A8]
0x180023785  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x18002378a  nop
0x18002378b  cmp     [rbp+4Fh+var_58], 0
0x180023790  jnz     short loc_180023797
0x180023792  xor     r8d, r8d
0x180023795  jmp     short loc_1800237A3
0x180023797  lea     rcx, [rbp+4Fh+var_68]
0x18002379b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800237a0  mov     r8, rax
0x1800237a3  lea     rcx, [rsi+98h]
0x1800237aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800237af  mov     r10, rax
0x1800237b2  lea     rcx, [rbp+4Fh+var_88]
0x1800237b6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800237bb  mov     rdx, rax
0x1800237be  lea     r9, [rbp+4Fh+var_A8]
0x1800237c2  mov     rcx, r10
0x1800237c5  call    ?GetAikCertificate@NgcCtnrCommon@@YAJQEBG00PEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcCtnrCommon::GetAikCertificate(ushort const * const,ushort const * const,ushort const * const,std::vector<uchar> *)
0x1800237ca  mov     ebx, eax
0x1800237cc  test    eax, eax
0x1800237ce  jns     short loc_1800237F7
0x1800237d0  mov     rcx, [rbp+57h]; this
0x1800237d4  mov     r9d, eax; char *
0x1800237d7  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800237de  mov     edx, 903h; void *
0x1800237e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800237e8  nop
0x1800237e9  lea     rcx, [rbp+4Fh+var_A8]
0x1800237ed  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800237f2  jmp     loc_180023740
0x1800237f7  mov     rbx, [rbp+4Fh+var_A0]
0x1800237fb  mov     rcx, [rbp+4Fh+var_A8]; this
0x1800237ff  sub     rbx, rcx
0x180023802  mov     r8, r15; unsigned __int64
0x180023805  mov     rdx, rbx; SourceSize
0x180023808  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x18002380d  mov     edi, eax
0x18002380f  test    eax, eax
0x180023811  jns     short loc_18002383A
0x180023813  mov     rcx, [rbp+57h]; this
0x180023817  mov     r9d, eax; char *
0x18002381a  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180023821  mov     edx, 908h; void *
0x180023826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002382b  nop
0x18002382c  lea     rcx, [rbp+4Fh+var_A8]
0x180023830  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180023835  jmp     loc_1800236BD
0x18002383a  mov     [r14], ebx
0x18002383d  lea     rcx, [rbp+4Fh+var_A8]
0x180023841  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180023846  nop
0x180023847  lea     rcx, [rbp+4Fh+var_48]
0x18002384b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023850  nop
0x180023851  lea     rcx, [rbp+4Fh+var_68]
0x180023855  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002385a  nop
0x18002385b  lea     rcx, [rbp+4Fh+var_88]
0x18002385f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180023864  xor     ebx, ebx
0x180023866  lea     rcx, [rbp+4Fh+var_90]
0x18002386a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002386f  mov     eax, ebx
0x180023871  mov     rcx, [rbp+4Fh+var_28]
0x180023875  xor     rcx, rsp; StackCookie
0x180023878  call    __security_check_cookie
0x18002387d  mov     rbx, [rsp+0D0h+arg_8]
0x180023885  add     rsp, 0B0h
0x18002388c  pop     r15
0x18002388e  pop     r14
0x180023890  pop     rdi
0x180023891  pop     rsi
0x180023892  pop     rbp
0x180023893  retn
```
