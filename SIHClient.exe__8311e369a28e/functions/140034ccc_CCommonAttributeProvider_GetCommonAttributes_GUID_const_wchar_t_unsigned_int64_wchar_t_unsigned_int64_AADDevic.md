# CCommonAttributeProvider::GetCommonAttributes(_GUID const &,wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,AADDeviceDataBoundaryInfo *)

- ea: `0x140034ccc`
- end: `0x140035488`
- name: `?GetCommonAttributes@CCommonAttributeProvider@@QEAAJAEBU_GUID@@PEA_W_KPEAPEA_WPEA_KPEAVAADDeviceDataBoundaryInfo@@@Z`
- size: `1980`
- prototype: `__int64 __fastcall(struct _OSVERSIONINFOW **this, GUID *rguid, wchar_t *, __int64, wchar_t **, unsigned __int64 *, struct AADDeviceDataBoundaryInfo *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140032b84`

## callees

- `0x140007780`
- `0x14000d7e4`
- `0x140011e3c`
- `0x1400154b4`
- `0x140033160`
- `0x140034ccc`
- `0x140035490`
- `0x1400356ac`
- `0x14003585c`
- `0x140035ce4`
- `0x140035e3c`
- `0x140035f64`
- `0x14003612c`
- `0x1400364ac`
- `0x14003689c`
- `0x140036c54`
- `0x14003e34c`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140034d9d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140034d9d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140034f98`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x140034f98`

## string_xrefs

- `0x1400353a4`: `CCommonAttributeProvider::GetCommonAttributes`
- `0x14003542f`: `C:\__w\1\s\src\Client\Engine\lib\SLS\CommonAttributeProvider.cpp`
- `0x140034ddb`: `CCommonAttributeProvider::AppendServiceID`
- `0x14003547c`: `CCommonAttributeProvider::AppendOSVersion`
- `0x140034f13`: `CCommonAttributeProvider::AppendArchitecture`

## pseudocode

```c
__int64 __fastcall CCommonAttributeProvider::GetCommonAttributes(
        struct _OSVERSIONINFOW **this,
        GUID *rguid,
        wchar_t *a3,
        __int64 a4,
        wchar_t **a5,
        unsigned __int64 *a6,
        struct AADDeviceDataBoundaryInfo *a7)
{
  unsigned __int64 v7; // rsi
  wchar_t *v8; // rdi
  int ProcessorArchitecture; // ebx
  __int64 v12; // rdx
  const char *v13; // rcx
  unsigned __int64 v14; // r9
  const wchar_t *v15; // r8
  CCommonAttributeProvider *v16; // rcx
  CCommonAttributeProvider *v17; // rcx
  CCommonAttributeProvider *v18; // rcx
  CCommonAttributeProvider *v19; // rcx
  CCommonAttributeProvider *v20; // rcx
  CCommonAttributeProvider *v21; // rcx
  unsigned __int64 *v22; // rax
  int appended; // eax
  wchar_t **v25; // [rsp+20h] [rbp-C1h]
  wchar_t **v26; // [rsp+20h] [rbp-C1h]
  unsigned __int64 *v27; // [rsp+28h] [rbp-B9h]
  unsigned int v28; // [rsp+30h] [rbp-B1h]
  unsigned int v29; // [rsp+30h] [rbp-B1h]
  unsigned int v30; // [rsp+30h] [rbp-B1h]
  unsigned int v31; // [rsp+30h] [rbp-B1h]
  unsigned int v32; // [rsp+30h] [rbp-B1h]
  unsigned int v33; // [rsp+30h] [rbp-B1h]
  unsigned int v34; // [rsp+30h] [rbp-B1h]
  unsigned int v35; // [rsp+30h] [rbp-B1h]
  unsigned int v36; // [rsp+30h] [rbp-B1h]
  unsigned int v37; // [rsp+30h] [rbp-B1h]
  unsigned int v38; // [rsp+30h] [rbp-B1h]
  unsigned int v39; // [rsp+30h] [rbp-B1h]
  unsigned int v40; // [rsp+30h] [rbp-B1h]
  unsigned int v41; // [rsp+30h] [rbp-B1h]
  unsigned int v42; // [rsp+30h] [rbp-B1h]
  wchar_t *v43; // [rsp+40h] [rbp-A1h] BYREF
  wchar_t *v44; // [rsp+48h] [rbp-99h] BYREF
  unsigned __int64 *v45; // [rsp+50h] [rbp-91h]
  wchar_t *v46[2]; // [rsp+60h] [rbp-81h] BYREF
  unsigned __int64 v47; // [rsp+70h] [rbp-71h] BYREF
  unsigned __int16 v48[4]; // [rsp+78h] [rbp-69h] BYREF
  OLECHAR sz[48]; // [rsp+80h] [rbp-61h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v7 = 2085;
  v8 = a3;
  v45 = a6;
  v47 = 2085;
  v46[0] = a3;
  if ( a3 && a5 && a6 )
  {
    ProcessorArchitecture = StringCchCatNExW(a3, 0x825u, L"/SLS/", 6u, v46, &v47, v28);
    if ( ProcessorArchitecture < 0 )
      goto LABEL_49;
    v7 = v47;
    v8 = v46[0];
    v44 = (wchar_t *)v47;
    v43 = v46[0];
    memset(sz, 0, 0x4Eu);
    if ( StringFromGUID2(rguid, sz, 39) > 0 )
    {
      ProcessorArchitecture = StringCchCatNExW(v8, v7, sz, 0x27u, &v43, (unsigned __int64 *)&v44, v29);
      if ( ProcessorArchitecture < 0 )
      {
        v12 = 231;
        v13 = "CCommonAttributeProvider::AppendServiceID";
LABEL_9:
        LODWORD(v26) = ProcessorArchitecture;
        WUTrace(v13, v12, 4, 1, v26, L"Method failed");
        goto LABEL_50;
      }
    }
    ProcessorArchitecture = StringCchCatNExW(v8, v7, L"/", 1u, v46, &v47, v29);
    if ( ProcessorArchitecture < 0 )
      goto LABEL_49;
    v7 = v47;
    v8 = v46[0];
    v43 = (wchar_t *)v47;
    v44 = v46[0];
    v48[0] = 0;
    ProcessorArchitecture = GetProcessorArchitecture(v48);
    if ( ProcessorArchitecture < 0 )
      goto LABEL_24;
    switch ( v48[0] )
    {
      case 0u:
        ProcessorArchitecture = StringCchCatNExW(v8, v7, L"x86", 3u, &v44, (unsigned __int64 *)&v43, v30);
        if ( ProcessorArchitecture >= 0 )
          goto LABEL_25;
        goto LABEL_24;
      case 5u:
        v15 = L"arm";
        break;
      case 9u:
        v15 = L"x64";
        break;
      case 0xCu:
        v14 = 5;
        v15 = L"arm64";
LABEL_21:
        ProcessorArchitecture = StringCchCatNExW(v8, v7, v15, v14, &v44, (unsigned __int64 *)&v43, v30);
        if ( ProcessorArchitecture >= 0 )
        {
LABEL_26:
          ProcessorArchitecture = StringCchCatNExW(v8, v7, L"/", 1u, v46, &v47, v30);
          if ( ProcessorArchitecture >= 0 )
          {
            v7 = v47;
            v8 = v46[0];
            v44 = (wchar_t *)v47;
            v43 = v46[0];
            memset(sz, 0, 0x58u);
            *(_QWORD *)v48 = 0;
            RtlGetDeviceFamilyInfoEnum(v48, 0, 0);
            v31 = v48[0];
            LODWORD(v27) = v48[1];
            LODWORD(v25) = v48[2];
            ProcessorArchitecture = StringCchPrintfW(sz, 0x2Cu, L"%u.%u.%u.%u", v48[3], v25, v27);
            if ( ProcessorArchitecture < 0
              || (ProcessorArchitecture = StringCchCatNExW(v8, v7, sz, 0x2Cu, &v43, (unsigned __int64 *)&v44, v31),
                  ProcessorArchitecture < 0) )
            {
              v12 = 266;
              v13 = "CCommonAttributeProvider::AppendOSVersion";
              goto LABEL_9;
            }
            ProcessorArchitecture = StringCchCatNExW(v8, v7, L"/", 1u, v46, &v47, v32);
            if ( ProcessorArchitecture >= 0 )
            {
              ProcessorArchitecture = CCommonAttributeProvider::AppendServicePack(this, v46[0], v47, v46, &v47);
              if ( ProcessorArchitecture >= 0 )
              {
                ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"?", 1u, v46, &v47, v33);
                if ( ProcessorArchitecture >= 0 )
                {
                  ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"CH=", 4u, v46, &v47, v34);
                  if ( ProcessorArchitecture >= 0 )
                  {
                    ProcessorArchitecture = CCommonAttributeProvider::AppendClientHash(v16, v46[0], v47, v46, &v47);
                    if ( ProcessorArchitecture >= 0 )
                    {
                      ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"&", 1u, v46, &v47, v35);
                      if ( ProcessorArchitecture >= 0 )
                      {
                        ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"L=", 3u, v46, &v47, v36);
                        if ( ProcessorArchitecture >= 0 )
                        {
                          ProcessorArchitecture = CCommonAttributeProvider::AppendLanguages(v17, v46[0], v47, v46, &v47);
                          if ( ProcessorArchitecture >= 0 )
                          {
                            ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"&", 1u, v46, &v47, v37);
                            if ( ProcessorArchitecture >= 0 )
                            {
                              ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"P=", 3u, v46, &v47, v38);
                              if ( ProcessorArchitecture >= 0 )
                              {
                                ProcessorArchitecture = CCommonAttributeProvider::AppendPrograms(
                                                          v18,
                                                          v46[0],
                                                          v47,
                                                          v46,
                                                          &v47);
                                if ( ProcessorArchitecture >= 0 )
                                {
                                  ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"&", 1u, v46, &v47, v39);
                                  if ( ProcessorArchitecture >= 0 )
                                  {
                                    ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"PT=", 4u, v46, &v47, v40);
                                    if ( ProcessorArchitecture >= 0 )
                                    {
                                      ProcessorArchitecture = CCommonAttributeProvider::AppendProductType(
                                                                v19,
                                                                v46[0],
                                                                v47,
                                                                v46,
                                                                &v47);
                                      if ( ProcessorArchitecture >= 0 )
                                      {
                                        ProcessorArchitecture = StringCchCatNExW(v46[0], v47, L"&", 1u, v46, &v47, v41);
                                        if ( ProcessorArchitecture >= 0 )
                                        {
                                          ProcessorArchitecture = StringCchCatNExW(
                                                                    v46[0],
                                                                    v47,
                                                                    L"WUA=",
                                                                    5u,
                                                                    v46,
                                                                    &v47,
                                                                    v42);
                                          if ( ProcessorArchitecture >= 0 )
                                          {
                                            ProcessorArchitecture = CCommonAttributeProvider::AppendWindowsUpdateAgentVersion(
                                                                      v20,
                                                                      v46[0],
                                                                      v47,
                                                                      v46,
                                                                      &v47);
                                            if ( ProcessorArchitecture >= 0 )
                                            {
                                              if ( a7 && *(_BYTE *)a7 )
                                              {
                                                ProcessorArchitecture = CCommonAttributeProvider::AppendDataBoundary(
                                                                          (CCommonAttributeProvider *)v46[0],
                                                                          *((const wchar_t **)a7 + 1),
                                                                          *((wchar_t **)a7 + 2),
                                                                          *((const wchar_t **)a7 + 3),
                                                                          v46[0],
                                                                          v47,
                                                                          v46,
                                                                          &v47);
                                                if ( ProcessorArchitecture < 0 )
                                                  goto LABEL_49;
                                              }
                                              else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_QMRForAutopatchManaged_56753991>::GetImpl'::`2'::impl) )
                                              {
                                                if ( QMRUtil::GetInQMR(v21) )
                                                {
                                                  appended = CCommonAttributeProvider::AppendQMRCachedDataBoundary(
                                                               v21,
                                                               v46[0],
                                                               v47,
                                                               v46,
                                                               &v47);
                                                  if ( appended < 0 )
                                                    wil::details::in1diag3::_Log_Hr(
                                                      retaddr,
                                                      (void *)0xBB,
                                                      (int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\SLS\\CommonAttributeProvider.cpp",
                                                      (const char *)(unsigned int)appended);
                                                }
                                              }
                                              ProcessorArchitecture = CCommonAttributeProvider::AppendDeviceTarget(
                                                                        v21,
                                                                        v46[0],
                                                                        v47,
                                                                        v46,
                                                                        &v47);
                                              v8 = v46[0];
                                              v7 = v47;
                                              if ( ProcessorArchitecture >= 0 )
                                                goto LABEL_51;
                                              goto LABEL_50;
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
LABEL_49:
          v8 = v46[0];
          v7 = v47;
          goto LABEL_50;
        }
        goto LABEL_24;
      default:
        ProcessorArchitecture = -2145124297;
LABEL_24:
        LODWORD(v25) = ProcessorArchitecture;
        WUTrace("CCommonAttributeProvider::AppendArchitecture", 314, 4, 1, v25, L"Method failed");
LABEL_25:
        if ( ProcessorArchitecture < 0 )
          goto LABEL_50;
        goto LABEL_26;
    }
    v14 = 3;
    goto LABEL_21;
  }
  ProcessorArchitecture = -2147467261;
LABEL_50:
  LODWORD(v25) = ProcessorArchitecture;
  WUTrace("CCommonAttributeProvider::GetCommonAttributes", 198, 4, 1, v25, L"Method failed");
LABEL_51:
  v22 = v45;
  *a5 = v8;
  *v22 = v7;
  return (unsigned int)ProcessorArchitecture;
}

```

## disassembly

```asm
0x140034ccc  mov     [rsp-8+arg_18], rbx
0x140034cd1  push    rbp
0x140034cd2  push    rsi
0x140034cd3  push    rdi
0x140034cd4  push    r12
0x140034cd6  push    r13
0x140034cd8  push    r14
0x140034cda  push    r15
0x140034cdc  lea     rbp, [rsp-0Fh]
0x140034ce1  sub     rsp, 0F0h
0x140034ce8  mov     rax, cs:__security_cookie
0x140034cef  xor     rax, rsp
0x140034cf2  mov     [rbp+3Fh+var_40], rax
0x140034cf6  mov     rax, [rbp+3Fh+arg_28]
0x140034cfa  mov     esi, 825h
0x140034cff  mov     r13, [rbp+3Fh+arg_20]
0x140034d03  mov     rdi, r8
0x140034d06  mov     r14, [rbp+3Fh+arg_30]
0x140034d0a  mov     r15, rdx
0x140034d0d  mov     [rsp+120h+var_D0], rax
0x140034d12  mov     r12, rcx
0x140034d15  mov     [rbp+3Fh+var_B0], rsi
0x140034d19  mov     [rsp+120h+var_C0], r8
0x140034d1e  test    r8, r8
0x140034d21  jnz     short loc_140034D2D
0x140034d23  mov     ebx, 80004003h
0x140034d28  jmp     loc_140035392
0x140034d2d  test    r13, r13
0x140034d30  jz      short loc_140034D23
0x140034d32  test    rax, rax
0x140034d35  jz      short loc_140034D23
0x140034d37  lea     rax, [rbp+3Fh+var_B0]
0x140034d3b  mov     r9d, 6; unsigned __int64
0x140034d41  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x140034d46  lea     r8, aSls_0; "/SLS/"
0x140034d4d  lea     rax, [rsp+120h+var_C0]
0x140034d52  mov     rdx, rsi; unsigned __int64
0x140034d55  mov     rcx, rdi; wchar_t *
0x140034d58  mov     [rsp+120h+var_100], rax; wchar_t **
0x140034d5d  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140034d62  mov     ebx, eax
0x140034d64  test    eax, eax
0x140034d66  js      loc_140035389
0x140034d6c  mov     rsi, [rbp+3Fh+var_B0]
0x140034d70  lea     rcx, [rbp+3Fh+sz]; void *
0x140034d74  mov     rdi, [rsp+120h+var_C0]
0x140034d79  xor     edx, edx; Val
0x140034d7b  mov     [rsp+120h+var_D8], rsi
0x140034d80  mov     [rsp+120h+var_E0], rdi
0x140034d85  lea     r8d, [rdx+4Eh]; Size
0x140034d89  call    memset
0x140034d8e  mov     ebx, 27h ; '''
0x140034d93  lea     rdx, [rbp+3Fh+sz]; lpsz
0x140034d97  mov     r8d, ebx; cchMax
0x140034d9a  mov     rcx, r15; rguid
0x140034d9d  call    cs:__imp_StringFromGUID2
0x140034da3  xor     r15d, r15d
0x140034da6  test    eax, eax
0x140034da8  jle     short loc_140034E06
0x140034daa  lea     rax, [rsp+120h+var_D8]
0x140034daf  mov     r9d, ebx; unsigned __int64
0x140034db2  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x140034db7  lea     r8, [rbp+3Fh+sz]; wchar_t *
0x140034dbb  lea     rax, [rsp+120h+var_E0]
0x140034dc0  mov     rdx, rsi; unsigned __int64
0x140034dc3  mov     rcx, rdi; wchar_t *
0x140034dc6  mov     [rsp+120h+var_100], rax; wchar_t **
0x140034dcb  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140034dd0  mov     ebx, eax
0x140034dd2  test    eax, eax
0x140034dd4  jns     short loc_140034E06
0x140034dd6  mov     edx, 0E7h
0x140034ddb  lea     rcx, aCcommonattribu_3; "CCommonAttributeProvider::AppendService"...
0x140034de2  mov     r8d, 4
0x140034de8  lea     rax, aMethodFailed; "Method failed"
0x140034def  mov     [rsp+120h+var_F8], rax
0x140034df4  mov     dword ptr [rsp+120h+var_100], ebx
0x140034df8  lea     r9d, [r8-3]
0x140034dfc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140034e01  jmp     loc_140035392
0x140034e06  lea     rax, [rbp+3Fh+var_B0]
0x140034e0a  mov     r9d, 1; unsigned __int64
0x140034e10  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x140034e15  lea     r8, asc_14006C8A8; "/"
0x140034e1c  lea     rax, [rsp+120h+var_C0]
0x140034e21  mov     rdx, rsi; unsigned __int64
0x140034e24  mov     rcx, rdi; wchar_t *
0x140034e27  mov     [rsp+120h+var_100], rax; wchar_t **
0x140034e2c  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140034e31  mov     ebx, eax
0x140034e33  test    eax, eax
0x140034e35  js      loc_140035389
0x140034e3b  mov     rsi, [rbp+3Fh+var_B0]
0x140034e3f  lea     rcx, [rbp+3Fh+var_A8]; unsigned __int16 *
0x140034e43  mov     rdi, [rsp+120h+var_C0]
0x140034e48  mov     [rsp+120h+var_E0], rsi
0x140034e4d  mov     [rsp+120h+var_D8], rdi
0x140034e52  mov     [rbp+3Fh+var_A8], r15w
0x140034e57  call    ?GetProcessorArchitecture@@YAJPEAG@Z; GetProcessorArchitecture(ushort *)
0x140034e5c  mov     ebx, eax
0x140034e5e  mov     ecx, 3
0x140034e63  test    eax, eax
0x140034e65  js      loc_140034F01
0x140034e6b  movzx   eax, [rbp+3Fh+var_A8]
0x140034e6f  test    eax, eax
0x140034e71  jz      short loc_140034ED2
0x140034e73  cmp     eax, 5
0x140034e76  jz      short loc_140034EA1
0x140034e78  cmp     eax, 9
0x140034e7b  jz      short loc_140034E98
0x140034e7d  cmp     eax, 0Ch
0x140034e80  jz      short loc_140034E89
0x140034e82  mov     ebx, 80240037h
0x140034e87  jmp     short loc_140034F01
0x140034e89  mov     r9d, 5
0x140034e8f  lea     r8, aArm64; "arm64"
0x140034e96  jmp     short loc_140034EAB
0x140034e98  lea     r8, aX64; "x64"
0x140034e9f  jmp     short loc_140034EA8
0x140034ea1  lea     r8, aArm; "arm"
0x140034ea8  mov     r9, rcx; unsigned __int64
0x140034eab  lea     rax, [rsp+120h+var_E0]
0x140034eb0  mov     rdx, rsi; unsigned __int64
0x140034eb3  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x140034eb8  mov     rcx, rdi; wchar_t *
0x140034ebb  lea     rax, [rsp+120h+var_D8]
0x140034ec0  mov     [rsp+120h+var_100], rax; wchar_t **
0x140034ec5  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140034eca  mov     ebx, eax
0x140034ecc  test    eax, eax
0x140034ece  js      short loc_140034F01
0x140034ed0  jmp     short loc_140034F34
0x140034ed2  lea     rax, [rsp+120h+var_E0]
0x140034ed7  mov     r9, rcx; unsigned __int64
0x140034eda  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x140034edf  lea     r8, aX86_0; "x86"
0x140034ee6  lea     rax, [rsp+120h+var_D8]
0x140034eeb  mov     rdx, rsi; unsigned __int64
0x140034eee  mov     rcx, rdi; wchar_t *
0x140034ef1  mov     [rsp+120h+var_100], rax; wchar_t **
0x140034ef6  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140034efb  mov     ebx, eax
0x140034efd  test    eax, eax
0x140034eff  jns     short loc_140034F2C
0x140034f01  mov     r9d, 1
0x140034f07  lea     rax, aMethodFailed; "Method failed"
0x140034f0e  mov     [rsp+120h+var_F8], rax
0x140034f13  lea     rcx, aCcommonattribu_8; "CCommonAttributeProvider::AppendArchite"...
0x140034f1a  mov     edx, 13Ah
0x140034f1f  mov     dword ptr [rsp+120h+var_100], ebx
0x140034f23  lea     r8d, [r9+3]
0x140034f27  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140034f2c  test    ebx, ebx
0x140034f2e  js      loc_140035392
0x140034f34  lea     rax, [rbp+3Fh+var_B0]
0x140034f38  mov     r9d, 1; unsigned __int64
0x140034f3e  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x140034f43  lea     r8, asc_14006C8A8; "/"
0x140034f4a  lea     rax, [rsp+120h+var_C0]
0x140034f4f  mov     rdx, rsi; unsigned __int64
0x140034f52  mov     rcx, rdi; wchar_t *
0x140034f55  mov     [rsp+120h+var_100], rax; wchar_t **
0x140034f5a  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140034f5f  mov     ebx, eax
0x140034f61  test    eax, eax
0x140034f63  js      loc_140035389
0x140034f69  mov     rsi, [rbp+3Fh+var_B0]
0x140034f6d  lea     rcx, [rbp+3Fh+sz]; void *
0x140034f71  mov     rdi, [rsp+120h+var_C0]
0x140034f76  xor     edx, edx; Val
0x140034f78  mov     [rsp+120h+var_D8], rsi
0x140034f7d  mov     [rsp+120h+var_E0], rdi
0x140034f82  lea     r8d, [rdx+58h]; Size
0x140034f86  call    memset
0x140034f8b  xor     r8d, r8d
0x140034f8e  mov     qword ptr [rbp+3Fh+var_A8], r15
0x140034f92  xor     edx, edx
0x140034f94  lea     rcx, [rbp+3Fh+var_A8]
0x140034f98  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x140034f9e  movzx   ecx, [rbp+3Fh+var_A8+2]
0x140034fa2  lea     r8, aUUUU; "%u.%u.%u.%u"
0x140034fa9  movzx   edx, [rbp+3Fh+var_A8+4]
0x140034fad  movzx   eax, [rbp+3Fh+var_A8]
0x140034fb1  movzx   r9d, [rbp+3Fh+var_A8+6]
0x140034fb6  mov     dword ptr [rsp+120h+var_F0], eax; unsigned int
0x140034fba  mov     dword ptr [rsp+120h+var_F8], ecx
0x140034fbe  lea     rcx, [rbp+3Fh+sz]; Buffer
0x140034fc2  mov     dword ptr [rsp+120h+var_100], edx
0x140034fc6  mov     edx, 2Ch ; ','; unsigned __int64
0x140034fcb  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140034fd0  mov     ebx, eax
0x140034fd2  test    eax, eax
0x140034fd4  js      loc_140035477
0x140034fda  lea     rax, [rsp+120h+var_D8]
0x140034fdf  mov     r9d, 2Ch ; ','; unsigned __int64
0x140034fe5  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x140034fea  lea     r8, [rbp+3Fh+sz]; wchar_t *
0x140034fee  lea     rax, [rsp+120h+var_E0]
0x140034ff3  mov     rdx, rsi; unsigned __int64
0x140034ff6  mov     rcx, rdi; wchar_t *
0x140034ff9  mov     [rsp+120h+var_100], rax; wchar_t **
0x140034ffe  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140035003  mov     ebx, eax
0x140035005  test    eax, eax
0x140035007  js      loc_140035477
0x14003500d  lea     rax, [rbp+3Fh+var_B0]
0x140035011  mov     r9d, 1; unsigned __int64
0x140035017  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x14003501c  lea     r8, asc_14006C8A8; "/"
0x140035023  lea     rax, [rsp+120h+var_C0]
0x140035028  mov     rdx, rsi; unsigned __int64
0x14003502b  mov     rcx, rdi; wchar_t *
0x14003502e  mov     [rsp+120h+var_100], rax; wchar_t **
0x140035033  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140035038  mov     ebx, eax
0x14003503a  test    eax, eax
0x14003503c  js      loc_140035389
0x140035042  mov     r8, [rbp+3Fh+var_B0]; unsigned __int64
0x140035046  lea     rax, [rbp+3Fh+var_B0]
0x14003504a  mov     rdx, [rsp+120h+var_C0]; wchar_t *
0x14003504f  lea     r9, [rsp+120h+var_C0]; wchar_t **
0x140035054  mov     rcx, r12; this
0x140035057  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x14003505c  call    ?AppendServicePack@CCommonAttributeProvider@@AEAAJPEA_W_KPEAPEA_WPEA_K@Z; CCommonAttributeProvider::AppendServicePack(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x140035061  mov     ebx, eax
0x140035063  test    eax, eax
0x140035065  js      loc_140035389
0x14003506b  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int64
0x14003506f  lea     rax, [rbp+3Fh+var_B0]
0x140035073  mov     rcx, [rsp+120h+var_C0]; wchar_t *
0x140035078  lea     r8, asc_14006C8E4; "?"
0x14003507f  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x140035084  mov     edi, 1
0x140035089  lea     rax, [rsp+120h+var_C0]
0x14003508e  mov     r9d, edi; unsigned __int64
0x140035091  mov     [rsp+120h+var_100], rax; wchar_t **
0x140035096  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x14003509b  mov     ebx, eax
0x14003509d  test    eax, eax
0x14003509f  js      loc_140035389
0x1400350a5  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int64
0x1400350a9  lea     rax, [rbp+3Fh+var_B0]
0x1400350ad  mov     rcx, [rsp+120h+var_C0]; wchar_t *
0x1400350b2  lea     r9d, [rdi+3]; unsigned __int64
0x1400350b6  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x1400350bb  lea     r8, aCh; "CH="
0x1400350c2  lea     rax, [rsp+120h+var_C0]
0x1400350c7  mov     [rsp+120h+var_100], rax; wchar_t **
0x1400350cc  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x1400350d1  mov     ebx, eax
0x1400350d3  test    eax, eax
0x1400350d5  js      loc_140035389
0x1400350db  mov     r8, [rbp+3Fh+var_B0]; unsigned __int64
0x1400350df  lea     rax, [rbp+3Fh+var_B0]
0x1400350e3  mov     rdx, [rsp+120h+var_C0]; wchar_t *
0x1400350e8  lea     r9, [rsp+120h+var_C0]; wchar_t **
0x1400350ed  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x1400350f2  call    ?AppendClientHash@CCommonAttributeProvider@@AEAAJPEA_W_KPEAPEA_WPEA_K@Z; CCommonAttributeProvider::AppendClientHash(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x1400350f7  mov     ebx, eax
0x1400350f9  test    eax, eax
0x1400350fb  js      loc_140035389
0x140035101  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int64
0x140035105  lea     rax, [rbp+3Fh+var_B0]
0x140035109  mov     rcx, [rsp+120h+var_C0]; wchar_t *
0x14003510e  lea     rsi, asc_14006C8E0; "&"
0x140035115  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x14003511a  mov     r9d, edi; unsigned __int64
0x14003511d  lea     rax, [rsp+120h+var_C0]
0x140035122  mov     r8, rsi; wchar_t *
0x140035125  mov     [rsp+120h+var_100], rax; wchar_t **
0x14003512a  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x14003512f  mov     ebx, eax
0x140035131  test    eax, eax
0x140035133  js      loc_140035389
0x140035139  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int64
0x14003513d  lea     rax, [rbp+3Fh+var_B0]
0x140035141  mov     rcx, [rsp+120h+var_C0]; wchar_t *
0x140035146  lea     r12d, [rdi+2]
0x14003514a  mov     [rsp+120h+var_F8], rax; unsigned __int64 *
0x14003514f  lea     r8, asc_14006D15C; "L="
0x140035156  lea     rax, [rsp+120h+var_C0]
0x14003515b  mov     r9d, r12d; unsigned __int64
0x14003515e  mov     [rsp+120h+var_100], rax; wchar_t **
0x140035163  call    ?StringCchCatNExW@@YAJPEA_W_KPEB_W1PEAPEA_WPEA_KK@Z; StringCchCatNExW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong)
0x140035168  mov     ebx, eax
0x14003516a  test    eax, eax
0x14003516c  js      loc_140035389
0x140035172  mov     r8, [rbp+3Fh+var_B0]; unsigned __int64
0x140035176  lea     rax, [rbp+3Fh+var_B0]
0x14003517a  mov     rdx, [rsp+120h+var_C0]; wchar_t *
0x14003517f  lea     r9, [rsp+120h+var_C0]; wchar_t **
0x140035184  mov     [rsp+120h+var_100], rax; unsigned __int64 *
0x140035189  call    ?AppendLanguages@CCommonAttributeProvider@@AEAAJPEA_W_KPEAPEA_WPEA_K@Z; CCommonAttributeProvider::AppendLanguages(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *)
0x14003518e  mov     ebx, eax
0x140035190  test    eax, eax
0x140035192  js      loc_140035389
0x140035198  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int64
0x14003519c  lea     rax, [rbp+3Fh+var_B0]
0x1400351a0  mov     rcx, [rsp+120h+var_C0]; wchar_t *
0x1400351a5  mov     r9d, edi; unsigned __int64
  ... truncated ...
```
