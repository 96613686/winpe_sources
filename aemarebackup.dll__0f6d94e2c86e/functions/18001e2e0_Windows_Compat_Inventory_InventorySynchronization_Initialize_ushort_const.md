# Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)

- ea: `0x18001e2e0`
- end: `0x18001e501`
- name: `?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001efb4`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000d62c`
- `0x18001e2e0`
- `0x1800256d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e3b7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001e3b7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e4c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001e4c9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001e354`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001e354`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e3cc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001e3cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e46c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e362`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e46c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e31a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e3fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e31a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e380`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e3fa`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001e4a0`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18001e4a0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e45d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18001e45d`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18001e42f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18001e42f`

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
0x18001e2e0  mov     [rsp+arg_10], rbx
0x18001e2e5  push    rsi
0x18001e2e6  push    rdi
0x18001e2e7  push    r14
0x18001e2e9  sub     rsp, 250h
0x18001e2f0  mov     rax, cs:__security_cookie
0x18001e2f7  xor     rax, rsp
0x18001e2fa  mov     [rsp+268h+var_28], rax
0x18001e302  mov     rsi, rdx
0x18001e305  mov     rdi, rcx
0x18001e308  xor     edx, edx; Val
0x18001e30a  lea     rcx, [rsp+268h+Name]; void *
0x18001e30f  mov     r8d, 208h; Size
0x18001e315  call    memset_0
0x18001e31a  call    cs:__imp_GetCurrentProcessId
0x18001e320  mov     r14d, 104h
0x18001e326  lea     r8, aInventorysynch_0; "InventorySynchronization%lsMutex%d"
0x18001e32d  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18001e332  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18001e336  mov     edx, r14d; unsigned __int64
0x18001e339  mov     r9, rsi
0x18001e33c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e341  mov     ebx, eax
0x18001e343  test    eax, eax
0x18001e345  js      loc_18001E4D3
0x18001e34b  lea     r8, [rsp+268h+Name]; lpName
0x18001e350  xor     edx, edx; bInitialOwner
0x18001e352  xor     ecx, ecx; lpMutexAttributes
0x18001e354  call    cs:__imp_CreateMutexW
0x18001e35a  mov     [rdi], rax
0x18001e35d  test    rax, rax
0x18001e360  jnz     short loc_18001E380
0x18001e362  call    cs:__imp_GetLastError
0x18001e368  mov     ebx, eax
0x18001e36a  test    eax, eax
0x18001e36c  jle     loc_18001E4CF
0x18001e372  movzx   ebx, ax
0x18001e375  or      ebx, 80070000h
0x18001e37b  jmp     loc_18001E4CF
0x18001e380  call    cs:__imp_GetCurrentProcessId
0x18001e386  mov     r9, rsi
0x18001e389  lea     r8, aInventorysynch; "InventorySynchronization%lsEvent%d"
0x18001e390  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18001e395  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18001e399  mov     rdx, r14; unsigned __int64
0x18001e39c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e3a1  mov     ebx, eax
0x18001e3a3  test    eax, eax
0x18001e3a5  js      loc_18001E4D3
0x18001e3ab  lea     r9, [rsp+268h+Name]; lpName
0x18001e3b0  xor     r8d, r8d; bInitialState
0x18001e3b3  xor     edx, edx; bManualReset
0x18001e3b5  xor     ecx, ecx; lpEventAttributes
0x18001e3b7  call    cs:__imp_CreateEventW
0x18001e3bd  mov     [rdi+10h], rax
0x18001e3c1  test    rax, rax
0x18001e3c4  jz      short loc_18001E362
0x18001e3c6  mov     rcx, [rdi]; hHandle
0x18001e3c9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001e3cc  call    cs:__imp_WaitForSingleObject
0x18001e3d2  test    eax, eax
0x18001e3d4  jz      short loc_18001E3FA
0x18001e3d6  call    cs:__imp_GetLastError
0x18001e3dc  mov     ebx, eax
0x18001e3de  test    eax, eax
0x18001e3e0  jle     short loc_18001E3EB
0x18001e3e2  movzx   ebx, ax
0x18001e3e5  or      ebx, 80070000h
0x18001e3eb  test    ebx, ebx
0x18001e3ed  mov     eax, 80004005h
0x18001e3f2  cmovns  ebx, eax
0x18001e3f5  jmp     loc_18001E4D3
0x18001e3fa  call    cs:__imp_GetCurrentProcessId
0x18001e400  mov     r9, rsi
0x18001e403  lea     r8, aInventorysynch_1; "InventorySynchronization%lsMemory%d"
0x18001e40a  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18001e40f  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18001e413  mov     rdx, r14; unsigned __int64
0x18001e416  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e41b  mov     ebx, eax
0x18001e41d  test    eax, eax
0x18001e41f  js      loc_18001E4C6
0x18001e425  xor     edx, edx; bInheritHandle
0x18001e427  lea     r8, [rsp+268h+Name]; lpName
0x18001e42c  lea     ecx, [rdx+2]; dwDesiredAccess
0x18001e42f  call    cs:__imp_OpenFileMappingW
0x18001e435  mov     [rdi+8], rax
0x18001e439  test    rax, rax
0x18001e43c  jnz     short loc_18001E487
0x18001e43e  xor     r9d, r9d; dwMaximumSizeHigh
0x18001e441  lea     rax, [rsp+268h+Name]
0x18001e446  mov     [rsp+268h+lpName], rax; lpName
0x18001e44b  xor     edx, edx; lpFileMappingAttributes
0x18001e44d  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18001e451  mov     [rsp+268h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x18001e459  lea     r8d, [r9+4]; flProtect
0x18001e45d  call    cs:__imp_CreateFileMappingW
0x18001e463  mov     [rdi+8], rax
0x18001e467  test    rax, rax
0x18001e46a  jnz     short loc_18001E483
0x18001e46c  call    cs:__imp_GetLastError
0x18001e472  mov     ebx, eax
0x18001e474  test    eax, eax
0x18001e476  jle     short loc_18001E4C6
0x18001e478  movzx   ebx, ax
0x18001e47b  or      ebx, 80070000h
0x18001e481  jmp     short loc_18001E4C6
0x18001e483  xor     bl, bl
0x18001e485  jmp     short loc_18001E489
0x18001e487  mov     bl, 1
0x18001e489  xor     r9d, r9d; dwFileOffsetLow
0x18001e48c  mov     qword ptr [rsp+268h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18001e495  xor     r8d, r8d; dwFileOffsetHigh
0x18001e498  mov     edx, 0F001Fh; dwDesiredAccess
0x18001e49d  mov     rcx, rax; hFileMappingObject
0x18001e4a0  call    cs:__imp_MapViewOfFile
0x18001e4a6  mov     [rdi+18h], rax
0x18001e4aa  test    rax, rax
0x18001e4ad  jz      short loc_18001E46C
0x18001e4af  test    bl, bl
0x18001e4b1  jnz     short loc_18001E4C4
0x18001e4b3  mov     dword ptr [rax], 0
0x18001e4b9  mov     rax, [rdi+18h]
0x18001e4bd  mov     dword ptr [rax+4], 0
0x18001e4c4  xor     ebx, ebx
0x18001e4c6  mov     rcx, [rdi]; hMutex
0x18001e4c9  call    cs:__imp_ReleaseMutex
0x18001e4cf  test    ebx, ebx
0x18001e4d1  jns     short loc_18001E4DB
0x18001e4d3  mov     rcx, rdi; this
0x18001e4d6  call    ?Uninitialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::Uninitialize(void)
0x18001e4db  mov     eax, ebx
0x18001e4dd  mov     rcx, [rsp+268h+var_28]
0x18001e4e5  xor     rcx, rsp; StackCookie
0x18001e4e8  call    __security_check_cookie
0x18001e4ed  mov     rbx, [rsp+268h+arg_10]
0x18001e4f5  add     rsp, 250h
0x18001e4fc  pop     r14
0x18001e4fe  pop     rdi
0x18001e4ff  pop     rsi
0x18001e500  retn
```
