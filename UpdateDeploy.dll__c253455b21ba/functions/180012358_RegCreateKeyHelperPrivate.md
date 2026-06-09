# RegCreateKeyHelperPrivate

- ea: `0x180012358`
- end: `0x1800124c2`
- name: `RegCreateKeyHelperPrivate`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800124c8`
- `0x1800330b8`

## callees

- `0x180011cb8`
- `0x180012358`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012490`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001249f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012490`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001249f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800123ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012453`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800123ea`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180012453`

## pseudocode

```c
__int64 __fastcall RegCreateKeyHelperPrivate(__int64 a1, const WCHAR *a2, const WCHAR *a3, HKEY *a4)
{
  int v5; // r14d
  signed int v8; // ebx
  REGSAM v9; // r15d
  LSTATUS v10; // eax
  HKEY v11; // rcx
  REGSAM samDesired; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF

  phkResult = 0;
  v5 = 0;
  hKey = 0;
  *a4 = 0;
  samDesired = 131078;
  v8 = SetRegistryType(a1, &samDesired);
  if ( v8 >= 0 )
  {
    v9 = samDesired;
    if ( a2 )
    {
      v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, samDesired, 0, &phkResult, 0);
      if ( v10 )
      {
LABEL_4:
        v8 = (unsigned __int16)v10 | 0x80070000;
        if ( v10 <= 0 )
          v8 = v10;
        goto LABEL_15;
      }
      v11 = phkResult;
      v5 = 1;
    }
    else
    {
      v11 = HKEY_LOCAL_MACHINE;
    }
    if ( a3 )
    {
      v10 = RegCreateKeyExW(v11, a3, 0, 0, 1u, v9, 0, &hKey, 0);
      if ( !v10 )
      {
        *a4 = hKey;
        hKey = 0;
        goto LABEL_17;
      }
      goto LABEL_4;
    }
    if ( v5 )
    {
      *a4 = phkResult;
      phkResult = 0;
    }
    else
    {
      *a4 = HKEY_LOCAL_MACHINE;
    }
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
LABEL_17:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012358  push    rbp
0x18001235a  push    rbx
0x18001235b  push    rsi
0x18001235c  push    rdi
0x18001235d  push    r12
0x18001235f  push    r14
0x180012361  push    r15
0x180012363  mov     rbp, rsp
0x180012366  sub     rsp, 70h
0x18001236a  mov     rax, cs:__security_cookie
0x180012371  xor     rax, rsp
0x180012374  mov     [rbp+var_8], rax
0x180012378  mov     rsi, rdx
0x18001237b  mov     [rbp+var_18], 0
0x180012383  xor     r14d, r14d
0x180012386  mov     [rbp+hKey], 0
0x18001238e  lea     rdx, [rbp+var_20]
0x180012392  mov     [r9], r14
0x180012395  mov     rdi, r9
0x180012398  mov     [rbp+var_20], 20006h
0x18001239f  mov     r12, r8
0x1800123a2  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x1800123a7  mov     ebx, eax
0x1800123a9  test    eax, eax
0x1800123ab  js      loc_180012487
0x1800123b1  mov     r15d, [rbp+var_20]
0x1800123b5  test    rsi, rsi
0x1800123b8  jz      short loc_180012413
0x1800123ba  mov     [rsp+70h+lpdwDisposition], r14; lpdwDisposition
0x1800123bf  lea     rax, [rbp+var_18]
0x1800123c3  mov     [rsp+70h+phkResult], rax; phkResult
0x1800123c8  mov     rdx, rsi; lpSubKey
0x1800123cb  mov     [rsp+70h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800123d0  mov     rsi, 0FFFFFFFF80000002h
0x1800123d7  mov     [rsp+70h+samDesired], r15d; samDesired
0x1800123dc  xor     r9d, r9d; lpClass
0x1800123df  xor     r8d, r8d; Reserved
0x1800123e2  mov     [rsp+70h+dwOptions], r14d; dwOptions
0x1800123e7  mov     rcx, rsi; hKey
0x1800123ea  call    cs:__imp_RegCreateKeyExW
0x1800123f0  test    eax, eax
0x1800123f2  jz      short loc_180012407
0x1800123f4  movzx   ebx, ax
0x1800123f7  or      ebx, 80070000h
0x1800123fd  test    eax, eax
0x1800123ff  cmovle  ebx, eax
0x180012402  jmp     loc_180012487
0x180012407  mov     rcx, [rbp+var_18]
0x18001240b  mov     r14d, 1
0x180012411  jmp     short loc_18001241D
0x180012413  mov     rsi, 0FFFFFFFF80000002h
0x18001241a  mov     rcx, rsi; hKey
0x18001241d  test    r12, r12
0x180012420  jz      short loc_18001246E
0x180012422  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18001242b  lea     rax, [rbp+hKey]
0x18001242f  mov     [rsp+70h+phkResult], rax; phkResult
0x180012434  xor     r9d, r9d; lpClass
0x180012437  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180012440  xor     r8d, r8d; Reserved
0x180012443  mov     [rsp+70h+samDesired], r15d; samDesired
0x180012448  mov     rdx, r12; lpSubKey
0x18001244b  mov     [rsp+70h+dwOptions], 1; dwOptions
0x180012453  call    cs:__imp_RegCreateKeyExW
0x180012459  test    eax, eax
0x18001245b  jnz     short loc_1800123F4
0x18001245d  mov     rax, [rbp+hKey]
0x180012461  mov     [rdi], rax
0x180012464  mov     [rbp+hKey], 0
0x18001246c  jmp     short loc_180012496
0x18001246e  test    r14d, r14d
0x180012471  jz      short loc_180012484
0x180012473  mov     rax, [rbp+var_18]
0x180012477  mov     [rdi], rax
0x18001247a  mov     [rbp+var_18], 0
0x180012482  jmp     short loc_180012487
0x180012484  mov     [rdi], rsi
0x180012487  mov     rcx, [rbp+hKey]; hKey
0x18001248b  test    rcx, rcx
0x18001248e  jz      short loc_180012496
0x180012490  call    cs:__imp_RegCloseKey
0x180012496  mov     rcx, [rbp+var_18]; hKey
0x18001249a  test    rcx, rcx
0x18001249d  jz      short loc_1800124A5
0x18001249f  call    cs:__imp_RegCloseKey
0x1800124a5  mov     eax, ebx
0x1800124a7  mov     rcx, [rbp+var_8]
0x1800124ab  xor     rcx, rsp; StackCookie
0x1800124ae  call    __security_check_cookie
0x1800124b3  add     rsp, 70h
0x1800124b7  pop     r15
0x1800124b9  pop     r14
0x1800124bb  pop     r12
0x1800124bd  pop     rdi
0x1800124be  pop     rsi
0x1800124bf  pop     rbx
0x1800124c0  pop     rbp
0x1800124c1  retn
```
