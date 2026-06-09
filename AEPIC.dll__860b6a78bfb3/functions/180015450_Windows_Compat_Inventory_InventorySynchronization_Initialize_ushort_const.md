# Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)

- ea: `0x180015450`
- end: `0x180015671`
- name: `?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180015cf0`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb74`
- `0x180015450`
- `0x18001b9a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800154c4`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800154c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001553c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001553c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015527`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180015527`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015639`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800154d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001548a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800154f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001556a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001548a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800154f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001556a`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18001559f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18001559f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800155cd`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800155cd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180015610`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180015610`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::InventorySynchronization::Initialize(
        Windows::Compat::Inventory::InventorySynchronization *this,
        const unsigned __int16 *a2)
{
  signed int v4; // ebx
  HANDLE MutexW; // rax
  signed int v6; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE FileMappingW; // rax
  signed int v10; // eax
  char v11; // bl
  _DWORD *v12; // rax
  DWORD dwMaximumSizeLowb; // [rsp+20h] [rbp-248h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-248h]
  DWORD dwMaximumSizeLowa[2]; // [rsp+20h] [rbp-248h]
  WCHAR Name[264]; // [rsp+30h] [rbp-238h] BYREF

  memset_0(Name, 0, 0x208u);
  dwMaximumSizeLowb = GetCurrentProcessId();
  v4 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsMutex%d", a2, dwMaximumSizeLowb);
  if ( v4 < 0 )
    goto LABEL_26;
  MutexW = CreateMutexW(0, 0, Name);
  *(_QWORD *)this = MutexW;
  if ( MutexW )
  {
    dwMaximumSizeLow[0] = GetCurrentProcessId();
    v4 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsEvent%d", a2, *(_QWORD *)dwMaximumSizeLow);
    if ( v4 < 0 )
    {
LABEL_26:
      Windows::Compat::Inventory::InventorySynchronization::Uninitialize(this);
      return (unsigned int)v4;
    }
    EventW = CreateEventW(0, 0, 0, Name);
    *((_QWORD *)this + 2) = EventW;
    if ( EventW )
    {
      if ( WaitForSingleObject(*(HANDLE *)this, 0xFFFFFFFF) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( v4 >= 0 )
          v4 = -2147467259;
        goto LABEL_26;
      }
      dwMaximumSizeLowa[0] = GetCurrentProcessId();
      v4 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsMemory%d", a2, *(_QWORD *)dwMaximumSizeLowa);
      if ( v4 < 0 )
        goto LABEL_24;
      FileMappingW = OpenFileMappingW(2u, 0, Name);
      *((_QWORD *)this + 1) = FileMappingW;
      if ( FileMappingW )
      {
        v11 = 1;
      }
      else
      {
        FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 8u, Name);
        *((_QWORD *)this + 1) = FileMappingW;
        if ( !FileMappingW )
          goto LABEL_16;
        v11 = 0;
      }
      v12 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
      *((_QWORD *)this + 3) = v12;
      if ( v12 )
      {
        if ( !v11 )
        {
          *v12 = 0;
          *(_DWORD *)(*((_QWORD *)this + 3) + 4LL) = 0;
        }
        v4 = 0;
        goto LABEL_24;
      }
LABEL_16:
      v10 = GetLastError();
      v4 = v10;
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
LABEL_24:
      ReleaseMutex(*(HANDLE *)this);
      goto LABEL_25;
    }
  }
  v6 = GetLastError();
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
LABEL_25:
  if ( v4 < 0 )
    goto LABEL_26;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015450  mov     [rsp+arg_10], rbx
0x180015455  push    rsi
0x180015456  push    rdi
0x180015457  push    r14
0x180015459  sub     rsp, 250h
0x180015460  mov     rax, cs:__security_cookie
0x180015467  xor     rax, rsp
0x18001546a  mov     [rsp+268h+var_28], rax
0x180015472  mov     rsi, rdx
0x180015475  mov     rdi, rcx
0x180015478  xor     edx, edx; Val
0x18001547a  lea     rcx, [rsp+268h+Name]; void *
0x18001547f  mov     r8d, 208h; Size
0x180015485  call    memset_0
0x18001548a  call    cs:__imp_GetCurrentProcessId
0x180015490  mov     r14d, 104h
0x180015496  lea     r8, aInventorysynch_0; "InventorySynchronization%lsMutex%d"
0x18001549d  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x1800154a2  mov     [rsp+268h+dwMaximumSizeLow], eax
0x1800154a6  mov     edx, r14d; unsigned __int64
0x1800154a9  mov     r9, rsi
0x1800154ac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800154b1  mov     ebx, eax
0x1800154b3  test    eax, eax
0x1800154b5  js      loc_180015643
0x1800154bb  lea     r8, [rsp+268h+Name]; lpName
0x1800154c0  xor     edx, edx; bInitialOwner
0x1800154c2  xor     ecx, ecx; lpMutexAttributes
0x1800154c4  call    cs:__imp_CreateMutexW
0x1800154ca  mov     [rdi], rax
0x1800154cd  test    rax, rax
0x1800154d0  jnz     short loc_1800154F0
0x1800154d2  call    cs:__imp_GetLastError
0x1800154d8  mov     ebx, eax
0x1800154da  test    eax, eax
0x1800154dc  jle     loc_18001563F
0x1800154e2  movzx   ebx, ax
0x1800154e5  or      ebx, 80070000h
0x1800154eb  jmp     loc_18001563F
0x1800154f0  call    cs:__imp_GetCurrentProcessId
0x1800154f6  mov     r9, rsi
0x1800154f9  lea     r8, aInventorysynch; "InventorySynchronization%lsEvent%d"
0x180015500  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180015505  mov     [rsp+268h+dwMaximumSizeLow], eax
0x180015509  mov     rdx, r14; unsigned __int64
0x18001550c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015511  mov     ebx, eax
0x180015513  test    eax, eax
0x180015515  js      loc_180015643
0x18001551b  lea     r9, [rsp+268h+Name]; lpName
0x180015520  xor     r8d, r8d; bInitialState
0x180015523  xor     edx, edx; bManualReset
0x180015525  xor     ecx, ecx; lpEventAttributes
0x180015527  call    cs:__imp_CreateEventW
0x18001552d  mov     [rdi+10h], rax
0x180015531  test    rax, rax
0x180015534  jz      short loc_1800154D2
0x180015536  mov     rcx, [rdi]; hHandle
0x180015539  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001553c  call    cs:__imp_WaitForSingleObject
0x180015542  test    eax, eax
0x180015544  jz      short loc_18001556A
0x180015546  call    cs:__imp_GetLastError
0x18001554c  mov     ebx, eax
0x18001554e  test    eax, eax
0x180015550  jle     short loc_18001555B
0x180015552  movzx   ebx, ax
0x180015555  or      ebx, 80070000h
0x18001555b  test    ebx, ebx
0x18001555d  mov     eax, 80004005h
0x180015562  cmovns  ebx, eax
0x180015565  jmp     loc_180015643
0x18001556a  call    cs:__imp_GetCurrentProcessId
0x180015570  mov     r9, rsi
0x180015573  lea     r8, aInventorysynch_1; "InventorySynchronization%lsMemory%d"
0x18001557a  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18001557f  mov     [rsp+268h+dwMaximumSizeLow], eax
0x180015583  mov     rdx, r14; unsigned __int64
0x180015586  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001558b  mov     ebx, eax
0x18001558d  test    eax, eax
0x18001558f  js      loc_180015636
0x180015595  xor     edx, edx; bInheritHandle
0x180015597  lea     r8, [rsp+268h+Name]; lpName
0x18001559c  lea     ecx, [rdx+2]; dwDesiredAccess
0x18001559f  call    cs:__imp_OpenFileMappingW
0x1800155a5  mov     [rdi+8], rax
0x1800155a9  test    rax, rax
0x1800155ac  jnz     short loc_1800155F7
0x1800155ae  xor     r9d, r9d; dwMaximumSizeHigh
0x1800155b1  lea     rax, [rsp+268h+Name]
0x1800155b6  mov     [rsp+268h+lpName], rax; lpName
0x1800155bb  xor     edx, edx; lpFileMappingAttributes
0x1800155bd  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1800155c1  mov     [rsp+268h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x1800155c9  lea     r8d, [r9+4]; flProtect
0x1800155cd  call    cs:__imp_CreateFileMappingW
0x1800155d3  mov     [rdi+8], rax
0x1800155d7  test    rax, rax
0x1800155da  jnz     short loc_1800155F3
0x1800155dc  call    cs:__imp_GetLastError
0x1800155e2  mov     ebx, eax
0x1800155e4  test    eax, eax
0x1800155e6  jle     short loc_180015636
0x1800155e8  movzx   ebx, ax
0x1800155eb  or      ebx, 80070000h
0x1800155f1  jmp     short loc_180015636
0x1800155f3  xor     bl, bl
0x1800155f5  jmp     short loc_1800155F9
0x1800155f7  mov     bl, 1
0x1800155f9  xor     r9d, r9d; dwFileOffsetLow
0x1800155fc  mov     qword ptr [rsp+268h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180015605  xor     r8d, r8d; dwFileOffsetHigh
0x180015608  mov     edx, 0F001Fh; dwDesiredAccess
0x18001560d  mov     rcx, rax; hFileMappingObject
0x180015610  call    cs:__imp_MapViewOfFile
0x180015616  mov     [rdi+18h], rax
0x18001561a  test    rax, rax
0x18001561d  jz      short loc_1800155DC
0x18001561f  test    bl, bl
0x180015621  jnz     short loc_180015634
0x180015623  mov     dword ptr [rax], 0
0x180015629  mov     rax, [rdi+18h]
0x18001562d  mov     dword ptr [rax+4], 0
0x180015634  xor     ebx, ebx
0x180015636  mov     rcx, [rdi]; hMutex
0x180015639  call    cs:__imp_ReleaseMutex
0x18001563f  test    ebx, ebx
0x180015641  jns     short loc_18001564B
0x180015643  mov     rcx, rdi; this
0x180015646  call    ?Uninitialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::Uninitialize(void)
0x18001564b  mov     eax, ebx
0x18001564d  mov     rcx, [rsp+268h+var_28]
0x180015655  xor     rcx, rsp; StackCookie
0x180015658  call    __security_check_cookie
0x18001565d  mov     rbx, [rsp+268h+arg_10]
0x180015665  add     rsp, 250h
0x18001566c  pop     r14
0x18001566e  pop     rdi
0x18001566f  pop     rsi
0x180015670  retn
```
