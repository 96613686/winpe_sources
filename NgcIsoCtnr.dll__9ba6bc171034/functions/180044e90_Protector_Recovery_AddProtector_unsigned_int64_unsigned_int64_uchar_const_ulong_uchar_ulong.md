# Protector::Recovery::AddProtector(unsigned __int64,unsigned __int64,uchar const *,ulong,uchar * *,ulong *)

- ea: `0x180044e90`
- end: `0x180045168`
- name: `?AddProtector@Recovery@Protector@@UEAAJ_K0PEBEKPEAPEAEPEAK@Z`
- size: `728`
- prototype: `__int64 __fastcall(Protector::Recovery *__hidden this, unsigned __int64, unsigned __int64, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007670`
- `0x18000d62c`
- `0x180017f94`
- `0x18002d274`
- `0x18002dfac`
- `0x18002ff34`
- `0x18003b8a4`
- `0x180044618`
- `0x180044648`
- `0x1800446cc`
- `0x180044e90`
- `0x180064a54`
- `0x180066934`
- `0x180070e3c`
- `0x180073e68`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800450f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800450f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045012`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045129`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045012`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180045129`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180045076`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180045076`

## string_xrefs

- `0x180044ef6`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x180044f82`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x180044fed`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x180045055`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`
- `0x1800450d1`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\protectors.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Protector::Recovery::AddProtector(
        Protector::Recovery *this,
        __int64 a2,
        __int64 a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // r8d
  HLOCAL v13; // rcx
  unsigned int v14; // eax
  int v15; // eax
  unsigned int v16; // edi
  void **v17; // r9
  unsigned __int8 *v18; // rcx
  HLOCAL v19; // rcx
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int SourceSize; // [rsp+48h] [rbp-B8h]
  unsigned int SourceSize_4; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int8 *v26; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 **p_hMem; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+68h] [rbp-98h]
  NgcUtils *v30[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[368]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  if ( Properties::SecretStore::IsEmpty((Protector::Recovery *)((char *)this + 56)) )
  {
    SourceSize = 0;
    v30[0] = 0;
    p_hMem = (unsigned __int8 **)v30;
    *(_QWORD *)v28 = 0;
    v29 = 1;
    v11 = (*(__int64 (__fastcall **)(Protector::Recovery *))(*(_QWORD *)this + 88LL))(this);
    v10 = NgcIsoTrustlet::AddProtector((char *)this + 8, v11, a2, a3);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(&p_hMem);
    if ( v10 >= 0 )
    {
      hMem = 0;
      SourceSize_4 = 0;
      p_hMem = (unsigned __int8 **)&hMem;
      *(_QWORD *)v28 = 0;
      v29 = 1;
      v10 = NgcUtils::ProtectData(
              v30[0],
              (const unsigned __int8 *)SourceSize,
              v12,
              (unsigned int)v28,
              (unsigned __int8 **)&SourceSize_4,
              0);
      wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      if ( v10 >= 0 )
      {
        Properties::RecoveryProtector::RecoveryProtector((Properties::RecoveryProtector *)&SystemTimeAsFileTime);
        v14 = (*(__int64 (__fastcall **)(Protector::Recovery *))(*(_QWORD *)this + 88LL))(this);
        v15 = NgcIsoTrustlet::ExportSecretStore((char *)this + 8, v14, v32);
        v10 = v15;
        if ( v15 >= 0 )
        {
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          Properties::RecoveryProtector::operator=((char *)this + 24, &SystemTimeAsFileTime);
          v26 = 0;
          p_hMem = &v26;
          *(_QWORD *)v28 = 0;
          v29 = 1;
          v16 = SourceSize_4;
          v10 = NgcUtils::CoMemAllocCopy((NgcUtils *)hMem, SourceSize_4, (unsigned __int64)v28, v17);
          wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_hMem);
          if ( v10 >= 0 )
          {
            *a6 = v26;
            *a7 = v16;
            v26 = 0;
            Properties::RecoveryProtector::~RecoveryProtector((Properties::RecoveryProtector *)&SystemTimeAsFileTime);
            v19 = hMem;
            hMem = 0;
            if ( v19 )
              LocalFree(v19);
            v10 = 0;
            goto LABEL_18;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x47F,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
            (const char *)(unsigned int)v10,
            v22);
          v18 = v26;
          v26 = 0;
          if ( v18 )
            CoTaskMemFree(v18);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x475,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
            (const char *)(unsigned int)v15,
            v22);
        }
        Properties::RecoveryProtector::~RecoveryProtector((Properties::RecoveryProtector *)&SystemTimeAsFileTime);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x46E,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
          (const char *)(unsigned int)v10,
          v22);
      }
      v13 = hMem;
      hMem = 0;
      if ( v13 )
        LocalFree(v13);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x462,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
        (const char *)(unsigned int)v10,
        0);
    }
LABEL_18:
    std::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>::~unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>(v30);
    return (unsigned int)v10;
  }
  v10 = -2146893809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x456,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\protectors.cpp",
    (const char *)0x8009000FLL,
    v21);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180044e90  mov     [rsp-8+arg_18], rbx
0x180044e95  push    rbp
0x180044e96  push    rsi
0x180044e97  push    rdi
0x180044e98  push    r12
0x180044e9a  push    r13
0x180044e9c  push    r14
0x180044e9e  push    r15
0x180044ea0  lea     rbp, [rsp-120h]
0x180044ea8  sub     rsp, 220h
0x180044eaf  mov     rax, cs:__security_cookie
0x180044eb6  xor     rax, rsp
0x180044eb9  mov     [rbp+150h+var_40], rax
0x180044ec0  mov     r12, r8
0x180044ec3  mov     rbx, rdx
0x180044ec6  mov     rdi, rcx
0x180044ec9  mov     rsi, [rbp+150h+arg_28]
0x180044ed0  mov     r14, [rbp+150h+arg_30]
0x180044ed7  add     rcx, 38h ; '8'; this
0x180044edb  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180044ee0  xor     r13d, r13d
0x180044ee3  test    al, al
0x180044ee5  jnz     short loc_180044F0C
0x180044ee7  mov     rcx, [rbp+158h]; this
0x180044eee  mov     ebx, 8009000Fh
0x180044ef3  mov     r9d, ebx; char *
0x180044ef6  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180044efd  mov     edx, 456h; void *
0x180044f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044f07  jmp     loc_18004513C
0x180044f0c  mov     dword ptr [rsp+250h+SourceSize], r13d
0x180044f11  mov     [rsp+250h+var_1E0], r13
0x180044f16  lea     rax, [rsp+250h+var_1E0]
0x180044f1b  mov     [rsp+250h+var_1F8], rax
0x180044f20  mov     qword ptr [rsp+250h+var_1F0], r13
0x180044f25  mov     [rsp+250h+var_1E8], 1
0x180044f2a  mov     rax, [rdi]
0x180044f2d  mov     rcx, rdi
0x180044f30  mov     rax, [rax+58h]
0x180044f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044f39  lea     rcx, [rsp+250h+var_1F0]
0x180044f3e  mov     [rsp+250h+var_218], rcx
0x180044f43  lea     rcx, [rsp+250h+SourceSize]
0x180044f48  mov     [rsp+250h+var_220], rcx
0x180044f4d  mov     [rsp+250h+var_228], r13; unsigned int *
0x180044f52  mov     [rsp+250h+var_230], r13; int
0x180044f57  mov     r9, r12
0x180044f5a  mov     r8, rbx
0x180044f5d  mov     edx, eax
0x180044f5f  lea     rcx, [rdi+8]
0x180044f63  call    ?AddProtector@NgcIsoTrustlet@@YAJAEBU_GUID@@W4NgcCtnrProtectorId@@_K22PEBEPEAKPEAPEAE@Z; NgcIsoTrustlet::AddProtector(_GUID const &,NgcCtnrProtectorId,unsigned __int64,unsigned __int64,unsigned __int64,uchar const *,ulong *,uchar * *)
0x180044f68  mov     ebx, eax
0x180044f6a  lea     rcx, [rsp+250h+var_1F8]
0x180044f6f  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>(void)
0x180044f74  test    ebx, ebx
0x180044f76  jns     short loc_180044F98
0x180044f78  mov     rcx, [rbp+158h]; this
0x180044f7f  mov     r9d, ebx; char *
0x180044f82  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180044f89  mov     edx, 462h; void *
0x180044f8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044f93  jmp     loc_180045132
0x180044f98  mov     [rsp+250h+hMem], r13
0x180044f9d  mov     dword ptr [rsp+250h+SourceSize+4], r13d
0x180044fa2  lea     rax, [rsp+250h+hMem]
0x180044fa7  mov     [rsp+250h+var_1F8], rax
0x180044fac  mov     qword ptr [rsp+250h+var_1F0], r13
0x180044fb1  mov     [rsp+250h+var_1E8], 1
0x180044fb6  lea     rax, [rsp+250h+SourceSize+4]
0x180044fbb  mov     [rsp+250h+var_230], rax; int
0x180044fc0  lea     r9, [rsp+250h+var_1F0]; unsigned int
0x180044fc5  mov     edx, dword ptr [rsp+250h+SourceSize]; unsigned __int8 *
0x180044fc9  mov     rcx, [rsp+250h+var_1E0]; this
0x180044fce  call    ?ProtectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z; NgcUtils::ProtectData(uchar const *,ulong,ulong,uchar * *,ulong *)
0x180044fd3  mov     ebx, eax
0x180044fd5  lea     rcx, [rsp+250h+var_1F8]
0x180044fda  call    ??1?$out_param_t@V?$unique_ptr@U_CERT_PUBLIC_KEY_INFO@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CERT_PUBLIC_KEY_INFO,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180044fdf  test    ebx, ebx
0x180044fe1  jns     short loc_18004501D
0x180044fe3  mov     rcx, [rbp+158h]; this
0x180044fea  mov     r9d, ebx; char *
0x180044fed  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180044ff4  mov     edx, 46Eh; void *
0x180044ff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044ffe  nop
0x180044fff  mov     rcx, [rsp+250h+hMem]; hMem
0x180045004  mov     [rsp+250h+hMem], r13
0x180045009  test    rcx, rcx
0x18004500c  jz      loc_180045132
0x180045012  call    cs:__imp_LocalFree
0x180045018  jmp     loc_180045132
0x18004501d  lea     rcx, [rbp+150h+SystemTimeAsFileTime]; this
0x180045021  call    ??0RecoveryProtector@Properties@@QEAA@XZ; Properties::RecoveryProtector::RecoveryProtector(void)
0x180045026  nop
0x180045027  mov     rax, [rdi]
0x18004502a  mov     rcx, rdi
0x18004502d  mov     rax, [rax+58h]
0x180045031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045036  mov     edx, eax
0x180045038  lea     r8, [rbp+150h+var_1B0]
0x18004503c  lea     rcx, [rdi+8]
0x180045040  call    ?ExportSecretStore@NgcIsoTrustlet@@YAJAEBU_GUID@@W4NgcCtnrProtectorId@@PEAUSecretStore@Properties@@@Z; NgcIsoTrustlet::ExportSecretStore(_GUID const &,NgcCtnrProtectorId,Properties::SecretStore *)
0x180045045  mov     ebx, eax
0x180045047  test    eax, eax
0x180045049  jns     short loc_180045072
0x18004504b  mov     rcx, [rbp+158h]; this
0x180045052  mov     r9d, eax; char *
0x180045055  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18004505c  mov     edx, 475h; void *
0x180045061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045066  nop
0x180045067  lea     rcx, [rbp+150h+SystemTimeAsFileTime]; this
0x18004506b  call    ??1RecoveryProtector@Properties@@QEAA@XZ; Properties::RecoveryProtector::~RecoveryProtector(void)
0x180045070  jmp     short loc_180044FFF
0x180045072  lea     rcx, [rbp+150h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180045076  call    cs:__imp_GetSystemTimeAsFileTime
0x18004507c  lea     rcx, [rdi+18h]
0x180045080  lea     rdx, [rbp+150h+SystemTimeAsFileTime]
0x180045084  call    ??4RecoveryProtector@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::RecoveryProtector::operator=(Properties::RecoveryProtector &&)
0x180045089  mov     [rsp+250h+var_200], r13
0x18004508e  lea     rax, [rsp+250h+var_200]
0x180045093  mov     [rsp+250h+var_1F8], rax
0x180045098  mov     qword ptr [rsp+250h+var_1F0], r13
0x18004509d  mov     [rsp+250h+var_1E8], 1
0x1800450a2  mov     edi, dword ptr [rsp+250h+SourceSize+4]
0x1800450a6  mov     edx, edi; SourceSize
0x1800450a8  lea     r8, [rsp+250h+var_1F0]; unsigned __int64
0x1800450ad  mov     rcx, [rsp+250h+hMem]; this
0x1800450b2  call    ?CoMemAllocCopy@NgcUtils@@YAJPEBX_KPEAPEAX@Z; NgcUtils::CoMemAllocCopy(void const *,unsigned __int64,void * *)
0x1800450b7  mov     ebx, eax
0x1800450b9  lea     rcx, [rsp+250h+var_1F8]
0x1800450be  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800450c3  test    ebx, ebx
0x1800450c5  jns     short loc_180045100
0x1800450c7  mov     rcx, [rbp+158h]; this
0x1800450ce  mov     r9d, ebx; char *
0x1800450d1  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800450d8  mov     edx, 47Fh; void *
0x1800450dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800450e2  mov     rcx, [rsp+250h+var_200]; pv
0x1800450e7  mov     [rsp+250h+var_200], r13
0x1800450ec  test    rcx, rcx
0x1800450ef  jz      loc_180045067
0x1800450f5  call    cs:__imp_CoTaskMemFree
0x1800450fb  jmp     loc_180045067
0x180045100  mov     rax, [rsp+250h+var_200]
0x180045105  mov     [rsi], rax
0x180045108  mov     [r14], edi
0x18004510b  mov     [rsp+250h+var_200], r13
0x180045110  lea     rcx, [rbp+150h+SystemTimeAsFileTime]; this
0x180045114  call    ??1RecoveryProtector@Properties@@QEAA@XZ; Properties::RecoveryProtector::~RecoveryProtector(void)
0x180045119  nop
0x18004511a  mov     rcx, [rsp+250h+hMem]; hMem
0x18004511f  mov     [rsp+250h+hMem], r13
0x180045124  test    rcx, rcx
0x180045127  jz      short loc_18004512F
0x180045129  call    cs:__imp_LocalFree
0x18004512f  mov     ebx, r13d
0x180045132  lea     rcx, [rsp+250h+var_1E0]
0x180045137  call    ??1?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>::~unique_ptr<uchar,wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>(void)
0x18004513c  mov     eax, ebx
0x18004513e  mov     rcx, [rbp+150h+var_40]
0x180045145  xor     rcx, rsp; StackCookie
0x180045148  call    __security_check_cookie
0x18004514d  mov     rbx, [rsp+250h+arg_18]
0x180045155  add     rsp, 220h
0x18004515c  pop     r15
0x18004515e  pop     r14
0x180045160  pop     r13
0x180045162  pop     r12
0x180045164  pop     rdi
0x180045165  pop     rsi
0x180045166  pop     rbp
0x180045167  retn
```
