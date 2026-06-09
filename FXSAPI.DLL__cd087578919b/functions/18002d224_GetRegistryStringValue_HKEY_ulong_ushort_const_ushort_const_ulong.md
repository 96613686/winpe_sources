# GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)

- ea: `0x18002d224`
- end: `0x18002d4c3`
- name: `?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z`
- size: `671`
- prototype: `BYTE *__fastcall(HKEY hKey, DWORD dwType, LPCWSTR lpValueName, const unsigned __int16 *, DWORD cbData)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002a650`
- `0x18002c064`
- `0x180032d88`
- `0x1800366d0`

## callees

- `0x1800278e8`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002d0e4`
- `0x18002d224`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002d3da`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002d40d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002d3da`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18002d40d`
- `KERNEL32!GetLastError` at `0x18002d43a`
- `KERNEL32!GetLastError` at `0x18002d43a`
- `ADVAPI32!RegSetValueExW` at `0x18002d394`
- `ADVAPI32!RegSetValueExW` at `0x18002d394`
- `ADVAPI32!RegQueryValueExW` at `0x18002d26b`
- `ADVAPI32!RegQueryValueExW` at `0x18002d31c`
- `ADVAPI32!RegQueryValueExW` at `0x18002d26b`
- `ADVAPI32!RegQueryValueExW` at `0x18002d31c`

## string_xrefs

- `0x18002d36f`: `StringCbCopy failed, hr: 0x%x`
- `0x18002d3bb`: `Can't create DefaultValue since it's NULL`
- `0x18002d3a7`: `RegSetValueEx() failed[%s], ec=%d`
- `0x18002d49b`: `StringCbCopy failed, hr = 0x%x`

## pseudocode

```c
BYTE *__fastcall GetRegistryStringValue(
        HKEY hKey,
        DWORD dwType,
        LPCWSTR lpValueName,
        const unsigned __int16 *a4,
        DWORD cbData)
{
  unsigned int v8; // eax
  __int64 v9; // r15
  BYTE *lpData; // rbx
  __int64 v11; // rcx
  DWORD v12; // ecx
  DWORD v13; // esi
  SIZE_T v14; // r13
  int v15; // eax
  unsigned int v16; // eax
  DWORD v17; // eax
  signed int v18; // r14d
  WCHAR *v19; // rax
  WCHAR *v20; // rsi
  signed int v21; // eax
  DWORD LastError; // eax
  unsigned __int16 *v24; // rax
  int v25; // eax
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  DWORD v27; // [rsp+34h] [rbp-14h]

  cbData = 0;
  Type = 0;
  v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  v9 = -1;
  if ( v8 )
  {
    lpData = 0;
    if ( v8 != 2 )
      goto LABEL_8;
    if ( !a4 )
    {
      fax_dprintf(L"RegQueryValueEx() failed, ec=%d - and no default value was specified", 2);
      goto LABEL_32;
    }
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v12 = 2 * v11 + 2;
    cbData = v12;
LABEL_11:
    if ( !v12 )
    {
      v12 = 32;
      cbData = 32;
    }
    v27 = v12 + (v12 & 1);
    v13 = v27 + 2;
    v14 = v27 + 2;
    lpData = (BYTE *)pMemAlloc(v14);
    if ( !lpData )
      goto LABEL_32;
    v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    lpData[v13 - 1] = 0;
    lpData[v27] = 0;
    if ( (cbData & 1) != 0 )
      lpData[v13 - 3] = 0;
    if ( !v8 )
    {
LABEL_24:
      if ( dwType != 2 )
        return lpData;
      v17 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
      v18 = v17;
      if ( v17 )
      {
        cbData = 2 * v17 + 2;
        v19 = (WCHAR *)pMemAlloc(cbData);
        v20 = v19;
        if ( v19 )
        {
          v21 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v19, v18);
          if ( v21 && v21 <= v18 )
          {
            pMemFree(lpData);
            return (BYTE *)v20;
          }
          pMemFree(v20);
          LastError = GetLastError();
          fax_dprintf(L"ExpandEnvironmentStrings() failed, ec=%d", LastError);
        }
      }
LABEL_32:
      pMemFree(lpData);
      if ( !a4 )
        return 0;
      do
        ++v9;
      while ( a4[v9] );
      cbData = 2 * v9 + 2;
      v24 = (unsigned __int16 *)pMemAlloc(cbData);
      lpData = (BYTE *)v24;
      if ( !v24 )
        return 0;
      v25 = StringCbCopyW(v24, cbData, a4);
      if ( v25 < 0 )
      {
        fax_dprintf(L"StringCbCopy failed, hr = 0x%x", (unsigned int)v25);
        pMemFree(lpData);
        return 0;
      }
      return lpData;
    }
    if ( v8 == 2 )
    {
      if ( !a4 )
      {
        fax_dprintf(L"Can't create DefaultValue since it's NULL");
        goto LABEL_32;
      }
      v15 = StringCbCopyW((unsigned __int16 *)lpData, v14, a4);
      if ( v15 < 0 )
      {
        fax_dprintf(L"StringCbCopy failed, hr: 0x%x", (unsigned int)v15);
        goto LABEL_32;
      }
      v16 = RegSetValueExW(hKey, lpValueName, 0, dwType, lpData, cbData);
      if ( v16 )
      {
        fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", lpValueName, v16);
        goto LABEL_32;
      }
      goto LABEL_24;
    }
LABEL_8:
    fax_dprintf(L"RegQueryValueEx() failed, ec=%d", v8);
    goto LABEL_32;
  }
  if ( Type == dwType )
  {
    v12 = cbData;
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x18002d224  mov     [rsp-40h+hKey], rcx
0x18002d229  push    rbp
0x18002d22a  push    rbx
0x18002d22b  push    rsi
0x18002d22c  push    rdi
0x18002d22d  push    r12
0x18002d22f  push    r13
0x18002d231  push    r14
0x18002d233  push    r15
0x18002d235  mov     rbp, rsp
0x18002d238  sub     rsp, 48h
0x18002d23c  mov     rax, rcx
0x18002d23f  mov     r12, r8
0x18002d242  xor     esi, esi
0x18002d244  lea     rcx, [rbp+cbData]
0x18002d248  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x18002d24d  mov     rdi, r9
0x18002d250  mov     r14d, edx
0x18002d253  mov     [rbp+cbData], esi
0x18002d256  mov     rcx, rax; hKey
0x18002d259  mov     [rbp+Type], esi
0x18002d25c  lea     r9, [rbp+Type]; lpType
0x18002d260  mov     [rsp+48h+lpData], rsi; lpData
0x18002d265  xor     r8d, r8d; lpReserved
0x18002d268  mov     rdx, r12; lpValueName
0x18002d26b  call    cs:__imp_RegQueryValueExW
0x18002d272  nop     dword ptr [rax+rax+00h]
0x18002d277  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002d27b  test    eax, eax
0x18002d27d  jz      short loc_18002D2C4
0x18002d27f  mov     ebx, esi
0x18002d281  cmp     eax, 2
0x18002d284  jnz     short loc_18002D2B9
0x18002d286  test    rdi, rdi
0x18002d289  jz      short loc_18002D2A3
0x18002d28b  mov     rcx, r15
0x18002d28e  inc     rcx
0x18002d291  cmp     [rdi+rcx*2], si
0x18002d295  jnz     short loc_18002D28E
0x18002d297  lea     ecx, ds:2[rcx*2]
0x18002d29e  mov     [rbp+cbData], ecx
0x18002d2a1  jmp     short loc_18002D2D1
0x18002d2a3  mov     edx, 2
0x18002d2a8  lea     rcx, aRegqueryvaluee; "RegQueryValueEx() failed, ec=%d - and n"...
0x18002d2af  call    fax_dprintf
0x18002d2b4  jmp     loc_18002D456
0x18002d2b9  mov     edx, eax
0x18002d2bb  lea     rcx, aRegqueryvaluee_1; "RegQueryValueEx() failed, ec=%d"
0x18002d2c2  jmp     short loc_18002D2AF
0x18002d2c4  cmp     [rbp+Type], r14d
0x18002d2c8  jnz     loc_18002D4AF
0x18002d2ce  mov     ecx, [rbp+cbData]
0x18002d2d1  test    ecx, ecx
0x18002d2d3  jnz     short loc_18002D2DD
0x18002d2d5  mov     ecx, 20h ; ' '
0x18002d2da  mov     [rbp+cbData], ecx
0x18002d2dd  mov     eax, ecx
0x18002d2df  and     eax, 1
0x18002d2e2  add     eax, ecx
0x18002d2e4  mov     [rbp+var_14], eax
0x18002d2e7  lea     esi, [rax+2]
0x18002d2ea  mov     ecx, esi; dwBytes
0x18002d2ec  mov     r13d, esi
0x18002d2ef  call    pMemAlloc
0x18002d2f4  mov     rbx, rax
0x18002d2f7  test    rax, rax
0x18002d2fa  jz      loc_18002D454
0x18002d300  mov     rcx, [rbp+hKey]; hKey
0x18002d304  lea     rax, [rbp+cbData]
0x18002d308  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18002d30d  lea     r9, [rbp+Type]; lpType
0x18002d311  xor     r8d, r8d; lpReserved
0x18002d314  mov     [rsp+48h+lpData], rbx; lpData
0x18002d319  mov     rdx, r12; lpValueName
0x18002d31c  call    cs:__imp_RegQueryValueExW
0x18002d323  nop     dword ptr [rax+rax+00h]
0x18002d328  lea     ecx, [rsi-1]
0x18002d32b  mov     byte ptr [rcx+rbx], 0
0x18002d32f  mov     ecx, [rbp+var_14]
0x18002d332  mov     byte ptr [rcx+rbx], 0
0x18002d336  test    byte ptr [rbp+cbData], 1
0x18002d33a  jz      short loc_18002D347
0x18002d33c  lea     ecx, [rsi-3]
0x18002d33f  xor     esi, esi
0x18002d341  mov     [rcx+rbx], sil
0x18002d345  jmp     short loc_18002D349
0x18002d347  xor     esi, esi
0x18002d349  test    eax, eax
0x18002d34b  jz      short loc_18002D3CC
0x18002d34d  cmp     eax, 2
0x18002d350  jnz     loc_18002D2B9
0x18002d356  test    rdi, rdi
0x18002d359  jz      short loc_18002D3BB
0x18002d35b  mov     r8, rdi; unsigned __int16 *
0x18002d35e  mov     rdx, r13; unsigned __int64
0x18002d361  mov     rcx, rbx; unsigned __int16 *
0x18002d364  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d369  test    eax, eax
0x18002d36b  jns     short loc_18002D37B
0x18002d36d  mov     edx, eax
0x18002d36f  lea     rcx, aStringcbcopyFa_0; "StringCbCopy failed, hr: 0x%x"
0x18002d376  jmp     loc_18002D2AF
0x18002d37b  mov     eax, [rbp+cbData]
0x18002d37e  mov     r9d, r14d; dwType
0x18002d381  mov     rcx, [rbp+hKey]; hKey
0x18002d385  xor     r8d, r8d; Reserved
0x18002d388  mov     dword ptr [rsp+48h+lpcbData], eax; cbData
0x18002d38c  mov     rdx, r12; lpValueName
0x18002d38f  mov     [rsp+48h+lpData], rbx; lpData
0x18002d394  call    cs:__imp_RegSetValueExW
0x18002d39b  nop     dword ptr [rax+rax+00h]
0x18002d3a0  test    eax, eax
0x18002d3a2  jz      short loc_18002D3CC
0x18002d3a4  mov     r8d, eax
0x18002d3a7  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18002d3ae  mov     rdx, r12
0x18002d3b1  call    fax_dprintf
0x18002d3b6  jmp     loc_18002D456
0x18002d3bb  lea     rcx, aCanTCreateDefa; "Can't create DefaultValue since it's NU"...
0x18002d3c2  call    fax_dprintf
0x18002d3c7  jmp     loc_18002D456
0x18002d3cc  cmp     r14d, 2
0x18002d3d0  jnz     short loc_18002D42D
0x18002d3d2  xor     r8d, r8d; nSize
0x18002d3d5  xor     edx, edx; lpDst
0x18002d3d7  mov     rcx, rbx; lpSrc
0x18002d3da  call    cs:__imp_ExpandEnvironmentStringsW
0x18002d3e1  nop     dword ptr [rax+rax+00h]
0x18002d3e6  mov     r14d, eax
0x18002d3e9  test    eax, eax
0x18002d3eb  jz      short loc_18002D456
0x18002d3ed  lea     ecx, ds:2[rax*2]; dwBytes
0x18002d3f4  mov     [rbp+cbData], ecx
0x18002d3f7  call    pMemAlloc
0x18002d3fc  mov     rsi, rax
0x18002d3ff  test    rax, rax
0x18002d402  jz      short loc_18002D454
0x18002d404  mov     r8d, r14d; nSize
0x18002d407  mov     rdx, rax; lpDst
0x18002d40a  mov     rcx, rbx; lpSrc
0x18002d40d  call    cs:__imp_ExpandEnvironmentStringsW
0x18002d414  nop     dword ptr [rax+rax+00h]
0x18002d419  test    eax, eax
0x18002d41b  jz      short loc_18002D432
0x18002d41d  cmp     eax, r14d
0x18002d420  jg      short loc_18002D432
0x18002d422  mov     rcx, rbx; lpMem
0x18002d425  call    pMemFree
0x18002d42a  mov     rbx, rsi
0x18002d42d  mov     rax, rbx
0x18002d430  jmp     short loc_18002D4B1
0x18002d432  mov     rcx, rsi; lpMem
0x18002d435  call    pMemFree
0x18002d43a  call    cs:__imp_GetLastError
0x18002d441  nop     dword ptr [rax+rax+00h]
0x18002d446  mov     edx, eax
0x18002d448  lea     rcx, aExpandenvironm; "ExpandEnvironmentStrings() failed, ec=%"...
0x18002d44f  call    fax_dprintf
0x18002d454  xor     esi, esi
0x18002d456  mov     rcx, rbx; lpMem
0x18002d459  call    pMemFree
0x18002d45e  test    rdi, rdi
0x18002d461  jz      short loc_18002D4AF
0x18002d463  inc     r15
0x18002d466  cmp     [rdi+r15*2], si
0x18002d46b  jnz     short loc_18002D463
0x18002d46d  lea     eax, ds:2[r15*2]
0x18002d475  mov     ecx, eax; dwBytes
0x18002d477  mov     [rbp+cbData], eax
0x18002d47a  call    pMemAlloc
0x18002d47f  mov     rbx, rax
0x18002d482  test    rax, rax
0x18002d485  jz      short loc_18002D4AF
0x18002d487  mov     edx, [rbp+cbData]; unsigned __int64
0x18002d48a  mov     r8, rdi; unsigned __int16 *
0x18002d48d  mov     rcx, rax; unsigned __int16 *
0x18002d490  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d495  test    eax, eax
0x18002d497  jns     short loc_18002D42D
0x18002d499  mov     edx, eax
0x18002d49b  lea     rcx, aStringcbcopyFa; "StringCbCopy failed, hr = 0x%x"
0x18002d4a2  call    fax_dprintf
0x18002d4a7  mov     rcx, rbx; lpMem
0x18002d4aa  call    pMemFree
0x18002d4af  xor     eax, eax
0x18002d4b1  add     rsp, 48h
0x18002d4b5  pop     r15
0x18002d4b7  pop     r14
0x18002d4b9  pop     r13
0x18002d4bb  pop     r12
0x18002d4bd  pop     rdi
0x18002d4be  pop     rsi
0x18002d4bf  pop     rbx
0x18002d4c0  pop     rbp
0x18002d4c1  retn
```
