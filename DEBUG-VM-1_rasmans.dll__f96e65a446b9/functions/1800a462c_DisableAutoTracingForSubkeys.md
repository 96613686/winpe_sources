# DisableAutoTracingForSubkeys

- ea: `0x1800a462c`
- end: `0x1800a486c`
- name: `DisableAutoTracingForSubkeys`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a44c4`

## callees

- `0x180053974`
- `0x1800a462c`
- `0x1800a5770`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a4688`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4696`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4696`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a46dd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800a46dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a47b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a47b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a477d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a477d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4828`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a4828`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a47f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a481d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a47f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a481d`

## pseudocode

```c
__int64 __fastcall DisableAutoTracingForSubkeys(DWORD a1, DWORD a2, HKEY a3)
{
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v8; // rdi
  DWORD i; // ebx
  const WCHAR *v11; // r8
  __int64 v12; // rdx
  wchar_t *v13; // rax
  __int64 v14; // rcx
  wchar_t *v15; // rcx
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  BYTE v20[8]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 2 * a2;
  cchName = 0;
  *(_DWORD *)v20 = 0;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  cbData = 4;
  ProcessHeap = GetProcessHeap();
  v8 = (wchar_t *)HeapAlloc(ProcessHeap, 0, v3);
  if ( !v8 )
    return 8;
  for ( i = 0; i < a1; ++i )
  {
    cchName = a2;
    if ( !RegEnumKeyExW(a3, i, v8, &cchName, 0, 0, 0, 0) )
    {
      v11 = L"SOFTWARE\\Microsoft\\Tracing";
      v12 = 261;
      v13 = pszDest;
      v14 = 2147483646;
      do
      {
        if ( !v14 )
          break;
        if ( !*v11 )
          break;
        *v13++ = *v11++;
        --v14;
        --v12;
      }
      while ( v12 );
      v15 = v13 - 1;
      if ( v12 )
        v15 = v13;
      *v15 = 0;
      StringCchCatW(pszDest, 0x105u, L"\\");
      StringCchCatW(pszDest, 0x105u, v8);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x2011Fu, &phkResult) )
      {
        cbData = 4;
        if ( !RegQueryValueExW(phkResult, L"EnableAutoFileTracing", 0, 0, Data, &cbData) && *(_DWORD *)Data == 1 )
        {
          *(_DWORD *)v20 = 0;
          *(_DWORD *)Data = 0;
          if ( !RegSetValueExW(phkResult, L"EnableAutoFileTracing", 0, 4u, Data, 4u) )
            RegSetValueExW(phkResult, L"EnableFileTracing", 0, 4u, v20, 4u);
        }
        RegCloseKey(phkResult);
      }
    }
  }
  MprCommonFree(v8);
  return 0;
}

```

## disassembly

```asm
0x1800a462c  mov     [rsp-8+arg_0], rbx
0x1800a4631  push    rbp
0x1800a4632  push    rsi
0x1800a4633  push    rdi
0x1800a4634  push    r12
0x1800a4636  push    r13
0x1800a4638  push    r14
0x1800a463a  push    r15
0x1800a463c  lea     rbp, [rsp-180h]
0x1800a4644  sub     rsp, 280h
0x1800a464b  mov     rax, cs:__security_cookie
0x1800a4652  xor     rax, rsp
0x1800a4655  mov     [rbp+1B0h+var_40], rax
0x1800a465c  xor     r12d, r12d
0x1800a465f  lea     ebx, [rdx+rdx]
0x1800a4662  mov     r15, r8
0x1800a4665  mov     [rsp+2B0h+cchName], r12d
0x1800a466a  mov     r14d, edx
0x1800a466d  mov     dword ptr [rsp+2B0h+var_258], r12d
0x1800a4672  mov     esi, ecx
0x1800a4674  mov     dword ptr [rsp+2B0h+Data], r12d
0x1800a4679  lea     r13d, [r12+4]
0x1800a467e  mov     [rsp+2B0h+phkResult], r12
0x1800a4683  mov     [rsp+2B0h+cbData], r13d
0x1800a4688  call    cs:__imp_GetProcessHeap
0x1800a468e  mov     r8d, ebx; dwBytes
0x1800a4691  xor     edx, edx; dwFlags
0x1800a4693  mov     rcx, rax; hHeap
0x1800a4696  call    cs:__imp_HeapAlloc
0x1800a469c  mov     rdi, rax
0x1800a469f  test    rax, rax
0x1800a46a2  jnz     short loc_1800A46AC
0x1800a46a4  lea     eax, [rdi+8]
0x1800a46a7  jmp     loc_1800A4842
0x1800a46ac  mov     ebx, r12d
0x1800a46af  test    esi, esi
0x1800a46b1  jz      loc_1800A4838
0x1800a46b7  mov     [rsp+2B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800a46bc  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x1800a46c1  mov     [rsp+2B0h+lpcchClass], r12; lpcchClass
0x1800a46c6  mov     r8, rdi; lpName
0x1800a46c9  mov     [rsp+2B0h+lpClass], r12; lpClass
0x1800a46ce  mov     edx, ebx; dwIndex
0x1800a46d0  mov     rcx, r15; hKey
0x1800a46d3  mov     [rsp+2B0h+lpReserved], r12; lpReserved
0x1800a46d8  mov     [rsp+2B0h+cchName], r14d
0x1800a46dd  call    cs:__imp_RegEnumKeyExW
0x1800a46e3  test    eax, eax
0x1800a46e5  jnz     loc_1800A482E
0x1800a46eb  mov     r10d, 105h
0x1800a46f1  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Tracing"
0x1800a46f8  mov     edx, r10d
0x1800a46fb  lea     rax, [rsp+2B0h+pszDest]
0x1800a4700  mov     ecx, 7FFFFFFEh
0x1800a4705  test    rcx, rcx
0x1800a4708  jz      short loc_1800A4729
0x1800a470a  movzx   r9d, word ptr [r8]
0x1800a470e  test    r9w, r9w
0x1800a4712  jz      short loc_1800A4729
0x1800a4714  mov     [rax], r9w
0x1800a4718  add     r8, 2
0x1800a471c  add     rax, 2
0x1800a4720  dec     rcx
0x1800a4723  sub     rdx, 1
0x1800a4727  jnz     short loc_1800A4705
0x1800a4729  test    rdx, rdx
0x1800a472c  lea     rcx, [rax-2]
0x1800a4730  lea     r8, Source; "\\"
0x1800a4737  mov     rdx, r10; cchDest
0x1800a473a  cmovnz  rcx, rax
0x1800a473e  mov     [rcx], r12w
0x1800a4742  lea     rcx, [rsp+2B0h+pszDest]; pszDest
0x1800a4747  call    StringCchCatW
0x1800a474c  mov     r8, rdi; pszSrc
0x1800a474f  lea     rcx, [rsp+2B0h+pszDest]; pszDest
0x1800a4754  mov     edx, 105h; cchDest
0x1800a4759  call    StringCchCatW
0x1800a475e  lea     rax, [rsp+2B0h+phkResult]
0x1800a4763  mov     r9d, 2011Fh; samDesired
0x1800a4769  xor     r8d, r8d; ulOptions
0x1800a476c  mov     [rsp+2B0h+lpReserved], rax; phkResult
0x1800a4771  lea     rdx, [rsp+2B0h+pszDest]; lpSubKey
0x1800a4776  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a477d  call    cs:__imp_RegOpenKeyExW
0x1800a4783  test    eax, eax
0x1800a4785  jnz     loc_1800A482E
0x1800a478b  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x1800a4790  lea     rax, [rsp+2B0h+cbData]
0x1800a4795  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x1800a479a  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800a47a1  lea     rax, [rsp+2B0h+Data]
0x1800a47a6  mov     [rsp+2B0h+cbData], r13d
0x1800a47ab  xor     r9d, r9d; lpType
0x1800a47ae  mov     [rsp+2B0h+lpReserved], rax; lpData
0x1800a47b3  xor     r8d, r8d; lpReserved
0x1800a47b6  call    cs:__imp_RegQueryValueExW
0x1800a47bc  test    eax, eax
0x1800a47be  jnz     short loc_1800A4823
0x1800a47c0  cmp     dword ptr [rsp+2B0h+Data], 1
0x1800a47c5  jnz     short loc_1800A4823
0x1800a47c7  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x1800a47cc  lea     rax, [rsp+2B0h+Data]
0x1800a47d1  mov     dword ptr [rsp+2B0h+lpClass], r13d; cbData
0x1800a47d6  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800a47dd  mov     r9d, r13d; dwType
0x1800a47e0  mov     [rsp+2B0h+lpReserved], rax; lpData
0x1800a47e5  xor     r8d, r8d; Reserved
0x1800a47e8  mov     dword ptr [rsp+2B0h+var_258], r12d
0x1800a47ed  mov     dword ptr [rsp+2B0h+Data], r12d
0x1800a47f2  call    cs:__imp_RegSetValueExW
0x1800a47f8  test    eax, eax
0x1800a47fa  jnz     short loc_1800A4823
0x1800a47fc  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x1800a4801  lea     rax, [rsp+2B0h+var_258]
0x1800a4806  mov     dword ptr [rsp+2B0h+lpClass], r13d; cbData
0x1800a480b  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800a4812  mov     r9d, r13d; dwType
0x1800a4815  mov     [rsp+2B0h+lpReserved], rax; lpData
0x1800a481a  xor     r8d, r8d; Reserved
0x1800a481d  call    cs:__imp_RegSetValueExW
0x1800a4823  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x1800a4828  call    cs:__imp_RegCloseKey
0x1800a482e  inc     ebx
0x1800a4830  cmp     ebx, esi
0x1800a4832  jb      loc_1800A46B7
0x1800a4838  mov     rcx, rdi; lpMem
0x1800a483b  call    MprCommonFree
0x1800a4840  xor     eax, eax
0x1800a4842  mov     rcx, [rbp+1B0h+var_40]
0x1800a4849  xor     rcx, rsp; StackCookie
0x1800a484c  call    __security_check_cookie
0x1800a4851  mov     rbx, [rsp+2B0h+arg_0]
0x1800a4859  add     rsp, 280h
0x1800a4860  pop     r15
0x1800a4862  pop     r14
0x1800a4864  pop     r13
0x1800a4866  pop     r12
0x1800a4868  pop     rdi
0x1800a4869  pop     rsi
0x1800a486a  pop     rbp
0x1800a486b  retn
```
