# SystemSettings::StorageSenseHandlers::CAppInfo::GetLogoPath(HSTRING__ * *)

- ea: `0x180052e10`
- end: `0x1800530fd`
- name: `?GetLogoPath@CAppInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `749`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this, HSTRING *newString)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18003bae0`
- `0x180047d94`
- `0x180051584`
- `0x1800515d0`
- `0x18005189c`
- `0x1800518d8`
- `0x180052e10`
- `0x18005387c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800530cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800530cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052ee5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052fd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052ff8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053009`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052ee5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052fd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052ff8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053009`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053050`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053074`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::GetLogoPath(
        SystemSettings::StorageSenseHandlers::CAppInfo *this,
        HSTRING *newString)
{
  HSTRING *v4; // r14
  int PackageFullName; // ebx
  __int64 *v6; // rax
  __int64 *v7; // rax
  __int64 *v8; // rax
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
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-39h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h] BYREF
  __int64 v26; // [rsp+50h] [rbp-29h] BYREF
  __int64 v27; // [rsp+58h] [rbp-21h] BYREF
  __int64 v28; // [rsp+60h] [rbp-19h] BYREF
  __int64 v29; // [rsp+68h] [rbp-11h] BYREF
  __int64 v30; // [rsp+70h] [rbp-9h] BYREF
  __int64 v31; // [rsp+78h] [rbp-1h] BYREF
  HSTRING v32[4]; // [rsp+80h] [rbp+7h] BYREF

  v4 = (HSTRING *)((char *)this + 112);
  if ( *((_QWORD *)this + 14) )
  {
    PackageFullName = 0;
LABEL_22:
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
  string = 0;
  v6 = (__int64 *)Windows::Internal::StringReference::StringReference(v32, (const unsigned __int16 (*)[41])newString);
  PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
                      *v6,
                      (__int64)&v31);
  if ( PackageFullName >= 0 )
  {
    v7 = (__int64 *)Windows::Internal::StringReference::StringReference(
                      v32,
                      L"Windows.Internal.StateRepository.Application");
    PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
                        *v7,
                        (__int64)&v30);
    if ( PackageFullName >= 0 )
    {
      v8 = (__int64 *)Windows::Internal::StringReference::StringReference(
                        v32,
                        L"Windows.Internal.StateRepository.ApplicationResourceResolver");
      PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(
                          *v8,
                          (__int64)&v29);
      if ( PackageFullName >= 0 )
      {
        WindowsDeleteString(string);
        string = 0;
        PackageFullName = SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(this, &string);
        if ( PackageFullName >= 0 )
        {
          v9 = v31;
          v10 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v31 + 368LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
          PackageFullName = v10(v9, 0, string, &v28);
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
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
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
                      goto LABEL_18;
                    }
                  }
                  WindowsDeleteString(v24);
                  v11 = v22;
                }
                if ( PackageFullName < 0 )
                  goto LABEL_21;
LABEL_18:
                v17 = v29;
                v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v29 + 48LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
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
LABEL_21:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  if ( PackageFullName >= 0 )
    goto LABEL_22;
  return (unsigned int)PackageFullName;
}

```

## disassembly

```asm
0x180052e10  mov     [rsp-8+arg_10], rbx
0x180052e15  mov     [rsp-8+arg_18], rsi
0x180052e1a  push    rbp
0x180052e1b  push    rdi
0x180052e1c  push    r12
0x180052e1e  push    r14
0x180052e20  push    r15
0x180052e22  lea     rbp, [rsp-37h]
0x180052e27  sub     rsp, 0B0h
0x180052e2e  mov     rax, cs:__security_cookie
0x180052e35  xor     rax, rsp
0x180052e38  mov     [rbp+57h+var_30], rax
0x180052e3c  mov     r15, rdx
0x180052e3f  mov     rdi, rcx
0x180052e42  lea     r14, [rcx+70h]
0x180052e46  xor     r12d, r12d
0x180052e49  cmp     [r14], r12
0x180052e4c  jz      short loc_180052E56
0x180052e4e  mov     ebx, r12d
0x180052e51  jmp     loc_1800530C7
0x180052e56  mov     [rbp+57h+var_58], r12
0x180052e5a  mov     [rbp+57h+var_60], r12
0x180052e5e  mov     [rbp+57h+var_68], r12
0x180052e62  mov     [rbp+57h+var_70], r12
0x180052e66  mov     [rbp+57h+var_88], r12
0x180052e6a  mov     [rbp+57h+var_78], r12
0x180052e6e  mov     [rbp+57h+var_80], r12
0x180052e72  mov     [rbp+57h+string], r12
0x180052e76  lea     rcx, [rbp+57h+var_50]; string
0x180052e7a  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x180052e7f  lea     rdx, [rbp+57h+var_58]
0x180052e83  mov     rcx, [rax]
0x180052e86  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x180052e8b  mov     ebx, eax
0x180052e8d  test    eax, eax
0x180052e8f  js      loc_180053070
0x180052e95  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180052e9c  lea     rcx, [rbp+57h+var_50]; string
0x180052ea0  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x180052ea5  lea     rdx, [rbp+57h+var_60]
0x180052ea9  mov     rcx, [rax]
0x180052eac  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x180052eb1  mov     ebx, eax
0x180052eb3  test    eax, eax
0x180052eb5  js      loc_180053070
0x180052ebb  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180052ec2  lea     rcx, [rbp+57h+var_50]; string
0x180052ec6  call    ??$?0$0DN@@StringReference@Internal@Windows@@QEAA@AEAY0DN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[61])
0x180052ecb  lea     rdx, [rbp+57h+var_68]
0x180052ecf  mov     rcx, [rax]
0x180052ed2  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>)
0x180052ed7  mov     ebx, eax
0x180052ed9  test    eax, eax
0x180052edb  js      loc_180053070
0x180052ee1  mov     rcx, [rbp+57h+string]; string
0x180052ee5  call    cs:__imp_WindowsDeleteString
0x180052eeb  mov     [rbp+57h+string], r12
0x180052eef  lea     rdx, [rbp+57h+string]; HSTRING *
0x180052ef3  mov     rcx, rdi; this
0x180052ef6  call    ?GetPackageFullName@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(HSTRING__ * *)
0x180052efb  mov     ebx, eax
0x180052efd  test    eax, eax
0x180052eff  js      loc_180053070
0x180052f05  mov     rdi, [rbp+57h+var_58]
0x180052f09  mov     rax, [rdi]
0x180052f0c  mov     rbx, [rax+170h]
0x180052f13  lea     rcx, [rbp+57h+var_70]
0x180052f17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052f1c  lea     r9, [rbp+57h+var_70]
0x180052f20  mov     r8, [rbp+57h+string]
0x180052f24  xor     edx, edx
0x180052f26  mov     rcx, rdi
0x180052f29  mov     rax, rbx
0x180052f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f31  mov     ebx, eax
0x180052f33  test    eax, eax
0x180052f35  js      loc_180053070
0x180052f3b  mov     rcx, [rbp+57h+var_60]
0x180052f3f  mov     rax, [rcx]
0x180052f42  lea     r9, [rbp+57h+var_80]
0x180052f46  mov     r8, [rbp+57h+var_70]
0x180052f4a  xor     edx, edx
0x180052f4c  mov     rax, [rax+130h]
0x180052f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f58  mov     ebx, eax
0x180052f5a  test    eax, eax
0x180052f5c  js      loc_180053070
0x180052f62  mov     [rbp+57h+var_A0], r12d
0x180052f66  mov     rcx, [rbp+57h+var_80]
0x180052f6a  mov     rax, [rcx]
0x180052f6d  lea     rdx, [rbp+57h+var_A0]
0x180052f71  mov     rax, [rax+38h]
0x180052f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f7a  test    eax, eax
0x180052f7c  js      loc_18005306B
0x180052f82  mov     eax, [rbp+57h+var_A0]
0x180052f85  test    eax, eax
0x180052f87  jz      loc_18005306B
0x180052f8d  mov     esi, r12d
0x180052f90  cmp     esi, eax
0x180052f92  jnb     short loc_180053011
0x180052f94  mov     [rbp+57h+var_90], r12
0x180052f98  mov     rdi, [rbp+57h+var_80]
0x180052f9c  mov     rax, [rdi]
0x180052f9f  mov     rbx, [rax+30h]
0x180052fa3  lea     rcx, [rbp+57h+var_88]
0x180052fa7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052fac  lea     r8, [rbp+57h+var_88]
0x180052fb0  mov     edx, esi
0x180052fb2  mov     rcx, rdi
0x180052fb5  mov     rax, rbx
0x180052fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fbd  mov     ebx, eax
0x180052fbf  test    eax, eax
0x180052fc1  js      short loc_180052FF4
0x180052fc3  mov     rdi, [rbp+57h+var_88]
0x180052fc7  mov     rax, [rdi]
0x180052fca  mov     rbx, [rax+0E8h]
0x180052fd1  mov     rcx, [rbp+57h+var_90]; string
0x180052fd5  call    cs:__imp_WindowsDeleteString
0x180052fdb  mov     [rbp+57h+var_90], r12
0x180052fdf  lea     rdx, [rbp+57h+var_90]
0x180052fe3  mov     rcx, rdi
0x180052fe6  mov     rax, rbx
0x180052fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fee  mov     ebx, eax
0x180052ff0  test    eax, eax
0x180052ff2  jns     short loc_180053005
0x180052ff4  mov     rcx, [rbp+57h+var_90]; string
0x180052ff8  call    cs:__imp_WindowsDeleteString
0x180052ffe  inc     esi
0x180053000  mov     eax, [rbp+57h+var_A0]
0x180053003  jmp     short loc_180052F90
0x180053005  mov     rcx, [rbp+57h+var_90]; string
0x180053009  call    cs:__imp_WindowsDeleteString
0x18005300f  jmp     short loc_180053015
0x180053011  test    ebx, ebx
0x180053013  js      short loc_180053070
0x180053015  mov     rdi, [rbp+57h+var_68]
0x180053019  mov     rax, [rdi]
0x18005301c  mov     rbx, [rax+30h]
0x180053020  lea     rcx, [rbp+57h+var_78]
0x180053024  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053029  lea     r8, [rbp+57h+var_78]
0x18005302d  mov     rdx, [rbp+57h+var_88]
0x180053031  mov     rcx, rdi
0x180053034  mov     rax, rbx
0x180053037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005303c  mov     ebx, eax
0x18005303e  test    eax, eax
0x180053040  js      short loc_180053070
0x180053042  mov     rdi, [rbp+57h+var_78]
0x180053046  mov     rax, [rdi]
0x180053049  mov     rbx, [rax+60h]
0x18005304d  mov     rcx, [r14]; string
0x180053050  call    cs:__imp_WindowsDeleteString
0x180053056  mov     [r14], r12
0x180053059  mov     rdx, r14
0x18005305c  mov     rcx, rdi
0x18005305f  mov     rax, rbx
0x180053062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053067  mov     ebx, eax
0x180053069  jmp     short loc_180053070
0x18005306b  mov     ebx, 8000FFFFh
0x180053070  mov     rcx, [rbp+57h+string]; string
0x180053074  call    cs:__imp_WindowsDeleteString
0x18005307a  mov     [rbp+57h+string], r12
0x18005307e  lea     rcx, [rbp+57h+var_80]
0x180053082  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053087  nop
0x180053088  lea     rcx, [rbp+57h+var_78]
0x18005308c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053091  nop
0x180053092  lea     rcx, [rbp+57h+var_88]
0x180053096  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005309b  nop
0x18005309c  lea     rcx, [rbp+57h+var_70]
0x1800530a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800530a5  nop
0x1800530a6  lea     rcx, [rbp+57h+var_68]
0x1800530aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800530af  nop
0x1800530b0  lea     rcx, [rbp+57h+var_60]
0x1800530b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800530b9  nop
0x1800530ba  lea     rcx, [rbp+57h+var_58]
0x1800530be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800530c3  test    ebx, ebx
0x1800530c5  js      short loc_1800530D3
0x1800530c7  mov     rdx, r15; newString
0x1800530ca  mov     rcx, [r14]; string
0x1800530cd  call    cs:__imp_WindowsDuplicateString
0x1800530d3  mov     eax, ebx
0x1800530d5  mov     rcx, [rbp+57h+var_30]
0x1800530d9  xor     rcx, rsp; StackCookie
0x1800530dc  call    __security_check_cookie
0x1800530e1  lea     r11, [rsp+0D0h+var_20]
0x1800530e9  mov     rbx, [r11+40h]
0x1800530ed  mov     rsi, [r11+48h]
0x1800530f1  mov     rsp, r11
0x1800530f4  pop     r15
0x1800530f6  pop     r14
0x1800530f8  pop     r12
0x1800530fa  pop     rdi
0x1800530fb  pop     rbp
0x1800530fc  retn
```
