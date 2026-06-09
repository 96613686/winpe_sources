# CfEnumAppPolicy

- ea: `0x180003810`
- end: `0x180003a54`
- name: `CfEnumAppPolicy`
- size: `580`
- prototype: `__int64 __fastcall(HKEY hKey, DWORD, WCHAR *, BYTE *, LPBYTE lpData, LPBYTE, LPBYTE)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000387b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000387b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003942`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003999`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003942`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003999`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800038a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a37`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003a37`

## string_xrefs

- `0x180003929`: `ImagePath`

## pseudocode

```c
__int64 __fastcall CfEnumAppPolicy(HKEY hKey, DWORD a2, WCHAR *a3, BYTE *a4, LPBYTE lpData, LPBYTE a6, LPBYTE a7)
{
  signed int v10; // ebx
  LSTATUS v11; // eax
  LSTATUS v12; // edi
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LPBYTE v15; // r14
  LSTATUS v16; // eax
  LPBYTE v17; // r14
  LSTATUS v18; // eax
  LPBYTE v19; // r14
  LSTATUS v20; // eax
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD cchName; // [rsp+88h] [rbp+38h] BYREF

  phkResult = 0;
  cchName = 65;
  *(_DWORD *)a4 = 0;
  if ( !hKey )
    return (unsigned int)-2147024637;
  v11 = RegEnumKeyExW(hKey, a2, a3, &cchName, 0, 0, 0, 0);
  v12 = v11;
  if ( !v11 )
  {
    cbData = 0;
    v13 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_36;
    cbData = 4;
    v14 = RegQueryValueExW(phkResult, L"Enabled", 0, 0, a4, &cbData);
    v10 = v14;
    if ( v14 == 2 )
    {
      *(_DWORD *)a4 = 0;
      v10 = 0;
    }
    else if ( v14 > 0 )
    {
      v10 = (unsigned __int16)v14 | 0x80070000;
    }
    if ( v10 < 0 )
      goto LABEL_36;
    v15 = lpData;
    if ( lpData )
    {
      cbData = 0x8000;
      v16 = RegQueryValueExW(phkResult, L"ImagePath", 0, 0, lpData, &cbData);
      v10 = v16;
      if ( v16 == 2 )
      {
        *(_WORD *)v15 = 0;
        v10 = 0;
      }
      else if ( v16 > 0 )
      {
        v10 = (unsigned __int16)v16 | 0x80070000;
      }
      if ( v10 < 0 )
        goto LABEL_36;
    }
    v17 = a6;
    if ( a6 )
    {
      cbData = 0x8000;
      v18 = RegQueryValueExW(phkResult, L"PackageName", 0, 0, a6, &cbData);
      v10 = v18;
      if ( v18 == 2 )
      {
        *(_WORD *)v17 = 0;
        v10 = 0;
      }
      else if ( v18 > 0 )
      {
        v10 = (unsigned __int16)v18 | 0x80070000;
      }
      if ( v10 < 0 )
        goto LABEL_36;
    }
    v19 = a7;
    if ( a7 )
    {
      cbData = 0x8000;
      v20 = RegQueryValueExW(phkResult, L"AppName", 0, 0, a7, &cbData);
      v10 = v20;
      if ( v20 == 2 )
      {
        *(_WORD *)v19 = 0;
        v10 = 0;
      }
      else if ( v20 > 0 )
      {
        v10 = (unsigned __int16)v20 | 0x80070000;
      }
      if ( v10 < 0 )
        goto LABEL_36;
    }
    goto LABEL_34;
  }
  if ( v11 == 234 )
  {
    v12 = 0;
LABEL_34:
    v10 = v12;
    goto LABEL_36;
  }
  if ( v11 <= 0 )
    goto LABEL_34;
  v10 = (unsigned __int16)v11 | 0x80070000;
LABEL_36:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003810  mov     [rsp-18h+arg_8], rbx
0x180003815  mov     [rsp-18h+arg_10], rsi
0x18000381a  push    rbp
0x18000381b  push    rdi
0x18000381c  push    r14
0x18000381e  mov     rbp, rsp
0x180003821  sub     rsp, 50h
0x180003825  mov     [rbp+phkResult], 0
0x18000382d  mov     r14, r9
0x180003830  mov     [rbp+cchName], 41h ; 'A'
0x180003837  mov     rsi, r8
0x18000383a  mov     dword ptr [r9], 0
0x180003841  mov     rbx, rcx
0x180003844  test    rcx, rcx
0x180003847  jnz     short loc_180003853
0x180003849  mov     ebx, 80070103h
0x18000384e  jmp     loc_180003A3D
0x180003853  mov     [rsp+50h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000385c  lea     r9, [rbp+cchName]; lpcchName
0x180003860  mov     [rsp+50h+lpcchClass], 0; lpcchClass
0x180003869  mov     [rsp+50h+lpClass], 0; lpClass
0x180003872  mov     [rsp+50h+lpReserved], 0; lpReserved
0x18000387b  call    cs:__imp_RegEnumKeyExW
0x180003881  mov     edi, eax
0x180003883  test    eax, eax
0x180003885  jnz     loc_180003A12
0x18000388b  mov     [rbp+cbData], eax
0x18000388e  mov     r9d, 20019h; samDesired
0x180003894  lea     rax, [rbp+phkResult]
0x180003898  xor     r8d, r8d; ulOptions
0x18000389b  mov     rdx, rsi; lpSubKey
0x18000389e  mov     [rsp+50h+lpReserved], rax; phkResult
0x1800038a3  mov     rcx, rbx; hKey
0x1800038a6  call    cs:__imp_RegOpenKeyExW
0x1800038ac  mov     ebx, eax
0x1800038ae  mov     esi, 80070000h
0x1800038b3  test    eax, eax
0x1800038b5  jle     short loc_1800038BC
0x1800038b7  movzx   ebx, ax
0x1800038ba  or      ebx, esi
0x1800038bc  test    ebx, ebx
0x1800038be  js      loc_180003A2E
0x1800038c4  mov     rcx, [rbp+phkResult]; hKey
0x1800038c8  lea     rax, [rbp+cbData]
0x1800038cc  mov     [rsp+50h+lpClass], rax; lpcbData
0x1800038d1  lea     rdx, ValueName; "Enabled"
0x1800038d8  xor     r9d, r9d; lpType
0x1800038db  mov     [rsp+50h+lpReserved], r14; lpData
0x1800038e0  xor     r8d, r8d; lpReserved
0x1800038e3  mov     [rbp+cbData], 4
0x1800038ea  call    cs:__imp_RegQueryValueExW
0x1800038f0  mov     ebx, eax
0x1800038f2  cmp     eax, 2
0x1800038f5  jnz     short loc_180003902
0x1800038f7  mov     dword ptr [r14], 0
0x1800038fe  xor     ebx, ebx
0x180003900  jmp     short loc_18000390B
0x180003902  test    eax, eax
0x180003904  jle     short loc_18000390B
0x180003906  movzx   ebx, ax
0x180003909  or      ebx, esi
0x18000390b  test    ebx, ebx
0x18000390d  js      loc_180003A2E
0x180003913  mov     r14, [rbp+lpData]
0x180003917  test    r14, r14
0x18000391a  jz      short loc_18000396A
0x18000391c  mov     rcx, [rbp+phkResult]; hKey
0x180003920  lea     rax, [rbp+cbData]
0x180003924  mov     [rsp+50h+lpClass], rax; lpcbData
0x180003929  lea     rdx, aImagepath; "ImagePath"
0x180003930  xor     r9d, r9d; lpType
0x180003933  mov     [rsp+50h+lpReserved], r14; lpData
0x180003938  xor     r8d, r8d; lpReserved
0x18000393b  mov     [rbp+cbData], 8000h
0x180003942  call    cs:__imp_RegQueryValueExW
0x180003948  mov     ebx, eax
0x18000394a  cmp     eax, 2
0x18000394d  jnz     short loc_180003959
0x18000394f  xor     eax, eax
0x180003951  mov     [r14], ax
0x180003955  xor     ebx, ebx
0x180003957  jmp     short loc_180003962
0x180003959  test    eax, eax
0x18000395b  jle     short loc_180003962
0x18000395d  movzx   ebx, ax
0x180003960  or      ebx, esi
0x180003962  test    ebx, ebx
0x180003964  js      loc_180003A2E
0x18000396a  mov     r14, [rbp+arg_28]
0x18000396e  test    r14, r14
0x180003971  jz      short loc_1800039BD
0x180003973  mov     rcx, [rbp+phkResult]; hKey
0x180003977  lea     rax, [rbp+cbData]
0x18000397b  mov     [rsp+50h+lpClass], rax; lpcbData
0x180003980  lea     rdx, aPackagename; "PackageName"
0x180003987  xor     r9d, r9d; lpType
0x18000398a  mov     [rsp+50h+lpReserved], r14; lpData
0x18000398f  xor     r8d, r8d; lpReserved
0x180003992  mov     [rbp+cbData], 8000h
0x180003999  call    cs:__imp_RegQueryValueExW
0x18000399f  mov     ebx, eax
0x1800039a1  cmp     eax, 2
0x1800039a4  jnz     short loc_1800039B0
0x1800039a6  xor     eax, eax
0x1800039a8  mov     [r14], ax
0x1800039ac  xor     ebx, ebx
0x1800039ae  jmp     short loc_1800039B9
0x1800039b0  test    eax, eax
0x1800039b2  jle     short loc_1800039B9
0x1800039b4  movzx   ebx, ax
0x1800039b7  or      ebx, esi
0x1800039b9  test    ebx, ebx
0x1800039bb  js      short loc_180003A2E
0x1800039bd  mov     r14, [rbp+arg_30]
0x1800039c1  test    r14, r14
0x1800039c4  jz      short loc_180003A21
0x1800039c6  mov     rcx, [rbp+phkResult]; hKey
0x1800039ca  lea     rax, [rbp+cbData]
0x1800039ce  mov     [rsp+50h+lpClass], rax; lpcbData
0x1800039d3  lea     rdx, aAppname; "AppName"
0x1800039da  xor     r9d, r9d; lpType
0x1800039dd  mov     [rsp+50h+lpReserved], r14; lpData
0x1800039e2  xor     r8d, r8d; lpReserved
0x1800039e5  mov     [rbp+cbData], 8000h
0x1800039ec  call    cs:__imp_RegQueryValueExW
0x1800039f2  mov     ebx, eax
0x1800039f4  cmp     eax, 2
0x1800039f7  jnz     short loc_180003A03
0x1800039f9  xor     eax, eax
0x1800039fb  mov     [r14], ax
0x1800039ff  xor     ebx, ebx
0x180003a01  jmp     short loc_180003A0C
0x180003a03  test    eax, eax
0x180003a05  jle     short loc_180003A0C
0x180003a07  movzx   ebx, ax
0x180003a0a  or      ebx, esi
0x180003a0c  test    ebx, ebx
0x180003a0e  jns     short loc_180003A21
0x180003a10  jmp     short loc_180003A2E
0x180003a12  cmp     eax, 0EAh
0x180003a17  jnz     short loc_180003A1D
0x180003a19  xor     edi, edi
0x180003a1b  jmp     short loc_180003A21
0x180003a1d  test    eax, eax
0x180003a1f  jg      short loc_180003A25
0x180003a21  mov     ebx, edi
0x180003a23  jmp     short loc_180003A2E
0x180003a25  movzx   ebx, ax
0x180003a28  or      ebx, 80070000h
0x180003a2e  mov     rcx, [rbp+phkResult]; hKey
0x180003a32  test    rcx, rcx
0x180003a35  jz      short loc_180003A3D
0x180003a37  call    cs:__imp_RegCloseKey
0x180003a3d  lea     r11, [rsp+50h+var_s0]
0x180003a42  mov     eax, ebx
0x180003a44  mov     rbx, [r11+28h]
0x180003a48  mov     rsi, [r11+30h]
0x180003a4c  mov     rsp, r11
0x180003a4f  pop     r14
0x180003a51  pop     rdi
0x180003a52  pop     rbp
0x180003a53  retn
```
