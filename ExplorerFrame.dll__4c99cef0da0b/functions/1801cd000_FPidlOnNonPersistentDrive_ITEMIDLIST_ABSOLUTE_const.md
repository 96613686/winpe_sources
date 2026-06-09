# FPidlOnNonPersistentDrive(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x1801cd000`
- end: `0x1801cd15c`
- name: `?FPidlOnNonPersistentDrive@@YAHPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800fb68c`

## callees

- `0x180039680`
- `0x1800941dc`
- `0x18013f7d0`
- `0x1801406ec`
- `0x1801cd000`

## import_xrefs

- `SHCORE!__imp_IsNetDrive` at `0x1801cd082`
- `SHCORE!__imp_IsNetDrive` at `0x1801cd082`
- `SHELL32!__imp_SHGetPathFromIDListAlloc` at `0x1801cd04b`
- `SHELL32!__imp_SHGetPathFromIDListAlloc` at `0x1801cd04b`
- `SHLWAPI!PathGetDriveNumberW` at `0x1801cd07a`
- `SHLWAPI!PathGetDriveNumberW` at `0x1801cd07a`
- `SHLWAPI!PathIsUNCW` at `0x1801cd067`
- `SHLWAPI!PathIsUNCW` at `0x1801cd067`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1801cd0fa`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1801cd10b`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1801cd0fa`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x1801cd10b`
- `MPR!WNetEnumResourceW` at `0x1801cd0e3`
- `MPR!WNetEnumResourceW` at `0x1801cd0e3`
- `MPR!WNetCloseEnum` at `0x1801cd11d`
- `MPR!WNetCloseEnum` at `0x1801cd11d`
- `MPR!WNetOpenEnumW` at `0x1801cd0a9`
- `MPR!WNetOpenEnumW` at `0x1801cd0a9`

## pseudocode

```c
__int64 __fastcall FPidlOnNonPersistentDrive(const struct _ITEMIDLIST_ABSOLUTE *a1)
{
  int DriveNumberW; // eax
  unsigned int v3; // edi
  unsigned __int16 v4; // bx
  LPCWSTR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  DWORD BufferSize; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cCount; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE hEnum; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Buffer[16]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v11; // [rsp+60h] [rbp-A0h]

  hEnum = 0;
  pszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPath,
    0);
  if ( (int)SHGetPathFromIDListAlloc(a1, &pszPath, 0) >= 0 && *pszPath )
  {
    if ( PathIsUNCW(pszPath) || (DriveNumberW = PathGetDriveNumberW(pszPath), !IsNetDrive(DriveNumberW)) )
    {
      v3 = 0;
    }
    else
    {
      v3 = 1;
      if ( !WNetOpenEnumW(3u, 1u, 0x12u, 0, &hEnum) )
      {
        cCount = 1;
        memset_0(Buffer, 0, 0x800u);
        BufferSize = 2048;
        while ( !WNetEnumResourceW(hEnum, &cCount, Buffer, &BufferSize) )
        {
          if ( v11 )
          {
            v4 = (unsigned __int16)CharUpperW((LPWSTR)*v11);
            if ( v4 == (unsigned __int16)CharUpperW((LPWSTR)*pszPath) )
            {
              v3 = 0;
              break;
            }
          }
        }
        WNetCloseEnum(hEnum);
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszPath);
    return v3;
  }
  else
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszPath);
    return 0;
  }
}

```

## disassembly

```asm
0x1801cd000  push    rbp
0x1801cd002  push    rbx
0x1801cd003  push    rsi
0x1801cd004  push    rdi
0x1801cd005  lea     rbp, [rsp-768h]
0x1801cd00d  sub     rsp, 868h
0x1801cd014  mov     rax, cs:__security_cookie
0x1801cd01b  xor     rax, rsp
0x1801cd01e  mov     [rbp+780h+var_30], rax
0x1801cd025  mov     rbx, rcx
0x1801cd028  xor     esi, esi
0x1801cd02a  lea     rcx, [rsp+880h+pszPath]
0x1801cd02f  mov     [rsp+880h+hEnum], rsi
0x1801cd034  xor     edx, edx
0x1801cd036  mov     [rsp+880h+pszPath], rsi
0x1801cd03b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801cd040  xor     r8d, r8d
0x1801cd043  lea     rdx, [rsp+880h+pszPath]
0x1801cd048  mov     rcx, rbx
0x1801cd04b  call    cs:__imp_SHGetPathFromIDListAlloc
0x1801cd051  test    eax, eax
0x1801cd053  js      loc_1801CD135
0x1801cd059  mov     rcx, [rsp+880h+pszPath]; pszPath
0x1801cd05e  cmp     [rcx], si
0x1801cd061  jz      loc_1801CD135
0x1801cd067  call    cs:__imp_PathIsUNCW
0x1801cd06d  test    eax, eax
0x1801cd06f  jnz     loc_1801CD125
0x1801cd075  mov     rcx, [rsp+880h+pszPath]; pszPath
0x1801cd07a  call    cs:__imp_PathGetDriveNumberW
0x1801cd080  mov     ecx, eax; iDrive
0x1801cd082  call    cs:__imp_IsNetDrive
0x1801cd088  test    eax, eax
0x1801cd08a  jz      loc_1801CD125
0x1801cd090  lea     rax, [rsp+880h+hEnum]
0x1801cd095  xor     r9d, r9d; lpNetResource
0x1801cd098  lea     edi, [rsi+1]
0x1801cd09b  mov     [rsp+880h+lphEnum], rax; lphEnum
0x1801cd0a0  mov     edx, edi; dwType
0x1801cd0a2  lea     r8d, [rsi+12h]; dwUsage
0x1801cd0a6  lea     ecx, [rsi+3]; dwScope
0x1801cd0a9  call    cs:__imp_WNetOpenEnumW
0x1801cd0af  test    eax, eax
0x1801cd0b1  jnz     short loc_1801CD127
0x1801cd0b3  mov     ebx, 800h
0x1801cd0b8  mov     [rsp+880h+cCount], edi
0x1801cd0bc  mov     r8d, ebx; Size
0x1801cd0bf  lea     rcx, [rsp+880h+Buffer]; void *
0x1801cd0c4  xor     edx, edx; Val
0x1801cd0c6  call    memset_0
0x1801cd0cb  mov     [rsp+880h+BufferSize], ebx
0x1801cd0cf  mov     rcx, [rsp+880h+hEnum]; hEnum
0x1801cd0d4  lea     r9, [rsp+880h+BufferSize]; lpBufferSize
0x1801cd0d9  lea     r8, [rsp+880h+Buffer]; lpBuffer
0x1801cd0de  lea     rdx, [rsp+880h+cCount]; lpcCount
0x1801cd0e3  call    cs:__imp_WNetEnumResourceW
0x1801cd0e9  test    eax, eax
0x1801cd0eb  jnz     short loc_1801CD118
0x1801cd0ed  mov     rax, [rsp+880h+var_820]
0x1801cd0f2  test    rax, rax
0x1801cd0f5  jz      short loc_1801CD0CF
0x1801cd0f7  movzx   ecx, word ptr [rax]; lpsz
0x1801cd0fa  call    cs:__imp_CharUpperW
0x1801cd100  mov     rcx, [rsp+880h+pszPath]
0x1801cd105  mov     rbx, rax
0x1801cd108  movzx   ecx, word ptr [rcx]; lpsz
0x1801cd10b  call    cs:__imp_CharUpperW
0x1801cd111  cmp     bx, ax
0x1801cd114  jnz     short loc_1801CD0CF
0x1801cd116  mov     edi, esi
0x1801cd118  mov     rcx, [rsp+880h+hEnum]; hEnum
0x1801cd11d  call    cs:__imp_WNetCloseEnum
0x1801cd123  jmp     short loc_1801CD127
0x1801cd125  mov     edi, esi
0x1801cd127  lea     rcx, [rsp+880h+pszPath]; void *
0x1801cd12c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1801cd131  mov     eax, edi
0x1801cd133  jmp     short loc_1801CD141
0x1801cd135  lea     rcx, [rsp+880h+pszPath]; void *
0x1801cd13a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1801cd13f  xor     eax, eax
0x1801cd141  mov     rcx, [rbp+780h+var_30]
0x1801cd148  xor     rcx, rsp; StackCookie
0x1801cd14b  call    __security_check_cookie
0x1801cd150  add     rsp, 868h
0x1801cd157  pop     rdi
0x1801cd158  pop     rsi
0x1801cd159  pop     rbx
0x1801cd15a  pop     rbp
0x1801cd15b  retn
```
