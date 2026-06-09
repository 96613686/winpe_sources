# OpenStoreKey(IAudioSessionInfo *,HKEY__ * *)

- ea: `0x180012c1c`
- end: `0x180012e5e`
- name: `?OpenStoreKey@@YAJPEAUIAudioSessionInfo@@PEAPEAUHKEY__@@@Z`
- size: `578`
- prototype: `int(struct IAudioSessionInfo *, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012aa0`

## callees

- `0x18000a384`
- `0x1800101ac`
- `0x180012c1c`
- `0x180012e64`
- `0x1800232a0`
- `0x180031960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012ca3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012e30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012ca3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012e30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d49`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012d76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012dae`
- `RPCRT4!RpcRevertToSelf` at `0x180012cf1`
- `RPCRT4!RpcRevertToSelf` at `0x180012d3f`
- `RPCRT4!RpcRevertToSelf` at `0x180012d6c`
- `RPCRT4!RpcRevertToSelf` at `0x180012cf1`
- `RPCRT4!RpcRevertToSelf` at `0x180012d3f`
- `RPCRT4!RpcRevertToSelf` at `0x180012d6c`
- `RPCRT4!RpcImpersonateClient` at `0x180012c52`
- `RPCRT4!RpcImpersonateClient` at `0x180012c52`

## string_xrefs

- `0x180012cc8`: `Audio\PolicyConfig\PropertyStore`

## pseudocode

```c
__int64 __fastcall OpenStoreKey(struct IAudioSessionInfo *a1, HKEY *a2)
{
  int v4; // ebx
  unsigned __int64 v5; // r8
  int PropKeyPath; // eax
  int LowRightsRegistryKey; // edi
  unsigned int v8; // esi
  bool v9; // sf
  unsigned int v11; // esi
  bool v12; // sf
  __int64 v13; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = RpcImpersonateClient(0);
  if ( v4 && v4 != 1725 && v4 != 1765 )
  {
    v12 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v12 = v4 < 0;
    }
    if ( v12 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)v4,
        phkResult);
    return (unsigned int)v4;
  }
  PropKeyPath = GetPropKeyPath(a1, SubKey, v5);
  LowRightsRegistryKey = PropKeyPath;
  if ( PropKeyPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCE,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)(unsigned int)PropKeyPath,
      phkResult);
LABEL_15:
    if ( !v4 )
      RpcRevertToSelf();
    return (unsigned int)LowRightsRegistryKey;
  }
  v8 = 131103;
  hKey[0] = 0;
  LowRightsRegistryKey = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x2001Fu, hKey);
  if ( LowRightsRegistryKey == 5 )
  {
    v8 = 131097;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      hKey,
      0);
    LowRightsRegistryKey = RegOpenKeyExW(HKEY_USERS, SubKey, 0, 0x20019u, hKey);
  }
  v9 = LowRightsRegistryKey < 0;
  if ( LowRightsRegistryKey > 0 )
  {
    LowRightsRegistryKey = (unsigned __int16)LowRightsRegistryKey | 0x80070000;
    v9 = LowRightsRegistryKey < 0;
  }
  if ( v9 )
  {
    v11 = -2147024894;
    if ( LowRightsRegistryKey != -2147024894 )
    {
      v13 = 223;
      goto LABEL_24;
    }
  }
  else
  {
    LowRightsRegistryKey = CreateLowRightsRegistryKey(hKey[0], L"Audio\\PolicyConfig\\PropertyStore", v8, a2);
    if ( LowRightsRegistryKey >= 0 )
    {
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      if ( !v4 )
        RpcRevertToSelf();
      return 0;
    }
    v11 = -2147024891;
    if ( LowRightsRegistryKey != -2147024891 )
    {
      v13 = 225;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)LowRightsRegistryKey,
        phkResulta);
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      goto LABEL_15;
    }
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( !v4 )
    RpcRevertToSelf();
  return v11;
}

```

## disassembly

```asm
0x180012c1c  mov     [rsp-8+arg_10], rbx
0x180012c21  mov     [rsp-8+arg_18], rsi
0x180012c26  push    rbp
0x180012c27  push    rdi
0x180012c28  push    r14
0x180012c2a  lea     rbp, [rsp-160h]
0x180012c32  sub     rsp, 260h
0x180012c39  mov     rax, cs:__security_cookie
0x180012c40  xor     rax, rsp
0x180012c43  mov     [rbp+170h+var_20], rax
0x180012c4a  mov     r14, rdx
0x180012c4d  mov     rdi, rcx
0x180012c50  xor     ecx, ecx; BindingHandle
0x180012c52  call    cs:__imp_RpcImpersonateClient
0x180012c58  mov     ebx, eax
0x180012c5a  test    eax, eax
0x180012c5c  jnz     loc_180012DE9
0x180012c62  lea     rdx, [rsp+270h+SubKey]; unsigned __int16 *
0x180012c67  mov     rcx, rdi; struct IAudioSessionInfo *
0x180012c6a  call    ?GetPropKeyPath@@YAJPEAUIAudioSessionInfo@@PEAG_K@Z; GetPropKeyPath(IAudioSessionInfo *,ushort *,unsigned __int64)
0x180012c6f  mov     edi, eax
0x180012c71  test    eax, eax
0x180012c73  js      loc_180012D20
0x180012c79  mov     esi, 2001Fh
0x180012c7e  mov     [rsp+270h+hKey], 0
0x180012c87  lea     rax, [rsp+270h+hKey]
0x180012c8c  mov     qword ptr [rsp+270h+phkResult], rax; int
0x180012c91  mov     r9d, esi; samDesired
0x180012c94  xor     r8d, r8d; ulOptions
0x180012c97  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x180012c9c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180012ca3  call    cs:__imp_RegOpenKeyExW
0x180012ca9  mov     edi, eax
0x180012cab  cmp     eax, 5
0x180012cae  jz      loc_180012E03
0x180012cb4  test    edi, edi
0x180012cb6  jg      loc_180012D7E
0x180012cbc  js      loc_180012D51
0x180012cc2  mov     r9, r14; HKEY *
0x180012cc5  mov     r8d, esi; unsigned int
0x180012cc8  lea     rdx, aAudioPolicycon; "Audio\\PolicyConfig\\PropertyStore"
0x180012ccf  mov     rcx, [rsp+270h+hKey]; HKEY
0x180012cd4  call    ?CreateLowRightsRegistryKey@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CreateLowRightsRegistryKey(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180012cd9  mov     edi, eax
0x180012cdb  test    eax, eax
0x180012cdd  js      loc_180012E47
0x180012ce3  mov     rcx, [rsp+270h+hKey]; hKey
0x180012ce8  test    rcx, rcx
0x180012ceb  jnz     short loc_180012D49
0x180012ced  test    ebx, ebx
0x180012cef  jnz     short loc_180012CF7
0x180012cf1  call    cs:__imp_RpcRevertToSelf
0x180012cf7  xor     eax, eax
0x180012cf9  mov     rcx, [rbp+170h+var_20]
0x180012d00  xor     rcx, rsp; StackCookie
0x180012d03  call    __security_check_cookie
0x180012d08  lea     r11, [rsp+270h+var_10]
0x180012d10  mov     rbx, [r11+30h]
0x180012d14  mov     rsi, [r11+38h]
0x180012d18  mov     rsp, r11
0x180012d1b  pop     r14
0x180012d1d  pop     rdi
0x180012d1e  pop     rbp
0x180012d1f  retn
0x180012d20  mov     rcx, [rbp+178h]; this
0x180012d27  mov     r9d, edi; char *
0x180012d2a  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180012d31  mov     edx, 0CEh; void *
0x180012d36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d3b  test    ebx, ebx
0x180012d3d  jnz     short loc_180012D45
0x180012d3f  call    cs:__imp_RpcRevertToSelf
0x180012d45  mov     eax, edi
0x180012d47  jmp     short loc_180012CF9
0x180012d49  call    cs:__imp_RegCloseKey
0x180012d4f  jmp     short loc_180012CED
0x180012d51  mov     esi, 80070002h
0x180012d56  cmp     edi, esi
0x180012d58  jnz     loc_180012E3D
0x180012d5e  mov     rcx, [rsp+270h+hKey]; hKey
0x180012d63  test    rcx, rcx
0x180012d66  jnz     short loc_180012D76
0x180012d68  test    ebx, ebx
0x180012d6a  jnz     short loc_180012D72
0x180012d6c  call    cs:__imp_RpcRevertToSelf
0x180012d72  mov     eax, esi
0x180012d74  jmp     short loc_180012CF9
0x180012d76  call    cs:__imp_RegCloseKey
0x180012d7c  jmp     short loc_180012D68
0x180012d7e  movzx   edi, di
0x180012d81  or      edi, 80070000h
0x180012d87  test    edi, edi
0x180012d89  jmp     loc_180012CBC
0x180012d8e  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180012d95  mov     r9d, edi; char *
0x180012d98  mov     rcx, [rbp+178h]; this
0x180012d9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012da4  mov     rcx, [rsp+270h+hKey]; hKey
0x180012da9  test    rcx, rcx
0x180012dac  jz      short loc_180012D3B
0x180012dae  call    cs:__imp_RegCloseKey
0x180012db4  jmp     short loc_180012D3B
0x180012db6  test    ebx, ebx
0x180012db8  jle     short loc_180012DC5
0x180012dba  movzx   ebx, bx
0x180012dbd  or      ebx, 80070000h
0x180012dc3  test    ebx, ebx
0x180012dc5  jns     short loc_180012DE2
0x180012dc7  mov     rcx, [rbp+178h]; this
0x180012dce  mov     r9d, ebx; char *
0x180012dd1  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
0x180012dd8  mov     edx, 0CBh; void *
0x180012ddd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012de2  mov     eax, ebx
0x180012de4  jmp     loc_180012CF9
0x180012de9  cmp     ebx, 6BDh
0x180012def  jz      loc_180012C62
0x180012df5  cmp     ebx, 6E5h
0x180012dfb  jz      loc_180012C62
0x180012e01  jmp     short loc_180012DB6
0x180012e03  mov     esi, 20019h
0x180012e08  xor     edx, edx
0x180012e0a  lea     rcx, [rsp+270h+hKey]
0x180012e0f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180012e14  lea     rax, [rsp+270h+hKey]
0x180012e19  mov     qword ptr [rsp+270h+phkResult], rax; phkResult
0x180012e1e  mov     r9d, esi; samDesired
0x180012e21  xor     r8d, r8d; ulOptions
0x180012e24  lea     rdx, [rsp+270h+SubKey]; lpSubKey
0x180012e29  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180012e30  call    cs:__imp_RegOpenKeyExW
0x180012e36  mov     edi, eax
0x180012e38  jmp     loc_180012CB4
0x180012e3d  mov     edx, 0DFh; void *
0x180012e42  jmp     loc_180012D8E
0x180012e47  mov     esi, 80070005h
0x180012e4c  cmp     edi, esi
0x180012e4e  jz      loc_180012D5E
0x180012e54  mov     edx, 0E1h
0x180012e59  jmp     loc_180012D8E
```
