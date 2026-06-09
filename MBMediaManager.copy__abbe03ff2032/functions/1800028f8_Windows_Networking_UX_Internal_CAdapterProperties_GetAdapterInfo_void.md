# Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterInfo(void)

- ea: `0x1800028f8`
- end: `0x180002bc2`
- name: `?GetAdapterInfo@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `714`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000217c`

## callees

- `0x1800028f8`
- `0x180002bd0`
- `0x1800034d4`
- `0x180003558`
- `0x180005c80`
- `0x1800198fc`
- `0x18001991c`
- `0x18001b1d4`
- `0x18001bdb8`
- `0x18001f5b8`
- `0x180026424`
- `0x18002cd20`
- `0x180053b54`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000296c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180002929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000296c`
- `IPHLPAPI!GetIfTable2Ex` at `0x1800029e2`
- `IPHLPAPI!GetIfTable2Ex` at `0x1800029e2`
- `IPHLPAPI!FreeMibTable` at `0x1800029bf`
- `IPHLPAPI!FreeMibTable` at `0x180002a11`
- `IPHLPAPI!FreeMibTable` at `0x1800029bf`
- `IPHLPAPI!FreeMibTable` at `0x180002a11`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=2
__int64 __fastcall Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterInfo(
        Windows::Networking::UX::Internal::CAdapterProperties *this)
{
  HSTRING *v2; // rbx
  int NetAdapterDriverProperty; // eax
  int v4; // eax
  unsigned int IfTable2; // eax
  unsigned int v6; // ebx
  unsigned int i; // edx
  const WCHAR *v9; // rbx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  const WCHAR *v13; // rax
  HRESULT v14; // eax
  char *v15; // rcx
  PVOID Memory; // [rsp+20h] [rbp-58h] BYREF
  const WCHAR *v17[3]; // [rsp+28h] [rbp-50h] BYREF
  _QWORD Src[4]; // [rsp+40h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v17[1] = (const WCHAR *)this;
  Memory = 0;
  v2 = (HSTRING *)((char *)this + 48);
  WindowsDeleteString(*((HSTRING *)this + 6));
  *v2 = 0;
  NetAdapterDriverProperty = Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(
                               this,
                               &DEVPKEY_Device_Manufacturer,
                               v2);
  if ( NetAdapterDriverProperty < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
      (const char *)(unsigned int)NetAdapterDriverProperty,
      (int)Memory);
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  v4 = Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(
         this,
         &DEVPKEY_Device_DriverVersion,
         (HSTRING *)this + 8);
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
    if ( Memory )
      FreeMibTable(Memory);
    return v6;
  }
  else
  {
    for ( i = 0; i < *(_DWORD *)Memory; ++i )
    {
      v9 = (const WCHAR *)(1352LL * i);
      v17[2] = v9;
      if ( (*((_BYTE *)Memory + (_QWORD)v9 + 1160) & 2) == 0 )
      {
        v10 = *(_QWORD *)((char *)Memory + (_QWORD)v9 + 20) - *((_QWORD *)this + 4);
        if ( !v10 )
          v10 = *(_QWORD *)((char *)Memory + (_QWORD)v9 + 28) - *((_QWORD *)this + 5);
        if ( !v10 )
        {
          v11 = Microsoft::WRL::Wrappers::HString::Set<257>(
                  (HSTRING *)this + 7,
                  (PCNZWCH)((char *)Memory + (_QWORD)v9 + 550));
          if ( v11 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1C0,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
              (const char *)(unsigned int)v11,
              (int)Memory);
          v12 = Microsoft::WRL::Wrappers::HString::Set<257>(
                  (HSTRING *)this + 11,
                  (PCNZWCH)((char *)Memory + (_QWORD)v9 + 36));
          if ( v12 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1C1,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
              (const char *)(unsigned int)v12,
              (int)Memory);
          Windows::Networking::UX::Internal::CAdapterProperties::FormatPhysicalAddress(Src);
          v13 = (const WCHAR *)Src;
          if ( Src[3] > 7u )
            v13 = (const WCHAR *)Src[0];
          v17[0] = v13;
          v14 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((HSTRING *)this + 9, v17);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x1C8,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
              (const char *)(unsigned int)v14,
              (int)Memory);
          std::wstring::_Tidy_deallocate(Src);
          v15 = (char *)Memory;
          *((_QWORD *)this + 21) = *(_QWORD *)((char *)Memory + (_QWORD)v9 + 1200);
          *((_QWORD *)this + 22) = *(_QWORD *)&v15[(_QWORD)v9 + 1208];
          break;
        }
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
0x1800028f8  mov     [rsp+arg_8], rbx
0x1800028fd  push    rdi
0x1800028fe  sub     rsp, 70h
0x180002902  mov     rax, cs:__security_cookie
0x180002909  xor     rax, rsp
0x18000290c  mov     [rsp+78h+var_18], rax
0x180002911  mov     rdi, rcx
0x180002914  mov     [rsp+78h+var_48], rcx
0x180002919  mov     [rsp+78h+Memory], 0; int
0x180002922  lea     rbx, [rcx+30h]
0x180002926  mov     rcx, [rbx]; string
0x180002929  call    cs:__imp_WindowsDeleteString
0x18000292f  mov     qword ptr [rbx], 0
0x180002936  mov     r8, rbx; HSTRING *
0x180002939  lea     rdx, DEVPKEY_Device_Manufacturer; struct _DEVPROPKEY *
0x180002940  mov     rcx, rdi; this
0x180002943  call    ?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)
0x180002948  mov     rcx, [rsp+78h]; this
0x18000294d  test    eax, eax
0x18000294f  jns     short loc_180002965
0x180002951  mov     r9d, eax; char *
0x180002954  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18000295b  mov     edx, 1B0h; void *
0x180002960  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002965  lea     rbx, [rdi+40h]
0x180002969  mov     rcx, [rbx]; string
0x18000296c  call    cs:__imp_WindowsDeleteString
0x180002972  mov     qword ptr [rbx], 0
0x180002979  mov     r8, rbx; HSTRING *
0x18000297c  lea     rdx, DEVPKEY_Device_DriverVersion; struct _DEVPROPKEY *
0x180002983  mov     rcx, rdi; this
0x180002986  call    ?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)
0x18000298b  mov     rcx, [rsp+78h]; this
0x180002990  test    eax, eax
0x180002992  jns     short loc_1800029A8
0x180002994  mov     r9d, eax; char *
0x180002997  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18000299e  mov     edx, 1B2h; void *
0x1800029a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800029a8  mov     rbx, [rsp+78h+Memory]
0x1800029ad  test    rbx, rbx
0x1800029b0  jz      short loc_1800029CF
0x1800029b2  lea     rcx, [rsp+78h+var_50]; this
0x1800029b7  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800029bc  mov     rcx, rbx; Memory
0x1800029bf  call    cs:__imp_FreeMibTable
0x1800029c5  lea     rcx, [rsp+78h+var_50]; this
0x1800029ca  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800029cf  mov     [rsp+78h+Memory], 0; int
0x1800029d8  lea     rdx, [rsp+78h+Memory]; Table
0x1800029dd  mov     ecx, 2; Level
0x1800029e2  call    cs:__imp_GetIfTable2Ex
0x1800029e8  test    eax, eax
0x1800029ea  jz      short loc_180002A1E
0x1800029ec  mov     rcx, [rsp+78h]; this
0x1800029f1  mov     r9d, eax; char *
0x1800029f4  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800029fb  mov     edx, 1B4h; void *
0x180002a00  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180002a05  mov     ebx, eax
0x180002a07  mov     rcx, [rsp+78h+Memory]; Memory
0x180002a0c  test    rcx, rcx
0x180002a0f  jz      short loc_180002A17
0x180002a11  call    cs:__imp_FreeMibTable
0x180002a17  mov     eax, ebx
0x180002a19  jmp     loc_180002B9E
0x180002a1e  xor     edx, edx
0x180002a20  mov     rax, [rsp+78h+Memory]
0x180002a25  cmp     edx, [rax]
0x180002a27  jnb     loc_180002B5A
0x180002a2d  mov     ecx, edx
0x180002a2f  imul    rbx, rcx, 548h
0x180002a36  mov     [rsp+78h+var_40], rbx
0x180002a3b  test    byte ptr [rbx+rax+488h], 2
0x180002a43  jnz     loc_180002BB9
0x180002a49  mov     rcx, [rbx+rax+14h]
0x180002a4e  sub     rcx, [rdi+20h]
0x180002a52  jnz     short loc_180002A5D
0x180002a54  mov     rcx, [rbx+rax+1Ch]
0x180002a59  sub     rcx, [rdi+28h]
0x180002a5d  test    rcx, rcx
0x180002a60  jnz     loc_180002BB9
0x180002a66  lea     rdx, [rax+226h]
0x180002a6d  add     rdx, rbx; sourceString
0x180002a70  lea     rcx, [rdi+38h]; string
0x180002a74  call    ??$Set@$0BAB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0BAB@G@Z; Microsoft::WRL::Wrappers::HString::Set<257>(ushort (&)[257])
0x180002a79  mov     rcx, [rsp+78h]; this
0x180002a7e  test    eax, eax
0x180002a80  jns     short loc_180002A96
0x180002a82  mov     r9d, eax; char *
0x180002a85  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180002a8c  mov     edx, 1C0h; void *
0x180002a91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002a96  mov     rdx, [rsp+78h+Memory]
0x180002a9b  add     rdx, 24h ; '$'
0x180002a9f  add     rdx, rbx; sourceString
0x180002aa2  lea     rcx, [rdi+58h]; string
0x180002aa6  call    ??$Set@$0BAB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0BAB@G@Z; Microsoft::WRL::Wrappers::HString::Set<257>(ushort (&)[257])
0x180002aab  mov     rcx, [rsp+78h]; this
0x180002ab0  test    eax, eax
0x180002ab2  jns     short loc_180002AC9
0x180002ab4  mov     r9d, eax; char *
0x180002ab7  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180002abe  mov     edx, 1C1h; void *
0x180002ac3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002ac8  nop
0x180002ac9  mov     rdx, [rsp+78h+Memory]
0x180002ace  add     rdx, 8
0x180002ad2  add     rdx, rbx
0x180002ad5  lea     rcx, [rsp+78h+Src]; Src
0x180002ada  call    ?FormatPhysicalAddress@CAdapterProperties@Internal@UX@Networking@Windows@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_MIB_IF_ROW2@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::FormatPhysicalAddress(_MIB_IF_ROW2 const &)
0x180002adf  lea     rcx, [rdi+48h]; string
0x180002ae3  lea     rax, [rsp+78h+Src]
0x180002ae8  cmp     [rsp+78h+var_20], 7
0x180002aee  cmova   rax, [rsp+78h+Src]
0x180002af4  mov     [rsp+78h+var_50], rax
0x180002af9  lea     rdx, [rsp+78h+var_50]
0x180002afe  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180002b03  mov     rcx, [rsp+78h]; this
0x180002b08  test    eax, eax
0x180002b0a  jns     short loc_180002B20
0x180002b0c  mov     r9d, eax; char *
0x180002b0f  lea     r8, aOnecoreuapNetU_2; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180002b16  mov     edx, 1C8h; void *
0x180002b1b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002b20  lea     rcx, [rsp+78h+Src]
0x180002b25  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180002b2a  nop
0x180002b2b  jmp     short loc_180002B37
0x180002b2d  mov     rdi, [rsp+78h+var_48]
0x180002b32  mov     rbx, [rsp+78h+var_40]
0x180002b37  mov     rcx, [rsp+78h+Memory]
0x180002b3c  mov     rax, [rbx+rcx+4B0h]
0x180002b44  mov     [rdi+0A8h], rax
0x180002b4b  mov     rax, [rbx+rcx+4B8h]
0x180002b53  mov     [rdi+0B0h], rax
0x180002b5a  lea     rax, WPP_GLOBAL_Control
0x180002b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b68  cmp     rcx, rax
0x180002b6b  jz      short loc_180002B8C
0x180002b6d  test    byte ptr [rcx+1Ch], 40h
0x180002b71  jz      short loc_180002B8C
0x180002b73  mov     edx, 12h
0x180002b78  xor     r9d, r9d
0x180002b7b  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180002b82  mov     rcx, [rcx+10h]
0x180002b86  call    WPP_SF_d
0x180002b8b  nop
0x180002b8c  lea     rcx, [rsp+78h+Memory]
0x180002b91  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x180002b96  xor     eax, eax
0x180002b98  jmp     short loc_180002B9E
0x180002b9a  mov     eax, dword ptr [rsp+78h+Memory]
0x180002b9e  mov     rcx, [rsp+78h+var_18]
0x180002ba3  xor     rcx, rsp; StackCookie
0x180002ba6  call    __security_check_cookie
0x180002bab  mov     rbx, [rsp+78h+arg_8]
0x180002bb3  add     rsp, 70h
0x180002bb7  pop     rdi
0x180002bb8  retn
0x180002bb9  inc     edx
0x180002bbb  jmp     loc_180002A25
```
