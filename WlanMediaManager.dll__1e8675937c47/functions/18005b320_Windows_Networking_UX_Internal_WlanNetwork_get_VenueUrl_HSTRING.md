# Windows::Networking::UX::Internal::WlanNetwork::get_VenueUrl(HSTRING__ * *)

- ea: `0x18005b320`
- end: `0x18005b4cf`
- name: `?get_VenueUrl@WlanNetwork@Internal@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `431`
- prototype: `int(Windows::Networking::UX::Internal::WlanNetwork *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x1800097b4`
- `0x18000de4c`
- `0x180012228`
- `0x18001668c`
- `0x18001d4d4`
- `0x1800287a0`
- `0x18005b320`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005b437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005b437`
- `wlanapi!WlanPrivateGetAnqpVenueUrl` at `0x18005b3f5`
- `wlanapi!WlanPrivateGetAnqpVenueUrl` at `0x18005b3f5`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetwork::get_VenueUrl(
        Windows::Networking::UX::Internal::WlanNetwork *this,
        HSTRING *a2)
{
  __int64 v4; // rax
  __int64 result; // rax
  unsigned int AnqpVenueUrl; // eax
  unsigned int v7; // ebx
  const char *v8; // r9
  HRESULT String; // eax
  unsigned int v10; // ebx
  UINT32 length; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v12[8]; // [rsp+28h] [rbp-220h] BYREF
  WCHAR sourceString[256]; // [rsp+30h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids);
  v4 = *((_QWORD *)this + 18);
  if ( (*(_BYTE *)(v4 + 620) & 0x10) != 0 )
  {
    try
    {
      wil::impersonate_token(v12);
      memset_0(sourceString, 0, 0x1FCu);
      length = 254;
      AnqpVenueUrl = WlanPrivateGetAnqpVenueUrl(*((_QWORD *)this + 18) + 512LL, 0, &length, sourceString);
      if ( AnqpVenueUrl )
      {
        v7 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x312,
               (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlannetwork.cpp",
               (const char *)AnqpVenueUrl,
               length);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v12);
        result = v7;
      }
      else
      {
        String = WindowsCreateString(sourceString, length, a2);
        v10 = String;
        if ( String >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids, 0);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v12);
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x313,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlannetwork.cpp",
            (const char *)(unsigned int)String,
            length);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v12);
          result = v10;
        }
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x316,
                             (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlannetwork.cpp",
                             v8);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30C,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlannetwork.cpp",
      (const char *)0x80004004LL,
      length);
    return 2147500036LL;
  }
  return result;
}

```

## disassembly

```asm
0x18005b320  mov     [rsp+arg_10], rbx
0x18005b325  mov     [rsp+arg_18], rsi
0x18005b32a  push    rdi
0x18005b32b  sub     rsp, 240h
0x18005b332  mov     rax, cs:__security_cookie
0x18005b339  xor     rax, rsp
0x18005b33c  mov     [rsp+248h+var_18], rax
0x18005b344  mov     rdi, rdx
0x18005b347  mov     rbx, rcx
0x18005b34a  lea     rsi, WPP_GLOBAL_Control
0x18005b351  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b358  cmp     rcx, rsi
0x18005b35b  jz      short loc_18005B378
0x18005b35d  test    byte ptr [rcx+1Ch], 40h
0x18005b361  jz      short loc_18005B378
0x18005b363  mov     edx, 1Ah
0x18005b368  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005b36f  mov     rcx, [rcx+10h]
0x18005b373  call    WPP_SF_
0x18005b378  mov     rax, [rbx+90h]
0x18005b37f  test    byte ptr [rax+26Ch], 10h
0x18005b386  jnz     short loc_18005B3B0
0x18005b388  mov     rcx, [rsp+248h]; this
0x18005b390  mov     ebx, 80004004h
0x18005b395  mov     r9d, ebx; char *
0x18005b398  lea     r8, aOnecoreuapNetU_26; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005b39f  mov     edx, 30Ch; void *
0x18005b3a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b3a9  mov     eax, ebx
0x18005b3ab  jmp     loc_18005B4A9
0x18005b3b0  mov     rdx, [rbx+0A8h]
0x18005b3b7  lea     rcx, [rsp+248h+var_220]
0x18005b3bc  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18005b3c1  xor     edx, edx; Val
0x18005b3c3  mov     r8d, 1FCh; Size
0x18005b3c9  lea     rcx, [rsp+248h+sourceString]; void *
0x18005b3ce  call    memset_0
0x18005b3d3  mov     [rsp+248h+length], 0FEh; int
0x18005b3db  mov     rcx, [rbx+90h]
0x18005b3e2  add     rcx, 200h
0x18005b3e9  lea     r9, [rsp+248h+sourceString]
0x18005b3ee  lea     r8, [rsp+248h+length]
0x18005b3f3  xor     edx, edx
0x18005b3f5  call    cs:__imp_WlanPrivateGetAnqpVenueUrl
0x18005b3fb  test    eax, eax
0x18005b3fd  jz      short loc_18005B42B
0x18005b3ff  mov     rcx, [rsp+248h]; this
0x18005b407  mov     r9d, eax; char *
0x18005b40a  lea     r8, aOnecoreuapNetU_26; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005b411  mov     edx, 312h; void *
0x18005b416  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005b41b  mov     ebx, eax
0x18005b41d  lea     rcx, [rsp+248h+var_220]
0x18005b422  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005b427  mov     eax, ebx
0x18005b429  jmp     short loc_18005B4A9
0x18005b42b  mov     r8, rdi; string
0x18005b42e  mov     edx, [rsp+248h+length]; length
0x18005b432  lea     rcx, [rsp+248h+sourceString]; sourceString
0x18005b437  call    cs:__imp_WindowsCreateString
0x18005b43d  mov     ebx, eax
0x18005b43f  test    eax, eax
0x18005b441  jns     short loc_18005B46D
0x18005b443  mov     rcx, [rsp+248h]; this
0x18005b44b  mov     r9d, eax; char *
0x18005b44e  lea     r8, aOnecoreuapNetU_26; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005b455  mov     edx, 313h; void *
0x18005b45a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b45f  lea     rcx, [rsp+248h+var_220]
0x18005b464  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005b469  mov     eax, ebx
0x18005b46b  jmp     short loc_18005B4A9
0x18005b46d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b474  cmp     rcx, rsi
0x18005b477  jz      short loc_18005B497
0x18005b479  test    byte ptr [rcx+1Ch], 40h
0x18005b47d  jz      short loc_18005B497
0x18005b47f  mov     edx, 1Bh
0x18005b484  xor     r9d, r9d
0x18005b487  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005b48e  mov     rcx, [rcx+10h]
0x18005b492  call    WPP_SF_d
0x18005b497  lea     rcx, [rsp+248h+var_220]
0x18005b49c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005b4a1  xor     eax, eax
0x18005b4a3  jmp     short loc_18005B4A9
0x18005b4a5  mov     eax, [rsp+248h+length]
0x18005b4a9  mov     rcx, [rsp+248h+var_18]
0x18005b4b1  xor     rcx, rsp; StackCookie
0x18005b4b4  call    __security_check_cookie
0x18005b4b9  lea     r11, [rsp+248h+var_8]
0x18005b4c1  mov     rbx, [r11+20h]
0x18005b4c5  mov     rsi, [r11+28h]
0x18005b4c9  mov     rsp, r11
0x18005b4cc  pop     rdi
0x18005b4cd  retn
```
