# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000863c`
- end: `0x180008783`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000863c`
- `0x180008afc`

## callees

- `0x1800038f0`
- `0x180006dc0`
- `0x18000863c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008732`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008754`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800086ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008732`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008754`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000869d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000869d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000871e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000871e`

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
0x18000863c  mov     [rsp-8+arg_10], rbx
0x180008641  mov     [rsp-8+arg_18], rsi
0x180008646  push    rbp
0x180008647  push    rdi
0x180008648  push    r14
0x18000864a  lea     rbp, [rsp-180h]
0x180008652  sub     rsp, 280h
0x180008659  mov     rax, cs:__security_cookie
0x180008660  xor     rax, rsp
0x180008663  mov     [rbp+190h+var_20], rax
0x18000866a  xor     r14d, r14d
0x18000866d  lea     rax, [rsp+290h+var_230]
0x180008672  mov     rdi, rcx
0x180008675  mov     [rsp+290h+hKey], r14
0x18000867a  mov     rcx, [rcx]; hKey
0x18000867d  mov     r9d, 2001Fh; samDesired
0x180008683  xor     r8d, r8d; ulOptions
0x180008686  mov     [rsp+290h+var_240], r14
0x18000868b  mov     [rsp+290h+var_238], r14
0x180008690  mov     rsi, rdx
0x180008693  mov     [rsp+290h+var_230], r14
0x180008698  mov     [rsp+290h+phkResult], rax; phkResult
0x18000869d  call    cs:__imp_RegOpenKeyExW
0x1800086a3  mov     rcx, [rsp+290h+hKey]; hKey
0x1800086a8  mov     ebx, eax
0x1800086aa  test    eax, eax
0x1800086ac  jnz     loc_18000874F
0x1800086b2  mov     ebx, r14d
0x1800086b5  test    rcx, rcx
0x1800086b8  jz      short loc_1800086C2
0x1800086ba  call    cs:__imp_RegCloseKey
0x1800086c0  mov     ebx, eax
0x1800086c2  mov     rcx, [rsp+290h+var_230]
0x1800086c7  mov     [rsp+290h+hKey], rcx
0x1800086cc  test    ebx, ebx
0x1800086ce  jnz     short loc_18000874F
0x1800086d0  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800086d5  jmp     short loc_1800086F1
0x1800086d7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800086dc  lea     rcx, [rsp+290h+hKey]; this
0x1800086e1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800086e6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800086eb  mov     ebx, eax
0x1800086ed  test    eax, eax
0x1800086ef  jnz     short loc_18000874F
0x1800086f1  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800086f6  mov     [rsp+290h+cchName], 100h
0x1800086fe  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180008703  lea     r9, [rsp+290h+cchName]; lpcchName
0x180008708  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000870d  lea     r8, [rsp+290h+Name]; lpName
0x180008712  mov     [rsp+290h+lpClass], r14; lpClass
0x180008717  xor     edx, edx; dwIndex
0x180008719  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000871e  call    cs:__imp_RegEnumKeyExW
0x180008724  test    eax, eax
0x180008726  jz      short loc_1800086D7
0x180008728  mov     rcx, [rsp+290h+hKey]; hKey
0x18000872d  test    rcx, rcx
0x180008730  jz      short loc_18000873D
0x180008732  call    cs:__imp_RegCloseKey
0x180008738  mov     [rsp+290h+hKey], r14
0x18000873d  mov     rdx, rsi; unsigned __int16 *
0x180008740  mov     rcx, rdi; this
0x180008743  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180008748  mov     rcx, [rsp+290h+hKey]; hKey
0x18000874d  mov     ebx, eax
0x18000874f  test    rcx, rcx
0x180008752  jz      short loc_18000875A
0x180008754  call    cs:__imp_RegCloseKey
0x18000875a  mov     eax, ebx
0x18000875c  mov     rcx, [rbp+190h+var_20]
0x180008763  xor     rcx, rsp; StackCookie
0x180008766  call    __security_check_cookie
0x18000876b  lea     r11, [rsp+290h+var_10]
0x180008773  mov     rbx, [r11+30h]
0x180008777  mov     rsi, [r11+38h]
0x18000877b  mov     rsp, r11
0x18000877e  pop     r14
0x180008780  pop     rdi
0x180008781  pop     rbp
0x180008782  retn
```
