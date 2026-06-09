# CProviderRegistrationCache::RefreshProvCache(void)

- ea: `0x180003fb0`
- end: `0x1800043c0`
- name: `?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ`
- size: `1040`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this)`
- caller_count: `8`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002560`
- `0x1800030f0`
- `0x1800066f0`
- `0x18000caa0`
- `0x18000d51c`
- `0x180014c2c`
- `0x1800157d4`
- `0x18001640c`

## callees

- `0x180003e60`
- `0x180003fb0`
- `0x1800043d0`
- `0x1800064e0`
- `0x180007b70`
- `0x180007d20`
- `0x180007da0`
- `0x180009960`
- `0x18000c344`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000418f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004226`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000418f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004343`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004343`
- `CRYPT32!CertControlStore` at `0x180004335`
- `CRYPT32!CertControlStore` at `0x180004335`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000405e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000405e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800041b9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800041b9`
- `ntdll!RtlReleaseResource` at `0x180004083`
- `ntdll!RtlReleaseResource` at `0x1800040fb`
- `ntdll!RtlReleaseResource` at `0x180004185`
- `ntdll!RtlReleaseResource` at `0x1800041fc`
- `ntdll!RtlReleaseResource` at `0x18000423a`
- `ntdll!RtlReleaseResource` at `0x180004250`
- `ntdll!RtlReleaseResource` at `0x18000425e`
- `ntdll!RtlReleaseResource` at `0x1800042a4`
- `ntdll!RtlReleaseResource` at `0x1800042c5`
- `ntdll!RtlReleaseResource` at `0x180004083`
- `ntdll!RtlReleaseResource` at `0x1800040fb`
- `ntdll!RtlReleaseResource` at `0x180004185`
- `ntdll!RtlReleaseResource` at `0x1800041fc`
- `ntdll!RtlReleaseResource` at `0x18000423a`
- `ntdll!RtlReleaseResource` at `0x180004250`
- `ntdll!RtlReleaseResource` at `0x18000425e`
- `ntdll!RtlReleaseResource` at `0x1800042a4`
- `ntdll!RtlReleaseResource` at `0x1800042c5`
- `ntdll!RtlAcquireResourceShared` at `0x180004010`
- `ntdll!RtlAcquireResourceShared` at `0x18000420f`
- `ntdll!RtlAcquireResourceShared` at `0x180004010`
- `ntdll!RtlAcquireResourceShared` at `0x18000420f`
- `ntdll!RtlAcquireResourceExclusive` at `0x180004269`
- `ntdll!RtlAcquireResourceExclusive` at `0x180004269`

## string_xrefs

- `0x180003fde`: `CProviderRegistrationCache::RefreshProvCache`
- `0x18000437e`: `RefreshProvCache::RegQueryInfoKey`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::RefreshProvCache(CProviderRegistrationCache *this)
{
  HKEY v2; // rcx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  void *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int LsaSrv; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  const HANDLE *v13; // rdx
  DWORD v14; // eax
  int v15; // ecx
  int v16; // r8d
  DWORD v17; // eax
  int IsDeviceJoined; // eax
  __int64 v19; // rdx
  struct _RTL_RESOURCE *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rcx
  const char *v24; // r8
  DWORD LastError; // eax
  int ProviderRegistration; // [rsp+60h] [rbp-78h] BYREF
  int v27; // [rsp+64h] [rbp-74h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-70h] BYREF
  const char *v29; // [rsp+70h] [rbp-68h] BYREF
  __int128 v30; // [rsp+78h] [rbp-60h]
  int *v31; // [rsp+88h] [rbp-50h]
  PRTL_RESOURCE Resource; // [rsp+90h] [rbp-48h] BYREF
  char v33; // [rsp+98h] [rbp-40h]

  ProviderRegistration = 0;
  ftLastWriteTime = 0;
  v29 = "CProviderRegistrationCache::RefreshProvCache";
  v30 = 0;
  v31 = &ProviderRegistration;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(this, Func_Start, "CProviderRegistrationCache::RefreshProvCache");
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 16), 1u);
  if ( !*((_DWORD *)this + 2) )
  {
    ProviderRegistration = 5023;
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
    goto LABEL_16;
  }
  v2 = (HKEY)*((_QWORD *)this + 14);
  if ( !v2 )
    goto LABEL_7;
  v3 = RegQueryInfoKeyW(v2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
  ProviderRegistration = v3;
  if ( v3 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v5, v4, "RefreshProvCache::RegQueryInfoKey", v3);
    goto LABEL_7;
  }
  v6 = (void *)*((_QWORD *)this + 16);
  if ( !v6 || !WaitForSingleObject(v6, 0) || (v13 = (const HANDLE *)*((_QWORD *)this + 21)) == 0 )
  {
LABEL_7:
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
    ProviderRegistration = CProviderRegistrationCache::ReadProviderRegistration(this);
    goto LABEL_8;
  }
  v14 = WaitForMultipleObjects(*((_DWORD *)this + 44), v13, 0, 0);
  if ( v14 < *((_DWORD *)this + 44) )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(v15, (unsigned int)Cert_Store_Changed, v16, 1, (__int64)&Resource);
    goto LABEL_7;
  }
  v20 = (struct _RTL_RESOURCE *)((char *)this + 16);
  if ( v14 != 258 )
  {
    ProviderRegistration = 735;
    RtlReleaseResource(v20);
    goto LABEL_16;
  }
  RtlReleaseResource(v20);
  Resource = (PRTL_RESOURCE)((char *)this + 16);
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 16), 1u);
  v33 = 1;
  v17 = WaitForSingleObject(*((HANDLE *)this + 42), 0);
  if ( v17 )
  {
    if ( v17 != 258 )
    {
      ProviderRegistration = 735;
      RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
      goto LABEL_16;
    }
    goto LABEL_33;
  }
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
  RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 16), 1u);
  v33 = 1;
  IsDeviceJoined = DsrIsDeviceJoinedEx((char *)this + 344);
  if ( IsDeviceJoined < 0 )
  {
    ProviderRegistration = 1353;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_37;
    McTemplateU0sq_EtwEventWriteTransfer(
      (unsigned int)Microsoft_Windows_CertPolEngEnableBits,
      v19,
      "DsrIsDeviceJoined",
      (unsigned int)IsDeviceJoined);
    v22 = (unsigned int)ProviderRegistration;
    v23 = (unsigned int)Microsoft_Windows_CertPolEngEnableBits;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_37;
    v24 = "DsrIsDeviceJoined(mapped)";
    goto LABEL_47;
  }
  if ( !CertControlStore(*((HCERTSTORE *)this + 41), 0, 4u, (char *)this + 336) )
  {
    LastError = GetLastError();
    ProviderRegistration = LastError;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
    {
LABEL_37:
      RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
      goto LABEL_16;
    }
    v22 = LastError;
    v24 = "CertControlStore";
LABEL_47:
    McTemplateU0sq_EtwEventWriteTransfer(v23, v21, v24, v22);
    goto LABEL_37;
  }
LABEL_33:
  RtlReleaseResource((PRTL_RESOURCE)((char *)this + 16));
LABEL_8:
  if ( *((_DWORD *)this + 78) )
    goto LABEL_16;
  CAutoRtlLock::CAutoRtlLock((__int64)&Resource, (struct _RTL_RESOURCE *)((char *)this + 16), 1);
  if ( *((_DWORD *)this + 78) )
  {
    if ( !v33 )
      goto LABEL_16;
LABEL_14:
    RtlReleaseResource(Resource);
    goto LABEL_16;
  }
  LsaSrv = CProviderRegistrationCache::LoadLsaSrv(this);
  ProviderRegistration = LsaSrv;
  if ( !LsaSrv )
  {
    *((_DWORD *)this + 78) = 1;
    if ( !v33 )
      goto LABEL_16;
    goto LABEL_14;
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    McTemplateU0sq_EtwEventWriteTransfer(v8, v7, "LoadLsaSrv", LsaSrv);
  if ( v33 )
    goto LABEL_14;
LABEL_16:
  v10 = ProviderRegistration;
  if ( ProviderRegistration > 0 )
    v11 = (unsigned __int16)ProviderRegistration | 0x80070000;
  else
    v11 = (unsigned int)ProviderRegistration;
  v27 = v11;
  if ( (int)v11 < 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v8, v7, "CProviderRegistrationCache::RefreshProvCache", v11);
    CertPolEngProvider::GenericMethodFailure<char const * &,long &>((const unsigned __int16 **)&v29, &v27);
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(v8, Func_Exit, "CProviderRegistrationCache::RefreshProvCache");
  return v10;
}

```

## disassembly

```asm
0x180003fb0  mov     r11, rsp
0x180003fb3  push    rbx
0x180003fb4  push    rsi
0x180003fb5  push    rdi
0x180003fb6  push    r14
0x180003fb8  sub     rsp, 0B8h
0x180003fbf  mov     rax, cs:__security_cookie
0x180003fc6  xor     rax, rsp
0x180003fc9  mov     [rsp+0D8h+var_38], rax
0x180003fd1  mov     rbx, rcx
0x180003fd4  xor     esi, esi
0x180003fd6  mov     [rsp+0D8h+var_78], esi
0x180003fda  mov     [r11-70h], rsi
0x180003fde  lea     r14, aCproviderregis_4; "CProviderRegistrationCache::RefreshProv"...
0x180003fe5  mov     [r11-68h], r14
0x180003fe9  xorps   xmm0, xmm0
0x180003fec  movdqu  [rsp+0D8h+var_60], xmm0
0x180003ff2  lea     rax, [r11-78h]
0x180003ff6  mov     [r11-50h], rax
0x180003ffa  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180004001  jnz     loc_1800042E3
0x180004007  lea     rdi, [rbx+10h]
0x18000400b  mov     dl, 1; Wait
0x18000400d  mov     rcx, rdi; Resource
0x180004010  call    cs:__imp_RtlAcquireResourceShared
0x180004016  cmp     dword ptr [rbx+8], 0
0x18000401a  jz      loc_18000417A
0x180004020  mov     rcx, [rbx+70h]; hKey
0x180004024  test    rcx, rcx
0x180004027  jz      short loc_180004080
0x180004029  lea     rax, [rsp+0D8h+ftLastWriteTime]
0x18000402e  mov     [rsp+0D8h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004033  mov     [rsp+0D8h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180004038  mov     [rsp+0D8h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18000403d  mov     [rsp+0D8h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180004042  mov     [rsp+0D8h+lpcValues], rsi; lpcValues
0x180004047  mov     [rsp+0D8h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18000404c  mov     [rsp+0D8h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180004051  mov     [rsp+0D8h+lpcSubKeys], rsi; lpcSubKeys
0x180004056  xor     r9d, r9d; lpReserved
0x180004059  xor     r8d, r8d; lpcchClass
0x18000405c  xor     edx, edx; lpClass
0x18000405e  call    cs:__imp_RegQueryInfoKeyW
0x180004064  mov     [rsp+0D8h+var_78], eax
0x180004068  test    eax, eax
0x18000406a  jnz     loc_18000436E
0x180004070  mov     rcx, [rbx+80h]; hHandle
0x180004077  test    rcx, rcx
0x18000407a  jnz     loc_18000418D
0x180004080  mov     rcx, rdi; Resource
0x180004083  call    cs:__imp_RtlReleaseResource
0x180004089  mov     rcx, rbx; this
0x18000408c  call    ?ReadProviderRegistration@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::ReadProviderRegistration(void)
0x180004091  mov     [rsp+0D8h+var_78], eax
0x180004095  cmp     dword ptr [rbx+138h], 0
0x18000409c  jnz     short loc_180004117
0x18000409e  mov     r8d, 1
0x1800040a4  mov     rdx, rdi
0x1800040a7  lea     rcx, [rsp+0D8h+Resource]
0x1800040af  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x1800040b4  cmp     dword ptr [rbx+138h], 0
0x1800040bb  jnz     loc_1800042D0
0x1800040c1  mov     rcx, rbx; this
0x1800040c4  call    ?LoadLsaSrv@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::LoadLsaSrv(void)
0x1800040c9  mov     [rsp+0D8h+var_78], eax
0x1800040cd  test    eax, eax
0x1800040cf  jz      short loc_180004103
0x1800040d1  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800040d8  jz      short loc_1800040E9
0x1800040da  mov     r9d, eax
0x1800040dd  lea     r8, aLoadlsasrv; "LoadLsaSrv"
0x1800040e4  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800040e9  cmp     [rsp+0D8h+var_40], 0
0x1800040f1  jz      short loc_180004117
0x1800040f3  mov     rcx, [rsp+0D8h+Resource]; Resource
0x1800040fb  call    cs:__imp_RtlReleaseResource
0x180004101  jmp     short loc_180004117
0x180004103  mov     dword ptr [rbx+138h], 1
0x18000410d  cmp     [rsp+0D8h+var_40], 0
0x180004115  jnz     short loc_1800040F3
0x180004117  mov     ebx, [rsp+0D8h+var_78]
0x18000411b  test    ebx, ebx
0x18000411d  jg      loc_18000438F
0x180004123  mov     r9d, ebx
0x180004126  mov     [rsp+0D8h+var_74], r9d
0x18000412b  test    r9d, r9d
0x18000412e  js      short loc_18000415C
0x180004130  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180004137  jnz     loc_1800043AC
0x18000413d  mov     eax, ebx
0x18000413f  mov     rcx, [rsp+0D8h+var_38]
0x180004147  xor     rcx, rsp; StackCookie
0x18000414a  call    __security_check_cookie
0x18000414f  add     rsp, 0B8h
0x180004156  pop     r14
0x180004158  pop     rdi
0x180004159  pop     rsi
0x18000415a  pop     rbx
0x18000415b  retn
0x18000415c  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004163  jnz     loc_18000439F
0x180004169  lea     rdx, [rsp+0D8h+var_74]
0x18000416e  lea     rcx, [rsp+0D8h+var_68]
0x180004173  call    ??$GenericMethodFailure@AEAPEBDAEAJ@CertPolEngProvider@@SAXAEAPEBDAEAJ@Z; CertPolEngProvider::GenericMethodFailure<char const * &,long &>(char const * &,long &)
0x180004178  jmp     short loc_180004130
0x18000417a  mov     [rsp+0D8h+var_78], 139Fh
0x180004182  mov     rcx, rdi; Resource
0x180004185  call    cs:__imp_RtlReleaseResource
0x18000418b  jmp     short loc_180004117
0x18000418d  xor     edx, edx; dwMilliseconds
0x18000418f  call    cs:__imp_WaitForSingleObject
0x180004195  test    eax, eax
0x180004197  jz      loc_180004080
0x18000419d  mov     rdx, [rbx+0A8h]; lpHandles
0x1800041a4  test    rdx, rdx
0x1800041a7  jz      loc_180004080
0x1800041ad  xor     r9d, r9d; dwMilliseconds
0x1800041b0  xor     r8d, r8d; bWaitAll
0x1800041b3  mov     ecx, [rbx+0B0h]; nCount
0x1800041b9  call    cs:__imp_WaitForMultipleObjects
0x1800041bf  cmp     eax, [rbx+0B0h]
0x1800041c5  jnb     loc_1800042AF
0x1800041cb  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x1800041d2  jz      loc_180004080
0x1800041d8  lea     rax, [rsp+0D8h+Resource]
0x1800041e0  mov     [rsp+0D8h+lpcSubKeys], rax
0x1800041e5  mov     r9d, 1
0x1800041eb  lea     rdx, Cert_Store_Changed
0x1800041f2  call    McGenEventWrite_EtwEventWriteTransfer
0x1800041f7  jmp     loc_180004080
0x1800041fc  call    cs:__imp_RtlReleaseResource
0x180004202  mov     [rsp+0D8h+Resource], rdi
0x18000420a  mov     dl, 1; Wait
0x18000420c  mov     rcx, rdi; Resource
0x18000420f  call    cs:__imp_RtlAcquireResourceShared
0x180004215  mov     [rsp+0D8h+var_40], 1
0x18000421d  xor     edx, edx; dwMilliseconds
0x18000421f  mov     rcx, [rbx+150h]; hHandle
0x180004226  call    cs:__imp_WaitForSingleObject
0x18000422c  test    eax, eax
0x18000422e  jz      short loc_18000425B
0x180004230  cmp     eax, 102h
0x180004235  jnz     short loc_180004245
0x180004237  mov     rcx, rdi; Resource
0x18000423a  call    cs:__imp_RtlReleaseResource
0x180004240  jmp     loc_180004095
0x180004245  mov     [rsp+0D8h+var_78], 2DFh
0x18000424d  mov     rcx, rdi; Resource
0x180004250  call    cs:__imp_RtlReleaseResource
0x180004256  jmp     loc_180004117
0x18000425b  mov     rcx, rdi; Resource
0x18000425e  call    cs:__imp_RtlReleaseResource
0x180004264  mov     dl, 1; Wait
0x180004266  mov     rcx, rdi; Resource
0x180004269  call    cs:__imp_RtlAcquireResourceExclusive
0x18000426f  mov     [rsp+0D8h+var_40], 1
0x180004277  lea     rcx, [rbx+158h]
0x18000427e  call    DsrIsDeviceJoinedEx
0x180004283  test    eax, eax
0x180004285  jns     loc_18000431F
0x18000428b  mov     r9d, 549h
0x180004291  mov     [rsp+0D8h+var_78], r9d
0x180004296  mov     ecx, cs:Microsoft_Windows_CertPolEngEnableBits
0x18000429c  test    cl, 2
0x18000429f  jnz     short loc_1800042F7
0x1800042a1  mov     rcx, rdi; Resource
0x1800042a4  call    cs:__imp_RtlReleaseResource
0x1800042aa  jmp     loc_180004117
0x1800042af  mov     rcx, rdi; Resource
0x1800042b2  cmp     eax, 102h
0x1800042b7  jz      loc_1800041FC
0x1800042bd  mov     [rsp+0D8h+var_78], 2DFh
0x1800042c5  call    cs:__imp_RtlReleaseResource
0x1800042cb  jmp     loc_180004117
0x1800042d0  cmp     [rsp+0D8h+var_40], 0
0x1800042d8  jnz     loc_1800040F3
0x1800042de  jmp     loc_180004117
0x1800042e3  mov     r8, r14
0x1800042e6  lea     rdx, Func_Start
0x1800042ed  call    McTemplateU0s_EtwEventWriteTransfer
0x1800042f2  jmp     loc_180004007
0x1800042f7  mov     r9d, eax
0x1800042fa  lea     r8, aDsrisdevicejoi_1; "DsrIsDeviceJoined"
0x180004301  call    McTemplateU0sq_EtwEventWriteTransfer
0x180004306  mov     r9d, [rsp+0D8h+var_78]
0x18000430b  mov     ecx, cs:Microsoft_Windows_CertPolEngEnableBits
0x180004311  test    cl, 2
0x180004314  jz      short loc_1800042A1
0x180004316  lea     r8, aDsrisdevicejoi_0; "DsrIsDeviceJoined(mapped)"
0x18000431d  jmp     short loc_180004364
0x18000431f  lea     r9, [rbx+150h]; pvCtrlPara
0x180004326  xor     edx, edx; dwFlags
0x180004328  mov     r8d, 4; dwCtrlType
0x18000432e  mov     rcx, [rbx+148h]; hCertStore
0x180004335  call    cs:__imp_CertControlStore
0x18000433b  test    eax, eax
0x18000433d  jnz     loc_180004237
0x180004343  call    cs:__imp_GetLastError
0x180004349  mov     [rsp+0D8h+var_78], eax
0x18000434d  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004354  jz      loc_1800042A1
0x18000435a  mov     r9d, eax
0x18000435d  lea     r8, aCertcontrolsto; "CertControlStore"
0x180004364  call    McTemplateU0sq_EtwEventWriteTransfer
0x180004369  jmp     loc_1800042A1
0x18000436e  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180004375  jz      loc_180004080
0x18000437b  mov     r9d, eax
0x18000437e  lea     r8, aRefreshprovcac; "RefreshProvCache::RegQueryInfoKey"
0x180004385  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000438a  jmp     loc_180004080
0x18000438f  movzx   r9d, bx
0x180004393  or      r9d, 80070000h
0x18000439a  jmp     loc_180004126
0x18000439f  mov     r8, r14
0x1800043a2  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800043a7  jmp     loc_180004169
0x1800043ac  mov     r8, r14
0x1800043af  lea     rdx, Func_Exit
0x1800043b6  call    McTemplateU0s_EtwEventWriteTransfer
0x1800043bb  jmp     loc_18000413D
```
