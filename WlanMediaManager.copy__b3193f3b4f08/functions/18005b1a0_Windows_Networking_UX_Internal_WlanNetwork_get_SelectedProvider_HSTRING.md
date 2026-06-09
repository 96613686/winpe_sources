# Windows::Networking::UX::Internal::WlanNetwork::get_SelectedProvider(HSTRING__ * *)

- ea: `0x18005b1a0`
- end: `0x18005b314`
- name: `?get_SelectedProvider@WlanNetwork@Internal@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `372`
- prototype: `int(Windows::Networking::UX::Internal::WlanNetwork *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000de4c`
- `0x180012228`
- `0x18001d4d4`
- `0x1800287a0`
- `0x18005b1a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005b28b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005b28b`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileMetadata` at `0x18005b227`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileMetadata` at `0x18005b227`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetwork::get_SelectedProvider(
        Windows::Networking::UX::Internal::WlanNetwork *this,
        HSTRING *a2)
{
  int ProfileMetadata; // eax
  unsigned int v5; // ebx
  HRESULT String; // eax
  const char *v7; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v10; // [rsp+50h] [rbp+8h] BYREF
  char v11; // [rsp+60h] [rbp+18h] BYREF
  PCNZWCH sourceString; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids);
  try
  {
    wil::impersonate_token(&v11, *((_QWORD *)this + 21));
    v10 = 0;
    sourceString = 0;
    ProfileMetadata = WlanGetProfileMetadata(
                        (char *)this - 72,
                        *((_QWORD *)this + 18),
                        0,
                        L"Selected Provider",
                        &v10,
                        &sourceString);
    v5 = ProfileMetadata;
    if ( ProfileMetadata )
    {
      if ( ProfileMetadata > 0 )
        v5 = (unsigned __int16)ProfileMetadata | 0x80070000;
      if ( (v5 & 0x80000000) != 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids, v5);
      }
    }
    else
    {
      String = WindowsCreateString(sourceString, v10 >> 1, a2);
      v5 = String;
      if ( String >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids,
            (unsigned int)String);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids,
          (unsigned int)String);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v11);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3DA,
                           (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlannetwork.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18005b1a0  push    rbx
0x18005b1a2  push    rsi
0x18005b1a3  push    rdi
0x18005b1a4  sub     rsp, 30h
0x18005b1a8  mov     rdi, rdx
0x18005b1ab  mov     rbx, rcx
0x18005b1ae  lea     rsi, WPP_GLOBAL_Control
0x18005b1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b1bc  cmp     rcx, rsi
0x18005b1bf  jz      short loc_18005B1DC
0x18005b1c1  test    byte ptr [rcx+1Ch], 40h
0x18005b1c5  jz      short loc_18005B1DC
0x18005b1c7  mov     edx, 2Bh ; '+'
0x18005b1cc  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005b1d3  mov     rcx, [rcx+10h]
0x18005b1d7  call    WPP_SF_
0x18005b1dc  mov     rdx, [rbx+0A8h]
0x18005b1e3  lea     rcx, [rsp+48h+arg_10]
0x18005b1e8  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18005b1ed  mov     [rsp+48h+arg_0], 0
0x18005b1f5  mov     [rsp+48h+sourceString], 0
0x18005b1fe  lea     rcx, [rbx-48h]
0x18005b202  lea     rax, [rsp+48h+sourceString]
0x18005b207  mov     [rsp+48h+var_20], rax
0x18005b20c  lea     rax, [rsp+48h+arg_0]
0x18005b211  mov     [rsp+48h+var_28], rax
0x18005b216  lea     r9, aSelectedProvid; "Selected Provider"
0x18005b21d  xor     r8d, r8d
0x18005b220  mov     rdx, [rbx+90h]
0x18005b227  call    cs:__imp_WlanGetProfileMetadata
0x18005b22d  mov     ebx, eax
0x18005b22f  test    eax, eax
0x18005b231  jz      short loc_18005B27D
0x18005b233  jle     short loc_18005B23E
0x18005b235  movzx   ebx, ax
0x18005b238  or      ebx, 80070000h
0x18005b23e  test    ebx, ebx
0x18005b240  jns     short loc_18005B26C
0x18005b242  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b249  cmp     rcx, rsi
0x18005b24c  jz      short loc_18005B26C
0x18005b24e  test    byte ptr [rcx+1Ch], 2
0x18005b252  jz      short loc_18005B26C
0x18005b254  mov     edx, 2Ch ; ','
0x18005b259  mov     r9d, ebx
0x18005b25c  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005b263  mov     rcx, [rcx+10h]
0x18005b267  call    WPP_SF_d
0x18005b26c  lea     rcx, [rsp+48h+arg_10]
0x18005b271  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005b276  mov     eax, ebx
0x18005b278  jmp     loc_18005B30B
0x18005b27d  mov     edx, [rsp+48h+arg_0]
0x18005b281  shr     edx, 1; length
0x18005b283  mov     r8, rdi; string
0x18005b286  mov     rcx, [rsp+48h+sourceString]; sourceString
0x18005b28b  call    cs:__imp_WindowsCreateString
0x18005b291  mov     ebx, eax
0x18005b293  test    eax, eax
0x18005b295  jns     short loc_18005B2CF
0x18005b297  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b29e  cmp     rcx, rsi
0x18005b2a1  jz      short loc_18005B2C1
0x18005b2a3  test    byte ptr [rcx+1Ch], 2
0x18005b2a7  jz      short loc_18005B2C1
0x18005b2a9  mov     edx, 2Dh ; '-'
0x18005b2ae  mov     r9d, eax
0x18005b2b1  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005b2b8  mov     rcx, [rcx+10h]
0x18005b2bc  call    WPP_SF_d
0x18005b2c1  lea     rcx, [rsp+48h+arg_10]
0x18005b2c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005b2cb  mov     eax, ebx
0x18005b2cd  jmp     short loc_18005B30B
0x18005b2cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b2d6  cmp     rcx, rsi
0x18005b2d9  jz      short loc_18005B2F9
0x18005b2db  test    byte ptr [rcx+1Ch], 40h
0x18005b2df  jz      short loc_18005B2F9
0x18005b2e1  mov     edx, 2Eh ; '.'
0x18005b2e6  mov     r9d, ebx
0x18005b2e9  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005b2f0  mov     rcx, [rcx+10h]
0x18005b2f4  call    WPP_SF_d
0x18005b2f9  lea     rcx, [rsp+48h+arg_10]
0x18005b2fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005b303  mov     eax, ebx
0x18005b305  jmp     short loc_18005B30B
0x18005b307  mov     eax, [rsp+48h+arg_0]
0x18005b30b  add     rsp, 30h
0x18005b30f  pop     rdi
0x18005b310  pop     rsi
0x18005b311  pop     rbx
0x18005b312  retn
```
