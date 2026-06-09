# Windows::Compat::Inventory::MareDataWriter::QueryOneSettings(bool &,unsigned __int64 &,ulong &,bool &)

- ea: `0x18002b1e0`
- end: `0x18002b4b2`
- name: `?QueryOneSettings@MareDataWriter@Inventory@Compat@Windows@@QEAAJAEA_NAEA_KAEAK0@Z`
- size: `722`
- prototype: `int(Windows::Compat::Inventory::MareDataWriter *__hidden this, bool *, unsigned __int64 *, unsigned int *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800172a0`

## callees

- `0x180014ed4`
- `0x180014fa0`
- `0x18002b1e0`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b33d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b3e6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b33d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002b3e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002b333`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002b3dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002b333`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002b3dc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b31a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b3c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b31a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002b3c2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b248`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b284`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b450`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b487`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b248`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b284`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b450`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002b487`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b29c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002b29c`

## string_xrefs

- `0x18002b3fa`: `TelCacheProvider::SetMetadata failed [%#x]`
- `0x18002b401`: `Windows::Compat::Inventory::MareDataWriter::QueryOneSettings`
- `0x18002b25b`: `MareBackupFreshJson`
- `0x18002b218`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\MareBackup`
- `0x18002b26e`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\MareBackup`
- `0x18002b446`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\MareBackup`
- `0x18002b475`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\OneSettings\MareBackup`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::QueryOneSettings(
        Windows::Compat::Inventory::MareDataWriter *this,
        bool *a2,
        unsigned __int64 *pvData,
        unsigned int *a4,
        bool *a5)
{
  bool *v5; // r13
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rax
  HANDLE *v11; // rbx
  _BYTE *v12; // rsi
  __int16 v13; // di
  __int64 v14; // rcx
  char v15; // dl
  bool v16; // zf
  int v17; // edi
  __int64 v18; // rcx
  char v19; // al
  DWORD v21; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-10h] BYREF
  unsigned __int64 v24; // [rsp+58h] [rbp-8h] BYREF
  DWORD pcbData; // [rsp+A8h] [rbp+48h] BYREF
  DWORD v26; // [rsp+B0h] [rbp+50h] BYREF
  DWORD v27; // [rsp+B8h] [rbp+58h] BYREF

  v5 = a5;
  *a2 = 0;
  *v5 = 0;
  *pvData = 0;
  *a4 = 0;
  pcbData = 8;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\MareBackup",
    L"MareBackupDefaultFar",
    0x20000040u,
    0,
    pvData,
    &pcbData);
  v22 = 0;
  v26 = 8;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\MareBackup",
    L"MareBackupFreshJson",
    0x20000040u,
    0,
    &v22,
    &v26);
  if ( !v22 )
    goto LABEL_27;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v9 = v22;
  if ( v22 >= *(_QWORD *)&SystemTimeAsFileTime )
    goto LABEL_27;
  v10 = 0;
  v11 = (HANDLE *)((char *)this + 248);
  v12 = (char *)this + 284;
  v24 = 0;
  if ( !*((_QWORD *)this + 29) )
    goto LABEL_14;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((Windows::Compat::Inventory::MareDataWriter *)((char *)this + 248));
  v13 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64 *))(**((_QWORD **)this + 29) + 64LL))(
          *((_QWORD *)this + 29),
          L"ResetTimestamp",
          &v24);
  if ( *v12 )
  {
    v14 = *((_QWORD *)this + 34);
    v15 = 0;
    if ( *(_DWORD *)(v14 + 4) == 1 )
    {
      *v12 = 0;
      v15 = 1;
    }
    --*(_DWORD *)(v14 + 4);
    if ( !v15 )
      goto LABEL_12;
    goto LABEL_11;
  }
  if ( !WaitForSingleObject(*v11, 0xFFFFFFFF) )
  {
    --**((_DWORD **)this + 34);
    --*((_DWORD *)this + 70);
    ReleaseMutex(*v11);
LABEL_11:
    SetEvent(*((HANDLE *)this + 33));
  }
LABEL_12:
  v16 = v13 == 2;
  v9 = v22;
  if ( v16 )
    goto LABEL_15;
  v10 = v24;
LABEL_14:
  if ( v10 >= v9 )
    goto LABEL_27;
LABEL_15:
  *a2 = 1;
  if ( !*((_QWORD *)this + 29) )
  {
    v17 = -2147467262;
LABEL_26:
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::QueryOneSettings",
      51,
      "TelCacheProvider::SetMetadata failed [%#x]",
      v17);
    goto LABEL_27;
  }
  Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock((Windows::Compat::Inventory::MareDataWriter *)((char *)this + 248));
  v17 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, unsigned __int64))(**((_QWORD **)this + 29) + 88LL))(
          *((_QWORD *)this + 29),
          L"ResetTimestamp",
          v9);
  if ( !*v12 )
  {
    if ( WaitForSingleObject(*v11, 0xFFFFFFFF) )
      goto LABEL_25;
    --**((_DWORD **)this + 34);
    --*((_DWORD *)this + 70);
    ReleaseMutex(*v11);
    goto LABEL_24;
  }
  v18 = *((_QWORD *)this + 34);
  v19 = 0;
  if ( *(_DWORD *)(v18 + 4) == 1 )
  {
    *v12 = 0;
    v19 = 1;
  }
  --*(_DWORD *)(v18 + 4);
  if ( v19 )
LABEL_24:
    SetEvent(*((HANDLE *)this + 33));
LABEL_25:
  if ( v17 < 0 )
    goto LABEL_26;
LABEL_27:
  v27 = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\MareBackup",
    L"MareBackupFileCount",
    0x20000010u,
    0,
    a4,
    &v27);
  LODWORD(a5) = 0;
  v21 = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\OneSettings\\MareBackup",
    L"MareBackupKeepHiddenArps",
    0x20000010u,
    0,
    &a5,
    &v21);
  *v5 = (_DWORD)a5 == 1;
  return 0;
}

```

## disassembly

```asm
0x18002b1e0  mov     r11, rsp
0x18002b1e3  mov     [r11+8], rbx
0x18002b1e7  push    rbp
0x18002b1e8  push    rsi
0x18002b1e9  push    rdi
0x18002b1ea  push    r12
0x18002b1ec  push    r13
0x18002b1ee  push    r14
0x18002b1f0  push    r15
0x18002b1f2  mov     rbp, rsp
0x18002b1f5  sub     rsp, 60h
0x18002b1f9  mov     r13, [rbp+arg_20]
0x18002b1fd  lea     rax, [rbp+arg_8]
0x18002b201  xor     esi, esi
0x18002b203  mov     [r11-68h], rax
0x18002b207  mov     [rdx], sil
0x18002b20a  mov     r12, r9
0x18002b20d  mov     [r11-70h], r8
0x18002b211  mov     r15, rdx
0x18002b214  mov     [r13+0], sil
0x18002b218  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002b21f  mov     [r8], rsi
0x18002b222  lea     ebx, [rsi+8]
0x18002b225  mov     [r9], esi
0x18002b228  lea     r8, aMarebackupdefa; "MareBackupDefaultFar"
0x18002b22f  mov     r14, rcx
0x18002b232  mov     [rbp+arg_8], ebx
0x18002b235  mov     edi, 20000040h
0x18002b23a  mov     [r11-78h], rsi
0x18002b23e  mov     r9d, edi; dwFlags
0x18002b241  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002b248  call    cs:__imp_RegGetValueW
0x18002b24e  lea     rax, [rbp+arg_10]
0x18002b252  mov     [rbp+var_18], rsi
0x18002b256  mov     [rsp+60h+pcbData], rax; pcbData
0x18002b25b  lea     r8, aMarebackupfres; "MareBackupFreshJson"
0x18002b262  lea     rax, [rbp+var_18]
0x18002b266  mov     [rbp+arg_10], ebx
0x18002b269  mov     [rsp+60h+pvData], rax; pvData
0x18002b26e  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002b275  mov     r9d, edi; dwFlags
0x18002b278  mov     [rsp+60h+pdwType], rsi; pdwType
0x18002b27d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002b284  call    cs:__imp_RegGetValueW
0x18002b28a  cmp     [rbp+var_18], rsi
0x18002b28e  jz      loc_18002B415
0x18002b294  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002b298  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rsi
0x18002b29c  call    cs:__imp_GetSystemTimeAsFileTime
0x18002b2a2  mov     rdi, [rbp+var_18]
0x18002b2a6  cmp     rdi, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002b2aa  jnb     loc_18002B415
0x18002b2b0  mov     eax, esi
0x18002b2b2  lea     rbx, [r14+0F8h]
0x18002b2b9  lea     rsi, [rbx+24h]
0x18002b2bd  mov     [rbp+var_8], rax
0x18002b2c1  cmp     [r14+0E8h], rax
0x18002b2c8  jz      loc_18002B351
0x18002b2ce  mov     rcx, rbx; this
0x18002b2d1  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x18002b2d6  mov     rcx, [r14+0E8h]
0x18002b2dd  lea     r8, [rbp+var_8]
0x18002b2e1  lea     rdx, aResettimestamp; "ResetTimestamp"
0x18002b2e8  mov     rax, [rcx]
0x18002b2eb  mov     rax, [rax+40h]
0x18002b2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2f4  cmp     byte ptr [rsi], 0
0x18002b2f7  mov     edi, eax
0x18002b2f9  jz      short loc_18002B314
0x18002b2fb  mov     rcx, [rbx+18h]
0x18002b2ff  xor     dl, dl
0x18002b301  cmp     dword ptr [rcx+4], 1
0x18002b305  jnz     short loc_18002B30B
0x18002b307  mov     [rsi], dl
0x18002b309  mov     dl, 1
0x18002b30b  dec     dword ptr [rcx+4]
0x18002b30e  test    dl, dl
0x18002b310  jz      short loc_18002B343
0x18002b312  jmp     short loc_18002B339
0x18002b314  mov     rcx, [rbx]; hHandle
0x18002b317  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002b31a  call    cs:__imp_WaitForSingleObject
0x18002b320  test    eax, eax
0x18002b322  jnz     short loc_18002B343
0x18002b324  mov     rax, [rbx+18h]
0x18002b328  or      ecx, 0FFFFFFFFh
0x18002b32b  add     [rax], ecx
0x18002b32d  add     [rbx+20h], ecx
0x18002b330  mov     rcx, [rbx]; hMutex
0x18002b333  call    cs:__imp_ReleaseMutex
0x18002b339  mov     rcx, [rbx+10h]; hEvent
0x18002b33d  call    cs:__imp_SetEvent
0x18002b343  cmp     di, 2
0x18002b347  mov     rdi, [rbp+var_18]
0x18002b34b  jz      short loc_18002B35A
0x18002b34d  mov     rax, [rbp+var_8]
0x18002b351  cmp     rax, rdi
0x18002b354  jnb     loc_18002B413
0x18002b35a  mov     byte ptr [r15], 1
0x18002b35e  cmp     qword ptr [r14+0E8h], 0
0x18002b366  jnz     short loc_18002B371
0x18002b368  mov     edi, 80004002h
0x18002b36d  xor     esi, esi
0x18002b36f  jmp     short loc_18002B3F0
0x18002b371  mov     rcx, rbx; this
0x18002b374  call    ?AcquireExclusiveLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireExclusiveLock(void)
0x18002b379  mov     rcx, [r14+0E8h]
0x18002b380  lea     rdx, aResettimestamp; "ResetTimestamp"
0x18002b387  mov     r8, rdi
0x18002b38a  mov     rax, [rcx]
0x18002b38d  mov     rax, [rax+58h]
0x18002b391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b396  cmp     byte ptr [rsi], 0
0x18002b399  mov     edi, eax
0x18002b39b  jz      short loc_18002B3B8
0x18002b39d  mov     rcx, [rbx+18h]
0x18002b3a1  xor     al, al
0x18002b3a3  cmp     dword ptr [rcx+4], 1
0x18002b3a7  jnz     short loc_18002B3AD
0x18002b3a9  mov     [rsi], al
0x18002b3ab  mov     al, 1
0x18002b3ad  dec     dword ptr [rcx+4]
0x18002b3b0  xor     esi, esi
0x18002b3b2  test    al, al
0x18002b3b4  jz      short loc_18002B3EC
0x18002b3b6  jmp     short loc_18002B3E2
0x18002b3b8  mov     rcx, [rbx]; hHandle
0x18002b3bb  or      r14d, 0FFFFFFFFh
0x18002b3bf  mov     edx, r14d; dwMilliseconds
0x18002b3c2  call    cs:__imp_WaitForSingleObject
0x18002b3c8  xor     esi, esi
0x18002b3ca  test    eax, eax
0x18002b3cc  jnz     short loc_18002B3EC
0x18002b3ce  mov     rax, [rbx+18h]
0x18002b3d2  add     [rax], r14d
0x18002b3d5  add     [rbx+20h], r14d
0x18002b3d9  mov     rcx, [rbx]; hMutex
0x18002b3dc  call    cs:__imp_ReleaseMutex
0x18002b3e2  mov     rcx, [rbx+10h]; hEvent
0x18002b3e6  call    cs:__imp_SetEvent
0x18002b3ec  test    edi, edi
0x18002b3ee  jns     short loc_18002B415
0x18002b3f0  mov     r8d, 33h ; '3'
0x18002b3f6  mov     dword ptr [rsp+60h+pdwType], edi
0x18002b3fa  lea     r9, aTelcacheprovid_15; "TelCacheProvider::SetMetadata failed [%"...
0x18002b401  lea     rdx, aWindowsCompatI_21; "Windows::Compat::Inventory::MareDataWri"...
0x18002b408  lea     ecx, [r8-32h]
0x18002b40c  call    AslLogCallPrintf
0x18002b411  jmp     short loc_18002B415
0x18002b413  xor     esi, esi
0x18002b415  lea     rax, [rbp+arg_18]
0x18002b419  mov     edi, 20000010h
0x18002b41e  mov     [rsp+60h+pcbData], rax; pcbData
0x18002b423  lea     r8, aMarebackupfile; "MareBackupFileCount"
0x18002b42a  mov     r14, 0FFFFFFFF80000002h
0x18002b431  mov     [rsp+60h+pvData], r12; pvData
0x18002b436  mov     ebx, 4
0x18002b43b  mov     [rsp+60h+pdwType], rsi; pdwType
0x18002b440  mov     r9d, edi; dwFlags
0x18002b443  mov     [rbp+arg_18], ebx
0x18002b446  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002b44d  mov     rcx, r14; hkey
0x18002b450  call    cs:__imp_RegGetValueW
0x18002b456  lea     rax, [rbp+var_20]
0x18002b45a  mov     dword ptr [rbp+arg_20], esi
0x18002b45d  mov     [rsp+60h+pcbData], rax; pcbData
0x18002b462  lea     r8, aMarebackupkeep; "MareBackupKeepHiddenArps"
0x18002b469  lea     rax, [rbp+arg_20]
0x18002b46d  mov     [rbp+var_20], ebx
0x18002b470  mov     [rsp+60h+pvData], rax; pvData
0x18002b475  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002b47c  mov     r9d, edi; dwFlags
0x18002b47f  mov     [rsp+60h+pdwType], rsi; pdwType
0x18002b484  mov     rcx, r14; hkey
0x18002b487  call    cs:__imp_RegGetValueW
0x18002b48d  cmp     dword ptr [rbp+arg_20], 1
0x18002b491  mov     rbx, [rsp+60h+arg_0]
0x18002b499  setz    al
0x18002b49c  mov     [r13+0], al
0x18002b4a0  xor     eax, eax
0x18002b4a2  add     rsp, 60h
0x18002b4a6  pop     r15
0x18002b4a8  pop     r14
0x18002b4aa  pop     r13
0x18002b4ac  pop     r12
0x18002b4ae  pop     rdi
0x18002b4af  pop     rsi
0x18002b4b0  pop     rbp
0x18002b4b1  retn
```
