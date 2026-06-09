# QueryUrlAclInfo

- ea: `0x18000941c`
- end: `0x1800096ba`
- name: `QueryUrlAclInfo`
- size: `670`
- prototype: `LSTATUS __fastcall(__int64, int, _QWORD *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180001e70`

## callees

- `0x18000941c`
- `0x18000a4bc`
- `0x18000a4c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000969a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000969a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009564`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800095bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009564`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800095bf`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180009523`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180009523`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009493`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009493`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000966e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000967d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000968b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000966e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000967d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000968b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800094cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000958d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800094cc`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000958d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800095f0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800095f0`

## string_xrefs

- `0x180009485`: `System\CurrentControlSet\Services\HTTP\Parameters\UrlAclInfo`

## pseudocode

```c
LSTATUS __fastcall QueryUrlAclInfo(__int64 a1, int a2, _QWORD *a3, unsigned int a4, unsigned int *a5)
{
  LSTATUS result; // eax
  HLOCAL v9; // rsi
  DWORD LastError; // ebx
  DWORD v11; // ebx
  WCHAR *v12; // rax
  WCHAR *v13; // rdi
  char v14; // r15
  LSTATUS v15; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  unsigned int v18; // ecx
  char *v19; // rbx
  size_t v20; // r8
  LPWSTR v21; // rdx
  DWORD cbData; // [rsp+40h] [rbp-28h] BYREF
  DWORD Type; // [rsp+44h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+50h] [rbp-18h] BYREF
  size_t Size; // [rsp+B0h] [rbp+48h] BYREF

  Type = 0;
  cbData = 0;
  LODWORD(Size) = 0;
  StringSecurityDescriptor = 0;
  hKey = 0;
  if ( !a1 || a2 != 24 )
    return 87;
  if ( !g_ServiceCommChannelHandle )
    return 6;
  result = RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Services\\HTTP\\Parameters\\UrlAclInfo",
             0,
             0x20019u,
             &hKey);
  if ( !result )
  {
    v9 = 0;
    if ( *(_DWORD *)a1 )
    {
      if ( *(_DWORD *)a1 != 1 )
      {
        LastError = 87;
LABEL_30:
        if ( StringSecurityDescriptor )
          LocalFree(StringSecurityDescriptor);
        if ( v9 )
          LocalFree(v9);
        if ( hKey )
          RegCloseKey(hKey);
        return LastError;
      }
      v11 = *(_DWORD *)(a1 + 16);
      LODWORD(Size) = 0x20000;
      cbData = 0;
      v12 = (WCHAR *)LocalAlloc(0, 0x20000u);
      v13 = v12;
      if ( !v12 )
      {
        LastError = 8;
        goto LABEL_30;
      }
      memset_0(v12, 0, (unsigned int)Size);
      v14 = 1;
      LODWORD(Size) = 0xFFFF;
      v15 = RegEnumValueW(hKey, v11, v13, (LPDWORD)&Size, 0, &Type, 0, &cbData);
      LODWORD(Size) = Size + 1;
    }
    else
    {
      v13 = *(WCHAR **)(a1 + 8);
      v14 = 0;
      v16 = -1;
      do
        ++v16;
      while ( v13[v16] );
      LODWORD(Size) = v16 + 1;
      v15 = RegQueryValueExW(hKey, v13, 0, &Type, 0, &cbData);
    }
    LastError = v15;
    if ( !v15 )
    {
      if ( Type != 3 || !cbData )
        goto LABEL_27;
      v9 = LocalAlloc(0, cbData);
      if ( !v9 )
      {
        LastError = 8;
        goto LABEL_28;
      }
      LastError = RegQueryValueExW(hKey, v13, 0, &Type, (LPBYTE)v9, &cbData);
      if ( !LastError )
      {
        if ( Type == 3 )
        {
          if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v9, 1u, 0xFu, &StringSecurityDescriptor, &cbData) )
          {
            cbData *= 2;
            v17 = (unsigned int)(2 * Size);
            LODWORD(Size) = v17;
            v18 = v17 + 16 + cbData;
            *a5 = v18;
            if ( a4 < v18 )
            {
              LastError = 122;
            }
            else
            {
              a3[1] = 0;
              v19 = (char *)a3 + v17 + 16;
              *a3 = a3 + 2;
              memcpy_0(a3 + 2, v13, (unsigned int)v17);
              v20 = cbData;
              v21 = StringSecurityDescriptor;
              a3[1] = v19;
              memcpy_0(v19, v21, v20);
              LastError = 0;
            }
          }
          else
          {
            LastError = GetLastError();
          }
          goto LABEL_28;
        }
LABEL_27:
        LastError = 1015;
      }
    }
LABEL_28:
    if ( v14 )
      LocalFree(v13);
    goto LABEL_30;
  }
  return result;
}

```

## disassembly

```asm
0x18000941c  push    rbp
0x18000941e  push    rbx
0x18000941f  push    rsi
0x180009420  push    rdi
0x180009421  push    r12
0x180009423  push    r13
0x180009425  push    r14
0x180009427  push    r15
0x180009429  mov     rbp, rsp
0x18000942c  sub     rsp, 68h
0x180009430  xor     r13d, r13d
0x180009433  mov     r12d, r9d
0x180009436  mov     [rbp+Type], r13d
0x18000943a  mov     r14, r8
0x18000943d  mov     [rbp+cbData], r13d
0x180009441  mov     rbx, rcx
0x180009444  mov     dword ptr [rbp+Size], r13d
0x180009448  mov     [rbp+StringSecurityDescriptor], r13
0x18000944c  mov     [rbp+hKey], r13
0x180009450  test    rcx, rcx
0x180009453  jz      loc_1800096A4
0x180009459  cmp     edx, 18h
0x18000945c  jnz     loc_1800096A4
0x180009462  cmp     cs:g_ServiceCommChannelHandle, r13
0x180009469  jnz     short loc_180009473
0x18000946b  lea     eax, [rdx-12h]
0x18000946e  jmp     loc_1800096A9
0x180009473  lea     rax, [rbp+hKey]
0x180009477  mov     r9d, 20019h; samDesired
0x18000947d  xor     r8d, r8d; ulOptions
0x180009480  mov     [rsp+68h+phkResult], rax; phkResult
0x180009485  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\HT"...
0x18000948c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009493  call    cs:__imp_RegOpenKeyExW
0x180009499  test    eax, eax
0x18000949b  jnz     loc_1800096A9
0x1800094a1  mov     ecx, [rbx]
0x1800094a3  mov     rsi, r13
0x1800094a6  test    ecx, ecx
0x1800094a8  jz      loc_18000952E
0x1800094ae  cmp     ecx, 1
0x1800094b1  jz      short loc_1800094BB
0x1800094b3  lea     ebx, [rax+57h]
0x1800094b6  jmp     loc_180009674
0x1800094bb  mov     ebx, [rbx+10h]
0x1800094be  mov     edx, 20000h; uBytes
0x1800094c3  xor     ecx, ecx; uFlags
0x1800094c5  mov     dword ptr [rbp+Size], edx
0x1800094c8  mov     [rbp+cbData], r13d
0x1800094cc  call    cs:__imp_LocalAlloc
0x1800094d2  mov     rdi, rax
0x1800094d5  test    rax, rax
0x1800094d8  jnz     short loc_1800094E2
0x1800094da  lea     ebx, [rax+8]
0x1800094dd  jmp     loc_180009674
0x1800094e2  mov     r8d, dword ptr [rbp+Size]; Size
0x1800094e6  xor     edx, edx; Val
0x1800094e8  mov     rcx, rdi; void *
0x1800094eb  call    memset_0
0x1800094f0  mov     rcx, [rbp+hKey]; hKey
0x1800094f4  lea     rax, [rbp+cbData]
0x1800094f8  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800094fd  lea     r9, [rbp+Size]; lpcchValueName
0x180009501  lea     rax, [rbp+Type]
0x180009505  mov     [rsp+68h+lpData], r13; lpData
0x18000950a  mov     [rsp+68h+lpType], rax; lpType
0x18000950f  mov     r8, rdi; lpValueName
0x180009512  mov     edx, ebx; dwIndex
0x180009514  mov     [rsp+68h+phkResult], r13; lpReserved
0x180009519  mov     r15b, 1
0x18000951c  mov     dword ptr [rbp+Size], 0FFFFh
0x180009523  call    cs:__imp_RegEnumValueW
0x180009529  inc     dword ptr [rbp+Size]
0x18000952c  jmp     short loc_18000956A
0x18000952e  mov     rdi, [rbx+8]
0x180009532  mov     r15b, r13b
0x180009535  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009539  inc     rax
0x18000953c  cmp     [rdi+rax*2], r13w
0x180009541  jnz     short loc_180009539
0x180009543  mov     rcx, [rbp+hKey]; hKey
0x180009547  lea     r9, [rbp+Type]; lpType
0x18000954b  inc     eax
0x18000954d  xor     r8d, r8d; lpReserved
0x180009550  mov     dword ptr [rbp+Size], eax
0x180009553  mov     rdx, rdi; lpValueName
0x180009556  lea     rax, [rbp+cbData]
0x18000955a  mov     [rsp+68h+lpType], rax; lpcbData
0x18000955f  mov     [rsp+68h+phkResult], r13; lpData
0x180009564  call    cs:__imp_RegQueryValueExW
0x18000956a  mov     ebx, eax
0x18000956c  test    eax, eax
0x18000956e  jnz     loc_180009666
0x180009574  cmp     [rbp+Type], 3
0x180009578  jnz     loc_180009661
0x18000957e  mov     eax, [rbp+cbData]
0x180009581  test    eax, eax
0x180009583  jz      loc_180009661
0x180009589  mov     edx, eax; uBytes
0x18000958b  xor     ecx, ecx; uFlags
0x18000958d  call    cs:__imp_LocalAlloc
0x180009593  mov     rsi, rax
0x180009596  test    rax, rax
0x180009599  jnz     short loc_1800095A3
0x18000959b  lea     ebx, [rax+8]
0x18000959e  jmp     loc_180009666
0x1800095a3  mov     rcx, [rbp+hKey]; hKey
0x1800095a7  lea     rax, [rbp+cbData]
0x1800095ab  mov     [rsp+68h+lpType], rax; lpcbData
0x1800095b0  lea     r9, [rbp+Type]; lpType
0x1800095b4  xor     r8d, r8d; lpReserved
0x1800095b7  mov     [rsp+68h+phkResult], rsi; lpData
0x1800095bc  mov     rdx, rdi; lpValueName
0x1800095bf  call    cs:__imp_RegQueryValueExW
0x1800095c5  mov     ebx, eax
0x1800095c7  test    eax, eax
0x1800095c9  jnz     loc_180009666
0x1800095cf  cmp     [rbp+Type], 3
0x1800095d3  jnz     loc_180009661
0x1800095d9  lea     rax, [rbp+cbData]
0x1800095dd  mov     rcx, rsi; SecurityDescriptor
0x1800095e0  lea     r9, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800095e4  mov     [rsp+68h+phkResult], rax; StringSecurityDescriptorLen
0x1800095e9  lea     edx, [rbx+1]; RequestedStringSDRevision
0x1800095ec  lea     r8d, [rbx+0Fh]; SecurityInformation
0x1800095f0  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800095f6  test    eax, eax
0x1800095f8  jnz     short loc_180009604
0x1800095fa  call    cs:__imp_GetLastError
0x180009600  mov     ebx, eax
0x180009602  jmp     short loc_180009666
0x180009604  mov     eax, [rbp+cbData]
0x180009607  lea     ecx, [rax+rax]
0x18000960a  mov     eax, dword ptr [rbp+Size]
0x18000960d  add     eax, eax
0x18000960f  mov     [rbp+cbData], ecx
0x180009612  mov     edx, eax
0x180009614  mov     dword ptr [rbp+Size], eax
0x180009617  add     eax, 10h
0x18000961a  add     ecx, eax
0x18000961c  mov     rax, [rbp+arg_20]
0x180009620  mov     [rax], ecx
0x180009622  cmp     r12d, ecx
0x180009625  jb      short loc_18000965A
0x180009627  lea     rcx, [r14+10h]; void *
0x18000962b  mov     [r14+8], r13
0x18000962f  lea     rbx, [rcx+rdx]
0x180009633  mov     [r14], rcx
0x180009636  mov     r8d, edx; Size
0x180009639  mov     rdx, rdi; Src
0x18000963c  call    memcpy_0
0x180009641  mov     r8d, [rbp+cbData]; Size
0x180009645  mov     rcx, rbx; void *
0x180009648  mov     rdx, [rbp+StringSecurityDescriptor]; Src
0x18000964c  mov     [r14+8], rbx
0x180009650  call    memcpy_0
0x180009655  mov     ebx, r13d
0x180009658  jmp     short loc_180009666
0x18000965a  mov     ebx, 7Ah ; 'z'
0x18000965f  jmp     short loc_180009666
0x180009661  mov     ebx, 3F7h
0x180009666  test    r15b, r15b
0x180009669  jz      short loc_180009674
0x18000966b  mov     rcx, rdi; hMem
0x18000966e  call    cs:__imp_LocalFree
0x180009674  mov     rcx, [rbp+StringSecurityDescriptor]; hMem
0x180009678  test    rcx, rcx
0x18000967b  jz      short loc_180009683
0x18000967d  call    cs:__imp_LocalFree
0x180009683  test    rsi, rsi
0x180009686  jz      short loc_180009691
0x180009688  mov     rcx, rsi; hMem
0x18000968b  call    cs:__imp_LocalFree
0x180009691  mov     rcx, [rbp+hKey]; hKey
0x180009695  test    rcx, rcx
0x180009698  jz      short loc_1800096A0
0x18000969a  call    cs:__imp_RegCloseKey
0x1800096a0  mov     eax, ebx
0x1800096a2  jmp     short loc_1800096A9
0x1800096a4  mov     eax, 57h ; 'W'
0x1800096a9  add     rsp, 68h
0x1800096ad  pop     r15
0x1800096af  pop     r14
0x1800096b1  pop     r13
0x1800096b3  pop     r12
0x1800096b5  pop     rdi
0x1800096b6  pop     rsi
0x1800096b7  pop     rbx
0x1800096b8  pop     rbp
0x1800096b9  retn
```
