# Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)

- ea: `0x180026818`
- end: `0x180026a39`
- name: `?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800272dc`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x18000f7bc`
- `0x180026818`
- `0x18002d088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800268ef`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800268ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026a01`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180026a01`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026904`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180026904`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002688c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18002688c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002689a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002690e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002689a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002690e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026852`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800268b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026852`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800268b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026932`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180026967`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x180026967`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800269d8`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800269d8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180026995`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180026995`

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
0x180026818  mov     [rsp+arg_10], rbx
0x18002681d  push    rsi
0x18002681e  push    rdi
0x18002681f  push    r14
0x180026821  sub     rsp, 250h
0x180026828  mov     rax, cs:__security_cookie
0x18002682f  xor     rax, rsp
0x180026832  mov     [rsp+268h+var_28], rax
0x18002683a  mov     rsi, rdx
0x18002683d  mov     rdi, rcx
0x180026840  xor     edx, edx; Val
0x180026842  lea     rcx, [rsp+268h+Name]; void *
0x180026847  mov     r8d, 208h; Size
0x18002684d  call    memset_0
0x180026852  call    cs:__imp_GetCurrentProcessId
0x180026858  mov     r14d, 104h
0x18002685e  lea     r8, aInventorysynch_0; "InventorySynchronization%lsMutex%d"
0x180026865  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18002686a  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18002686e  mov     edx, r14d; unsigned __int64
0x180026871  mov     r9, rsi
0x180026874  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026879  mov     ebx, eax
0x18002687b  test    eax, eax
0x18002687d  js      loc_180026A0B
0x180026883  lea     r8, [rsp+268h+Name]; lpName
0x180026888  xor     edx, edx; bInitialOwner
0x18002688a  xor     ecx, ecx; lpMutexAttributes
0x18002688c  call    cs:__imp_CreateMutexW
0x180026892  mov     [rdi], rax
0x180026895  test    rax, rax
0x180026898  jnz     short loc_1800268B8
0x18002689a  call    cs:__imp_GetLastError
0x1800268a0  mov     ebx, eax
0x1800268a2  test    eax, eax
0x1800268a4  jle     loc_180026A07
0x1800268aa  movzx   ebx, ax
0x1800268ad  or      ebx, 80070000h
0x1800268b3  jmp     loc_180026A07
0x1800268b8  call    cs:__imp_GetCurrentProcessId
0x1800268be  mov     r9, rsi
0x1800268c1  lea     r8, aInventorysynch; "InventorySynchronization%lsEvent%d"
0x1800268c8  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x1800268cd  mov     [rsp+268h+dwMaximumSizeLow], eax
0x1800268d1  mov     rdx, r14; unsigned __int64
0x1800268d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800268d9  mov     ebx, eax
0x1800268db  test    eax, eax
0x1800268dd  js      loc_180026A0B
0x1800268e3  lea     r9, [rsp+268h+Name]; lpName
0x1800268e8  xor     r8d, r8d; bInitialState
0x1800268eb  xor     edx, edx; bManualReset
0x1800268ed  xor     ecx, ecx; lpEventAttributes
0x1800268ef  call    cs:__imp_CreateEventW
0x1800268f5  mov     [rdi+10h], rax
0x1800268f9  test    rax, rax
0x1800268fc  jz      short loc_18002689A
0x1800268fe  mov     rcx, [rdi]; hHandle
0x180026901  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180026904  call    cs:__imp_WaitForSingleObject
0x18002690a  test    eax, eax
0x18002690c  jz      short loc_180026932
0x18002690e  call    cs:__imp_GetLastError
0x180026914  mov     ebx, eax
0x180026916  test    eax, eax
0x180026918  jle     short loc_180026923
0x18002691a  movzx   ebx, ax
0x18002691d  or      ebx, 80070000h
0x180026923  test    ebx, ebx
0x180026925  mov     eax, 80004005h
0x18002692a  cmovns  ebx, eax
0x18002692d  jmp     loc_180026A0B
0x180026932  call    cs:__imp_GetCurrentProcessId
0x180026938  mov     r9, rsi
0x18002693b  lea     r8, aInventorysynch_1; "InventorySynchronization%lsMemory%d"
0x180026942  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180026947  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18002694b  mov     rdx, r14; unsigned __int64
0x18002694e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026953  mov     ebx, eax
0x180026955  test    eax, eax
0x180026957  js      loc_1800269FE
0x18002695d  xor     edx, edx; bInheritHandle
0x18002695f  lea     r8, [rsp+268h+Name]; lpName
0x180026964  lea     ecx, [rdx+2]; dwDesiredAccess
0x180026967  call    cs:__imp_OpenFileMappingW
0x18002696d  mov     [rdi+8], rax
0x180026971  test    rax, rax
0x180026974  jnz     short loc_1800269BF
0x180026976  xor     r9d, r9d; dwMaximumSizeHigh
0x180026979  lea     rax, [rsp+268h+Name]
0x18002697e  mov     [rsp+268h+lpName], rax; lpName
0x180026983  xor     edx, edx; lpFileMappingAttributes
0x180026985  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180026989  mov     [rsp+268h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x180026991  lea     r8d, [r9+4]; flProtect
0x180026995  call    cs:__imp_CreateFileMappingW
0x18002699b  mov     [rdi+8], rax
0x18002699f  test    rax, rax
0x1800269a2  jnz     short loc_1800269BB
0x1800269a4  call    cs:__imp_GetLastError
0x1800269aa  mov     ebx, eax
0x1800269ac  test    eax, eax
0x1800269ae  jle     short loc_1800269FE
0x1800269b0  movzx   ebx, ax
0x1800269b3  or      ebx, 80070000h
0x1800269b9  jmp     short loc_1800269FE
0x1800269bb  xor     bl, bl
0x1800269bd  jmp     short loc_1800269C1
0x1800269bf  mov     bl, 1
0x1800269c1  xor     r9d, r9d; dwFileOffsetLow
0x1800269c4  mov     qword ptr [rsp+268h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x1800269cd  xor     r8d, r8d; dwFileOffsetHigh
0x1800269d0  mov     edx, 0F001Fh; dwDesiredAccess
0x1800269d5  mov     rcx, rax; hFileMappingObject
0x1800269d8  call    cs:__imp_MapViewOfFile
0x1800269de  mov     [rdi+18h], rax
0x1800269e2  test    rax, rax
0x1800269e5  jz      short loc_1800269A4
0x1800269e7  test    bl, bl
0x1800269e9  jnz     short loc_1800269FC
0x1800269eb  mov     dword ptr [rax], 0
0x1800269f1  mov     rax, [rdi+18h]
0x1800269f5  mov     dword ptr [rax+4], 0
0x1800269fc  xor     ebx, ebx
0x1800269fe  mov     rcx, [rdi]; hMutex
0x180026a01  call    cs:__imp_ReleaseMutex
0x180026a07  test    ebx, ebx
0x180026a09  jns     short loc_180026A13
0x180026a0b  mov     rcx, rdi; this
0x180026a0e  call    ?Uninitialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::Uninitialize(void)
0x180026a13  mov     eax, ebx
0x180026a15  mov     rcx, [rsp+268h+var_28]
0x180026a1d  xor     rcx, rsp; StackCookie
0x180026a20  call    __security_check_cookie
0x180026a25  mov     rbx, [rsp+268h+arg_10]
0x180026a2d  add     rsp, 250h
0x180026a34  pop     r14
0x180026a36  pop     rdi
0x180026a37  pop     rsi
0x180026a38  retn
```
