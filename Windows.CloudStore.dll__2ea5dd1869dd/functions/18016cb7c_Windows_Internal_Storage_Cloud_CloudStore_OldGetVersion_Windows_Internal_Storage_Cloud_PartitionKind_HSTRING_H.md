# Windows::Internal::Storage::Cloud::CloudStore::OldGetVersion(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,unsigned __int64 *)

- ea: `0x18016cb7c`
- end: `0x18016cfca`
- name: `?OldGetVersion@CloudStore@Cloud@Storage@Internal@Windows@@QEAAJW4PartitionKind@2345@PEAUHSTRING__@@11PEA_K@Z`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18016b3e0`

## callees

- `0x180010688`
- `0x180024020`
- `0x180047904`
- `0x18005babc`
- `0x18005d4b8`
- `0x18005f34c`
- `0x18005f748`
- `0x18005f914`
- `0x18006010c`
- `0x180062040`
- `0x1800c8458`
- `0x1800d1d50`
- `0x1801201a0`
- `0x18016cb7c`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016ccf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18016ccf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cbff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cc4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cc70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ccc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ccd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cd41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cd51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cdd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cde8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ce3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ce4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cf22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cf32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cf7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cf8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cbff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cc4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cc70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ccc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ccd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cd41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cd51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cdd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cde8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ce3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016ce4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cef6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cf22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cf32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cf7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18016cf8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::OldGetVersion(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        HSTRING a4,
        int a5,
        _QWORD *a6)
{
  const char *v10; // r9
  __int64 v11; // r9
  int EffectivePartition; // eax
  unsigned int v13; // edi
  int DataStoreId; // eax
  unsigned int v16; // edi
  const unsigned __int16 *StringRawBuffer; // rsi
  int TypeServiceAttributesForId; // eax
  __int64 v19; // r8
  unsigned int v20; // edi
  int RootFromAttribute; // edi
  __int64 v22; // rdx
  __int64 v23; // r8
  HKEY *v24; // r9
  int v25; // eax
  unsigned int v26; // edi
  int v27; // eax
  unsigned int v28; // edi
  HSTRING string; // [rsp+30h] [rbp-88h] BYREF
  HSTRING v30; // [rsp+38h] [rbp-80h] BYREF
  __int64 v31; // [rsp+40h] [rbp-78h] BYREF
  __int64 v32; // [rsp+48h] [rbp-70h] BYREF
  __int64 *v33; // [rsp+50h] [rbp-68h] BYREF
  __int64 v34; // [rsp+58h] [rbp-60h] BYREF
  char v35; // [rsp+60h] [rbp-58h]
  __int128 v36; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(
         (Windows::Internal::Storage::Cloud::CloudStore *)a1,
         a4) )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3CF,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      v10);
  }
  *a6 = 0;
  EffectiveUserContext::Impersonate((void ***)(a1 + 200), &v32);
  WindowsDeleteString(0);
  string = 0;
  LOBYTE(v11) = 1;
  EffectivePartition = Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(a1, a2, a3, v11);
  v13 = EffectivePartition;
  if ( EffectivePartition >= 0 )
  {
    WindowsDeleteString(0);
    v30 = 0;
    DataStoreId = Windows::Internal::Storage::Cloud::CloudStore::GetDataStoreId(a1, a2, string, a4);
    v16 = DataStoreId;
    if ( DataStoreId >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v30, 0);
      v36 = 0;
      TypeServiceAttributesForId = Windows::Internal::Storage::Cloud::CloudStore::GetTypeServiceAttributesForId(
                                     (Windows::Internal::Storage::Cloud::CloudStore *)a1,
                                     StringRawBuffer,
                                     (struct TypeAttributes *)&v36);
      v20 = TypeServiceAttributesForId;
      if ( TypeServiceAttributesForId >= 0 )
      {
        v31 = 0;
        v33 = &v31;
        v34 = 0;
        v35 = 1;
        RootFromAttribute = CloudStoreUtilities::GetRootFromAttribute(a1 + 232, (unsigned int)v36, v19, &v34);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v33);
        if ( RootFromAttribute >= 0 )
        {
          v25 = Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStoreCache((RTL_SRWLOCK *)a1, v22, v23, v24);
          v26 = v25;
          if ( v25 >= 0 )
          {
            v27 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64, const unsigned __int16 *))(**(_QWORD **)(a1 + 496) + 56LL))(
                    *(_QWORD *)(a1 + 496),
                    StringRawBuffer,
                    v31,
                    L"Current");
            v28 = v27;
            if ( v27 == -2147024894 )
            {
              if ( (_DWORD)v36 == 1 )
                (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64, const unsigned __int16 *, _QWORD *, HSTRING *))(**(_QWORD **)(a1 + 496) + 56LL))(
                  *(_QWORD *)(a1 + 496),
                  StringRawBuffer,
                  v31,
                  L"Cloud",
                  a6,
                  &v30);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
              WindowsDeleteString(v30);
              v30 = 0;
              WindowsDeleteString(string);
              string = 0;
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v32);
              return 0;
            }
            else
            {
              if ( v27 < 0 )
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x3EC,
                  (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                  (const char *)(unsigned int)v27,
                  (int)a6);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
              WindowsDeleteString(v30);
              WindowsDeleteString(string);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v32);
              return v28;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E0,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
              (const char *)(unsigned int)v25,
              a5);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
            WindowsDeleteString(v30);
            v30 = 0;
            WindowsDeleteString(string);
            string = 0;
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v32);
            return v26;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3DE,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)RootFromAttribute,
            a5);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
          WindowsDeleteString(v30);
          v30 = 0;
          WindowsDeleteString(string);
          string = 0;
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v32);
          return (unsigned int)RootFromAttribute;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3DC,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
          (const char *)(unsigned int)TypeServiceAttributesForId,
          a5);
        WindowsDeleteString(v30);
        v30 = 0;
        WindowsDeleteString(string);
        string = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v32);
        return v20;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3D8,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)DataStoreId,
        a5);
      WindowsDeleteString(v30);
      v30 = 0;
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v32);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D5,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
      (const char *)(unsigned int)EffectivePartition,
      (int)&string);
    WindowsDeleteString(string);
    string = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v32);
    return v13;
  }
}

```

## disassembly

```asm
0x18016cb7c  push    rbx
0x18016cb7e  push    rsi
0x18016cb7f  push    rdi
0x18016cb80  push    r12
0x18016cb82  push    r13
0x18016cb84  push    r14
0x18016cb86  push    r15
0x18016cb88  sub     rsp, 80h
0x18016cb8f  mov     rax, cs:__security_cookie
0x18016cb96  xor     rax, rsp
0x18016cb99  mov     [rsp+0B8h+var_40], rax
0x18016cb9e  mov     rsi, r9
0x18016cba1  mov     rdi, r8
0x18016cba4  mov     r15d, edx
0x18016cba7  mov     rbx, rcx
0x18016cbaa  mov     r12, qword ptr [rsp+0B8h+arg_20]
0x18016cbb2  mov     r14, qword ptr [rsp+0B8h+arg_28]
0x18016cbba  mov     rdx, r9; HSTRING
0x18016cbbd  call    ?ShouldUseActivityFeedForSync@CloudStore@Cloud@Storage@Internal@Windows@@AEAA_NPEAUHSTRING__@@@Z; Windows::Internal::Storage::Cloud::CloudStore::ShouldUseActivityFeedForSync(HSTRING__ *)
0x18016cbc2  mov     rcx, [rsp+0B8h]; this
0x18016cbca  xor     r13d, r13d
0x18016cbcd  test    al, al
0x18016cbcf  jz      short loc_18016CBE3
0x18016cbd1  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18016cbd8  mov     edx, 3CFh; void *
0x18016cbdd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18016cbe3  mov     [r14], r13
0x18016cbe6  lea     rcx, [rbx+0C8h]
0x18016cbed  lea     rdx, [rsp+0B8h+var_70]
0x18016cbf2  call    ?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; EffectiveUserContext::Impersonate(void)
0x18016cbf7  nop
0x18016cbf8  mov     [rsp+0B8h+string], r13
0x18016cbfd  xor     ecx, ecx; string
0x18016cbff  call    cs:__imp_WindowsDeleteString
0x18016cc05  mov     [rsp+0B8h+string], r13
0x18016cc0a  lea     rax, [rsp+0B8h+string]
0x18016cc0f  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x18016cc14  mov     r9b, 1
0x18016cc17  mov     r8, rdi
0x18016cc1a  mov     edx, r15d
0x18016cc1d  mov     rcx, rbx
0x18016cc20  call    ?GetEffectivePartition@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@_NPEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetEffectivePartition(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,bool,HSTRING__ * *)
0x18016cc25  mov     edi, eax
0x18016cc27  test    eax, eax
0x18016cc29  jns     short loc_18016CC69
0x18016cc2b  mov     rcx, [rsp+0B8h]; this
0x18016cc33  mov     r9d, eax; char *
0x18016cc36  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18016cc3d  mov     edx, 3D5h; void *
0x18016cc42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016cc47  nop
0x18016cc48  mov     rcx, [rsp+0B8h+string]; string
0x18016cc4d  call    cs:__imp_WindowsDeleteString
0x18016cc53  mov     [rsp+0B8h+string], r13
0x18016cc58  lea     rcx, [rsp+0B8h+var_70]
0x18016cc5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18016cc62  mov     eax, edi
0x18016cc64  jmp     loc_18016CFA9
0x18016cc69  mov     [rsp+0B8h+var_80], r13
0x18016cc6e  xor     ecx, ecx; string
0x18016cc70  call    cs:__imp_WindowsDeleteString
0x18016cc76  mov     [rsp+0B8h+var_80], r13
0x18016cc7b  lea     rax, [rsp+0B8h+var_80]
0x18016cc80  mov     [rsp+0B8h+var_90], rax
0x18016cc85  mov     qword ptr [rsp+0B8h+var_98], r12; int
0x18016cc8a  mov     r9, rsi
0x18016cc8d  mov     r8, [rsp+0B8h+string]
0x18016cc92  mov     edx, r15d
0x18016cc95  mov     rcx, rbx
0x18016cc98  call    ?GetDataStoreId@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJW4PartitionKind@2345@PEAUHSTRING__@@11PEAPEAU7@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetDataStoreId(Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18016cc9d  mov     edi, eax
0x18016cc9f  test    eax, eax
0x18016cca1  jns     short loc_18016CCF1
0x18016cca3  mov     rcx, [rsp+0B8h]; this
0x18016ccab  mov     r9d, eax; char *
0x18016ccae  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18016ccb5  mov     edx, 3D8h; void *
0x18016ccba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016ccbf  nop
0x18016ccc0  mov     rcx, [rsp+0B8h+var_80]; string
0x18016ccc5  call    cs:__imp_WindowsDeleteString
0x18016cccb  mov     [rsp+0B8h+var_80], r13
0x18016ccd0  mov     rcx, [rsp+0B8h+string]; string
0x18016ccd5  call    cs:__imp_WindowsDeleteString
0x18016ccdb  mov     [rsp+0B8h+string], r13
0x18016cce0  lea     rcx, [rsp+0B8h+var_70]
0x18016cce5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18016ccea  mov     eax, edi
0x18016ccec  jmp     loc_18016CFA9
0x18016ccf1  xor     edx, edx; length
0x18016ccf3  mov     rcx, [rsp+0B8h+var_80]; string
0x18016ccf8  call    cs:__imp_WindowsGetStringRawBuffer
0x18016ccfe  mov     rsi, rax
0x18016cd01  xorps   xmm0, xmm0
0x18016cd04  movups  [rsp+0B8h+var_50], xmm0
0x18016cd09  lea     r8, [rsp+0B8h+var_50]; struct TypeAttributes *
0x18016cd0e  mov     rdx, rax; unsigned __int16 *
0x18016cd11  mov     rcx, rbx; this
0x18016cd14  call    ?GetTypeServiceAttributesForId@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAUTypeAttributes@@@Z; Windows::Internal::Storage::Cloud::CloudStore::GetTypeServiceAttributesForId(ushort const *,TypeAttributes *)
0x18016cd19  mov     edi, eax
0x18016cd1b  test    eax, eax
0x18016cd1d  jns     short loc_18016CD6D
0x18016cd1f  mov     rcx, [rsp+0B8h]; this
0x18016cd27  mov     r9d, eax; char *
0x18016cd2a  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18016cd31  mov     edx, 3DCh; void *
0x18016cd36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016cd3b  nop
0x18016cd3c  mov     rcx, [rsp+0B8h+var_80]; string
0x18016cd41  call    cs:__imp_WindowsDeleteString
0x18016cd47  mov     [rsp+0B8h+var_80], r13
0x18016cd4c  mov     rcx, [rsp+0B8h+string]; string
0x18016cd51  call    cs:__imp_WindowsDeleteString
0x18016cd57  mov     [rsp+0B8h+string], r13
0x18016cd5c  lea     rcx, [rsp+0B8h+var_70]
0x18016cd61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18016cd66  mov     eax, edi
0x18016cd68  jmp     loc_18016CFA9
0x18016cd6d  mov     [rsp+0B8h+var_78], r13
0x18016cd72  lea     rax, [rsp+0B8h+var_78]
0x18016cd77  mov     [rsp+0B8h+var_68], rax
0x18016cd7c  mov     [rsp+0B8h+var_60], r13
0x18016cd81  mov     [rsp+0B8h+var_58], 1
0x18016cd86  lea     rcx, [rbx+0E8h]
0x18016cd8d  lea     r9, [rsp+0B8h+var_60]
0x18016cd92  mov     edx, dword ptr [rsp+0B8h+var_50]
0x18016cd96  call    ?GetRootFromAttribute@CloudStoreUtilities@@YAJAEBVEffectiveWebAccountContext@@W4ScopeValue@@W4TRIBIT@@PEAPEAG@Z; CloudStoreUtilities::GetRootFromAttribute(EffectiveWebAccountContext const &,ScopeValue,TRIBIT,ushort * *)
0x18016cd9b  mov     edi, eax
0x18016cd9d  lea     rcx, [rsp+0B8h+var_68]
0x18016cda2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18016cda7  test    edi, edi
0x18016cda9  jns     short loc_18016CE04
0x18016cdab  mov     rcx, [rsp+0B8h]; this
0x18016cdb3  mov     r9d, edi; char *
0x18016cdb6  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18016cdbd  mov     edx, 3DEh; void *
0x18016cdc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016cdc7  nop
0x18016cdc8  lea     rcx, [rsp+0B8h+var_78]
0x18016cdcd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18016cdd2  nop
0x18016cdd3  mov     rcx, [rsp+0B8h+var_80]; string
0x18016cdd8  call    cs:__imp_WindowsDeleteString
0x18016cdde  mov     [rsp+0B8h+var_80], r13
0x18016cde3  mov     rcx, [rsp+0B8h+string]; string
0x18016cde8  call    cs:__imp_WindowsDeleteString
0x18016cdee  mov     [rsp+0B8h+string], r13
0x18016cdf3  lea     rcx, [rsp+0B8h+var_70]
0x18016cdf8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18016cdfd  mov     eax, edi
0x18016cdff  jmp     loc_18016CFA9
0x18016ce04  mov     rcx, rbx; this
0x18016ce07  call    ?EnsureCloudStoreCache@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureCloudStoreCache(void)
0x18016ce0c  mov     edi, eax
0x18016ce0e  test    eax, eax
0x18016ce10  jns     short loc_18016CE6B
0x18016ce12  mov     rcx, [rsp+0B8h]; this
0x18016ce1a  mov     r9d, eax; char *
0x18016ce1d  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18016ce24  mov     edx, 3E0h; void *
0x18016ce29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016ce2e  nop
0x18016ce2f  lea     rcx, [rsp+0B8h+var_78]
0x18016ce34  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18016ce39  nop
0x18016ce3a  mov     rcx, [rsp+0B8h+var_80]; string
0x18016ce3f  call    cs:__imp_WindowsDeleteString
0x18016ce45  mov     [rsp+0B8h+var_80], r13
0x18016ce4a  mov     rcx, [rsp+0B8h+string]; string
0x18016ce4f  call    cs:__imp_WindowsDeleteString
0x18016ce55  mov     [rsp+0B8h+string], r13
0x18016ce5a  lea     rcx, [rsp+0B8h+var_70]
0x18016ce5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18016ce64  mov     eax, edi
0x18016ce66  jmp     loc_18016CFA9
0x18016ce6b  mov     rcx, [rbx+1F0h]
0x18016ce72  mov     rax, [rcx]
0x18016ce75  mov     qword ptr [rsp+0B8h+var_98], r14; int
0x18016ce7a  lea     r9, aCurrent_1; "Current"
0x18016ce81  mov     r8, [rsp+0B8h+var_78]
0x18016ce86  mov     rdx, rsi
0x18016ce89  mov     rax, [rax+38h]
0x18016ce8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ce92  mov     edi, eax
0x18016ce94  mov     r15d, 80070002h
0x18016ce9a  cmp     eax, r15d
0x18016ce9d  jnz     loc_18016CF4B
0x18016cea3  cmp     dword ptr [rsp+0B8h+var_50], 1
0x18016cea8  jnz     short loc_18016CF12
0x18016ceaa  mov     rcx, [rbx+1F0h]
0x18016ceb1  mov     rax, [rcx]
0x18016ceb4  mov     qword ptr [rsp+0B8h+var_98], r14
0x18016ceb9  lea     r9, aCloud; "Cloud"
0x18016cec0  mov     r8, [rsp+0B8h+var_78]
0x18016cec5  mov     rdx, rsi
0x18016cec8  mov     rax, [rax+38h]
0x18016cecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ced1  cmp     eax, r15d
0x18016ced4  jnz     short loc_18016CF12
0x18016ced6  lea     rcx, [rsp+0B8h+var_78]
0x18016cedb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18016cee0  nop
0x18016cee1  mov     rcx, [rsp+0B8h+var_80]; string
0x18016cee6  call    cs:__imp_WindowsDeleteString
0x18016ceec  mov     [rsp+0B8h+var_80], r13
0x18016cef1  mov     rcx, [rsp+0B8h+string]; string
0x18016cef6  call    cs:__imp_WindowsDeleteString
0x18016cefc  mov     [rsp+0B8h+string], r13
0x18016cf01  lea     rcx, [rsp+0B8h+var_70]
0x18016cf06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18016cf0b  xor     eax, eax
0x18016cf0d  jmp     loc_18016CFA9
0x18016cf12  lea     rcx, [rsp+0B8h+var_78]
0x18016cf17  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18016cf1c  nop
0x18016cf1d  mov     rcx, [rsp+0B8h+var_80]; string
0x18016cf22  call    cs:__imp_WindowsDeleteString
0x18016cf28  mov     [rsp+0B8h+var_80], r13
0x18016cf2d  mov     rcx, [rsp+0B8h+string]; string
0x18016cf32  call    cs:__imp_WindowsDeleteString
0x18016cf38  mov     [rsp+0B8h+string], r13
0x18016cf3d  lea     rcx, [rsp+0B8h+var_70]
0x18016cf42  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18016cf47  xor     eax, eax
0x18016cf49  jmp     short loc_18016CFA9
0x18016cf4b  test    edi, edi
0x18016cf4d  jns     short loc_18016CF6C
0x18016cf4f  mov     rcx, [rsp+0B8h]; this
0x18016cf57  mov     r9d, edi; char *
0x18016cf5a  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18016cf61  mov     edx, 3ECh; void *
0x18016cf66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016cf6b  nop
0x18016cf6c  lea     rcx, [rsp+0B8h+var_78]
0x18016cf71  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18016cf76  nop
0x18016cf77  mov     rcx, [rsp+0B8h+var_80]; string
0x18016cf7c  call    cs:__imp_WindowsDeleteString
0x18016cf82  mov     [rsp+0B8h+var_80], r13
0x18016cf87  mov     rcx, [rsp+0B8h+string]; string
0x18016cf8c  call    cs:__imp_WindowsDeleteString
0x18016cf92  mov     [rsp+0B8h+string], r13
0x18016cf97  lea     rcx, [rsp+0B8h+var_70]
0x18016cf9c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18016cfa1  mov     eax, edi
0x18016cfa3  jmp     short loc_18016CFA9
0x18016cfa5  mov     eax, dword ptr [rsp+0B8h+string]
0x18016cfa9  mov     rcx, [rsp+0B8h+var_40]
0x18016cfae  xor     rcx, rsp; StackCookie
0x18016cfb1  call    __security_check_cookie
0x18016cfb6  add     rsp, 80h
0x18016cfbd  pop     r15
0x18016cfbf  pop     r14
0x18016cfc1  pop     r13
0x18016cfc3  pop     r12
0x18016cfc5  pop     rdi
0x18016cfc6  pop     rsi
0x18016cfc7  pop     rbx
0x18016cfc8  retn
```
