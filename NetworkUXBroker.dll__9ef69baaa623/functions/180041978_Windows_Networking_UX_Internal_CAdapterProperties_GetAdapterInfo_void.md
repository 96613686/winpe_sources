# Windows::Networking::UX::Internal::CAdapterProperties::GetAdapterInfo(void)

- ea: `0x180041978`
- end: `0x180041c36`
- name: `?GetAdapterInfo@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `702`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CAdapterProperties *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042718`

## callees

- `0x180002520`
- `0x18000b43c`
- `0x18000f054`
- `0x18000f0b0`
- `0x180011984`
- `0x180011dfc`
- `0x18001a2d0`
- `0x180030678`
- `0x180037c4c`
- `0x18003e404`
- `0x180040dbc`
- `0x180041658`
- `0x180041978`
- `0x1800421ec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800419ec`
- `IPHLPAPI!FreeMibTable` at `0x180041a3f`
- `IPHLPAPI!FreeMibTable` at `0x180041a3f`
- `IPHLPAPI!GetIfTable2Ex` at `0x180041a62`
- `IPHLPAPI!GetIfTable2Ex` at `0x180041a62`

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
        v10 = Microsoft::WRL::Wrappers::HString::Set<65>(
                (Microsoft::WRL::Wrappers::HString *)(this + 7),
                (unsigned __int16 *)((char *)Memory + v9 + 550));
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C0,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
            (const char *)(unsigned int)v10,
            (int)Memory);
        v11 = Microsoft::WRL::Wrappers::HString::Set<65>(
                (Microsoft::WRL::Wrappers::HString *)(this + 11),
                (unsigned __int16 *)((char *)Memory + v9 + 36));
        if ( v11 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C1,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\cadapterproperties.cpp",
            (const char *)(unsigned int)v11,
            (int)Memory);
        Windows::Networking::UX::Internal::CAdapterProperties::FormatPhysicalAddress(v18, (char *)Memory + v9 + 8);
        v17[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18, v12, v13);
        v14 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>((Microsoft::WRL::Wrappers::HString *)(this + 9));
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
0x180041978  mov     [rsp+arg_8], rbx
0x18004197d  push    rdi
0x18004197e  sub     rsp, 70h
0x180041982  mov     rax, cs:__security_cookie
0x180041989  xor     rax, rsp
0x18004198c  mov     [rsp+78h+var_18], rax
0x180041991  mov     rdi, rcx
0x180041994  mov     [rsp+78h+var_48], rcx
0x180041999  mov     [rsp+78h+Memory], 0; int
0x1800419a2  lea     rbx, [rcx+30h]
0x1800419a6  mov     rcx, [rbx]; string
0x1800419a9  call    cs:__imp_WindowsDeleteString
0x1800419af  mov     qword ptr [rbx], 0
0x1800419b6  mov     r8, rbx; HSTRING *
0x1800419b9  lea     rdx, DEVPKEY_Device_Manufacturer; struct _DEVPROPKEY *
0x1800419c0  mov     rcx, rdi; this
0x1800419c3  call    ?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)
0x1800419c8  mov     rcx, [rsp+78h]; this
0x1800419cd  test    eax, eax
0x1800419cf  jns     short loc_1800419E5
0x1800419d1  mov     r9d, eax; char *
0x1800419d4  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x1800419db  mov     edx, 1B0h; void *
0x1800419e0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800419e5  lea     rbx, [rdi+40h]
0x1800419e9  mov     rcx, [rbx]; string
0x1800419ec  call    cs:__imp_WindowsDeleteString
0x1800419f2  mov     qword ptr [rbx], 0
0x1800419f9  mov     r8, rbx; HSTRING *
0x1800419fc  lea     rdx, DEVPKEY_Device_DriverVersion; struct _DEVPROPKEY *
0x180041a03  mov     rcx, rdi; this
0x180041a06  call    ?GetNetAdapterDriverProperty@CAdapterProperties@Internal@UX@Networking@Windows@@AEAAJAEBU_DEVPROPKEY@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::GetNetAdapterDriverProperty(_DEVPROPKEY const &,HSTRING__ * *)
0x180041a0b  mov     rcx, [rsp+78h]; this
0x180041a10  test    eax, eax
0x180041a12  jns     short loc_180041A28
0x180041a14  mov     r9d, eax; char *
0x180041a17  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180041a1e  mov     edx, 1B2h; void *
0x180041a23  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041a28  mov     rbx, [rsp+78h+Memory]
0x180041a2d  test    rbx, rbx
0x180041a30  jz      short loc_180041A4F
0x180041a32  lea     rcx, [rsp+78h+var_50]; this
0x180041a37  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180041a3c  mov     rcx, rbx; Memory
0x180041a3f  call    cs:__imp_FreeMibTable
0x180041a45  lea     rcx, [rsp+78h+var_50]; this
0x180041a4a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180041a4f  mov     [rsp+78h+Memory], 0; int
0x180041a58  lea     rdx, [rsp+78h+Memory]; Table
0x180041a5d  mov     ecx, 2; Level
0x180041a62  call    cs:__imp_GetIfTable2Ex
0x180041a68  test    eax, eax
0x180041a6a  jz      short loc_180041A98
0x180041a6c  mov     rcx, [rsp+78h]; this
0x180041a71  mov     r9d, eax; char *
0x180041a74  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180041a7b  mov     edx, 1B4h; void *
0x180041a80  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180041a85  mov     ebx, eax
0x180041a87  lea     rcx, [rsp+78h+Memory]
0x180041a8c  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x180041a91  mov     eax, ebx
0x180041a93  jmp     loc_180041C12
0x180041a98  xor     edx, edx
0x180041a9a  mov     rax, [rsp+78h+Memory]
0x180041a9f  cmp     edx, [rax]
0x180041aa1  jnb     loc_180041BCE
0x180041aa7  mov     ecx, edx
0x180041aa9  imul    rbx, rcx, 548h
0x180041ab0  mov     [rsp+78h+var_40], rbx
0x180041ab5  test    byte ptr [rbx+rax+488h], 2
0x180041abd  jnz     loc_180041C2D
0x180041ac3  mov     rcx, [rbx+rax+14h]
0x180041ac8  cmp     rcx, [rdi+20h]
0x180041acc  jnz     loc_180041C2D
0x180041ad2  mov     rcx, [rbx+rax+1Ch]
0x180041ad7  cmp     rcx, [rdi+28h]
0x180041adb  jnz     loc_180041C2D
0x180041ae1  lea     rdx, [rax+226h]
0x180041ae8  add     rdx, rbx; unsigned __int16 *
0x180041aeb  lea     rcx, [rdi+38h]; this
0x180041aef  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180041af4  mov     rcx, [rsp+78h]; this
0x180041af9  test    eax, eax
0x180041afb  jns     short loc_180041B11
0x180041afd  mov     r9d, eax; char *
0x180041b00  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180041b07  mov     edx, 1C0h; void *
0x180041b0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041b11  mov     rdx, [rsp+78h+Memory]
0x180041b16  add     rdx, 24h ; '$'
0x180041b1a  add     rdx, rbx; unsigned __int16 *
0x180041b1d  lea     rcx, [rdi+58h]; this
0x180041b21  call    ??$Set@$0EB@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0EB@G@Z; Microsoft::WRL::Wrappers::HString::Set<65>(ushort (&)[65])
0x180041b26  mov     rcx, [rsp+78h]; this
0x180041b2b  test    eax, eax
0x180041b2d  jns     short loc_180041B44
0x180041b2f  mov     r9d, eax; char *
0x180041b32  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180041b39  mov     edx, 1C1h; void *
0x180041b3e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041b43  nop
0x180041b44  mov     rdx, [rsp+78h+Memory]
0x180041b49  add     rdx, 8
0x180041b4d  add     rdx, rbx
0x180041b50  lea     rcx, [rsp+78h+var_38]
0x180041b55  call    ?FormatPhysicalAddress@CAdapterProperties@Internal@UX@Networking@Windows@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_MIB_IF_ROW2@@@Z; Windows::Networking::UX::Internal::CAdapterProperties::FormatPhysicalAddress(_MIB_IF_ROW2 const &)
0x180041b5a  lea     rcx, [rsp+78h+var_38]
0x180041b5f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180041b64  mov     [rsp+78h+var_50], rax
0x180041b69  lea     rcx, [rdi+48h]; this
0x180041b6d  lea     rdx, [rsp+78h+var_50]
0x180041b72  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180041b77  mov     rcx, [rsp+78h]; this
0x180041b7c  test    eax, eax
0x180041b7e  jns     short loc_180041B94
0x180041b80  mov     r9d, eax; char *
0x180041b83  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x180041b8a  mov     edx, 1C8h; void *
0x180041b8f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041b94  lea     rcx, [rsp+78h+var_38]
0x180041b99  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180041b9e  nop
0x180041b9f  jmp     short loc_180041BAB
0x180041ba1  mov     rdi, [rsp+78h+var_48]
0x180041ba6  mov     rbx, [rsp+78h+var_40]
0x180041bab  mov     rcx, [rsp+78h+Memory]
0x180041bb0  mov     rax, [rbx+rcx+4B0h]
0x180041bb8  mov     [rdi+0A8h], rax
0x180041bbf  mov     rax, [rbx+rcx+4B8h]
0x180041bc7  mov     [rdi+0B0h], rax
0x180041bce  lea     rax, WPP_GLOBAL_Control
0x180041bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180041bdc  cmp     rcx, rax
0x180041bdf  jz      short loc_180041C00
0x180041be1  test    byte ptr [rcx+1Ch], 40h
0x180041be5  jz      short loc_180041C00
0x180041be7  mov     edx, 12h
0x180041bec  xor     r9d, r9d
0x180041bef  lea     r8, WPP_07bd92578572370284dbe53730fdfa75_Traceguids
0x180041bf6  mov     rcx, [rcx+10h]
0x180041bfa  call    WPP_SF_d
0x180041bff  nop
0x180041c00  lea     rcx, [rsp+78h+Memory]
0x180041c05  call    ??1?$unique_storage@U?$resource_policy@PEAU_MIB_IF_TABLE2@@P6AXPEAX@Z$1?FreeMibTable@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_MIB_IF_TABLE2 *,void (*)(void *),&FreeMibTable(void *),wistd::integral_constant<unsigned __int64,0>,_MIB_IF_TABLE2 *,_MIB_IF_TABLE2 *,0,std::nullptr_t>>(void)
0x180041c0a  xor     eax, eax
0x180041c0c  jmp     short loc_180041C12
0x180041c0e  mov     eax, dword ptr [rsp+78h+Memory]
0x180041c12  mov     rcx, [rsp+78h+var_18]
0x180041c17  xor     rcx, rsp; StackCookie
0x180041c1a  call    __security_check_cookie
0x180041c1f  mov     rbx, [rsp+78h+arg_8]
0x180041c27  add     rsp, 70h
0x180041c2b  pop     rdi
0x180041c2c  retn
0x180041c2d  inc     edx
0x180041c2f  jmp     loc_180041A9F
```
