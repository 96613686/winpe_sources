# EnterpriseDB::UpdateRecord(TABLEID,DB_COLUMN,DB_COLUMN *,ushort)

- ea: `0x180031dc0`
- end: `0x180031f88`
- name: `?UpdateRecord@EnterpriseDB@@QEAAJW4TABLEID@@UDB_COLUMN@@PEAU3@G@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001cc00`

## callees

- `0x180006ac0`
- `0x180031820`
- `0x180031dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031e69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031e69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031f4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031f4e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031df2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031df2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031ef9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031ef9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031e5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031f68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031e5b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031f68`

## string_xrefs

- `0x180031f37`: `Update Record Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseDB::UpdateRecord(__int64 a1, int a2, __int64 a3, __int64 a4, unsigned __int16 a5)
{
  __int64 v7; // rdi
  struct _RTL_CRITICAL_SECTION *v9; // r12
  __int64 v10; // rcx
  unsigned int v11; // ebx
  LPCWSTR *v12; // rsi
  HKEY v13; // r14
  DWORD LastError; // ebx
  LPCWSTR v15; // r14
  int v16; // edi
  int v17; // ebp
  int v18; // eax
  LSTATUS v19; // eax
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF

  v7 = a2;
  hKey = 0;
  v9 = (struct _RTL_CRITICAL_SECTION *)(a1 + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( *(_DWORD *)a1 )
  {
    if ( !a4 )
      goto LABEL_18;
    if ( (unsigned int)v7 > 1 )
      goto LABEL_18;
    v10 = 3 * v7;
    v12 = &(&g_TableInfo)[3 * v7];
    if ( !v12 )
      goto LABEL_18;
    v13 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v13);
      SetLastError(LastError);
    }
    hKey = 0;
    v11 = EnterpriseDB::OpenRecord(a1, (unsigned int)v7, a3, &hKey);
    if ( (v11 & 0x80000000) != 0 )
      goto LABEL_19;
    v15 = v12[2];
    if ( v15 )
    {
      v16 = 0;
      v17 = a5;
      if ( !a5 )
        goto LABEL_21;
      while ( 1 )
      {
        v18 = *(unsigned __int16 *)(a4 + 24LL * v16);
        if ( (_WORD)v18 != *((_WORD *)v12 + 6) )
        {
          v19 = RegSetValueExW(
                  hKey,
                  *(LPCWSTR *)&v15[8 * v18],
                  0,
                  *(_DWORD *)&v15[8 * v18 + 4],
                  *(const BYTE **)(a4 + 24LL * v16 + 8),
                  *(_DWORD *)(a4 + 24LL * v16 + 16));
          if ( v19 )
            break;
        }
        if ( ++v16 >= v17 )
          goto LABEL_21;
      }
      if ( v19 > 0 )
        v11 = (unsigned __int16)v19 | 0x80070000;
      else
        v11 = v19;
    }
    else
    {
LABEL_18:
      v11 = -2147024809;
    }
  }
  else
  {
    v11 = -2147467259;
  }
LABEL_19:
  if ( (Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits & 0x100) != 0 )
    McTemplateU0zq_EventWriteTransfer(v10, EnterpriseAppDBError, L"Update Record Failed", v11);
LABEL_21:
  LeaveCriticalSection(v9);
  if ( hKey )
    RegCloseKey(hKey);
  return v11;
}

```

## disassembly

```asm
0x180031dc0  mov     rax, rsp
0x180031dc3  push    rbx
0x180031dc4  push    rbp
0x180031dc5  push    rsi
0x180031dc6  push    rdi
0x180031dc7  push    r12
0x180031dc9  push    r13
0x180031dcb  push    r14
0x180031dcd  push    r15
0x180031dcf  sub     rsp, 48h
0x180031dd3  mov     r15, r9
0x180031dd6  mov     r13, r8
0x180031dd9  movsxd  rdi, edx
0x180031ddc  mov     rbp, rcx
0x180031ddf  mov     qword ptr [rax+8], 0
0x180031de7  lea     r12, [rcx+18h]
0x180031deb  mov     [rax-58h], r12
0x180031def  mov     rcx, r12; lpCriticalSection
0x180031df2  call    cs:__imp_EnterCriticalSection
0x180031df9  nop     dword ptr [rax+rax+00h]
0x180031dfe  mov     [rsp+88h+var_50], 1
0x180031e03  cmp     dword ptr [rbp+0], 0
0x180031e07  jnz     short loc_180031E13
0x180031e09  mov     ebx, 80004005h
0x180031e0e  jmp     loc_180031F2B
0x180031e13  test    r15, r15
0x180031e16  jz      loc_180031F26
0x180031e1c  cmp     edi, 1
0x180031e1f  ja      loc_180031F26
0x180031e25  lea     rcx, [rdi+rdi*2]
0x180031e29  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x180031e30  lea     rsi, [rax+rcx*8]
0x180031e34  test    rsi, rsi
0x180031e37  jz      loc_180031F26
0x180031e3d  mov     r14, [rsp+88h+hKey]
0x180031e45  test    r14, r14
0x180031e48  jz      short loc_180031E75
0x180031e4a  call    cs:__imp_GetLastError
0x180031e51  nop     dword ptr [rax+rax+00h]
0x180031e56  mov     ebx, eax
0x180031e58  mov     rcx, r14; hKey
0x180031e5b  call    cs:__imp_RegCloseKey
0x180031e62  nop     dword ptr [rax+rax+00h]
0x180031e67  mov     ecx, ebx; dwErrCode
0x180031e69  call    cs:__imp_SetLastError
0x180031e70  nop     dword ptr [rax+rax+00h]
0x180031e75  mov     [rsp+88h+hKey], 0
0x180031e81  lea     r9, [rsp+88h+hKey]
0x180031e89  mov     r8, r13
0x180031e8c  mov     edx, edi
0x180031e8e  mov     rcx, rbp
0x180031e91  call    ?OpenRecord@EnterpriseDB@@AEAAJW4TABLEID@@AEAUDB_COLUMN@@PEAPEAUHKEY__@@@Z; EnterpriseDB::OpenRecord(TABLEID,DB_COLUMN &,HKEY__ * *)
0x180031e96  mov     ebx, eax
0x180031e98  test    eax, eax
0x180031e9a  js      loc_180031F2B
0x180031ea0  mov     r14, [rsi+10h]
0x180031ea4  test    r14, r14
0x180031ea7  jz      short loc_180031F26
0x180031ea9  xor     edi, edi
0x180031eab  movzx   ebp, [rsp+88h+arg_20]
0x180031eb3  test    ebp, ebp
0x180031eb5  jz      loc_180031F4B
0x180031ebb  movsxd  rax, edi
0x180031ebe  lea     rcx, [rax+rax*2]
0x180031ec2  movzx   eax, word ptr [r15+rcx*8]
0x180031ec7  cmp     ax, [rsi+0Ch]
0x180031ecb  jz      short loc_180031F09
0x180031ecd  mov     edx, eax
0x180031ecf  add     rdx, rdx
0x180031ed2  mov     eax, [r15+rcx*8+10h]
0x180031ed7  mov     [rsp+88h+cbData], eax; cbData
0x180031edb  mov     rax, [r15+rcx*8+8]
0x180031ee0  mov     [rsp+88h+lpData], rax; lpData
0x180031ee5  mov     r9d, [r14+rdx*8+8]; dwType
0x180031eea  xor     r8d, r8d; Reserved
0x180031eed  mov     rdx, [r14+rdx*8]; lpValueName
0x180031ef1  mov     rcx, [rsp+88h+hKey]; hKey
0x180031ef9  call    cs:__imp_RegSetValueExW
0x180031f00  nop     dword ptr [rax+rax+00h]
0x180031f05  test    eax, eax
0x180031f07  jnz     short loc_180031F11
0x180031f09  inc     edi
0x180031f0b  cmp     edi, ebp
0x180031f0d  jl      short loc_180031EBB
0x180031f0f  jmp     short loc_180031F4B
0x180031f11  jg      short loc_180031F17
0x180031f13  mov     ebx, eax
0x180031f15  jmp     short loc_180031F20
0x180031f17  movzx   ebx, ax
0x180031f1a  or      ebx, 80070000h
0x180031f20  test    ebx, ebx
0x180031f22  jns     short loc_180031F4B
0x180031f24  jmp     short loc_180031F2B
0x180031f26  mov     ebx, 80070057h
0x180031f2b  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x180031f32  jz      short loc_180031F4B
0x180031f34  mov     r9d, ebx
0x180031f37  lea     r8, aUpdateRecordFa; "Update Record Failed"
0x180031f3e  lea     rdx, EnterpriseAppDBError
0x180031f45  call    McTemplateU0zq_EventWriteTransfer
0x180031f4a  nop
0x180031f4b  mov     rcx, r12; lpCriticalSection
0x180031f4e  call    cs:__imp_LeaveCriticalSection
0x180031f55  nop     dword ptr [rax+rax+00h]
0x180031f5a  nop
0x180031f5b  mov     rcx, [rsp+88h+hKey]; hKey
0x180031f63  test    rcx, rcx
0x180031f66  jz      short loc_180031F74
0x180031f68  call    cs:__imp_RegCloseKey
0x180031f6f  nop     dword ptr [rax+rax+00h]
0x180031f74  mov     eax, ebx
0x180031f76  add     rsp, 48h
0x180031f7a  pop     r15
0x180031f7c  pop     r14
0x180031f7e  pop     r13
0x180031f80  pop     r12
0x180031f82  pop     rdi
0x180031f83  pop     rsi
0x180031f84  pop     rbp
0x180031f85  pop     rbx
0x180031f86  retn
```
