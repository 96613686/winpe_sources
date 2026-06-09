# SystemSettings::StorageSenseHandlers::CAppInfo::GetLogoPath(HSTRING__ * *)

- ea: `0x180246180`
- end: `0x1802464c8`
- name: `?GetLogoPath@CAppInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this, HSTRING *newString)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180214498`
- `0x1802144f0`
- `0x180214534`
- `0x180243e6c`
- `0x1802445a4`
- `0x180246180`
- `0x180246fac`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180246257`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180246257`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180246491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180246491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024627e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802463a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802463bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18024627e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802463a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802463bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180246432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180246238`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180246238`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::GetLogoPath(
        SystemSettings::StorageSenseHandlers::CAppInfo *this,
        HSTRING *newString)
{
  HSTRING *v4; // r14
  int PackageFullName; // ebx
  _QWORD *v6; // rax
  const unsigned __int16 *v7; // rdx
  _QWORD *v8; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, HSTRING, __int64 *); // rbx
  unsigned int v11; // eax
  unsigned int i; // esi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, __int64 *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  unsigned int v22; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v23; // [rsp+38h] [rbp-41h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h] BYREF
  __int64 v26; // [rsp+50h] [rbp-29h] BYREF
  __int64 v27; // [rsp+58h] [rbp-21h] BYREF
  __int64 v28; // [rsp+60h] [rbp-19h] BYREF
  __int64 v29; // [rsp+68h] [rbp-11h] BYREF
  __int64 v30; // [rsp+70h] [rbp-9h] BYREF
  __int64 v31; // [rsp+78h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp+Fh] BYREF

  v4 = (HSTRING *)((char *)this + 112);
  if ( *((_QWORD *)this + 14) )
  {
    PackageFullName = 0;
LABEL_24:
    WindowsDuplicateString(*v4, newString);
    return (unsigned int)PackageFullName;
  }
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v25 = 0;
  v27 = 0;
  v26 = 0;
  v23 = 0;
  v6 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[41])newString);
  PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
                      *v6,
                      &v31);
  if ( PackageFullName >= 0 )
  {
    v8 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[45])v7);
    PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
                        *v8,
                        &v30);
    if ( PackageFullName >= 0 )
    {
      if ( WindowsCreateStringReference(
             L"Windows.Internal.StateRepository.ApplicationResourceResolver",
             0x3Cu,
             &hstringHeader,
             &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(
                          string,
                          &v29);
      if ( PackageFullName >= 0 )
      {
        WindowsDeleteString(v23);
        v23 = 0;
        PackageFullName = SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(this, &v23);
        if ( PackageFullName >= 0 )
        {
          v9 = v31;
          v10 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v31 + 368LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
          PackageFullName = v10(v9, 0, v23, &v28);
          if ( PackageFullName >= 0 )
          {
            PackageFullName = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v30 + 304LL))(
                                v30,
                                0,
                                v28,
                                &v26);
            if ( PackageFullName >= 0 )
            {
              v22 = 0;
              if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 56LL))(v26, &v22) >= 0
                && (v11 = v22) != 0 )
              {
                for ( i = 0; i < v11; ++i )
                {
                  v24 = 0;
                  v13 = v26;
                  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 48LL);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
                  PackageFullName = v14(v13, i, &v25);
                  if ( PackageFullName >= 0 )
                  {
                    v15 = v25;
                    v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 232LL);
                    WindowsDeleteString(v24);
                    v24 = 0;
                    PackageFullName = v16(v15, &v24);
                    if ( PackageFullName >= 0 )
                    {
                      WindowsDeleteString(v24);
                      goto LABEL_20;
                    }
                  }
                  WindowsDeleteString(v24);
                  v11 = v22;
                }
                if ( PackageFullName < 0 )
                  goto LABEL_23;
LABEL_20:
                v17 = v29;
                v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v29 + 48LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
                PackageFullName = v18(v17, v25, &v27);
                if ( PackageFullName >= 0 )
                {
                  v19 = v27;
                  v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 96LL);
                  WindowsDeleteString(*v4);
                  *v4 = 0;
                  PackageFullName = v20(v19, v4);
                }
              }
              else
              {
                PackageFullName = -2147418113;
              }
            }
          }
        }
      }
    }
  }
LABEL_23:
  WindowsDeleteString(v23);
  v23 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  if ( PackageFullName >= 0 )
    goto LABEL_24;
  return (unsigned int)PackageFullName;
}

```

## disassembly

```asm
0x180246180  mov     [rsp-8+arg_10], rbx
0x180246185  mov     [rsp-8+arg_18], rsi
0x18024618a  push    rbp
0x18024618b  push    rdi
0x18024618c  push    r12
0x18024618e  push    r14
0x180246190  push    r15
0x180246192  lea     rbp, [rsp-37h]
0x180246197  sub     rsp, 0B0h
0x18024619e  mov     rax, cs:__security_cookie
0x1802461a5  xor     rax, rsp
0x1802461a8  mov     [rbp+57h+var_30], rax
0x1802461ac  mov     r15, rdx
0x1802461af  mov     rdi, rcx
0x1802461b2  lea     r14, [rcx+70h]
0x1802461b6  xor     r12d, r12d
0x1802461b9  cmp     [r14], r12
0x1802461bc  jz      short loc_1802461C6
0x1802461be  mov     ebx, r12d
0x1802461c1  jmp     loc_18024648B
0x1802461c6  mov     [rbp+57h+var_58], r12
0x1802461ca  mov     [rbp+57h+var_60], r12
0x1802461ce  mov     [rbp+57h+var_68], r12
0x1802461d2  mov     [rbp+57h+var_70], r12
0x1802461d6  mov     [rbp+57h+var_88], r12
0x1802461da  mov     [rbp+57h+var_78], r12
0x1802461de  mov     [rbp+57h+var_80], r12
0x1802461e2  mov     [rbp+57h+var_98], r12
0x1802461e6  lea     rcx, [rbp+57h+string]; string
0x1802461ea  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x1802461ef  lea     rdx, [rbp+57h+var_58]
0x1802461f3  mov     rcx, [rax]
0x1802461f6  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1802461fb  mov     ebx, eax
0x1802461fd  test    eax, eax
0x1802461ff  js      loc_18024642E
0x180246205  lea     rcx, [rbp+57h+string]; string
0x180246209  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x18024620e  lea     rdx, [rbp+57h+var_60]
0x180246212  mov     rcx, [rax]
0x180246215  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x18024621a  mov     ebx, eax
0x18024621c  test    eax, eax
0x18024621e  js      loc_18024642E
0x180246224  lea     r9, [rbp+57h+string]; string
0x180246228  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18024622c  mov     edx, 3Ch ; '<'; length
0x180246231  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180246238  call    cs:__imp_WindowsCreateStringReference
0x18024623f  nop     dword ptr [rax+rax+00h]
0x180246244  test    eax, eax
0x180246246  jns     short loc_180246263
0x180246248  xor     r9d, r9d; lpArguments
0x18024624b  xor     r8d, r8d; nNumberOfArguments
0x18024624e  lea     edx, [r9+1]; dwExceptionFlags
0x180246252  mov     ecx, 0C000000Dh; dwExceptionCode
0x180246257  call    cs:__imp_RaiseException
0x18024625e  nop     dword ptr [rax+rax+00h]
0x180246263  lea     rdx, [rbp+57h+var_68]
0x180246267  mov     rcx, [rbp+57h+string]
0x18024626b  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>)
0x180246270  mov     ebx, eax
0x180246272  test    eax, eax
0x180246274  js      loc_18024642E
0x18024627a  mov     rcx, [rbp+57h+var_98]; string
0x18024627e  call    cs:__imp_WindowsDeleteString
0x180246285  nop     dword ptr [rax+rax+00h]
0x18024628a  mov     [rbp+57h+var_98], r12
0x18024628e  lea     rdx, [rbp+57h+var_98]; HSTRING *
0x180246292  mov     rcx, rdi; this
0x180246295  call    ?GetPackageFullName@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(HSTRING__ * *)
0x18024629a  mov     ebx, eax
0x18024629c  test    eax, eax
0x18024629e  js      loc_18024642E
0x1802462a4  mov     rdi, [rbp+57h+var_58]
0x1802462a8  mov     rax, [rdi]
0x1802462ab  mov     rbx, [rax+170h]
0x1802462b2  lea     rcx, [rbp+57h+var_70]
0x1802462b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802462bb  lea     r9, [rbp+57h+var_70]
0x1802462bf  mov     r8, [rbp+57h+var_98]
0x1802462c3  xor     edx, edx
0x1802462c5  mov     rcx, rdi
0x1802462c8  mov     rax, rbx
0x1802462cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802462d0  mov     ebx, eax
0x1802462d2  test    eax, eax
0x1802462d4  js      loc_18024642E
0x1802462da  mov     rcx, [rbp+57h+var_60]
0x1802462de  mov     rax, [rcx]
0x1802462e1  lea     r9, [rbp+57h+var_80]
0x1802462e5  mov     r8, [rbp+57h+var_70]
0x1802462e9  xor     edx, edx
0x1802462eb  mov     rax, [rax+130h]
0x1802462f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802462f7  mov     ebx, eax
0x1802462f9  test    eax, eax
0x1802462fb  js      loc_18024642E
0x180246301  mov     [rbp+57h+var_A0], r12d
0x180246305  mov     rcx, [rbp+57h+var_80]
0x180246309  mov     rax, [rcx]
0x18024630c  lea     rdx, [rbp+57h+var_A0]
0x180246310  mov     rax, [rax+38h]
0x180246314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246319  test    eax, eax
0x18024631b  js      loc_180246429
0x180246321  mov     eax, [rbp+57h+var_A0]
0x180246324  test    eax, eax
0x180246326  jz      loc_180246429
0x18024632c  mov     esi, r12d
0x18024632f  cmp     esi, eax
0x180246331  jnb     loc_1802463C9
0x180246337  mov     [rbp+57h+var_90], r12
0x18024633b  mov     rdi, [rbp+57h+var_80]
0x18024633f  mov     rax, [rdi]
0x180246342  mov     rbx, [rax+30h]
0x180246346  lea     rcx, [rbp+57h+var_88]
0x18024634a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18024634f  lea     r8, [rbp+57h+var_88]
0x180246353  mov     edx, esi
0x180246355  mov     rcx, rdi
0x180246358  mov     rax, rbx
0x18024635b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246360  mov     ebx, eax
0x180246362  test    eax, eax
0x180246364  js      short loc_18024639D
0x180246366  mov     rdi, [rbp+57h+var_88]
0x18024636a  mov     rax, [rdi]
0x18024636d  mov     rbx, [rax+0E8h]
0x180246374  mov     rcx, [rbp+57h+var_90]; string
0x180246378  call    cs:__imp_WindowsDeleteString
0x18024637f  nop     dword ptr [rax+rax+00h]
0x180246384  mov     [rbp+57h+var_90], r12
0x180246388  lea     rdx, [rbp+57h+var_90]
0x18024638c  mov     rcx, rdi
0x18024638f  mov     rax, rbx
0x180246392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246397  mov     ebx, eax
0x180246399  test    eax, eax
0x18024639b  jns     short loc_1802463B7
0x18024639d  mov     rcx, [rbp+57h+var_90]; string
0x1802463a1  call    cs:__imp_WindowsDeleteString
0x1802463a8  nop     dword ptr [rax+rax+00h]
0x1802463ad  inc     esi
0x1802463af  mov     eax, [rbp+57h+var_A0]
0x1802463b2  jmp     loc_18024632F
0x1802463b7  mov     rcx, [rbp+57h+var_90]; string
0x1802463bb  call    cs:__imp_WindowsDeleteString
0x1802463c2  nop     dword ptr [rax+rax+00h]
0x1802463c7  jmp     short loc_1802463CD
0x1802463c9  test    ebx, ebx
0x1802463cb  js      short loc_18024642E
0x1802463cd  mov     rdi, [rbp+57h+var_68]
0x1802463d1  mov     rax, [rdi]
0x1802463d4  mov     rbx, [rax+30h]
0x1802463d8  lea     rcx, [rbp+57h+var_78]
0x1802463dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802463e1  lea     r8, [rbp+57h+var_78]
0x1802463e5  mov     rdx, [rbp+57h+var_88]
0x1802463e9  mov     rcx, rdi
0x1802463ec  mov     rax, rbx
0x1802463ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802463f4  mov     ebx, eax
0x1802463f6  test    eax, eax
0x1802463f8  js      short loc_18024642E
0x1802463fa  mov     rdi, [rbp+57h+var_78]
0x1802463fe  mov     rax, [rdi]
0x180246401  mov     rbx, [rax+60h]
0x180246405  mov     rcx, [r14]; string
0x180246408  call    cs:__imp_WindowsDeleteString
0x18024640f  nop     dword ptr [rax+rax+00h]
0x180246414  mov     [r14], r12
0x180246417  mov     rdx, r14
0x18024641a  mov     rcx, rdi
0x18024641d  mov     rax, rbx
0x180246420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180246425  mov     ebx, eax
0x180246427  jmp     short loc_18024642E
0x180246429  mov     ebx, 8000FFFFh
0x18024642e  mov     rcx, [rbp+57h+var_98]; string
0x180246432  call    cs:__imp_WindowsDeleteString
0x180246439  nop     dword ptr [rax+rax+00h]
0x18024643e  mov     [rbp+57h+var_98], r12
0x180246442  lea     rcx, [rbp+57h+var_80]
0x180246446  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18024644b  nop
0x18024644c  lea     rcx, [rbp+57h+var_78]
0x180246450  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180246455  nop
0x180246456  lea     rcx, [rbp+57h+var_88]
0x18024645a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18024645f  nop
0x180246460  lea     rcx, [rbp+57h+var_70]
0x180246464  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180246469  nop
0x18024646a  lea     rcx, [rbp+57h+var_68]
0x18024646e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180246473  nop
0x180246474  lea     rcx, [rbp+57h+var_60]
0x180246478  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18024647d  nop
0x18024647e  lea     rcx, [rbp+57h+var_58]
0x180246482  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180246487  test    ebx, ebx
0x180246489  js      short loc_18024649D
0x18024648b  mov     rdx, r15; newString
0x18024648e  mov     rcx, [r14]; string
0x180246491  call    cs:__imp_WindowsDuplicateString
0x180246498  nop     dword ptr [rax+rax+00h]
0x18024649d  mov     eax, ebx
0x18024649f  mov     rcx, [rbp+57h+var_30]
0x1802464a3  xor     rcx, rsp; StackCookie
0x1802464a6  call    __security_check_cookie
0x1802464ab  lea     r11, [rsp+0D0h+var_20]
0x1802464b3  mov     rbx, [r11+40h]
0x1802464b7  mov     rsi, [r11+48h]
0x1802464bb  mov     rsp, r11
0x1802464be  pop     r15
0x1802464c0  pop     r14
0x1802464c2  pop     r12
0x1802464c4  pop     rdi
0x1802464c5  pop     rbp
0x1802464c6  retn
```
