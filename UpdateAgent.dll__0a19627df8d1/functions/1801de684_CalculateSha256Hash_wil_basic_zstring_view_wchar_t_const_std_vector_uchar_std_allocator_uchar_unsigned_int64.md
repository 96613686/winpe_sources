# CalculateSha256Hash(wil::basic_zstring_view<wchar_t> const &,std::vector<uchar,std::allocator<uchar>> *,unsigned __int64 *)

- ea: `0x1801de684`
- end: `0x1801de99c`
- name: `?CalculateSha256Hash@@YAJAEBV?$basic_zstring_view@_W@wil@@PEAV?$vector@EV?$allocator@E@std@@@std@@PEA_K@Z`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180220914`

## callees

- `0x1800059d0`
- `0x18000c4c4`
- `0x18000dd74`
- `0x18008b38c`
- `0x18008b3bc`
- `0x1801de268`
- `0x1801de684`
- `0x1801e0318`
- `0x1801e3c10`
- `0x1801e4504`
- `0x1801e46a0`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x1801de7f0`
- `bcrypt!BCryptCreateHash` at `0x1801de7f0`
- `bcrypt!BCryptHashData` at `0x1801de847`
- `bcrypt!BCryptHashData` at `0x1801de847`
- `bcrypt!BCryptDestroyHash` at `0x1801de776`
- `bcrypt!BCryptDestroyHash` at `0x1801de8b8`
- `bcrypt!BCryptDestroyHash` at `0x1801de903`
- `bcrypt!BCryptDestroyHash` at `0x1801de952`
- `bcrypt!BCryptDestroyHash` at `0x1801de776`
- `bcrypt!BCryptDestroyHash` at `0x1801de8b8`
- `bcrypt!BCryptDestroyHash` at `0x1801de903`
- `bcrypt!BCryptDestroyHash` at `0x1801de952`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801de8d0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801de91b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801de96f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801de8d0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801de91b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801de96f`
- `bcrypt!BCryptFinishHash` at `0x1801de881`
- `bcrypt!BCryptFinishHash` at `0x1801de881`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801de79d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1801de79d`

## string_xrefs

- `0x1801de723`: `Failed to open {}`
- `0x1801de7b2`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x1801de937`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CalculateSha256Hash(__int64 a1, __int64 a2, unsigned __int64 *a3)
{
  unsigned int v6; // edx
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  int v9; // eax
  unsigned int v10; // ebx
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // edx
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  int v17; // r15d
  int pbSecret; // [rsp+20h] [rbp-89h]
  int pbSecreta; // [rsp+20h] [rbp-89h]
  _QWORD v21[2]; // [rsp+40h] [rbp-69h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp-59h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-51h] BYREF
  int v24; // [rsp+60h] [rbp-49h] BYREF
  _OWORD v25[2]; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int64 v26; // [rsp+90h] [rbp-19h]
  ULONG cbInput[2]; // [rsp+98h] [rbp-11h]
  __int128 v28; // [rsp+A0h] [rbp-9h]
  PUCHAR pbInput; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v21[1] = -2;
  phAlgorithm = 0;
  hHash = 0;
  if ( !*(_QWORD *)(a1 + 8) || !a2 )
  {
    v10 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1E,
      (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
      (const char *)0x80004003LL,
      pbSecret);
    return v10;
  }
  GetCanonicalUNCPath(v25, (LPCWSTR *)a1);
  v26 = 0;
  *(_QWORD *)cbInput = 0;
  v28 = 0;
  pbInput = 0;
  v9 = CMappedFile::Open((CMappedFile *)v25, v6, v7, v8, pbSecret);
  v10 = v9;
  if ( v9 < 0 )
  {
    v24 = v9;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to open {}",
        a1);
      v21[0] = &v24;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v21);
    }
    goto LABEL_6;
  }
  v11 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( v11 < 0 )
  {
    v12 = 2863;
LABEL_11:
    v10 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v12,
            (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
            (const char *)(unsigned int)v11,
            pbSecreta);
LABEL_6:
    CMappedFile::~CMappedFile((CMappedFile *)v25);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    return v10;
  }
  v11 = BCryptCreateHash(phAlgorithm, &hHash, 0, 0, 0, 0, 0);
  if ( v11 < 0 )
  {
    v12 = 2865;
    goto LABEL_11;
  }
  v14 = 0;
  v15 = v26;
  if ( v26 )
  {
    while ( 1 )
    {
      v16 = v15 - v14;
      if ( v16 > 0x6400000 )
        v16 = 104857600;
      v17 = CMappedFile::OpenNewView((CMappedFile *)v25, v13, v14, v16);
      if ( v17 < 0 )
        break;
      v11 = BCryptHashData(hHash, pbInput, cbInput[0], 0);
      if ( v11 < 0 )
      {
        v12 = 2878;
        goto LABEL_11;
      }
      v14 += v16;
      v15 = v26;
      if ( v14 >= v26 )
        goto LABEL_20;
    }
    CMappedFile::~CMappedFile((CMappedFile *)v25);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    return (unsigned int)v17;
  }
  else
  {
LABEL_20:
    std::vector<unsigned char>::resize(a2, 32);
    v11 = BCryptFinishHash(hHash, *(PUCHAR *)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2, 0);
    if ( v11 < 0 )
    {
      v12 = 2884;
      goto LABEL_11;
    }
    if ( a3 )
      *a3 = v26;
    CMappedFile::~CMappedFile((CMappedFile *)v25);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( phAlgorithm )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x1801de684  push    rbp
0x1801de686  push    rbx
0x1801de687  push    rsi
0x1801de688  push    rdi
0x1801de689  push    r13
0x1801de68b  push    r14
0x1801de68d  push    r15
0x1801de68f  lea     rbp, [rsp-27h]
0x1801de694  sub     rsp, 0D0h
0x1801de69b  mov     [rbp+57h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1801de6a3  mov     rax, cs:__security_cookie
0x1801de6aa  xor     rax, rsp
0x1801de6ad  mov     [rbp+57h+var_40], rax
0x1801de6b1  mov     rsi, r8
0x1801de6b4  mov     r14, rdx
0x1801de6b7  mov     rdi, rcx
0x1801de6ba  mov     [rbp+57h+phAlgorithm], 0
0x1801de6c2  mov     [rbp+57h+hHash], 0
0x1801de6ca  cmp     qword ptr [rcx+8], 0
0x1801de6cf  jz      loc_1801DE92B
0x1801de6d5  test    rdx, rdx
0x1801de6d8  jz      loc_1801DE92B
0x1801de6de  mov     rdx, rcx
0x1801de6e1  lea     rcx, [rbp+57h+var_90]
0x1801de6e5  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x1801de6ea  xor     eax, eax
0x1801de6ec  mov     [rbp+57h+var_70], rax
0x1801de6f0  mov     qword ptr [rbp+57h+cbInput], rax
0x1801de6f4  xorps   xmm0, xmm0
0x1801de6f7  movdqa  [rbp+57h+var_60], xmm0
0x1801de6fc  mov     [rbp+57h+pbInput], rax
0x1801de700  lea     rcx, [rbp+57h+var_90]; this
0x1801de704  call    ?Open@CMappedFile@@QEAAJKKK_N@Z; CMappedFile::Open(ulong,ulong,ulong,bool)
0x1801de709  mov     ebx, eax
0x1801de70b  test    eax, eax
0x1801de70d  jns     short loc_1801DE78C
0x1801de70f  mov     [rbp+57h+var_A0], eax
0x1801de712  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801de719  test    rcx, rcx
0x1801de71c  jz      short loc_1801DE763
0x1801de71e  mov     [rsp+100h+pbSecret], rdi
0x1801de723  lea     r9, aFailedToOpen; "Failed to open {}"
0x1801de72a  mov     edi, 3
0x1801de72f  mov     r8d, edi
0x1801de732  xor     edx, edx
0x1801de734  call    ??$LogNumObjects@V?$basic_zstring_view@_W@wil@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_zstring_view@_W@wil@@@Z; LogAdapter::Logger::LogNumObjects<wil::basic_zstring_view<wchar_t>>(bool,LogAdapter::LogLevel,char const * const,wil::basic_zstring_view<wchar_t> const &)
0x1801de739  lea     rax, [rbp+57h+var_A0]
0x1801de73d  mov     [rbp+57h+var_C0], rax
0x1801de741  lea     rax, [rbp+57h+var_C0]
0x1801de745  mov     [rsp+100h+pbSecret], rax
0x1801de74a  lea     r9, asc_1802C6678; ": {}"
0x1801de751  mov     r8d, edi
0x1801de754  mov     dl, 1
0x1801de756  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801de75d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801de762  nop
0x1801de763  lea     rcx, [rbp+57h+var_90]; this
0x1801de767  call    ??1CMappedFile@@QEAA@XZ; CMappedFile::~CMappedFile(void)
0x1801de76c  nop
0x1801de76d  mov     rcx, [rbp+57h+hHash]; hHash
0x1801de771  test    rcx, rcx
0x1801de774  jz      short loc_1801DE783
0x1801de776  call    cs:__imp_BCryptDestroyHash
0x1801de77d  nop     dword ptr [rax+rax+00h]
0x1801de782  nop
0x1801de783  mov     rcx, [rbp+57h+phAlgorithm]
0x1801de787  jmp     loc_1801DE968
0x1801de78c  xor     r9d, r9d; dwFlags
0x1801de78f  xor     r8d, r8d; pszImplementation
0x1801de792  lea     rdx, pszAlgId; "SHA256"
0x1801de799  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1801de79d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1801de7a4  nop     dword ptr [rax+rax+00h]
0x1801de7a9  test    eax, eax
0x1801de7ab  jns     short loc_1801DE7C9
0x1801de7ad  mov     edx, 0B2Fh; void *
0x1801de7b2  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801de7b9  mov     r9d, eax; char *
0x1801de7bc  mov     rcx, [rbp+5Fh]; this
0x1801de7c0  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801de7c5  mov     ebx, eax
0x1801de7c7  jmp     short loc_1801DE763
0x1801de7c9  mov     [rsp+100h+dwFlags], 0; dwFlags
0x1801de7d1  mov     [rsp+100h+cbSecret], 0; cbSecret
0x1801de7d9  mov     [rsp+100h+pbSecret], 0; pbSecret
0x1801de7e2  xor     r9d, r9d; cbHashObject
0x1801de7e5  xor     r8d, r8d; pbHashObject
0x1801de7e8  lea     rdx, [rbp+57h+hHash]; phHash
0x1801de7ec  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1801de7f0  call    cs:__imp_BCryptCreateHash
0x1801de7f7  nop     dword ptr [rax+rax+00h]
0x1801de7fc  test    eax, eax
0x1801de7fe  jns     short loc_1801DE807
0x1801de800  mov     edx, 0B31h
0x1801de805  jmp     short loc_1801DE7B2
0x1801de807  xor     edi, edi
0x1801de809  mov     rbx, [rbp+57h+var_70]
0x1801de80d  test    rbx, rbx
0x1801de810  jz      short loc_1801DE863
0x1801de812  mov     r13d, 6400000h
0x1801de818  sub     rbx, rdi
0x1801de81b  cmp     rbx, r13
0x1801de81e  cmova   rbx, r13
0x1801de822  mov     r9, rbx; unsigned __int64
0x1801de825  mov     r8, rdi; unsigned __int64
0x1801de828  lea     rcx, [rbp+57h+var_90]; this
0x1801de82c  call    ?OpenNewView@CMappedFile@@QEAAJK_K0@Z; CMappedFile::OpenNewView(ulong,unsigned __int64,unsigned __int64)
0x1801de831  mov     r15d, eax
0x1801de834  test    eax, eax
0x1801de836  js      short loc_1801DE8A5
0x1801de838  xor     r9d, r9d; dwFlags
0x1801de83b  mov     r8d, [rbp+57h+cbInput]; cbInput
0x1801de83f  mov     rdx, [rbp+57h+pbInput]; pbInput
0x1801de843  mov     rcx, [rbp+57h+hHash]; hHash
0x1801de847  call    cs:__imp_BCryptHashData
0x1801de84e  nop     dword ptr [rax+rax+00h]
0x1801de853  test    eax, eax
0x1801de855  js      short loc_1801DE89B
0x1801de857  add     rdi, rbx
0x1801de85a  mov     rbx, [rbp+57h+var_70]
0x1801de85e  cmp     rdi, rbx
0x1801de861  jb      short loc_1801DE818
0x1801de863  mov     edx, 20h ; ' '
0x1801de868  mov     rcx, r14
0x1801de86b  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1801de870  mov     r8d, [r14+8]
0x1801de874  sub     r8d, [r14]; cbOutput
0x1801de877  xor     r9d, r9d; dwFlags
0x1801de87a  mov     rdx, [r14]; pbOutput
0x1801de87d  mov     rcx, [rbp+57h+hHash]; hHash
0x1801de881  call    cs:__imp_BCryptFinishHash
0x1801de888  nop     dword ptr [rax+rax+00h]
0x1801de88d  test    eax, eax
0x1801de88f  jns     short loc_1801DE8E4
0x1801de891  mov     edx, 0B44h
0x1801de896  jmp     loc_1801DE7B2
0x1801de89b  mov     edx, 0B3Eh
0x1801de8a0  jmp     loc_1801DE7B2
0x1801de8a5  lea     rcx, [rbp+57h+var_90]; this
0x1801de8a9  call    ??1CMappedFile@@QEAA@XZ; CMappedFile::~CMappedFile(void)
0x1801de8ae  nop
0x1801de8af  mov     rcx, [rbp+57h+hHash]; hHash
0x1801de8b3  test    rcx, rcx
0x1801de8b6  jz      short loc_1801DE8C5
0x1801de8b8  call    cs:__imp_BCryptDestroyHash
0x1801de8bf  nop     dword ptr [rax+rax+00h]
0x1801de8c4  nop
0x1801de8c5  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1801de8c9  test    rcx, rcx
0x1801de8cc  jz      short loc_1801DE8DC
0x1801de8ce  xor     edx, edx; dwFlags
0x1801de8d0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801de8d7  nop     dword ptr [rax+rax+00h]
0x1801de8dc  mov     eax, r15d
0x1801de8df  jmp     loc_1801DE97D
0x1801de8e4  test    rsi, rsi
0x1801de8e7  jz      short loc_1801DE8F0
0x1801de8e9  mov     rax, [rbp+57h+var_70]
0x1801de8ed  mov     [rsi], rax
0x1801de8f0  lea     rcx, [rbp+57h+var_90]; this
0x1801de8f4  call    ??1CMappedFile@@QEAA@XZ; CMappedFile::~CMappedFile(void)
0x1801de8f9  nop
0x1801de8fa  mov     rcx, [rbp+57h+hHash]; hHash
0x1801de8fe  test    rcx, rcx
0x1801de901  jz      short loc_1801DE910
0x1801de903  call    cs:__imp_BCryptDestroyHash
0x1801de90a  nop     dword ptr [rax+rax+00h]
0x1801de90f  nop
0x1801de910  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1801de914  test    rcx, rcx
0x1801de917  jz      short loc_1801DE927
0x1801de919  xor     edx, edx; dwFlags
0x1801de91b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801de922  nop     dword ptr [rax+rax+00h]
0x1801de927  xor     eax, eax
0x1801de929  jmp     short loc_1801DE97D
0x1801de92b  mov     rcx, [rbp+5Fh]; this
0x1801de92f  mov     ebx, 80004003h
0x1801de934  mov     r9d, ebx; char *
0x1801de937  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1801de93e  mov     edx, 0B1Eh; void *
0x1801de943  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801de948  nop
0x1801de949  mov     rcx, [rbp+57h+hHash]; hHash
0x1801de94d  test    rcx, rcx
0x1801de950  jz      short loc_1801DE95F
0x1801de952  call    cs:__imp_BCryptDestroyHash
0x1801de959  nop     dword ptr [rax+rax+00h]
0x1801de95e  nop
0x1801de95f  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1801de963  test    rcx, rcx
0x1801de966  jz      short loc_1801DE97B
0x1801de968  test    rcx, rcx
0x1801de96b  jz      short loc_1801DE97B
0x1801de96d  xor     edx, edx; dwFlags
0x1801de96f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801de976  nop     dword ptr [rax+rax+00h]
0x1801de97b  mov     eax, ebx
0x1801de97d  mov     rcx, [rbp+57h+var_40]
0x1801de981  xor     rcx, rsp; StackCookie
0x1801de984  call    __security_check_cookie
0x1801de989  add     rsp, 0D0h
0x1801de990  pop     r15
0x1801de992  pop     r14
0x1801de994  pop     r13
0x1801de996  pop     rdi
0x1801de997  pop     rsi
0x1801de998  pop     rbx
0x1801de999  pop     rbp
0x1801de99a  retn
```
