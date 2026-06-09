# GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)

- ea: `0x18000f20c`
- end: `0x18000f44e`
- name: `?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z`
- size: `578`
- prototype: `unsigned __int16 *__usercall@<rax>(HKEY hKey@<rcx>, DWORD dwType@<edx>, LPCWSTR lpValueName@<r8>, const unsigned __int16 *@<r9>, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180017aa0`
- `0x180017cb0`
- `0x180017f10`
- `0x180018000`
- `0x180018130`

## callees

- `0x18000f128`
- `0x18000f1c8`
- `0x18000f20c`
- `0x18000f4d4`
- `0x1800174d8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f436`
- `KERNEL32!GetLastError` at `0x18000f436`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000f3cd`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000f407`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000f3cd`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000f407`
- `ADVAPI32!RegQueryValueExW` at `0x18000f256`
- `ADVAPI32!RegQueryValueExW` at `0x18000f331`
- `ADVAPI32!RegQueryValueExW` at `0x18000f256`
- `ADVAPI32!RegQueryValueExW` at `0x18000f331`
- `ADVAPI32!RegSetValueExW` at `0x18000f399`
- `ADVAPI32!RegSetValueExW` at `0x18000f399`

## string_xrefs

- `0x18000f375`: `StringCbCopy failed, hr: 0x%x`
- `0x18000f2b5`: `StringCbCopy failed, hr = 0x%x`
- `0x18000f3ac`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
BYTE *__fastcall GetRegistryStringValue(
        HKEY hKey,
        DWORD dwType,
        LPCWSTR lpValueName,
        const unsigned __int16 *a4,
        unsigned int *Type)
{
  unsigned int v8; // eax
  DWORD v9; // ecx
  BYTE *lpData; // rbx
  unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // r8
  int v13; // eax
  __int64 v15; // r13
  const unsigned __int16 *v16; // r8
  int v17; // eax
  unsigned int v18; // eax
  DWORD v19; // eax
  signed int v20; // esi
  WCHAR *v21; // rax
  WCHAR *v22; // rdi
  signed int v23; // eax
  DWORD LastError; // eax
  DWORD cbData; // [rsp+98h] [rbp+60h] BYREF
  int v26; // [rsp+9Ch] [rbp+64h]

  v26 = HIDWORD(a4);
  cbData = 0;
  LODWORD(Type) = 0;
  v8 = RegQueryValueExW(hKey, lpValueName, 0, (LPDWORD)&Type, 0, &cbData);
  if ( v8 )
  {
    if ( v8 != 2 )
    {
      lpData = 0;
      goto LABEL_5;
    }
    v9 = 2;
    goto LABEL_13;
  }
  if ( (_DWORD)Type != dwType )
    return 0;
  v9 = cbData;
  if ( !cbData )
  {
    v9 = 32;
LABEL_13:
    cbData = v9;
  }
  v15 = v9 + (v9 & 1);
  lpData = (BYTE *)pMemAlloc((unsigned int)(v15 + 2));
  if ( !lpData )
    goto LABEL_6;
  v8 = RegQueryValueExW(hKey, lpValueName, 0, (LPDWORD)&Type, lpData, &cbData);
  lpData[v15] = 0;
  lpData[(unsigned int)(v15 + 1)] = 0;
  if ( (cbData & 1) != 0 )
    lpData[(unsigned int)(v15 - 1)] = 0;
  if ( !v8 )
    goto LABEL_23;
  if ( v8 != 2 )
  {
LABEL_5:
    fax_dprintf(L"RegQueryValueEx() failed, ec=%d", v8);
    goto LABEL_6;
  }
  v17 = StringCbCopyW((unsigned __int16 *)lpData, (unsigned int)(v15 + 2), v16);
  if ( v17 < 0 )
  {
    fax_dprintf(L"StringCbCopy failed, hr: 0x%x", (unsigned int)v17);
    goto LABEL_6;
  }
  v18 = RegSetValueExW(hKey, lpValueName, 0, dwType, lpData, cbData);
  if ( v18 )
  {
    fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", lpValueName, v18);
    goto LABEL_6;
  }
LABEL_23:
  if ( dwType != 2 )
    return lpData;
  v19 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
  v20 = v19;
  if ( v19 )
  {
    cbData = 2 * v19 + 2;
    v21 = (WCHAR *)pMemAlloc(cbData);
    v22 = v21;
    if ( v21 )
    {
      v23 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v21, v20);
      if ( v23 && v23 <= v20 )
      {
        pMemFree(lpData);
        return (BYTE *)v22;
      }
      pMemFree(v22);
      LastError = GetLastError();
      fax_dprintf(L"ExpandEnvironmentStrings() failed, ec=%d", LastError);
    }
  }
LABEL_6:
  pMemFree(lpData);
  cbData = 2;
  v11 = (unsigned __int16 *)pMemAlloc(2u);
  lpData = (BYTE *)v11;
  if ( !v11 )
    return 0;
  v13 = StringCbCopyW(v11, cbData, v12);
  if ( v13 < 0 )
  {
    fax_dprintf(L"StringCbCopy failed, hr = 0x%x", (unsigned int)v13);
    pMemFree(lpData);
    return 0;
  }
  return lpData;
}

```

## disassembly

```asm
0x18000f20c  mov     qword ptr [rsp-40h+cbData], r9
0x18000f211  push    rbp
0x18000f212  push    rbx
0x18000f213  push    rsi
0x18000f214  push    rdi
0x18000f215  push    r12
0x18000f217  push    r13
0x18000f219  push    r14
0x18000f21b  push    r15
0x18000f21d  mov     rbp, rsp
0x18000f220  sub     rsp, 38h
0x18000f224  mov     rsi, r8
0x18000f227  mov     [rbp+cbData], 0
0x18000f22e  lea     rax, [rbp+cbData]
0x18000f232  mov     [rbp+Type], 0
0x18000f239  mov     edi, edx
0x18000f23b  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000f240  mov     rdx, rsi; lpValueName
0x18000f243  mov     [rsp+38h+lpData], 0; lpData
0x18000f24c  lea     r9, [rbp+Type]; lpType
0x18000f250  xor     r8d, r8d; lpReserved
0x18000f253  mov     r12, rcx
0x18000f256  call    cs:__imp_RegQueryValueExW
0x18000f25d  nop     dword ptr [rax+rax+00h]
0x18000f262  test    eax, eax
0x18000f264  jz      short loc_18000F2DD
0x18000f266  cmp     eax, 2
0x18000f269  jnz     short loc_18000F26F
0x18000f26b  mov     ecx, eax
0x18000f26d  jmp     short loc_18000F2EE
0x18000f26f  xor     ebx, ebx
0x18000f271  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx() failed, ec=%d"
0x18000f278  mov     edx, eax
0x18000f27a  call    fax_dprintf
0x18000f27f  mov     rcx, rbx; lpMem
0x18000f282  call    pMemFree
0x18000f287  mov     ecx, 2; dwBytes
0x18000f28c  mov     [rbp+cbData], 2
0x18000f293  call    pMemAlloc
0x18000f298  mov     rbx, rax
0x18000f29b  test    rax, rax
0x18000f29e  jz      short loc_18000F2C9
0x18000f2a0  mov     edx, [rbp+cbData]; unsigned __int64
0x18000f2a3  mov     rcx, rax; unsigned __int16 *
0x18000f2a6  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f2ab  test    eax, eax
0x18000f2ad  jns     loc_18000F426
0x18000f2b3  mov     edx, eax
0x18000f2b5  lea     rcx, aStringcbcopyFa; "StringCbCopy failed, hr = 0x%x"
0x18000f2bc  call    fax_dprintf
0x18000f2c1  mov     rcx, rbx; lpMem
0x18000f2c4  call    pMemFree
0x18000f2c9  xor     eax, eax
0x18000f2cb  add     rsp, 38h
0x18000f2cf  pop     r15
0x18000f2d1  pop     r14
0x18000f2d3  pop     r13
0x18000f2d5  pop     r12
0x18000f2d7  pop     rdi
0x18000f2d8  pop     rsi
0x18000f2d9  pop     rbx
0x18000f2da  pop     rbp
0x18000f2db  retn
0x18000f2dd  cmp     [rbp+Type], edi
0x18000f2e0  jnz     short loc_18000F2C9
0x18000f2e2  mov     ecx, [rbp+cbData]
0x18000f2e5  test    ecx, ecx
0x18000f2e7  jnz     short loc_18000F2F1
0x18000f2e9  mov     ecx, 20h ; ' '
0x18000f2ee  mov     [rbp+cbData], ecx
0x18000f2f1  mov     r13d, ecx
0x18000f2f4  and     r13d, 1
0x18000f2f8  add     r13d, ecx
0x18000f2fb  lea     r14d, [r13+2]
0x18000f2ff  mov     ecx, r14d; dwBytes
0x18000f302  mov     r15d, r14d
0x18000f305  call    pMemAlloc
0x18000f30a  mov     rbx, rax
0x18000f30d  test    rax, rax
0x18000f310  jz      loc_18000F27F
0x18000f316  lea     rax, [rbp+cbData]
0x18000f31a  xor     r8d, r8d; lpReserved
0x18000f31d  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000f322  lea     r9, [rbp+Type]; lpType
0x18000f326  mov     rdx, rsi; lpValueName
0x18000f329  mov     [rsp+38h+lpData], rbx; lpData
0x18000f32e  mov     rcx, r12; hKey
0x18000f331  call    cs:__imp_RegQueryValueExW
0x18000f338  nop     dword ptr [rax+rax+00h]
0x18000f33d  lea     ecx, [r14-1]
0x18000f341  mov     byte ptr [r13+rbx+0], 0
0x18000f347  mov     byte ptr [rcx+rbx], 0
0x18000f34b  test    byte ptr [rbp+cbData], 1
0x18000f34f  jz      short loc_18000F359
0x18000f351  lea     ecx, [r14-3]
0x18000f355  mov     byte ptr [rcx+rbx], 0
0x18000f359  test    eax, eax
0x18000f35b  jz      short loc_18000F3C0
0x18000f35d  cmp     eax, 2
0x18000f360  jnz     loc_18000F271
0x18000f366  mov     rdx, r15; unsigned __int64
0x18000f369  mov     rcx, rbx; unsigned __int16 *
0x18000f36c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f371  test    eax, eax
0x18000f373  jns     short loc_18000F381
0x18000f375  lea     rcx, aStringcbcopyFa_0; "StringCbCopy failed, hr: 0x%x"
0x18000f37c  jmp     loc_18000F278
0x18000f381  mov     eax, [rbp+cbData]
0x18000f384  mov     r9d, edi; dwType
0x18000f387  mov     dword ptr [rsp+38h+lpcbData], eax; cbData
0x18000f38b  xor     r8d, r8d; Reserved
0x18000f38e  mov     rdx, rsi; lpValueName
0x18000f391  mov     [rsp+38h+lpData], rbx; lpData
0x18000f396  mov     rcx, r12; hKey
0x18000f399  call    cs:__imp_RegSetValueExW
0x18000f3a0  nop     dword ptr [rax+rax+00h]
0x18000f3a5  test    eax, eax
0x18000f3a7  jz      short loc_18000F3C0
0x18000f3a9  mov     r8d, eax
0x18000f3ac  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000f3b3  mov     rdx, rsi
0x18000f3b6  call    fax_dprintf
0x18000f3bb  jmp     loc_18000F27F
0x18000f3c0  cmp     edi, 2
0x18000f3c3  jnz     short loc_18000F426
0x18000f3c5  xor     r8d, r8d; nSize
0x18000f3c8  xor     edx, edx; lpDst
0x18000f3ca  mov     rcx, rbx; lpSrc
0x18000f3cd  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f3d4  nop     dword ptr [rax+rax+00h]
0x18000f3d9  mov     esi, eax
0x18000f3db  test    eax, eax
0x18000f3dd  jz      loc_18000F27F
0x18000f3e3  lea     ecx, ds:2[rax*2]; dwBytes
0x18000f3ea  mov     [rbp+cbData], ecx
0x18000f3ed  call    pMemAlloc
0x18000f3f2  mov     rdi, rax
0x18000f3f5  test    rax, rax
0x18000f3f8  jz      loc_18000F27F
0x18000f3fe  mov     r8d, esi; nSize
0x18000f401  mov     rdx, rax; lpDst
0x18000f404  mov     rcx, rbx; lpSrc
0x18000f407  call    cs:__imp_ExpandEnvironmentStringsW
0x18000f40e  nop     dword ptr [rax+rax+00h]
0x18000f413  test    eax, eax
0x18000f415  jz      short loc_18000F42E
0x18000f417  cmp     eax, esi
0x18000f419  jg      short loc_18000F42E
0x18000f41b  mov     rcx, rbx; lpMem
0x18000f41e  call    pMemFree
0x18000f423  mov     rbx, rdi
0x18000f426  mov     rax, rbx
0x18000f429  jmp     loc_18000F2CB
0x18000f42e  mov     rcx, rdi; lpMem
0x18000f431  call    pMemFree
0x18000f436  call    cs:__imp_GetLastError
0x18000f43d  nop     dword ptr [rax+rax+00h]
0x18000f442  lea     rcx, aExpandenvironm; "ExpandEnvironmentStrings() failed, ec=%"...
0x18000f449  jmp     loc_18000F278
```
