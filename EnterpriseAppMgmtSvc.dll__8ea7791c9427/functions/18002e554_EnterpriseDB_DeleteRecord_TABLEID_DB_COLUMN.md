# EnterpriseDB::DeleteRecord(TABLEID,DB_COLUMN)

- ea: `0x18002e554`
- end: `0x18002e71e`
- name: `?DeleteRecord@EnterpriseDB@@QEAAJW4TABLEID@@UDB_COLUMN@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800199e4`

## callees

- `0x180006858`
- `0x18002e554`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e60f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002e60f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e63a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e63a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e64d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e64d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e6e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e6e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e5ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e5ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e674`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e674`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e645`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e6f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e645`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e6f2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002e686`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002e686`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002e699`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002e699`

## string_xrefs

- `0x18002e6cb`: `Delete Record Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseDB::DeleteRecord(__int64 a1, int a2, __int64 a3)
{
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // r14
  __int64 v7; // rcx
  unsigned int v8; // ebx
  LPCWSTR *v9; // rax
  HKEY v10; // rdi
  LSTATUS v11; // eax
  bool v12; // cc
  HKEY hKey[2]; // [rsp+30h] [rbp-49h] BYREF
  char v15; // [rsp+40h] [rbp-39h]
  GUID rguid; // [rsp+48h] [rbp-31h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-19h] BYREF

  v4 = a2;
  hKey[0] = 0;
  memset_0(sz, 0, sizeof(sz));
  rguid = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  hKey[1] = (HKEY)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v15 = 1;
  if ( !*(_DWORD *)a1 )
    goto LABEL_2;
  if ( (unsigned int)v4 > 1 || (v7 = 3 * v4, (v9 = &(&g_TableInfo)[3 * v4]) == 0) || *(_WORD *)a3 != *((_WORD *)v9 + 6) )
  {
    v8 = -2147024809;
LABEL_20:
    if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x100) != 0 )
      McTemplateU0zq_EventWriteTransfer(v7, EnterpriseAppDBError, L"Delete Record Failed", v8);
    goto LABEL_22;
  }
  rguid = *(GUID *)*(_QWORD *)(a3 + 8);
  if ( !StringFromGUID2(&rguid, sz, 40) || (!(_DWORD)v4 ? (v10 = *(HKEY *)(a1 + 8)) : (v10 = *(HKEY *)(a1 + 16)), !v10) )
  {
LABEL_2:
    v8 = -2147467259;
    goto LABEL_20;
  }
  hKey[0] = 0;
  v11 = RegOpenKeyExW(v10, sz, 0, 0xF003Fu, hKey);
  v8 = v11;
  v12 = v11 <= 0;
  if ( !v11 )
  {
    v11 = RegDeleteTreeW(hKey[0], 0);
    v8 = v11;
    v12 = v11 <= 0;
    if ( !v11 )
    {
      v11 = RegDeleteKeyW(v10, sz);
      v8 = v11;
      v12 = v11 <= 0;
      if ( !v11 )
      {
        v8 = 0;
        goto LABEL_22;
      }
    }
  }
  if ( !v12 )
    v8 = (unsigned __int16)v11 | 0x80070000;
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_20;
LABEL_22:
  LeaveCriticalSection(v6);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v8;
}

```

## disassembly

```asm
0x18002e554  mov     [rsp-8+arg_8], rbx
0x18002e559  mov     [rsp-8+arg_18], rsi
0x18002e55e  push    rbp
0x18002e55f  push    rdi
0x18002e560  push    r14
0x18002e562  lea     rbp, [rsp-47h]
0x18002e567  sub     rsp, 0C0h
0x18002e56e  mov     rax, cs:__security_cookie
0x18002e575  xor     rax, rsp
0x18002e578  mov     [rbp+57h+var_20], rax
0x18002e57c  mov     rsi, r8
0x18002e57f  movsxd  rbx, edx
0x18002e582  mov     rdi, rcx
0x18002e585  mov     [rbp+57h+hKey], 0
0x18002e58d  xor     edx, edx; Val
0x18002e58f  lea     r8d, [rdx+50h]; Size
0x18002e593  lea     rcx, [rbp+57h+sz]; void *
0x18002e597  call    memset_0
0x18002e59c  xorps   xmm0, xmm0
0x18002e59f  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x18002e5a3  lea     r14, [rdi+18h]
0x18002e5a7  mov     [rbp+57h+var_98], r14
0x18002e5ab  mov     rcx, r14; lpCriticalSection
0x18002e5ae  call    cs:__imp_EnterCriticalSection
0x18002e5b4  mov     [rbp+57h+var_90], 1
0x18002e5b8  cmp     dword ptr [rdi], 0
0x18002e5bb  jnz     short loc_18002E5C7
0x18002e5bd  mov     ebx, 80004005h
0x18002e5c2  jmp     loc_18002E6BF
0x18002e5c7  cmp     ebx, 1
0x18002e5ca  ja      loc_18002E6BA
0x18002e5d0  lea     rcx, [rbx+rbx*2]
0x18002e5d4  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x18002e5db  lea     rax, [rax+rcx*8]
0x18002e5df  test    rax, rax
0x18002e5e2  jz      loc_18002E6BA
0x18002e5e8  movzx   eax, word ptr [rax+0Ch]
0x18002e5ec  cmp     [rsi], ax
0x18002e5ef  jnz     loc_18002E6BA
0x18002e5f5  mov     rax, [rsi+8]
0x18002e5f9  movups  xmm0, xmmword ptr [rax]
0x18002e5fc  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x18002e601  mov     r8d, 28h ; '('; cchMax
0x18002e607  lea     rdx, [rbp+57h+sz]; lpsz
0x18002e60b  lea     rcx, [rbp+57h+rguid]; rguid
0x18002e60f  call    cs:__imp_StringFromGUID2
0x18002e615  test    eax, eax
0x18002e617  jz      short loc_18002E5BD
0x18002e619  test    ebx, ebx
0x18002e61b  jz      short loc_18002E628
0x18002e61d  cmp     ebx, 1
0x18002e620  jnz     short loc_18002E5BD
0x18002e622  mov     rdi, [rdi+10h]
0x18002e626  jmp     short loc_18002E62C
0x18002e628  mov     rdi, [rdi+8]
0x18002e62c  test    rdi, rdi
0x18002e62f  jz      short loc_18002E5BD
0x18002e631  mov     rsi, [rbp+57h+hKey]
0x18002e635  test    rsi, rsi
0x18002e638  jz      short loc_18002E653
0x18002e63a  call    cs:__imp_GetLastError
0x18002e640  mov     ebx, eax
0x18002e642  mov     rcx, rsi; hKey
0x18002e645  call    cs:__imp_RegCloseKey
0x18002e64b  mov     ecx, ebx; dwErrCode
0x18002e64d  call    cs:__imp_SetLastError
0x18002e653  mov     [rbp+57h+hKey], 0
0x18002e65b  lea     rax, [rbp+57h+hKey]
0x18002e65f  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18002e664  mov     r9d, 0F003Fh; samDesired
0x18002e66a  xor     r8d, r8d; ulOptions
0x18002e66d  lea     rdx, [rbp+57h+sz]; lpSubKey
0x18002e671  mov     rcx, rdi; hKey
0x18002e674  call    cs:__imp_RegOpenKeyExW
0x18002e67a  mov     ebx, eax
0x18002e67c  test    eax, eax
0x18002e67e  jnz     short loc_18002E6A5
0x18002e680  xor     edx, edx; lpSubKey
0x18002e682  mov     rcx, [rbp+57h+hKey]; hKey
0x18002e686  call    cs:__imp_RegDeleteTreeW
0x18002e68c  mov     ebx, eax
0x18002e68e  test    eax, eax
0x18002e690  jnz     short loc_18002E6A5
0x18002e692  lea     rdx, [rbp+57h+sz]; lpSubKey
0x18002e696  mov     rcx, rdi; hKey
0x18002e699  call    cs:__imp_RegDeleteKeyW
0x18002e69f  mov     ebx, eax
0x18002e6a1  test    eax, eax
0x18002e6a3  jz      short loc_18002E6B6
0x18002e6a5  jle     short loc_18002E6B0
0x18002e6a7  movzx   ebx, ax
0x18002e6aa  or      ebx, 80070000h
0x18002e6b0  test    ebx, ebx
0x18002e6b2  jns     short loc_18002E6DF
0x18002e6b4  jmp     short loc_18002E6BF
0x18002e6b6  xor     ebx, ebx
0x18002e6b8  jmp     short loc_18002E6DF
0x18002e6ba  mov     ebx, 80070057h
0x18002e6bf  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x18002e6c6  jz      short loc_18002E6DF
0x18002e6c8  mov     r9d, ebx
0x18002e6cb  lea     r8, aDeleteRecordFa; "Delete Record Failed"
0x18002e6d2  lea     rdx, EnterpriseAppDBError
0x18002e6d9  call    McTemplateU0zq_EventWriteTransfer
0x18002e6de  nop
0x18002e6df  mov     rcx, r14; lpCriticalSection
0x18002e6e2  call    cs:__imp_LeaveCriticalSection
0x18002e6e8  nop
0x18002e6e9  mov     rcx, [rbp+57h+hKey]; hKey
0x18002e6ed  test    rcx, rcx
0x18002e6f0  jz      short loc_18002E6F8
0x18002e6f2  call    cs:__imp_RegCloseKey
0x18002e6f8  mov     eax, ebx
0x18002e6fa  mov     rcx, [rbp+57h+var_20]
0x18002e6fe  xor     rcx, rsp; StackCookie
0x18002e701  call    __security_check_cookie
0x18002e706  lea     r11, [rsp+0D0h+var_10]
0x18002e70e  mov     rbx, [r11+28h]
0x18002e712  mov     rsi, [r11+38h]
0x18002e716  mov     rsp, r11
0x18002e719  pop     r14
0x18002e71b  pop     rdi
0x18002e71c  pop     rbp
0x18002e71d  retn
```
