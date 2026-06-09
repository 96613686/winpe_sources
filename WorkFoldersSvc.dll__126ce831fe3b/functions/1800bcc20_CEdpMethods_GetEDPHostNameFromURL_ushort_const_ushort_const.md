# CEdpMethods::GetEDPHostNameFromURL(ushort const *,ushort const * *)

- ea: `0x1800bcc20`
- end: `0x1800bced5`
- name: `?GetEDPHostNameFromURL@CEdpMethods@@UEAAJPEBGPEAPEBG@Z`
- size: `693`
- prototype: `int(CEdpMethods *__hidden this, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180004420`
- `0x180007e10`
- `0x180011314`
- `0x180021b04`
- `0x180059d50`
- `0x1800bbe18`
- `0x1800bc0f4`
- `0x1800bcc20`
- `0x1800bd244`
- `0x18013e010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800bcd03`
- `KERNEL32!RaiseException` at `0x1800bcd03`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800bce87`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800bce87`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800bcd0c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800bcd0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bccef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bccef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bce39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bce39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bcd6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800bcd6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bce66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bce70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bce7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bce66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bce70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bce7a`

## string_xrefs

- `0x1800bccac`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall CEdpMethods::GetEDPHostNameFromURL(
        unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 **a3)
{
  _BYTE *v6; // rax
  char v7; // cl
  HRESULT v8; // eax
  int v9; // ebx
  __int16 v10; // ax
  __int64 v11; // rdx
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, HSTRING, __int64 *); // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v15; // edi
  int v17; // [rsp+20h] [rbp-59h] BYREF
  int v18; // [rsp+24h] [rbp-55h]
  char v19; // [rsp+28h] [rbp-51h]
  const char *v20; // [rsp+30h] [rbp-49h]
  __int64 v21; // [rsp+38h] [rbp-41h]
  __int64 v22; // [rsp+40h] [rbp-39h] BYREF
  UINT32 length; // [rsp+48h] [rbp-31h] BYREF
  HSTRING v24; // [rsp+50h] [rbp-29h] BYREF
  HSTRING v25; // [rsp+58h] [rbp-21h] BYREF
  __int64 v26; // [rsp+60h] [rbp-19h] BYREF
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64); // [rsp+68h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-9h] BYREF
  HSTRING string; // [rsp+88h] [rbp+Fh] BYREF

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (v6[68] & 0x20) == 0 || (v7 = 1, v6[65] < 6u) )
    v7 = 0;
  v19 = v7;
  v20 = "CEdpMethods::GetEDPHostNameFromURL";
  v17 = 0;
  v18 = 146;
  v21 = 0;
  v27 = 0;
  v26 = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  length = 0;
  string = 0;
  v8 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v9 = RoInitialize(1);
  v17 = v9;
  v10 = 162;
  if ( v9 < 0 )
    goto LABEL_11;
  LOWORD(v18) = 162;
  v10 = 164;
  if ( !a2 || (LOWORD(v18) = 164, v10 = 165, !a3) )
  {
    v17 = -2147024809;
LABEL_11:
    HIWORD(v18) = v10;
    goto LABEL_24;
  }
  v17 = 0;
  v11 = -1;
  LOWORD(v18) = 165;
  *a3 = 0;
  do
    ++v11;
  while ( a2[v11] );
  v17 = WindowsCreateString(a2, v11, &v24);
  v10 = 172;
  if ( v17 < 0 )
    goto LABEL_11;
  LOWORD(v18) = 172;
  v17 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(
          (__int64)string,
          (__int64)&v27);
  v10 = 175;
  if ( v17 < 0 )
    goto LABEL_11;
  LOWORD(v18) = 175;
  v17 = Microsoft::WRL::ComPtr<IActivationFactory>::As<Windows::Foundation::IUriRuntimeClassFactory>(
          &v27,
          (__int64)&v26);
  v10 = 176;
  if ( v17 < 0 )
    goto LABEL_11;
  v12 = v26;
  LOWORD(v18) = 176;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v26 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v22);
  v17 = v13(v12, v24, &v22);
  v10 = 179;
  if ( v17 < 0 )
    goto LABEL_11;
  LOWORD(v18) = 179;
  v17 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 88LL))(v22, &v25);
  v10 = 182;
  if ( v17 < 0 )
    goto LABEL_11;
  LOWORD(v18) = 182;
  CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(this + 3);
  StringRawBuffer = WindowsGetStringRawBuffer(v25, &length);
  v17 = CSyncCoreStringUtils::StringCopyAlloc(StringRawBuffer, this + 3);
  v10 = 187;
  if ( v17 < 0 )
    goto LABEL_11;
  LOWORD(v18) = 187;
  *a3 = this[3];
LABEL_24:
  WindowsDeleteString(0);
  WindowsDeleteString(v24);
  WindowsDeleteString(v25);
  v15 = v17;
  if ( v9 >= 0 )
    RoUninitialize();
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v17);
  return v15;
}

```

## disassembly

```asm
0x1800bcc20  push    rbp
0x1800bcc22  push    rbx
0x1800bcc23  push    rsi
0x1800bcc24  push    rdi
0x1800bcc25  push    r12
0x1800bcc27  push    r14
0x1800bcc29  push    r15
0x1800bcc2b  lea     rbp, [rsp-27h]
0x1800bcc30  sub     rsp, 0A0h
0x1800bcc37  mov     rax, cs:__security_cookie
0x1800bcc3e  xor     rax, rsp
0x1800bcc41  mov     [rbp+57h+var_40], rax
0x1800bcc45  mov     r14, r8
0x1800bcc48  mov     rdi, rdx
0x1800bcc4b  mov     r15, rcx
0x1800bcc4e  mov     rax, cs:WPP_GLOBAL_Control
0x1800bcc55  lea     rcx, WPP_GLOBAL_Control
0x1800bcc5c  cmp     rax, rcx
0x1800bcc5f  jz      short loc_1800BCC89
0x1800bcc61  test    byte ptr [rax+44h], 20h
0x1800bcc65  jz      short loc_1800BCC89
0x1800bcc67  cmp     byte ptr [rax+41h], 6
0x1800bcc6b  jb      short loc_1800BCC89
0x1800bcc6d  mov     rcx, [rax+38h]
0x1800bcc71  lea     r8, WPP_72c5c6effac033b2a523fdb134c86117_Traceguids
0x1800bcc78  mov     edx, 0Dh
0x1800bcc7d  call    WPP_SF_
0x1800bcc82  mov     rax, cs:WPP_GLOBAL_Control
0x1800bcc89  xor     r12d, r12d
0x1800bcc8c  test    byte ptr [rax+44h], 20h
0x1800bcc90  lea     ebx, [r12+1]
0x1800bcc95  jz      short loc_1800BCC9F
0x1800bcc97  cmp     byte ptr [rax+41h], 6
0x1800bcc9b  mov     cl, bl
0x1800bcc9d  jnb     short loc_1800BCCA2
0x1800bcc9f  mov     cl, r12b
0x1800bcca2  mov     [rbp+57h+var_A8], cl
0x1800bcca5  lea     rax, aCedpmethodsGet; "CEdpMethods::GetEDPHostNameFromURL"
0x1800bccac  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x1800bccb3  mov     [rbp+57h+var_A0], rax
0x1800bccb7  lea     r9, [rbp+57h+string]; string
0x1800bccbb  mov     [rbp+57h+var_B0], r12d
0x1800bccbf  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800bccc3  mov     [rbp+57h+var_AC], 92h
0x1800bccca  mov     edx, 16h; length
0x1800bcccf  mov     [rbp+57h+var_98], r12
0x1800bccd3  mov     [rbp+57h+var_68], r12
0x1800bccd7  mov     [rbp+57h+var_70], r12
0x1800bccdb  mov     [rbp+57h+var_90], r12
0x1800bccdf  mov     [rbp+57h+var_80], r12
0x1800bcce3  mov     [rbp+57h+var_78], r12
0x1800bcce7  mov     [rbp+57h+length], r12d
0x1800bcceb  mov     [rbp+57h+string], r12
0x1800bccef  call    cs:__imp_WindowsCreateStringReference
0x1800bccf5  test    eax, eax
0x1800bccf7  jns     short loc_1800BCD0A
0x1800bccf9  xor     r9d, r9d; lpArguments
0x1800bccfc  xor     r8d, r8d; nNumberOfArguments
0x1800bccff  mov     edx, ebx; dwExceptionFlags
0x1800bcd01  mov     ecx, eax; dwExceptionCode
0x1800bcd03  call    cs:__imp_RaiseException
0x1800bcd09  int     3; Trap to Debugger
0x1800bcd0a  mov     ecx, ebx
0x1800bcd0c  call    cs:__imp_RoInitialize
0x1800bcd12  mov     ebx, eax
0x1800bcd14  mov     [rbp+57h+var_B0], eax
0x1800bcd17  test    eax, eax
0x1800bcd19  mov     eax, 0A2h
0x1800bcd1e  jns     short loc_1800BCD29
0x1800bcd20  mov     word ptr [rbp+57h+var_AC+2], ax
0x1800bcd24  jmp     loc_1800BCE64
0x1800bcd29  mov     word ptr [rbp+57h+var_AC], ax
0x1800bcd2d  mov     eax, 0A4h
0x1800bcd32  test    rdi, rdi
0x1800bcd35  jnz     short loc_1800BCD40
0x1800bcd37  mov     [rbp+57h+var_B0], 80070057h
0x1800bcd3e  jmp     short loc_1800BCD20
0x1800bcd40  mov     word ptr [rbp+57h+var_AC], ax
0x1800bcd44  mov     eax, 0A5h
0x1800bcd49  test    r14, r14
0x1800bcd4c  jz      short loc_1800BCD37
0x1800bcd4e  mov     [rbp+57h+var_B0], r12d
0x1800bcd52  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800bcd56  mov     word ptr [rbp+57h+var_AC], ax
0x1800bcd5a  mov     [r14], r12
0x1800bcd5d  inc     rdx; length
0x1800bcd60  cmp     [rdi+rdx*2], r12w
0x1800bcd65  jnz     short loc_1800BCD5D
0x1800bcd67  lea     r8, [rbp+57h+var_80]; string
0x1800bcd6b  mov     rcx, rdi; sourceString
0x1800bcd6e  call    cs:__imp_WindowsCreateString
0x1800bcd74  mov     [rbp+57h+var_B0], eax
0x1800bcd77  test    eax, eax
0x1800bcd79  mov     eax, 0ACh
0x1800bcd7e  js      short loc_1800BCD20
0x1800bcd80  mov     rcx, [rbp+57h+string]
0x1800bcd84  lea     rdx, [rbp+57h+var_68]
0x1800bcd88  mov     word ptr [rbp+57h+var_AC], ax
0x1800bcd8c  call    ??$GetActivationFactory@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<IActivationFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IActivationFactory>>)
0x1800bcd91  mov     [rbp+57h+var_B0], eax
0x1800bcd94  test    eax, eax
0x1800bcd96  mov     eax, 0AFh
0x1800bcd9b  js      short loc_1800BCD20
0x1800bcd9d  lea     rdx, [rbp+57h+var_70]
0x1800bcda1  mov     word ptr [rbp+57h+var_AC], ax
0x1800bcda5  lea     rcx, [rbp+57h+var_68]
0x1800bcda9  call    ??$As@UIUriRuntimeClassFactory@Foundation@Windows@@@?$ComPtr@UIActivationFactory@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IActivationFactory>::As<Windows::Foundation::IUriRuntimeClassFactory>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x1800bcdae  mov     [rbp+57h+var_B0], eax
0x1800bcdb1  test    eax, eax
0x1800bcdb3  mov     eax, 0B0h
0x1800bcdb8  js      loc_1800BCD20
0x1800bcdbe  mov     rsi, [rbp+57h+var_70]
0x1800bcdc2  lea     rcx, [rbp+57h+var_90]
0x1800bcdc6  mov     word ptr [rbp+57h+var_AC], ax
0x1800bcdca  mov     rax, [rsi]
0x1800bcdcd  mov     rdi, [rax+30h]
0x1800bcdd1  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bcdd6  mov     rdx, [rbp+57h+var_80]
0x1800bcdda  lea     r8, [rbp+57h+var_90]
0x1800bcdde  mov     rcx, rsi
0x1800bcde1  mov     rax, rdi
0x1800bcde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcde9  mov     [rbp+57h+var_B0], eax
0x1800bcdec  test    eax, eax
0x1800bcdee  mov     eax, 0B3h
0x1800bcdf3  js      loc_1800BCD20
0x1800bcdf9  mov     rcx, [rbp+57h+var_90]
0x1800bcdfd  lea     rdx, [rbp+57h+var_78]
0x1800bce01  mov     word ptr [rbp+57h+var_AC], ax
0x1800bce05  mov     rax, [rcx]
0x1800bce08  mov     rax, [rax+58h]
0x1800bce0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bce11  mov     [rbp+57h+var_B0], eax
0x1800bce14  test    eax, eax
0x1800bce16  mov     eax, 0B6h
0x1800bce1b  js      loc_1800BCD20
0x1800bce21  lea     rdi, [r15+18h]
0x1800bce25  mov     word ptr [rbp+57h+var_AC], ax
0x1800bce29  mov     rcx, rdi
0x1800bce2c  call    ?Free@?$CEcsMemPtr@U_FS_APPLIER_SWAP_PLAN_ENTRY@CCloudFileSystemApplier@@$0A@@@QEAAXXZ; CEcsMemPtr<CCloudFileSystemApplier::_FS_APPLIER_SWAP_PLAN_ENTRY,0>::Free(void)
0x1800bce31  mov     rcx, [rbp+57h+var_78]; string
0x1800bce35  lea     rdx, [rbp+57h+length]; length
0x1800bce39  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bce3f  mov     rcx, rax; unsigned __int16 *
0x1800bce42  mov     rdx, rdi; unsigned __int16 **
0x1800bce45  call    ?StringCopyAlloc@CSyncCoreStringUtils@@SAJPEBGPEAPEAG@Z; CSyncCoreStringUtils::StringCopyAlloc(ushort const *,ushort * *)
0x1800bce4a  mov     [rbp+57h+var_B0], eax
0x1800bce4d  test    eax, eax
0x1800bce4f  mov     eax, 0BBh
0x1800bce54  js      loc_1800BCD20
0x1800bce5a  mov     word ptr [rbp+57h+var_AC], ax
0x1800bce5e  mov     rax, [rdi]
0x1800bce61  mov     [r14], rax
0x1800bce64  xor     ecx, ecx; string
0x1800bce66  call    cs:__imp_WindowsDeleteString
0x1800bce6c  mov     rcx, [rbp+57h+var_80]; string
0x1800bce70  call    cs:__imp_WindowsDeleteString
0x1800bce76  mov     rcx, [rbp+57h+var_78]; string
0x1800bce7a  call    cs:__imp_WindowsDeleteString
0x1800bce80  mov     edi, [rbp+57h+var_B0]
0x1800bce83  test    ebx, ebx
0x1800bce85  js      short loc_1800BCE8D
0x1800bce87  call    cs:__imp_RoUninitialize
0x1800bce8d  lea     rcx, [rbp+57h+var_90]
0x1800bce91  mov     [rbp+57h+string], r12
0x1800bce95  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bce9a  lea     rcx, [rbp+57h+var_70]
0x1800bce9e  call    ?InternalRelease@?$ComPtr@UIProtectionPolicyManagerStatics@EnterpriseData@Security@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Security::EnterpriseData::IProtectionPolicyManagerStatics>::InternalRelease(void)
0x1800bcea3  lea     rcx, [rbp+57h+var_68]
0x1800bcea7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800bceac  lea     rcx, [rbp+57h+var_B0]; this
0x1800bceb0  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800bceb5  mov     eax, edi
0x1800bceb7  mov     rcx, [rbp+57h+var_40]
0x1800bcebb  xor     rcx, rsp; StackCookie
0x1800bcebe  call    __security_check_cookie
0x1800bcec3  add     rsp, 0A0h
0x1800bceca  pop     r15
0x1800bcecc  pop     r14
0x1800bcece  pop     r12
0x1800bced0  pop     rdi
0x1800bced1  pop     rsi
0x1800bced2  pop     rbx
0x1800bced3  pop     rbp
0x1800bced4  retn
```
