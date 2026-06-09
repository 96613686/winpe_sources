# Windows::Internal::Storage::Cloud::CloudStore::OldIsNewDataAvailableInCloud(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,uchar *)

- ea: `0x18003a068`
- end: `0x18003a41f`
- name: `?OldIsNewDataAvailableInCloud@CloudStore@Cloud@Storage@Internal@Windows@@QEAAJW4PartitionKind@2345@PEAUHSTRING__@@11PEAE@Z`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180039e70`

## callees

- `0x180010688`
- `0x180024020`
- `0x18002570c`
- `0x18003a068`
- `0x18003a428`
- `0x18005babc`
- `0x18005d4b8`
- `0x18005f7bc`
- `0x18006010c`
- `0x1800c8458`
- `0x1800d1d50`
- `0x18010d418`
- `0x1801201a0`
- `0x180168920`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003a164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a0ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a126`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a2b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a313`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a389`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a3ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a3fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a0ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a126`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a1d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a2a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a2b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a313`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a389`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a3ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003a3fa`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::OldIsNewDataAvailableInCloud(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        HSTRING a4,
        int a5,
        _BYTE *a6)
{
  const char *v10; // r9
  __int64 v11; // r9
  int EffectivePartition; // eax
  unsigned int v13; // ebx
  int DataStoreId; // eax
  unsigned int v15; // ebx
  PCWSTR StringRawBuffer; // rsi
  int v17; // eax
  int v18; // ebx
  void *v19; // rdx
  const char *v20; // r9
  __int64 result; // rax
  void *v22; // rdx
  __int64 v23; // rdx
  void *v24; // rdx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  int v29; // [rsp+20h] [rbp-78h]
  int v30; // [rsp+20h] [rbp-78h]
  HSTRING v31; // [rsp+30h] [rbp-68h] BYREF
  HSTRING string; // [rsp+38h] [rbp-60h]
  HANDLE hObject; // [rsp+40h] [rbp-58h] BYREF
  __int128 v34; // [rsp+48h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    if ( Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(
           (Windows::Internal::Storage::Cloud::CloudStore *)a1,
           a4) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x747,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        v10);
    }
    *a6 = 0;
    EffectiveUserContext::Impersonate((void ***)(a1 + 200), &hObject);
    if ( IsASTAOrMainSTA() )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x74A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)0x8001010ELL,
        v29);
    WindowsDeleteString(0);
    v31 = 0;
    LOBYTE(v11) = 1;
    EffectivePartition = Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(a1, a2, a3, v11);
    v13 = EffectivePartition;
    if ( EffectivePartition < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74D,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)EffectivePartition,
        (int)&v31);
      WindowsDeleteString(v31);
      v31 = 0;
      if ( hObject != (HANDLE)-1LL )
        wil::details::RevertImpersonateToken(hObject, v22);
      return v13;
    }
    WindowsDeleteString(0);
    string = 0;
    v30 = a5;
    DataStoreId = Windows::Internal::Storage::Cloud::CloudStore::GetDataStoreId(a1, a2, v31, a4);
    v15 = DataStoreId;
    if ( DataStoreId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x750,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)DataStoreId,
        a5);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v31);
      v31 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
      return v15;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v34 = 0;
    v17 = Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices((Windows::Internal::Storage::Cloud::CloudStore *)a1);
    v18 = v17;
    if ( v17 < 0 )
    {
      v23 = 4511;
    }
    else
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR, __int128 *))(**(_QWORD **)(a1 + 480) + 32LL))(
              *(_QWORD *)(a1 + 480),
              StringRawBuffer,
              &v34);
      v18 = v17;
      if ( v17 >= 0 )
      {
        v18 = 0;
        goto LABEL_9;
      }
      v23 = 4512;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)(unsigned int)v17,
      a5);
LABEL_9:
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x754,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)v18,
        v30);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v31);
      v31 = 0;
      if ( hObject != (HANDLE)-1LL )
        wil::details::RevertImpersonateToken(hObject, v24);
      result = (unsigned int)v18;
    }
    else
    {
      if ( (_DWORD)v34 != 1 )
        goto LABEL_11;
      v25 = Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStorage((Windows::Internal::Storage::Cloud::CloudStore *)a1);
      v26 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x758,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v25,
          v30);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v31);
        v31 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
        return v26;
      }
      v27 = (*(__int64 (__fastcall **)(_QWORD, PCWSTR, _BYTE *))(**(_QWORD **)(a1 + 488) + 24LL))(
              *(_QWORD *)(a1 + 488),
              StringRawBuffer,
              a6);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x759,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)v27,
          v30);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v31);
        v31 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&hObject);
        result = v28;
      }
      else
      {
LABEL_11:
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v31);
        v31 = 0;
        if ( hObject != (HANDLE)-1LL )
          wil::details::RevertImpersonateToken(hObject, v19);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x75E,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x18003a068  push    rbx
0x18003a06a  push    rsi
0x18003a06b  push    rdi
0x18003a06c  push    r12
0x18003a06e  push    r13
0x18003a070  push    r14
0x18003a072  push    r15
0x18003a074  sub     rsp, 60h
0x18003a078  mov     rax, cs:__security_cookie
0x18003a07f  xor     rax, rsp
0x18003a082  mov     [rsp+98h+var_40], rax
0x18003a087  mov     rsi, r9
0x18003a08a  mov     rbx, r8
0x18003a08d  mov     r14d, edx
0x18003a090  mov     rdi, rcx
0x18003a093  mov     r12, qword ptr [rsp+98h+arg_20]
0x18003a09b  mov     r15, [rsp+98h+arg_28]
0x18003a0a3  mov     rdx, r9; HSTRING
0x18003a0a6  call    ?ShouldUseActivityFeedForSync@CloudStore@Cloud@Storage@Internal@Windows@@AEAA_NPEAUHSTRING__@@@Z; Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(HSTRING__ *)
0x18003a0ab  mov     rcx, [rsp+98h]; this
0x18003a0b3  xor     r13d, r13d
0x18003a0b6  test    al, al
0x18003a0b8  jnz     loc_18003A273
0x18003a0be  mov     [r15], r13b
0x18003a0c1  lea     rcx, [rdi+0C8h]
0x18003a0c8  lea     rdx, [rsp+98h+hObject]
0x18003a0cd  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x18003a0d2  nop
0x18003a0d3  call    ?IsASTAOrMainSTA@@YA_NXZ; IsASTAOrMainSTA(void)
0x18003a0d8  mov     rcx, [rsp+98h]; this
0x18003a0e0  test    al, al
0x18003a0e2  jnz     loc_18003A2D9
0x18003a0e8  mov     [rsp+98h+var_68], r13
0x18003a0ed  xor     ecx, ecx; string
0x18003a0ef  call    cs:__imp_WindowsDeleteString
0x18003a0f5  mov     [rsp+98h+var_68], r13
0x18003a0fa  lea     rax, [rsp+98h+var_68]
0x18003a0ff  mov     qword ptr [rsp+98h+var_78], rax; int
0x18003a104  mov     r9b, 1
0x18003a107  mov     r8, rbx
0x18003a10a  mov     edx, r14d
0x18003a10d  mov     rcx, rdi
0x18003a110  call    ?GetEffectivePartition@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@_NPEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,bool,HSTRING__ * *)
0x18003a115  mov     ebx, eax
0x18003a117  test    eax, eax
0x18003a119  js      loc_18003A211
0x18003a11f  mov     [rsp+98h+string], r13
0x18003a124  xor     ecx, ecx; string
0x18003a126  call    cs:__imp_WindowsDeleteString
0x18003a12c  mov     [rsp+98h+string], r13
0x18003a131  lea     rax, [rsp+98h+string]
0x18003a136  mov     [rsp+98h+var_70], rax
0x18003a13b  mov     qword ptr [rsp+98h+var_78], r12; int
0x18003a140  mov     r9, rsi
0x18003a143  mov     r8, [rsp+98h+var_68]
0x18003a148  mov     edx, r14d
0x18003a14b  mov     rcx, rdi
0x18003a14e  call    ?GetDataStoreId@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@11PEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetDataStoreId(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18003a153  mov     ebx, eax
0x18003a155  test    eax, eax
0x18003a157  js      loc_18003A2F1
0x18003a15d  xor     edx, edx; length
0x18003a15f  mov     rcx, [rsp+98h+string]; string
0x18003a164  call    cs:__imp_WindowsGetStringRawBuffer
0x18003a16a  mov     rsi, rax
0x18003a16d  xorps   xmm0, xmm0
0x18003a170  movups  [rsp+98h+var_50], xmm0
0x18003a175  mov     rcx, rdi; this
0x18003a178  call    ?EnsureTypeServices@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices(void)
0x18003a17d  mov     ebx, eax
0x18003a17f  test    eax, eax
0x18003a181  js      loc_18003A33F
0x18003a187  mov     rcx, [rdi+1E0h]
0x18003a18e  mov     rax, [rcx]
0x18003a191  lea     r8, [rsp+98h+var_50]
0x18003a196  mov     rdx, rsi
0x18003a199  mov     rax, [rax+20h]
0x18003a19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1a2  mov     ebx, eax
0x18003a1a4  test    eax, eax
0x18003a1a6  js      loc_18003A252
0x18003a1ac  mov     ebx, r13d
0x18003a1af  test    ebx, ebx
0x18003a1b1  js      loc_18003A285
0x18003a1b7  cmp     dword ptr [rsp+98h+var_50], 1
0x18003a1bc  jz      loc_18003A349
0x18003a1c2  mov     rcx, [rsp+98h+string]; string
0x18003a1c7  call    cs:__imp_WindowsDeleteString
0x18003a1cd  mov     [rsp+98h+string], r13
0x18003a1d2  mov     rcx, [rsp+98h+var_68]; string
0x18003a1d7  call    cs:__imp_WindowsDeleteString
0x18003a1dd  mov     [rsp+98h+var_68], r13
0x18003a1e2  mov     rcx, [rsp+98h+hObject]; hObject
0x18003a1e7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003a1eb  jz      short loc_18003A1F2
0x18003a1ed  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18003a1f2  xor     eax, eax
0x18003a1f4  mov     rcx, [rsp+98h+var_40]
0x18003a1f9  xor     rcx, rsp; StackCookie
0x18003a1fc  call    __security_check_cookie
0x18003a201  add     rsp, 60h
0x18003a205  pop     r15
0x18003a207  pop     r14
0x18003a209  pop     r13
0x18003a20b  pop     r12
0x18003a20d  pop     rdi
0x18003a20e  pop     rsi
0x18003a20f  pop     rbx
0x18003a210  retn
0x18003a211  mov     rcx, [rsp+98h]; this
0x18003a219  mov     r9d, ebx; char *
0x18003a21c  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a223  mov     edx, 74Dh; void *
0x18003a228  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a22d  nop
0x18003a22e  mov     rcx, [rsp+98h+var_68]; string
0x18003a233  call    cs:__imp_WindowsDeleteString
0x18003a239  mov     [rsp+98h+var_68], r13
0x18003a23e  mov     rcx, [rsp+98h+hObject]; hObject
0x18003a243  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003a247  jz      short loc_18003A24E
0x18003a249  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18003a24e  mov     eax, ebx
0x18003a250  jmp     short loc_18003A1F4
0x18003a252  mov     edx, 11A0h; void *
0x18003a257  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a25e  mov     r9d, eax; char *
0x18003a261  mov     rcx, [rsp+98h]; this
0x18003a269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a26e  jmp     loc_18003A1AF
0x18003a273  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a27a  mov     edx, 747h; void *
0x18003a27f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003a285  mov     rcx, [rsp+98h]; this
0x18003a28d  mov     r9d, ebx; char *
0x18003a290  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a297  mov     edx, 754h; void *
0x18003a29c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a2a1  nop
0x18003a2a2  mov     rcx, [rsp+98h+string]; string
0x18003a2a7  call    cs:__imp_WindowsDeleteString
0x18003a2ad  mov     [rsp+98h+string], r13
0x18003a2b2  mov     rcx, [rsp+98h+var_68]; string
0x18003a2b7  call    cs:__imp_WindowsDeleteString
0x18003a2bd  mov     [rsp+98h+var_68], r13
0x18003a2c2  mov     rcx, [rsp+98h+hObject]; hObject
0x18003a2c7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003a2cb  jz      short loc_18003A2D2
0x18003a2cd  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x18003a2d2  mov     eax, ebx
0x18003a2d4  jmp     loc_18003A1F4
0x18003a2d9  mov     r9d, 8001010Eh; char *
0x18003a2df  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a2e6  mov     edx, 74Ah; void *
0x18003a2eb  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18003a2f1  mov     rcx, [rsp+98h]; this
0x18003a2f9  mov     r9d, ebx; char *
0x18003a2fc  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a303  mov     edx, 750h; void *
0x18003a308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a30d  nop
0x18003a30e  mov     rcx, [rsp+98h+string]; string
0x18003a313  call    cs:__imp_WindowsDeleteString
0x18003a319  mov     [rsp+98h+string], r13
0x18003a31e  mov     rcx, [rsp+98h+var_68]; string
0x18003a323  call    cs:__imp_WindowsDeleteString
0x18003a329  mov     [rsp+98h+var_68], r13
0x18003a32e  lea     rcx, [rsp+98h+hObject]
0x18003a333  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18003a338  mov     eax, ebx
0x18003a33a  jmp     loc_18003A1F4
0x18003a33f  mov     edx, 119Fh
0x18003a344  jmp     loc_18003A257
0x18003a349  mov     rcx, rdi; this
0x18003a34c  call    ?EnsureCloudStorage@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStorage(void)
0x18003a351  mov     ebx, eax
0x18003a353  test    eax, eax
0x18003a355  jns     short loc_18003A3A5
0x18003a357  mov     rcx, [rsp+98h]; this
0x18003a35f  mov     r9d, eax; char *
0x18003a362  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a369  mov     edx, 758h; void *
0x18003a36e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a373  nop
0x18003a374  mov     rcx, [rsp+98h+string]; string
0x18003a379  call    cs:__imp_WindowsDeleteString
0x18003a37f  mov     [rsp+98h+string], r13
0x18003a384  mov     rcx, [rsp+98h+var_68]; string
0x18003a389  call    cs:__imp_WindowsDeleteString
0x18003a38f  mov     [rsp+98h+var_68], r13
0x18003a394  lea     rcx, [rsp+98h+hObject]
0x18003a399  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18003a39e  mov     eax, ebx
0x18003a3a0  jmp     loc_18003A1F4
0x18003a3a5  mov     rcx, [rdi+1E8h]
0x18003a3ac  mov     rax, [rcx]
0x18003a3af  mov     r8, r15
0x18003a3b2  mov     rdx, rsi
0x18003a3b5  mov     rax, [rax+18h]
0x18003a3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3be  mov     ebx, eax
0x18003a3c0  test    eax, eax
0x18003a3c2  jns     loc_18003A1C2
0x18003a3c8  mov     rcx, [rsp+98h]; this
0x18003a3d0  mov     r9d, eax; char *
0x18003a3d3  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a3da  mov     edx, 759h; void *
0x18003a3df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a3e4  nop
0x18003a3e5  mov     rcx, [rsp+98h+string]; string
0x18003a3ea  call    cs:__imp_WindowsDeleteString
0x18003a3f0  mov     [rsp+98h+string], r13
0x18003a3f5  mov     rcx, [rsp+98h+var_68]; string
0x18003a3fa  call    cs:__imp_WindowsDeleteString
0x18003a400  mov     [rsp+98h+var_68], r13
0x18003a405  lea     rcx, [rsp+98h+hObject]
0x18003a40a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18003a40f  mov     eax, ebx
0x18003a411  jmp     loc_18003A1F4
0x18003a416  mov     eax, dword ptr [rsp+98h+var_68]
0x18003a41a  jmp     loc_18003A1F4
```
