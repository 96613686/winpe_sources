# CBrowserBrokerInstance::CopyFavoriteIconFile(ushort const *,ushort * *)

- ea: `0x180007af0`
- end: `0x180007c3c`
- name: `?CopyFavoriteIconFile@CBrowserBrokerInstance@@UEAAJPEBGPEAPEAG@Z`
- size: `332`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callees

- `0x180002ce0`
- `0x180007af0`
- `0x18000c144`
- `0x18000c164`
- `0x18000e428`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x180007b5f`
- `iertutil!__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z` at `0x180007b5f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180007b89`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180007b89`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180007bf0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180007bf0`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180007bac`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x180007bac`
- `OLEAUT32!__imp_SysAllocString` at `0x180007bca`
- `OLEAUT32!__imp_SysAllocString` at `0x180007bca`
- `profapi!__imp_GetAppContainerPath` at `0x180007b73`
- `profapi!__imp_GetAppContainerPath` at `0x180007b73`

## string_xrefs

- `0x180007b44`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`
- `0x180007c02`: `onecoreuap\inetcore\spartan\desktopbroker\brokerfactory.cpp`

## pseudocode

```c
__int64 __fastcall CBrowserBrokerInstance::CopyFavoriteIconFile(
        CBrowserBrokerInstance *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int PIC; // ebx
  __int64 v6; // rdx
  __int64 String; // rax
  const WCHAR *FileNameW; // rax
  unsigned __int16 *v10; // rax
  const char *v11; // r9
  ULONG dwFlags; // [rsp+20h] [rbp-458h]
  unsigned int v13[4]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR pszPathIn[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR pszPathOut[264]; // [rsp+250h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+0h]

  v13[0] = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, v13);
  if ( PIC < 0 )
  {
    v6 = 3135;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
      (const char *)(unsigned int)PIC,
      dwFlags);
    return (unsigned int)PIC;
  }
  String = IEConfiguration_GetString(268435506);
  PIC = GetAppContainerPath(String, pszPathIn, 260);
  if ( PIC < 0 )
  {
    v6 = 3138;
    goto LABEL_3;
  }
  FileNameW = PathFindFileNameW(a2);
  PIC = PathCchCombineEx(pszPathOut, 0x104u, pszPathIn, FileNameW, 0);
  if ( PIC < 0 )
  {
    v6 = 3143;
    goto LABEL_3;
  }
  v10 = SysAllocString(pszPathOut);
  *a3 = v10;
  if ( !v10 )
  {
    PIC = -2147024882;
    v6 = 3146;
    goto LABEL_3;
  }
  if ( CopyFileW(a2, v10, 0) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xC4B,
             (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\brokerfactory.cpp",
             v11);
}

```

## disassembly

```asm
0x180007af0  mov     [rsp+arg_0], rbx
0x180007af5  mov     [rsp+arg_18], rsi
0x180007afa  push    rdi
0x180007afb  sub     rsp, 470h
0x180007b02  mov     rax, cs:__security_cookie
0x180007b09  xor     rax, rsp
0x180007b0c  mov     [rsp+478h+var_18], rax
0x180007b14  mov     rdi, rdx
0x180007b17  mov     [rsp+478h+var_448], 0
0x180007b1f  lea     rdx, [rsp+478h+var_448]; unsigned int *
0x180007b24  mov     ecx, 1; unsigned int
0x180007b29  mov     rsi, r8
0x180007b2c  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180007b31  mov     ebx, eax
0x180007b33  test    eax, eax
0x180007b35  jns     short loc_180007B5A
0x180007b37  mov     edx, 0C3Fh; void *
0x180007b3c  mov     rcx, [rsp+478h]; this
0x180007b44  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180007b4b  mov     r9d, ebx; char *
0x180007b4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b53  mov     eax, ebx
0x180007b55  jmp     loc_180007C17
0x180007b5a  mov     ecx, 10000032h
0x180007b5f  call    cs:__imp_?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x180007b65  mov     r8d, 104h
0x180007b6b  lea     rdx, [rsp+478h+pszPathIn]
0x180007b70  mov     rcx, rax
0x180007b73  call    cs:__imp_GetAppContainerPath
0x180007b79  mov     ebx, eax
0x180007b7b  test    eax, eax
0x180007b7d  jns     short loc_180007B86
0x180007b7f  mov     edx, 0C42h
0x180007b84  jmp     short loc_180007B3C
0x180007b86  mov     rcx, rdi; pszPath
0x180007b89  call    cs:__imp_PathFindFileNameW
0x180007b8f  lea     r8, [rsp+478h+pszPathIn]; pszPathIn
0x180007b94  mov     [rsp+478h+dwFlags], 0; dwFlags
0x180007b9c  mov     r9, rax; pszMore
0x180007b9f  lea     rcx, [rsp+478h+pszPathOut]; pszPathOut
0x180007ba7  mov     edx, 104h; cchPathOut
0x180007bac  call    cs:__imp_PathCchCombineEx
0x180007bb2  mov     ebx, eax
0x180007bb4  test    eax, eax
0x180007bb6  jns     short loc_180007BC2
0x180007bb8  mov     edx, 0C47h
0x180007bbd  jmp     loc_180007B3C
0x180007bc2  lea     rcx, [rsp+478h+pszPathOut]; psz
0x180007bca  call    cs:__imp_SysAllocString
0x180007bd0  mov     [rsi], rax
0x180007bd3  test    rax, rax
0x180007bd6  jnz     short loc_180007BE7
0x180007bd8  mov     ebx, 8007000Eh
0x180007bdd  mov     edx, 0C4Ah
0x180007be2  jmp     loc_180007B3C
0x180007be7  xor     r8d, r8d; bFailIfExists
0x180007bea  mov     rdx, rax; lpNewFileName
0x180007bed  mov     rcx, rdi; lpExistingFileName
0x180007bf0  call    cs:__imp_CopyFileW
0x180007bf6  test    eax, eax
0x180007bf8  jnz     short loc_180007C15
0x180007bfa  mov     rcx, [rsp+478h]; this
0x180007c02  lea     r8, aOnecoreuapInet_0; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x180007c09  mov     edx, 0C4Bh; void *
0x180007c0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007c13  jmp     short loc_180007C17
0x180007c15  xor     eax, eax
0x180007c17  mov     rcx, [rsp+478h+var_18]
0x180007c1f  xor     rcx, rsp; StackCookie
0x180007c22  call    __security_check_cookie
0x180007c27  lea     r11, [rsp+478h+var_8]
0x180007c2f  mov     rbx, [r11+10h]
0x180007c33  mov     rsi, [r11+28h]
0x180007c37  mov     rsp, r11
0x180007c3a  pop     rdi
0x180007c3b  retn
```
