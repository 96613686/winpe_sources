# EnrollmentManager::UpdateField(TABLEID,_GUID,DB_COLUMN *,ushort)

- ea: `0x18001b878`
- end: `0x18001ba4e`
- name: `?UpdateField@EnrollmentManager@@SAJW4TABLEID@@U_GUID@@PEAUDB_COLUMN@@G@Z`
- size: `470`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180007280`
- `0x180010ce0`
- `0x180010df0`
- `0x180010f20`
- `0x180011050`
- `0x180011160`
- `0x180016aa8`
- `0x18001845c`
- `0x180018518`
- `0x18001b664`
- `0x18001c6d8`
- `0x18001c844`

## callees

- `0x180006858`
- `0x18001b878`
- `0x180027a18`
- `0x18002ee24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b940`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b953`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b9cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001b9cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b94b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ba2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b94b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ba2b`

## string_xrefs

- `0x18001ba04`: `Update Record Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnrollmentManager::UpdateField(int a1, __int64 a2, __int64 a3, unsigned __int16 a4)
{
  __int64 v6; // rsi
  struct EnterpriseDB *DBInstance; // rax
  struct EnterpriseDB *v8; // rdi
  unsigned int v9; // ebx
  struct _RTL_CRITICAL_SECTION *v10; // r12
  __int64 v11; // rcx
  LPCWSTR *v12; // r14
  LPCWSTR v13; // r15
  int v14; // edi
  int v15; // eax
  LSTATUS v16; // eax
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  __int128 v20; // [rsp+40h] [rbp-40h]
  __int64 v21; // [rsp+50h] [rbp-30h]
  __int128 v22; // [rsp+60h] [rbp-20h] BYREF
  __int64 v23; // [rsp+70h] [rbp-10h]

  v6 = a1;
  v20 = 0;
  v21 = 0;
  DBInstance = EnterpriseConfig::GetDBInstance();
  v8 = DBInstance;
  if ( !DBInstance )
    return (unsigned int)-2147024882;
  *((_QWORD *)&v20 + 1) = a2;
  LODWORD(v21) = 16;
  v22 = v20;
  v23 = v21;
  hKey = 0;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)DBInstance + 24);
  *(_QWORD *)&v20 = (char *)DBInstance + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)DBInstance + 24));
  BYTE8(v20) = 1;
  if ( !*(_DWORD *)v8 )
  {
    v9 = -2147467259;
    goto LABEL_19;
  }
  if ( !a3 )
    goto LABEL_18;
  if ( (unsigned int)v6 > 1 )
    goto LABEL_18;
  v11 = 3 * v6;
  v12 = &(&g_TableInfo)[3 * v6];
  if ( !v12 )
    goto LABEL_18;
  hKey = 0;
  v9 = EnterpriseDB::OpenRecord(v8, (unsigned int)v6, &v22, &hKey);
  if ( (v9 & 0x80000000) != 0 )
    goto LABEL_19;
  v13 = v12[2];
  if ( !v13 )
  {
LABEL_18:
    v9 = -2147024809;
LABEL_19:
    if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x100) != 0 )
      McTemplateU0zq_EventWriteTransfer(v11, EnterpriseAppDBError, L"Update Record Failed", v9);
    goto LABEL_21;
  }
  v14 = 0;
  if ( a4 )
  {
    while ( 1 )
    {
      v15 = *(unsigned __int16 *)(a3 + 24LL * v14);
      if ( (_WORD)v15 != *((_WORD *)v12 + 6) )
      {
        v16 = RegSetValueExW(
                hKey,
                *(LPCWSTR *)&v13[8 * v15],
                0,
                *(_DWORD *)&v13[8 * v15 + 4],
                *(const BYTE **)(a3 + 24LL * v14 + 8),
                *(_DWORD *)(a3 + 24LL * v14 + 16));
        if ( v16 )
          break;
      }
      if ( ++v14 >= a4 )
        goto LABEL_21;
    }
    if ( v16 > 0 )
      v9 = (unsigned __int16)v16 | 0x80070000;
    else
      v9 = v16;
    goto LABEL_19;
  }
LABEL_21:
  LeaveCriticalSection(v10);
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18001b878  mov     [rsp-38h+arg_18], rbx
0x18001b87d  push    rbp
0x18001b87e  push    rsi
0x18001b87f  push    rdi
0x18001b880  push    r12
0x18001b882  push    r13
0x18001b884  push    r14
0x18001b886  push    r15
0x18001b888  mov     rbp, rsp
0x18001b88b  sub     rsp, 80h
0x18001b892  mov     [rbp+var_50], r9w
0x18001b897  mov     r13, r8
0x18001b89a  mov     rbx, rdx
0x18001b89d  movsxd  rsi, ecx
0x18001b8a0  xorps   xmm0, xmm0
0x18001b8a3  xor     eax, eax
0x18001b8a5  movups  [rbp+var_40], xmm0
0x18001b8a9  mov     [rbp+var_30], rax
0x18001b8ad  call    ?GetDBInstance@EnterpriseConfig@@SAPEAVEnterpriseDB@@XZ; EnterpriseConfig::GetDBInstance(void)
0x18001b8b2  mov     rdi, rax
0x18001b8b5  test    rax, rax
0x18001b8b8  jnz     short loc_18001B8C4
0x18001b8ba  mov     ebx, 8007000Eh
0x18001b8bf  jmp     loc_18001BA31
0x18001b8c4  mov     qword ptr [rbp+var_40+8], rbx
0x18001b8c8  mov     dword ptr [rbp+var_30], 10h
0x18001b8cf  movups  xmm0, [rbp+var_40]
0x18001b8d3  movaps  [rbp+var_20], xmm0
0x18001b8d7  movsd   xmm1, [rbp+var_30]
0x18001b8dc  movsd   [rbp+var_10], xmm1
0x18001b8e1  mov     [rbp+hKey], 0
0x18001b8e9  lea     r12, [rax+18h]
0x18001b8ed  mov     qword ptr [rbp+var_40], r12
0x18001b8f1  mov     rcx, r12; lpCriticalSection
0x18001b8f4  call    cs:__imp_EnterCriticalSection
0x18001b8fa  mov     byte ptr [rbp+var_40+8], 1
0x18001b8fe  cmp     dword ptr [rdi], 0
0x18001b901  jnz     short loc_18001B90D
0x18001b903  mov     ebx, 80004005h
0x18001b908  jmp     loc_18001B9F8
0x18001b90d  test    r13, r13
0x18001b910  jz      loc_18001B9F3
0x18001b916  cmp     esi, 1
0x18001b919  ja      loc_18001B9F3
0x18001b91f  lea     rcx, [rsi+rsi*2]
0x18001b923  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x18001b92a  lea     r14, [rax+rcx*8]
0x18001b92e  test    r14, r14
0x18001b931  jz      loc_18001B9F3
0x18001b937  mov     r15, [rbp+hKey]
0x18001b93b  test    r15, r15
0x18001b93e  jz      short loc_18001B959
0x18001b940  call    cs:__imp_GetLastError
0x18001b946  mov     ebx, eax
0x18001b948  mov     rcx, r15; hKey
0x18001b94b  call    cs:__imp_RegCloseKey
0x18001b951  mov     ecx, ebx; dwErrCode
0x18001b953  call    cs:__imp_SetLastError
0x18001b959  mov     [rbp+hKey], 0
0x18001b961  lea     r9, [rbp+hKey]
0x18001b965  lea     r8, [rbp+var_20]
0x18001b969  mov     edx, esi
0x18001b96b  mov     rcx, rdi
0x18001b96e  call    ?OpenRecord@EnterpriseDB@@AEAAJW4TABLEID@@AEAUDB_COLUMN@@PEAPEAUHKEY__@@@Z; EnterpriseDB::OpenRecord(TABLEID,DB_COLUMN &,HKEY__ * *)
0x18001b973  mov     ebx, eax
0x18001b975  test    eax, eax
0x18001b977  js      short loc_18001B9F8
0x18001b979  mov     r15, [r14+10h]
0x18001b97d  test    r15, r15
0x18001b980  jz      short loc_18001B9F3
0x18001b982  xor     edi, edi
0x18001b984  movzx   esi, [rbp+var_50]
0x18001b988  test    esi, esi
0x18001b98a  jz      loc_18001BA18
0x18001b990  movsxd  rax, edi
0x18001b993  lea     rcx, [rax+rax*2]
0x18001b997  movzx   eax, word ptr [r13+rcx*8+0]
0x18001b99d  cmp     ax, [r14+0Ch]
0x18001b9a2  jz      short loc_18001B9D6
0x18001b9a4  mov     edx, eax
0x18001b9a6  add     rdx, rdx
0x18001b9a9  mov     eax, [r13+rcx*8+10h]
0x18001b9ae  mov     [rsp+80h+cbData], eax; cbData
0x18001b9b2  mov     rax, [r13+rcx*8+8]
0x18001b9b7  mov     [rsp+80h+lpData], rax; lpData
0x18001b9bc  mov     r9d, [r15+rdx*8+8]; dwType
0x18001b9c1  xor     r8d, r8d; Reserved
0x18001b9c4  mov     rdx, [r15+rdx*8]; lpValueName
0x18001b9c8  mov     rcx, [rbp+hKey]; hKey
0x18001b9cc  call    cs:__imp_RegSetValueExW
0x18001b9d2  test    eax, eax
0x18001b9d4  jnz     short loc_18001B9DE
0x18001b9d6  inc     edi
0x18001b9d8  cmp     edi, esi
0x18001b9da  jl      short loc_18001B990
0x18001b9dc  jmp     short loc_18001BA18
0x18001b9de  jg      short loc_18001B9E4
0x18001b9e0  mov     ebx, eax
0x18001b9e2  jmp     short loc_18001B9ED
0x18001b9e4  movzx   ebx, ax
0x18001b9e7  or      ebx, 80070000h
0x18001b9ed  test    ebx, ebx
0x18001b9ef  jns     short loc_18001BA18
0x18001b9f1  jmp     short loc_18001B9F8
0x18001b9f3  mov     ebx, 80070057h
0x18001b9f8  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x18001b9ff  jz      short loc_18001BA18
0x18001ba01  mov     r9d, ebx
0x18001ba04  lea     r8, aUpdateRecordFa; "Update Record Failed"
0x18001ba0b  lea     rdx, EnterpriseAppDBError
0x18001ba12  call    McTemplateU0zq_EventWriteTransfer
0x18001ba17  nop
0x18001ba18  mov     rcx, r12; lpCriticalSection
0x18001ba1b  call    cs:__imp_LeaveCriticalSection
0x18001ba21  nop
0x18001ba22  mov     rcx, [rbp+hKey]; hKey
0x18001ba26  test    rcx, rcx
0x18001ba29  jz      short loc_18001BA31
0x18001ba2b  call    cs:__imp_RegCloseKey
0x18001ba31  mov     eax, ebx
0x18001ba33  mov     rbx, [rsp+80h+arg_18]
0x18001ba3b  add     rsp, 80h
0x18001ba42  pop     r15
0x18001ba44  pop     r14
0x18001ba46  pop     r13
0x18001ba48  pop     r12
0x18001ba4a  pop     rdi
0x18001ba4b  pop     rsi
0x18001ba4c  pop     rbp
0x18001ba4d  retn
```
