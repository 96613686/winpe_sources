# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180018a88`
- end: `0x180018b87`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `255`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018a88`
- `0x180018fb0`

## callees

- `0x18000ee1c`
- `0x1800161e0`
- `0x180017490`
- `0x180018a88`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180018b1f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180018b1f`

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
0x180018a88  mov     [rsp-8+arg_10], rbx
0x180018a8d  push    rbp
0x180018a8e  push    rsi
0x180018a8f  push    rdi
0x180018a90  lea     rbp, [rsp-180h]
0x180018a98  sub     rsp, 280h
0x180018a9f  mov     rax, cs:__security_cookie
0x180018aa6  xor     rax, rsp
0x180018aa9  mov     [rbp+190h+var_20], rax
0x180018ab0  and     [rsp+290h+hKey], 0
0x180018ab6  mov     rsi, rdx
0x180018ab9  and     [rsp+290h+var_240], 0
0x180018abf  mov     r8, rdx; lpSubKey
0x180018ac2  mov     rdx, [rcx]; hKey
0x180018ac5  mov     rdi, rcx
0x180018ac8  and     [rsp+290h+var_238], 0
0x180018ace  lea     rcx, [rsp+290h+hKey]; this
0x180018ad3  mov     r9d, 2001Fh; unsigned int
0x180018ad9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180018ade  mov     ebx, eax
0x180018ae0  test    eax, eax
0x180018ae2  jnz     short loc_180018B58
0x180018ae4  and     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], 0
0x180018aea  mov     rcx, [rsp+290h+hKey]; hKey
0x180018aef  lea     rax, [rsp+290h+ftLastWriteTime]
0x180018af4  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180018af9  lea     r9, [rsp+290h+cchName]; lpcchName
0x180018afe  and     [rsp+290h+var_260], 0
0x180018b04  lea     r8, [rsp+290h+Name]; lpName
0x180018b09  and     [rsp+290h+var_268], 0
0x180018b0f  xor     edx, edx; dwIndex
0x180018b11  and     [rsp+290h+var_270], 0
0x180018b17  mov     [rsp+290h+cchName], 100h
0x180018b1f  call    cs:__imp_RegEnumKeyExW
0x180018b26  nop     dword ptr [rax+rax+00h]
0x180018b2b  lea     rcx, [rsp+290h+hKey]; this
0x180018b30  test    eax, eax
0x180018b32  jnz     short loc_180018B46
0x180018b34  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180018b39  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180018b3e  mov     ebx, eax
0x180018b40  test    eax, eax
0x180018b42  jnz     short loc_180018B58
0x180018b44  jmp     short loc_180018AEA
0x180018b46  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018b4b  mov     rdx, rsi; unsigned __int16 *
0x180018b4e  mov     rcx, rdi; this
0x180018b51  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180018b56  mov     ebx, eax
0x180018b58  lea     rcx, [rsp+290h+hKey]; this
0x180018b5d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180018b62  mov     eax, ebx
0x180018b64  mov     rcx, [rbp+190h+var_20]
0x180018b6b  xor     rcx, rsp; StackCookie
0x180018b6e  call    __security_check_cookie
0x180018b73  mov     rbx, [rsp+290h+arg_10]
0x180018b7b  add     rsp, 280h
0x180018b82  pop     rdi
0x180018b83  pop     rsi
0x180018b84  pop     rbp
0x180018b85  retn
```
