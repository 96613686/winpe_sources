# Windows::Networking::UX::Internal::CWiFiProtocolUri::_SetPassword(void)

- ea: `0x1800621b8`
- end: `0x1800622c3`
- name: `?_SetPassword@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `267`
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
- `0x1800621b8`
- `0x180062da4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006223b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006223b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180062259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180062259`

## string_xrefs

- `0x18006226d`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CWiFiProtocolUri::_SetPassword(
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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_798799ef23c633adda075654372160e0_Traceguids);
  v13 = 3;
  v2 = (_QWORD *)std::_Tree<std::_Tmap_traits<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring,std::less<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType>,std::allocator<std::pair<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType const,std::wstring>>,0>>::find(
                   (char *)this + 88,
                   &v14,
                   &v13);
  try
  {
    if ( *v2 == *((_QWORD *)this + 11)
      || (v13 = 3,
          v4 = std::map<enum Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring>::operator[](
                 (char *)this + 88,
                 &v13),
          WindowsDeleteString(*((HSTRING *)this + 16)),
          *((_QWORD *)this + 16) = 0,
          v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4, v5, v6),
          String = WindowsCreateString(v7, *(_DWORD *)(v4 + 16), (HSTRING *)this + 16),
          v9 = String,
          String >= 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_798799ef23c633adda075654372160e0_Traceguids, 0);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEF,
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
                           (void *)0xF3,
                           (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x1800621b8  mov     [rsp+arg_10], rbx
0x1800621bd  push    rsi
0x1800621be  push    rdi
0x1800621bf  push    r14; int
0x1800621c1  sub     rsp, 20h
0x1800621c5  mov     rdi, rcx
0x1800621c8  lea     r14, WPP_GLOBAL_Control
0x1800621cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800621d6  cmp     rcx, r14
0x1800621d9  jz      short loc_1800621F6
0x1800621db  test    byte ptr [rcx+1Ch], 40h
0x1800621df  jz      short loc_1800621F6
0x1800621e1  mov     edx, 1Ah
0x1800621e6  lea     r8, WPP_798799ef23c633adda075654372160e0_Traceguids
0x1800621ed  mov     rcx, [rcx+10h]
0x1800621f1  call    WPP_SF_
0x1800621f6  lea     rbx, [rdi+58h]
0x1800621fa  mov     esi, 3
0x1800621ff  mov     [rsp+38h+arg_0], esi
0x180062203  lea     r8, [rsp+38h+arg_0]
0x180062208  lea     rdx, [rsp+38h+arg_8]
0x18006220d  mov     rcx, rbx
0x180062210  call    ?find@?$_Tree@V?$_Tmap_traits@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@7@V?$allocator@U?$pair@$$CBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@AEBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@Z; std::_Tree<std::_Tmap_traits<Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring,std::less<Windows::Networking::UX::Internal::WiFiProtocolKeyType>,std::allocator<std::pair<Windows::Networking::UX::Internal::WiFiProtocolKeyType const,std::wstring>>,0>>::find(Windows::Networking::UX::Internal::WiFiProtocolKeyType const &)
0x180062215  mov     rdx, [rbx]
0x180062218  cmp     [rax], rdx
0x18006221b  jz      short loc_180062282
0x18006221d  mov     [rsp+38h+arg_0], esi
0x180062221  lea     rdx, [rsp+38h+arg_0]
0x180062226  mov     rcx, rbx
0x180062229  call    ??A?$map@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@7@V?$allocator@U?$pair@$$CBW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@7@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4WiFiProtocolKeyType@Internal@UX@Networking@Windows@@@Z; std::map<Windows::Networking::UX::Internal::WiFiProtocolKeyType,std::wstring>::operator[](Windows::Networking::UX::Internal::WiFiProtocolKeyType &&)
0x18006222e  mov     rsi, rax
0x180062231  lea     rbx, [rdi+80h]
0x180062238  mov     rcx, [rbx]; string
0x18006223b  call    cs:__imp_WindowsDeleteString
0x180062241  mov     qword ptr [rbx], 0
0x180062248  mov     rcx, rsi
0x18006224b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062250  mov     r8, rbx; string
0x180062253  mov     edx, [rsi+10h]; length
0x180062256  mov     rcx, rax; sourceString
0x180062259  call    cs:__imp_WindowsCreateString
0x18006225f  mov     ebx, eax
0x180062261  test    eax, eax
0x180062263  jns     short loc_180062282
0x180062265  mov     rcx, [rsp+38h]; this
0x18006226a  mov     r9d, eax; char *
0x18006226d  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180062274  mov     edx, 0EFh; void *
0x180062279  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006227e  mov     eax, ebx
0x180062280  jmp     short loc_1800622B4
0x180062282  mov     rcx, cs:WPP_GLOBAL_Control
0x180062289  cmp     rcx, r14
0x18006228c  jz      short loc_1800622AC
0x18006228e  test    byte ptr [rcx+1Ch], 8
0x180062292  jz      short loc_1800622AC
0x180062294  mov     edx, 1Bh
0x180062299  xor     r9d, r9d
0x18006229c  lea     r8, WPP_798799ef23c633adda075654372160e0_Traceguids
0x1800622a3  mov     rcx, [rcx+10h]
0x1800622a7  call    WPP_SF_d
0x1800622ac  xor     eax, eax
0x1800622ae  jmp     short loc_1800622B4
0x1800622b0  mov     eax, [rsp+38h+arg_0]
0x1800622b4  mov     rbx, [rsp+38h+arg_10]
0x1800622b9  add     rsp, 20h
0x1800622bd  pop     r14
0x1800622bf  pop     rdi
0x1800622c0  pop     rsi
0x1800622c1  retn
```
