# Windows::Management::Provisioning::PackageServer::GetProvCommandResults(uint *,Windows::Management::Provisioning::ProvCommandResult * *)

- ea: `0x180079260`
- end: `0x1800794d7`
- name: `?GetProvCommandResults@PackageServer@Provisioning@Management@Windows@@UEAAJPEAIPEAPEAUProvCommandResult@234@@Z`
- size: `631`
- prototype: `__int64 __fastcall(Windows::Management::Provisioning::PackageServer *__hidden this, unsigned int *, struct Windows::Management::Provisioning::ProvCommandResult **)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004d50`
- `0x180005904`
- `0x18000cfdc`
- `0x18000d724`
- `0x1800168d0`
- `0x180019ae4`
- `0x18001e414`
- `0x18003ec00`
- `0x18006e250`
- `0x18006ec38`
- `0x180078e84`
- `0x180078ff0`
- `0x180079020`
- `0x180079260`
- `0x18007a314`
- `0x1800a8650`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007941a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18007941a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079482`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180079482`

## string_xrefs

- `0x1800792d7`: `SOFTWARE\Microsoft\Provisioning\CommandResults`

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
0x180079260  push    rbx
0x180079262  push    rsi
0x180079263  push    rdi
0x180079264  push    r12
0x180079266  push    r13
0x180079268  push    r14
0x18007926a  push    r15
0x18007926c  sub     rsp, 80h
0x180079273  mov     rax, cs:__security_cookie
0x18007927a  xor     rax, rsp
0x18007927d  mov     [rsp+0B8h+var_40], rax
0x180079282  mov     r15, r8
0x180079285  mov     r14, rdx
0x180079288  mov     rbx, rcx
0x18007928b  xor     edi, edi
0x18007928d  mov     rcx, [rsp+0B8h]; this
0x180079295  test    rdx, rdx
0x180079298  jnz     short loc_1800792AB
0x18007929a  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800792a1  mov     edx, 135h; void *
0x1800792a6  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800792ab  mov     rcx, [rsp+0B8h]; this
0x1800792b3  test    r15, r15
0x1800792b6  jnz     short loc_1800792C9
0x1800792b8  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x1800792bf  mov     edx, 136h; void *
0x1800792c4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800792c9  mov     [r8], rdi
0x1800792cc  mov     [rdx], edi
0x1800792ce  mov     [rsp+0B8h+var_68], 0FFFFFFFF80000002h
0x1800792d7  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Provisioning\\Comm"...
0x1800792de  lea     rcx, [rsp+0B8h+var_60]
0x1800792e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800792e8  nop
0x1800792e9  lea     rcx, [rbx+68h]
0x1800792ed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800792f2  mov     r9, rax
0x1800792f5  lea     rdx, [rsp+0B8h+var_80]
0x1800792fa  lea     rcx, [rsp+0B8h+var_68]
0x1800792ff  call    ?Parse@RegistryResults@@QEAA?AV?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@PEBG0@Z; RegistryResults::Parse(ushort const *,ushort const *)
0x180079304  nop
0x180079305  mov     rsi, [rsp+0B8h+var_78]
0x18007930a  test    rsi, rsi
0x18007930d  jz      loc_180079499
0x180079313  mov     rdx, rsi
0x180079316  lea     rcx, [rsp+0B8h+var_90]
0x18007931b  call    ??$make_unique_cotaskmem@$$BY0A@UProvisioningMVUIItem@Provisioning@Management@Windows@@@wil@@YA?AV?$unique_ptr@$$BY0A@UProvisioningMVUIItem@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<Windows::Management::Provisioning::ProvisioningMVUIItem [0]>(unsigned __int64)
0x180079320  nop
0x180079321  mov     r8, rsi
0x180079324  shl     r8, 4; Size
0x180079328  xor     edx, edx; Val
0x18007932a  mov     rcx, [rsp+0B8h+var_90]; void *
0x18007932f  call    memset_0
0x180079334  mov     r12, rdi
0x180079337  lea     rdx, [rsp+0B8h+var_88]
0x18007933c  lea     rcx, [rsp+0B8h+var_80]
0x180079341  call    ?_Unchecked_begin@?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEBA?AV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@I@std@@@std@@U_Iterator_base0@2@@2@XZ; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::_Unchecked_begin(void)
0x180079346  mov     rbx, [rsp+0B8h+var_80]
0x18007934b  cmp     [rsp+0B8h+var_88], rbx
0x180079350  jnz     short loc_1800793B4
0x180079352  mov     dword ptr [rsp+0B8h+string], edi; int
0x180079356  lea     rdx, [rsp+0B8h+string]; unsigned int *
0x18007935b  mov     rcx, rsi; unsigned __int64
0x18007935e  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180079363  mov     rcx, [rsp+0B8h]; this
0x18007936b  test    eax, eax
0x18007936d  jns     short loc_180079383
0x18007936f  mov     r9d, eax; char *
0x180079372  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079379  mov     edx, 165h; void *
0x18007937e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180079383  mov     rax, [rsp+0B8h+var_90]
0x180079388  mov     [r15], rax
0x18007938b  mov     eax, dword ptr [rsp+0B8h+string]
0x18007938f  mov     [r14], eax
0x180079392  mov     [rsp+0B8h+var_90], rdi
0x180079397  lea     rcx, [rsp+0B8h+var_80]
0x18007939c  call    ??1?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@XZ; std::list<CommandResult>::~list<CommandResult>(void)
0x1800793a1  nop
0x1800793a2  lea     rcx, [rsp+0B8h+var_60]
0x1800793a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800793ac  nop
0x1800793ad  xor     eax, eax
0x1800793af  jmp     loc_1800794B6
0x1800793b4  lea     rcx, [rsp+0B8h+var_88]
0x1800793b9  call    ??D?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@std@@@std@@QEBAAEAUCommandResult@@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<CommandResult>>>::operator*(void)
0x1800793be  mov     r13, rax
0x1800793c1  mov     rdi, r12
0x1800793c4  shl     rdi, 4
0x1800793c8  add     rdi, [rsp+0B8h+var_90]
0x1800793cd  mov     [rsp+0B8h+string], 0; int
0x1800793d6  mov     rcx, rax
0x1800793d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800793de  mov     [rsp+0B8h+var_70], rax
0x1800793e3  lea     rdx, [rsp+0B8h+var_70]
0x1800793e8  lea     rcx, [rsp+0B8h+string]
0x1800793ed  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x1800793f2  mov     rcx, [rsp+0B8h]; this
0x1800793fa  test    eax, eax
0x1800793fc  jns     short loc_180079412
0x1800793fe  mov     r9d, eax; char *
0x180079401  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079408  mov     edx, 14Ch; void *
0x18007940d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180079412  mov     rdx, rdi; newString
0x180079415  mov     rcx, [rsp+0B8h+string]; string
0x18007941a  call    cs:__imp_WindowsDuplicateString
0x180079420  mov     rcx, [rsp+0B8h]; this
0x180079428  test    eax, eax
0x18007942a  jns     short loc_180079440
0x18007942c  mov     r9d, eax; char *
0x18007942f  lea     r8, aOnecoreuapAdmi_29; "onecoreuap\\admin\\prov\\provapi\\lib\\"...
0x180079436  mov     edx, 14Dh; void *
0x18007943b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180079440  mov     eax, [r13+20h]
0x180079444  mov     [rdi+0Ch], eax
0x180079447  mov     dword ptr [rdi+8], 0
0x18007944e  mov     ecx, [r13+24h]
0x180079452  sub     ecx, 1
0x180079455  jz      short loc_180079473
0x180079457  sub     ecx, 1
0x18007945a  jz      short loc_18007946A
0x18007945c  cmp     ecx, 1
0x18007945f  jnz     short loc_18007947A
0x180079461  mov     dword ptr [rdi+8], 3
0x180079468  jmp     short loc_18007947A
0x18007946a  mov     dword ptr [rdi+8], 2
0x180079471  jmp     short loc_18007947A
0x180079473  mov     dword ptr [rdi+8], 1
0x18007947a  inc     r12
0x18007947d  mov     rcx, [rsp+0B8h+string]; string
0x180079482  call    cs:__imp_WindowsDeleteString
0x180079488  lea     rcx, [rsp+0B8h+var_88]
0x18007948d  call    ??E?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@UCommandResult@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<CommandResult>>>::operator++(void)
0x180079492  xor     edi, edi
0x180079494  jmp     loc_18007934B
0x180079499  lea     rcx, [rsp+0B8h+var_80]
0x18007949e  call    ??1?$list@UCommandResult@@V?$allocator@UCommandResult@@@std@@@std@@QEAA@XZ; std::list<CommandResult>::~list<CommandResult>(void)
0x1800794a3  nop
0x1800794a4  lea     rcx, [rsp+0B8h+var_60]
0x1800794a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800794ae  xor     eax, eax
0x1800794b0  jmp     short loc_1800794B6
0x1800794b2  mov     eax, dword ptr [rsp+0B8h+string]
0x1800794b6  mov     rcx, [rsp+0B8h+var_40]
0x1800794bb  xor     rcx, rsp; StackCookie
0x1800794be  call    __security_check_cookie
0x1800794c3  add     rsp, 80h
0x1800794ca  pop     r15
0x1800794cc  pop     r14
0x1800794ce  pop     r13
0x1800794d0  pop     r12
0x1800794d2  pop     rdi
0x1800794d3  pop     rsi
0x1800794d4  pop     rbx
0x1800794d5  retn
```
