# GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)

- ea: `0x18000eafc`
- end: `0x18000ed19`
- name: `?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z`
- size: `541`
- prototype: `unsigned __int16 *__usercall@<rax>(HKEY hKey@<rcx>, DWORD dwType@<edx>, LPCWSTR lpValueName@<r8>, const unsigned __int16 *@<r9>, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180016d30`
- `0x180016f40`
- `0x180017190`
- `0x180017280`
- `0x1800173a0`

## callees

- `0x18000ea18`
- `0x18000eac0`
- `0x18000eafc`
- `0x18000ed98`
- `0x180016794`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ed07`
- `KERNEL32!GetLastError` at `0x18000ed07`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000ecaa`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000ecde`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000ecaa`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18000ecde`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb46`
- `ADVAPI32!RegQueryValueExW` at `0x18000ec1a`
- `ADVAPI32!RegQueryValueExW` at `0x18000eb46`
- `ADVAPI32!RegQueryValueExW` at `0x18000ec1a`
- `ADVAPI32!RegSetValueExW` at `0x18000ec7c`
- `ADVAPI32!RegSetValueExW` at `0x18000ec7c`

## string_xrefs

- `0x18000ec58`: `StringCbCopy failed, hr: 0x%x`
- `0x18000eb9f`: `StringCbCopy failed, hr = 0x%x`
- `0x18000ec89`: `RegSetValueEx() failed[%s], ec=%d`

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
0x18000eafc  mov     qword ptr [rsp-40h+cbData], r9
0x18000eb01  push    rbp
0x18000eb02  push    rbx
0x18000eb03  push    rsi
0x18000eb04  push    rdi
0x18000eb05  push    r12
0x18000eb07  push    r13
0x18000eb09  push    r14
0x18000eb0b  push    r15
0x18000eb0d  mov     rbp, rsp
0x18000eb10  sub     rsp, 38h
0x18000eb14  mov     rsi, r8
0x18000eb17  mov     [rbp+cbData], 0
0x18000eb1e  lea     rax, [rbp+cbData]
0x18000eb22  mov     [rbp+Type], 0
0x18000eb29  mov     edi, edx
0x18000eb2b  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000eb30  mov     rdx, rsi; lpValueName
0x18000eb33  mov     [rsp+38h+lpData], 0; lpData
0x18000eb3c  lea     r9, [rbp+Type]; lpType
0x18000eb40  xor     r8d, r8d; lpReserved
0x18000eb43  mov     r12, rcx
0x18000eb46  call    cs:__imp_RegQueryValueExW
0x18000eb4c  test    eax, eax
0x18000eb4e  jz      short loc_18000EBC6
0x18000eb50  cmp     eax, 2
0x18000eb53  jnz     short loc_18000EB59
0x18000eb55  mov     ecx, eax
0x18000eb57  jmp     short loc_18000EBD7
0x18000eb59  xor     ebx, ebx
0x18000eb5b  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx() failed, ec=%d"
0x18000eb62  mov     edx, eax
0x18000eb64  call    fax_dprintf
0x18000eb69  mov     rcx, rbx; lpMem
0x18000eb6c  call    pMemFree
0x18000eb71  mov     ecx, 2; dwBytes
0x18000eb76  mov     [rbp+cbData], 2
0x18000eb7d  call    pMemAlloc
0x18000eb82  mov     rbx, rax
0x18000eb85  test    rax, rax
0x18000eb88  jz      short loc_18000EBB3
0x18000eb8a  mov     edx, [rbp+cbData]; unsigned __int64
0x18000eb8d  mov     rcx, rax; unsigned __int16 *
0x18000eb90  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000eb95  test    eax, eax
0x18000eb97  jns     loc_18000ECF7
0x18000eb9d  mov     edx, eax
0x18000eb9f  lea     rcx, aStringcbcopyFa; "StringCbCopy failed, hr = 0x%x"
0x18000eba6  call    fax_dprintf
0x18000ebab  mov     rcx, rbx; lpMem
0x18000ebae  call    pMemFree
0x18000ebb3  xor     eax, eax
0x18000ebb5  add     rsp, 38h
0x18000ebb9  pop     r15
0x18000ebbb  pop     r14
0x18000ebbd  pop     r13
0x18000ebbf  pop     r12
0x18000ebc1  pop     rdi
0x18000ebc2  pop     rsi
0x18000ebc3  pop     rbx
0x18000ebc4  pop     rbp
0x18000ebc5  retn
0x18000ebc6  cmp     [rbp+Type], edi
0x18000ebc9  jnz     short loc_18000EBB3
0x18000ebcb  mov     ecx, [rbp+cbData]
0x18000ebce  test    ecx, ecx
0x18000ebd0  jnz     short loc_18000EBDA
0x18000ebd2  mov     ecx, 20h ; ' '
0x18000ebd7  mov     [rbp+cbData], ecx
0x18000ebda  mov     r13d, ecx
0x18000ebdd  and     r13d, 1
0x18000ebe1  add     r13d, ecx
0x18000ebe4  lea     r14d, [r13+2]
0x18000ebe8  mov     ecx, r14d; dwBytes
0x18000ebeb  mov     r15d, r14d
0x18000ebee  call    pMemAlloc
0x18000ebf3  mov     rbx, rax
0x18000ebf6  test    rax, rax
0x18000ebf9  jz      loc_18000EB69
0x18000ebff  lea     rax, [rbp+cbData]
0x18000ec03  xor     r8d, r8d; lpReserved
0x18000ec06  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000ec0b  lea     r9, [rbp+Type]; lpType
0x18000ec0f  mov     rdx, rsi; lpValueName
0x18000ec12  mov     [rsp+38h+lpData], rbx; lpData
0x18000ec17  mov     rcx, r12; hKey
0x18000ec1a  call    cs:__imp_RegQueryValueExW
0x18000ec20  lea     ecx, [r14-1]
0x18000ec24  mov     byte ptr [r13+rbx+0], 0
0x18000ec2a  mov     byte ptr [rcx+rbx], 0
0x18000ec2e  test    byte ptr [rbp+cbData], 1
0x18000ec32  jz      short loc_18000EC3C
0x18000ec34  lea     ecx, [r14-3]
0x18000ec38  mov     byte ptr [rcx+rbx], 0
0x18000ec3c  test    eax, eax
0x18000ec3e  jz      short loc_18000EC9D
0x18000ec40  cmp     eax, 2
0x18000ec43  jnz     loc_18000EB5B
0x18000ec49  mov     rdx, r15; unsigned __int64
0x18000ec4c  mov     rcx, rbx; unsigned __int16 *
0x18000ec4f  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ec54  test    eax, eax
0x18000ec56  jns     short loc_18000EC64
0x18000ec58  lea     rcx, aStringcbcopyFa_0; "StringCbCopy failed, hr: 0x%x"
0x18000ec5f  jmp     loc_18000EB62
0x18000ec64  mov     eax, [rbp+cbData]
0x18000ec67  mov     r9d, edi; dwType
0x18000ec6a  mov     dword ptr [rsp+38h+lpcbData], eax; cbData
0x18000ec6e  xor     r8d, r8d; Reserved
0x18000ec71  mov     rdx, rsi; lpValueName
0x18000ec74  mov     [rsp+38h+lpData], rbx; lpData
0x18000ec79  mov     rcx, r12; hKey
0x18000ec7c  call    cs:__imp_RegSetValueExW
0x18000ec82  test    eax, eax
0x18000ec84  jz      short loc_18000EC9D
0x18000ec86  mov     r8d, eax
0x18000ec89  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x18000ec90  mov     rdx, rsi
0x18000ec93  call    fax_dprintf
0x18000ec98  jmp     loc_18000EB69
0x18000ec9d  cmp     edi, 2
0x18000eca0  jnz     short loc_18000ECF7
0x18000eca2  xor     r8d, r8d; nSize
0x18000eca5  xor     edx, edx; lpDst
0x18000eca7  mov     rcx, rbx; lpSrc
0x18000ecaa  call    cs:__imp_ExpandEnvironmentStringsW
0x18000ecb0  mov     esi, eax
0x18000ecb2  test    eax, eax
0x18000ecb4  jz      loc_18000EB69
0x18000ecba  lea     ecx, ds:2[rax*2]; dwBytes
0x18000ecc1  mov     [rbp+cbData], ecx
0x18000ecc4  call    pMemAlloc
0x18000ecc9  mov     rdi, rax
0x18000eccc  test    rax, rax
0x18000eccf  jz      loc_18000EB69
0x18000ecd5  mov     r8d, esi; nSize
0x18000ecd8  mov     rdx, rax; lpDst
0x18000ecdb  mov     rcx, rbx; lpSrc
0x18000ecde  call    cs:__imp_ExpandEnvironmentStringsW
0x18000ece4  test    eax, eax
0x18000ece6  jz      short loc_18000ECFF
0x18000ece8  cmp     eax, esi
0x18000ecea  jg      short loc_18000ECFF
0x18000ecec  mov     rcx, rbx; lpMem
0x18000ecef  call    pMemFree
0x18000ecf4  mov     rbx, rdi
0x18000ecf7  mov     rax, rbx
0x18000ecfa  jmp     loc_18000EBB5
0x18000ecff  mov     rcx, rdi; lpMem
0x18000ed02  call    pMemFree
0x18000ed07  call    cs:__imp_GetLastError
0x18000ed0d  lea     rcx, aExpandenvironm; "ExpandEnvironmentStrings() failed, ec=%"...
0x18000ed14  jmp     loc_18000EB62
```
