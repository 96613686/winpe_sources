# ApplicationTracker::GetAppListByCategoryAndEventTypes(ushort const *,utl::vector<_SebiEventType,utl::allocator<_SebiEventType>> const &,utl::vector<_ApplicationPackageInfo,utl::allocator<_ApplicationPackageInfo>> *)

- ea: `0x180050010`
- end: `0x1800505b7`
- name: `?GetAppListByCategoryAndEventTypes@ApplicationTracker@@KAJPEBGAEBV?$vector@W4_SebiEventType@@V?$allocator@W4_SebiEventType@@@utl@@@utl@@PEAV?$vector@U_ApplicationPackageInfo@@V?$allocator@U_ApplicationPackageInfo@@@utl@@@3@@Z`
- size: `1447`
- prototype: `__int64 __fastcall(PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800797c0`
- `0x18007b460`

## callees

- `0x180006e94`
- `0x180050010`
- `0x180050d70`
- `0x180050e58`
- `0x180050fd8`
- `0x180051410`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005007f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050184`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005007f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050184`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800500b4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800500b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800502d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800502d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800502af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005047d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005053c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800502af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050383`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005047d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005053c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050199`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180050199`
- `PhoneUtil!GetRpcClientUser` at `0x180050105`
- `PhoneUtil!GetRpcClientUser` at `0x180050105`

## string_xrefs

- `0x18005005b`: `Windows.Internal.StateRepository.ApplicationExtension`

## pseudocode

```c
__int64 __fastcall ApplicationTracker::GetAppListByCategoryAndEventTypes(PCWSTR sourceString)
{
  __int64 v2; // rcx
  HSTRING v3; // rbx
  int ActivationFactory; // eax
  BackTraceCollection *v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // r8
  __int64 v8; // rcx
  int RpcClientUser; // eax
  BackTraceCollection *v11; // rcx
  __int64 v12; // r8
  struct Windows::Internal::StateRepository::IUser *v13; // rcx
  __int64 v14; // rdi
  unsigned __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, struct Windows::Internal::StateRepository::IUser *, HSTRING, __int64 *); // r14
  int v17; // eax
  BackTraceCollection *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  BackTraceCollection *v23; // rcx
  unsigned int v24; // esi
  int v25; // eax
  BackTraceCollection *v26; // rcx
  int v27; // eax
  BackTraceCollection *v28; // rcx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, HSTRING *); // rbx
  int v31; // eax
  BackTraceCollection *v32; // rcx
  const WCHAR *StringRawBuffer; // rdi
  int IsRegisteredByApp; // eax
  BackTraceCollection *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  struct Windows::Internal::StateRepository::IUser *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // r8
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rcx
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  struct Windows::Internal::StateRepository::IUser *v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h] BYREF
  HSTRING v54; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v55; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v56[272]; // [rsp+90h] [rbp-70h] BYREF

  v49 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.ApplicationExtension",
         0x35u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = v49;
  v3 = string;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  ActivationFactory = RoGetActivationFactory(v3, &GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12, &v49);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    BackTraceCollection::Capture(v5, ActivationFactory);
    Log_HREvent_10(v6, 1, v7, 135);
LABEL_7:
    v8 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (**)(void))(*(_QWORD *)v8 + 16LL))();
    }
    return v6;
  }
  v50 = 0;
  RpcClientUser = GetRpcClientUser(&v50);
  v6 = RpcClientUser;
  if ( RpcClientUser < 0 )
  {
    BackTraceCollection::Capture(v11, RpcClientUser);
    Log_HREvent_10(v6, 1, v12, 138);
LABEL_12:
    v13 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IUser *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_7;
  }
  v14 = v49;
  v15 = -1;
  v51 = 0;
  v16 = *(__int64 (__fastcall **)(__int64, struct Windows::Internal::StateRepository::IUser *, HSTRING, __int64 *))(*(_QWORD *)v49 + 160LL);
  do
    ++v15;
  while ( sourceString[v15] );
  if ( v15 > 0xFFFFFFFF )
  {
    LODWORD(v15) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(sourceString, v15, &hstringHeader, &string);
  v17 = v16(v14, v50, string, &v51);
  v6 = v17;
  if ( v17 < 0 )
  {
    BackTraceCollection::Capture(v18, v17);
    v20 = 141;
LABEL_20:
    Log_HREvent_10(v6, 1, v19, v20);
LABEL_21:
    v21 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_12;
  }
  v55 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v51 + 56LL))(v51, &v55);
  v6 = v22;
  if ( v22 < 0 )
  {
    BackTraceCollection::Capture(v23, v22);
    v20 = 144;
    goto LABEL_20;
  }
  memset_0(v56, 0, 0x106u);
  v24 = 0;
  if ( v55 )
  {
    while ( 1 )
    {
      v52 = 0;
      v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v51 + 48LL))(v51, v24, &v52);
      v6 = v25;
      if ( v25 < 0 )
      {
        BackTraceCollection::Capture(v26, v25);
        Log_HREvent_10(v6, 1, v45, 150);
        goto LABEL_49;
      }
      v53 = 0;
      v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v52 + 72LL))(v52, &v53);
      v6 = v27;
      if ( v27 < 0 )
        break;
      v29 = v53;
      v54 = 0;
      v30 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v53 + 232LL);
      WindowsDeleteString(0);
      v54 = 0;
      v31 = v30(v29, &v54);
      v6 = v31;
      if ( v31 < 0 )
      {
        BackTraceCollection::Capture(v32, v31);
        v42 = 156;
        goto LABEL_44;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(v54, 0);
      IsRegisteredByApp = ApplicationTracker::IsRegisteredByApp(StringRawBuffer);
      v6 = IsRegisteredByApp;
      if ( IsRegisteredByApp < 0 )
      {
        BackTraceCollection::Capture(v35, IsRegisteredByApp);
        v42 = 160;
LABEL_44:
        Log_HREvent_10(v6, 1, v41, v42);
        WindowsDeleteString(v54);
        v54 = 0;
        goto LABEL_46;
      }
      WindowsDeleteString(v54);
      v36 = v53;
      v54 = 0;
      if ( v53 )
      {
        v53 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      v37 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      if ( ++v24 >= v55 )
        goto LABEL_35;
    }
    BackTraceCollection::Capture(v28, v27);
    Log_HREvent_10(v6, 1, v43, 153);
LABEL_46:
    v44 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
LABEL_49:
    v46 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    goto LABEL_21;
  }
LABEL_35:
  v38 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v39 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IUser *))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  return 0;
}

```

## disassembly

```asm
0x180050010  mov     [rsp-8+arg_18], rbx
0x180050015  push    rbp
0x180050016  push    rsi
0x180050017  push    rdi
0x180050018  push    r12
0x18005001a  push    r13
0x18005001c  push    r14
0x18005001e  push    r15
0x180050020  lea     rbp, [rsp-0B0h]
0x180050028  sub     rsp, 1B0h
0x18005002f  mov     rax, cs:__security_cookie
0x180050036  xor     rax, rsp
0x180050039  mov     [rbp+0E0h+var_40], rax
0x180050040  xor     r13d, r13d
0x180050043  lea     r9, [rsp+1E0h+string]; string
0x180050048  mov     r15, r8
0x18005004b  mov     [rsp+1E0h+var_188], r13
0x180050050  mov     r12, rdx
0x180050053  lea     r8, [rsp+1E0h+hstringHeader]; hstringHeader
0x180050058  mov     rsi, rcx
0x18005005b  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationExtension@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x180050062  lea     edx, [r13+35h]; length
0x180050066  call    cs:__imp_WindowsCreateStringReference
0x18005006c  test    eax, eax
0x18005006e  jns     short loc_180050085
0x180050070  xor     r9d, r9d; lpArguments
0x180050073  lea     edx, [r13+1]; dwExceptionFlags
0x180050077  xor     r8d, r8d; nNumberOfArguments
0x18005007a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005007f  call    cs:__imp_RaiseException
0x180050085  mov     rcx, [rsp+1E0h+var_188]
0x18005008a  mov     rbx, [rsp+1E0h+string]
0x18005008f  test    rcx, rcx
0x180050092  jz      short loc_1800500A5
0x180050094  mov     [rsp+1E0h+var_188], r13
0x180050099  mov     rax, [rcx]
0x18005009c  mov     rax, [rax+10h]
0x1800500a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500a5  lea     r8, [rsp+1E0h+var_188]
0x1800500aa  mov     rcx, rbx
0x1800500ad  lea     rdx, _GUID_b94b62a2_4012_4b7e_a395_f21cc665fd12
0x1800500b4  call    cs:__imp_RoGetActivationFactory
0x1800500ba  mov     ebx, eax
0x1800500bc  test    eax, eax
0x1800500be  jns     short loc_1800500FB
0x1800500c0  mov     edx, eax; int
0x1800500c2  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800500c7  mov     edx, 1
0x1800500cc  mov     r9d, 87h
0x1800500d2  mov     ecx, ebx
0x1800500d4  call    Log_HREvent_10
0x1800500d9  mov     rcx, [rsp+1E0h+var_188]
0x1800500de  test    rcx, rcx
0x1800500e1  jz      short loc_1800500F4
0x1800500e3  mov     [rsp+1E0h+var_188], r13
0x1800500e8  mov     rax, [rcx]
0x1800500eb  mov     rax, [rax+10h]
0x1800500ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500f4  mov     eax, ebx
0x1800500f6  jmp     loc_180050422
0x1800500fb  lea     rcx, [rsp+1E0h+var_180]
0x180050100  mov     [rsp+1E0h+var_180], r13
0x180050105  call    cs:__imp_?GetRpcClientUser@@YAJPEAPEAUIUser@StateRepository@Internal@Windows@@@Z; GetRpcClientUser(Windows::Internal::StateRepository::IUser * *)
0x18005010b  mov     ebx, eax
0x18005010d  test    eax, eax
0x18005010f  jns     short loc_180050147
0x180050111  mov     edx, eax; int
0x180050113  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050118  mov     edx, 1
0x18005011d  mov     r9d, 8Ah
0x180050123  mov     ecx, ebx
0x180050125  call    Log_HREvent_10
0x18005012a  mov     rcx, [rsp+1E0h+var_180]
0x18005012f  test    rcx, rcx
0x180050132  jz      short loc_1800500D9
0x180050134  mov     [rsp+1E0h+var_180], r13
0x180050139  mov     rax, [rcx]
0x18005013c  mov     rax, [rax+10h]
0x180050140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050145  jmp     short loc_1800500D9
0x180050147  mov     rdi, [rsp+1E0h+var_188]
0x18005014c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180050150  mov     [rsp+1E0h+var_178], r13
0x180050155  mov     rax, [rdi]
0x180050158  mov     r14, [rax+0A0h]
0x18005015f  inc     rbx
0x180050162  cmp     [rsi+rbx*2], r13w
0x180050167  jnz     short loc_18005015F
0x180050169  mov     eax, 0FFFFFFFFh
0x18005016e  cmp     rbx, rax
0x180050171  jbe     short loc_18005018A
0x180050173  xor     r9d, r9d; lpArguments
0x180050176  xor     r8d, r8d; nNumberOfArguments
0x180050179  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005017e  mov     ebx, eax
0x180050180  lea     edx, [r9+1]; dwExceptionFlags
0x180050184  call    cs:__imp_RaiseException
0x18005018a  lea     r9, [rsp+1E0h+string]; string
0x18005018f  mov     edx, ebx; length
0x180050191  lea     r8, [rsp+1E0h+hstringHeader]; hstringHeader
0x180050196  mov     rcx, rsi; sourceString
0x180050199  call    cs:__imp_WindowsCreateStringReference
0x18005019f  mov     r8, [rsp+1E0h+string]
0x1800501a4  lea     r9, [rsp+1E0h+var_178]
0x1800501a9  mov     rdx, [rsp+1E0h+var_180]
0x1800501ae  mov     rcx, rdi
0x1800501b1  mov     rax, r14
0x1800501b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501b9  mov     ebx, eax
0x1800501bb  test    eax, eax
0x1800501bd  jns     short loc_1800501FC
0x1800501bf  mov     edx, eax; int
0x1800501c1  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800501c6  mov     r9d, 8Dh
0x1800501cc  mov     edx, 1
0x1800501d1  mov     ecx, ebx
0x1800501d3  call    Log_HREvent_10
0x1800501d8  mov     rcx, [rsp+1E0h+var_178]
0x1800501dd  test    rcx, rcx
0x1800501e0  jz      loc_18005012A
0x1800501e6  mov     [rsp+1E0h+var_178], r13
0x1800501eb  mov     rax, [rcx]
0x1800501ee  mov     rax, [rax+10h]
0x1800501f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501f7  jmp     loc_18005012A
0x1800501fc  mov     rcx, [rsp+1E0h+var_178]
0x180050201  lea     rdx, [rbp+0E0h+var_158]
0x180050205  mov     [rbp+0E0h+var_158], r13d
0x180050209  mov     rax, [rcx]
0x18005020c  mov     rax, [rax+38h]
0x180050210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050215  mov     ebx, eax
0x180050217  test    eax, eax
0x180050219  jns     short loc_18005022A
0x18005021b  mov     edx, eax; int
0x18005021d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050222  mov     r9d, 90h
0x180050228  jmp     short loc_1800501CC
0x18005022a  xor     edx, edx; Val
0x18005022c  lea     rcx, [rbp+0E0h+var_150]; void *
0x180050230  mov     r8d, 106h; Size
0x180050236  call    memset_0
0x18005023b  mov     esi, r13d
0x18005023e  cmp     [rbp+0E0h+var_158], r13d
0x180050242  jbe     loc_1800503CF
0x180050248  mov     r14d, 1
0x18005024e  mov     rcx, [rsp+1E0h+var_178]
0x180050253  lea     r8, [rsp+1E0h+var_170]
0x180050258  mov     [rsp+1E0h+var_170], r13
0x18005025d  mov     edx, esi
0x18005025f  mov     rax, [rcx]
0x180050262  mov     rax, [rax+30h]
0x180050266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005026b  mov     ebx, eax
0x18005026d  test    eax, eax
0x18005026f  js      loc_18005057C
0x180050275  mov     rcx, [rsp+1E0h+var_170]
0x18005027a  lea     rdx, [rsp+1E0h+var_168]
0x18005027f  mov     [rsp+1E0h+var_168], r13
0x180050284  mov     rax, [rcx]
0x180050287  mov     rax, [rax+48h]
0x18005028b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050290  mov     ebx, eax
0x180050292  test    eax, eax
0x180050294  js      loc_180050548
0x18005029a  mov     rdi, [rsp+1E0h+var_168]
0x18005029f  xor     ecx, ecx; string
0x1800502a1  mov     [rbp+0E0h+var_160], r13
0x1800502a5  mov     rax, [rdi]
0x1800502a8  mov     rbx, [rax+0E8h]
0x1800502af  call    cs:__imp_WindowsDeleteString
0x1800502b5  lea     rdx, [rbp+0E0h+var_160]
0x1800502b9  mov     [rbp+0E0h+var_160], r13
0x1800502bd  mov     rcx, rdi
0x1800502c0  mov     rax, rbx
0x1800502c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502c8  mov     ebx, eax
0x1800502ca  test    eax, eax
0x1800502cc  js      loc_180050521
0x1800502d2  mov     rcx, [rbp+0E0h+var_160]; string
0x1800502d6  xor     edx, edx; length
0x1800502d8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800502de  lea     r8, [rsp+1E0h+var_1B0]
0x1800502e3  mov     [rsp+1E0h+var_1B0], r13d
0x1800502e8  mov     rcx, rax; applicationUserModelId
0x1800502eb  mov     rdx, r12
0x1800502ee  mov     rdi, rax
0x1800502f1  call    ?IsRegisteredByApp@ApplicationTracker@@KAJPEBGAEBV?$vector@W4_SebiEventType@@V?$allocator@W4_SebiEventType@@@utl@@@utl@@PEAH@Z; ApplicationTracker::IsRegisteredByApp(ushort const *,utl::vector<_SebiEventType,utl::allocator<_SebiEventType>> const &,int *)
0x1800502f6  mov     ebx, eax
0x1800502f8  test    eax, eax
0x1800502fa  js      loc_180050512
0x180050300  cmp     [rsp+1E0h+var_1B0], r13d
0x180050305  jz      short loc_18005037F
0x180050307  mov     eax, 7FFFFFFEh
0x18005030c  lea     r8, [rbp+0E0h+var_150]
0x180050310  mov     edx, 82h
0x180050315  test    rax, rax
0x180050318  jz      short loc_180050336
0x18005031a  movzx   ecx, word ptr [rdi]
0x18005031d  test    cx, cx
0x180050320  jz      short loc_180050336
0x180050322  mov     [r8], cx
0x180050326  add     rdi, 2
0x18005032a  add     r8, 2
0x18005032e  sub     rax, r14
0x180050331  sub     rdx, r14
0x180050334  jnz     short loc_180050315
0x180050336  mov     rax, rdx
0x180050339  lea     rcx, [r8-2]
0x18005033d  neg     rax
0x180050340  sbb     ebx, ebx
0x180050342  not     ebx
0x180050344  and     ebx, 8007007Ah
0x18005034a  test    rdx, rdx
0x18005034d  cmovnz  rcx, r8; this
0x180050351  mov     [rcx], r13w
0x180050355  jz      loc_180050462
0x18005035b  lea     rdx, [rbp+0E0h+var_150]
0x18005035f  mov     rcx, r15
0x180050362  call    ?IsApplicationInList@ApplicationTracker@@KAHAEBV?$vector@U_ApplicationPackageInfo@@V?$allocator@U_ApplicationPackageInfo@@@utl@@@utl@@AEBU_ApplicationPackageInfo@@@Z; ApplicationTracker::IsApplicationInList(utl::vector<_ApplicationPackageInfo,utl::allocator<_ApplicationPackageInfo>> const &,_ApplicationPackageInfo const &)
0x180050367  test    eax, eax
0x180050369  jnz     short loc_18005037F
0x18005036b  lea     rdx, [rbp+0E0h+var_150]
0x18005036f  mov     rcx, r15
0x180050372  call    ?push_back@?$vector@U_ApplicationPackageInfo@@V?$allocator@U_ApplicationPackageInfo@@@utl@@@utl@@QEAA_NAEBU_ApplicationPackageInfo@@@Z; utl::vector<_ApplicationPackageInfo,utl::allocator<_ApplicationPackageInfo>>::push_back(_ApplicationPackageInfo const &)
0x180050377  test    al, al
0x180050379  jz      loc_18005044C
0x18005037f  mov     rcx, [rbp+0E0h+var_160]; string
0x180050383  call    cs:__imp_WindowsDeleteString
0x180050389  mov     rcx, [rsp+1E0h+var_168]
0x18005038e  mov     [rbp+0E0h+var_160], r13
0x180050392  test    rcx, rcx
0x180050395  jz      short loc_1800503A8
0x180050397  mov     [rsp+1E0h+var_168], r13
0x18005039c  mov     rax, [rcx]
0x18005039f  mov     rax, [rax+10h]
0x1800503a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503a8  mov     rcx, [rsp+1E0h+var_170]
0x1800503ad  test    rcx, rcx
0x1800503b0  jz      short loc_1800503C3
0x1800503b2  mov     [rsp+1E0h+var_170], r13
0x1800503b7  mov     rax, [rcx]
0x1800503ba  mov     rax, [rax+10h]
0x1800503be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503c3  add     esi, r14d
0x1800503c6  cmp     esi, [rbp+0E0h+var_158]
0x1800503c9  jb      loc_18005024E
0x1800503cf  mov     rcx, [rsp+1E0h+var_178]
0x1800503d4  test    rcx, rcx
0x1800503d7  jz      short loc_1800503EA
0x1800503d9  mov     [rsp+1E0h+var_178], r13
0x1800503de  mov     rax, [rcx]
0x1800503e1  mov     rax, [rax+10h]
0x1800503e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503ea  mov     rcx, [rsp+1E0h+var_180]
0x1800503ef  test    rcx, rcx
0x1800503f2  jz      short loc_180050405
0x1800503f4  mov     [rsp+1E0h+var_180], r13
0x1800503f9  mov     rax, [rcx]
0x1800503fc  mov     rax, [rax+10h]
0x180050400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050405  mov     rcx, [rsp+1E0h+var_188]
0x18005040a  test    rcx, rcx
0x18005040d  jz      short loc_180050420
0x18005040f  mov     [rsp+1E0h+var_188], r13
0x180050414  mov     rax, [rcx]
0x180050417  mov     rax, [rax+10h]
0x18005041b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050420  xor     eax, eax
0x180050422  mov     rcx, [rbp+0E0h+var_40]
0x180050429  xor     rcx, rsp; StackCookie
0x18005042c  call    __security_check_cookie
0x180050431  mov     rbx, [rsp+1E0h+arg_18]
0x180050439  add     rsp, 1B0h
0x180050440  pop     r15
0x180050442  pop     r14
0x180050444  pop     r13
0x180050446  pop     r12
0x180050448  pop     rdi
0x180050449  pop     rsi
0x18005044a  pop     rbp
0x18005044b  retn
0x18005044c  mov     ebx, 8007000Eh
0x180050451  mov     edx, ebx; int
0x180050453  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050458  xor     edx, edx
0x18005045a  mov     r9d, 0AAh
0x180050460  jmp     short loc_180050472
0x180050462  mov     edx, ebx; int
0x180050464  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180050469  mov     r9d, 0A3h
0x18005046f  mov     edx, r14d
0x180050472  mov     ecx, ebx
0x180050474  call    Log_HREvent_10
0x180050479  mov     rcx, [rbp+0E0h+var_160]; string
0x18005047d  call    cs:__imp_WindowsDeleteString
0x180050483  mov     rcx, [rsp+1E0h+var_168]
0x180050488  mov     [rbp+0E0h+var_160], r13
0x18005048c  test    rcx, rcx
0x18005048f  jz      short loc_1800504A2
  ... truncated ...
```
