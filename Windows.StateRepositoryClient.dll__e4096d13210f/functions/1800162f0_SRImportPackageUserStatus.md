# SRImportPackageUserStatus

- ea: `0x1800162f0`
- end: `0x1800164a1`
- name: `SRImportPackageUserStatus`
- size: `433`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PCWSTR)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002980`
- `0x1800075e4`
- `0x180008b00`
- `0x180008bd4`
- `0x18000956c`
- `0x18000b30c`
- `0x18000b348`
- `0x18000c408`
- `0x1800162f0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800163dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016427`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800163dc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800163f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001643b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800163f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001643b`

## pseudocode

```c
__int64 __fastcall SRImportPackageUserStatus(PCWSTR sourceString, PCWSTR a2, __int64 a3, int a4)
{
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // ebx
  __int64 *v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rsi
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  __int64 (__fastcall *v17)(__int64, HSTRING, HSTRING, __int64); // r15
  const ULONG_PTR *v18; // r9
  HSTRING v19; // rdi
  const ULONG_PTR *v20; // r9
  int v22; // [rsp+20h] [rbp-59h]
  UINT32 length; // [rsp+30h] [rbp-49h] BYREF
  int v24; // [rsp+34h] [rbp-45h] BYREF
  __int64 v25; // [rsp+38h] [rbp-41h] BYREF
  HSTRING v26; // [rsp+40h] [rbp-39h] BYREF
  HSTRING_HEADER v27; // [rsp+48h] [rbp-31h] BYREF
  HSTRING string; // [rsp+60h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v24 = -2147221008;
  v8 = Common::AutoWinRTInitialize::Initialize(&v24);
  v10 = v8;
  if ( v8 >= 0 )
  {
    v25 = 0;
    v11 = (__int64 *)Windows::Internal::StringReference::StringReference(&v26, (const unsigned __int16 (*)[62])v9);
    v12 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>(
            *v11,
            &v25);
    v10 = v12;
    if ( v12 >= 0 )
    {
      v14 = v25;
      v15 = -1;
      length = 0;
      v16 = -1;
      v17 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64))(*(_QWORD *)v25 + 304LL);
      do
        ++v16;
      while ( a2[v16] );
      if ( (int)ULongLongToUInt(v16, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, v18);
      WindowsCreateStringReference(a2, length, &hstringHeader, &string);
      v19 = string;
      length = 0;
      do
        ++v15;
      while ( sourceString[v15] );
      if ( (int)ULongLongToUInt(v15, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, v20);
      WindowsCreateStringReference(sourceString, length, &v27, &v26);
      v22 = a4;
      v12 = v17(v14, v26, v19, a3);
      v10 = v12;
      if ( v12 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v25);
        v10 = 0;
        goto LABEL_17;
      }
      v13 = 216;
    }
    else
    {
      v13 = 215;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)v12,
      v22);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v25);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset_status.cpp",
      (const char *)(unsigned int)v8,
      v22);
  }
LABEL_17:
  Common::AutoWinRTInitialize::~AutoWinRTInitialize((Common::AutoWinRTInitialize *)&v24);
  return v10;
}

```

## disassembly

```asm
0x1800162f0  push    rbp
0x1800162f2  push    rbx
0x1800162f3  push    rsi
0x1800162f4  push    rdi
0x1800162f5  push    r12
0x1800162f7  push    r13
0x1800162f9  push    r14
0x1800162fb  push    r15
0x1800162fd  lea     rbp, [rsp-1Fh]
0x180016302  sub     rsp, 98h
0x180016309  mov     rax, cs:__security_cookie
0x180016310  xor     rax, rsp
0x180016313  mov     [rbp+57h+var_50], rax
0x180016317  mov     r14, rcx
0x18001631a  mov     [rbp+57h+var_9C], 800401F0h
0x180016321  lea     rcx, [rbp+57h+var_9C]
0x180016325  mov     r13, r9
0x180016328  mov     r12, r8
0x18001632b  mov     rdi, rdx
0x18001632e  call    ?Initialize@AutoWinRTInitialize@Common@@QEAAJW4RO_INIT_TYPE@@@Z; Common::AutoWinRTInitialize::Initialize(RO_INIT_TYPE)
0x180016333  xor     esi, esi
0x180016335  mov     ebx, eax
0x180016337  test    eax, eax
0x180016339  jns     short loc_180016358
0x18001633b  mov     rcx, [rbp+5Fh]; this
0x18001633f  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180016346  mov     r9d, eax; char *
0x180016349  mov     edx, 0D4h; void *
0x18001634e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016353  jmp     loc_180016476
0x180016358  lea     rcx, [rbp+57h+var_90]; string
0x18001635c  mov     [rbp+57h+var_98], rsi
0x180016360  call    ??$?0$0DO@@StringReference@Internal@Windows@@QEAA@AEAY0DO@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[62])
0x180016365  lea     rdx, [rbp+57h+var_98]
0x180016369  mov     rcx, [rax]
0x18001636c  call    ??$ActivateInstance@V?$ComPtr@UIRepositoryManager@Management@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRepositoryManager@Management@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>)
0x180016371  mov     ebx, eax
0x180016373  test    eax, eax
0x180016375  jns     short loc_18001639D
0x180016377  mov     edx, 0D7h; void *
0x18001637c  mov     rcx, [rbp+5Fh]; this
0x180016380  lea     r8, aOnecoreBaseApp_32; "onecore\\base\\appmodel\\staterepositor"...
0x180016387  mov     r9d, eax; char *
0x18001638a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001638f  lea     rcx, [rbp+57h+var_98]
0x180016393  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180016398  jmp     loc_180016476
0x18001639d  mov     rsi, [rbp+57h+var_98]
0x1800163a1  xor     r9d, r9d
0x1800163a4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800163a8  mov     [rbp+57h+length], r9d
0x1800163ac  mov     rcx, rbx
0x1800163af  mov     rax, [rsi]
0x1800163b2  mov     r15, [rax+130h]
0x1800163b9  inc     rcx; unsigned __int64
0x1800163bc  cmp     [rdi+rcx*2], r9w
0x1800163c1  jnz     short loc_1800163B9
0x1800163c3  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800163c7  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800163cc  test    eax, eax
0x1800163ce  jns     short loc_1800163E2
0x1800163d0  xor     r8d, r8d; nNumberOfArguments
0x1800163d3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800163d8  lea     edx, [r8+1]; dwExceptionFlags
0x1800163dc  call    cs:__imp_RaiseException
0x1800163e2  mov     edx, [rbp+57h+length]; length
0x1800163e5  lea     r9, [rbp+57h+string]; string
0x1800163e9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800163ed  mov     rcx, rdi; sourceString
0x1800163f0  call    cs:__imp_WindowsCreateStringReference
0x1800163f6  mov     rdi, [rbp+57h+string]
0x1800163fa  xor     r9d, r9d
0x1800163fd  mov     [rbp+57h+length], r9d
0x180016401  inc     rbx
0x180016404  cmp     [r14+rbx*2], r9w
0x180016409  jnz     short loc_180016401
0x18001640b  lea     rdx, [rbp+57h+length]; unsigned int *
0x18001640f  mov     rcx, rbx; unsigned __int64
0x180016412  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180016417  test    eax, eax
0x180016419  jns     short loc_18001642D
0x18001641b  xor     r8d, r8d; nNumberOfArguments
0x18001641e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180016423  lea     edx, [r8+1]; dwExceptionFlags
0x180016427  call    cs:__imp_RaiseException
0x18001642d  mov     edx, [rbp+57h+length]; length
0x180016430  lea     r9, [rbp+57h+var_90]; string
0x180016434  lea     r8, [rbp+57h+var_88]; hstringHeader
0x180016438  mov     rcx, r14; sourceString
0x18001643b  call    cs:__imp_WindowsCreateStringReference
0x180016441  mov     rdx, [rbp+57h+var_90]
0x180016445  mov     r9, r12
0x180016448  mov     r8, rdi
0x18001644b  mov     qword ptr [rsp+0D0h+var_B0], r13
0x180016450  mov     rcx, rsi
0x180016453  mov     rax, r15
0x180016456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001645b  mov     ebx, eax
0x18001645d  test    eax, eax
0x18001645f  jns     short loc_18001646B
0x180016461  mov     edx, 0D8h
0x180016466  jmp     loc_18001637C
0x18001646b  lea     rcx, [rbp+57h+var_98]
0x18001646f  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x180016474  xor     ebx, ebx
0x180016476  lea     rcx, [rbp+57h+var_9C]; this
0x18001647a  call    ??1AutoWinRTInitialize@Common@@QEAA@XZ; Common::AutoWinRTInitialize::~AutoWinRTInitialize(void)
0x18001647f  mov     eax, ebx
0x180016481  mov     rcx, [rbp+57h+var_50]
0x180016485  xor     rcx, rsp; StackCookie
0x180016488  call    __security_check_cookie
0x18001648d  add     rsp, 98h
0x180016494  pop     r15
0x180016496  pop     r14
0x180016498  pop     r13
0x18001649a  pop     r12
0x18001649c  pop     rdi
0x18001649d  pop     rsi
0x18001649e  pop     rbx
0x18001649f  pop     rbp
0x1800164a0  retn
```
