# EnterpriseDB::EnumeratePrimaryKeys(TABLEID,_GUID * *,ulong &)

- ea: `0x180031064`
- end: `0x1800312de`
- name: `?EnumeratePrimaryKeys@EnterpriseDB@@QEAAJW4TABLEID@@PEAPEAU_GUID@@AEAK@Z`
- size: `634`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b548`
- `0x18001b63c`
- `0x18001b69c`
- `0x18001b7fc`
- `0x18001d338`

## callees

- `0x180002fc0`
- `0x180006ac0`
- `0x180031064`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18003124d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18003124d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003121f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003121f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800312a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800312a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800310c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800310c2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031200`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180031200`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003116f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003116f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180031064  mov     [rsp-8+arg_8], rbx
0x180031069  push    rbp
0x18003106a  push    rsi
0x18003106b  push    rdi
0x18003106c  push    r12
0x18003106e  push    r13
0x180031070  push    r14
0x180031072  push    r15
0x180031074  lea     rbp, [rsp-27h]
0x180031079  sub     rsp, 0E0h
0x180031080  mov     rax, cs:__security_cookie
0x180031087  xor     rax, rsp
0x18003108a  mov     [rbp+57h+var_40], rax
0x18003108e  mov     r13, r9
0x180031091  mov     r15, r8
0x180031094  movsxd  rbx, edx
0x180031097  mov     rdi, rcx
0x18003109a  mov     [rbp+57h+cSubKeys], 0
0x1800310a1  mov     [rbp+57h+cbMaxSubKeyLen], 0
0x1800310a8  xor     edx, edx; Val
0x1800310aa  lea     r8d, [rdx+50h]; Size
0x1800310ae  lea     rcx, [rbp+57h+Name]; void *
0x1800310b2  call    memset_0
0x1800310b7  lea     r12, [rdi+18h]
0x1800310bb  mov     [rbp+57h+var_A8], r12
0x1800310bf  mov     rcx, r12; lpCriticalSection
0x1800310c2  call    cs:__imp_EnterCriticalSection
0x1800310c9  nop     dword ptr [rax+rax+00h]
0x1800310ce  mov     [rbp+57h+var_A0], 1
0x1800310d2  test    r15, r15
0x1800310d5  jz      loc_180031280
0x1800310db  cmp     ebx, 1
0x1800310de  ja      loc_180031280
0x1800310e4  lea     rcx, [rbx+rbx*2]
0x1800310e8  lea     rax, ?g_TableInfo@@3PAUTABLE_INFO@@A; TABLE_INFO near * g_TableInfo
0x1800310ef  lea     rax, [rax+rcx*8]
0x1800310f3  test    rax, rax
0x1800310f6  jz      loc_180031280
0x1800310fc  test    ebx, ebx
0x1800310fe  jz      short loc_18003110F
0x180031100  cmp     ebx, 1
0x180031103  jnz     loc_180031279
0x180031109  mov     rdi, [rdi+10h]
0x18003110d  jmp     short loc_180031113
0x18003110f  mov     rdi, [rdi+8]
0x180031113  test    rdi, rdi
0x180031116  jz      loc_180031279
0x18003111c  mov     [rsp+110h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180031125  mov     [rsp+110h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18003112e  mov     [rsp+110h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180031137  mov     [rsp+110h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180031140  mov     [rsp+110h+lpcValues], 0; lpcValues
0x180031149  mov     [rsp+110h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180031152  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180031156  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003115b  lea     rax, [rbp+57h+cSubKeys]
0x18003115f  mov     [rsp+110h+lpcSubKeys], rax; lpcSubKeys
0x180031164  xor     r9d, r9d; lpReserved
0x180031167  xor     r8d, r8d; lpcchClass
0x18003116a  xor     edx, edx; lpClass
0x18003116c  mov     rcx, rdi; hKey
0x18003116f  call    cs:__imp_RegQueryInfoKeyW
0x180031176  nop     dword ptr [rax+rax+00h]
0x18003117b  mov     ebx, eax
0x18003117d  test    eax, eax
0x18003117f  jnz     loc_180031268
0x180031185  cmp     [rbp+57h+cbMaxSubKeyLen], 28h ; '('
0x180031189  jnb     loc_180031279
0x18003118f  mov     eax, [rbp+57h+cSubKeys]
0x180031192  test    eax, eax
0x180031194  jz      loc_1800312A5
0x18003119a  mov     ecx, eax
0x18003119c  lea     eax, [rbx+10h]
0x18003119f  mul     rcx
0x1800311a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800311a9  cmovb   rax, rcx
0x1800311ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800311b4  mov     rcx, rax; unsigned __int64
0x1800311b7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800311bc  mov     r14, rax
0x1800311bf  xor     esi, esi
0x1800311c1  mov     eax, [rbp+57h+cSubKeys]
0x1800311c4  test    eax, eax
0x1800311c6  jz      short loc_18003123A
0x1800311c8  mov     [rbp+57h+cbMaxSubKeyLen], 28h ; '('
0x1800311cf  mov     [rsp+110h+lpcValues], 0; lpftLastWriteTime
0x1800311d8  mov     [rsp+110h+lpcbMaxClassLen], 0; lpcchClass
0x1800311e1  mov     [rsp+110h+lpcbMaxSubKeyLen], 0; lpClass
0x1800311ea  mov     [rsp+110h+lpcSubKeys], 0; lpReserved
0x1800311f3  lea     r9, [rbp+57h+cbMaxSubKeyLen]; lpcchName
0x1800311f7  lea     r8, [rbp+57h+Name]; lpName
0x1800311fb  mov     edx, esi; dwIndex
0x1800311fd  mov     rcx, rdi; hKey
0x180031200  call    cs:__imp_RegEnumKeyExW
0x180031207  nop     dword ptr [rax+rax+00h]
0x18003120c  mov     ebx, eax
0x18003120e  test    eax, eax
0x180031210  jnz     short loc_18003125B
0x180031212  mov     edx, esi
0x180031214  shl     rdx, 4
0x180031218  add     rdx, r14; pclsid
0x18003121b  lea     rcx, [rbp+57h+Name]; lpsz
0x18003121f  call    cs:__imp_CLSIDFromString
0x180031226  nop     dword ptr [rax+rax+00h]
0x18003122b  mov     ebx, eax
0x18003122d  test    eax, eax
0x18003122f  js      short loc_180031241
0x180031231  inc     esi
0x180031233  mov     eax, [rbp+57h+cSubKeys]
0x180031236  cmp     esi, eax
0x180031238  jb      short loc_1800311C8
0x18003123a  mov     [r15], r14
0x18003123d  mov     [r13+0], eax
0x180031241  test    r14, r14
0x180031244  jz      short loc_180031273
0x180031246  test    ebx, ebx
0x180031248  jns     short loc_1800312A5
0x18003124a  mov     rcx, r14
0x18003124d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180031254  nop     dword ptr [rax+rax+00h]
0x180031259  jmp     short loc_180031285
0x18003125b  jle     short loc_180031241
0x18003125d  movzx   ebx, ax
0x180031260  or      ebx, 80070000h
0x180031266  jmp     short loc_180031241
0x180031268  jle     short loc_180031273
0x18003126a  movzx   ebx, ax
0x18003126d  or      ebx, 80070000h
0x180031273  test    ebx, ebx
0x180031275  jns     short loc_1800312A5
0x180031277  jmp     short loc_180031285
0x180031279  mov     ebx, 80004005h
0x18003127e  jmp     short loc_180031285
0x180031280  mov     ebx, 80070057h
0x180031285  test    byte ptr cs:Microsoft_WindowsPhone_EnterpriseAppMgmtEnableBits+1, 1
0x18003128c  jz      short loc_1800312A5
0x18003128e  mov     r9d, ebx
0x180031291  lea     r8, aEnumerateKeysF; "Enumerate Keys Failed"
0x180031298  lea     rdx, EnterpriseAppDBError
0x18003129f  call    McTemplateU0zq_EventWriteTransfer
0x1800312a4  nop
0x1800312a5  mov     rcx, r12; lpCriticalSection
0x1800312a8  call    cs:__imp_LeaveCriticalSection
0x1800312af  nop     dword ptr [rax+rax+00h]
0x1800312b4  mov     eax, ebx
0x1800312b6  mov     rcx, [rbp+57h+var_40]
0x1800312ba  xor     rcx, rsp; StackCookie
0x1800312bd  call    __security_check_cookie
0x1800312c2  mov     rbx, [rsp+110h+arg_8]
0x1800312ca  add     rsp, 0E0h
0x1800312d1  pop     r15
0x1800312d3  pop     r14
0x1800312d5  pop     r13
0x1800312d7  pop     r12
0x1800312d9  pop     rdi
0x1800312da  pop     rsi
0x1800312db  pop     rbp
0x1800312dc  retn
```
