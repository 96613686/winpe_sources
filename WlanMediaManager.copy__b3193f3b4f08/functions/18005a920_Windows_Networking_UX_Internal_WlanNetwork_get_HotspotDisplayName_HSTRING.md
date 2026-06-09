# Windows::Networking::UX::Internal::WlanNetwork::get_HotspotDisplayName(HSTRING__ * *)

- ea: `0x18005a920`
- end: `0x18005aaaa`
- name: `?get_HotspotDisplayName@WlanNetwork@Internal@UX@Networking@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `394`
- prototype: `int(Windows::Networking::UX::Internal::WlanNetwork *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000de4c`
- `0x180012228`
- `0x18001d4d4`
- `0x1800287a0`
- `0x18005a920`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005aa0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005aa0c`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005aa56`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x18005aa56`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileMetadata` at `0x18005a9ad`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanGetProfileMetadata` at `0x18005a9ad`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanNetwork::get_HotspotDisplayName(
        Windows::Networking::UX::Internal::WlanNetwork *this,
        HSTRING *a2)
{
  unsigned int v4; // edx
  const WCHAR *v5; // rcx
  int ProfileMetadata; // eax
  bool v7; // sf
  HRESULT String; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  const char *v11; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v14; // [rsp+50h] [rbp+8h] BYREF
  PCNZWCH sourceString; // [rsp+60h] [rbp+18h] BYREF
  char v16; // [rsp+68h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids);
  try
  {
    wil::impersonate_token(&v16, *((_QWORD *)this + 21));
    v4 = 0;
    v14 = 0;
    v5 = 0;
    sourceString = 0;
    if ( *((_DWORD *)this + 21) == 1 )
    {
      ProfileMetadata = WlanGetProfileMetadata(
                          (char *)this - 72,
                          *((_QWORD *)this + 18),
                          0,
                          L"Hotspot Display Name",
                          &v14,
                          &sourceString);
      v7 = ProfileMetadata < 0;
      if ( ProfileMetadata )
      {
        if ( ProfileMetadata > 0 )
        {
          ProfileMetadata = (unsigned __int16)ProfileMetadata | 0x80070000;
          v7 = ProfileMetadata < 0;
        }
        if ( v7 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids,
            (unsigned int)ProfileMetadata);
        v4 = 0;
        v14 = 0;
        v5 = 0;
        sourceString = 0;
      }
      else
      {
        v4 = v14;
        v5 = sourceString;
      }
    }
    String = WindowsCreateString(v5, v4 >> 1, a2);
    v9 = String;
    if ( String < 0 )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_20;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids,
        (unsigned int)String);
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
    if ( sourceString )
    {
      WlanFreeMemory((PVOID)sourceString);
      sourceString = 0;
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 )
      WPP_SF_d(v10[2], 53, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids, v9);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v16);
    result = v9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x418,
                           (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlannetwork.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18005a920  push    rbx
0x18005a922  push    rsi
0x18005a923  push    rdi
0x18005a924  sub     rsp, 30h
0x18005a928  mov     rdi, rdx
0x18005a92b  mov     rbx, rcx
0x18005a92e  lea     rsi, WPP_GLOBAL_Control
0x18005a935  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a93c  cmp     rcx, rsi
0x18005a93f  jz      short loc_18005A95C
0x18005a941  test    byte ptr [rcx+1Ch], 40h
0x18005a945  jz      short loc_18005A95C
0x18005a947  mov     edx, 32h ; '2'
0x18005a94c  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005a953  mov     rcx, [rcx+10h]
0x18005a957  call    WPP_SF_
0x18005a95c  mov     rdx, [rbx+0A8h]
0x18005a963  lea     rcx, [rsp+48h+arg_18]
0x18005a968  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18005a96d  xor     edx, edx
0x18005a96f  mov     [rsp+48h+arg_0], edx
0x18005a973  xor     ecx, ecx
0x18005a975  mov     [rsp+48h+sourceString], rcx
0x18005a97a  cmp     dword ptr [rbx+54h], 1
0x18005a97e  jnz     loc_18005AA07
0x18005a984  lea     rcx, [rbx-48h]
0x18005a988  lea     rax, [rsp+48h+sourceString]
0x18005a98d  mov     [rsp+48h+var_20], rax
0x18005a992  lea     rax, [rsp+48h+arg_0]
0x18005a997  mov     [rsp+48h+var_28], rax
0x18005a99c  lea     r9, aHotspotDisplay; "Hotspot Display Name"
0x18005a9a3  xor     r8d, r8d
0x18005a9a6  mov     rdx, [rbx+90h]
0x18005a9ad  call    cs:__imp_WlanGetProfileMetadata
0x18005a9b3  test    eax, eax
0x18005a9b5  jz      short loc_18005A9FE
0x18005a9b7  jle     short loc_18005A9C3
0x18005a9b9  movzx   eax, ax
0x18005a9bc  or      eax, 80070000h
0x18005a9c1  test    eax, eax
0x18005a9c3  jns     short loc_18005A9EF
0x18005a9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a9cc  cmp     rcx, rsi
0x18005a9cf  jz      short loc_18005A9EF
0x18005a9d1  test    byte ptr [rcx+1Ch], 2
0x18005a9d5  jz      short loc_18005A9EF
0x18005a9d7  mov     edx, 33h ; '3'
0x18005a9dc  mov     r9d, eax
0x18005a9df  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005a9e6  mov     rcx, [rcx+10h]
0x18005a9ea  call    WPP_SF_d
0x18005a9ef  xor     edx, edx
0x18005a9f1  mov     [rsp+48h+arg_0], edx
0x18005a9f5  xor     ecx, ecx
0x18005a9f7  mov     [rsp+48h+sourceString], rcx
0x18005a9fc  jmp     short loc_18005AA07
0x18005a9fe  mov     edx, [rsp+48h+arg_0]
0x18005aa02  mov     rcx, [rsp+48h+sourceString]; sourceString
0x18005aa07  shr     edx, 1; length
0x18005aa09  mov     r8, rdi; string
0x18005aa0c  call    cs:__imp_WindowsCreateString
0x18005aa12  mov     ebx, eax
0x18005aa14  test    eax, eax
0x18005aa16  jns     short loc_18005AA42
0x18005aa18  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa1f  cmp     rcx, rsi
0x18005aa22  jz      short loc_18005AA49
0x18005aa24  test    byte ptr [rcx+1Ch], 2
0x18005aa28  jz      short loc_18005AA49
0x18005aa2a  mov     edx, 34h ; '4'
0x18005aa2f  mov     r9d, eax
0x18005aa32  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005aa39  mov     rcx, [rcx+10h]
0x18005aa3d  call    WPP_SF_d
0x18005aa42  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa49  mov     rax, [rsp+48h+sourceString]
0x18005aa4e  test    rax, rax
0x18005aa51  jz      short loc_18005AA6C
0x18005aa53  mov     rcx, rax; pMemory
0x18005aa56  call    cs:__imp_WlanFreeMemory
0x18005aa5c  mov     [rsp+48h+sourceString], 0
0x18005aa65  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa6c  cmp     rcx, rsi
0x18005aa6f  jz      short loc_18005AA8F
0x18005aa71  test    byte ptr [rcx+1Ch], 40h
0x18005aa75  jz      short loc_18005AA8F
0x18005aa77  mov     edx, 35h ; '5'
0x18005aa7c  mov     r9d, ebx
0x18005aa7f  lea     r8, WPP_986cb96e1ae83fcb14083ce1067b4995_Traceguids
0x18005aa86  mov     rcx, [rcx+10h]
0x18005aa8a  call    WPP_SF_d
0x18005aa8f  lea     rcx, [rsp+48h+arg_18]
0x18005aa94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18005aa99  mov     eax, ebx
0x18005aa9b  jmp     short loc_18005AAA1
0x18005aa9d  mov     eax, [rsp+48h+arg_0]
0x18005aaa1  add     rsp, 30h
0x18005aaa5  pop     rdi
0x18005aaa6  pop     rsi
0x18005aaa7  pop     rbx
0x18005aaa8  retn
```
