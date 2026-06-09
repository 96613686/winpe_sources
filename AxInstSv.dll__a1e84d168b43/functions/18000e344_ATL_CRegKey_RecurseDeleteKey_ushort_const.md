# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000e344`
- end: `0x18000e451`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000e344`
- `0x18000e810`

## callees

- `0x180001720`
- `0x18000a1a0`
- `0x18000a880`
- `0x18000d354`
- `0x18000e344`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e3f0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e3f0`

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
0x18000e344  mov     [rsp-8+arg_10], rbx
0x18000e349  push    rbp
0x18000e34a  push    rsi
0x18000e34b  push    rdi
0x18000e34c  lea     rbp, [rsp-180h]
0x18000e354  sub     rsp, 280h
0x18000e35b  mov     rax, cs:__security_cookie
0x18000e362  xor     rax, rsp
0x18000e365  mov     [rbp+190h+var_20], rax
0x18000e36c  mov     rsi, rdx
0x18000e36f  mov     [rsp+290h+hKey], 0
0x18000e378  mov     r8, rdx; lpSubKey
0x18000e37b  mov     [rsp+290h+var_240], 0
0x18000e384  mov     rdx, [rcx]; hKey
0x18000e387  mov     rdi, rcx
0x18000e38a  lea     rcx, [rsp+290h+hKey]; this
0x18000e38f  mov     [rsp+290h+var_238], 0
0x18000e398  mov     r9d, 2001Fh; unsigned int
0x18000e39e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000e3a3  mov     ebx, eax
0x18000e3a5  test    eax, eax
0x18000e3a7  jnz     short loc_18000E423
0x18000e3a9  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x18000e3b2  mov     rcx, [rsp+290h+hKey]; hKey
0x18000e3b7  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000e3bc  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000e3c1  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000e3c6  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x18000e3cf  lea     r8, [rsp+290h+Name]; lpName
0x18000e3d4  mov     [rsp+290h+lpClass], 0; lpClass
0x18000e3dd  xor     edx, edx; dwIndex
0x18000e3df  mov     [rsp+290h+lpReserved], 0; lpReserved
0x18000e3e8  mov     [rsp+290h+cchName], 100h
0x18000e3f0  call    cs:__imp_RegEnumKeyExW
0x18000e3f6  lea     rcx, [rsp+290h+hKey]; this
0x18000e3fb  test    eax, eax
0x18000e3fd  jnz     short loc_18000E411
0x18000e3ff  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000e404  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000e409  mov     ebx, eax
0x18000e40b  test    eax, eax
0x18000e40d  jnz     short loc_18000E423
0x18000e40f  jmp     short loc_18000E3B2
0x18000e411  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e416  mov     rdx, rsi; unsigned __int16 *
0x18000e419  mov     rcx, rdi; this
0x18000e41c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000e421  mov     ebx, eax
0x18000e423  lea     rcx, [rsp+290h+hKey]; this
0x18000e428  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000e42d  mov     eax, ebx
0x18000e42f  mov     rcx, [rbp+190h+var_20]
0x18000e436  xor     rcx, rsp; StackCookie
0x18000e439  call    __security_check_cookie
0x18000e43e  mov     rbx, [rsp+290h+arg_10]
0x18000e446  add     rsp, 280h
0x18000e44d  pop     rdi
0x18000e44e  pop     rsi
0x18000e44f  pop     rbp
0x18000e450  retn
```
