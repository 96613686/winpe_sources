# Windows::Security::Authentication::Web::Core::CWebTokenResponse::Serialize(Windows::Internal::Security::CPropertiesSerializer &)

- ea: `0x1800460c4`
- end: `0x180046665`
- name: `?Serialize@CWebTokenResponse@Core@Web@Authentication@Security@Windows@@AEAAJAEAVCPropertiesSerializer@5Internal@6@@Z`
- size: `1441`
- prototype: `int(Windows::Security::Authentication::Web::Core::CWebTokenResponse *__hidden this, struct Windows::Internal::Security::CPropertiesSerializer *)`
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180045fb0`
- `0x1800f7f50`
- `0x1800f9ec0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x1800174f8`
- `0x18001873c`
- `0x1800425b0`
- `0x1800460c4`
- `0x18004666c`
- `0x1800471e0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180046115`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180046115`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800463af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800463af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180046457`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180046471`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004648b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180046457`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180046471`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004648b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004619c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800462d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004619c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800462d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180046330`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800460fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800460fa`

## string_xrefs

- `0x180046303`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x18004635e`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x18004637b`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800463c3`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x180046417`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x18004649d`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800464ed`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x180046533`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x1800465d9`: `onecore\ds\security\tokenbroker\api\lib\webtoken.cpp`
- `0x180046329`: `WTRes_Token`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Security::Authentication::Web::Core::CWebTokenResponse::Serialize(
        Windows::Security::Authentication::Web::Core::CWebTokenResponse *this,
        struct Windows::Internal::Security::CPropertiesSerializer *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  int v6; // eax
  unsigned int v7; // edi
  unsigned __int8 *v8; // r14
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 (__fastcall ***v15)(_QWORD, GUID *, unsigned __int8 **); // rdi
  __int64 v16; // rcx
  __int64 v18; // rbx
  int v19; // eax
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  HSTRING v22; // rbx
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 (__fastcall *v27)(_QWORD, GUID *, unsigned __int8 **); // rbx
  int v28; // eax
  int v29; // eax
  unsigned int v30; // ebx
  unsigned __int8 *v31; // rdi
  HSTRING *v32; // rax
  int v33; // eax
  unsigned __int8 *v34; // [rsp+20h] [rbp-39h] BYREF
  unsigned int v35[2]; // [rsp+28h] [rbp-31h] BYREF
  unsigned int v36; // [rsp+30h] [rbp-29h] BYREF
  __int64 v37; // [rsp+38h] [rbp-21h] BYREF
  unsigned __int8 *v38; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v39; // [rsp+48h] [rbp-11h] BYREF
  HSTRING_HEADER v40; // [rsp+50h] [rbp-9h] BYREF
  HSTRING string; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !WindowsIsStringEmpty(*((HSTRING *)this + 12)) )
  {
    v22 = (HSTRING)*((_QWORD *)this + 12);
    if ( WindowsCreateStringReference(L"WTRes_Token", 0xBu, &v40, &v39) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v23 = Windows::Internal::Security::CPropertiesSerializer::AddStringProperty(a2, v39, v22);
    v14 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x490,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)v23,
        (int)v34);
      return v14;
    }
  }
  AcquireSRWLockShared((PSRWLOCK)this + 16);
  v38 = (unsigned __int8 *)this + 128;
  if ( !*((_QWORD *)this + 13) )
  {
LABEL_13:
    if ( this != (Windows::Security::Authentication::Web::Core::CWebTokenResponse *)-128LL )
      ReleaseSRWLockShared((PSRWLOCK)this + 16);
    v37 = 0;
    v11 = *((_QWORD *)this + 14);
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    v13 = v12(v11, &v37);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B6,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)v13,
        (int)v34);
      v26 = v37;
      if ( v37 )
      {
        v37 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      return v14;
    }
    if ( !v37 )
      goto LABEL_17;
    v36 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 56LL))(v37, &v36);
    if ( (v14 & 0x80000000) != 0 )
    {
      v20 = v14;
      v21 = 1210;
    }
    else
    {
      if ( !v36 )
        goto LABEL_17;
      v18 = v37;
      if ( WindowsCreateStringReference(L"WTRes_PropertyBag", 0x11u, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v19 = Windows::Internal::Security::CPropertiesSerializer::AddHStringPropertyBagProperty(a2, string, v18);
      v14 = v19;
      if ( v19 >= 0 )
      {
LABEL_17:
        v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, unsigned __int8 **))*((_QWORD *)this + 15);
        if ( !v15 )
        {
LABEL_18:
          v16 = v37;
          if ( v37 )
          {
            v37 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          return v14;
        }
        v34 = 0;
        v27 = **v15;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        v28 = v27(v15, &GUID_ad7b0e08_6151_4da3_b6ba_890936053b0e, &v34);
        v14 = v28;
        if ( v28 >= 0 )
        {
          v38 = 0;
          v35[0] = 0;
          v39 = (HSTRING)&v38;
          v40.Reserved.Reserved1 = &v34;
          v40.Reserved.Reserved2[8] = 1;
          v29 = (*(__int64 (__fastcall **)(unsigned __int8 *, unsigned __int8 **, unsigned int *))(*(_QWORD *)v34 + 32LL))(
                  v34,
                  &v38,
                  v35);
          v14 = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4D5,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
              (const char *)(unsigned int)v29,
              (int)v34);
            if ( v38 && v34 )
              (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v34 + 40LL))(v34);
          }
          else
          {
            v30 = v35[0];
            v31 = v38;
            v32 = Windows::Internal::StringReference::StringReference(&string, L"WTRes_Error");
            v33 = Windows::Internal::Security::CPropertiesSerializer::AddBytesProperty(a2, *v32, v31, v30);
            v14 = v33;
            if ( v33 >= 0 )
            {
              if ( v38 && v34 )
                (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v34 + 40LL))(v34);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
              goto LABEL_18;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4DA,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
              (const char *)(unsigned int)v33,
              (int)v34);
            if ( v38 && v34 )
              (*(void (__fastcall **)(unsigned __int8 *))(*(_QWORD *)v34 + 40LL))(v34);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4C7,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
            (const char *)(unsigned int)v28,
            (int)v34);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
LABEL_50:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
        return v14;
      }
      v20 = (unsigned int)v19;
      v21 = 1216;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)v20,
      (int)v34);
    goto LABEL_50;
  }
  *(_QWORD *)v35 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<IXProcByValueMarshalHelper>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))this + 13,
         (__int64)v35);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49A,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
      (const char *)(unsigned int)v4,
      (int)v34);
    v24 = *(_QWORD *)v35;
    if ( *(_QWORD *)v35 )
    {
      *(_QWORD *)v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  else
  {
    v34 = 0;
    v36 = 0;
    v39 = (HSTRING)&v34;
    v40.Reserved.Reserved1 = v35;
    v40.Reserved.Reserved2[8] = 1;
    v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 **, unsigned int *))(**(_QWORD **)v35 + 32LL))(
           *(_QWORD *)v35,
           &v34,
           &v36);
    v5 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A8,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)v6,
        (int)v34);
      if ( v34 && *(_QWORD *)v35 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 40LL))(*(_QWORD *)v35);
      v25 = *(_QWORD *)v35;
      if ( *(_QWORD *)v35 )
      {
        *(_QWORD *)v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      }
    }
    else
    {
      v7 = v36;
      v8 = v34;
      if ( WindowsCreateStringReference(L"WTRes_Account", 0xDu, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v9 = Windows::Internal::Security::CPropertiesSerializer::AddBytesProperty(a2, string, v8, v7);
      v5 = v9;
      if ( v9 >= 0 )
      {
        if ( v34 && *(_QWORD *)v35 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 40LL))(*(_QWORD *)v35);
        v10 = *(_QWORD *)v35;
        if ( *(_QWORD *)v35 )
        {
          *(_QWORD *)v35 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        }
        goto LABEL_13;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4AD,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\webtoken.cpp",
        (const char *)(unsigned int)v9,
        (int)v34);
      if ( v34 && *(_QWORD *)v35 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v35 + 40LL))(*(_QWORD *)v35);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
    }
  }
  if ( this != (Windows::Security::Authentication::Web::Core::CWebTokenResponse *)-128LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 16);
  return v5;
}

```

## disassembly

```asm
0x1800460c4  mov     [rsp-8+arg_10], rbx
0x1800460c9  mov     [rsp-8+arg_18], rsi
0x1800460ce  push    rbp
0x1800460cf  push    rdi
0x1800460d0  push    r12
0x1800460d2  push    r14
0x1800460d4  push    r15
0x1800460d6  lea     rbp, [rsp-37h]
0x1800460db  sub     rsp, 90h
0x1800460e2  mov     rax, cs:__security_cookie
0x1800460e9  xor     rax, rsp
0x1800460ec  mov     [rbp+57h+var_28], rax
0x1800460f0  mov     r15, rdx
0x1800460f3  mov     rsi, rcx
0x1800460f6  mov     rcx, [rcx+60h]; string
0x1800460fa  call    cs:__imp_WindowsIsStringEmpty
0x180046100  xor     r12d, r12d
0x180046103  test    eax, eax
0x180046105  jz      loc_180046318
0x18004610b  lea     rbx, [rsi+80h]
0x180046112  mov     rcx, rbx; SRWLock
0x180046115  call    cs:__imp_AcquireSRWLockShared
0x18004611b  mov     [rbp+57h+var_70], rbx
0x18004611f  lea     rcx, [rsi+68h]
0x180046123  cmp     [rcx], r12
0x180046126  jz      loc_1800461FF
0x18004612c  mov     qword ptr [rbp+57h+var_88], r12
0x180046130  lea     rdx, [rbp+57h+var_88]
0x180046134  call    ??$As@UIXProcByValueMarshalHelper@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXProcByValueMarshalHelper@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<IXProcByValueMarshalHelper>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXProcByValueMarshalHelper>>)
0x180046139  mov     edi, eax
0x18004613b  test    eax, eax
0x18004613d  js      loc_180046374
0x180046143  mov     [rbp+57h+var_90], r12
0x180046147  mov     [rbp+57h+var_80], r12d
0x18004614b  lea     rax, [rbp+57h+var_90]
0x18004614f  mov     [rbp+57h+var_68], rax
0x180046153  lea     rax, [rbp+57h+var_88]
0x180046157  mov     qword ptr [rbp+57h+var_60.Reserved], rax
0x18004615b  mov     byte ptr [rbp+57h+var_60.Reserved+8], 1
0x18004615f  mov     rcx, qword ptr [rbp+57h+var_88]
0x180046163  mov     rax, [rcx]
0x180046166  lea     r8, [rbp+57h+var_80]
0x18004616a  lea     rdx, [rbp+57h+var_90]
0x18004616e  mov     rax, [rax+20h]
0x180046172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046177  mov     edi, eax
0x180046179  test    eax, eax
0x18004617b  js      loc_1800463BC
0x180046181  mov     edi, [rbp+57h+var_80]
0x180046184  mov     r14, [rbp+57h+var_90]
0x180046188  lea     r9, [rbp+57h+string]; string
0x18004618c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180046190  mov     edx, 0Dh; length
0x180046195  lea     rcx, aWtresAccount; "WTRes_Account"
0x18004619c  call    cs:__imp_WindowsCreateStringReference
0x1800461a2  test    eax, eax
0x1800461a4  js      loc_180046448
0x1800461aa  mov     r9d, edi; unsigned int
0x1800461ad  mov     r8, r14; unsigned __int8 *
0x1800461b0  mov     rdx, [rbp+57h+string]; HSTRING
0x1800461b4  mov     rcx, r15; this
0x1800461b7  call    ?AddBytesProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAEK@Z; Windows::Internal::Security::CPropertiesSerializer::AddBytesProperty(HSTRING__ *,uchar *,ulong)
0x1800461bc  mov     edi, eax
0x1800461be  test    eax, eax
0x1800461c0  js      loc_1800464E6
0x1800461c6  mov     rdx, [rbp+57h+var_90]
0x1800461ca  test    rdx, rdx
0x1800461cd  jz      short loc_1800461E5
0x1800461cf  mov     rcx, qword ptr [rbp+57h+var_88]
0x1800461d3  test    rcx, rcx
0x1800461d6  jz      short loc_1800461E5
0x1800461d8  mov     rax, [rcx]
0x1800461db  mov     rax, [rax+28h]
0x1800461df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461e4  nop
0x1800461e5  mov     rcx, qword ptr [rbp+57h+var_88]
0x1800461e9  test    rcx, rcx
0x1800461ec  jz      short loc_1800461FF
0x1800461ee  mov     qword ptr [rbp+57h+var_88], r12
0x1800461f2  mov     rax, [rcx]
0x1800461f5  mov     rax, [rax+10h]
0x1800461f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800461fe  nop
0x1800461ff  test    rbx, rbx
0x180046202  jz      short loc_18004620D
0x180046204  mov     rcx, rbx; SRWLock
0x180046207  call    cs:__imp_ReleaseSRWLockShared
0x18004620d  mov     [rbp+57h+var_78], r12
0x180046211  mov     rdi, [rsi+70h]
0x180046215  mov     rax, [rdi]
0x180046218  mov     rbx, [rax+48h]
0x18004621c  lea     rcx, [rbp+57h+var_78]
0x180046220  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046225  lea     rdx, [rbp+57h+var_78]
0x180046229  mov     rcx, rdi
0x18004622c  mov     rax, rbx
0x18004622f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046234  mov     ebx, eax
0x180046236  test    eax, eax
0x180046238  js      loc_180046410
0x18004623e  mov     rcx, [rbp+57h+var_78]
0x180046242  test    rcx, rcx
0x180046245  jnz     short loc_180046298
0x180046247  mov     rdi, [rsi+78h]
0x18004624b  test    rdi, rdi
0x18004624e  jnz     loc_1800465A3
0x180046254  mov     rcx, [rbp+57h+var_78]
0x180046258  test    rcx, rcx
0x18004625b  jz      short loc_18004626E
0x18004625d  mov     [rbp+57h+var_78], r12
0x180046261  mov     rax, [rcx]
0x180046264  mov     rax, [rax+10h]
0x180046268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004626d  nop
0x18004626e  mov     eax, ebx
0x180046270  mov     rcx, [rbp+57h+var_28]
0x180046274  xor     rcx, rsp; StackCookie
0x180046277  call    __security_check_cookie
0x18004627c  lea     r11, [rsp+0B0h+var_20]
0x180046284  mov     rbx, [r11+40h]
0x180046288  mov     rsi, [r11+48h]
0x18004628c  mov     rsp, r11
0x18004628f  pop     r15
0x180046291  pop     r14
0x180046293  pop     r12
0x180046295  pop     rdi
0x180046296  pop     rbp
0x180046297  retn
0x180046298  mov     [rbp+57h+var_80], r12d
0x18004629c  mov     rax, [rcx]
0x18004629f  lea     rdx, [rbp+57h+var_80]
0x1800462a3  mov     rax, [rax+38h]
0x1800462a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800462ac  mov     ebx, eax
0x1800462ae  test    eax, eax
0x1800462b0  js      loc_180046596
0x1800462b6  cmp     [rbp+57h+var_80], r12d
0x1800462ba  jbe     short loc_180046247
0x1800462bc  mov     rbx, [rbp+57h+var_78]
0x1800462c0  lea     r9, [rbp+57h+string]; string
0x1800462c4  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800462c8  mov     edx, 11h; length
0x1800462cd  lea     rcx, aWtresPropertyb; "WTRes_PropertyBag"
0x1800462d4  call    cs:__imp_WindowsCreateStringReference
0x1800462da  test    eax, eax
0x1800462dc  js      loc_180046462
0x1800462e2  mov     r8, rbx
0x1800462e5  mov     rdx, [rbp+57h+string]
0x1800462e9  mov     rcx, r15
0x1800462ec  call    ?AddHStringPropertyBagProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@PEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@4@@Z; Windows::Internal::Security::CPropertiesSerializer::AddHStringPropertyBagProperty(HSTRING__ *,Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *)
0x1800462f1  mov     ebx, eax
0x1800462f3  test    eax, eax
0x1800462f5  jns     loc_180046247
0x1800462fb  mov     r9d, eax; char *
0x1800462fe  mov     edx, 4C0h; void *
0x180046303  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x18004630a  mov     rcx, [rbp+5Fh]; this
0x18004630e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046313  jmp     loc_1800464D8
0x180046318  mov     rbx, [rsi+60h]
0x18004631c  lea     r9, [rbp+57h+var_68]; string
0x180046320  lea     r8, [rbp+57h+var_60]; hstringHeader
0x180046324  mov     edx, 0Bh; length
0x180046329  lea     rcx, aWtresToken; "WTRes_Token"
0x180046330  call    cs:__imp_WindowsCreateStringReference
0x180046336  test    eax, eax
0x180046338  js      loc_18004647C
0x18004633e  mov     r8, rbx; HSTRING
0x180046341  mov     rdx, [rbp+57h+var_68]; HSTRING
0x180046345  mov     rcx, r15; this
0x180046348  call    ?AddStringProperty@CPropertiesSerializer@Security@Internal@Windows@@QEAAJPEAUHSTRING__@@0@Z; Windows::Internal::Security::CPropertiesSerializer::AddStringProperty(HSTRING__ *,HSTRING__ *)
0x18004634d  mov     ebx, eax
0x18004634f  test    eax, eax
0x180046351  jns     loc_18004610B
0x180046357  mov     rcx, [rbp+5Fh]; this
0x18004635b  mov     r9d, eax; char *
0x18004635e  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180046365  mov     edx, 490h; void *
0x18004636a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004636f  jmp     loc_18004626E
0x180046374  mov     rcx, [rbp+5Fh]; this
0x180046378  mov     r9d, edi; char *
0x18004637b  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x180046382  mov     edx, 49Ah; void *
0x180046387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004638c  nop
0x18004638d  mov     rcx, qword ptr [rbp+57h+var_88]
0x180046391  test    rcx, rcx
0x180046394  jz      short loc_1800463A7
0x180046396  mov     qword ptr [rbp+57h+var_88], r12
0x18004639a  mov     rax, [rcx]
0x18004639d  mov     rax, [rax+10h]
0x1800463a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463a6  nop
0x1800463a7  test    rbx, rbx
0x1800463aa  jz      short loc_1800463B5
0x1800463ac  mov     rcx, rbx; SRWLock
0x1800463af  call    cs:__imp_ReleaseSRWLockShared
0x1800463b5  mov     eax, edi
0x1800463b7  jmp     loc_180046270
0x1800463bc  mov     rcx, [rbp+5Fh]; this
0x1800463c0  mov     r9d, edi; char *
0x1800463c3  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800463ca  mov     edx, 4A8h; void *
0x1800463cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800463d4  nop
0x1800463d5  mov     rdx, [rbp+57h+var_90]
0x1800463d9  test    rdx, rdx
0x1800463dc  jz      short loc_1800463F4
0x1800463de  mov     rcx, qword ptr [rbp+57h+var_88]
0x1800463e2  test    rcx, rcx
0x1800463e5  jz      short loc_1800463F4
0x1800463e7  mov     rax, [rcx]
0x1800463ea  mov     rax, [rax+28h]
0x1800463ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800463f3  nop
0x1800463f4  mov     rcx, qword ptr [rbp+57h+var_88]
0x1800463f8  test    rcx, rcx
0x1800463fb  jz      short loc_18004640E
0x1800463fd  mov     qword ptr [rbp+57h+var_88], r12
0x180046401  mov     rax, [rcx]
0x180046404  mov     rax, [rax+10h]
0x180046408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004640d  nop
0x18004640e  jmp     short loc_1800463A7
0x180046410  mov     rcx, [rbp+5Fh]; this
0x180046414  mov     r9d, ebx; char *
0x180046417  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x18004641e  mov     edx, 4B6h; void *
0x180046423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046428  nop
0x180046429  mov     rcx, [rbp+57h+var_78]
0x18004642d  test    rcx, rcx
0x180046430  jz      short loc_180046443
0x180046432  mov     [rbp+57h+var_78], r12
0x180046436  mov     rax, [rcx]
0x180046439  mov     rax, [rax+10h]
0x18004643d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046442  nop
0x180046443  jmp     loc_18004626E
0x180046448  xor     r9d, r9d; lpArguments
0x18004644b  xor     r8d, r8d; nNumberOfArguments
0x18004644e  lea     edx, [r9+1]; dwExceptionFlags
0x180046452  mov     ecx, 0C000000Dh; dwExceptionCode
0x180046457  call    cs:__imp_RaiseException
0x18004645d  jmp     loc_1800461AA
0x180046462  xor     r9d, r9d; lpArguments
0x180046465  xor     r8d, r8d; nNumberOfArguments
0x180046468  lea     edx, [r9+1]; dwExceptionFlags
0x18004646c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180046471  call    cs:__imp_RaiseException
0x180046477  jmp     loc_1800462E2
0x18004647c  xor     r9d, r9d; lpArguments
0x18004647f  xor     r8d, r8d; nNumberOfArguments
0x180046482  lea     edx, [r9+1]; dwExceptionFlags
0x180046486  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004648b  call    cs:__imp_RaiseException
0x180046491  jmp     loc_18004633E
0x180046496  mov     rcx, [rbp+5Fh]; this
0x18004649a  mov     r9d, eax; char *
0x18004649d  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800464a4  mov     edx, 4D5h; void *
0x1800464a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800464ae  nop
0x1800464af  mov     rdx, [rbp+57h+var_70]
0x1800464b3  test    rdx, rdx
0x1800464b6  jz      short loc_1800464CE
0x1800464b8  mov     rcx, [rbp+57h+var_90]
0x1800464bc  test    rcx, rcx
0x1800464bf  jz      short loc_1800464CE
0x1800464c1  mov     rax, [rcx]
0x1800464c4  mov     rax, [rax+28h]
0x1800464c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800464cd  nop
0x1800464ce  lea     rcx, [rbp+57h+var_90]
0x1800464d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800464d7  nop
0x1800464d8  lea     rcx, [rbp+57h+var_78]
0x1800464dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800464e1  jmp     loc_18004626E
0x1800464e6  mov     rcx, [rbp+5Fh]; this
0x1800464ea  mov     r9d, edi; char *
0x1800464ed  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800464f4  mov     edx, 4ADh; void *
0x1800464f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800464fe  nop
0x1800464ff  mov     rdx, [rbp+57h+var_90]
0x180046503  test    rdx, rdx
0x180046506  jz      short loc_18004651E
0x180046508  mov     rcx, qword ptr [rbp+57h+var_88]
0x18004650c  test    rcx, rcx
0x18004650f  jz      short loc_18004651E
0x180046511  mov     rax, [rcx]
0x180046514  mov     rax, [rax+28h]
0x180046518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004651d  nop
0x18004651e  lea     rcx, [rbp+57h+var_88]
0x180046522  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046527  jmp     loc_1800463A7
0x18004652c  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
