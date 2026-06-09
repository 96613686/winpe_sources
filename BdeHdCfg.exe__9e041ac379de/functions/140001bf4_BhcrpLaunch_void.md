# BhcrpLaunch(void)

- ea: `0x140001bf4`
- end: `0x140001d66`
- name: `?BhcrpLaunch@@YAJXZ`
- size: `370`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140004200`

## callees

- `0x140001008`
- `0x1400013c8`
- `0x140001970`
- `0x140001a28`
- `0x140001bf4`
- `0x140001fac`
- `0x140002930`
- `0x140003340`

## import_xrefs

- `KERNEL32!CreateMutexW` at `0x140001c4a`
- `KERNEL32!CreateMutexW` at `0x140001c4a`
- `KERNEL32!GetLastError` at `0x140001c5d`
- `KERNEL32!GetLastError` at `0x140001c7b`
- `KERNEL32!GetLastError` at `0x140001c5d`
- `KERNEL32!GetLastError` at `0x140001c7b`
- `KERNEL32!CloseHandle` at `0x140001d2d`
- `KERNEL32!CloseHandle` at `0x1400045bc`
- `KERNEL32!CloseHandle` at `0x140001d2d`
- `KERNEL32!CloseHandle` at `0x1400045bc`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x140001d4e`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x1400045e8`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x140001d4e`
- `BDEHDCFGLIB!BdeCfgLogError` at `0x1400045e8`
- `BDEHDCFGLIB!BdeCfgLogClose` at `0x140001d54`
- `BDEHDCFGLIB!BdeCfgLogClose` at `0x1400045ef`
- `BDEHDCFGLIB!BdeCfgLogClose` at `0x140001d54`
- `BDEHDCFGLIB!BdeCfgLogClose` at `0x1400045ef`
- `BDEHDCFGLIB!BdeCfgLogInit` at `0x140001c39`
- `BDEHDCFGLIB!BdeCfgLogInit` at `0x140001c39`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140001c25`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140001c25`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140001ce0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140001ce0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140001d38`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400045d1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140001d38`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400045d1`

## pseudocode

```c
__int64 BhcrpLaunch(void)
{
  HANDLE MutexW; // rsi
  CBdeCfgConsole *v1; // rdi
  char v2; // r14
  __int64 v3; // rdx
  __int64 v4; // rcx
  int ResourceString; // ebx
  __int64 v6; // r8
  signed int LastError; // eax
  CBdeCfgConsole *v8; // rax
  CBdeCfgConsole *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  void *Block; // [rsp+70h] [rbp+8h] BYREF

  MutexW = 0;
  v1 = 0;
  Block = 0;
  v2 = 0;
  ResourceString = BdeCfgLoadResourceString(0x64u, (unsigned __int16 **)&Block);
  if ( ResourceString >= 0 )
  {
    BdeCfgLogInit(v4, v3, v6);
    MutexW = CreateMutexW(0, 0, L"{9ebf696d-2428-4dc4-b048-d46c6da4b717}");
    if ( MutexW )
    {
      if ( GetLastError() == 183 )
      {
        ResourceString = -2147024713;
      }
      else
      {
        v8 = (CBdeCfgConsole *)operator new(0x5E0u, (const struct std::nothrow_t *)std::nothrow);
        if ( v8 )
          v1 = CBdeCfgConsole::CBdeCfgConsole(v8);
        else
          v1 = 0;
        if ( v1 )
        {
          ResourceString = CBdeCfgConsole::InitializeUI(v9);
          if ( ResourceString >= 0 )
          {
            CBdeCfgConsole::PrintProgramBanner(v1);
            ResourceString = CoInitializeEx(0, 0);
            if ( ResourceString >= 0 )
            {
              v2 = 1;
              ResourceString = CBdeCfgConsole::DoConsoleMode(v1);
            }
          }
        }
        else
        {
          ResourceString = -2147024882;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      ResourceString = LastError;
      if ( LastError > 0 )
        ResourceString = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v1 )
  {
    CBdeCfgConsole::~CBdeCfgConsole(v1);
    operator delete(v1);
  }
  operator delete(Block);
  if ( MutexW )
    CloseHandle(MutexW);
  if ( v2 )
  {
    CoUninitialize();
  }
  else if ( ResourceString < 0 )
  {
    BdeCfgLogError(1, (unsigned int)ResourceString);
  }
  BdeCfgLogClose(v11, v10, v12);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x140001bf4  mov     rax, rsp
0x140001bf7  push    rbx
0x140001bf8  push    rsi
0x140001bf9  push    rdi
0x140001bfa  push    r14
0x140001bfc  sub     rsp, 48h
0x140001c00  mov     dword ptr [rax-44h], 0
0x140001c07  xor     esi, esi
0x140001c09  mov     [rax-40h], rsi
0x140001c0d  xor     edi, edi
0x140001c0f  mov     [rax-38h], rdi
0x140001c13  mov     [rax+8], rsi
0x140001c17  xor     r14b, r14b
0x140001c1a  mov     [rax-48h], r14b
0x140001c1e  lea     rdx, [rax+8]
0x140001c22  lea     ecx, [rsi+64h]
0x140001c25  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140001c2b  mov     ebx, eax
0x140001c2d  mov     [rsp+68h+var_44], eax
0x140001c31  test    eax, eax
0x140001c33  js      loc_140001D06
0x140001c39  call    cs:__imp_BdeCfgLogInit
0x140001c3f  lea     r8, Name; "{9ebf696d-2428-4dc4-b048-d46c6da4b717}"
0x140001c46  xor     edx, edx; bInitialOwner
0x140001c48  xor     ecx, ecx; lpMutexAttributes
0x140001c4a  call    cs:__imp_CreateMutexW
0x140001c50  mov     rsi, rax
0x140001c53  mov     [rsp+68h+var_40], rax
0x140001c58  test    rax, rax
0x140001c5b  jnz     short loc_140001C7B
0x140001c5d  call    cs:__imp_GetLastError
0x140001c63  mov     ebx, eax
0x140001c65  test    eax, eax
0x140001c67  jle     short loc_140001C72
0x140001c69  movzx   ebx, ax
0x140001c6c  or      ebx, 80070000h
0x140001c72  mov     [rsp+68h+var_44], ebx
0x140001c76  jmp     loc_140001D06
0x140001c7b  call    cs:__imp_GetLastError
0x140001c81  cmp     eax, 0B7h
0x140001c86  jnz     short loc_140001C8F
0x140001c88  mov     ebx, 800700B7h
0x140001c8d  jmp     short loc_140001C72
0x140001c8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140001c96  mov     ecx, 5E0h; unsigned __int64
0x140001c9b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140001ca0  test    rax, rax
0x140001ca3  jz      short loc_140001CB2
0x140001ca5  mov     rcx, rax; this
0x140001ca8  call    ??0CBdeCfgConsole@@QEAA@XZ; CBdeCfgConsole::CBdeCfgConsole(void)
0x140001cad  mov     rdi, rax
0x140001cb0  jmp     short loc_140001CB4
0x140001cb2  xor     edi, edi
0x140001cb4  mov     [rsp+68h+var_38], rdi
0x140001cb9  test    rdi, rdi
0x140001cbc  jnz     short loc_140001CC5
0x140001cbe  mov     ebx, 8007000Eh
0x140001cc3  jmp     short loc_140001C72
0x140001cc5  call    ?InitializeUI@CBdeCfgConsole@@QEAAJXZ; CBdeCfgConsole::InitializeUI(void)
0x140001cca  mov     ebx, eax
0x140001ccc  mov     [rsp+68h+var_44], eax
0x140001cd0  test    eax, eax
0x140001cd2  js      short loc_140001D06
0x140001cd4  mov     rcx, rdi; this
0x140001cd7  call    ?PrintProgramBanner@CBdeCfgConsole@@QEAAXXZ; CBdeCfgConsole::PrintProgramBanner(void)
0x140001cdc  xor     edx, edx; dwCoInit
0x140001cde  xor     ecx, ecx; pvReserved
0x140001ce0  call    cs:__imp_CoInitializeEx
0x140001ce6  mov     ebx, eax
0x140001ce8  mov     [rsp+68h+var_44], eax
0x140001cec  test    eax, eax
0x140001cee  js      short loc_140001D06
0x140001cf0  mov     r14b, 1
0x140001cf3  mov     [rsp+68h+var_48], r14b
0x140001cf8  mov     rcx, rdi; this
0x140001cfb  call    ?DoConsoleMode@CBdeCfgConsole@@QEAAJXZ; CBdeCfgConsole::DoConsoleMode(void)
0x140001d00  mov     ebx, eax
0x140001d02  mov     [rsp+68h+var_44], eax
0x140001d06  test    rdi, rdi
0x140001d09  jz      short loc_140001D1B
0x140001d0b  mov     rcx, rdi; this
0x140001d0e  call    ??1CBdeCfgConsole@@QEAA@XZ; CBdeCfgConsole::~CBdeCfgConsole(void)
0x140001d13  mov     rcx, rdi; Block
0x140001d16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001d1b  mov     rcx, [rsp+68h+Block]; Block
0x140001d20  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001d25  test    rsi, rsi
0x140001d28  jz      short loc_140001D33
0x140001d2a  mov     rcx, rsi; hObject
0x140001d2d  call    cs:__imp_CloseHandle
0x140001d33  test    r14b, r14b
0x140001d36  jz      short loc_140001D43
0x140001d38  call    cs:__imp_CoUninitialize
0x140001d3e  test    r14b, r14b
0x140001d41  jnz     short loc_140001D54
0x140001d43  test    ebx, ebx
0x140001d45  jns     short loc_140001D54
0x140001d47  mov     edx, ebx
0x140001d49  mov     ecx, 1
0x140001d4e  call    cs:__imp_BdeCfgLogError
0x140001d54  call    cs:__imp_BdeCfgLogClose
0x140001d5a  mov     eax, ebx
0x140001d5c  add     rsp, 48h
0x140001d60  pop     r14
0x140001d62  pop     rdi
0x140001d63  pop     rsi
0x140001d64  pop     rbx
0x140001d65  retn
0x140004586  push    rbx
0x140004588  push    rbp
0x140004589  sub     rsp, 28h
0x14000458d  mov     rbp, rdx
0x140004590  mov     rbx, [rbp+30h]
0x140004594  test    rbx, rbx
0x140004597  jz      short loc_1400045AA
0x140004599  mov     rcx, rbx; this
0x14000459c  call    ??1CBdeCfgConsole@@QEAA@XZ; CBdeCfgConsole::~CBdeCfgConsole(void)
0x1400045a1  mov     rcx, rbx; Block
0x1400045a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400045a9  nop
0x1400045aa  mov     rcx, [rbp+70h]; Block
0x1400045ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400045b3  mov     rcx, [rbp+28h]; hObject
0x1400045b7  test    rcx, rcx
0x1400045ba  jz      short loc_1400045CA
0x1400045bc  call    cs:__imp_CloseHandle
0x1400045c2  mov     qword ptr [rbp+28h], 0
0x1400045ca  mov     bl, [rbp+20h]
0x1400045cd  test    bl, bl
0x1400045cf  jz      short loc_1400045DC
0x1400045d1  call    cs:__imp_CoUninitialize
0x1400045d7  nop
0x1400045d8  test    bl, bl
0x1400045da  jnz     short loc_1400045EF
0x1400045dc  mov     edx, [rbp+24h]
0x1400045df  test    edx, edx
0x1400045e1  jns     short loc_1400045EF
0x1400045e3  mov     ecx, 1
0x1400045e8  call    cs:__imp_BdeCfgLogError
0x1400045ee  nop
0x1400045ef  call    cs:__imp_BdeCfgLogClose
0x1400045f5  nop
0x1400045f6  add     rsp, 28h
0x1400045fa  pop     rbp
0x1400045fb  pop     rbx
0x1400045fc  retn
```
