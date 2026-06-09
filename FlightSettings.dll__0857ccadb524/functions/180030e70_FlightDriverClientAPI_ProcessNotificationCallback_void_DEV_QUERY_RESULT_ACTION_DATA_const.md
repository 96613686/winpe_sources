# FlightDriverClientAPI::ProcessNotificationCallback(void *,_DEV_QUERY_RESULT_ACTION_DATA const *)

- ea: `0x180030e70`
- end: `0x180031320`
- name: `?ProcessNotificationCallback@FlightDriverClientAPI@@CAJPEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z`
- size: `1200`
- prototype: `__int64 __fastcall(void *, const struct _DEV_QUERY_RESULT_ACTION_DATA *)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180030430`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x1800133d0`
- `0x18001c6f4`
- `0x1800254ac`
- `0x18002f918`
- `0x18002f9f4`
- `0x18003029c`
- `0x1800304a4`
- `0x180030e70`
- `0x1800314e0`
- `0x180031a08`
- `0x180031bd8`
- `0x1800320cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800310d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003127e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800312ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800310d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003127e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800312ee`

## string_xrefs

- `0x180030e9b`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x180030eff`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x180030fbb`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x180031039`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x1800310fc`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x18003116d`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x180031219`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x18003122c`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x1800312a0`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall FlightDriverClientAPI::ProcessNotificationCallback(
        _DWORD *a1,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a2)
{
  __int64 v3; // rdx
  unsigned int v4; // ebx
  int v5; // eax
  char *v6; // rcx
  unsigned __int64 i; // rdi
  char *v8; // rcx
  unsigned __int64 j; // rbx
  int v10; // eax
  unsigned int v11; // edi
  char *v12; // rcx
  unsigned __int64 mm; // rbx
  int v14; // eax
  unsigned __int64 kk; // rbx
  unsigned __int64 k; // rbx
  int v17; // eax
  unsigned __int64 jj; // rbx
  int v19; // eax
  unsigned __int64 ii; // rbx
  unsigned __int8 *v21; // rbx
  __int64 v22; // rdx
  const unsigned __int16 *FlightingRegistryPath; // rax
  unsigned __int64 n; // rdi
  int updated; // eax
  unsigned __int64 m; // rbx
  unsigned int v28; // [rsp+20h] [rbp-29h]
  unsigned int v29; // [rsp+20h] [rbp-29h]
  unsigned __int16 *v30; // [rsp+30h] [rbp-19h] BYREF
  __int64 v31; // [rsp+38h] [rbp-11h]
  __int64 v32; // [rsp+40h] [rbp-9h]
  LPVOID pv; // [rsp+48h] [rbp-1h] BYREF
  unsigned __int64 v34; // [rsp+50h] [rbp+7h]
  __int64 v35; // [rsp+58h] [rbp+Fh]
  __int64 v36; // [rsp+60h] [rbp+17h]
  _QWORD v37[7]; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  int v39; // [rsp+B0h] [rbp+67h] BYREF
  unsigned __int8 *v40; // [rsp+C0h] [rbp+77h] BYREF
  unsigned __int64 v41; // [rsp+C8h] [rbp+7Fh] BYREF

  if ( a1 )
  {
    if ( !a2 )
    {
      v3 = 143;
      goto LABEL_3;
    }
    memset(v37, 0, 32);
    pv = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v5 = FlightDriverClientAPI::EvaluateDevQueryAction(a2, a1, v37, &pv);
    v4 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
        (const char *)(unsigned int)v5,
        v28);
      v6 = (char *)pv;
      if ( pv )
      {
        for ( i = 0; i < v34; v6 = (char *)pv )
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v6[8 * i++]);
LABEL_49:
        CoTaskMemFree(v6);
        pv = 0;
        goto LABEL_57;
      }
      goto LABEL_57;
    }
    if ( !a1[4] )
    {
      v8 = (char *)pv;
      if ( pv )
      {
        for ( j = 0; j < v34; v8 = (char *)pv )
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8[8 * j++]);
LABEL_30:
        CoTaskMemFree(v8);
        pv = 0;
        goto LABEL_31;
      }
      goto LABEL_31;
    }
    v30 = 0;
    v31 = 0;
    v32 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
    v31 = -1;
    v32 = -1;
    v10 = FlightDriverClientAPI::NormalizeFlightDriverIds(v37, &v30);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v40 = 0;
      v41 = 0;
      v39 = 0;
      v14 = FlightDriverClientAPI::ProceedBasedOnHash(v30, &v40, &v41, &v39);
      v11 = v14;
      if ( v14 >= 0 )
      {
        if ( !v39 )
        {
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v40);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
          v8 = (char *)pv;
          if ( pv )
          {
            for ( k = 0; k < v34; v8 = (char *)pv )
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8[8 * k++]);
            goto LABEL_30;
          }
LABEL_31:
          v4 = 0;
          goto LABEL_57;
        }
        v17 = FlightDriverClientAPI::EvaluateFlightIds(v37);
        v11 = v17;
        if ( v17 >= 0 )
        {
          v19 = FlightDriverClientAPI::SaveFlightIdsInRegistry(v30);
          v11 = v19;
          if ( v19 >= 0 )
          {
            v21 = v40;
            if ( v40 )
            {
              FlightingRegistryPath = GetFlightingRegistryPath(0xBu);
              v4 = RegWow64Helpers::SetBinary(HKEY_LOCAL_MACHINE, FlightingRegistryPath, L"FlightIdsHash", v21, v41);
              if ( (v4 & 0x80000000) == 0 )
              {
                updated = FlightDriverClientAPI::UpdateDrvpkgidFlightIdsMapping(&pv);
                v11 = updated;
                if ( updated < 0 )
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xAA,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
                    (const char *)(unsigned int)updated,
                    v28);
                CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v40);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
                v12 = (char *)pv;
                if ( !pv )
                  goto LABEL_56;
                for ( m = 0; m < v34; v12 = (char *)pv )
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12[8 * m++]);
                goto LABEL_55;
              }
              v22 = 824;
            }
            else
            {
              v4 = -2147024809;
              v22 = 817;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v22,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
              (const char *)v4,
              v28);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA8,
              (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
              (const char *)v4,
              v29);
            CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v40);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
            v6 = (char *)pv;
            if ( pv )
            {
              for ( n = 0; n < v34; v6 = (char *)pv )
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v6[8 * n++]);
              goto LABEL_49;
            }
LABEL_57:
            v34 = 0;
            v36 = 0;
            CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::RemoveAll(v37);
            return v4;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA6,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
            (const char *)(unsigned int)v19,
            v28);
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v40);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
          v12 = (char *)pv;
          if ( pv )
          {
            for ( ii = 0; ii < v34; v12 = (char *)pv )
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12[8 * ii++]);
            goto LABEL_55;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA4,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
            (const char *)(unsigned int)v17,
            v28);
          CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v40);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
          v12 = (char *)pv;
          if ( pv )
          {
            for ( jj = 0; jj < v34; v12 = (char *)pv )
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12[8 * jj++]);
            goto LABEL_55;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
          (const char *)(unsigned int)v14,
          v28);
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v40);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
        v12 = (char *)pv;
        if ( pv )
        {
          for ( kk = 0; kk < v34; v12 = (char *)pv )
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12[8 * kk++]);
          goto LABEL_55;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
        (const char *)(unsigned int)v10,
        v28);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v30);
      v12 = (char *)pv;
      if ( pv )
      {
        for ( mm = 0; mm < v34; v12 = (char *)pv )
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v12[8 * mm++]);
LABEL_55:
        CoTaskMemFree(v12);
        pv = 0;
      }
    }
LABEL_56:
    v4 = v11;
    goto LABEL_57;
  }
  v3 = 142;
LABEL_3:
  v4 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
    (const char *)0x80070057LL,
    v28);
  return v4;
}

```

## disassembly

```asm
0x180030e70  mov     [rsp-8+arg_8], rbx
0x180030e75  push    rbp
0x180030e76  push    rsi
0x180030e77  push    rdi
0x180030e78  lea     rbp, [rsp-47h]
0x180030e7d  sub     rsp, 90h
0x180030e84  mov     rax, rdx
0x180030e87  mov     rdi, rcx
0x180030e8a  xor     esi, esi
0x180030e8c  test    rcx, rcx
0x180030e8f  jnz     short loc_180030EB3
0x180030e91  mov     edx, 8Eh; void *
0x180030e96  mov     ebx, 80070057h
0x180030e9b  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180030ea2  mov     r9d, ebx; char *
0x180030ea5  mov     rcx, [rbp+5Fh]; this
0x180030ea9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030eae  jmp     loc_18003130B
0x180030eb3  test    rax, rax
0x180030eb6  jnz     short loc_180030EBF
0x180030eb8  mov     edx, 8Fh
0x180030ebd  jmp     short loc_180030E96
0x180030ebf  mov     [rbp+57h+var_38], rsi
0x180030ec3  mov     [rbp+57h+var_30], rsi
0x180030ec7  mov     [rbp+57h+var_28], rsi
0x180030ecb  mov     [rbp+57h+var_20], rsi
0x180030ecf  mov     [rbp+57h+pv], rsi
0x180030ed3  mov     [rbp+57h+var_50], rsi
0x180030ed7  mov     [rbp+57h+var_48], rsi
0x180030edb  mov     [rbp+57h+var_40], rsi
0x180030edf  lea     r9, [rbp+57h+pv]
0x180030ee3  lea     r8, [rbp+57h+var_38]
0x180030ee7  mov     rdx, rdi
0x180030eea  mov     rcx, rax
0x180030eed  call    ?EvaluateDevQueryAction@FlightDriverClientAPI@@CAJPEBU_DEV_QUERY_RESULT_ACTION_DATA@@PEAVFlightDriverNotificationContext@@PEAV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@PEAV?$CCoSimpleArray@V?$ComPtr@VFlightDriverPkgIdMapping@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VFlightDriverPkgIdMapping@@@WRL@Microsoft@@@@@@@Z; FlightDriverClientAPI::EvaluateDevQueryAction(_DEV_QUERY_RESULT_ACTION_DATA const *,FlightDriverNotificationContext *,CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> *,CCoSimpleArray<Microsoft::WRL::ComPtr<FlightDriverPkgIdMapping>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<FlightDriverPkgIdMapping>>> *)
0x180030ef2  mov     ebx, eax
0x180030ef4  test    eax, eax
0x180030ef6  jns     short loc_180030F46
0x180030ef8  mov     rcx, [rbp+5Fh]; this
0x180030efc  mov     r9d, eax; char *
0x180030eff  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180030f06  mov     edx, 95h; void *
0x180030f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030f10  nop
0x180030f11  mov     rcx, [rbp+57h+pv]
0x180030f15  test    rcx, rcx
0x180030f18  jz      loc_1800312FA
0x180030f1e  mov     rdi, rsi
0x180030f21  cmp     [rbp+57h+var_50], rsi
0x180030f25  jbe     loc_18003127E
0x180030f2b  lea     rcx, [rcx+rdi*8]
0x180030f2f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180030f34  inc     rdi
0x180030f37  mov     rcx, [rbp+57h+pv]
0x180030f3b  cmp     rdi, [rbp+57h+var_50]
0x180030f3f  jb      short loc_180030F2B
0x180030f41  jmp     loc_18003127E
0x180030f46  cmp     [rdi+10h], esi
0x180030f49  jnz     short loc_180030F80
0x180030f4b  mov     rcx, [rbp+57h+pv]
0x180030f4f  test    rcx, rcx
0x180030f52  jz      loc_1800310DF
0x180030f58  mov     rbx, rsi
0x180030f5b  cmp     [rbp+57h+var_50], rsi
0x180030f5f  jbe     loc_1800310D5
0x180030f65  lea     rcx, [rcx+rbx*8]
0x180030f69  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180030f6e  inc     rbx
0x180030f71  mov     rcx, [rbp+57h+pv]
0x180030f75  cmp     rbx, [rbp+57h+var_50]
0x180030f79  jb      short loc_180030F65
0x180030f7b  jmp     loc_1800310D5
0x180030f80  mov     [rbp+57h+var_70], rsi
0x180030f84  mov     [rbp+57h+var_68], rsi
0x180030f88  mov     [rbp+57h+var_60], rsi
0x180030f8c  lea     rcx, [rbp+57h+var_70]
0x180030f90  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030f95  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030f99  mov     [rbp+57h+var_68], rax
0x180030f9d  mov     [rbp+57h+var_60], rax
0x180030fa1  lea     rdx, [rbp+57h+var_70]
0x180030fa5  lea     rcx, [rbp+57h+var_38]
0x180030fa9  call    ?NormalizeFlightDriverIds@FlightDriverClientAPI@@CAJQEAV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@PEAPEAG@Z; FlightDriverClientAPI::NormalizeFlightDriverIds(CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> * const,ushort * *)
0x180030fae  mov     edi, eax
0x180030fb0  test    eax, eax
0x180030fb2  jns     short loc_18003100C
0x180030fb4  mov     rcx, [rbp+5Fh]; this
0x180030fb8  mov     r9d, eax; char *
0x180030fbb  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180030fc2  mov     edx, 9Ah; void *
0x180030fc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030fcc  nop
0x180030fcd  lea     rcx, [rbp+57h+var_70]
0x180030fd1  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030fd6  nop
0x180030fd7  mov     rcx, [rbp+57h+pv]
0x180030fdb  test    rcx, rcx
0x180030fde  jz      loc_1800312F8
0x180030fe4  mov     rbx, rsi
0x180030fe7  cmp     [rbp+57h+var_50], rsi
0x180030feb  jbe     loc_1800312EE
0x180030ff1  lea     rcx, [rcx+rbx*8]
0x180030ff5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180030ffa  inc     rbx
0x180030ffd  mov     rcx, [rbp+57h+pv]
0x180031001  cmp     rbx, [rbp+57h+var_50]
0x180031005  jb      short loc_180030FF1
0x180031007  jmp     loc_1800312EE
0x18003100c  mov     [rbp+57h+arg_10], rsi
0x180031010  mov     [rbp+57h+arg_18], rsi
0x180031014  mov     [rbp+57h+arg_0], esi
0x180031017  lea     r9, [rbp+57h+arg_0]; int *
0x18003101b  lea     r8, [rbp+57h+arg_18]; unsigned __int64 *
0x18003101f  lea     rdx, [rbp+57h+arg_10]; unsigned __int8 **
0x180031023  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x180031027  call    ?ProceedBasedOnHash@FlightDriverClientAPI@@CAJPEBGPEAPEAEPEA_KPEAH@Z; FlightDriverClientAPI::ProceedBasedOnHash(ushort const *,uchar * *,unsigned __int64 *,int *)
0x18003102c  mov     edi, eax
0x18003102e  test    eax, eax
0x180031030  jns     short loc_180031094
0x180031032  mov     rcx, [rbp+5Fh]; this
0x180031036  mov     r9d, eax; char *
0x180031039  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031040  mov     edx, 0A0h; void *
0x180031045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003104a  nop
0x18003104b  lea     rcx, [rbp+57h+arg_10]
0x18003104f  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180031054  nop
0x180031055  lea     rcx, [rbp+57h+var_70]
0x180031059  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003105e  nop
0x18003105f  mov     rcx, [rbp+57h+pv]
0x180031063  test    rcx, rcx
0x180031066  jz      loc_1800312F8
0x18003106c  mov     rbx, rsi
0x18003106f  cmp     [rbp+57h+var_50], rsi
0x180031073  jbe     loc_1800312EE
0x180031079  lea     rcx, [rcx+rbx*8]
0x18003107d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031082  inc     rbx
0x180031085  mov     rcx, [rbp+57h+pv]
0x180031089  cmp     rbx, [rbp+57h+var_50]
0x18003108d  jb      short loc_180031079
0x18003108f  jmp     loc_1800312EE
0x180031094  cmp     [rbp+57h+arg_0], esi
0x180031097  jnz     short loc_1800310E6
0x180031099  lea     rcx, [rbp+57h+arg_10]
0x18003109d  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800310a2  nop
0x1800310a3  lea     rcx, [rbp+57h+var_70]
0x1800310a7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800310ac  nop
0x1800310ad  mov     rcx, [rbp+57h+pv]
0x1800310b1  test    rcx, rcx
0x1800310b4  jz      short loc_1800310DF
0x1800310b6  mov     rbx, rsi
0x1800310b9  cmp     [rbp+57h+var_50], rsi
0x1800310bd  jbe     short loc_1800310D5
0x1800310bf  lea     rcx, [rcx+rbx*8]
0x1800310c3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800310c8  inc     rbx
0x1800310cb  mov     rcx, [rbp+57h+pv]; pv
0x1800310cf  cmp     rbx, [rbp+57h+var_50]
0x1800310d3  jb      short loc_1800310BF
0x1800310d5  call    cs:__imp_CoTaskMemFree
0x1800310db  mov     [rbp+57h+pv], rsi
0x1800310df  mov     ebx, esi
0x1800310e1  jmp     loc_1800312FA
0x1800310e6  lea     rcx, [rbp+57h+var_38]
0x1800310ea  call    ?EvaluateFlightIds@FlightDriverClientAPI@@CAJQEAV?$CCoSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@@Z; FlightDriverClientAPI::EvaluateFlightIds(CCoSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>> * const)
0x1800310ef  mov     edi, eax
0x1800310f1  test    eax, eax
0x1800310f3  jns     short loc_180031157
0x1800310f5  mov     rcx, [rbp+5Fh]; this
0x1800310f9  mov     r9d, eax; char *
0x1800310fc  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031103  mov     edx, 0A4h; void *
0x180031108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003110d  nop
0x18003110e  lea     rcx, [rbp+57h+arg_10]
0x180031112  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180031117  nop
0x180031118  lea     rcx, [rbp+57h+var_70]
0x18003111c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031121  nop
0x180031122  mov     rcx, [rbp+57h+pv]
0x180031126  test    rcx, rcx
0x180031129  jz      loc_1800312F8
0x18003112f  mov     rbx, rsi
0x180031132  cmp     [rbp+57h+var_50], rsi
0x180031136  jbe     loc_1800312EE
0x18003113c  lea     rcx, [rcx+rbx*8]
0x180031140  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031145  inc     rbx
0x180031148  mov     rcx, [rbp+57h+pv]
0x18003114c  cmp     rbx, [rbp+57h+var_50]
0x180031150  jb      short loc_18003113C
0x180031152  jmp     loc_1800312EE
0x180031157  mov     rcx, [rbp+57h+var_70]; unsigned __int16 *
0x18003115b  call    ?SaveFlightIdsInRegistry@FlightDriverClientAPI@@CAJPEBG@Z; FlightDriverClientAPI::SaveFlightIdsInRegistry(ushort const *)
0x180031160  mov     edi, eax
0x180031162  test    eax, eax
0x180031164  jns     short loc_1800311C8
0x180031166  mov     rcx, [rbp+5Fh]; this
0x18003116a  mov     r9d, eax; char *
0x18003116d  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031174  mov     edx, 0A6h; void *
0x180031179  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003117e  nop
0x18003117f  lea     rcx, [rbp+57h+arg_10]
0x180031183  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180031188  nop
0x180031189  lea     rcx, [rbp+57h+var_70]
0x18003118d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031192  nop
0x180031193  mov     rcx, [rbp+57h+pv]
0x180031197  test    rcx, rcx
0x18003119a  jz      loc_1800312F8
0x1800311a0  mov     rbx, rsi
0x1800311a3  cmp     [rbp+57h+var_50], rsi
0x1800311a7  jbe     loc_1800312EE
0x1800311ad  lea     rcx, [rcx+rbx*8]
0x1800311b1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800311b6  inc     rbx
0x1800311b9  mov     rcx, [rbp+57h+pv]
0x1800311bd  cmp     rbx, [rbp+57h+var_50]
0x1800311c1  jb      short loc_1800311AD
0x1800311c3  jmp     loc_1800312EE
0x1800311c8  mov     rbx, [rbp+57h+arg_10]
0x1800311cc  test    rbx, rbx
0x1800311cf  jnz     short loc_1800311DD
0x1800311d1  mov     ebx, 80070057h
0x1800311d6  mov     edx, 331h
0x1800311db  jmp     short loc_180031212
0x1800311dd  mov     ecx, 0Bh
0x1800311e2  call    ?GetFlightingRegistryPath@@YAPEBGW4FlightingRegistryKey@@@Z; GetFlightingRegistryPath(FlightingRegistryKey)
0x1800311e7  mov     rdx, rax; unsigned __int16 *
0x1800311ea  mov     eax, dword ptr [rbp+57h+arg_18]
0x1800311ed  mov     [rsp+0A0h+var_80], eax; int
0x1800311f1  mov     r9, rbx; void *
0x1800311f4  lea     r8, aFlightidshash; "FlightIdsHash"
0x1800311fb  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180031202  call    ?SetBinary@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG1QEBXK@Z; RegWow64Helpers::SetBinary(HKEY__ * const,ushort const * const,ushort const * const,void const * const,ulong)
0x180031207  mov     ebx, eax
0x180031209  test    eax, eax
0x18003120b  jns     short loc_18003128A
0x18003120d  mov     edx, 338h; void *
0x180031212  mov     r9d, ebx; char *
0x180031215  mov     rcx, [rbp+5Fh]; this
0x180031219  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031220  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031225  mov     rcx, [rbp+5Fh]; this
0x180031229  mov     r9d, ebx; char *
0x18003122c  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031233  mov     edx, 0A8h; void *
0x180031238  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003123d  nop
0x18003123e  lea     rcx, [rbp+57h+arg_10]
0x180031242  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180031247  nop
0x180031248  lea     rcx, [rbp+57h+var_70]
0x18003124c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031251  nop
0x180031252  mov     rcx, [rbp+57h+pv]
0x180031256  test    rcx, rcx
0x180031259  jz      loc_1800312FA
0x18003125f  mov     rdi, rsi
0x180031262  cmp     [rbp+57h+var_50], rsi
0x180031266  jbe     short loc_18003127E
0x180031268  lea     rcx, [rcx+rdi*8]
0x18003126c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031271  inc     rdi
0x180031274  mov     rcx, [rbp+57h+pv]; pv
0x180031278  cmp     rdi, [rbp+57h+var_50]
0x18003127c  jb      short loc_180031268
0x18003127e  call    cs:__imp_CoTaskMemFree
0x180031284  mov     [rbp+57h+pv], rsi
0x180031288  jmp     short loc_1800312FA
0x18003128a  lea     rcx, [rbp+57h+pv]
0x18003128e  call    ?UpdateDrvpkgidFlightIdsMapping@FlightDriverClientAPI@@CAJPEAV?$CCoSimpleArray@V?$ComPtr@VFlightDriverPkgIdMapping@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VFlightDriverPkgIdMapping@@@WRL@Microsoft@@@@@@@Z; FlightDriverClientAPI::UpdateDrvpkgidFlightIdsMapping(CCoSimpleArray<Microsoft::WRL::ComPtr<FlightDriverPkgIdMapping>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<FlightDriverPkgIdMapping>>> *)
0x180031293  mov     edi, eax
0x180031295  test    eax, eax
0x180031297  jns     short loc_1800312B2
0x180031299  mov     rcx, [rbp+5Fh]; this
0x18003129d  mov     r9d, eax; char *
0x1800312a0  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x1800312a7  mov     edx, 0AAh; void *
0x1800312ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800312b1  nop
0x1800312b2  lea     rcx, [rbp+57h+arg_10]
0x1800312b6  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800312bb  nop
0x1800312bc  lea     rcx, [rbp+57h+var_70]
0x1800312c0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800312c5  nop
0x1800312c6  mov     rcx, [rbp+57h+pv]
0x1800312ca  test    rcx, rcx
0x1800312cd  jz      short loc_1800312F8
0x1800312cf  mov     rbx, rsi
0x1800312d2  cmp     [rbp+57h+var_50], rsi
  ... truncated ...
```
