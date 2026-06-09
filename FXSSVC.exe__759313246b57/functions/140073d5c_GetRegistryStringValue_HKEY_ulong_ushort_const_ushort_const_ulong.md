# GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)

- ea: `0x140073d5c`
- end: `0x140073ffb`
- name: `?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z`
- size: `671`
- prototype: `BYTE *__fastcall(HKEY hKey, DWORD dwType, LPCWSTR lpValueName, const unsigned __int16 *, DWORD cbData)`
- caller_count: `12`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000dd74`
- `0x140053e5c`
- `0x1400791f0`
- `0x14007f8d0`
- `0x14007fb00`
- `0x14007fd80`
- `0x14007ff10`
- `0x140080050`
- `0x1400815a0`
- `0x1400821e4`
- `0x140082538`
- `0x140082830`

## callees

- `0x140016244`
- `0x1400698ec`
- `0x14006998c`
- `0x140073d5c`
- `0x140076758`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140073ecc`
- `ADVAPI32!RegSetValueExW` at `0x140073ecc`
- `ADVAPI32!RegQueryValueExW` at `0x140073da3`
- `ADVAPI32!RegQueryValueExW` at `0x140073e54`
- `ADVAPI32!RegQueryValueExW` at `0x140073da3`
- `ADVAPI32!RegQueryValueExW` at `0x140073e54`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140073f12`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140073f45`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140073f12`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x140073f45`
- `KERNEL32!GetLastError` at `0x140073f72`
- `KERNEL32!GetLastError` at `0x140073f72`

## string_xrefs

- `0x140073ea7`: `StringCbCopy failed, hr: 0x%x`
- `0x140073ef3`: `Can't create DefaultValue since it's NULL`
- `0x140073edf`: `RegSetValueEx() failed[%s], ec=%d`
- `0x140073fd3`: `StringCbCopy failed, hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140073d5c  mov     [rsp-40h+hKey], rcx
0x140073d61  push    rbp
0x140073d62  push    rbx
0x140073d63  push    rsi
0x140073d64  push    rdi
0x140073d65  push    r12
0x140073d67  push    r13
0x140073d69  push    r14
0x140073d6b  push    r15
0x140073d6d  mov     rbp, rsp
0x140073d70  sub     rsp, 48h
0x140073d74  mov     rax, rcx
0x140073d77  mov     r12, r8
0x140073d7a  xor     esi, esi
0x140073d7c  lea     rcx, [rbp+cbData]
0x140073d80  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x140073d85  mov     rdi, r9
0x140073d88  mov     r14d, edx
0x140073d8b  mov     [rbp+cbData], esi
0x140073d8e  mov     rcx, rax; hKey
0x140073d91  mov     [rbp+Type], esi
0x140073d94  lea     r9, [rbp+Type]; lpType
0x140073d98  mov     [rsp+48h+lpData], rsi; lpData
0x140073d9d  xor     r8d, r8d; lpReserved
0x140073da0  mov     rdx, r12; lpValueName
0x140073da3  call    cs:__imp_RegQueryValueExW
0x140073daa  nop     dword ptr [rax+rax+00h]
0x140073daf  or      r15, 0FFFFFFFFFFFFFFFFh
0x140073db3  test    eax, eax
0x140073db5  jz      short loc_140073DFC
0x140073db7  mov     ebx, esi
0x140073db9  cmp     eax, 2
0x140073dbc  jnz     short loc_140073DF1
0x140073dbe  test    rdi, rdi
0x140073dc1  jz      short loc_140073DDB
0x140073dc3  mov     rcx, r15
0x140073dc6  inc     rcx
0x140073dc9  cmp     [rdi+rcx*2], si
0x140073dcd  jnz     short loc_140073DC6
0x140073dcf  lea     ecx, ds:2[rcx*2]
0x140073dd6  mov     [rbp+cbData], ecx
0x140073dd9  jmp     short loc_140073E09
0x140073ddb  mov     edx, 2
0x140073de0  lea     rcx, aRegqueryvaluee; "RegQueryValueEx() failed, ec=%d - and n"...
0x140073de7  call    fax_dprintf
0x140073dec  jmp     loc_140073F8E
0x140073df1  mov     edx, eax
0x140073df3  lea     rcx, aRegqueryvaluee_1; "RegQueryValueEx() failed, ec=%d"
0x140073dfa  jmp     short loc_140073DE7
0x140073dfc  cmp     [rbp+Type], r14d
0x140073e00  jnz     loc_140073FE7
0x140073e06  mov     ecx, [rbp+cbData]
0x140073e09  test    ecx, ecx
0x140073e0b  jnz     short loc_140073E15
0x140073e0d  mov     ecx, 20h ; ' '
0x140073e12  mov     [rbp+cbData], ecx
0x140073e15  mov     eax, ecx
0x140073e17  and     eax, 1
0x140073e1a  add     eax, ecx
0x140073e1c  mov     [rbp+var_14], eax
0x140073e1f  lea     esi, [rax+2]
0x140073e22  mov     ecx, esi; dwBytes
0x140073e24  mov     r13d, esi
0x140073e27  call    pMemAlloc
0x140073e2c  mov     rbx, rax
0x140073e2f  test    rax, rax
0x140073e32  jz      loc_140073F8C
0x140073e38  mov     rcx, [rbp+hKey]; hKey
0x140073e3c  lea     rax, [rbp+cbData]
0x140073e40  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140073e45  lea     r9, [rbp+Type]; lpType
0x140073e49  xor     r8d, r8d; lpReserved
0x140073e4c  mov     [rsp+48h+lpData], rbx; lpData
0x140073e51  mov     rdx, r12; lpValueName
0x140073e54  call    cs:__imp_RegQueryValueExW
0x140073e5b  nop     dword ptr [rax+rax+00h]
0x140073e60  lea     ecx, [rsi-1]
0x140073e63  mov     byte ptr [rcx+rbx], 0
0x140073e67  mov     ecx, [rbp+var_14]
0x140073e6a  mov     byte ptr [rcx+rbx], 0
0x140073e6e  test    byte ptr [rbp+cbData], 1
0x140073e72  jz      short loc_140073E7F
0x140073e74  lea     ecx, [rsi-3]
0x140073e77  xor     esi, esi
0x140073e79  mov     [rcx+rbx], sil
0x140073e7d  jmp     short loc_140073E81
0x140073e7f  xor     esi, esi
0x140073e81  test    eax, eax
0x140073e83  jz      short loc_140073F04
0x140073e85  cmp     eax, 2
0x140073e88  jnz     loc_140073DF1
0x140073e8e  test    rdi, rdi
0x140073e91  jz      short loc_140073EF3
0x140073e93  mov     r8, rdi; unsigned __int16 *
0x140073e96  mov     rdx, r13; unsigned __int64
0x140073e99  mov     rcx, rbx; unsigned __int16 *
0x140073e9c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140073ea1  test    eax, eax
0x140073ea3  jns     short loc_140073EB3
0x140073ea5  mov     edx, eax
0x140073ea7  lea     rcx, aStringcbcopyFa_0; "StringCbCopy failed, hr: 0x%x"
0x140073eae  jmp     loc_140073DE7
0x140073eb3  mov     eax, [rbp+cbData]
0x140073eb6  mov     r9d, r14d; dwType
0x140073eb9  mov     rcx, [rbp+hKey]; hKey
0x140073ebd  xor     r8d, r8d; Reserved
0x140073ec0  mov     dword ptr [rsp+48h+lpcbData], eax; cbData
0x140073ec4  mov     rdx, r12; lpValueName
0x140073ec7  mov     [rsp+48h+lpData], rbx; lpData
0x140073ecc  call    cs:__imp_RegSetValueExW
0x140073ed3  nop     dword ptr [rax+rax+00h]
0x140073ed8  test    eax, eax
0x140073eda  jz      short loc_140073F04
0x140073edc  mov     r8d, eax
0x140073edf  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x140073ee6  mov     rdx, r12
0x140073ee9  call    fax_dprintf
0x140073eee  jmp     loc_140073F8E
0x140073ef3  lea     rcx, aCanTCreateDefa; "Can't create DefaultValue since it's NU"...
0x140073efa  call    fax_dprintf
0x140073eff  jmp     loc_140073F8E
0x140073f04  cmp     r14d, 2
0x140073f08  jnz     short loc_140073F65
0x140073f0a  xor     r8d, r8d; nSize
0x140073f0d  xor     edx, edx; lpDst
0x140073f0f  mov     rcx, rbx; lpSrc
0x140073f12  call    cs:__imp_ExpandEnvironmentStringsW
0x140073f19  nop     dword ptr [rax+rax+00h]
0x140073f1e  mov     r14d, eax
0x140073f21  test    eax, eax
0x140073f23  jz      short loc_140073F8E
0x140073f25  lea     ecx, ds:2[rax*2]; dwBytes
0x140073f2c  mov     [rbp+cbData], ecx
0x140073f2f  call    pMemAlloc
0x140073f34  mov     rsi, rax
0x140073f37  test    rax, rax
0x140073f3a  jz      short loc_140073F8C
0x140073f3c  mov     r8d, r14d; nSize
0x140073f3f  mov     rdx, rax; lpDst
0x140073f42  mov     rcx, rbx; lpSrc
0x140073f45  call    cs:__imp_ExpandEnvironmentStringsW
0x140073f4c  nop     dword ptr [rax+rax+00h]
0x140073f51  test    eax, eax
0x140073f53  jz      short loc_140073F6A
0x140073f55  cmp     eax, r14d
0x140073f58  jg      short loc_140073F6A
0x140073f5a  mov     rcx, rbx; lpMem
0x140073f5d  call    pMemFree
0x140073f62  mov     rbx, rsi
0x140073f65  mov     rax, rbx
0x140073f68  jmp     short loc_140073FE9
0x140073f6a  mov     rcx, rsi; lpMem
0x140073f6d  call    pMemFree
0x140073f72  call    cs:__imp_GetLastError
0x140073f79  nop     dword ptr [rax+rax+00h]
0x140073f7e  mov     edx, eax
0x140073f80  lea     rcx, aExpandenvironm; "ExpandEnvironmentStrings() failed, ec=%"...
0x140073f87  call    fax_dprintf
0x140073f8c  xor     esi, esi
0x140073f8e  mov     rcx, rbx; lpMem
0x140073f91  call    pMemFree
0x140073f96  test    rdi, rdi
0x140073f99  jz      short loc_140073FE7
0x140073f9b  inc     r15
0x140073f9e  cmp     [rdi+r15*2], si
0x140073fa3  jnz     short loc_140073F9B
0x140073fa5  lea     eax, ds:2[r15*2]
0x140073fad  mov     ecx, eax; dwBytes
0x140073faf  mov     [rbp+cbData], eax
0x140073fb2  call    pMemAlloc
0x140073fb7  mov     rbx, rax
0x140073fba  test    rax, rax
0x140073fbd  jz      short loc_140073FE7
0x140073fbf  mov     edx, [rbp+cbData]; unsigned __int64
0x140073fc2  mov     r8, rdi; unsigned __int16 *
0x140073fc5  mov     rcx, rax; unsigned __int16 *
0x140073fc8  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140073fcd  test    eax, eax
0x140073fcf  jns     short loc_140073F65
0x140073fd1  mov     edx, eax
0x140073fd3  lea     rcx, aStringcbcopyFa; "StringCbCopy failed, hr = 0x%x"
0x140073fda  call    fax_dprintf
0x140073fdf  mov     rcx, rbx; lpMem
0x140073fe2  call    pMemFree
0x140073fe7  xor     eax, eax
0x140073fe9  add     rsp, 48h
0x140073fed  pop     r15
0x140073fef  pop     r14
0x140073ff1  pop     r13
0x140073ff3  pop     r12
0x140073ff5  pop     rdi
0x140073ff6  pop     rsi
0x140073ff7  pop     rbx
0x140073ff8  pop     rbp
0x140073ff9  retn
```
