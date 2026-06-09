# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180019bcc`
- end: `0x180019ce4`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `280`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180019bcc`
- `0x18001a0d8`

## callees

- `0x18000fd88`
- `0x18000fde8`
- `0x180016a40`
- `0x180019470`
- `0x180019bcc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019c7c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019c7c`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v4 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, *this, a2, 0x2001Fu);
  if ( !v4 )
  {
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(hKey[0], 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_7;
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return v4;
}

```

## disassembly

```asm
0x180019bcc  mov     [rsp-8+arg_10], rbx
0x180019bd1  push    rbp
0x180019bd2  push    rsi
0x180019bd3  push    rdi
0x180019bd4  lea     rbp, [rsp-180h]
0x180019bdc  sub     rsp, 280h
0x180019be3  mov     rax, cs:__security_cookie
0x180019bea  xor     rax, rsp
0x180019bed  mov     [rbp+190h+var_20], rax
0x180019bf4  mov     rsi, rdx
0x180019bf7  mov     [rsp+290h+hKey], 0
0x180019c00  mov     r8, rdx; lpSubKey
0x180019c03  mov     [rsp+290h+var_240], 0
0x180019c0c  mov     rdx, [rcx]; hKey
0x180019c0f  mov     rdi, rcx
0x180019c12  lea     rcx, [rsp+290h+hKey]; this
0x180019c17  mov     [rsp+290h+var_238], 0
0x180019c20  mov     r9d, 2001Fh; unsigned int
0x180019c26  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180019c2b  mov     ebx, eax
0x180019c2d  test    eax, eax
0x180019c2f  jnz     loc_180019CB5
0x180019c35  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180019c3e  mov     rcx, [rsp+290h+hKey]; hKey
0x180019c43  lea     rax, [rsp+290h+ftLastWriteTime]
0x180019c48  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180019c4d  lea     r9, [rsp+290h+cchName]; lpcchName
0x180019c52  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180019c5b  lea     r8, [rsp+290h+Name]; lpName
0x180019c60  mov     [rsp+290h+lpClass], 0; lpClass
0x180019c69  xor     edx, edx; dwIndex
0x180019c6b  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180019c74  mov     [rsp+290h+cchName], 100h
0x180019c7c  call    cs:__imp_RegEnumKeyExW
0x180019c83  nop     dword ptr [rax+rax+00h]
0x180019c88  lea     rcx, [rsp+290h+hKey]; this
0x180019c8d  test    eax, eax
0x180019c8f  jnz     short loc_180019CA3
0x180019c91  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180019c96  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180019c9b  mov     ebx, eax
0x180019c9d  test    eax, eax
0x180019c9f  jnz     short loc_180019CB5
0x180019ca1  jmp     short loc_180019C3E
0x180019ca3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019ca8  mov     rdx, rsi; unsigned __int16 *
0x180019cab  mov     rcx, rdi; this
0x180019cae  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180019cb3  mov     ebx, eax
0x180019cb5  lea     rcx, [rsp+290h+hKey]; this
0x180019cba  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019cbf  mov     eax, ebx
0x180019cc1  mov     rcx, [rbp+190h+var_20]
0x180019cc8  xor     rcx, rsp; StackCookie
0x180019ccb  call    __security_check_cookie
0x180019cd0  mov     rbx, [rsp+290h+arg_10]
0x180019cd8  add     rsp, 280h
0x180019cdf  pop     rdi
0x180019ce0  pop     rsi
0x180019ce1  pop     rbp
0x180019ce2  retn
```
