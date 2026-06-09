# EnterpriseDB::DeleteRecord(TABLEID,DB_COLUMN)

- ea: `0x180030e54`
- end: `0x18003105b`
- name: `?DeleteRecord@EnterpriseDB@@QEAAJW4TABLEID@@UDB_COLUMN@@@Z`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001ac50`

## callees

- `0x180006ac0`
- `0x180030e54`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180030f15`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180030f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030f46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030f46`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030f65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030f65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031012`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031012`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030eae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030eae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030f92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030f92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031028`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031028`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180030faa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180030faa`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180030fc3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180030fc3`

## string_xrefs

- `0x180030ffb`: `Delete Record Failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180030e54  mov     [rsp-8+arg_8], rbx
0x180030e59  mov     [rsp-8+arg_18], rsi
0x180030e5e  push    rbp
0x180030e5f  push    rdi
0x180030e60  push    r14
0x180030e62  lea     rbp, [rsp-47h]
0x180030e67  sub     rsp, 0C0h
0x180030e6e  mov     rax, cs:__security_cookie
0x180030e75  xor     rax, rsp
0x180030e78  mov     [rbp+57h+var_20], rax
0x180030e7c  mov     rsi, r8
0x180030e7f  movsxd  rbx, edx
0x180030e82  mov     rdi, rcx
0x180030e85  mov     [rbp+57h+hKey], 0
0x180030e8d  xor     edx, edx; Val
0x180030e8f  lea     r8d, [rdx+50h]; Size
0x180030e93  lea     rcx, [rbp+57h+sz]; void *
0x180030e97  call    memset_0
0x180030e9c  xorps   xmm0, xmm0
0x180030e9f  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x180030ea3  lea     r14, [rdi+18h]
0x180030ea7  mov     [rbp+57h+var_98], r14
0x180030eab  mov     rcx, r14; lpCriticalSection
0x180030eae  call    cs:__imp_EnterCriticalSection
0x180030eb5  nop     dword ptr [rax+rax+00h]
0x180030eba  mov     [rbp+57h+var_90], 1
0x180030ebe  cmp     dword ptr [rdi], 0
0x180030ec1  jnz     short loc_180030ECD
0x180030ec3  mov     ebx, 80004005h
0x180030ec8  jmp     loc_180030FEF
0x180030ecd  cmp     ebx, 1
0x180030ed0  ja      loc_180030FEA
0x180030ed6  lea     rcx, [rbx+rbx*2]
0x180030eda  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x180030ee1  lea     rax, [rax+rcx*8]
0x180030ee5  test    rax, rax
0x180030ee8  jz      loc_180030FEA
0x180030eee  movzx   eax, word ptr [rax+0Ch]
0x180030ef2  cmp     [rsi], ax
0x180030ef5  jnz     loc_180030FEA
0x180030efb  mov     rax, [rsi+8]
0x180030eff  movups  xmm0, xmmword ptr [rax]
0x180030f02  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x180030f07  mov     r8d, 28h ; '('; cchMax
0x180030f0d  lea     rdx, [rbp+57h+sz]; lpsz
0x180030f11  lea     rcx, [rbp+57h+rguid]; rguid
0x180030f15  call    cs:__imp_StringFromGUID2
0x180030f1c  nop     dword ptr [rax+rax+00h]
0x180030f21  test    eax, eax
0x180030f23  jz      short loc_180030EC3
0x180030f25  test    ebx, ebx
0x180030f27  jz      short loc_180030F34
0x180030f29  cmp     ebx, 1
0x180030f2c  jnz     short loc_180030EC3
0x180030f2e  mov     rdi, [rdi+10h]
0x180030f32  jmp     short loc_180030F38
0x180030f34  mov     rdi, [rdi+8]
0x180030f38  test    rdi, rdi
0x180030f3b  jz      short loc_180030EC3
0x180030f3d  mov     rsi, [rbp+57h+hKey]
0x180030f41  test    rsi, rsi
0x180030f44  jz      short loc_180030F71
0x180030f46  call    cs:__imp_GetLastError
0x180030f4d  nop     dword ptr [rax+rax+00h]
0x180030f52  mov     ebx, eax
0x180030f54  mov     rcx, rsi; hKey
0x180030f57  call    cs:__imp_RegCloseKey
0x180030f5e  nop     dword ptr [rax+rax+00h]
0x180030f63  mov     ecx, ebx; dwErrCode
0x180030f65  call    cs:__imp_SetLastError
0x180030f6c  nop     dword ptr [rax+rax+00h]
0x180030f71  mov     [rbp+57h+hKey], 0
0x180030f79  lea     rax, [rbp+57h+hKey]
0x180030f7d  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180030f82  mov     r9d, 0F003Fh; samDesired
0x180030f88  xor     r8d, r8d; ulOptions
0x180030f8b  lea     rdx, [rbp+57h+sz]; lpSubKey
0x180030f8f  mov     rcx, rdi; hKey
0x180030f92  call    cs:__imp_RegOpenKeyExW
0x180030f99  nop     dword ptr [rax+rax+00h]
0x180030f9e  mov     ebx, eax
0x180030fa0  test    eax, eax
0x180030fa2  jnz     short loc_180030FD5
0x180030fa4  xor     edx, edx; lpSubKey
0x180030fa6  mov     rcx, [rbp+57h+hKey]; hKey
0x180030faa  call    cs:__imp_RegDeleteTreeW
0x180030fb1  nop     dword ptr [rax+rax+00h]
0x180030fb6  mov     ebx, eax
0x180030fb8  test    eax, eax
0x180030fba  jnz     short loc_180030FD5
0x180030fbc  lea     rdx, [rbp+57h+sz]; lpSubKey
0x180030fc0  mov     rcx, rdi; hKey
0x180030fc3  call    cs:__imp_RegDeleteKeyW
0x180030fca  nop     dword ptr [rax+rax+00h]
0x180030fcf  mov     ebx, eax
0x180030fd1  test    eax, eax
0x180030fd3  jz      short loc_180030FE6
0x180030fd5  jle     short loc_180030FE0
0x180030fd7  movzx   ebx, ax
0x180030fda  or      ebx, 80070000h
0x180030fe0  test    ebx, ebx
0x180030fe2  jns     short loc_18003100F
0x180030fe4  jmp     short loc_180030FEF
0x180030fe6  xor     ebx, ebx
0x180030fe8  jmp     short loc_18003100F
0x180030fea  mov     ebx, 80070057h
0x180030fef  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x180030ff6  jz      short loc_18003100F
0x180030ff8  mov     r9d, ebx
0x180030ffb  lea     r8, aDeleteRecordFa; "Delete Record Failed"
0x180031002  lea     rdx, EnterpriseAppDBError
0x180031009  call    McTemplateU0zq_EventWriteTransfer
0x18003100e  nop
0x18003100f  mov     rcx, r14; lpCriticalSection
0x180031012  call    cs:__imp_LeaveCriticalSection
0x180031019  nop     dword ptr [rax+rax+00h]
0x18003101e  nop
0x18003101f  mov     rcx, [rbp+57h+hKey]; hKey
0x180031023  test    rcx, rcx
0x180031026  jz      short loc_180031034
0x180031028  call    cs:__imp_RegCloseKey
0x18003102f  nop     dword ptr [rax+rax+00h]
0x180031034  mov     eax, ebx
0x180031036  mov     rcx, [rbp+57h+var_20]
0x18003103a  xor     rcx, rsp; StackCookie
0x18003103d  call    __security_check_cookie
0x180031042  lea     r11, [rsp+0D0h+var_10]
0x18003104a  mov     rbx, [r11+28h]
0x18003104e  mov     rsi, [r11+38h]
0x180031052  mov     rsp, r11
0x180031055  pop     r14
0x180031057  pop     rdi
0x180031058  pop     rbp
0x180031059  retn
```
