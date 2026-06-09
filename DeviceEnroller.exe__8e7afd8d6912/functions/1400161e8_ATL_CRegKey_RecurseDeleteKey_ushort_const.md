# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1400161e8`
- end: `0x14001632f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400161e8`
- `0x140016794`

## callees

- `0x1400042f0`
- `0x14000e87c`
- `0x1400161e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016249`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140016249`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016266`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400162de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016300`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016266`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400162de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140016300`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400162ca`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1400162ca`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x1400161e8  mov     [rsp-8+arg_10], rbx
0x1400161ed  mov     [rsp-8+arg_18], rsi
0x1400161f2  push    rbp
0x1400161f3  push    rdi
0x1400161f4  push    r14
0x1400161f6  lea     rbp, [rsp-180h]
0x1400161fe  sub     rsp, 280h
0x140016205  mov     rax, cs:__security_cookie
0x14001620c  xor     rax, rsp
0x14001620f  mov     [rbp+190h+var_20], rax
0x140016216  xor     r14d, r14d
0x140016219  lea     rax, [rsp+290h+var_230]
0x14001621e  mov     rdi, rcx
0x140016221  mov     [rsp+290h+hKey], r14
0x140016226  mov     rcx, [rcx]; hKey
0x140016229  mov     r9d, 2001Fh; samDesired
0x14001622f  xor     r8d, r8d; ulOptions
0x140016232  mov     [rsp+290h+var_240], r14
0x140016237  mov     [rsp+290h+var_238], r14
0x14001623c  mov     rsi, rdx
0x14001623f  mov     [rsp+290h+var_230], r14
0x140016244  mov     [rsp+290h+phkResult], rax; phkResult
0x140016249  call    cs:__imp_RegOpenKeyExW
0x14001624f  mov     rcx, [rsp+290h+hKey]; hKey
0x140016254  mov     ebx, eax
0x140016256  test    eax, eax
0x140016258  jnz     loc_1400162FB
0x14001625e  mov     ebx, r14d
0x140016261  test    rcx, rcx
0x140016264  jz      short loc_14001626E
0x140016266  call    cs:__imp_RegCloseKey
0x14001626c  mov     ebx, eax
0x14001626e  mov     rcx, [rsp+290h+var_230]
0x140016273  mov     [rsp+290h+hKey], rcx
0x140016278  test    ebx, ebx
0x14001627a  jnz     short loc_1400162FB
0x14001627c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x140016281  jmp     short loc_14001629D
0x140016283  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x140016288  lea     rcx, [rsp+290h+hKey]; this
0x14001628d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140016292  mov     rcx, [rsp+290h+hKey]; hKey
0x140016297  mov     ebx, eax
0x140016299  test    eax, eax
0x14001629b  jnz     short loc_1400162FB
0x14001629d  lea     rax, [rsp+290h+ftLastWriteTime]
0x1400162a2  mov     [rsp+290h+cchName], 100h
0x1400162aa  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400162af  lea     r9, [rsp+290h+cchName]; lpcchName
0x1400162b4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1400162b9  lea     r8, [rsp+290h+Name]; lpName
0x1400162be  mov     [rsp+290h+lpClass], r14; lpClass
0x1400162c3  xor     edx, edx; dwIndex
0x1400162c5  mov     [rsp+290h+phkResult], r14; lpReserved
0x1400162ca  call    cs:__imp_RegEnumKeyExW
0x1400162d0  test    eax, eax
0x1400162d2  jz      short loc_140016283
0x1400162d4  mov     rcx, [rsp+290h+hKey]; hKey
0x1400162d9  test    rcx, rcx
0x1400162dc  jz      short loc_1400162E9
0x1400162de  call    cs:__imp_RegCloseKey
0x1400162e4  mov     [rsp+290h+hKey], r14
0x1400162e9  mov     rdx, rsi; unsigned __int16 *
0x1400162ec  mov     rcx, rdi; this
0x1400162ef  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1400162f4  mov     rcx, [rsp+290h+hKey]; hKey
0x1400162f9  mov     ebx, eax
0x1400162fb  test    rcx, rcx
0x1400162fe  jz      short loc_140016306
0x140016300  call    cs:__imp_RegCloseKey
0x140016306  mov     eax, ebx
0x140016308  mov     rcx, [rbp+190h+var_20]
0x14001630f  xor     rcx, rsp; StackCookie
0x140016312  call    __security_check_cookie
0x140016317  lea     r11, [rsp+290h+var_10]
0x14001631f  mov     rbx, [r11+30h]
0x140016323  mov     rsi, [r11+38h]
0x140016327  mov     rsp, r11
0x14001632a  pop     r14
0x14001632c  pop     rdi
0x14001632d  pop     rbp
0x14001632e  retn
```
