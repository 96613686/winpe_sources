# EnterpriseDB::EnumeratePrimaryKeys(TABLEID,_GUID * *,ulong &)

- ea: `0x18002e724`
- end: `0x18002e979`
- name: `?EnumeratePrimaryKeys@EnterpriseDB@@QEAAJW4TABLEID@@PEAPEAU_GUID@@AEAK@Z`
- size: `597`
- prototype: `__int64 __fastcall(__int64, int, GUID **, DWORD *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a298`
- `0x18001a374`
- `0x18001a3d4`
- `0x18001a52c`
- `0x18001c0dc`

## callees

- `0x180002f70`
- `0x180006858`
- `0x18002e724`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002e8f5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002e8f5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002e8cd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002e8cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e94a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e94a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e782`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e782`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002e8b4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002e8b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002e829`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002e829`

## pseudocode

```c
__int64 __fastcall EnterpriseDB::EnumeratePrimaryKeys(__int64 a1, int a2, GUID **a3, DWORD *a4)
{
  __int64 v6; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // r12
  __int64 v9; // rcx
  HKEY v10; // rdi
  LSTATUS v11; // eax
  int v12; // ebx
  unsigned __int64 v13; // rax
  GUID *v14; // r14
  DWORD v15; // esi
  DWORD v16; // eax
  LSTATUS v17; // eax
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-59h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-55h] BYREF
  __int64 v21; // [rsp+68h] [rbp-51h]
  char v22; // [rsp+70h] [rbp-49h]
  WCHAR Name[40]; // [rsp+80h] [rbp-39h] BYREF

  v6 = a2;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  memset_0(Name, 0, sizeof(Name));
  v8 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  v21 = a1 + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v22 = 1;
  if ( a3 && (unsigned int)v6 <= 1 && (v9 = 3 * v6, &(&g_TableInfo)[3 * v6]) )
  {
    if ( (_DWORD)v6 )
      v10 = *(HKEY *)(a1 + 16);
    else
      v10 = *(HKEY *)(a1 + 8);
    if ( v10 )
    {
      v11 = RegQueryInfoKeyW(v10, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      v12 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v12 = (unsigned __int16)v11 | 0x80070000;
LABEL_25:
        if ( v12 >= 0 )
          goto LABEL_31;
        goto LABEL_29;
      }
      if ( cbMaxSubKeyLen < 0x28 )
      {
        if ( !cSubKeys )
          goto LABEL_31;
        v13 = 16LL * cSubKeys;
        if ( !is_mul_ok(cSubKeys, 0x10u) )
          v13 = -1;
        v14 = (GUID *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
        v15 = 0;
        v16 = cSubKeys;
        if ( cSubKeys )
        {
          while ( 1 )
          {
            cbMaxSubKeyLen = 40;
            v17 = RegEnumKeyExW(v10, v15, Name, &cbMaxSubKeyLen, 0, 0, 0, 0);
            v12 = v17;
            if ( v17 )
              break;
            v12 = CLSIDFromString(Name, &v14[v15]);
            if ( v12 < 0 )
              goto LABEL_18;
            ++v15;
            v16 = cSubKeys;
            if ( v15 >= cSubKeys )
              goto LABEL_17;
          }
          if ( v17 > 0 )
            v12 = (unsigned __int16)v17 | 0x80070000;
        }
        else
        {
LABEL_17:
          *a3 = v14;
          *a4 = v16;
        }
LABEL_18:
        if ( v14 )
        {
          if ( v12 >= 0 )
            goto LABEL_31;
          operator delete[](v14);
          goto LABEL_29;
        }
        goto LABEL_25;
      }
    }
    v12 = -2147467259;
  }
  else
  {
    v12 = -2147024809;
  }
LABEL_29:
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x100) != 0 )
    McTemplateU0zq_EventWriteTransfer(v9, EnterpriseAppDBError, L"Enumerate Keys Failed", (unsigned int)v12);
LABEL_31:
  LeaveCriticalSection(v8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18002e724  mov     [rsp-8+arg_8], rbx
0x18002e729  push    rbp
0x18002e72a  push    rsi
0x18002e72b  push    rdi
0x18002e72c  push    r12
0x18002e72e  push    r13
0x18002e730  push    r14
0x18002e732  push    r15
0x18002e734  lea     rbp, [rsp-27h]
0x18002e739  sub     rsp, 0E0h
0x18002e740  mov     rax, cs:__security_cookie
0x18002e747  xor     rax, rsp
0x18002e74a  mov     [rbp+57h+var_40], rax
0x18002e74e  mov     r13, r9
0x18002e751  mov     r15, r8
0x18002e754  movsxd  rbx, edx
0x18002e757  mov     rdi, rcx
0x18002e75a  mov     [rbp+57h+cSubKeys], 0
0x18002e761  mov     [rbp+57h+cbMaxSubKeyLen], 0
0x18002e768  xor     edx, edx; Val
0x18002e76a  lea     r8d, [rdx+50h]; Size
0x18002e76e  lea     rcx, [rbp+57h+Name]; void *
0x18002e772  call    memset_0
0x18002e777  lea     r12, [rdi+18h]
0x18002e77b  mov     [rbp+57h+var_A8], r12
0x18002e77f  mov     rcx, r12; lpCriticalSection
0x18002e782  call    cs:__imp_EnterCriticalSection
0x18002e788  mov     [rbp+57h+var_A0], 1
0x18002e78c  test    r15, r15
0x18002e78f  jz      loc_18002E922
0x18002e795  cmp     ebx, 1
0x18002e798  ja      loc_18002E922
0x18002e79e  lea     rcx, [rbx+rbx*2]
0x18002e7a2  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x18002e7a9  lea     rax, [rax+rcx*8]
0x18002e7ad  test    rax, rax
0x18002e7b0  jz      loc_18002E922
0x18002e7b6  test    ebx, ebx
0x18002e7b8  jz      short loc_18002E7C9
0x18002e7ba  cmp     ebx, 1
0x18002e7bd  jnz     loc_18002E91B
0x18002e7c3  mov     rdi, [rdi+10h]
0x18002e7c7  jmp     short loc_18002E7CD
0x18002e7c9  mov     rdi, [rdi+8]
0x18002e7cd  test    rdi, rdi
0x18002e7d0  jz      loc_18002E91B
0x18002e7d6  mov     [rsp+110h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18002e7df  mov     [rsp+110h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18002e7e8  mov     [rsp+110h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18002e7f1  mov     [rsp+110h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18002e7fa  mov     [rsp+110h+lpcValues], 0; lpcValues
0x18002e803  mov     [rsp+110h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18002e80c  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18002e810  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18002e815  lea     rax, [rbp+57h+cSubKeys]
0x18002e819  mov     [rsp+110h+lpcSubKeys], rax; lpcSubKeys
0x18002e81e  xor     r9d, r9d; lpReserved
0x18002e821  xor     r8d, r8d; lpcchClass
0x18002e824  xor     edx, edx; lpClass
0x18002e826  mov     rcx, rdi; hKey
0x18002e829  call    cs:__imp_RegQueryInfoKeyW
0x18002e82f  mov     ebx, eax
0x18002e831  test    eax, eax
0x18002e833  jnz     loc_18002E90A
0x18002e839  cmp     [rbp+57h+cbMaxSubKeyLen], 28h ; '('
0x18002e83d  jnb     loc_18002E91B
0x18002e843  mov     eax, [rbp+57h+cSubKeys]
0x18002e846  test    eax, eax
0x18002e848  jz      loc_18002E947
0x18002e84e  mov     ecx, eax
0x18002e850  lea     eax, [rbx+10h]
0x18002e853  mul     rcx
0x18002e856  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002e85d  cmovb   rax, rcx
0x18002e861  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e868  mov     rcx, rax; unsigned __int64
0x18002e86b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002e870  mov     r14, rax
0x18002e873  xor     esi, esi
0x18002e875  mov     eax, [rbp+57h+cSubKeys]
0x18002e878  test    eax, eax
0x18002e87a  jz      short loc_18002E8E2
0x18002e87c  mov     [rbp+57h+cbMaxSubKeyLen], 28h ; '('
0x18002e883  mov     [rsp+110h+lpcValues], 0; lpftLastWriteTime
0x18002e88c  mov     [rsp+110h+lpcbMaxClassLen], 0; lpcchClass
0x18002e895  mov     [rsp+110h+lpcbMaxSubKeyLen], 0; lpClass
0x18002e89e  mov     [rsp+110h+lpcSubKeys], 0; lpReserved
0x18002e8a7  lea     r9, [rbp+57h+cbMaxSubKeyLen]; lpcchName
0x18002e8ab  lea     r8, [rbp+57h+Name]; lpName
0x18002e8af  mov     edx, esi; dwIndex
0x18002e8b1  mov     rcx, rdi; hKey
0x18002e8b4  call    cs:__imp_RegEnumKeyExW
0x18002e8ba  mov     ebx, eax
0x18002e8bc  test    eax, eax
0x18002e8be  jnz     short loc_18002E8FD
0x18002e8c0  mov     edx, esi
0x18002e8c2  shl     rdx, 4
0x18002e8c6  add     rdx, r14; pclsid
0x18002e8c9  lea     rcx, [rbp+57h+Name]; lpsz
0x18002e8cd  call    cs:__imp_CLSIDFromString
0x18002e8d3  mov     ebx, eax
0x18002e8d5  test    eax, eax
0x18002e8d7  js      short loc_18002E8E9
0x18002e8d9  inc     esi
0x18002e8db  mov     eax, [rbp+57h+cSubKeys]
0x18002e8de  cmp     esi, eax
0x18002e8e0  jb      short loc_18002E87C
0x18002e8e2  mov     [r15], r14
0x18002e8e5  mov     [r13+0], eax
0x18002e8e9  test    r14, r14
0x18002e8ec  jz      short loc_18002E915
0x18002e8ee  test    ebx, ebx
0x18002e8f0  jns     short loc_18002E947
0x18002e8f2  mov     rcx, r14
0x18002e8f5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002e8fb  jmp     short loc_18002E927
0x18002e8fd  jle     short loc_18002E8E9
0x18002e8ff  movzx   ebx, ax
0x18002e902  or      ebx, 80070000h
0x18002e908  jmp     short loc_18002E8E9
0x18002e90a  jle     short loc_18002E915
0x18002e90c  movzx   ebx, ax
0x18002e90f  or      ebx, 80070000h
0x18002e915  test    ebx, ebx
0x18002e917  jns     short loc_18002E947
0x18002e919  jmp     short loc_18002E927
0x18002e91b  mov     ebx, 80004005h
0x18002e920  jmp     short loc_18002E927
0x18002e922  mov     ebx, 80070057h
0x18002e927  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x18002e92e  jz      short loc_18002E947
0x18002e930  mov     r9d, ebx
0x18002e933  lea     r8, aEnumerateKeysF; "Enumerate Keys Failed"
0x18002e93a  lea     rdx, EnterpriseAppDBError
0x18002e941  call    McTemplateU0zq_EventWriteTransfer
0x18002e946  nop
0x18002e947  mov     rcx, r12; lpCriticalSection
0x18002e94a  call    cs:__imp_LeaveCriticalSection
0x18002e950  mov     eax, ebx
0x18002e952  mov     rcx, [rbp+57h+var_40]
0x18002e956  xor     rcx, rsp; StackCookie
0x18002e959  call    __security_check_cookie
0x18002e95e  mov     rbx, [rsp+110h+arg_8]
0x18002e966  add     rsp, 0E0h
0x18002e96d  pop     r15
0x18002e96f  pop     r14
0x18002e971  pop     r13
0x18002e973  pop     r12
0x18002e975  pop     rdi
0x18002e976  pop     rsi
0x18002e977  pop     rbp
0x18002e978  retn
```
