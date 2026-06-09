# CSyncDelegateFolder::_GetExtractIcon(_GUID const &,void * *)

- ea: `0x180046b9c`
- end: `0x180046d29`
- name: `?_GetExtractIcon@CSyncDelegateFolder@@AEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `397`
- prototype: `__int64 __fastcall(CSyncDelegateFolder *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180046660`

## callees

- `0x180008584`
- `0x18000b310`
- `0x1800133b0`
- `0x1800134dc`
- `0x180046b9c`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateDefaultExtractIcon` at `0x180046c73`
- `SHELL32!SHCreateDefaultExtractIcon` at `0x180046c73`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180046be6`
- `SHLWAPI!__imp_SHStringFromGUIDW` at `0x180046be6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046cf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046cf1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046c38`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046c38`

## string_xrefs

- `0x180046bfe`: `CLSID\%ws`

## pseudocode

```c
__int64 __fastcall CSyncDelegateFolder::_GetExtractIcon(CSyncDelegateFolder *this, const struct _GUID *a2, void **a3)
{
  char *v3; // rdi
  int Icon; // ebx
  LSTATUS v7; // eax
  void **v8; // rax
  __int64 v10; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = (char *)this + 104;
  if ( *((_WORD *)this + 52) )
    Icon = 0;
  else
    Icon = SHStringFromGUIDW((char *)this + 64, v3, 39);
  if ( Icon >= 0 )
  {
    StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ws", v3);
    hKey = 0;
    v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
    Icon = v7;
    if ( v7 > 0 )
      Icon = (unsigned __int16)v7 | 0x80070000;
    if ( Icon >= 0 )
    {
      ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v10);
      v8 = (void **)ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(&v10);
      Icon = SHCreateDefaultExtractIcon(&GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58, v8);
      if ( Icon >= 0 )
      {
        Icon = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 24LL))(v10, 4);
        if ( Icon >= 0 )
        {
          Icon = (*(__int64 (__fastcall **)(__int64, HKEY))(*(_QWORD *)v10 + 32LL))(v10, hKey);
          if ( Icon >= 0 )
          {
            Icon = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v10 + 40LL))(v10, 0, 3);
            if ( Icon >= 0 )
              Icon = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v10)(v10, a2, a3);
          }
        }
      }
      RegCloseKey(hKey);
      ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v10);
    }
  }
  return (unsigned int)Icon;
}

```

## disassembly

```asm
0x180046b9c  mov     [rsp-8+arg_18], rbx
0x180046ba1  push    rbp
0x180046ba2  push    rsi
0x180046ba3  push    rdi
0x180046ba4  push    r14
0x180046ba6  push    r15
0x180046ba8  lea     rbp, [rsp-160h]
0x180046bb0  sub     rsp, 260h
0x180046bb7  mov     rax, cs:__security_cookie
0x180046bbe  xor     rax, rsp
0x180046bc1  mov     [rbp+180h+var_30], rax
0x180046bc8  lea     rdi, [rcx+68h]
0x180046bcc  xor     r15d, r15d
0x180046bcf  mov     r14, r8
0x180046bd2  mov     rsi, rdx
0x180046bd5  cmp     [rdi], r15w
0x180046bd9  jnz     short loc_180046BF0
0x180046bdb  add     rcx, 40h ; '@'
0x180046bdf  lea     r8d, [r15+27h]
0x180046be3  mov     rdx, rdi
0x180046be6  call    cs:__imp_SHStringFromGUIDW
0x180046bec  mov     ebx, eax
0x180046bee  jmp     short loc_180046BF3
0x180046bf0  mov     ebx, r15d
0x180046bf3  test    ebx, ebx
0x180046bf5  js      loc_180046D01
0x180046bfb  mov     r9, rdi
0x180046bfe  lea     r8, aClsidWs; "CLSID\\%ws"
0x180046c05  mov     edx, 104h; unsigned __int64
0x180046c0a  lea     rcx, [rsp+280h+SubKey]; unsigned __int16 *
0x180046c0f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046c14  lea     rax, [rsp+280h+hKey]
0x180046c19  mov     [rsp+280h+hKey], r15
0x180046c1e  mov     r9d, 20019h; samDesired
0x180046c24  mov     [rsp+280h+phkResult], rax; phkResult
0x180046c29  xor     r8d, r8d; ulOptions
0x180046c2c  lea     rdx, [rsp+280h+SubKey]; lpSubKey
0x180046c31  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180046c38  call    cs:__imp_RegOpenKeyExW
0x180046c3e  mov     ebx, eax
0x180046c40  test    eax, eax
0x180046c42  jle     short loc_180046C4D
0x180046c44  movzx   ebx, ax
0x180046c47  or      ebx, 80070000h
0x180046c4d  test    ebx, ebx
0x180046c4f  js      loc_180046D01
0x180046c55  lea     rcx, [rsp+280h+var_250]; void *
0x180046c5a  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180046c5f  lea     rcx, [rsp+280h+var_250]; void *
0x180046c64  call    ??I?$CComPtrBase@UISyncClientFolderItemCache@@@ATL@@QEAAPEAPEAUISyncClientFolderItemCache@@XZ; ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(void)
0x180046c69  mov     rdx, rax; ppv
0x180046c6c  lea     rcx, _GUID_41ded17d_d6b3_4261_997d_88c60e4b1d58; riid
0x180046c73  call    cs:__imp_SHCreateDefaultExtractIcon
0x180046c79  mov     ebx, eax
0x180046c7b  test    eax, eax
0x180046c7d  js      short loc_180046CEC
0x180046c7f  mov     rcx, [rsp+280h+var_250]
0x180046c84  mov     edx, 4
0x180046c89  mov     rax, [rcx]
0x180046c8c  mov     rax, [rax+18h]
0x180046c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c95  mov     ebx, eax
0x180046c97  test    eax, eax
0x180046c99  js      short loc_180046CEC
0x180046c9b  mov     rcx, [rsp+280h+var_250]
0x180046ca0  mov     rdx, [rsp+280h+hKey]
0x180046ca5  mov     rax, [rcx]
0x180046ca8  mov     rax, [rax+20h]
0x180046cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cb1  mov     ebx, eax
0x180046cb3  test    eax, eax
0x180046cb5  js      short loc_180046CEC
0x180046cb7  mov     rcx, [rsp+280h+var_250]
0x180046cbc  xor     edx, edx
0x180046cbe  mov     rax, [rcx]
0x180046cc1  lea     r8d, [rdx+3]
0x180046cc5  mov     rax, [rax+28h]
0x180046cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cce  mov     ebx, eax
0x180046cd0  test    eax, eax
0x180046cd2  js      short loc_180046CEC
0x180046cd4  mov     rcx, [rsp+280h+var_250]
0x180046cd9  mov     r8, r14
0x180046cdc  mov     rdx, rsi
0x180046cdf  mov     rax, [rcx]
0x180046ce2  mov     rax, [rax]
0x180046ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046cea  mov     ebx, eax
0x180046cec  mov     rcx, [rsp+280h+hKey]; hKey
0x180046cf1  call    cs:__imp_RegCloseKey
0x180046cf7  lea     rcx, [rsp+280h+var_250]
0x180046cfc  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x180046d01  mov     eax, ebx
0x180046d03  mov     rcx, [rbp+180h+var_30]
0x180046d0a  xor     rcx, rsp; StackCookie
0x180046d0d  call    __security_check_cookie
0x180046d12  mov     rbx, [rsp+280h+arg_18]
0x180046d1a  add     rsp, 260h
0x180046d21  pop     r15
0x180046d23  pop     r14
0x180046d25  pop     rdi
0x180046d26  pop     rsi
0x180046d27  pop     rbp
0x180046d28  retn
```
