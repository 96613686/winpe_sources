# Windows::Management::Provisioning::PackageServer::GetProvCommandResults(uint *,Windows::Management::Provisioning::ProvCommandResult * *)

- ea: `0x18007aa70`
- end: `0x18007acf3`
- name: `?GetProvCommandResults@PackageServer@Provisioning@Management@Windows@@UEAAJPEAIPEAPEAUProvCommandResult@234@@Z`
- size: `643`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::PackageServer *__hidden this, unsigned int *, struct Windows::Management::Provisioning::ProvCommandResult **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x18000d50c`
- `0x18000dc18`
- `0x180017024`
- `0x1800184c0`
- `0x18001c920`
- `0x18003e5d4`
- `0x18006f6a0`
- `0x1800700ac`
- `0x18007a688`
- `0x18007a7f8`
- `0x18007a828`
- `0x18007aa70`
- `0x18007bb80`
- `0x1800abbc0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007ac2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007ac2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ac98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007ac98`

## string_xrefs

- `0x18007aae7`: `SOFTWARE\Microsoft\Provisioning\CommandResults`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Windows::Management::Provisioning::PackageServer::GetProvCommandResults(
        Windows::Management::Provisioning::PackageServer *this,
        unsigned int *a2,
        struct Windows::Management::Provisioning::ProvCommandResult **a3,
        const char *a4)
{
  const WCHAR *v7; // rax
  HKEY v8; // r8
  unsigned __int64 v9; // rsi
  __int64 v10; // r12
  __int64 v11; // rbx
  int v12; // eax
  __int64 v14; // r13
  HSTRING *v15; // rdi
  int v16; // eax
  HRESULT v17; // eax
  HSTRING string; // [rsp+20h] [rbp-98h] BYREF
  void *v19; // [rsp+28h] [rbp-90h] BYREF
  __int64 v20; // [rsp+30h] [rbp-88h] BYREF
  __int64 v21; // [rsp+38h] [rbp-80h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-78h]
  __int64 v23; // [rsp+48h] [rbp-70h] BYREF
  __int64 v24; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v25[32]; // [rsp+58h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
      a4);
  if ( !a3 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
      a4);
  *a3 = 0;
  *a2 = 0;
  v24 = -2147483646;
  std::wstring::wstring(v25, L"SOFTWARE\\Microsoft\\Provisioning\\CommandResults");
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 104);
  RegistryResults::Parse((__int64)&v24, (__int64)&v21, v8, v7);
  v9 = v22;
  if ( v22 )
  {
    wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningMVUIItem [0]>(&v19);
    memset_0(v19, 0, 16 * v9);
    v10 = 0;
    std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::_Unchecked_begin(
      &v21,
      &v20);
    v11 = v21;
    while ( v20 != v11 )
    {
      v14 = std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<CommandResult>>>::operator*(&v20);
      v15 = (HSTRING *)((char *)v19 + 16 * v10);
      string = 0;
      v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
      v16 = Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(&string, &v23);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14C,
          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
          (const char *)(unsigned int)v16,
          (int)string);
      v17 = WindowsDuplicateString(string, v15);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
          (const char *)(unsigned int)v17,
          (int)string);
      *((_DWORD *)v15 + 3) = *(_DWORD *)(v14 + 32);
      *((_DWORD *)v15 + 2) = 0;
      switch ( *(_DWORD *)(v14 + 36) )
      {
        case 1:
          *((_DWORD *)v15 + 2) = 1;
          break;
        case 2:
          *((_DWORD *)v15 + 2) = 2;
          break;
        case 3:
          *((_DWORD *)v15 + 2) = 3;
          break;
      }
      ++v10;
      WindowsDeleteString(string);
      std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<CommandResult>>>::operator++(&v20);
    }
    LODWORD(string) = 0;
    v12 = ULongLongToULong(v9, (unsigned int *)&string);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x165,
        (unsigned int)"onecoreuap\\admin\\prov\\provapi\\lib\\packageserver.cpp",
        (const char *)(unsigned int)v12,
        (int)string);
    *a3 = (struct Windows::Management::Provisioning::ProvCommandResult *)v19;
    *a2 = (unsigned int)string;
    v19 = 0;
    std::list<CommandResult>::~list<CommandResult>(&v21);
    std::wstring::~wstring(v25);
    return 0;
  }
  else
  {
    std::list<CommandResult>::~list<CommandResult>(&v21);
    std::wstring::~wstring(v25);
    return 0;
  }
}

```

## disassembly

```asm
0x18007aa70  push    rbx
0x18007aa72  push    rsi
0x18007aa73  push    rdi
0x18007aa74  push    r12
0x18007aa76  push    r13
0x18007aa78  push    r14
0x18007aa7a  push    r15
0x18007aa7c  sub     rsp, 80h
0x18007aa83  mov     rax, cs:__security_cookie
0x18007aa8a  xor     rax, rsp
0x18007aa8d  mov     [rsp+0B8h+var_40], rax
0x18007aa92  mov     r15, r8
0x18007aa95  mov     r14, rdx
0x18007aa98  mov     rbx, rcx
0x18007aa9b  xor     edi, edi
0x18007aa9d  mov     rcx, [rsp+0B8h]; this
0x18007aaa5  test    rdx, rdx
0x18007aaa8  jnz     short loc_18007AABB
0x18007aaaa  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007aab1  mov     edx, 135h; void *
0x18007aab6  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007aabb  mov     rcx, [rsp+0B8h]; this
0x18007aac3  test    r15, r15
0x18007aac6  jnz     short loc_18007AAD9
0x18007aac8  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007aacf  mov     edx, 136h; void *
0x18007aad4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007aad9  mov     [r8], rdi
0x18007aadc  mov     [rdx], edi
0x18007aade  mov     [rsp+0B8h+var_68], 0FFFFFFFF80000002h
0x18007aae7  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Provisioning\\Comm"...
0x18007aaee  lea     rcx, [rsp+0B8h+var_60]
0x18007aaf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007aaf8  nop
0x18007aaf9  lea     rcx, [rbx+68h]
0x18007aafd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ab02  mov     r9, rax
0x18007ab05  lea     rdx, [rsp+0B8h+var_80]
0x18007ab0a  lea     rcx, [rsp+0B8h+var_68]
0x18007ab0f  call    ?Parse@RegistryResults@@QEAA?AV?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@PEBG0@Z; RegistryResults::Parse(ushort const *,ushort const *)
0x18007ab14  nop
0x18007ab15  mov     rsi, [rsp+0B8h+var_78]
0x18007ab1a  test    rsi, rsi
0x18007ab1d  jz      loc_18007ACB5
0x18007ab23  mov     rdx, rsi
0x18007ab26  lea     rcx, [rsp+0B8h+var_90]
0x18007ab2b  call    ??$make_unique_cotaskmem@$$BY0A@UProvisioningMVUIItem@Provisioning@Management@Windows@@@wil@@YA?AV?$unique_ptr@$$BY0A@UProvisioningMVUIItem@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningMVUIItem [0]>(unsigned __int64)
0x18007ab30  nop
0x18007ab31  mov     r8, rsi
0x18007ab34  shl     r8, 4; Size
0x18007ab38  xor     edx, edx; Val
0x18007ab3a  mov     rcx, [rsp+0B8h+var_90]; void *
0x18007ab3f  call    memset_0
0x18007ab44  mov     r12, rdi
0x18007ab47  lea     rdx, [rsp+0B8h+var_88]
0x18007ab4c  lea     rcx, [rsp+0B8h+var_80]
0x18007ab51  call    ?_Unchecked_begin@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEBA?AV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@U_Iterator_base0@2@@2@XZ; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Unchecked_begin(void)
0x18007ab56  mov     rbx, [rsp+0B8h+var_80]
0x18007ab5b  cmp     [rsp+0B8h+var_88], rbx
0x18007ab60  jnz     short loc_18007ABC4
0x18007ab62  mov     dword ptr [rsp+0B8h+string], edi; int
0x18007ab66  lea     rdx, [rsp+0B8h+string]; unsigned int *
0x18007ab6b  mov     rcx, rsi; unsigned __int64
0x18007ab6e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18007ab73  mov     rcx, [rsp+0B8h]; this
0x18007ab7b  test    eax, eax
0x18007ab7d  jns     short loc_18007AB93
0x18007ab7f  mov     r9d, eax; char *
0x18007ab82  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007ab89  mov     edx, 165h; void *
0x18007ab8e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ab93  mov     rax, [rsp+0B8h+var_90]
0x18007ab98  mov     [r15], rax
0x18007ab9b  mov     eax, dword ptr [rsp+0B8h+string]
0x18007ab9f  mov     [r14], eax
0x18007aba2  mov     [rsp+0B8h+var_90], rdi
0x18007aba7  lea     rcx, [rsp+0B8h+var_80]
0x18007abac  call    ??1?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@XZ; std::list<CommandResult>::~list<CommandResult>(void)
0x18007abb1  nop
0x18007abb2  lea     rcx, [rsp+0B8h+var_60]
0x18007abb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007abbc  nop
0x18007abbd  xor     eax, eax
0x18007abbf  jmp     loc_18007ACD2
0x18007abc4  lea     rcx, [rsp+0B8h+var_88]
0x18007abc9  call    ??D?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@std@@@std@@QEBAAEAUCommandResult@@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<CommandResult>>>::operator*(void)
0x18007abce  mov     r13, rax
0x18007abd1  mov     rdi, r12
0x18007abd4  shl     rdi, 4
0x18007abd8  add     rdi, [rsp+0B8h+var_90]
0x18007abdd  mov     [rsp+0B8h+string], 0; int
0x18007abe6  mov     rcx, rax
0x18007abe9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007abee  mov     [rsp+0B8h+var_70], rax
0x18007abf3  lea     rdx, [rsp+0B8h+var_70]
0x18007abf8  lea     rcx, [rsp+0B8h+string]
0x18007abfd  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18007ac02  mov     rcx, [rsp+0B8h]; this
0x18007ac0a  test    eax, eax
0x18007ac0c  jns     short loc_18007AC22
0x18007ac0e  mov     r9d, eax; char *
0x18007ac11  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007ac18  mov     edx, 14Ch; void *
0x18007ac1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ac22  mov     rdx, rdi; newString
0x18007ac25  mov     rcx, [rsp+0B8h+string]; string
0x18007ac2a  call    cs:__imp_WindowsDuplicateString
0x18007ac31  nop     dword ptr [rax+rax+00h]
0x18007ac36  mov     rcx, [rsp+0B8h]; this
0x18007ac3e  test    eax, eax
0x18007ac40  jns     short loc_18007AC56
0x18007ac42  mov     r9d, eax; char *
0x18007ac45  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x18007ac4c  mov     edx, 14Dh; void *
0x18007ac51  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007ac56  mov     eax, [r13+20h]
0x18007ac5a  mov     [rdi+0Ch], eax
0x18007ac5d  mov     dword ptr [rdi+8], 0
0x18007ac64  mov     ecx, [r13+24h]
0x18007ac68  sub     ecx, 1
0x18007ac6b  jz      short loc_18007AC89
0x18007ac6d  sub     ecx, 1
0x18007ac70  jz      short loc_18007AC80
0x18007ac72  cmp     ecx, 1
0x18007ac75  jnz     short loc_18007AC90
0x18007ac77  mov     dword ptr [rdi+8], 3
0x18007ac7e  jmp     short loc_18007AC90
0x18007ac80  mov     dword ptr [rdi+8], 2
0x18007ac87  jmp     short loc_18007AC90
0x18007ac89  mov     dword ptr [rdi+8], 1
0x18007ac90  inc     r12
0x18007ac93  mov     rcx, [rsp+0B8h+string]; string
0x18007ac98  call    cs:__imp_WindowsDeleteString
0x18007ac9f  nop     dword ptr [rax+rax+00h]
0x18007aca4  lea     rcx, [rsp+0B8h+var_88]
0x18007aca9  call    ??E?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<CommandResult>>>::operator++(void)
0x18007acae  xor     edi, edi
0x18007acb0  jmp     loc_18007AB5B
0x18007acb5  lea     rcx, [rsp+0B8h+var_80]
0x18007acba  call    ??1?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@XZ; std::list<CommandResult>::~list<CommandResult>(void)
0x18007acbf  nop
0x18007acc0  lea     rcx, [rsp+0B8h+var_60]
0x18007acc5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007acca  xor     eax, eax
0x18007accc  jmp     short loc_18007ACD2
0x18007acce  mov     eax, dword ptr [rsp+0B8h+string]
0x18007acd2  mov     rcx, [rsp+0B8h+var_40]
0x18007acd7  xor     rcx, rsp; StackCookie
0x18007acda  call    __security_check_cookie
0x18007acdf  add     rsp, 80h
0x18007ace6  pop     r15
0x18007ace8  pop     r14
0x18007acea  pop     r13
0x18007acec  pop     r12
0x18007acee  pop     rdi
0x18007acef  pop     rsi
0x18007acf0  pop     rbx
0x18007acf1  retn
```
