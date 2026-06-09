# EEDBManager::DeleteEnrollment(_GUID)

- ea: `0x180017d40`
- end: `0x180017e24`
- name: `?DeleteEnrollment@EEDBManager@@UEAAJU_GUID@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(EEDBManager *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001c60`
- `0x1800051d8`
- `0x180017d40`
- `0x180017e2c`
- `0x1800188f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180017dfc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180017dfc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180017d89`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180017d89`

## pseudocode

```c
__int64 __fastcall EEDBManager::DeleteEnrollment(EEDBManager *this, struct _GUID *a2)
{
  GUID v2; // xmm0
  int v3; // ebx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  GUID rguid; // [rsp+30h] [rbp-2D8h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-2C8h] BYREF
  unsigned __int16 v8[40]; // [rsp+90h] [rbp-278h] BYREF
  WCHAR SubKey[264]; // [rsp+E0h] [rbp-228h] BYREF

  v2 = *a2;
  SubKey[0] = 0;
  rguid = v2;
  v8[0] = 0;
  sz[0] = 0;
  if ( StringFromGUID2(&rguid, sz, 39) == 39 )
  {
    v3 = EEDBTrimGuidBracket(sz, v8);
    if ( v3 >= 0 )
    {
      EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
      v3 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", EnrollmentsRootKey, v8);
      if ( v3 >= 0 )
        RegDeleteTreeW(HKEY_LOCAL_MACHINE, SubKey);
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017d40  push    rbx
0x180017d42  sub     rsp, 300h
0x180017d49  mov     rax, cs:__security_cookie
0x180017d50  xor     rax, rsp
0x180017d53  mov     [rsp+308h+var_18], rax
0x180017d5b  movups  xmm0, xmmword ptr [rdx]
0x180017d5e  xor     eax, eax
0x180017d60  lea     rdx, [rsp+308h+sz]; lpsz
0x180017d65  lea     rcx, [rsp+308h+rguid]; rguid
0x180017d6a  mov     [rsp+308h+SubKey], ax
0x180017d72  movdqu  xmmword ptr [rsp+308h+rguid.Data1], xmm0
0x180017d78  mov     [rsp+308h+var_278], ax
0x180017d80  lea     r8d, [rax+27h]; cchMax
0x180017d84  mov     [rsp+308h+sz], ax
0x180017d89  call    cs:__imp_StringFromGUID2
0x180017d90  nop     dword ptr [rax+rax+00h]
0x180017d95  cmp     eax, 27h ; '''
0x180017d98  jz      short loc_180017DA1
0x180017d9a  mov     ebx, 8000FFFFh
0x180017d9f  jmp     short loc_180017E08
0x180017da1  lea     rdx, [rsp+308h+var_278]; unsigned __int16 *
0x180017da9  lea     rcx, [rsp+308h+sz]; unsigned __int16 *
0x180017dae  call    ?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z; EEDBTrimGuidBracket(ushort const *,ushort *)
0x180017db3  mov     ebx, eax
0x180017db5  test    eax, eax
0x180017db7  js      short loc_180017E08
0x180017db9  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x180017dbe  mov     r9, rax
0x180017dc1  lea     r8, aSS; "%s\\%s"
0x180017dc8  lea     rax, [rsp+308h+var_278]
0x180017dd0  mov     edx, 104h; unsigned __int64
0x180017dd5  lea     rcx, [rsp+308h+SubKey]; unsigned __int16 *
0x180017ddd  mov     [rsp+308h+var_2E8], rax
0x180017de2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017de7  mov     ebx, eax
0x180017de9  test    eax, eax
0x180017deb  js      short loc_180017E08
0x180017ded  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x180017df5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017dfc  call    cs:__imp_RegDeleteTreeW
0x180017e03  nop     dword ptr [rax+rax+00h]
0x180017e08  mov     eax, ebx
0x180017e0a  mov     rcx, [rsp+308h+var_18]
0x180017e12  xor     rcx, rsp; StackCookie
0x180017e15  call    __security_check_cookie
0x180017e1a  add     rsp, 300h
0x180017e21  pop     rbx
0x180017e22  retn
```
