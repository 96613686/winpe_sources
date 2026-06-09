# Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)

- ea: `0x180106840`
- end: `0x180106a6f`
- name: `?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `559`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801072ac`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x180106840`
- `0x18010b7f0`

## import_xrefs

- `KERNEL32!OpenFileMappingW` at `0x18010699b`
- `KERNEL32!OpenFileMappingW` at `0x18010699b`
- `KERNEL32!CreateFileMappingW` at `0x1801069c9`
- `KERNEL32!CreateFileMappingW` at `0x1801069c9`
- `KERNEL32!MapViewOfFile` at `0x180106a0c`
- `KERNEL32!MapViewOfFile` at `0x180106a0c`
- `KERNEL32!CreateMutexW` at `0x1801068b8`
- `KERNEL32!CreateMutexW` at `0x1801068b8`
- `KERNEL32!CreateEventW` at `0x18010691f`
- `KERNEL32!CreateEventW` at `0x18010691f`
- `KERNEL32!GetCurrentProcessId` at `0x18010687a`
- `KERNEL32!GetCurrentProcessId` at `0x1801068e4`
- `KERNEL32!GetCurrentProcessId` at `0x180106962`
- `KERNEL32!GetCurrentProcessId` at `0x18010687a`
- `KERNEL32!GetCurrentProcessId` at `0x1801068e4`
- `KERNEL32!GetCurrentProcessId` at `0x180106962`
- `KERNEL32!GetLastError` at `0x1801068c6`
- `KERNEL32!GetLastError` at `0x18010693e`
- `KERNEL32!GetLastError` at `0x1801069d8`
- `KERNEL32!GetLastError` at `0x1801068c6`
- `KERNEL32!GetLastError` at `0x18010693e`
- `KERNEL32!GetLastError` at `0x1801069d8`
- `KERNEL32!ReleaseMutex` at `0x180106a35`
- `KERNEL32!ReleaseMutex` at `0x180106a35`
- `KERNEL32!WaitForSingleObject` at `0x180106934`
- `KERNEL32!WaitForSingleObject` at `0x180106934`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::InventorySynchronization::Initialize(
        Windows::Compat::Inventory::InventorySynchronization *this,
        const unsigned __int16 *a2)
{
  signed int v3; // ebx
  HANDLE MutexW; // rax
  signed int v5; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE FileMappingW; // rax
  signed int v9; // eax
  char v10; // bl
  _DWORD *v11; // rax
  DWORD dwMaximumSizeLowb; // [rsp+20h] [rbp-238h]
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-238h]
  DWORD dwMaximumSizeLowa[2]; // [rsp+20h] [rbp-238h]
  WCHAR Name[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Name, 0, 0x208u);
  dwMaximumSizeLowb = GetCurrentProcessId();
  v3 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsMutex%d", L"Mare", dwMaximumSizeLowb);
  if ( v3 < 0 )
    goto LABEL_26;
  MutexW = CreateMutexW(0, 0, Name);
  *(_QWORD *)this = MutexW;
  if ( MutexW )
  {
    dwMaximumSizeLow[0] = GetCurrentProcessId();
    v3 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsEvent%d", L"Mare", *(_QWORD *)dwMaximumSizeLow);
    if ( v3 < 0 )
    {
LABEL_26:
      Windows::Compat::Inventory::InventorySynchronization::Uninitialize(this);
      return (unsigned int)v3;
    }
    EventW = CreateEventW(0, 0, 0, Name);
    *((_QWORD *)this + 2) = EventW;
    if ( EventW )
    {
      if ( WaitForSingleObject(*(HANDLE *)this, 0xFFFFFFFF) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( v3 >= 0 )
          v3 = -2147467259;
        goto LABEL_26;
      }
      dwMaximumSizeLowa[0] = GetCurrentProcessId();
      v3 = StringCchPrintfW(Name, 0x104u, L"InventorySynchronization%lsMemory%d", L"Mare", *(_QWORD *)dwMaximumSizeLowa);
      if ( v3 < 0 )
        goto LABEL_24;
      FileMappingW = OpenFileMappingW(2u, 0, Name);
      *((_QWORD *)this + 1) = FileMappingW;
      if ( FileMappingW )
      {
        v10 = 1;
      }
      else
      {
        FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 8u, Name);
        *((_QWORD *)this + 1) = FileMappingW;
        if ( !FileMappingW )
          goto LABEL_16;
        v10 = 0;
      }
      v11 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
      *((_QWORD *)this + 3) = v11;
      if ( v11 )
      {
        if ( !v10 )
        {
          *v11 = 0;
          *(_DWORD *)(*((_QWORD *)this + 3) + 4LL) = 0;
        }
        v3 = 0;
        goto LABEL_24;
      }
LABEL_16:
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
LABEL_24:
      ReleaseMutex(*(HANDLE *)this);
      goto LABEL_25;
    }
  }
  v5 = GetLastError();
  v3 = v5;
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
LABEL_25:
  if ( v3 < 0 )
    goto LABEL_26;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180106840  mov     [rsp+arg_8], rbx
0x180106845  mov     [rsp+arg_10], rdi
0x18010684a  push    r14
0x18010684c  sub     rsp, 250h
0x180106853  mov     rax, cs:__security_cookie
0x18010685a  xor     rax, rsp
0x18010685d  mov     [rsp+258h+var_18], rax
0x180106865  mov     rdi, rcx
0x180106868  xor     edx, edx; Val
0x18010686a  lea     rcx, [rsp+258h+Name]; void *
0x18010686f  mov     r8d, 208h; Size
0x180106875  call    memset_0
0x18010687a  call    cs:__imp_GetCurrentProcessId
0x180106880  mov     r14d, 104h
0x180106886  lea     r9, aMare; "Mare"
0x18010688d  lea     r8, aInventorysynch_0; "InventorySynchronization%lsMutex%d"
0x180106894  mov     [rsp+258h+dwMaximumSizeLow], eax
0x180106898  mov     edx, r14d; unsigned __int64
0x18010689b  lea     rcx, [rsp+258h+Name]; unsigned __int16 *
0x1801068a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801068a5  mov     ebx, eax
0x1801068a7  test    eax, eax
0x1801068a9  js      loc_180106A3F
0x1801068af  lea     r8, [rsp+258h+Name]; lpName
0x1801068b4  xor     edx, edx; bInitialOwner
0x1801068b6  xor     ecx, ecx; lpMutexAttributes
0x1801068b8  call    cs:__imp_CreateMutexW
0x1801068be  mov     [rdi], rax
0x1801068c1  test    rax, rax
0x1801068c4  jnz     short loc_1801068E4
0x1801068c6  call    cs:__imp_GetLastError
0x1801068cc  mov     ebx, eax
0x1801068ce  test    eax, eax
0x1801068d0  jle     loc_180106A3B
0x1801068d6  movzx   ebx, ax
0x1801068d9  or      ebx, 80070000h
0x1801068df  jmp     loc_180106A3B
0x1801068e4  call    cs:__imp_GetCurrentProcessId
0x1801068ea  lea     r9, aMare; "Mare"
0x1801068f1  mov     rdx, r14; unsigned __int64
0x1801068f4  lea     r8, aInventorysynch; "InventorySynchronization%lsEvent%d"
0x1801068fb  mov     [rsp+258h+dwMaximumSizeLow], eax
0x1801068ff  lea     rcx, [rsp+258h+Name]; unsigned __int16 *
0x180106904  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180106909  mov     ebx, eax
0x18010690b  test    eax, eax
0x18010690d  js      loc_180106A3F
0x180106913  lea     r9, [rsp+258h+Name]; lpName
0x180106918  xor     r8d, r8d; bInitialState
0x18010691b  xor     edx, edx; bManualReset
0x18010691d  xor     ecx, ecx; lpEventAttributes
0x18010691f  call    cs:__imp_CreateEventW
0x180106925  mov     [rdi+10h], rax
0x180106929  test    rax, rax
0x18010692c  jz      short loc_1801068C6
0x18010692e  mov     rcx, [rdi]; hHandle
0x180106931  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180106934  call    cs:__imp_WaitForSingleObject
0x18010693a  test    eax, eax
0x18010693c  jz      short loc_180106962
0x18010693e  call    cs:__imp_GetLastError
0x180106944  mov     ebx, eax
0x180106946  test    eax, eax
0x180106948  jle     short loc_180106953
0x18010694a  movzx   ebx, ax
0x18010694d  or      ebx, 80070000h
0x180106953  test    ebx, ebx
0x180106955  mov     eax, 80004005h
0x18010695a  cmovns  ebx, eax
0x18010695d  jmp     loc_180106A3F
0x180106962  call    cs:__imp_GetCurrentProcessId
0x180106968  lea     r9, aMare; "Mare"
0x18010696f  mov     rdx, r14; unsigned __int64
0x180106972  lea     r8, aInventorysynch_1; "InventorySynchronization%lsMemory%d"
0x180106979  mov     [rsp+258h+dwMaximumSizeLow], eax
0x18010697d  lea     rcx, [rsp+258h+Name]; unsigned __int16 *
0x180106982  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180106987  mov     ebx, eax
0x180106989  test    eax, eax
0x18010698b  js      loc_180106A32
0x180106991  xor     edx, edx; bInheritHandle
0x180106993  lea     r8, [rsp+258h+Name]; lpName
0x180106998  lea     ecx, [rdx+2]; dwDesiredAccess
0x18010699b  call    cs:__imp_OpenFileMappingW
0x1801069a1  mov     [rdi+8], rax
0x1801069a5  test    rax, rax
0x1801069a8  jnz     short loc_1801069F3
0x1801069aa  xor     r9d, r9d; dwMaximumSizeHigh
0x1801069ad  lea     rax, [rsp+258h+Name]
0x1801069b2  mov     [rsp+258h+lpName], rax; lpName
0x1801069b7  xor     edx, edx; lpFileMappingAttributes
0x1801069b9  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x1801069bd  mov     [rsp+258h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x1801069c5  lea     r8d, [r9+4]; flProtect
0x1801069c9  call    cs:__imp_CreateFileMappingW
0x1801069cf  mov     [rdi+8], rax
0x1801069d3  test    rax, rax
0x1801069d6  jnz     short loc_1801069EF
0x1801069d8  call    cs:__imp_GetLastError
0x1801069de  mov     ebx, eax
0x1801069e0  test    eax, eax
0x1801069e2  jle     short loc_180106A32
0x1801069e4  movzx   ebx, ax
0x1801069e7  or      ebx, 80070000h
0x1801069ed  jmp     short loc_180106A32
0x1801069ef  xor     bl, bl
0x1801069f1  jmp     short loc_1801069F5
0x1801069f3  mov     bl, 1
0x1801069f5  xor     r9d, r9d; dwFileOffsetLow
0x1801069f8  mov     qword ptr [rsp+258h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180106a01  xor     r8d, r8d; dwFileOffsetHigh
0x180106a04  mov     edx, 0F001Fh; dwDesiredAccess
0x180106a09  mov     rcx, rax; hFileMappingObject
0x180106a0c  call    cs:__imp_MapViewOfFile
0x180106a12  mov     [rdi+18h], rax
0x180106a16  test    rax, rax
0x180106a19  jz      short loc_1801069D8
0x180106a1b  test    bl, bl
0x180106a1d  jnz     short loc_180106A30
0x180106a1f  mov     dword ptr [rax], 0
0x180106a25  mov     rax, [rdi+18h]
0x180106a29  mov     dword ptr [rax+4], 0
0x180106a30  xor     ebx, ebx
0x180106a32  mov     rcx, [rdi]; hMutex
0x180106a35  call    cs:__imp_ReleaseMutex
0x180106a3b  test    ebx, ebx
0x180106a3d  jns     short loc_180106A47
0x180106a3f  mov     rcx, rdi; this
0x180106a42  call    ?Uninitialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::Uninitialize(void)
0x180106a47  mov     eax, ebx
0x180106a49  mov     rcx, [rsp+258h+var_18]
0x180106a51  xor     rcx, rsp; StackCookie
0x180106a54  call    __security_check_cookie
0x180106a59  lea     r11, [rsp+258h+var_8]
0x180106a61  mov     rbx, [r11+18h]
0x180106a65  mov     rdi, [r11+20h]
0x180106a69  mov     rsp, r11
0x180106a6c  pop     r14
0x180106a6e  retn
```
