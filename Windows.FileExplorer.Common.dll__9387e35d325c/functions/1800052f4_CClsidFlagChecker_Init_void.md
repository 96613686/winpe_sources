# CClsidFlagChecker::_Init(void)

- ea: `0x1800052f4`
- end: `0x1800053e1`
- name: `?_Init@CClsidFlagChecker@@AEAAJXZ`
- size: `237`
- prototype: `__int64 __fastcall(CClsidFlagChecker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000524c`

## callees

- `0x1800052f4`
- `0x180006bc8`
- `0x180037780`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000532c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000532c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005395`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005395`

## string_xrefs

- `0x18000534d`: `CLSID\%s`
- `0x1800053ce`: `ExplorerCLSIDFlags\%s`

## pseudocode

```c
__int64 __fastcall CClsidFlagChecker::_Init(CClsidFlagChecker *this)
{
  unsigned int v1; // edx
  int v3; // eax
  int v4; // eax
  LSTATUS v5; // eax
  OLECHAR sz[40]; // [rsp+30h] [rbp-138h] BYREF
  WCHAR SubKey[104]; // [rsp+80h] [rbp-E8h] BYREF

  v1 = *((_DWORD *)this + 8);
  if ( v1 == -2147221497 )
  {
    v3 = StringFromGUID2((const GUID *const)this, sz, 39);
    v1 = v3 == 0 ? 0x80004005 : 0;
    *((_DWORD *)this + 8) = v1;
    if ( v3 )
    {
      if ( *((_DWORD *)this + 4) )
      {
        if ( *((_DWORD *)this + 4) != 1 )
        {
          v1 = -2147023728;
LABEL_8:
          *((_DWORD *)this + 8) = v1;
          return v1;
        }
        v4 = StringCchPrintfW(SubKey, 0x67u, L"ExplorerCLSIDFlags\\%s", sz);
      }
      else
      {
        v4 = StringCchPrintfW(SubKey, 0x67u, L"CLSID\\%s", sz);
      }
      *((_DWORD *)this + 8) = v4;
      v1 = v4;
      if ( v4 >= 0 )
      {
        v5 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, (PHKEY)this + 3);
        v1 = v5;
        if ( v5 > 0 )
          v1 = (unsigned __int16)v5 | 0x80070000;
        goto LABEL_8;
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800052f4  push    rbx
0x1800052f6  sub     rsp, 160h
0x1800052fd  mov     rax, cs:__security_cookie
0x180005304  xor     rax, rsp
0x180005307  mov     [rsp+168h+var_18], rax
0x18000530f  mov     edx, [rcx+20h]
0x180005312  mov     rbx, rcx
0x180005315  cmp     edx, 80040007h
0x18000531b  jnz     loc_1800053AD
0x180005321  mov     r8d, 27h ; '''; cchMax
0x180005327  lea     rdx, [rsp+168h+sz]; lpsz
0x18000532c  call    cs:__imp_StringFromGUID2
0x180005332  mov     ecx, eax
0x180005334  neg     ecx
0x180005336  sbb     edx, edx
0x180005338  not     edx
0x18000533a  and     edx, 80004005h
0x180005340  mov     [rbx+20h], edx
0x180005343  test    eax, eax
0x180005345  jz      short loc_1800053AD
0x180005347  cmp     dword ptr [rbx+10h], 0
0x18000534b  jnz     short loc_1800053C8
0x18000534d  lea     r8, aClsidS; "CLSID\\%s"
0x180005354  lea     r9, [rsp+168h+sz]
0x180005359  mov     edx, 67h ; 'g'; unsigned __int64
0x18000535e  lea     rcx, [rsp+168h+SubKey]; unsigned __int16 *
0x180005366  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000536b  mov     [rbx+20h], eax
0x18000536e  mov     edx, eax
0x180005370  test    eax, eax
0x180005372  js      short loc_1800053AD
0x180005374  lea     rax, [rbx+18h]
0x180005378  mov     r9d, 20019h; samDesired
0x18000537e  xor     r8d, r8d; ulOptions
0x180005381  mov     [rsp+168h+phkResult], rax; phkResult
0x180005386  lea     rdx, [rsp+168h+SubKey]; lpSubKey
0x18000538e  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005395  call    cs:__imp_RegOpenKeyExW
0x18000539b  mov     edx, eax
0x18000539d  test    eax, eax
0x18000539f  jle     short loc_1800053AA
0x1800053a1  movzx   edx, ax
0x1800053a4  or      edx, 80070000h
0x1800053aa  mov     [rbx+20h], edx
0x1800053ad  mov     eax, edx
0x1800053af  mov     rcx, [rsp+168h+var_18]
0x1800053b7  xor     rcx, rsp; StackCookie
0x1800053ba  call    __security_check_cookie
0x1800053bf  add     rsp, 160h
0x1800053c6  pop     rbx
0x1800053c7  retn
0x1800053c8  cmp     dword ptr [rbx+10h], 1
0x1800053cc  jnz     short loc_1800053DA
0x1800053ce  lea     r8, aExplorerclsidf; "ExplorerCLSIDFlags\\%s"
0x1800053d5  jmp     loc_180005354
0x1800053da  mov     edx, 80070490h
0x1800053df  jmp     short loc_1800053AA
```
