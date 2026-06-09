# BipRemoveStaleUserDataCallback

- ea: `0x180083ea0`
- end: `0x1800840dd`
- name: `BipRemoveStaleUserDataCallback`
- size: `573`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004474`
- `0x18000a430`
- `0x18000d7c0`
- `0x18000da50`
- `0x1800121b0`
- `0x18004d764`
- `0x180083ea0`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x180083fc1`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180083fc1`
- `ntdll!RtlCreateHashTable` at `0x180083efb`
- `ntdll!RtlCreateHashTable` at `0x180083efb`
- `ntdll!RtlInsertEntryHashTable` at `0x180084017`
- `ntdll!RtlInsertEntryHashTable` at `0x180084017`
- `ntdll!RtlFreeHeap` at `0x180084079`
- `ntdll!RtlFreeHeap` at `0x180084079`
- `ntdll!RtlAllocateHeap` at `0x180083fea`
- `ntdll!RtlAllocateHeap` at `0x180083fea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083f4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083f41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083f4e`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180083f7d`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180083f7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084089`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180084089`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083f2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180083f2a`

## pseudocode

```c
char __fastcall BipRemoveStaleUserDataCallback(__int64 a1, __int64 a2)
{
  char result; // al
  PVOID Heap; // rdi
  unsigned int LastError; // ebx
  DWORD i; // esi
  LSTATUS v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rbx
  __int64 v10; // r15
  WCHAR *v11; // rdi
  unsigned int j; // r14d
  WCHAR v13; // ax
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v19; // [rsp+50h] [rbp-B0h]
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  v19 = 0;
  v18 = 0;
  hKey = 0;
  v16 = 0;
  BipStorageSynchronizeWithInitialization();
  result = RtlCreateHashTable(&v16, 0, 0);
  if ( result )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
           0,
           0x20019u,
           &hKey) )
    {
      Heap = 0;
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        Name[0] = 0;
        v7 = RegEnumKeyW(hKey, i, Name, 0x104u);
        LastError = v7;
        if ( v7 == 259 )
          break;
        if ( v7 )
          goto LABEL_18;
        v9 = -1;
        do
          ++v9;
        while ( Name[v9] );
        v10 = qword_1800C4148;
        v11 = Name;
        for ( j = 0; j < (unsigned int)v9; ++j )
        {
          v13 = RtlUpcaseUnicodeChar(*v11++);
          v10 = v13 + 39 * v10;
        }
        Heap = RtlAllocateHeap(BipHeap, 0, 0x18u);
        if ( Heap )
        {
          v19 = 0;
          v18 = 0;
          if ( (unsigned __int8)RtlInsertEntryHashTable(v16, Heap, v10, &v18) )
            continue;
        }
        LastError = -1073741801;
        goto LABEL_19;
      }
      BipAcquireGlobalLock(v8);
      BipEnumeratePackagesWithCallback(BipRemoveStalePackageInfo, v16);
      BipLockWatchdogContextDisarmWatchdog(v14);
      LOBYTE(v15) = 1;
      BipSyncReleaseLock(&BipGlobalLock, v15);
      LastError = 0;
LABEL_18:
      Heap = 0;
    }
LABEL_19:
    result = BipCleanupHashTable(v16);
    if ( Heap )
      result = RtlFreeHeap(BipHeap, 0, Heap);
    if ( hKey )
      result = RegCloseKey(hKey);
    if ( a2 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, LastError | 0x10000000);
      return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180083ea0  push    rbp
0x180083ea2  push    rbx
0x180083ea3  push    rsi
0x180083ea4  push    rdi
0x180083ea5  push    r12
0x180083ea7  push    r13
0x180083ea9  push    r14
0x180083eab  push    r15
0x180083ead  lea     rbp, [rsp-188h]
0x180083eb5  sub     rsp, 288h
0x180083ebc  mov     rax, cs:__security_cookie
0x180083ec3  xor     rax, rsp
0x180083ec6  mov     [rbp+1C0h+var_50], rax
0x180083ecd  xorps   xmm0, xmm0
0x180083ed0  xor     eax, eax
0x180083ed2  xor     r13d, r13d
0x180083ed5  mov     [rsp+2C0h+var_270], rax
0x180083eda  movups  [rsp+2C0h+var_280], xmm0
0x180083edf  mov     [rsp+2C0h+hKey], r13
0x180083ee4  mov     r12, rdx
0x180083ee7  mov     [rsp+2C0h+var_290], r13
0x180083eec  call    BipStorageSynchronizeWithInitialization
0x180083ef1  xor     r8d, r8d
0x180083ef4  lea     rcx, [rsp+2C0h+var_290]
0x180083ef9  xor     edx, edx
0x180083efb  call    cs:__imp_RtlCreateHashTable
0x180083f01  test    al, al
0x180083f03  jz      loc_1800840BA
0x180083f09  lea     rax, [rsp+2C0h+hKey]
0x180083f0e  mov     r9d, 20019h; samDesired
0x180083f14  xor     r8d, r8d; ulOptions
0x180083f17  mov     [rsp+2C0h+phkResult], rax; phkResult
0x180083f1c  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180083f23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180083f2a  call    cs:__imp_RegOpenKeyExW
0x180083f30  test    eax, eax
0x180083f32  jz      short loc_180083F62
0x180083f34  mov     edi, r13d
0x180083f37  call    cs:__imp_GetLastError
0x180083f3d  test    eax, eax
0x180083f3f  jg      short loc_180083F4E
0x180083f41  call    cs:__imp_GetLastError
0x180083f47  mov     ebx, eax
0x180083f49  jmp     loc_18008405E
0x180083f4e  call    cs:__imp_GetLastError
0x180083f54  movzx   ebx, ax
0x180083f57  or      ebx, 0C0070000h
0x180083f5d  jmp     loc_18008405E
0x180083f62  mov     esi, r13d
0x180083f65  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180083f6a  lea     r8, [rsp+2C0h+Name]; lpName
0x180083f6f  mov     r9d, 104h; cchName
0x180083f75  mov     [rsp+2C0h+Name], r13w
0x180083f7b  mov     edx, esi; dwIndex
0x180083f7d  call    cs:__imp_RegEnumKeyW
0x180083f83  mov     ebx, eax
0x180083f85  cmp     eax, 103h
0x180083f8a  jz      loc_18008402F
0x180083f90  test    eax, eax
0x180083f92  jnz     loc_18008405B
0x180083f98  lea     rax, [rsp+2C0h+Name]
0x180083f9d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180083fa1  inc     rbx
0x180083fa4  cmp     [rax+rbx*2], r13w
0x180083fa9  jnz     short loc_180083FA1
0x180083fab  mov     r15, cs:qword_1800C4148
0x180083fb2  lea     rdi, [rsp+2C0h+Name]
0x180083fb7  mov     r14d, r13d
0x180083fba  test    ebx, ebx
0x180083fbc  jz      short loc_180083FDD
0x180083fbe  movzx   ecx, word ptr [rdi]; Source
0x180083fc1  call    cs:__imp_RtlUpcaseUnicodeChar
0x180083fc7  imul    r15, 27h ; '''
0x180083fcb  movzx   ecx, ax
0x180083fce  lea     rdi, [rdi+2]
0x180083fd2  add     r15, rcx
0x180083fd5  inc     r14d
0x180083fd8  cmp     r14d, ebx
0x180083fdb  jb      short loc_180083FBE
0x180083fdd  mov     rcx, cs:BipHeap; HeapHandle
0x180083fe4  xor     edx, edx; Flags
0x180083fe6  lea     r8d, [rdx+18h]; Size
0x180083fea  call    cs:__imp_RtlAllocateHeap
0x180083ff0  mov     rdi, rax
0x180083ff3  test    rax, rax
0x180083ff6  jz      short loc_180084028
0x180083ff8  mov     rcx, [rsp+2C0h+var_290]
0x180083ffd  lea     r9, [rsp+2C0h+var_280]
0x180084002  xorps   xmm0, xmm0
0x180084005  xor     eax, eax
0x180084007  mov     r8, r15
0x18008400a  mov     [rsp+2C0h+var_270], rax
0x18008400f  mov     rdx, rdi
0x180084012  movups  [rsp+2C0h+var_280], xmm0
0x180084017  call    cs:__imp_RtlInsertEntryHashTable
0x18008401d  test    al, al
0x18008401f  jz      short loc_180084028
0x180084021  inc     esi
0x180084023  jmp     loc_180083F65
0x180084028  mov     ebx, 0C0000017h
0x18008402d  jmp     short loc_18008405E
0x18008402f  call    BipAcquireGlobalLock
0x180084034  mov     rdx, [rsp+2C0h+var_290]
0x180084039  lea     rcx, ?BipRemoveStalePackageInfo@@YAXPEAU_BI_PACKAGE@@PEAX@Z; BipRemoveStalePackageInfo(_BI_PACKAGE *,void *)
0x180084040  call    BipEnumeratePackagesWithCallback
0x180084045  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18008404a  mov     dl, 1
0x18008404c  lea     rcx, BipGlobalLock
0x180084053  call    BipSyncReleaseLock
0x180084058  mov     ebx, r13d
0x18008405b  mov     rdi, r13
0x18008405e  mov     rcx, [rsp+2C0h+var_290]
0x180084063  call    BipCleanupHashTable
0x180084068  test    rdi, rdi
0x18008406b  jz      short loc_18008407F
0x18008406d  mov     rcx, cs:BipHeap; HeapHandle
0x180084074  mov     r8, rdi; P
0x180084077  xor     edx, edx; Flags
0x180084079  call    cs:__imp_RtlFreeHeap
0x18008407f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180084084  test    rcx, rcx
0x180084087  jz      short loc_18008408F
0x180084089  call    cs:__imp_RegCloseKey
0x18008408f  test    r12, r12
0x180084092  jz      short loc_1800840BA
0x180084094  mov     rax, [r12]
0x180084098  bts     ebx, 1Ch
0x18008409c  mov     edx, ebx
0x18008409e  mov     rcx, r12
0x1800840a1  mov     rax, [rax+20h]
0x1800840a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800840aa  mov     rax, [r12]
0x1800840ae  mov     rcx, r12
0x1800840b1  mov     rax, [rax+10h]
0x1800840b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800840ba  mov     rcx, [rbp+1C0h+var_50]
0x1800840c1  xor     rcx, rsp; StackCookie
0x1800840c4  call    __security_check_cookie
0x1800840c9  add     rsp, 288h
0x1800840d0  pop     r15
0x1800840d2  pop     r14
0x1800840d4  pop     r13
0x1800840d6  pop     r12
0x1800840d8  pop     rdi
0x1800840d9  pop     rsi
0x1800840da  pop     rbx
0x1800840db  pop     rbp
0x1800840dc  retn
```
