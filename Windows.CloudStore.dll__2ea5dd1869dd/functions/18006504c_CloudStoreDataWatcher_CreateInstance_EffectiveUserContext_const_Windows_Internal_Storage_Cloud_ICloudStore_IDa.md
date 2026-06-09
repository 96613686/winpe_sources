# CloudStoreDataWatcher_CreateInstance(EffectiveUserContext const &,Windows::Internal::Storage::Cloud::ICloudStore *,IDataChangeWatcher *,Windows::Internal::Storage::Cloud::PartitionKind,HSTRING__ *,HSTRING__ *,HSTRING__ *,Windows::Internal::Storage::Cloud::CloudDataChangeKinds,unsigned __int64,Windows::Internal::Storage::Cloud::ICloudStoreDataWatcher * *)

- ea: `0x18006504c`
- end: `0x1800653fc`
- name: `?CloudStoreDataWatcher_CreateInstance@@YAJAEBVEffectiveUserContext@@PEAUICloudStore@Cloud@Storage@Internal@Windows@@PEAUIDataChangeWatcher@@W4PartitionKind@3456@PEAUHSTRING__@@44W4CloudDataChangeKinds@3456@_KPEAPEAUICloudStoreDataWatcher@3456@@Z`
- size: `944`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006635c`

## callees

- `0x18000dfe4`
- `0x18003f11c`
- `0x180055f38`
- `0x180057f20`
- `0x18006504c`
- `0x180065614`
- `0x1800c8458`
- `0x1801236bc`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800650aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180065097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800650aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800650fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180065145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006518e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800650fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180065145`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006518e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800652a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800652c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800652fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006530c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006533b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006539a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065231`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800652a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800652c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800652fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006530c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006533b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180065369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006539a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudStoreDataWatcher_CreateInstance(
        int a1,
        int a2,
        int a3,
        int a4,
        HSTRING a5,
        HSTRING string,
        HSTRING a7,
        int a8,
        __int64 a9,
        HSTRING a10)
{
  HSTRING v14; // rsi
  PCWSTR StringRawBuffer; // rdi
  PCWSTR v16; // rbx
  PCWSTR v17; // rax
  __int64 v18; // r8
  HRESULT v19; // ebx
  HRESULT v20; // ebx
  HRESULT v21; // ebx
  void *v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  const char *v25; // r9
  __int64 result; // rax
  int v27; // [rsp+20h] [rbp-A8h]
  HSTRING v28; // [rsp+60h] [rbp-68h] BYREF
  __int64 v29; // [rsp+68h] [rbp-60h] BYREF
  HSTRING v30; // [rsp+70h] [rbp-58h] BYREF
  HSTRING *v31; // [rsp+78h] [rbp-50h] BYREF
  HSTRING newString; // [rsp+80h] [rbp-48h] BYREF
  char v33; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v14 = a10;
  *(_QWORD *)a10 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v16 = WindowsGetStringRawBuffer(a7, 0);
  v17 = WindowsGetStringRawBuffer(a5, 0);
  try
  {
    CloudStoreItemName_CreateInstance(&v29, (__int64)v17, v18, (__int64)v16, (__int64)StringRawBuffer);
    a10 = 0;
    v31 = &a10;
    newString = 0;
    v33 = 1;
    v19 = WindowsDuplicateString(a5, &newString);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v31);
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoredatawatcher.cpp",
        (const char *)(unsigned int)v19,
        v27);
      if ( a10 )
        WindowsDeleteString(a10);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      result = (unsigned int)v19;
    }
    else
    {
      v28 = 0;
      v31 = &v28;
      newString = 0;
      v33 = 1;
      v20 = WindowsDuplicateString(string, &newString);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v31);
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x147,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoredatawatcher.cpp",
          (const char *)(unsigned int)v20,
          v27);
        if ( v28 )
          WindowsDeleteString(v28);
        if ( a10 )
          WindowsDeleteString(a10);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        result = (unsigned int)v20;
      }
      else
      {
        v30 = 0;
        v31 = &v30;
        newString = 0;
        v33 = 1;
        v21 = WindowsDuplicateString(a7, &newString);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v31);
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14A,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoredatawatcher.cpp",
            (const char *)(unsigned int)v21,
            v27);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v30);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v28);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&a10);
          wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(&v29);
          result = (unsigned int)v21;
        }
        else
        {
          v22 = operator new(0xE8u, (const struct std::nothrow_t *)std::nothrow);
          v23 = v29;
          if ( v22
            && (v24 = Windows::Internal::Storage::Cloud::CloudStoreDataWatcher::CloudStoreDataWatcher(
                        (_DWORD)v22,
                        a1,
                        a2,
                        a3,
                        a4,
                        (__int64)&a10,
                        (__int64)&v28,
                        (__int64)&v30,
                        a8,
                        a9,
                        v29)) != 0 )
          {
            *(_QWORD *)v14 = v24;
            if ( v30 )
              WindowsDeleteString(v30);
            if ( v28 )
              WindowsDeleteString(v28);
            if ( a10 )
              WindowsDeleteString(a10);
            if ( v23 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x14D,
              (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoredatawatcher.cpp",
              (const char *)0x8007000ELL,
              v27);
            if ( v30 )
              WindowsDeleteString(v30);
            if ( v28 )
              WindowsDeleteString(v28);
            if ( a10 )
              WindowsDeleteString(a10);
            if ( v23 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
            result = 2147942414LL;
          }
        }
      }
    }
  }
  catch ( ... )
  {
    LODWORD(a10) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x151,
                     (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstoredatawatcher.cpp",
                     v25);
    return (unsigned int)a10;
  }
  return result;
}

```

## disassembly

```asm
0x18006504c  push    rbx
0x18006504e  push    rsi
0x18006504f  push    rdi
0x180065050  push    r12
0x180065052  push    r13
0x180065054  push    r14
0x180065056  push    r15
0x180065058  sub     rsp, 90h
0x18006505f  mov     r14d, r9d
0x180065062  mov     r15, r8
0x180065065  mov     r12, rdx
0x180065068  mov     r13, rcx
0x18006506b  mov     rsi, [rsp+0C8h+arg_48]
0x180065073  mov     qword ptr [rsi], 0
0x18006507a  xor     edx, edx; length
0x18006507c  mov     rcx, [rsp+0C8h+string]; string
0x180065084  call    cs:__imp_WindowsGetStringRawBuffer
0x18006508a  mov     rdi, rax
0x18006508d  xor     edx, edx; length
0x18006508f  mov     rcx, [rsp+0C8h+arg_30]; string
0x180065097  call    cs:__imp_WindowsGetStringRawBuffer
0x18006509d  mov     rbx, rax
0x1800650a0  xor     edx, edx; length
0x1800650a2  mov     rcx, [rsp+0C8h+arg_20]; string
0x1800650aa  call    cs:__imp_WindowsGetStringRawBuffer
0x1800650b0  mov     qword ptr [rsp+0C8h+var_A8], rdi; int
0x1800650b5  mov     r9, rbx
0x1800650b8  mov     rdx, rax
0x1800650bb  lea     rcx, [rsp+0C8h+var_60]
0x1800650c0  call    ?CloudStoreItemName_CreateInstance@@YA?AV?$com_ptr_t@UICloudStoreItemName@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG000@Z; CloudStoreItemName_CreateInstance(ushort const *,ushort const *,ushort const *,ushort const *)
0x1800650c5  xor     edi, edi
0x1800650c7  mov     [rsp+0C8h+arg_48], rdi
0x1800650cf  lea     rax, [rsp+0C8h+arg_48]
0x1800650d7  mov     [rsp+0C8h+var_50], rax
0x1800650dc  mov     [rsp+0C8h+newString], rdi
0x1800650e4  mov     [rsp+0C8h+var_40], 1
0x1800650ec  lea     rdx, [rsp+0C8h+newString]; newString
0x1800650f4  mov     rcx, [rsp+0C8h+arg_20]; string
0x1800650fc  call    cs:__imp_WindowsDuplicateString
0x180065102  mov     ebx, eax
0x180065104  lea     rcx, [rsp+0C8h+var_50]
0x180065109  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18006510e  test    ebx, ebx
0x180065110  js      loc_18006527E
0x180065116  mov     [rsp+0C8h+var_68], rdi
0x18006511b  lea     rax, [rsp+0C8h+var_68]
0x180065120  mov     [rsp+0C8h+var_50], rax
0x180065125  mov     [rsp+0C8h+newString], rdi
0x18006512d  mov     [rsp+0C8h+var_40], 1
0x180065135  lea     rdx, [rsp+0C8h+newString]; newString
0x18006513d  mov     rcx, [rsp+0C8h+string]; string
0x180065145  call    cs:__imp_WindowsDuplicateString
0x18006514b  mov     ebx, eax
0x18006514d  lea     rcx, [rsp+0C8h+var_50]
0x180065152  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x180065157  test    ebx, ebx
0x180065159  js      loc_180065343
0x18006515f  mov     [rsp+0C8h+var_58], rdi
0x180065164  lea     rax, [rsp+0C8h+var_58]
0x180065169  mov     [rsp+0C8h+var_50], rax
0x18006516e  mov     [rsp+0C8h+newString], rdi
0x180065176  mov     [rsp+0C8h+var_40], 1
0x18006517e  lea     rdx, [rsp+0C8h+newString]; newString
0x180065186  mov     rcx, [rsp+0C8h+arg_30]; string
0x18006518e  call    cs:__imp_WindowsDuplicateString
0x180065194  mov     ebx, eax
0x180065196  lea     rcx, [rsp+0C8h+var_50]
0x18006519b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800651a0  test    ebx, ebx
0x1800651a2  js      loc_1800653A2
0x1800651a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800651af  mov     ecx, 0E8h; unsigned __int64
0x1800651b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800651b9  mov     rbx, [rsp+0C8h+var_60]
0x1800651be  test    rax, rax
0x1800651c1  jz      loc_1800652D1
0x1800651c7  mov     [rsp+0C8h+var_78], rbx
0x1800651cc  mov     rcx, [rsp+0C8h+arg_40]
0x1800651d4  mov     [rsp+0C8h+var_80], rcx
0x1800651d9  mov     ecx, [rsp+0C8h+arg_38]
0x1800651e0  mov     [rsp+0C8h+var_88], ecx
0x1800651e4  lea     rcx, [rsp+0C8h+var_58]
0x1800651e9  mov     [rsp+0C8h+var_90], rcx
0x1800651ee  lea     rcx, [rsp+0C8h+var_68]
0x1800651f3  mov     [rsp+0C8h+var_98], rcx
0x1800651f8  lea     rcx, [rsp+0C8h+arg_48]
0x180065200  mov     [rsp+0C8h+var_A0], rcx
0x180065205  mov     [rsp+0C8h+var_A8], r14d
0x18006520a  mov     r9, r15
0x18006520d  mov     r8, r12
0x180065210  mov     rdx, r13
0x180065213  mov     rcx, rax
0x180065216  call    ??0CloudStoreDataWatcher@Cloud@Storage@Internal@Windows@@QEAA@AEBVEffectiveUserContext@@PEAUICloudStore@1234@PEAUIDataChangeWatcher@@W4PartitionKind@1234@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@44W4CloudDataChangeKinds@1234@_KPEAUICloudStoreItemName@1234@@Z; Windows::Internal::Storage::Cloud::CloudStoreDataWatcher::CloudStoreDataWatcher(EffectiveUserContext const &,Windows::Internal::Storage::Cloud::ICloudStore *,IDataChangeWatcher *,Windows::Internal::Storage::Cloud::PartitionKind,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> &&,Windows::Internal::Storage::Cloud::CloudDataChangeKinds,unsigned __int64,Windows::Internal::Storage::Cloud::ICloudStoreItemName *)
0x18006521b  test    rax, rax
0x18006521e  jz      loc_1800652D1
0x180065224  mov     [rsi], rax
0x180065227  mov     rcx, [rsp+0C8h+var_58]; string
0x18006522c  test    rcx, rcx
0x18006522f  jz      short loc_180065237
0x180065231  call    cs:__imp_WindowsDeleteString
0x180065237  mov     rcx, [rsp+0C8h+var_68]; string
0x18006523c  test    rcx, rcx
0x18006523f  jz      short loc_180065247
0x180065241  call    cs:__imp_WindowsDeleteString
0x180065247  mov     rcx, [rsp+0C8h+arg_48]; string
0x18006524f  test    rcx, rcx
0x180065252  jnz     short loc_1800652C9
0x180065254  test    rbx, rbx
0x180065257  jz      short loc_180065269
0x180065259  mov     rax, [rbx]
0x18006525c  mov     rcx, rbx
0x18006525f  mov     rax, [rax+10h]
0x180065263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065268  nop
0x180065269  xor     eax, eax
0x18006526b  add     rsp, 90h
0x180065272  pop     r15
0x180065274  pop     r14
0x180065276  pop     r13
0x180065278  pop     r12
0x18006527a  pop     rdi
0x18006527b  pop     rsi
0x18006527c  pop     rbx
0x18006527d  retn
0x18006527e  mov     rcx, [rsp+0C8h]; this
0x180065286  mov     r9d, ebx; char *
0x180065289  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180065290  mov     edx, 144h; void *
0x180065295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006529a  mov     rcx, [rsp+0C8h+arg_48]; string
0x1800652a2  test    rcx, rcx
0x1800652a5  jz      short loc_1800652AE
0x1800652a7  call    cs:__imp_WindowsDeleteString
0x1800652ad  nop
0x1800652ae  mov     rcx, [rsp+0C8h+var_60]
0x1800652b3  test    rcx, rcx
0x1800652b6  jz      short loc_1800652C5
0x1800652b8  mov     rax, [rcx]
0x1800652bb  mov     rax, [rax+10h]
0x1800652bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800652c4  nop
0x1800652c5  mov     eax, ebx
0x1800652c7  jmp     short loc_18006526B
0x1800652c9  call    cs:__imp_WindowsDeleteString
0x1800652cf  jmp     short loc_180065254
0x1800652d1  mov     rcx, [rsp+0C8h]; this
0x1800652d9  mov     esi, 8007000Eh
0x1800652de  mov     r9d, esi; char *
0x1800652e1  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800652e8  mov     edx, 14Dh; void *
0x1800652ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800652f2  mov     rcx, [rsp+0C8h+var_58]; string
0x1800652f7  test    rcx, rcx
0x1800652fa  jz      short loc_180065302
0x1800652fc  call    cs:__imp_WindowsDeleteString
0x180065302  mov     rcx, [rsp+0C8h+var_68]; string
0x180065307  test    rcx, rcx
0x18006530a  jz      short loc_180065312
0x18006530c  call    cs:__imp_WindowsDeleteString
0x180065312  mov     rcx, [rsp+0C8h+arg_48]; string
0x18006531a  test    rcx, rcx
0x18006531d  jnz     short loc_18006533B
0x18006531f  test    rbx, rbx
0x180065322  jz      short loc_180065334
0x180065324  mov     rcx, [rbx]
0x180065327  mov     rax, [rcx+10h]
0x18006532b  mov     rcx, rbx
0x18006532e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065333  nop
0x180065334  mov     eax, esi
0x180065336  jmp     loc_18006526B
0x18006533b  call    cs:__imp_WindowsDeleteString
0x180065341  jmp     short loc_18006531F
0x180065343  mov     rcx, [rsp+0C8h]; this
0x18006534b  mov     r9d, ebx; char *
0x18006534e  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x180065355  mov     edx, 147h; void *
0x18006535a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006535f  mov     rcx, [rsp+0C8h+var_68]; string
0x180065364  test    rcx, rcx
0x180065367  jz      short loc_18006536F
0x180065369  call    cs:__imp_WindowsDeleteString
0x18006536f  mov     rcx, [rsp+0C8h+arg_48]; string
0x180065377  test    rcx, rcx
0x18006537a  jnz     short loc_18006539A
0x18006537c  mov     rcx, [rsp+0C8h+var_60]
0x180065381  test    rcx, rcx
0x180065384  jz      short loc_180065393
0x180065386  mov     rax, [rcx]
0x180065389  mov     rax, [rax+10h]
0x18006538d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065392  nop
0x180065393  mov     eax, ebx
0x180065395  jmp     loc_18006526B
0x18006539a  call    cs:__imp_WindowsDeleteString
0x1800653a0  jmp     short loc_18006537C
0x1800653a2  mov     rcx, [rsp+0C8h]; this
0x1800653aa  mov     r9d, ebx; char *
0x1800653ad  lea     r8, aOnecoreuapShel_22; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x1800653b4  mov     edx, 14Ah; void *
0x1800653b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800653be  lea     rcx, [rsp+0C8h+var_58]
0x1800653c3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800653c8  lea     rcx, [rsp+0C8h+var_68]
0x1800653cd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800653d2  lea     rcx, [rsp+0C8h+arg_48]
0x1800653da  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800653df  lea     rcx, [rsp+0C8h+var_60]
0x1800653e4  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800653e9  mov     eax, ebx
0x1800653eb  jmp     loc_18006526B
0x1800653f0  mov     eax, dword ptr [rsp+0C8h+arg_48]
0x1800653f7  jmp     loc_18006526B
```
