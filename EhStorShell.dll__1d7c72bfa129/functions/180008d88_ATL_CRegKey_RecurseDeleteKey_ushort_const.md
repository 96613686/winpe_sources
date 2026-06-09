# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180008d88`
- end: `0x180008e95`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `269`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180004fb8`
- `0x180008d88`

## callees

- `0x180006820`
- `0x180008894`
- `0x180008a68`
- `0x180008d88`
- `0x18000b630`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180008e34`
- `ADVAPI32!RegEnumKeyExW` at `0x180008e34`

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
  v4 = ATL::CRegKey::Open(hKey, *this, a2, 0x2001Fu);
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
    ATL::CRegKey::Close(hKey);
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
  }
LABEL_7:
  ATL::CRegKey::Close(hKey);
  return v4;
}

```

## disassembly

```asm
0x180008d88  mov     [rsp-8+arg_10], rbx
0x180008d8d  push    rbp
0x180008d8e  push    rsi
0x180008d8f  push    rdi
0x180008d90  lea     rbp, [rsp-180h]
0x180008d98  sub     rsp, 280h
0x180008d9f  mov     rax, cs:__security_cookie
0x180008da6  xor     rax, rsp
0x180008da9  mov     [rbp+190h+var_20], rax
0x180008db0  mov     rsi, rdx
0x180008db3  mov     [rsp+290h+hKey], 0
0x180008dbc  mov     r8, rdx; lpSubKey
0x180008dbf  mov     [rsp+290h+var_240], 0
0x180008dc8  mov     rdx, [rcx]; hKey
0x180008dcb  mov     rdi, rcx
0x180008dce  lea     rcx, [rsp+290h+hKey]; this
0x180008dd3  mov     [rsp+290h+var_238], 0
0x180008ddc  mov     r9d, 2001Fh; unsigned int
0x180008de2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008de7  mov     ebx, eax
0x180008de9  test    eax, eax
0x180008deb  jnz     short loc_180008E67
0x180008ded  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180008df6  mov     rcx, [rsp+290h+hKey]; hKey
0x180008dfb  lea     rax, [rsp+290h+ftLastWriteTime]
0x180008e00  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180008e05  lea     r9, [rsp+290h+cchName]; lpcchName
0x180008e0a  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180008e13  lea     r8, [rsp+290h+Name]; lpName
0x180008e18  mov     [rsp+290h+lpClass], 0; lpClass
0x180008e21  xor     edx, edx; dwIndex
0x180008e23  mov     [rsp+290h+lpReserved], 0; lpReserved
0x180008e2c  mov     [rsp+290h+cchName], 100h
0x180008e34  call    cs:__imp_RegEnumKeyExW
0x180008e3a  lea     rcx, [rsp+290h+hKey]; this
0x180008e3f  test    eax, eax
0x180008e41  jnz     short loc_180008E55
0x180008e43  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180008e48  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008e4d  mov     ebx, eax
0x180008e4f  test    eax, eax
0x180008e51  jnz     short loc_180008E67
0x180008e53  jmp     short loc_180008DF6
0x180008e55  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008e5a  mov     rdx, rsi; unsigned __int16 *
0x180008e5d  mov     rcx, rdi; this
0x180008e60  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180008e65  mov     ebx, eax
0x180008e67  lea     rcx, [rsp+290h+hKey]; this
0x180008e6c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008e71  mov     eax, ebx
0x180008e73  mov     rcx, [rbp+190h+var_20]
0x180008e7a  xor     rcx, rsp; StackCookie
0x180008e7d  call    __security_check_cookie
0x180008e82  mov     rbx, [rsp+290h+arg_10]
0x180008e8a  add     rsp, 280h
0x180008e91  pop     rdi
0x180008e92  pop     rsi
0x180008e93  pop     rbp
0x180008e94  retn
```
