# RetailDemoUserAgent::LaunchAppAndStealForeground(ushort const *,ushort const *,bool,tagRECT *)

- ea: `0x18003e178`
- end: `0x18003e3a6`
- name: `?LaunchAppAndStealForeground@RetailDemoUserAgent@@AEAAJPEBG0_NPEAUtagRECT@@@Z`
- size: `558`
- prototype: `__int64 __usercall@<rax>(RetailDemoUserAgent *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, struct tagRECT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003e3b0`

## callees

- `0x180008bbc`
- `0x18000aa7c`
- `0x1800181b0`
- `0x180022298`
- `0x18002231c`
- `0x180022448`
- `0x180034ad0`
- `0x180036018`
- `0x180036570`
- `0x18003ac20`
- `0x18003d8e8`
- `0x18003e178`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e363`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e1f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e232`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e1f7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e232`

## string_xrefs

- `0x18003e1e6`: `OSDATA\Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18003e24a`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e2a7`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e30f`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`
- `0x18003e228`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RetailDemoUserAgent::LaunchAppAndStealForeground(
        unsigned __int16 **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char a4,
        struct tagRECT *a5)
{
  const unsigned __int16 *v6; // r14
  unsigned int v8; // ebx
  unsigned __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // esi
  const unsigned __int16 *v13; // rax
  int ForegroundControl; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdx
  RetailDemoUserAgent *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int pdwType; // [rsp+28h] [rbp-51h]
  DWORD pcbData; // [rsp+48h] [rbp-31h] BYREF
  int pvData; // [rsp+4Ch] [rbp-2Dh] BYREF
  unsigned int v28; // [rsp+50h] [rbp-29h] BYREF
  struct ITrustedComponentForegroundControl *v29; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v30[104]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+57h]
  const unsigned __int16 *v32; // [rsp+E0h] [rbp+67h] BYREF
  const unsigned __int16 *v33; // [rsp+E8h] [rbp+6Fh] BYREF
  char v34; // [rsp+F0h] [rbp+77h] BYREF

  v34 = a4;
  v32 = a2;
  v6 = a2;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl'::`2'::impl,
    a2);
  pvData = 0;
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"OSDATA\\Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
         L"Enabled",
         0x10010u,
         0,
         &pvData,
         &pcbData) )
  {
    pcbData = 4;
    RegGetValueW(
      HKEY_LOCAL_MACHINE,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
      L"Enabled",
      0x20010010u,
      0,
      &pvData,
      &pcbData);
  }
  if ( pvData )
  {
    if ( v6 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v6[v9] );
      v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
              this + 14,
              v9);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x274,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
          (const char *)(unsigned int)v10,
          pdwType);
        return v11;
      }
      StringCchCopyNW(this[14], v9 + 1, v6, v9);
      this[15] = (unsigned __int16 *)v9;
    }
    else
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(this + 14);
    }
    v13 = &qword_180057BE0;
    if ( a3 )
      v13 = a3;
    v33 = v13;
    v29 = 0;
    ForegroundControl = RetailDemoUserAgent::EnsureForegroundPrivilegeInitialized((RetailDemoUserAgent *)this);
    v8 = ForegroundControl;
    if ( ForegroundControl >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29, v15, v16);
      ForegroundControl = RetailDemoUserAgent::GetForegroundControl(v18, &v29);
      v8 = ForegroundControl;
      if ( ForegroundControl >= 0 )
      {
        v28 = 0;
        v21 = lambda_6e2f007c37fc2c249cdaece063b7a5d6_::_lambda_6e2f007c37fc2c249cdaece063b7a5d6_(
                (unsigned int)v30,
                (_DWORD)this,
                (unsigned int)&v29,
                (unsigned int)&v32,
                (__int64)&v33,
                (__int64)&v34,
                (__int64)&a5,
                (__int64)&v28);
        CurrentThreadId = GetCurrentThreadId();
        Windows::Internal::ComTaskPool::QueueTask__lambda_6e2f007c37fc2c249cdaece063b7a5d6___(
          v24,
          v23,
          CurrentThreadId,
          v21);
        lambda_6e2f007c37fc2c249cdaece063b7a5d6_::__lambda_6e2f007c37fc2c249cdaece063b7a5d6_(v30);
        v8 = v28;
        goto LABEL_20;
      }
      v17 = 639;
    }
    else
    {
      v17 = 638;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)ForegroundControl,
      pdwType);
LABEL_20:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29, v19, v20);
    return v8;
  }
  v8 = -2147024891;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x273,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
    (const char *)0x80070005LL,
    pdwType);
  return v8;
}

```

## disassembly

```asm
0x18003e178  mov     rax, rsp
0x18003e17b  mov     [rax+8], rbx
0x18003e17f  mov     [rax+20h], r9b
0x18003e183  mov     [rax+10h], rdx
0x18003e187  push    rbp
0x18003e188  push    rsi
0x18003e189  push    rdi
0x18003e18a  push    r12
0x18003e18c  push    r13
0x18003e18e  push    r14
0x18003e190  push    r15
0x18003e192  lea     rbp, [rax-57h]
0x18003e196  sub     rsp, 90h
0x18003e19d  mov     r12, r8
0x18003e1a0  mov     r14, rdx
0x18003e1a3  mov     r15, rcx
0x18003e1a6  mov     dl, 1
0x18003e1a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport> `wil::Feature<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::GetImpl(void)'::`2'::impl
0x18003e1af  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_CentennialAppSupport@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_CentennialAppSupport>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18003e1b4  xor     r13d, r13d
0x18003e1b7  mov     [rbp+4Fh+var_7C], r13d
0x18003e1bb  lea     ebx, [r13+4]
0x18003e1bf  mov     [rbp+4Fh+var_80], ebx
0x18003e1c2  lea     rax, [rbp+4Fh+var_80]
0x18003e1c6  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18003e1cb  lea     rax, [rbp+4Fh+var_7C]
0x18003e1cf  mov     [rsp+0C0h+pvData], rax; pvData
0x18003e1d4  mov     [rsp+0C0h+pdwType], r13; pdwType
0x18003e1d9  mov     r9d, 10010h; dwFlags
0x18003e1df  lea     r8, c_retailDemoValueEnabled; "Enabled"
0x18003e1e6  lea     rdx, SubKey; "OSDATA\\Software\\Microsoft\\Windows\\C"...
0x18003e1ed  mov     rdi, 0FFFFFFFF80000002h
0x18003e1f4  mov     rcx, rdi; hkey
0x18003e1f7  call    cs:__imp_RegGetValueW
0x18003e1fd  test    eax, eax
0x18003e1ff  jz      short loc_18003E238
0x18003e201  mov     [rbp+4Fh+var_80], ebx
0x18003e204  lea     rax, [rbp+4Fh+var_80]
0x18003e208  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18003e20d  lea     rax, [rbp+4Fh+var_7C]
0x18003e211  mov     [rsp+0C0h+pvData], rax; pvData
0x18003e216  mov     [rsp+0C0h+pdwType], r13; int
0x18003e21b  mov     r9d, 20010010h; dwFlags
0x18003e221  lea     r8, c_retailDemoValueEnabled; "Enabled"
0x18003e228  lea     rdx, c_retailDemoKeyOobeWrite; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003e22f  mov     rcx, rdi; hkey
0x18003e232  call    cs:__imp_RegGetValueW
0x18003e238  cmp     [rbp+4Fh+var_7C], r13d
0x18003e23c  jnz     short loc_18003E260
0x18003e23e  mov     rcx, [rbp+57h]; this
0x18003e242  mov     ebx, 80070005h
0x18003e247  mov     r9d, ebx; char *
0x18003e24a  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e251  mov     edx, 273h; void *
0x18003e256  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e25b  jmp     loc_18003E389
0x18003e260  lea     rdi, [r15+70h]
0x18003e264  test    r14, r14
0x18003e267  jz      short loc_18003E2BF
0x18003e269  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003e26d  inc     rbx
0x18003e270  cmp     [r14+rbx*2], r13w
0x18003e275  jnz     short loc_18003E26D
0x18003e277  mov     rdx, rbx
0x18003e27a  mov     rcx, rdi
0x18003e27d  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18003e282  mov     esi, eax
0x18003e284  test    eax, eax
0x18003e286  js      short loc_18003E2A0
0x18003e288  lea     rdx, [rbx+1]; unsigned __int64
0x18003e28c  mov     r9, rbx; unsigned __int64
0x18003e28f  mov     r8, r14; unsigned __int16 *
0x18003e292  mov     rcx, [rdi]; unsigned __int16 *
0x18003e295  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18003e29a  mov     [rdi+8], rbx
0x18003e29e  jmp     short loc_18003E2C7
0x18003e2a0  mov     rcx, [rbp+57h]; this
0x18003e2a4  mov     r9d, esi; char *
0x18003e2a7  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e2ae  mov     edx, 274h; void *
0x18003e2b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e2b8  mov     eax, esi
0x18003e2ba  jmp     loc_18003E38B
0x18003e2bf  mov     rcx, rdi
0x18003e2c2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003e2c7  lea     rax, qword_180057BE0
0x18003e2ce  test    r12, r12
0x18003e2d1  cmovnz  rax, r12
0x18003e2d5  mov     [rbp+4Fh+arg_10], rax
0x18003e2d9  mov     [rbp+4Fh+var_70], r13
0x18003e2dd  mov     rcx, r15; this
0x18003e2e0  call    ?EnsureForegroundPrivilegeInitialized@RetailDemoUserAgent@@AEAAJXZ; RetailDemoUserAgent::EnsureForegroundPrivilegeInitialized(void)
0x18003e2e5  mov     ebx, eax
0x18003e2e7  test    eax, eax
0x18003e2e9  jns     short loc_18003E2F2
0x18003e2eb  mov     edx, 27Eh
0x18003e2f0  jmp     short loc_18003E30F
0x18003e2f2  lea     rcx, [rbp+4Fh+var_70]
0x18003e2f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e2fb  lea     rdx, [rbp+4Fh+var_70]; struct ITrustedComponentForegroundControl **
0x18003e2ff  call    ?GetForegroundControl@RetailDemoUserAgent@@AEAAJPEAPEAUITrustedComponentForegroundControl@@@Z; RetailDemoUserAgent::GetForegroundControl(ITrustedComponentForegroundControl * *)
0x18003e304  mov     ebx, eax
0x18003e306  test    eax, eax
0x18003e308  jns     short loc_18003E324
0x18003e30a  mov     edx, 27Fh; void *
0x18003e30f  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18003e316  mov     r9d, eax; char *
0x18003e319  mov     rcx, [rbp+57h]; this
0x18003e31d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e322  jmp     short loc_18003E380
0x18003e324  mov     [rbp+4Fh+var_78], r13d
0x18003e328  lea     rax, [rbp+4Fh+var_78]
0x18003e32c  mov     [rsp+38h], rax
0x18003e331  lea     rax, [rbp+4Fh+arg_20]
0x18003e335  mov     [rsp+0C0h+pcbData], rax
0x18003e33a  lea     rax, [rbp+4Fh+arg_18]
0x18003e33e  mov     [rsp+0C0h+pvData], rax
0x18003e343  lea     rax, [rbp+4Fh+arg_10]
0x18003e347  mov     [rsp+0C0h+pdwType], rax
0x18003e34c  lea     r9, [rbp+4Fh+arg_8]
0x18003e350  lea     r8, [rbp+4Fh+var_70]
0x18003e354  mov     rdx, r15
0x18003e357  lea     rcx, [rbp+4Fh+var_68]
0x18003e35b  call    _lambda_6e2f007c37fc2c249cdaece063b7a5d6____lambda_6e2f007c37fc2c249cdaece063b7a5d6_
0x18003e360  mov     rbx, rax
0x18003e363  call    cs:__imp_GetCurrentThreadId
0x18003e369  mov     r9, rbx
0x18003e36c  mov     r8d, eax
0x18003e36f  call    Windows__Internal__ComTaskPool__QueueTask__lambda_6e2f007c37fc2c249cdaece063b7a5d6___
0x18003e374  lea     rcx, [rbp+4Fh+var_68]
0x18003e378  call    _lambda_6e2f007c37fc2c249cdaece063b7a5d6_____lambda_6e2f007c37fc2c249cdaece063b7a5d6_
0x18003e37d  mov     ebx, [rbp+4Fh+var_78]
0x18003e380  lea     rcx, [rbp+4Fh+var_70]
0x18003e384  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e389  mov     eax, ebx
0x18003e38b  mov     rbx, [rsp+0C0h+arg_0]
0x18003e393  add     rsp, 90h
0x18003e39a  pop     r15
0x18003e39c  pop     r14
0x18003e39e  pop     r13
0x18003e3a0  pop     r12
0x18003e3a2  pop     rdi
0x18003e3a3  pop     rsi
0x18003e3a4  pop     rbp
0x18003e3a5  retn
```
