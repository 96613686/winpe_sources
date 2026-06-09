# EnterpriseDB::InsertRecord(TABLEID,DB_COLUMN *,ushort)

- ea: `0x18002eb84`
- end: `0x18002ee1c`
- name: `?InsertRecord@EnterpriseDB@@QEAAJW4TABLEID@@PEAUDB_COLUMN@@G@Z`
- size: `664`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013400`
- `0x180019608`
- `0x18001a704`

## callees

- `0x180006858`
- `0x18002eb84`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002ec92`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002ec92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ecdc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ecdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002eddd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ebe7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ebe7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ed17`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002ed17`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ed65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ed65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ecd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eded`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ecd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002eded`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002ed9f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002ed9f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002edac`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002edac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseDB::InsertRecord(__int64 a1, int a2, __int64 a3, unsigned __int16 a4)
{
  unsigned int v4; // esi
  __int64 v6; // rbx
  int v8; // r14d
  __int64 v9; // rcx
  unsigned int v10; // ebx
  LPCWSTR *v11; // rax
  LPCWSTR v12; // r12
  int v13; // r15d
  __int64 v14; // rdx
  unsigned int i; // r8d
  HKEY v16; // rdi
  LSTATUS v17; // eax
  int v18; // esi
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-61h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-59h]
  char v23; // [rsp+68h] [rbp-51h]
  GUID rguid; // [rsp+70h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-39h] BYREF

  v4 = a4;
  v6 = a2;
  v8 = 0;
  hKey = 0;
  dwDisposition = 0;
  memset_0(sz, 0, sizeof(sz));
  rguid = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v23 = 1;
  if ( !a3 )
    goto LABEL_32;
  if ( !*(_DWORD *)a1 )
  {
LABEL_3:
    v10 = -2147467259;
    goto LABEL_33;
  }
  if ( (unsigned int)v6 > 1 )
    goto LABEL_32;
  v9 = 3 * v6;
  v11 = &(&g_TableInfo)[3 * v6];
  if ( !v11 )
    goto LABEL_32;
  v12 = v11[2];
  if ( !v12 )
    goto LABEL_32;
  v13 = v4;
  if ( !v4 )
    goto LABEL_32;
  v14 = 0;
  for ( i = 0; i < v4; ++i )
  {
    v9 = 3LL * i;
    if ( *(_WORD *)(a3 + 24LL * i) == *((_WORD *)v11 + 6) )
      v14 = a3 + 24LL * i;
  }
  if ( !v14 )
  {
LABEL_32:
    v10 = -2147024809;
    goto LABEL_33;
  }
  rguid = *(GUID *)*(_QWORD *)(v14 + 8);
  if ( !StringFromGUID2(&rguid, sz, 40) )
    goto LABEL_3;
  v16 = (_DWORD)v6 ? *(HKEY *)(a1 + 16) : *(HKEY *)(a1 + 8);
  if ( !v16 )
    goto LABEL_3;
  hKey = 0;
  v17 = RegCreateKeyExW(v16, sz, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  v10 = v17;
  if ( v17 )
  {
    if ( v17 <= 0 )
      goto LABEL_29;
LABEL_28:
    v10 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_29;
  }
  if ( dwDisposition != 1 )
  {
    v10 = -2147024713;
    goto LABEL_33;
  }
  v10 = 0;
  v18 = 0;
  v8 = 1;
  while ( 1 )
  {
    v17 = RegSetValueExW(
            hKey,
            *(LPCWSTR *)&v12[8 * *(unsigned __int16 *)(a3 + 24LL * v18)],
            0,
            *(_DWORD *)&v12[8 * *(unsigned __int16 *)(a3 + 24LL * v18) + 4],
            *(const BYTE **)(a3 + 24LL * v18 + 8),
            *(_DWORD *)(a3 + 24LL * v18 + 16));
    if ( v17 )
      break;
    if ( ++v18 >= v13 )
      goto LABEL_35;
  }
  if ( v17 > 0 )
    goto LABEL_28;
  v10 = v17;
LABEL_29:
  if ( (v10 & 0x80000000) == 0 )
    goto LABEL_35;
  if ( v8 )
  {
    RegDeleteTreeW(hKey, 0);
    RegDeleteKeyW(v16, sz);
  }
LABEL_33:
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x100) != 0 )
    McTemplateU0zq_EventWriteTransfer(v9, EnterpriseAppDBError, L"Insert Record Failed", v10);
LABEL_35:
  LeaveCriticalSection(lpCriticalSection);
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x18002eb84  mov     [rsp-8+arg_18], rbx
0x18002eb89  push    rbp
0x18002eb8a  push    rsi
0x18002eb8b  push    rdi
0x18002eb8c  push    r12
0x18002eb8e  push    r13
0x18002eb90  push    r14
0x18002eb92  push    r15
0x18002eb94  lea     rbp, [rsp-27h]
0x18002eb99  sub     rsp, 0E0h
0x18002eba0  mov     rax, cs:__security_cookie
0x18002eba7  xor     rax, rsp
0x18002ebaa  mov     [rbp+57h+var_40], rax
0x18002ebae  movzx   esi, r9w
0x18002ebb2  mov     r13, r8
0x18002ebb5  movsxd  rbx, edx
0x18002ebb8  mov     rdi, rcx
0x18002ebbb  xor     r14d, r14d
0x18002ebbe  mov     [rbp+57h+hKey], r14
0x18002ebc2  mov     [rbp+57h+dwDisposition], r14d
0x18002ebc6  xor     edx, edx; Val
0x18002ebc8  lea     r8d, [r14+50h]; Size
0x18002ebcc  lea     rcx, [rbp+57h+sz]; void *
0x18002ebd0  call    memset_0
0x18002ebd5  xorps   xmm0, xmm0
0x18002ebd8  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x18002ebdc  lea     rax, [rdi+18h]
0x18002ebe0  mov     [rbp+57h+lpCriticalSection], rax
0x18002ebe4  mov     rcx, rax; lpCriticalSection
0x18002ebe7  call    cs:__imp_EnterCriticalSection
0x18002ebed  mov     [rbp+57h+var_A8], 1
0x18002ebf1  test    r13, r13
0x18002ebf4  jz      loc_18002EDB4
0x18002ebfa  cmp     [rdi], r14d
0x18002ebfd  jnz     short loc_18002EC09
0x18002ebff  mov     ebx, 80004005h
0x18002ec04  jmp     loc_18002EDB9
0x18002ec09  cmp     ebx, 1
0x18002ec0c  ja      loc_18002EDB4
0x18002ec12  lea     rcx, [rbx+rbx*2]
0x18002ec16  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x18002ec1d  lea     rax, [rax+rcx*8]
0x18002ec21  test    rax, rax
0x18002ec24  jz      loc_18002EDB4
0x18002ec2a  mov     r12, [rax+10h]
0x18002ec2e  test    r12, r12
0x18002ec31  jz      loc_18002EDB4
0x18002ec37  mov     r15d, esi
0x18002ec3a  test    esi, esi
0x18002ec3c  jz      loc_18002EDB4
0x18002ec42  mov     rdx, r14
0x18002ec45  mov     r8d, r14d
0x18002ec48  movzx   r9d, word ptr [rax+0Ch]
0x18002ec4d  mov     eax, r8d
0x18002ec50  lea     rcx, [rax+rax*2]
0x18002ec54  lea     rax, ds:0[rcx*8]
0x18002ec5c  add     rax, r13
0x18002ec5f  cmp     [rax], r9w
0x18002ec63  cmovz   rdx, rax
0x18002ec67  inc     r8d
0x18002ec6a  cmp     r8d, r15d
0x18002ec6d  jb      short loc_18002EC4D
0x18002ec6f  test    rdx, rdx
0x18002ec72  jz      loc_18002EDB4
0x18002ec78  mov     rax, [rdx+8]
0x18002ec7c  movups  xmm0, xmmword ptr [rax]
0x18002ec7f  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x18002ec84  mov     r8d, 28h ; '('; cchMax
0x18002ec8a  lea     rdx, [rbp+57h+sz]; lpsz
0x18002ec8e  lea     rcx, [rbp+57h+rguid]; rguid
0x18002ec92  call    cs:__imp_StringFromGUID2
0x18002ec98  test    eax, eax
0x18002ec9a  jz      loc_18002EBFF
0x18002eca0  test    ebx, ebx
0x18002eca2  jz      short loc_18002ECB3
0x18002eca4  cmp     ebx, 1
0x18002eca7  jnz     loc_18002EBFF
0x18002ecad  mov     rdi, [rdi+10h]
0x18002ecb1  jmp     short loc_18002ECB7
0x18002ecb3  mov     rdi, [rdi+8]
0x18002ecb7  test    rdi, rdi
0x18002ecba  jz      loc_18002EBFF
0x18002ecc0  mov     rsi, [rbp+57h+hKey]
0x18002ecc4  test    rsi, rsi
0x18002ecc7  jz      short loc_18002ECE2
0x18002ecc9  call    cs:__imp_GetLastError
0x18002eccf  mov     ebx, eax
0x18002ecd1  mov     rcx, rsi; hKey
0x18002ecd4  call    cs:__imp_RegCloseKey
0x18002ecda  mov     ecx, ebx; dwErrCode
0x18002ecdc  call    cs:__imp_SetLastError
0x18002ece2  mov     [rbp+57h+hKey], r14
0x18002ece6  lea     rax, [rbp+57h+dwDisposition]
0x18002ecea  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x18002ecef  lea     rax, [rbp+57h+hKey]
0x18002ecf3  mov     [rsp+110h+phkResult], rax; phkResult
0x18002ecf8  mov     [rsp+110h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18002ecfd  mov     [rsp+110h+samDesired], 0F003Fh; samDesired
0x18002ed05  mov     [rsp+110h+dwOptions], r14d; dwOptions
0x18002ed0a  xor     r9d, r9d; lpClass
0x18002ed0d  xor     r8d, r8d; Reserved
0x18002ed10  lea     rdx, [rbp+57h+sz]; lpSubKey
0x18002ed14  mov     rcx, rdi; hKey
0x18002ed17  call    cs:__imp_RegCreateKeyExW
0x18002ed1d  mov     ebx, eax
0x18002ed1f  test    eax, eax
0x18002ed21  jnz     short loc_18002ED85
0x18002ed23  cmp     [rbp+57h+dwDisposition], 1
0x18002ed27  jnz     short loc_18002ED7E
0x18002ed29  mov     ebx, r14d
0x18002ed2c  xor     esi, esi
0x18002ed2e  lea     r14d, [rax+1]
0x18002ed32  movsxd  rax, esi
0x18002ed35  lea     r8, [rax+rax*2]
0x18002ed39  movzx   edx, word ptr [r13+r8*8+0]
0x18002ed3f  add     rdx, rdx
0x18002ed42  mov     eax, [r13+r8*8+10h]
0x18002ed47  mov     [rsp+110h+samDesired], eax; cbData
0x18002ed4b  mov     rax, [r13+r8*8+8]
0x18002ed50  mov     qword ptr [rsp+110h+dwOptions], rax; lpData
0x18002ed55  mov     r9d, [r12+rdx*8+8]; dwType
0x18002ed5a  xor     r8d, r8d; Reserved
0x18002ed5d  mov     rdx, [r12+rdx*8]; lpValueName
0x18002ed61  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ed65  call    cs:__imp_RegSetValueExW
0x18002ed6b  test    eax, eax
0x18002ed6d  jnz     short loc_18002ED78
0x18002ed6f  inc     esi
0x18002ed71  cmp     esi, r15d
0x18002ed74  jl      short loc_18002ED32
0x18002ed76  jmp     short loc_18002EDD9
0x18002ed78  jg      short loc_18002ED87
0x18002ed7a  mov     ebx, eax
0x18002ed7c  jmp     short loc_18002ED90
0x18002ed7e  mov     ebx, 800700B7h
0x18002ed83  jmp     short loc_18002EDB9
0x18002ed85  jle     short loc_18002ED90
0x18002ed87  movzx   ebx, ax
0x18002ed8a  or      ebx, 80070000h
0x18002ed90  test    ebx, ebx
0x18002ed92  jns     short loc_18002EDD9
0x18002ed94  test    r14d, r14d
0x18002ed97  jz      short loc_18002EDB9
0x18002ed99  xor     edx, edx; lpSubKey
0x18002ed9b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ed9f  call    cs:__imp_RegDeleteTreeW
0x18002eda5  lea     rdx, [rbp+57h+sz]; lpSubKey
0x18002eda9  mov     rcx, rdi; hKey
0x18002edac  call    cs:__imp_RegDeleteKeyW
0x18002edb2  jmp     short loc_18002EDB9
0x18002edb4  mov     ebx, 80070057h
0x18002edb9  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x18002edc0  jz      short loc_18002EDD9
0x18002edc2  mov     r9d, ebx
0x18002edc5  lea     r8, aInsertRecordFa; "Insert Record Failed"
0x18002edcc  lea     rdx, EnterpriseAppDBError
0x18002edd3  call    McTemplateU0zq_EventWriteTransfer
0x18002edd8  nop
0x18002edd9  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18002eddd  call    cs:__imp_LeaveCriticalSection
0x18002ede3  nop
0x18002ede4  mov     rcx, [rbp+57h+hKey]; hKey
0x18002ede8  test    rcx, rcx
0x18002edeb  jz      short loc_18002EDF3
0x18002eded  call    cs:__imp_RegCloseKey
0x18002edf3  mov     eax, ebx
0x18002edf5  mov     rcx, [rbp+57h+var_40]
0x18002edf9  xor     rcx, rsp; StackCookie
0x18002edfc  call    __security_check_cookie
0x18002ee01  mov     rbx, [rsp+110h+arg_18]
0x18002ee09  add     rsp, 0E0h
0x18002ee10  pop     r15
0x18002ee12  pop     r14
0x18002ee14  pop     r13
0x18002ee16  pop     r12
0x18002ee18  pop     rdi
0x18002ee19  pop     rsi
0x18002ee1a  pop     rbp
0x18002ee1b  retn
```
