# CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x18002c9fc`
- end: `0x18002cb74`
- name: `?SetSize@?$CArray@UCFastNtfsEntry@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@U12@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `376`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180025f90`
- `0x180026824`
- `0x180029140`

## callees

- `0x180002746`
- `0x180025f00`
- `0x180027008`
- `0x1800293a4`
- `0x18002c9fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ca7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ca7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cade`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ca6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cade`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cb4d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002caed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002caed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb5b`

## pseudocode

```c
__int64 __fastcall CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsEntry,CAdaptorDefault,CPoliciesDefault>::SetSize(
        __int64 a1,
        int a2)
{
  void *v3; // rbx
  int v5; // r15d
  SIZE_T v6; // r14
  int v7; // edi
  HANDLE v8; // rax
  void *v9; // rax
  void *v10; // r12
  void *v11; // r13
  int v12; // edi
  __int64 v13; // r14
  __int64 v14; // rbx
  HANDLE ProcessHeap; // rax
  void *v16; // rdi
  HANDLE v17; // rax
  void *v18; // rax

  v3 = 0;
  if ( *(_DWORD *)a1 == a2 )
  {
LABEL_25:
    v7 = 0;
    goto LABEL_26;
  }
  v5 = *(_DWORD *)(a1 + 4);
  if ( a2 < v5 )
    v5 = a2;
  if ( a2 <= 0 )
  {
LABEL_14:
    v10 = v3;
    v11 = v3;
    if ( a2 < *(_DWORD *)(a1 + 4) )
    {
      v12 = a2;
      do
      {
        v13 = *(_QWORD *)(a1 + 8) + ((__int64)v12 << 6);
        if ( v13 )
        {
          CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(v13 + 48);
          v14 = *(_QWORD *)(v13 + 8);
          if ( v14 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, (LPVOID)(v14 - 4));
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            *(_QWORD *)(v13 + 8) = 0;
          }
        }
        ++v12;
      }
      while ( v12 < *(_DWORD *)(a1 + 4) );
    }
    v16 = *(void **)(a1 + 8);
    if ( v16 )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, v16);
      *(_QWORD *)(a1 + 8) = 0;
    }
    v18 = 0;
    if ( v10 )
      v18 = v11;
    *(_QWORD *)(a1 + 8) = v18;
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)a1 = a2;
    goto LABEL_25;
  }
  v6 = (__int64)a2 << 6;
  if ( (a2 & 0x3FFFFFFFFFFFFFFLL) == a2 )
  {
    v7 = 0;
  }
  else
  {
    v7 = -2147024362;
    v6 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v7 >= 0 )
  {
    v8 = GetProcessHeap();
    v9 = HeapAlloc(v8, 0, v6);
    v3 = v9;
    if ( !v9 )
    {
      v7 = -2147024882;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
      goto LABEL_26;
    }
    if ( v5 )
      memcpy_0(v9, *(const void **)(a1 + 8), (__int64)v5 << 6);
    goto LABEL_14;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
LABEL_26:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002c9fc  push    rbx
0x18002c9fe  push    rbp
0x18002c9ff  push    rsi
0x18002ca00  push    rdi
0x18002ca01  push    r12
0x18002ca03  push    r13
0x18002ca05  push    r14
0x18002ca07  push    r15
0x18002ca09  sub     rsp, 28h
0x18002ca0d  movsxd  rbp, edx
0x18002ca10  xor     ebx, ebx
0x18002ca12  mov     rsi, rcx
0x18002ca15  cmp     [rcx], ebp
0x18002ca17  jz      loc_18002CB3F
0x18002ca1d  mov     r15d, [rcx+4]
0x18002ca21  cmp     ebp, r15d
0x18002ca24  cmovl   r15d, ebp
0x18002ca28  test    edx, edx
0x18002ca2a  jle     loc_18002CAB2
0x18002ca30  mov     r14, rbp
0x18002ca33  shl     r14, 6
0x18002ca37  mov     rax, r14
0x18002ca3a  shr     rax, 6
0x18002ca3e  cmp     rax, rbp
0x18002ca41  jz      short loc_18002CA54
0x18002ca43  mov     edi, 80070216h
0x18002ca48  xor     r14d, r14d
0x18002ca4b  mov     ecx, edi
0x18002ca4d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002ca52  jmp     short loc_18002CA56
0x18002ca54  xor     edi, edi
0x18002ca56  mov     ecx, edi
0x18002ca58  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002ca5d  test    edi, edi
0x18002ca5f  jns     short loc_18002CA6D
0x18002ca61  mov     ecx, edi
0x18002ca63  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002ca68  jmp     loc_18002CB41
0x18002ca6d  call    cs:__imp_GetProcessHeap
0x18002ca73  mov     r8, r14; dwBytes
0x18002ca76  xor     edx, edx; dwFlags
0x18002ca78  mov     rcx, rax; hHeap
0x18002ca7b  call    cs:__imp_HeapAlloc
0x18002ca81  mov     rbx, rax
0x18002ca84  test    rax, rax
0x18002ca87  jnz     short loc_18002CA9A
0x18002ca89  mov     edi, 8007000Eh
0x18002ca8e  mov     ecx, edi
0x18002ca90  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002ca95  jmp     loc_18002CB41
0x18002ca9a  test    r15d, r15d
0x18002ca9d  jz      short loc_18002CAB2
0x18002ca9f  mov     rdx, [rsi+8]; Src
0x18002caa3  mov     rcx, rax; void *
0x18002caa6  movsxd  r8, r15d
0x18002caa9  shl     r8, 6; Size
0x18002caad  call    memcpy_0
0x18002cab2  mov     r12, rbx
0x18002cab5  mov     r13, rbx
0x18002cab8  cmp     ebp, [rsi+4]
0x18002cabb  jge     short loc_18002CB09
0x18002cabd  mov     edi, ebp
0x18002cabf  movsxd  r14, edi
0x18002cac2  shl     r14, 6
0x18002cac6  add     r14, [rsi+8]
0x18002caca  jz      short loc_18002CB02
0x18002cacc  lea     rcx, [r14+30h]
0x18002cad0  call    ??1?$CArray@UCFastNtfsIndex@?$CFastDeleteImplT@V?$CDirectoryProviderT@VCWindowsOldAdaptor@@@@$00@@_KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAA@XZ; CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>::~CArray<CFastDeleteImplT<CDirectoryProviderT<CWindowsOldAdaptor>,1>::CFastNtfsIndex,unsigned __int64,CAdaptorDefault,CPoliciesDefault>(void)
0x18002cad5  mov     rbx, [r14+8]
0x18002cad9  test    rbx, rbx
0x18002cadc  jz      short loc_18002CB02
0x18002cade  call    cs:__imp_GetProcessHeap
0x18002cae4  lea     r8, [rbx-4]; lpMem
0x18002cae8  xor     edx, edx; dwFlags
0x18002caea  mov     rcx, rax; hHeap
0x18002caed  call    cs:__imp_HeapFree
0x18002caf3  xor     ecx, ecx
0x18002caf5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cafa  mov     qword ptr [r14+8], 0
0x18002cb02  inc     edi
0x18002cb04  cmp     edi, [rsi+4]
0x18002cb07  jl      short loc_18002CABF
0x18002cb09  mov     rdi, [rsi+8]
0x18002cb0d  xor     ebx, ebx
0x18002cb0f  test    rdi, rdi
0x18002cb12  jz      short loc_18002CB2C
0x18002cb14  call    cs:__imp_GetProcessHeap
0x18002cb1a  mov     r8, rdi; lpMem
0x18002cb1d  xor     edx, edx; dwFlags
0x18002cb1f  mov     rcx, rax; hHeap
0x18002cb22  call    cs:__imp_HeapFree
0x18002cb28  mov     [rsi+8], rbx
0x18002cb2c  xor     eax, eax
0x18002cb2e  test    r12, r12
0x18002cb31  cmovnz  rax, r13
0x18002cb35  mov     [rsi+8], rax
0x18002cb39  mov     [rsi+4], r15d
0x18002cb3d  mov     [rsi], ebp
0x18002cb3f  xor     edi, edi
0x18002cb41  mov     ecx, edi
0x18002cb43  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002cb48  test    rbx, rbx
0x18002cb4b  jz      short loc_18002CB61
0x18002cb4d  call    cs:__imp_GetProcessHeap
0x18002cb53  mov     r8, rbx; lpMem
0x18002cb56  xor     edx, edx; dwFlags
0x18002cb58  mov     rcx, rax; hHeap
0x18002cb5b  call    cs:__imp_HeapFree
0x18002cb61  mov     eax, edi
0x18002cb63  add     rsp, 28h
0x18002cb67  pop     r15
0x18002cb69  pop     r14
0x18002cb6b  pop     r13
0x18002cb6d  pop     r12
0x18002cb6f  pop     rdi
0x18002cb70  pop     rsi
0x18002cb71  pop     rbp
0x18002cb72  pop     rbx
0x18002cb73  retn
```
