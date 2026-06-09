# Windows::Networking::UX::Internal::CWiFiProtocolUri::_SetNetworkName(void)

- ea: `0x180061f70`
- end: `0x180062078`
- name: `?_SetNetworkName@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `264`
- prototype: `int(Windows::Networking::UX::Internal::CWiFiProtocolUri *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006170c`

## callees

- `0x1800097b4`
- `0x18000de4c`
- `0x18001b838`
- `0x18001d4d4`
- `0x180060c00`
- `0x180061f70`
- `0x180062da4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006200e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006200e`

## string_xrefs

- `0x180062022`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CWiFiProtocolUri::_SetNetworkName(
        Windows::Networking::UX::Internal::CWiFiProtocolUri *this)
{
  _QWORD *v2; // rax
  const char *v3; // r9
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  const WCHAR *v7; // rax
  HRESULT String; // eax
  unsigned int v9; // ebx
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v13; // [rsp+40h] [rbp+8h] BYREF
  char v14; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_798799ef23c633adda075654372160e0_Traceguids);
  v13 = 2;
  v2 = (_QWORD *)std::_Tree<std::_Tmap_traits<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring,std::less<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType>,std::allocator<std::pair<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType const,std::wstring>>,0>>::find(
                   (char *)this + 88,
                   &v14,
                   &v13);
  try
  {
    if ( *v2 == *((_QWORD *)this + 11)
      || (v13 = 2,
          v4 = std::map<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring>::operator[](
                 (char *)this + 88,
                 &v13),
          WindowsDeleteString(*((HSTRING *)this + 15)),
          *((_QWORD *)this + 15) = 0,
          v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4, v5, v6),
          String = WindowsCreateString(v7, *(_DWORD *)(v4 + 16), (HSTRING *)this + 15),
          v9 = String,
          String >= 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_798799ef23c633adda075654372160e0_Traceguids, 0);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
        (const char *)(unsigned int)String,
        v11);
      result = v9;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE7,
                           (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180061f70  mov     [rsp+arg_10], rbx
0x180061f75  push    rsi
0x180061f76  push    rdi
0x180061f77  push    r14; int
0x180061f79  sub     rsp, 20h
0x180061f7d  mov     rdi, rcx
0x180061f80  lea     r14, WPP_GLOBAL_Control
0x180061f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180061f8e  cmp     rcx, r14
0x180061f91  jz      short loc_180061FAE
0x180061f93  test    byte ptr [rcx+1Ch], 40h
0x180061f97  jz      short loc_180061FAE
0x180061f99  mov     edx, 18h
0x180061f9e  lea     r8, WPP_798799ef23c633adda075654372160e0_Traceguids
0x180061fa5  mov     rcx, [rcx+10h]
0x180061fa9  call    WPP_SF_
0x180061fae  lea     rbx, [rdi+58h]
0x180061fb2  mov     esi, 2
0x180061fb7  mov     [rsp+38h+arg_0], esi
0x180061fbb  lea     r8, [rsp+38h+arg_0]
0x180061fc0  lea     rdx, [rsp+38h+arg_8]
0x180061fc5  mov     rcx, rbx
0x180061fc8  call    ?find@?$_Tree@V?$_Tmap_traits@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@7@V?$allocator@U?$pair@$$CBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@AEBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@Z; std::_Tree<std::_Tmap_traits<Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring,std::less<Windows::Networking::UX::Internal::WiFiProtocolKeyType>,std::allocator<std::pair<Windows::Networking::UX::Internal::WiFiProtocolKeyType const,std::wstring>>,0>>::find(Windows::Networking::UX::Internal::WiFiProtocolKeyType const &)
0x180061fcd  mov     rdx, [rbx]
0x180061fd0  cmp     [rax], rdx
0x180061fd3  jz      short loc_180062037
0x180061fd5  mov     [rsp+38h+arg_0], esi
0x180061fd9  lea     rdx, [rsp+38h+arg_0]
0x180061fde  mov     rcx, rbx
0x180061fe1  call    ??A?$map@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@7@V?$allocator@U?$pair@$$CBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@7@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@Z; std::map<Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring>::operator[](Windows::Networking::UX::Internal::WiFiProtocolKeyType &&)
0x180061fe6  mov     rsi, rax
0x180061fe9  lea     rbx, [rdi+78h]
0x180061fed  mov     rcx, [rbx]; string
0x180061ff0  call    cs:__imp_WindowsDeleteString
0x180061ff6  mov     qword ptr [rbx], 0
0x180061ffd  mov     rcx, rsi
0x180062000  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062005  mov     r8, rbx; string
0x180062008  mov     edx, [rsi+10h]; length
0x18006200b  mov     rcx, rax; sourceString
0x18006200e  call    cs:__imp_WindowsCreateString
0x180062014  mov     ebx, eax
0x180062016  test    eax, eax
0x180062018  jns     short loc_180062037
0x18006201a  mov     rcx, [rsp+38h]; this
0x18006201f  mov     r9d, eax; char *
0x180062022  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180062029  mov     edx, 0E3h; void *
0x18006202e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062033  mov     eax, ebx
0x180062035  jmp     short loc_180062069
0x180062037  mov     rcx, cs:WPP_GLOBAL_Control
0x18006203e  cmp     rcx, r14
0x180062041  jz      short loc_180062061
0x180062043  test    byte ptr [rcx+1Ch], 8
0x180062047  jz      short loc_180062061
0x180062049  mov     edx, 19h
0x18006204e  xor     r9d, r9d
0x180062051  lea     r8, WPP_798799ef23c633adda075654372160e0_Traceguids
0x180062058  mov     rcx, [rcx+10h]
0x18006205c  call    WPP_SF_d
0x180062061  xor     eax, eax
0x180062063  jmp     short loc_180062069
0x180062065  mov     eax, [rsp+38h+arg_0]
0x180062069  mov     rbx, [rsp+38h+arg_10]
0x18006206e  add     rsp, 20h
0x180062072  pop     r14
0x180062074  pop     rdi
0x180062075  pop     rsi
0x180062076  retn
```
