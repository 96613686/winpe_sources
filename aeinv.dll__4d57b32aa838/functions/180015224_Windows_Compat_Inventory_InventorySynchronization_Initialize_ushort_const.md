# Windows::Compat::Inventory::InventorySynchronization::Initialize(ushort const *)

- ea: `0x180015224`
- end: `0x18001544b`
- name: `?Initialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAJPEBG@Z`
- size: `551`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InventorySynchronization *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002debc`

## callees

- `0x180015224`
- `0x180015eec`
- `0x1800289fc`
- `0x180059920`
- `0x18005a8bc`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x180015298`
- `KERNEL32!CreateMutexW` at `0x180015298`
- `KERNEL32!GetCurrentProcessId` at `0x18001525e`
- `KERNEL32!GetCurrentProcessId` at `0x1800152aa`
- `KERNEL32!GetCurrentProcessId` at `0x180015308`
- `KERNEL32!GetCurrentProcessId` at `0x18001525e`
- `KERNEL32!GetCurrentProcessId` at `0x1800152aa`
- `KERNEL32!GetCurrentProcessId` at `0x180015308`
- `KERNEL32!OpenFileMappingW` at `0x18001533d`
- `KERNEL32!OpenFileMappingW` at `0x18001533d`
- `KERNEL32!CreateFileMappingW` at `0x18001536f`
- `KERNEL32!CreateFileMappingW` at `0x18001536f`
- `KERNEL32!MapViewOfFile` at `0x18001539b`
- `KERNEL32!MapViewOfFile` at `0x18001539b`
- `KERNEL32!CreateEventW` at `0x1800152e1`
- `KERNEL32!CreateEventW` at `0x1800152e1`
- `KERNEL32!WaitForSingleObject` at `0x1800152fa`
- `KERNEL32!WaitForSingleObject` at `0x1800152fa`
- `KERNEL32!ReleaseMutex` at `0x1800153c4`
- `KERNEL32!ReleaseMutex` at `0x1800153c4`
- `KERNEL32!GetLastError` at `0x1800153f4`
- `KERNEL32!GetLastError` at `0x18001540b`
- `KERNEL32!GetLastError` at `0x180015422`
- `KERNEL32!GetLastError` at `0x1800153f4`
- `KERNEL32!GetLastError` at `0x18001540b`
- `KERNEL32!GetLastError` at `0x180015422`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::InventorySynchronization::Initialize(
        Windows::Compat::Inventory::InventorySynchronization *this,
        const unsigned __int16 *a2)
{
  signed int v4; // ebx
  HANDLE MutexW; // rax
  HANDLE EventW; // rax
  HANDLE FileMappingW; // rax
  char v8; // bl
  _DWORD *v9; // rax
  signed int v11; // eax
  signed int v12; // eax
  signed int LastError; // eax
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
        goto LABEL_15;
      FileMappingW = OpenFileMappingW(2u, 0, Name);
      *((_QWORD *)this + 1) = FileMappingW;
      if ( FileMappingW )
      {
        v8 = 1;
      }
      else
      {
        FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 8u, Name);
        *((_QWORD *)this + 1) = FileMappingW;
        if ( !FileMappingW )
          goto LABEL_20;
        v8 = 0;
      }
      v9 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
      *((_QWORD *)this + 3) = v9;
      if ( v9 )
      {
        if ( !v8 )
        {
          *v9 = 0;
          *(_DWORD *)(*((_QWORD *)this + 3) + 4LL) = 0;
        }
        v4 = 0;
LABEL_15:
        ReleaseMutex(*(HANDLE *)this);
        goto LABEL_16;
      }
LABEL_20:
      v12 = GetLastError();
      v4 = v12;
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
      goto LABEL_15;
    }
  }
  v11 = GetLastError();
  v4 = v11;
  if ( v11 > 0 )
    v4 = (unsigned __int16)v11 | 0x80070000;
LABEL_16:
  if ( v4 < 0 )
    goto LABEL_26;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015224  mov     [rsp+arg_10], rbx
0x180015229  push    rsi
0x18001522a  push    rdi
0x18001522b  push    r14
0x18001522d  sub     rsp, 250h
0x180015234  mov     rax, cs:__security_cookie
0x18001523b  xor     rax, rsp
0x18001523e  mov     [rsp+268h+var_28], rax
0x180015246  mov     rsi, rdx
0x180015249  mov     rdi, rcx
0x18001524c  xor     edx, edx; Val
0x18001524e  lea     rcx, [rsp+268h+Name]; void *
0x180015253  mov     r8d, 208h; Size
0x180015259  call    memset_0
0x18001525e  call    cs:__imp_GetCurrentProcessId
0x180015264  mov     r14d, 104h
0x18001526a  lea     r8, aInventorysynch_0; "InventorySynchronization%lsMutex%d"
0x180015271  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x180015276  mov     [rsp+268h+dwMaximumSizeLow], eax
0x18001527a  mov     edx, r14d; unsigned __int64
0x18001527d  mov     r9, rsi
0x180015280  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015285  mov     ebx, eax
0x180015287  test    eax, eax
0x180015289  js      loc_180015441
0x18001528f  lea     r8, [rsp+268h+Name]; lpName
0x180015294  xor     edx, edx; bInitialOwner
0x180015296  xor     ecx, ecx; lpMutexAttributes
0x180015298  call    cs:__imp_CreateMutexW
0x18001529e  mov     [rdi], rax
0x1800152a1  test    rax, rax
0x1800152a4  jz      loc_1800153F4
0x1800152aa  call    cs:__imp_GetCurrentProcessId
0x1800152b0  mov     r9, rsi
0x1800152b3  lea     r8, aInventorysynch; "InventorySynchronization%lsEvent%d"
0x1800152ba  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x1800152bf  mov     [rsp+268h+dwMaximumSizeLow], eax
0x1800152c3  mov     edx, r14d; unsigned __int64
0x1800152c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800152cb  mov     ebx, eax
0x1800152cd  test    eax, eax
0x1800152cf  js      loc_180015441
0x1800152d5  lea     r9, [rsp+268h+Name]; lpName
0x1800152da  xor     r8d, r8d; bInitialState
0x1800152dd  xor     edx, edx; bManualReset
0x1800152df  xor     ecx, ecx; lpEventAttributes
0x1800152e1  call    cs:__imp_CreateEventW
0x1800152e7  mov     [rdi+10h], rax
0x1800152eb  test    rax, rax
0x1800152ee  jz      loc_1800153F4
0x1800152f4  mov     rcx, [rdi]; hHandle
0x1800152f7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800152fa  call    cs:__imp_WaitForSingleObject
0x180015300  test    eax, eax
0x180015302  jnz     loc_180015422
0x180015308  call    cs:__imp_GetCurrentProcessId
0x18001530e  mov     r9, rsi
0x180015311  lea     r8, aInventorysynch_1; "InventorySynchronization%lsMemory%d"
0x180015318  lea     rcx, [rsp+268h+Name]; unsigned __int16 *
0x18001531d  mov     [rsp+268h+dwMaximumSizeLow], eax
0x180015321  mov     edx, r14d; unsigned __int64
0x180015324  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015329  mov     ebx, eax
0x18001532b  test    eax, eax
0x18001532d  js      loc_1800153C1
0x180015333  xor     edx, edx; bInheritHandle
0x180015335  lea     r8, [rsp+268h+Name]; lpName
0x18001533a  lea     ecx, [rdx+2]; dwDesiredAccess
0x18001533d  call    cs:__imp_OpenFileMappingW
0x180015343  mov     [rdi+8], rax
0x180015347  test    rax, rax
0x18001534a  jz      short loc_180015350
0x18001534c  mov     bl, 1
0x18001534e  jmp     short loc_180015384
0x180015350  xor     r9d, r9d; dwMaximumSizeHigh
0x180015353  lea     rax, [rsp+268h+Name]
0x180015358  mov     [rsp+268h+lpName], rax; lpName
0x18001535d  xor     edx, edx; lpFileMappingAttributes
0x18001535f  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x180015363  mov     [rsp+268h+dwMaximumSizeLow], 8; dwMaximumSizeLow
0x18001536b  lea     r8d, [r9+4]; flProtect
0x18001536f  call    cs:__imp_CreateFileMappingW
0x180015375  mov     [rdi+8], rax
0x180015379  test    rax, rax
0x18001537c  jz      loc_18001540B
0x180015382  xor     bl, bl
0x180015384  xor     r9d, r9d; dwFileOffsetLow
0x180015387  mov     qword ptr [rsp+268h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180015390  xor     r8d, r8d; dwFileOffsetHigh
0x180015393  mov     edx, 0F001Fh; dwDesiredAccess
0x180015398  mov     rcx, rax; hFileMappingObject
0x18001539b  call    cs:__imp_MapViewOfFile
0x1800153a1  mov     [rdi+18h], rax
0x1800153a5  test    rax, rax
0x1800153a8  jz      short loc_18001540B
0x1800153aa  test    bl, bl
0x1800153ac  jnz     short loc_1800153BF
0x1800153ae  mov     dword ptr [rax], 0
0x1800153b4  mov     rax, [rdi+18h]
0x1800153b8  mov     dword ptr [rax+4], 0
0x1800153bf  xor     ebx, ebx
0x1800153c1  mov     rcx, [rdi]; hMutex
0x1800153c4  call    cs:__imp_ReleaseMutex
0x1800153ca  test    ebx, ebx
0x1800153cc  js      short loc_180015441
0x1800153ce  mov     eax, ebx
0x1800153d0  mov     rcx, [rsp+268h+var_28]
0x1800153d8  xor     rcx, rsp; StackCookie
0x1800153db  call    __security_check_cookie
0x1800153e0  mov     rbx, [rsp+268h+arg_10]
0x1800153e8  add     rsp, 250h
0x1800153ef  pop     r14
0x1800153f1  pop     rdi
0x1800153f2  pop     rsi
0x1800153f3  retn
0x1800153f4  call    cs:__imp_GetLastError
0x1800153fa  mov     ebx, eax
0x1800153fc  test    eax, eax
0x1800153fe  jle     short loc_1800153CA
0x180015400  movzx   ebx, ax
0x180015403  or      ebx, 80070000h
0x180015409  jmp     short loc_1800153CA
0x18001540b  call    cs:__imp_GetLastError
0x180015411  mov     ebx, eax
0x180015413  test    eax, eax
0x180015415  jle     short loc_1800153C1
0x180015417  movzx   ebx, ax
0x18001541a  or      ebx, 80070000h
0x180015420  jmp     short loc_1800153C1
0x180015422  call    cs:__imp_GetLastError
0x180015428  mov     ebx, eax
0x18001542a  test    eax, eax
0x18001542c  jle     short loc_180015437
0x18001542e  movzx   ebx, ax
0x180015431  or      ebx, 80070000h
0x180015437  test    ebx, ebx
0x180015439  mov     eax, 80004005h
0x18001543e  cmovns  ebx, eax
0x180015441  mov     rcx, rdi; this
0x180015444  call    ?Uninitialize@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::Uninitialize(void)
0x180015449  jmp     short loc_1800153CE
```
