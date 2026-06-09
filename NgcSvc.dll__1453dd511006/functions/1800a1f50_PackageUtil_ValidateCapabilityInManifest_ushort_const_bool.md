# PackageUtil::ValidateCapabilityInManifest(ushort const *,bool *)

- ea: `0x1800a1f50`
- end: `0x1800a2144`
- name: `?ValidateCapabilityInManifest@PackageUtil@@SAJPEBGPEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(char *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009abe4`

## callees

- `0x18000782c`
- `0x18004826c`
- `0x180048434`
- `0x18005cee0`
- `0x18005dd44`
- `0x1800a0d68`
- `0x1800a1f50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800a20ad`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800a20ad`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800a1fc5`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800a1fc5`
- `ntdll!RtlInitUnicodeString` at `0x1800a1fb1`
- `ntdll!RtlInitUnicodeString` at `0x1800a1fb1`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x1800a2070`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x1800a20d1`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x1800a211a`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x1800a2070`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x1800a20d1`
- `ext-ms-win-kernel32-package-l1-1-0!AppXFreeMemory` at `0x1800a211a`
- `ext-ms-win-kernel32-package-l1-1-0!AppXGetPackageCapabilities` at `0x1800a202f`
- `ext-ms-win-kernel32-package-l1-1-0!AppXGetPackageCapabilities` at `0x1800a202f`

## string_xrefs

- `0x1800a1fd3`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a2049`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`
- `0x1800a20eb`: `onecore\ds\security\devicecredential\service\packageutil\packageutil.cpp`

## pseudocode

```c
__int64 __fastcall PackageUtil::ValidateCapabilityInManifest(char *a1, bool *a2)
{
  int v4; // eax
  int v6; // ebx
  __int64 v7; // rcx
  const char *v8; // rax
  __int64 v9; // rdx
  unsigned int i; // ebx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // [rsp+20h] [rbp-E0h]
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v16; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 *v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  char v19; // [rsp+50h] [rbp-B0h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pSid2[80]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[80]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  DestinationString = 0;
  memset_0(pSid2, 0, 0x44u);
  memset_0(v22, 0, 0x44u);
  *a2 = 0;
  RtlInitUnicodeString(&DestinationString, L"microsoft.secondaryAuthenticationFactorForLogon_8wekyb3d8bbwe");
  v4 = RtlDeriveCapabilitySidsFromName(&DestinationString, v22, pSid2);
  if ( v4 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x1D8,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
             (const char *)(unsigned int)v4,
             v13);
  v16 = 0;
  v17 = &v14;
  v14 = 0;
  v15 = 0;
  v18 = 0;
  v19 = 1;
  v6 = AppXGetPackageCapabilities(a1, &v15, &v18, &v16);
  wil::details::out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>(&v17);
  if ( v6 >= 0 )
  {
    if ( v15 )
    {
      v8 = "%ws is an FullTrust App";
      v9 = 488;
LABEL_17:
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
        (const char *)0x80070005LL,
        (int)v8,
        a1);
      v12 = v14;
      v14 = 0;
      if ( v12 )
        AppXFreeMemory(v12);
      return 2147942405LL;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v16 )
        {
          v8 = "%ws doesn't have capability";
          v9 = 502;
          goto LABEL_17;
        }
        if ( EqualSid(*(PSID *)(v14 + 16LL * i), pSid2) )
          break;
      }
      v11 = v14;
      *a2 = 1;
      v14 = 0;
      if ( v11 )
        AppXFreeMemory(v11);
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\packageutil\\packageutil.cpp",
      (const char *)(unsigned int)v6,
      v13);
    v7 = v14;
    v14 = 0;
    if ( v7 )
      AppXFreeMemory(v7);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x1800a1f50  mov     [rsp-8+arg_10], rbx
0x1800a1f55  push    rbp
0x1800a1f56  push    rsi
0x1800a1f57  push    rdi
0x1800a1f58  lea     rbp, [rsp-20h]
0x1800a1f5d  sub     rsp, 120h
0x1800a1f64  mov     rax, cs:__security_cookie
0x1800a1f6b  xor     rax, rsp
0x1800a1f6e  mov     [rbp+30h+var_20], rax
0x1800a1f72  mov     rsi, rdx
0x1800a1f75  mov     rdi, rcx
0x1800a1f78  xorps   xmm0, xmm0
0x1800a1f7b  lea     rcx, [rsp+130h+pSid2]; void *
0x1800a1f80  mov     ebx, 44h ; 'D'
0x1800a1f85  xor     edx, edx; Val
0x1800a1f87  mov     r8d, ebx; Size
0x1800a1f8a  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x1800a1f8f  call    memset_0
0x1800a1f94  mov     r8d, ebx; Size
0x1800a1f97  lea     rcx, [rbp+30h+var_70]; void *
0x1800a1f9b  xor     edx, edx; Val
0x1800a1f9d  call    memset_0
0x1800a1fa2  lea     rdx, aMicrosoftSecon; "microsoft.secondaryAuthenticationFactor"...
0x1800a1fa9  mov     byte ptr [rsi], 0
0x1800a1fac  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x1800a1fb1  call    cs:__imp_RtlInitUnicodeString
0x1800a1fb7  lea     r8, [rsp+130h+pSid2]
0x1800a1fbc  lea     rdx, [rbp+30h+var_70]
0x1800a1fc0  lea     rcx, [rsp+130h+DestinationString]
0x1800a1fc5  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800a1fcb  test    eax, eax
0x1800a1fcd  jns     short loc_1800A1FEC
0x1800a1fcf  mov     rcx, [rbp+38h]; this
0x1800a1fd3  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a1fda  mov     r9d, eax; char *
0x1800a1fdd  mov     edx, 1D8h; void *
0x1800a1fe2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a1fe7  jmp     loc_1800A2125
0x1800a1fec  lea     rax, [rsp+130h+var_100]
0x1800a1ff1  mov     [rsp+130h+var_F4], 0
0x1800a1ff9  lea     r9, [rsp+130h+var_F4]
0x1800a1ffe  mov     [rsp+130h+var_F0], rax
0x1800a2003  lea     r8, [rsp+130h+var_E8]
0x1800a2008  mov     [rsp+130h+var_100], 0
0x1800a2011  lea     rdx, [rsp+130h+var_F8]
0x1800a2016  mov     [rsp+130h+var_F8], 0
0x1800a201e  mov     rcx, rdi
0x1800a2021  mov     [rsp+130h+var_E8], 0
0x1800a202a  mov     [rsp+130h+var_E0], 1
0x1800a202f  call    cs:__imp_AppXGetPackageCapabilities
0x1800a2035  lea     rcx, [rsp+130h+var_F0]
0x1800a203a  mov     ebx, eax
0x1800a203c  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@U_SID_AND_ATTRIBUTES@@U?$function_deleter@P6AXPEAX@Z$1?AppXFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&AppXFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&AppXFreeMemory(void *)>>>(void)
0x1800a2041  test    ebx, ebx
0x1800a2043  jns     short loc_1800A207D
0x1800a2045  mov     rcx, [rbp+38h]; this
0x1800a2049  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a2050  mov     r9d, ebx; char *
0x1800a2053  mov     edx, 1E2h; void *
0x1800a2058  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a205d  mov     rcx, [rsp+130h+var_100]
0x1800a2062  mov     [rsp+130h+var_100], 0
0x1800a206b  test    rcx, rcx
0x1800a206e  jz      short loc_1800A2076
0x1800a2070  call    cs:__imp_AppXFreeMemory
0x1800a2076  mov     eax, ebx
0x1800a2078  jmp     loc_1800A2125
0x1800a207d  cmp     [rsp+130h+var_F8], 0
0x1800a2082  jz      short loc_1800A2092
0x1800a2084  lea     rax, aWsIsAnFulltrus; "%ws is an FullTrust App"
0x1800a208b  mov     edx, 1E8h
0x1800a2090  jmp     short loc_1800A20E7
0x1800a2092  xor     ebx, ebx
0x1800a2094  cmp     ebx, [rsp+130h+var_F4]
0x1800a2098  jnb     short loc_1800A20DB
0x1800a209a  mov     rcx, [rsp+130h+var_100]
0x1800a209f  lea     rdx, [rsp+130h+pSid2]; pSid2
0x1800a20a4  mov     eax, ebx
0x1800a20a6  add     rax, rax
0x1800a20a9  mov     rcx, [rcx+rax*8]; pSid1
0x1800a20ad  call    cs:__imp_EqualSid
0x1800a20b3  test    eax, eax
0x1800a20b5  jnz     short loc_1800A20BB
0x1800a20b7  inc     ebx
0x1800a20b9  jmp     short loc_1800A2094
0x1800a20bb  mov     rcx, [rsp+130h+var_100]
0x1800a20c0  mov     byte ptr [rsi], 1
0x1800a20c3  mov     [rsp+130h+var_100], 0
0x1800a20cc  test    rcx, rcx
0x1800a20cf  jz      short loc_1800A20D7
0x1800a20d1  call    cs:__imp_AppXFreeMemory
0x1800a20d7  xor     eax, eax
0x1800a20d9  jmp     short loc_1800A2125
0x1800a20db  lea     rax, aWsDoesnTHaveCa; "%ws doesn't have capability"
0x1800a20e2  mov     edx, 1F6h; void *
0x1800a20e7  mov     rcx, [rbp+38h]; this
0x1800a20eb  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\devicecredential"...
0x1800a20f2  mov     [rsp+130h+var_108], rdi; char *
0x1800a20f7  mov     r9d, 80070005h; char *
0x1800a20fd  mov     qword ptr [rsp+130h+var_110], rax; int
0x1800a2102  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800a2107  mov     rcx, [rsp+130h+var_100]
0x1800a210c  mov     [rsp+130h+var_100], 0
0x1800a2115  test    rcx, rcx
0x1800a2118  jz      short loc_1800A2120
0x1800a211a  call    cs:__imp_AppXFreeMemory
0x1800a2120  mov     eax, 80070005h
0x1800a2125  mov     rcx, [rbp+30h+var_20]
0x1800a2129  xor     rcx, rsp; StackCookie
0x1800a212c  call    __security_check_cookie
0x1800a2131  mov     rbx, [rsp+130h+arg_10]
0x1800a2139  add     rsp, 120h
0x1800a2140  pop     rdi
0x1800a2141  pop     rsi
0x1800a2142  pop     rbp
0x1800a2143  retn
```
