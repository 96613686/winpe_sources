# Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterInfo(void)

- ea: `0x180082280`
- end: `0x18008253e`
- name: `?GetAdapterInfo@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `702`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800849f8`

## callees

- `0x180003ed0`
- `0x180007a2c`
- `0x180007d10`
- `0x18001668c`
- `0x18001b230`
- `0x18001b838`
- `0x18001c044`
- `0x18001d4d4`
- `0x18001d6d0`
- `0x1800373ec`
- `0x18007d714`
- `0x180082004`
- `0x180082280`
- `0x180083154`

## import_xrefs

- `IPHLPAPI!GetIfTable2Ex` at `0x18008236a`
- `IPHLPAPI!GetIfTable2Ex` at `0x18008236a`
- `IPHLPAPI!FreeMibTable` at `0x180082347`
- `IPHLPAPI!FreeMibTable` at `0x180082347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800822b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800822f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800822b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800822f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=2
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterInfo(HSTRING *this)
{
  HSTRING *v2; // rbx
  int NetAdapterDriverProperty; // eax
  int v4; // eax
  unsigned int IfTable2; // eax
  unsigned int v6; // ebx
  unsigned int i; // edx
  __int64 v9; // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  char *v15; // rcx
  PVOID Memory; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v17[3]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v17[1] = this;
  Memory = 0;
  v2 = this + 6;
  WindowsDeleteString(this[6]);
  *v2 = 0;
  NetAdapterDriverProperty = Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(
                               (Windows::Networking::UX::Internal::CAdapterProperties *)this,
                               &DEVPKEY_Device_Manufacturer,
                               v2);
  if ( NetAdapterDriverProperty < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
      (const char *)(unsigned int)NetAdapterDriverProperty,
      (int)Memory);
  WindowsDeleteString(this[8]);
  this[8] = 0;
  v4 = Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(
         (Windows::Networking::UX::Internal::CAdapterProperties *)this,
         &DEVPKEY_Device_DriverVersion,
         this + 8);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B2,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
      (const char *)(unsigned int)v4,
      (int)Memory);
  if ( Memory )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v17);
    FreeMibTable(Memory);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v17);
  }
  Memory = 0;
  IfTable2 = GetIfTable2Ex((MIB_IF_TABLE_LEVEL)2, (PMIB_IF_TABLE2 *)&Memory);
  if ( IfTable2 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1B4,
           (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
           (const char *)IfTable2,
           (unsigned int)Memory);
    wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Memory);
    return v6;
  }
  else
  {
    for ( i = 0; i < *(_DWORD *)Memory; ++i )
    {
      v9 = 1352LL * i;
      v17[2] = v9;
      if ( (*((_BYTE *)Memory + v9 + 1160) & 2) == 0
        && *(HSTRING *)((char *)Memory + v9 + 20) == this[4]
        && *(HSTRING *)((char *)Memory + v9 + 28) == this[5] )
      {
        v10 = Microsoft::WRL::Wrappers::HString::Set<65>(this + 7, (char *)Memory + v9 + 550);
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C0,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
            (const char *)(unsigned int)v10,
            (int)Memory);
        v11 = Microsoft::WRL::Wrappers::HString::Set<65>(this + 11, (char *)Memory + v9 + 36);
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C1,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
            (const char *)(unsigned int)v11,
            (int)Memory);
        Windows::Networking::UX::Internal::CAdapterProperties::FormatPhysicalAddress(v18, (char *)Memory + v9 + 8);
        v17[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18, v12, v13);
        v14 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(this + 9, v17);
        if ( v14 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C8,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
            (const char *)(unsigned int)v14,
            (int)Memory);
        std::wstring::_Tidy_deallocate(v18);
        v15 = (char *)Memory;
        this[21] = *(HSTRING *)((char *)Memory + v9 + 1200);
        this[22] = *(HSTRING *)&v15[v9 + 1208];
        break;
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_07bd92578572370284dbe53730fdfa75_Traceguids, 0);
    wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&void FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(&Memory);
    return 0;
  }
}

```

## disassembly

```asm
0x180082280  mov     [rsp+arg_8], rbx
0x180082285  push    rdi
0x180082286  sub     rsp, 70h
0x18008228a  mov     rax, cs:__security_cookie
0x180082291  xor     rax, rsp
0x180082294  mov     [rsp+78h+var_18], rax
0x180082299  mov     rdi, rcx
0x18008229c  mov     [rsp+78h+var_48], rcx
0x1800822a1  mov     [rsp+78h+Memory], 0; int
0x1800822aa  lea     rbx, [rcx+30h]
0x1800822ae  mov     rcx, [rbx]; string
0x1800822b1  call    cs:__imp_WindowsDeleteString
0x1800822b7  mov     qword ptr [rbx], 0
0x1800822be  mov     r8, rbx; HSTRING *
0x1800822c1  lea     rdx, DEVPKEY_Device_Manufacturer; struct _DEVPROPKEY *
0x1800822c8  mov     rcx, rdi; this
0x1800822cb  call    ?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)
0x1800822d0  mov     rcx, [rsp+78h]; this
0x1800822d5  test    eax, eax
0x1800822d7  jns     short loc_1800822ED
0x1800822d9  mov     r9d, eax; char *
0x1800822dc  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800822e3  mov     edx, 1B0h; void *
0x1800822e8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800822ed  lea     rbx, [rdi+40h]
0x1800822f1  mov     rcx, [rbx]; string
0x1800822f4  call    cs:__imp_WindowsDeleteString
0x1800822fa  mov     qword ptr [rbx], 0
0x180082301  mov     r8, rbx; HSTRING *
0x180082304  lea     rdx, DEVPKEY_Device_DriverVersion; struct _DEVPROPKEY *
0x18008230b  mov     rcx, rdi; this
0x18008230e  call    ?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)
0x180082313  mov     rcx, [rsp+78h]; this
0x180082318  test    eax, eax
0x18008231a  jns     short loc_180082330
0x18008231c  mov     r9d, eax; char *
0x18008231f  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180082326  mov     edx, 1B2h; void *
0x18008232b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082330  mov     rbx, [rsp+78h+Memory]
0x180082335  test    rbx, rbx
0x180082338  jz      short loc_180082357
0x18008233a  lea     rcx, [rsp+78h+var_50]; this
0x18008233f  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180082344  mov     rcx, rbx; Memory
0x180082347  call    cs:__imp_FreeMibTable
0x18008234d  lea     rcx, [rsp+78h+var_50]; this
0x180082352  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180082357  mov     [rsp+78h+Memory], 0; int
0x180082360  lea     rdx, [rsp+78h+Memory]; Table
0x180082365  mov     ecx, 2; Level
0x18008236a  call    cs:__imp_GetIfTable2Ex
0x180082370  test    eax, eax
0x180082372  jz      short loc_1800823A0
0x180082374  mov     rcx, [rsp+78h]; this
0x180082379  mov     r9d, eax; char *
0x18008237c  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180082383  mov     edx, 1B4h; void *
0x180082388  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008238d  mov     ebx, eax
0x18008238f  lea     rcx, [rsp+78h+Memory]
0x180082394  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x180082399  mov     eax, ebx
0x18008239b  jmp     loc_18008251A
0x1800823a0  xor     edx, edx
0x1800823a2  mov     rax, [rsp+78h+Memory]
0x1800823a7  cmp     edx, [rax]
0x1800823a9  jnb     loc_1800824D6
0x1800823af  mov     ecx, edx
0x1800823b1  imul    rbx, rcx, 548h
0x1800823b8  mov     [rsp+78h+var_40], rbx
0x1800823bd  test    byte ptr [rbx+rax+488h], 2
0x1800823c5  jnz     loc_180082535
0x1800823cb  mov     rcx, [rbx+rax+14h]
0x1800823d0  cmp     rcx, [rdi+20h]
0x1800823d4  jnz     loc_180082535
0x1800823da  mov     rcx, [rbx+rax+1Ch]
0x1800823df  cmp     rcx, [rdi+28h]
0x1800823e3  jnz     loc_180082535
0x1800823e9  lea     rdx, [rax+226h]
0x1800823f0  add     rdx, rbx
0x1800823f3  lea     rcx, [rdi+38h]
0x1800823f7  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x1800823fc  mov     rcx, [rsp+78h]; this
0x180082401  test    eax, eax
0x180082403  jns     short loc_180082419
0x180082405  mov     r9d, eax; char *
0x180082408  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18008240f  mov     edx, 1C0h; void *
0x180082414  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180082419  mov     rdx, [rsp+78h+Memory]
0x18008241e  add     rdx, 24h ; '$'
0x180082422  add     rdx, rbx
0x180082425  lea     rcx, [rdi+58h]
0x180082429  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x18008242e  mov     rcx, [rsp+78h]; this
0x180082433  test    eax, eax
0x180082435  jns     short loc_18008244C
0x180082437  mov     r9d, eax; char *
0x18008243a  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180082441  mov     edx, 1C1h; void *
0x180082446  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008244b  nop
0x18008244c  mov     rdx, [rsp+78h+Memory]
0x180082451  add     rdx, 8
0x180082455  add     rdx, rbx
0x180082458  lea     rcx, [rsp+78h+var_38]
0x18008245d  call    ?FormatPhysicalAddress@CAdapterProperties@Internal@UX@Networking@Windows@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_MIB_IF_ROW2@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::FormatPhysicalAddress(_MIB_IF_ROW2 const &)
0x180082462  lea     rcx, [rsp+78h+var_38]
0x180082467  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18008246c  mov     [rsp+78h+var_50], rax
0x180082471  lea     rcx, [rdi+48h]
0x180082475  lea     rdx, [rsp+78h+var_50]
0x18008247a  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x18008247f  mov     rcx, [rsp+78h]; this
0x180082484  test    eax, eax
0x180082486  jns     short loc_18008249C
0x180082488  mov     r9d, eax; char *
0x18008248b  lea     r8, aOnecoreuapNetU_4; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180082492  mov     edx, 1C8h; void *
0x180082497  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008249c  lea     rcx, [rsp+78h+var_38]
0x1800824a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800824a6  nop
0x1800824a7  jmp     short loc_1800824B3
0x1800824a9  mov     rdi, [rsp+78h+var_48]
0x1800824ae  mov     rbx, [rsp+78h+var_40]
0x1800824b3  mov     rcx, [rsp+78h+Memory]
0x1800824b8  mov     rax, [rbx+rcx+4B0h]
0x1800824c0  mov     [rdi+0A8h], rax
0x1800824c7  mov     rax, [rbx+rcx+4B8h]
0x1800824cf  mov     [rdi+0B0h], rax
0x1800824d6  lea     rax, WPP_GLOBAL_Control
0x1800824dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800824e4  cmp     rcx, rax
0x1800824e7  jz      short loc_180082508
0x1800824e9  test    byte ptr [rcx+1Ch], 40h
0x1800824ed  jz      short loc_180082508
0x1800824ef  mov     edx, 12h
0x1800824f4  xor     r9d, r9d
0x1800824f7  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x1800824fe  mov     rcx, [rcx+10h]
0x180082502  call    WPP_SF_d
0x180082507  nop
0x180082508  lea     rcx, [rsp+78h+Memory]
0x18008250d  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x180082512  xor     eax, eax
0x180082514  jmp     short loc_18008251A
0x180082516  mov     eax, dword ptr [rsp+78h+Memory]
0x18008251a  mov     rcx, [rsp+78h+var_18]
0x18008251f  xor     rcx, rsp; StackCookie
0x180082522  call    __security_check_cookie
0x180082527  mov     rbx, [rsp+78h+arg_8]
0x18008252f  add     rsp, 70h
0x180082533  pop     rdi
0x180082534  retn
0x180082535  inc     edx
0x180082537  jmp     loc_1800823A7
```
