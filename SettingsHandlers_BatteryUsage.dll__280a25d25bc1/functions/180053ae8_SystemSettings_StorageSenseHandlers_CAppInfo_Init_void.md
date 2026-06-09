# SystemSettings::StorageSenseHandlers::CAppInfo::Init(void)

- ea: `0x180053ae8`
- end: `0x180053e7e`
- name: `?Init@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJXZ`
- size: `918`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppInfo *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180052354`
- `0x1800523d8`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18000a13c`
- `0x18003bae0`
- `0x180047d94`
- `0x180051584`
- `0x1800515d0`
- `0x18005189c`
- `0x1800518d8`
- `0x18005387c`
- `0x180053ae8`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053d4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053e0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053b92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053cdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053d01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053d4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053d9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053dc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180053e0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::Init(
        SystemSettings::StorageSenseHandlers::CAppInfo *this,
        const unsigned __int16 *a2)
{
  _DWORD *v3; // rsi
  _DWORD *v4; // r12
  __int64 *v5; // rax
  int PackageFullName; // r14d
  __int64 *v7; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, HSTRING, __int64 *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 *v12; // rax
  unsigned int v13; // eax
  unsigned int i; // esi
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, _QWORD, __int64 *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, __int64 *); // rbx
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, char *); // rdi
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, char *); // rdi
  int v25; // eax
  int v27; // [rsp+20h] [rbp-79h]
  unsigned int v28; // [rsp+30h] [rbp-69h] BYREF
  __int64 v29; // [rsp+38h] [rbp-61h] BYREF
  HSTRING string; // [rsp+40h] [rbp-59h] BYREF
  HSTRING v31; // [rsp+48h] [rbp-51h] BYREF
  __int64 v32; // [rsp+50h] [rbp-49h] BYREF
  __int64 v33; // [rsp+58h] [rbp-41h] BYREF
  __int64 v34; // [rsp+60h] [rbp-39h] BYREF
  __int64 v35; // [rsp+68h] [rbp-31h] BYREF
  __int64 v36; // [rsp+70h] [rbp-29h] BYREF
  __int64 v37; // [rsp+78h] [rbp-21h] BYREF
  HSTRING v38[4]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v3 = (_DWORD *)((char *)this + 128);
  *((_DWORD *)this + 32) = 0;
  v4 = (_DWORD *)((char *)this + 124);
  *((_DWORD *)this + 31) = 0;
  v37 = 0;
  v36 = 0;
  v35 = 0;
  v33 = 0;
  v29 = 0;
  v32 = 0;
  v34 = 0;
  string = 0;
  v5 = (__int64 *)Windows::Internal::StringReference::StringReference(v38, (const unsigned __int16 (*)[41])a2);
  PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
                      *v5,
                      (__int64)&v37);
  if ( PackageFullName < 0 )
    goto LABEL_28;
  v7 = (__int64 *)Windows::Internal::StringReference::StringReference(
                    v38,
                    L"Windows.Internal.StateRepository.Application");
  PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
                      *v7,
                      (__int64)&v36);
  if ( PackageFullName < 0 )
    goto LABEL_28;
  WindowsDeleteString(string);
  string = 0;
  PackageFullName = SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(this, &string);
  if ( PackageFullName < 0 )
    goto LABEL_28;
  v8 = v37;
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v37 + 368LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  v10 = v9(v8, 0, string, &v33);
  PackageFullName = v10;
  if ( v10 != -2147023728 )
  {
    if ( v10 >= 0 )
    {
      PackageFullName = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v36 + 304LL))(
                          v36,
                          0,
                          v33,
                          &v34);
      if ( PackageFullName >= 0 )
      {
        if ( (*(int (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v33 + 128LL))(v33, v3) < 0 )
          *v3 = 0;
        v12 = (__int64 *)Windows::Internal::StringReference::StringReference(
                           v38,
                           L"Windows.Internal.StateRepository.ApplicationResourceResolver");
        PackageFullName = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(
                            *v12,
                            (__int64)&v35);
        if ( PackageFullName >= 0 )
        {
          v28 = 0;
          if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v34 + 56LL))(v34, &v28) >= 0
            && (v13 = v28) != 0 )
          {
            for ( i = 0; i < v13; ++i )
            {
              v31 = 0;
              v15 = v34;
              v16 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 48LL);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
              PackageFullName = v16(v15, i, &v29);
              if ( PackageFullName >= 0 )
              {
                v17 = v29;
                v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 232LL);
                WindowsDeleteString(v31);
                v31 = 0;
                PackageFullName = v18(v17, &v31);
                if ( PackageFullName >= 0 )
                {
                  if ( (*(int (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v29 + 88LL))(v29, v4) < 0 )
                    *v4 = 0;
                  if ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v29 + 344LL))(v29, (char *)this + 120) < 0 )
                    *((_DWORD *)this + 30) = 0;
                  WindowsDeleteString(v31);
                  goto LABEL_24;
                }
              }
              WindowsDeleteString(v31);
              v13 = v28;
            }
            if ( PackageFullName < 0 )
              goto LABEL_28;
LABEL_24:
            v19 = v35;
            v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v35 + 48LL);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
            PackageFullName = v20(v19, v29, &v32);
            if ( PackageFullName >= 0 )
            {
              v21 = v32;
              v22 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v32 + 96LL);
              WindowsDeleteString(*((HSTRING *)this + 14));
              *((_QWORD *)this + 14) = 0;
              PackageFullName = v22(v21, (char *)this + 112);
              v23 = v32;
              v24 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v32 + 48LL);
              WindowsDeleteString(*((HSTRING *)this + 12));
              *((_QWORD *)this + 12) = 0;
              v25 = v24(v23, (char *)this + 96);
              v11 = v25;
              if ( v25 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD7,
                  (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\legacyapplisthelperlib\\lib\\applisthelper.cpp",
                  (const char *)(unsigned int)v25,
                  v27);
                goto LABEL_29;
              }
            }
          }
          else
          {
            PackageFullName = -2147418113;
          }
        }
      }
    }
LABEL_28:
    v11 = PackageFullName;
    goto LABEL_29;
  }
  v11 = 0;
LABEL_29:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
  return v11;
}

```

## disassembly

```asm
0x180053ae8  push    rbp
0x180053aea  push    rbx
0x180053aeb  push    rsi
0x180053aec  push    rdi
0x180053aed  push    r12
0x180053aef  push    r13
0x180053af1  push    r14
0x180053af3  push    r15
0x180053af5  lea     rbp, [rsp-1Fh]
0x180053afa  sub     rsp, 0B8h
0x180053b01  mov     rax, cs:__security_cookie
0x180053b08  xor     rax, rsp
0x180053b0b  mov     [rbp+57h+var_50], rax
0x180053b0f  mov     r15, rcx
0x180053b12  lea     rsi, [rcx+80h]
0x180053b19  xor     r13d, r13d
0x180053b1c  mov     [rsi], r13d
0x180053b1f  lea     r12, [rcx+7Ch]
0x180053b23  mov     [r12], r13d
0x180053b27  mov     [rbp+57h+var_78], r13
0x180053b2b  mov     [rbp+57h+var_80], r13
0x180053b2f  mov     [rbp+57h+var_88], r13
0x180053b33  mov     [rbp+57h+var_98], r13
0x180053b37  mov     [rbp+57h+var_B8], r13
0x180053b3b  mov     [rbp+57h+var_A0], r13
0x180053b3f  mov     [rbp+57h+var_90], r13
0x180053b43  mov     [rbp+57h+string], r13
0x180053b47  lea     rcx, [rbp+57h+var_70]; string
0x180053b4b  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x180053b50  lea     rdx, [rbp+57h+var_78]
0x180053b54  mov     rcx, [rax]
0x180053b57  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x180053b5c  mov     r14d, eax
0x180053b5f  test    eax, eax
0x180053b61  js      loc_180053E06
0x180053b67  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180053b6e  lea     rcx, [rbp+57h+var_70]; string
0x180053b72  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x180053b77  lea     rdx, [rbp+57h+var_80]
0x180053b7b  mov     rcx, [rax]
0x180053b7e  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x180053b83  mov     r14d, eax
0x180053b86  test    eax, eax
0x180053b88  js      loc_180053E06
0x180053b8e  mov     rcx, [rbp+57h+string]; string
0x180053b92  call    cs:__imp_WindowsDeleteString
0x180053b98  mov     [rbp+57h+string], r13
0x180053b9c  lea     rdx, [rbp+57h+string]; HSTRING *
0x180053ba0  mov     rcx, r15; this
0x180053ba3  call    ?GetPackageFullName@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppInfo::GetPackageFullName(HSTRING__ * *)
0x180053ba8  mov     r14d, eax
0x180053bab  test    eax, eax
0x180053bad  js      loc_180053E06
0x180053bb3  mov     rdi, [rbp+57h+var_78]
0x180053bb7  mov     rax, [rdi]
0x180053bba  mov     rbx, [rax+170h]
0x180053bc1  lea     rcx, [rbp+57h+var_98]
0x180053bc5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053bca  lea     r9, [rbp+57h+var_98]
0x180053bce  mov     r8, [rbp+57h+string]
0x180053bd2  xor     edx, edx
0x180053bd4  mov     rcx, rdi
0x180053bd7  mov     rax, rbx
0x180053bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bdf  mov     r14d, eax
0x180053be2  cmp     eax, 80070490h
0x180053be7  jnz     short loc_180053BF1
0x180053be9  mov     ebx, r13d
0x180053bec  jmp     loc_180053E09
0x180053bf1  test    eax, eax
0x180053bf3  js      loc_180053E06
0x180053bf9  mov     rcx, [rbp+57h+var_80]
0x180053bfd  mov     rax, [rcx]
0x180053c00  lea     r9, [rbp+57h+var_90]
0x180053c04  mov     r8, [rbp+57h+var_98]
0x180053c08  xor     edx, edx
0x180053c0a  mov     rax, [rax+130h]
0x180053c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c16  mov     r14d, eax
0x180053c19  test    eax, eax
0x180053c1b  js      loc_180053E06
0x180053c21  mov     rcx, [rbp+57h+var_98]
0x180053c25  mov     rax, [rcx]
0x180053c28  mov     rdx, rsi
0x180053c2b  mov     rax, [rax+80h]
0x180053c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c37  test    eax, eax
0x180053c39  jns     short loc_180053C3E
0x180053c3b  mov     [rsi], r13d
0x180053c3e  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180053c45  lea     rcx, [rbp+57h+var_70]; string
0x180053c49  call    ??$?0$0DN@@StringReference@Internal@Windows@@QEAA@AEAY0DN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[61])
0x180053c4e  lea     rdx, [rbp+57h+var_88]
0x180053c52  mov     rcx, [rax]
0x180053c55  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationResourceResolverStatics>>)
0x180053c5a  mov     r14d, eax
0x180053c5d  test    eax, eax
0x180053c5f  js      loc_180053E06
0x180053c65  mov     [rbp+57h+var_C0], r13d
0x180053c69  mov     rcx, [rbp+57h+var_90]
0x180053c6d  mov     rax, [rcx]
0x180053c70  lea     rdx, [rbp+57h+var_C0]
0x180053c74  mov     rax, [rax+38h]
0x180053c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c7d  test    eax, eax
0x180053c7f  js      loc_180053E00
0x180053c85  mov     eax, [rbp+57h+var_C0]
0x180053c88  test    eax, eax
0x180053c8a  jz      loc_180053E00
0x180053c90  mov     esi, r13d
0x180053c93  cmp     esi, eax
0x180053c95  jnb     loc_180053D54
0x180053c9b  mov     [rbp+57h+var_A8], r13
0x180053c9f  mov     rdi, [rbp+57h+var_90]
0x180053ca3  mov     rax, [rdi]
0x180053ca6  mov     rbx, [rax+30h]
0x180053caa  lea     rcx, [rbp+57h+var_B8]
0x180053cae  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053cb3  lea     r8, [rbp+57h+var_B8]
0x180053cb7  mov     edx, esi
0x180053cb9  mov     rcx, rdi
0x180053cbc  mov     rax, rbx
0x180053cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cc4  mov     r14d, eax
0x180053cc7  test    eax, eax
0x180053cc9  js      short loc_180053CFD
0x180053ccb  mov     rdi, [rbp+57h+var_B8]
0x180053ccf  mov     rax, [rdi]
0x180053cd2  mov     rbx, [rax+0E8h]
0x180053cd9  mov     rcx, [rbp+57h+var_A8]; string
0x180053cdd  call    cs:__imp_WindowsDeleteString
0x180053ce3  mov     [rbp+57h+var_A8], r13
0x180053ce7  lea     rdx, [rbp+57h+var_A8]
0x180053ceb  mov     rcx, rdi
0x180053cee  mov     rax, rbx
0x180053cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053cf6  mov     r14d, eax
0x180053cf9  test    eax, eax
0x180053cfb  jns     short loc_180053D0E
0x180053cfd  mov     rcx, [rbp+57h+var_A8]; string
0x180053d01  call    cs:__imp_WindowsDeleteString
0x180053d07  inc     esi
0x180053d09  mov     eax, [rbp+57h+var_C0]
0x180053d0c  jmp     short loc_180053C93
0x180053d0e  mov     rcx, [rbp+57h+var_B8]
0x180053d12  mov     rax, [rcx]
0x180053d15  mov     rdx, r12
0x180053d18  mov     rax, [rax+58h]
0x180053d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d21  test    eax, eax
0x180053d23  jns     short loc_180053D29
0x180053d25  mov     [r12], r13d
0x180053d29  mov     rcx, [rbp+57h+var_B8]
0x180053d2d  mov     rax, [rcx]
0x180053d30  lea     rdx, [r15+78h]
0x180053d34  mov     rax, [rax+158h]
0x180053d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d40  test    eax, eax
0x180053d42  jns     short loc_180053D48
0x180053d44  mov     [r15+78h], r13d
0x180053d48  mov     rcx, [rbp+57h+var_A8]; string
0x180053d4c  call    cs:__imp_WindowsDeleteString
0x180053d52  jmp     short loc_180053D5D
0x180053d54  test    r14d, r14d
0x180053d57  js      loc_180053E06
0x180053d5d  mov     rdi, [rbp+57h+var_88]
0x180053d61  mov     rax, [rdi]
0x180053d64  mov     rbx, [rax+30h]
0x180053d68  lea     rcx, [rbp+57h+var_A0]
0x180053d6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053d71  lea     r8, [rbp+57h+var_A0]
0x180053d75  mov     rdx, [rbp+57h+var_B8]
0x180053d79  mov     rcx, rdi
0x180053d7c  mov     rax, rbx
0x180053d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d84  mov     r14d, eax
0x180053d87  test    eax, eax
0x180053d89  js      short loc_180053E06
0x180053d8b  mov     rsi, [rbp+57h+var_A0]
0x180053d8f  mov     rax, [rsi]
0x180053d92  mov     rdi, [rax+60h]
0x180053d96  lea     rbx, [r15+70h]
0x180053d9a  mov     rcx, [rbx]; string
0x180053d9d  call    cs:__imp_WindowsDeleteString
0x180053da3  mov     [rbx], r13
0x180053da6  mov     rdx, rbx
0x180053da9  mov     rcx, rsi
0x180053dac  mov     rax, rdi
0x180053daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053db4  mov     r14d, eax
0x180053db7  mov     rsi, [rbp+57h+var_A0]
0x180053dbb  mov     rax, [rsi]
0x180053dbe  mov     rdi, [rax+30h]
0x180053dc2  lea     rbx, [r15+60h]
0x180053dc6  mov     rcx, [rbx]; string
0x180053dc9  call    cs:__imp_WindowsDeleteString
0x180053dcf  mov     [rbx], r13
0x180053dd2  mov     rdx, rbx
0x180053dd5  mov     rcx, rsi
0x180053dd8  mov     rax, rdi
0x180053ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053de0  mov     ebx, eax
0x180053de2  test    eax, eax
0x180053de4  jns     short loc_180053E06
0x180053de6  mov     rcx, [rbp+5Fh]; this
0x180053dea  mov     r9d, eax; char *
0x180053ded  lea     r8, aOnecoreuapShel_20; "onecoreuap\\shell\\coresettinghandlers"...
0x180053df4  mov     edx, 0D7h; void *
0x180053df9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053dfe  jmp     short loc_180053E09
0x180053e00  mov     r14d, 8000FFFFh
0x180053e06  mov     ebx, r14d
0x180053e09  mov     rcx, [rbp+57h+string]; string
0x180053e0d  call    cs:__imp_WindowsDeleteString
0x180053e13  mov     [rbp+57h+string], r13
0x180053e17  lea     rcx, [rbp+57h+var_90]
0x180053e1b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053e20  nop
0x180053e21  lea     rcx, [rbp+57h+var_A0]
0x180053e25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053e2a  nop
0x180053e2b  lea     rcx, [rbp+57h+var_B8]
0x180053e2f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053e34  nop
0x180053e35  lea     rcx, [rbp+57h+var_98]
0x180053e39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053e3e  nop
0x180053e3f  lea     rcx, [rbp+57h+var_88]
0x180053e43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053e48  nop
0x180053e49  lea     rcx, [rbp+57h+var_80]
0x180053e4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053e52  nop
0x180053e53  lea     rcx, [rbp+57h+var_78]
0x180053e57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180053e5c  mov     eax, ebx
0x180053e5e  mov     rcx, [rbp+57h+var_50]
0x180053e62  xor     rcx, rsp; StackCookie
0x180053e65  call    __security_check_cookie
0x180053e6a  add     rsp, 0B8h
0x180053e71  pop     r15
0x180053e73  pop     r14
0x180053e75  pop     r13
0x180053e77  pop     r12
0x180053e79  pop     rdi
0x180053e7a  pop     rsi
0x180053e7b  pop     rbx
0x180053e7c  pop     rbp
0x180053e7d  retn
```
