# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000902c`
- end: `0x180009173`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000902c`
- `0x1800094ec`

## callees

- `0x180004180`
- `0x1800077f0`
- `0x18000902c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000910e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000910e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800090aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009144`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800090aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009122`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009144`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000908d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000908d`

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
0x18000902c  mov     [rsp-8+arg_10], rbx
0x180009031  mov     [rsp-8+arg_18], rsi
0x180009036  push    rbp
0x180009037  push    rdi
0x180009038  push    r14
0x18000903a  lea     rbp, [rsp-180h]
0x180009042  sub     rsp, 280h
0x180009049  mov     rax, cs:__security_cookie
0x180009050  xor     rax, rsp
0x180009053  mov     [rbp+190h+var_20], rax
0x18000905a  xor     r14d, r14d
0x18000905d  lea     rax, [rsp+290h+var_230]
0x180009062  mov     rdi, rcx
0x180009065  mov     [rsp+290h+hKey], r14
0x18000906a  mov     rcx, [rcx]; hKey
0x18000906d  mov     r9d, 2001Fh; samDesired
0x180009073  xor     r8d, r8d; ulOptions
0x180009076  mov     [rsp+290h+var_240], r14
0x18000907b  mov     [rsp+290h+var_238], r14
0x180009080  mov     rsi, rdx
0x180009083  mov     [rsp+290h+var_230], r14
0x180009088  mov     [rsp+290h+phkResult], rax; phkResult
0x18000908d  call    cs:__imp_RegOpenKeyExW
0x180009093  mov     rcx, [rsp+290h+hKey]; hKey
0x180009098  mov     ebx, eax
0x18000909a  test    eax, eax
0x18000909c  jnz     loc_18000913F
0x1800090a2  mov     ebx, r14d
0x1800090a5  test    rcx, rcx
0x1800090a8  jz      short loc_1800090B2
0x1800090aa  call    cs:__imp_RegCloseKey
0x1800090b0  mov     ebx, eax
0x1800090b2  mov     rcx, [rsp+290h+var_230]
0x1800090b7  mov     [rsp+290h+hKey], rcx
0x1800090bc  test    ebx, ebx
0x1800090be  jnz     short loc_18000913F
0x1800090c0  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800090c5  jmp     short loc_1800090E1
0x1800090c7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800090cc  lea     rcx, [rsp+290h+hKey]; this
0x1800090d1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800090d6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800090db  mov     ebx, eax
0x1800090dd  test    eax, eax
0x1800090df  jnz     short loc_18000913F
0x1800090e1  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800090e6  mov     [rsp+290h+cchName], 100h
0x1800090ee  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800090f3  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800090f8  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800090fd  lea     r8, [rsp+290h+Name]; lpName
0x180009102  mov     [rsp+290h+lpClass], r14; lpClass
0x180009107  xor     edx, edx; dwIndex
0x180009109  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000910e  call    cs:__imp_RegEnumKeyExW
0x180009114  test    eax, eax
0x180009116  jz      short loc_1800090C7
0x180009118  mov     rcx, [rsp+290h+hKey]; hKey
0x18000911d  test    rcx, rcx
0x180009120  jz      short loc_18000912D
0x180009122  call    cs:__imp_RegCloseKey
0x180009128  mov     [rsp+290h+hKey], r14
0x18000912d  mov     rdx, rsi; unsigned __int16 *
0x180009130  mov     rcx, rdi; this
0x180009133  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009138  mov     rcx, [rsp+290h+hKey]; hKey
0x18000913d  mov     ebx, eax
0x18000913f  test    rcx, rcx
0x180009142  jz      short loc_18000914A
0x180009144  call    cs:__imp_RegCloseKey
0x18000914a  mov     eax, ebx
0x18000914c  mov     rcx, [rbp+190h+var_20]
0x180009153  xor     rcx, rsp; StackCookie
0x180009156  call    __security_check_cookie
0x18000915b  lea     r11, [rsp+290h+var_10]
0x180009163  mov     rbx, [r11+30h]
0x180009167  mov     rsi, [r11+38h]
0x18000916b  mov     rsp, r11
0x18000916e  pop     r14
0x180009170  pop     rdi
0x180009171  pop     rbp
0x180009172  retn
```
