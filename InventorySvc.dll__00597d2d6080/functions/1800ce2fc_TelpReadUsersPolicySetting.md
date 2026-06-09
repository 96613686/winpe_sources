# TelpReadUsersPolicySetting

- ea: `0x1800ce2fc`
- end: `0x1800ce5d9`
- name: `TelpReadUsersPolicySetting`
- size: `733`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800ce078`
- `0x1800ce224`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x18000ec54`
- `0x18000f698`
- `0x1800cd964`
- `0x1800cdb68`
- `0x1800ce2fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce46d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce561`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce46d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ce561`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ce47b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ce47b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ce56f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ce56f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ce4ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ce4ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ce44b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ce44b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce590`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ce590`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce3e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ce3e4`

## pseudocode

```c
__int64 __fastcall TelpReadUsersPolicySetting(_DWORD *a1, int *a2, const WCHAR *a3)
{
  DWORD v4; // r14d
  __int64 v5; // rbx
  WCHAR *LocalAllowTelemetryRegPath; // rax
  unsigned __int64 v7; // rdx
  WCHAR *v8; // r8
  WCHAR *v9; // rcx
  signed int v10; // ebx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  SIZE_T v13; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v15; // r15
  char v16; // r12
  int v17; // edi
  LSTATUS v18; // eax
  int v19; // eax
  HANDLE v20; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-A0h] BYREF
  int pvData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpValue; // [rsp+80h] [rbp-80h]
  int *v29; // [rsp+88h] [rbp-78h]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  lpValue = a3;
  v29 = a2;
  v4 = 0;
  *a1 = 1;
  hKey = 0;
  memset_0(SubKey, 0, 0x208u);
  v5 = 2147483646;
  LocalAllowTelemetryRegPath = (WCHAR *)TelGetLocalAllowTelemetryRegPath();
  v7 = 260;
  v8 = SubKey;
  do
  {
    if ( !v5 )
      break;
    if ( !*LocalAllowTelemetryRegPath )
      break;
    *v8++ = *LocalAllowTelemetryRegPath++;
    --v5;
    --v7;
  }
  while ( v7 );
  v9 = v8 - 1;
  v10 = v7 == 0 ? 0x8007007A : 0;
  if ( v7 )
    v9 = v8;
  *v9 = 0;
  if ( !v7 )
    goto LABEL_32;
  v10 = StringCchCatW(SubKey, v7, L"\\Users");
  if ( v10 < 0 )
    goto LABEL_32;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v10 = v11;
  if ( v11 > 0 )
    v10 = (unsigned __int16)v11 | 0x80070000;
  if ( v10 < 0 )
    goto LABEL_32;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v10 = v12;
  if ( v12 > 0 )
    v10 = (unsigned __int16)v12 | 0x80070000;
  if ( v10 >= 0 )
  {
    v13 = 2LL * (cbMaxSubKeyLen + 1);
    ProcessHeap = GetProcessHeap();
    v15 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v13);
    if ( v15 )
    {
      v16 = 0;
      v17 = 3;
      if ( !cSubKeys )
        goto LABEL_29;
      do
      {
        cchName = cbMaxSubKeyLen + 1;
        pvData = 0;
        v18 = RegEnumKeyExW(hKey, v4, v15, &cchName, 0, 0, 0, 0);
        v10 = v18;
        if ( v18 > 0 )
          v10 = (unsigned __int16)v18 | 0x80070000;
        if ( v10 != -2147024894 )
        {
          if ( v10 < 0 )
            goto LABEL_31;
          v19 = TelpReadRegistryDword(&pvData, hKey, v15, lpValue);
          v10 = v19;
          if ( v19 != -2147024894 )
          {
            if ( v19 < 0 )
              goto LABEL_31;
            v16 = 1;
            if ( pvData < v17 )
              v17 = pvData;
          }
        }
        ++v4;
      }
      while ( v4 < cSubKeys );
      if ( v16 )
        *v29 = v17;
      else
LABEL_29:
        *a1 = 0;
      v10 = 0;
LABEL_31:
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v15);
    }
    else
    {
      v10 = -2147024882;
    }
  }
  else
  {
LABEL_32:
    if ( v10 == -2147024894 )
    {
      v10 = 0;
      *a1 = 0;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v10 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E9,
      (unsigned int)"onecore\\base\\telemetry\\permission\\lib\\telemetrypermission.cpp",
      (const char *)(unsigned int)v10,
      phkResult);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800ce2fc  push    rbp
0x1800ce2fe  push    rbx
0x1800ce2ff  push    rdi
0x1800ce300  push    r12
0x1800ce302  push    r13
0x1800ce304  push    r14
0x1800ce306  push    r15
0x1800ce308  lea     rbp, [rsp-1B0h]
0x1800ce310  sub     rsp, 2B0h
0x1800ce317  mov     rax, cs:__security_cookie
0x1800ce31e  xor     rax, rsp
0x1800ce321  mov     [rbp+1E0h+var_40], rax
0x1800ce328  mov     [rbp+1E0h+lpValue], r8
0x1800ce32c  mov     r13, rcx
0x1800ce32f  mov     [rbp+1E0h+var_258], rdx
0x1800ce333  xor     r14d, r14d
0x1800ce336  mov     dword ptr [rcx], 1
0x1800ce33c  xor     edx, edx; Val
0x1800ce33e  mov     r8d, 208h; Size
0x1800ce344  mov     [rsp+2E0h+hKey], r14
0x1800ce349  lea     rcx, [rbp+1E0h+SubKey]; void *
0x1800ce34d  call    memset_0
0x1800ce352  mov     ebx, 7FFFFFFEh
0x1800ce357  call    TelGetLocalAllowTelemetryRegPath
0x1800ce35c  mov     edx, 104h
0x1800ce361  lea     r8, [rbp+1E0h+SubKey]
0x1800ce365  test    rbx, rbx
0x1800ce368  jz      short loc_1800CE387
0x1800ce36a  movzx   ecx, word ptr [rax]
0x1800ce36d  test    cx, cx
0x1800ce370  jz      short loc_1800CE387
0x1800ce372  mov     [r8], cx
0x1800ce376  add     rax, 2
0x1800ce37a  add     r8, 2
0x1800ce37e  dec     rbx
0x1800ce381  sub     rdx, 1; unsigned __int64
0x1800ce385  jnz     short loc_1800CE365
0x1800ce387  mov     rax, rdx
0x1800ce38a  lea     rcx, [r8-2]
0x1800ce38e  neg     rax
0x1800ce391  sbb     ebx, ebx
0x1800ce393  not     ebx
0x1800ce395  and     ebx, 8007007Ah
0x1800ce39b  test    rdx, rdx
0x1800ce39e  cmovnz  rcx, r8
0x1800ce3a2  mov     [rcx], r14w
0x1800ce3a6  jz      loc_1800CE577
0x1800ce3ac  lea     r8, aUsers; "\\Users"
0x1800ce3b3  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x1800ce3b7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ce3bc  mov     ebx, eax
0x1800ce3be  test    eax, eax
0x1800ce3c0  js      loc_1800CE577
0x1800ce3c6  lea     rax, [rsp+2E0h+hKey]
0x1800ce3cb  mov     r9d, 20019h; samDesired
0x1800ce3d1  xor     r8d, r8d; ulOptions
0x1800ce3d4  mov     [rsp+2E0h+phkResult], rax; phkResult
0x1800ce3d9  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x1800ce3dd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ce3e4  call    cs:__imp_RegOpenKeyExW
0x1800ce3ea  mov     ebx, eax
0x1800ce3ec  mov     edi, 80070000h
0x1800ce3f1  test    eax, eax
0x1800ce3f3  jle     short loc_1800CE3FA
0x1800ce3f5  movzx   ebx, ax
0x1800ce3f8  or      ebx, edi
0x1800ce3fa  test    ebx, ebx
0x1800ce3fc  js      loc_1800CE577
0x1800ce402  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ce407  lea     rax, [rsp+2E0h+cbMaxSubKeyLen]
0x1800ce40c  mov     [rsp+2E0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800ce411  xor     r9d, r9d; lpReserved
0x1800ce414  mov     [rsp+2E0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800ce419  xor     r8d, r8d; lpcchClass
0x1800ce41c  mov     [rsp+2E0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800ce421  xor     edx, edx; lpClass
0x1800ce423  mov     [rsp+2E0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800ce428  mov     [rsp+2E0h+lpcValues], r14; lpcValues
0x1800ce42d  mov     [rsp+2E0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800ce432  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800ce437  lea     rax, [rsp+2E0h+cSubKeys]
0x1800ce43c  mov     [rsp+2E0h+phkResult], rax; lpcSubKeys
0x1800ce441  mov     [rsp+2E0h+cSubKeys], r14d
0x1800ce446  mov     [rsp+2E0h+cbMaxSubKeyLen], r14d
0x1800ce44b  call    cs:__imp_RegQueryInfoKeyW
0x1800ce451  mov     ebx, eax
0x1800ce453  test    eax, eax
0x1800ce455  jle     short loc_1800CE45C
0x1800ce457  movzx   ebx, ax
0x1800ce45a  or      ebx, edi
0x1800ce45c  test    ebx, ebx
0x1800ce45e  js      loc_1800CE577
0x1800ce464  mov     ebx, [rsp+2E0h+cbMaxSubKeyLen]
0x1800ce468  inc     ebx
0x1800ce46a  add     rbx, rbx
0x1800ce46d  call    cs:__imp_GetProcessHeap
0x1800ce473  mov     r8, rbx; dwBytes
0x1800ce476  xor     edx, edx; dwFlags
0x1800ce478  mov     rcx, rax; hHeap
0x1800ce47b  call    cs:__imp_HeapAlloc
0x1800ce481  mov     r15, rax
0x1800ce484  test    rax, rax
0x1800ce487  jnz     short loc_1800CE493
0x1800ce489  mov     ebx, 8007000Eh
0x1800ce48e  jmp     loc_1800CE586
0x1800ce493  mov     r12b, r14b
0x1800ce496  mov     edi, 3
0x1800ce49b  cmp     [rsp+2E0h+cSubKeys], r14d
0x1800ce4a0  jbe     loc_1800CE55A
0x1800ce4a6  mov     eax, [rsp+2E0h+cbMaxSubKeyLen]
0x1800ce4aa  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1800ce4af  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ce4b4  inc     eax
0x1800ce4b6  mov     [rsp+2E0h+lpcValues], 0; lpftLastWriteTime
0x1800ce4bf  mov     r8, r15; lpName
0x1800ce4c2  mov     [rsp+2E0h+lpcbMaxClassLen], 0; lpcchClass
0x1800ce4cb  mov     edx, r14d; dwIndex
0x1800ce4ce  mov     [rsp+2E0h+lpcbMaxSubKeyLen], 0; lpClass
0x1800ce4d7  mov     [rsp+2E0h+cchName], eax
0x1800ce4db  mov     [rsp+2E0h+pvData], 0
0x1800ce4e3  mov     [rsp+2E0h+phkResult], 0; lpReserved
0x1800ce4ec  call    cs:__imp_RegEnumKeyExW
0x1800ce4f2  mov     ebx, eax
0x1800ce4f4  test    eax, eax
0x1800ce4f6  jle     short loc_1800CE501
0x1800ce4f8  movzx   ebx, ax
0x1800ce4fb  or      ebx, 80070000h
0x1800ce501  cmp     ebx, 80070002h
0x1800ce507  jz      short loc_1800CE53C
0x1800ce509  test    ebx, ebx
0x1800ce50b  js      short loc_1800CE561
0x1800ce50d  mov     r9, [rbp+1E0h+lpValue]; lpValue
0x1800ce511  lea     rcx, [rsp+2E0h+pvData]; pvData
0x1800ce516  mov     rdx, [rsp+2E0h+hKey]; hkey
0x1800ce51b  mov     r8, r15; lpSubKey
0x1800ce51e  call    TelpReadRegistryDword
0x1800ce523  mov     ebx, eax
0x1800ce525  cmp     eax, 80070002h
0x1800ce52a  jz      short loc_1800CE53C
0x1800ce52c  test    eax, eax
0x1800ce52e  js      short loc_1800CE561
0x1800ce530  cmp     [rsp+2E0h+pvData], edi
0x1800ce534  mov     r12b, 1
0x1800ce537  cmovl   edi, [rsp+2E0h+pvData]
0x1800ce53c  inc     r14d
0x1800ce53f  cmp     r14d, [rsp+2E0h+cSubKeys]
0x1800ce544  jb      loc_1800CE4A6
0x1800ce54a  xor     r14d, r14d
0x1800ce54d  test    r12b, r12b
0x1800ce550  jz      short loc_1800CE55A
0x1800ce552  mov     rax, [rbp+1E0h+var_258]
0x1800ce556  mov     [rax], edi
0x1800ce558  jmp     short loc_1800CE55E
0x1800ce55a  mov     [r13+0], r14d
0x1800ce55e  mov     ebx, r14d
0x1800ce561  call    cs:__imp_GetProcessHeap
0x1800ce567  mov     r8, r15; lpMem
0x1800ce56a  xor     edx, edx; dwFlags
0x1800ce56c  mov     rcx, rax; hHeap
0x1800ce56f  call    cs:__imp_HeapFree
0x1800ce575  jmp     short loc_1800CE586
0x1800ce577  cmp     ebx, 80070002h
0x1800ce57d  jnz     short loc_1800CE586
0x1800ce57f  mov     ebx, r14d
0x1800ce582  mov     [r13+0], r14d
0x1800ce586  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800ce58b  test    rcx, rcx
0x1800ce58e  jz      short loc_1800CE596
0x1800ce590  call    cs:__imp_RegCloseKey
0x1800ce596  test    ebx, ebx
0x1800ce598  jns     short loc_1800CE5B5
0x1800ce59a  mov     rcx, [rbp+1E8h]; this
0x1800ce5a1  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\permission\\l"...
0x1800ce5a8  mov     r9d, ebx; char *
0x1800ce5ab  mov     edx, 4E9h; void *
0x1800ce5b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce5b5  mov     eax, ebx
0x1800ce5b7  mov     rcx, [rbp+1E0h+var_40]
0x1800ce5be  xor     rcx, rsp; StackCookie
0x1800ce5c1  call    __security_check_cookie
0x1800ce5c6  add     rsp, 2B0h
0x1800ce5cd  pop     r15
0x1800ce5cf  pop     r14
0x1800ce5d1  pop     r13
0x1800ce5d3  pop     r12
0x1800ce5d5  pop     rdi
0x1800ce5d6  pop     rbx
0x1800ce5d7  pop     rbp
0x1800ce5d8  retn
```
