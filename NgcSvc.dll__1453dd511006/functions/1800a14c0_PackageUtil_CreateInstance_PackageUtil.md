# PackageUtil::CreateInstance(PackageUtil * *)

- ea: `0x1800a14c0`
- end: `0x1800a1619`
- name: `?CreateInstance@PackageUtil@@SAJPEAPEAV1@@Z`
- size: `345`
- prototype: `__int64 __fastcall(struct PackageUtil **)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004b854`
- `0x18005504c`
- `0x180099258`

## callees

- `0x18000782c`
- `0x18005cee0`
- `0x18005d60c`
- `0x18009b38c`
- `0x1800a0b64`
- `0x1800a0c04`
- `0x1800a14c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a1541`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a1594`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a1541`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a1594`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a1528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a157b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a1528`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800a157b`

## string_xrefs

- `0x1800a15e2`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`

## pseudocode

```c
__int64 __fastcall PackageUtil::CreateInstance(struct PackageUtil **a1)
{
  struct PackageUtil *v2; // rax
  struct PackageUtil *v3; // rdi
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // eax
  int v10[2]; // [rsp+20h] [rbp-38h] BYREF
  HSTRING string; // [rsp+28h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (struct PackageUtil *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
  {
    v5 = -2147024882;
    *(_QWORD *)v10 = 0;
    v6 = 2147942414LL;
    v7 = 55;
    goto LABEL_12;
  }
  *(_QWORD *)v2 = 0;
  *((_QWORD *)v2 + 1) = 0;
  *(_QWORD *)v10 = v2;
  if ( WindowsCreateStringReference(
         L"Windows.Management.Deployment.Internal.PackageManagerInternal",
         0x3Du,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
         (__int64)string,
         (_QWORD *)v3 + 1);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = (unsigned int)v4;
    v7 = 59;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)v6,
      v10[0]);
    goto LABEL_13;
  }
  if ( WindowsCreateStringReference(L"Windows.Management.Deployment.PackageManager", 0x2Cu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
         (__int64)string,
         v3);
  v5 = v8;
  if ( v8 < 0 )
  {
    v6 = (unsigned int)v8;
    v7 = 63;
    goto LABEL_12;
  }
  *(_QWORD *)v10 = 0;
  v5 = 0;
  *a1 = v3;
LABEL_13:
  wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(v10, 0);
  return v5;
}

```

## disassembly

```asm
0x1800a14c0  mov     [rsp+arg_8], rbx
0x1800a14c5  mov     [rsp+arg_10], rsi
0x1800a14ca  push    rdi
0x1800a14cb  sub     rsp, 50h
0x1800a14cf  mov     rax, cs:__security_cookie
0x1800a14d6  xor     rax, rsp
0x1800a14d9  mov     [rsp+58h+var_10], rax
0x1800a14de  mov     rsi, rcx
0x1800a14e1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a14e8  mov     ecx, 10h; unsigned __int64
0x1800a14ed  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800a14f2  mov     rdi, rax
0x1800a14f5  test    rax, rax
0x1800a14f8  jz      loc_1800A15C7
0x1800a14fe  mov     qword ptr [rax], 0
0x1800a1505  lea     r9, [rsp+58h+string]; string
0x1800a150a  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800a150f  mov     qword ptr [rax+8], 0
0x1800a1517  mov     edx, 3Dh ; '='; length
0x1800a151c  mov     qword ptr [rsp+58h+var_38], rax
0x1800a1521  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x1800a1528  call    cs:__imp_WindowsCreateStringReference
0x1800a152e  test    eax, eax
0x1800a1530  jns     short loc_1800A1547
0x1800a1532  xor     r9d, r9d; lpArguments
0x1800a1535  xor     r8d, r8d; nNumberOfArguments
0x1800a1538  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a153d  lea     edx, [r9+1]; dwExceptionFlags
0x1800a1541  call    cs:__imp_RaiseException
0x1800a1547  mov     rcx, [rsp+58h+string]
0x1800a154c  lea     rdx, [rdi+8]
0x1800a1550  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x1800a1555  mov     ebx, eax
0x1800a1557  test    eax, eax
0x1800a1559  jns     short loc_1800A1565
0x1800a155b  mov     r9d, eax
0x1800a155e  mov     edx, 3Bh ; ';'
0x1800a1563  jmp     short loc_1800A15DD
0x1800a1565  lea     r9, [rsp+58h+string]; string
0x1800a156a  mov     edx, 2Ch ; ','; length
0x1800a156f  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x1800a1574  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1800a157b  call    cs:__imp_WindowsCreateStringReference
0x1800a1581  test    eax, eax
0x1800a1583  jns     short loc_1800A159A
0x1800a1585  xor     r9d, r9d; lpArguments
0x1800a1588  xor     r8d, r8d; nNumberOfArguments
0x1800a158b  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800a1590  lea     edx, [r9+1]; dwExceptionFlags
0x1800a1594  call    cs:__imp_RaiseException
0x1800a159a  mov     rcx, [rsp+58h+string]
0x1800a159f  mov     rdx, rdi
0x1800a15a2  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x1800a15a7  mov     ebx, eax
0x1800a15a9  test    eax, eax
0x1800a15ab  jns     short loc_1800A15B7
0x1800a15ad  mov     r9d, eax
0x1800a15b0  mov     edx, 3Fh ; '?'
0x1800a15b5  jmp     short loc_1800A15DD
0x1800a15b7  mov     qword ptr [rsp+58h+var_38], 0
0x1800a15c0  xor     ebx, ebx
0x1800a15c2  mov     [rsi], rdi
0x1800a15c5  jmp     short loc_1800A15EE
0x1800a15c7  mov     ebx, 8007000Eh
0x1800a15cc  mov     qword ptr [rsp+58h+var_38], 0; int
0x1800a15d5  mov     r9d, ebx; char *
0x1800a15d8  mov     edx, 37h ; '7'; void *
0x1800a15dd  mov     rcx, [rsp+58h]; this
0x1800a15e2  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a15e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a15ee  xor     edx, edx
0x1800a15f0  lea     rcx, [rsp+58h+var_38]
0x1800a15f5  call    ?reset@?$unique_ptr@VPackageUtil@@U?$default_delete@VPackageUtil@@@wistd@@@wistd@@QEAAXPEAVPackageUtil@@@Z; wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(PackageUtil *)
0x1800a15fa  mov     eax, ebx
0x1800a15fc  mov     rcx, [rsp+58h+var_10]
0x1800a1601  xor     rcx, rsp; StackCookie
0x1800a1604  call    __security_check_cookie
0x1800a1609  mov     rbx, [rsp+58h+arg_8]
0x1800a160e  mov     rsi, [rsp+58h+arg_10]
0x1800a1613  add     rsp, 50h
0x1800a1617  pop     rdi
0x1800a1618  retn
```
