# __delayLoadHelper2

- ea: `0x18000b5c0`
- end: `0x18000ba8a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002146`

## callees

- `0x180002134`
- `0x18000b4dc`
- `0x18000b5c0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b919`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b919`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000b7a1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000b7a1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b89c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b89c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b92b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b6ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b838`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b9b4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b6ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b838`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b9b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b871`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000b871`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b85f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b85f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b631`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b99f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b631`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b99f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b9fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ba72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b607`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b97a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b9cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba4d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b607`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b7fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b97a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b9cd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ba4d`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile signed __int64 *v4; // r15
  DWORD dwTimeStamp; // ecx
  char *v6; // r12
  int v7; // eax
  HMODULE Library; // rbx
  __int64 v10; // rcx
  PfnDliHook v11; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v13; // r15
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v15; // rax
  __int64 v16; // rcx
  struct DelayLoadInfo v17; // [rsp+20h] [rbp-50h] BYREF
  DWORD v18; // [rsp+B0h] [rbp+40h]
  __int64 flOldProtect; // [rsp+B8h] [rbp+48h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+50h] BYREF

  *(&v17.cb + 1) = 0;
  memset_0(&v17, 0, 0x44u);
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  v4 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v6 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v17.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  v7 = a1->grAttrs & 1;
  v18 = dwTimeStamp;
  v17.cb = 72;
  v17.pidd = a1;
  v17.ppfn = a2;
  v17.dlp.fImportByName = 0;
  memset(&v17.dlp.szProcName, 0, 28);
  if ( !(_BYTE)v7 )
  {
    Arguments = (ULONG_PTR)&v17;
    LODWORD(flOldProtect) = 0;
    AcquireSRWLockExclusive(&DloadSrwLock);
    if ( !--DloadSectionLockCount )
      DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
    ReleaseSRWLockExclusive(&DloadSrwLock);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v4;
  v10 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3) + a1->rvaINT;
  flOldProtect = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v17.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + v10) >= 0LL;
  if ( v17.dlp.fImportByName )
    v17.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v10);
  else
    v17.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + v10);
  v11 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v17), v11 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v11 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(1, &v17)) == 0 )
      {
        Library = LoadLibraryExA(v17.szDll, 0, 0);
        if ( !Library )
        {
          v17.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v17)) == 0 )
          {
            Arguments = (ULONG_PTR)&v17;
            LODWORD(flOldProtect) = 0;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v17.pfnCur;
          }
        }
      }
      v13 = _InterlockedCompareExchange64(v4, (signed __int64)Library, 0);
      if ( v13 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v13 )
          Library = (HMODULE)v13;
      }
      else if ( Library != (HMODULE)-1LL )
      {
        if ( a1->rvaUnloadIAT )
        {
          ProcessHeap = GetProcessHeap();
          v15 = (struct UnloadInfo *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          if ( v15 )
          {
            v15->pidd = a1;
            v15->puiNext = _puiHead;
            _puiHead = v15;
          }
        }
      }
      v11 = _pfnDliNotifyHook2;
    }
    v17.hmodCur = Library;
    if ( v11 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(2, &v17);
      v11 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v16 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v16) != 17744)
        || *(_DWORD *)((char *)Library + v16 + 8) != v18
        || Library != *(HMODULE *)((char *)Library + v16 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v6[flOldProtect]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v17.dlp.szProcName);
        if ( !ProcAddress )
        {
          v17.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v17)) == 0 )
          {
            Arguments = (ULONG_PTR)&v17;
            LODWORD(flOldProtect) = 0;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( ++DloadSectionLockCount == 1 )
              DloadProtectSection(4u, &DloadSectionOldProtection);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            ProcAddress = v17.pfnCur;
          }
        }
        v11 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v11 )
  {
    v17.dwLastError = 0;
    v17.hmodCur = Library;
    v17.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v11)(5, &v17);
  }
  LODWORD(flOldProtect) = 0;
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  return ProcAddress;
}

```

## disassembly

```asm
0x18000b5c0  push    rbp
0x18000b5c2  push    rbx
0x18000b5c3  push    rsi
0x18000b5c4  push    rdi
0x18000b5c5  push    r12
0x18000b5c7  push    r13
0x18000b5c9  push    r15
0x18000b5cb  mov     rbp, rsp
0x18000b5ce  sub     rsp, 70h
0x18000b5d2  xor     eax, eax
0x18000b5d4  mov     r13, rdx
0x18000b5d7  mov     rsi, rcx
0x18000b5da  mov     [rbp+var_4C], eax
0x18000b5dd  xor     edx, edx; Val
0x18000b5df  lea     rcx, [rbp+var_50]; void *
0x18000b5e3  lea     r8d, [rax+44h]; Size
0x18000b5e7  call    memset_0
0x18000b5ec  test    cs:dword_18000D160, 1000h
0x18000b5f6  lea     rbx, DloadSrwLock
0x18000b5fd  mov     edi, 1
0x18000b602  jz      short loc_18000B637
0x18000b604  mov     rcx, rbx; SRWLock
0x18000b607  call    cs:__imp_AcquireSRWLockExclusive
0x18000b60d  mov     eax, cs:DloadSectionLockCount
0x18000b613  add     eax, edi
0x18000b615  mov     cs:DloadSectionLockCount, eax
0x18000b61b  cmp     eax, edi
0x18000b61d  jnz     short loc_18000B62E
0x18000b61f  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000b626  lea     ecx, [rdi+3]; flNewProtect
0x18000b629  call    DloadProtectSection
0x18000b62e  mov     rcx, rbx; SRWLock
0x18000b631  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b637  mov     eax, [rsi+4]
0x18000b63a  lea     rdx, __ImageBase
0x18000b641  mov     r15d, [rsi+8]
0x18000b645  add     rax, rdx
0x18000b648  mov     r12d, [rsi+14h]
0x18000b64c  add     r15, rdx
0x18000b64f  mov     ecx, [rsi+1Ch]
0x18000b652  add     r12, rdx
0x18000b655  mov     [rbp+lpLibFileName], rax
0x18000b659  mov     eax, [rsi]
0x18000b65b  and     eax, edi
0x18000b65d  mov     [rbp+arg_0], ecx
0x18000b660  mov     [rbp+var_50], 48h ; 'H'
0x18000b667  mov     [rbp+var_48], rsi
0x18000b66b  mov     [rbp+var_40], r13
0x18000b66f  mov     [rbp+var_30], 0
0x18000b676  mov     [rbp+lpProcName], 0
0x18000b67e  mov     [rbp+var_20], 0
0x18000b686  mov     [rbp+var_18], 0
0x18000b68e  mov     [rbp+var_10], 0
0x18000b695  test    al, al
0x18000b697  jnz     short loc_18000B6F9
0x18000b699  test    cs:dword_18000D160, 1000h
0x18000b6a3  lea     rax, [rbp+var_50]
0x18000b6a7  mov     [rbp+Arguments], rax
0x18000b6ab  mov     dword ptr [rbp+flOldProtect], 0
0x18000b6b2  jz      short loc_18000B6DE
0x18000b6b4  mov     rcx, rbx; SRWLock
0x18000b6b7  call    cs:__imp_AcquireSRWLockExclusive
0x18000b6bd  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000b6c4  jnz     short loc_18000B6D5
0x18000b6c6  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000b6cc  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18000b6d0  call    DloadProtectSection
0x18000b6d5  mov     rcx, rbx; SRWLock
0x18000b6d8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b6de  lea     r9, [rbp+Arguments]; lpArguments
0x18000b6e2  mov     r8d, edi; nNumberOfArguments
0x18000b6e5  xor     edx, edx; dwExceptionFlags
0x18000b6e7  mov     ecx, 0C06D0057h; dwExceptionCode
0x18000b6ec  call    cs:__imp_RaiseException
0x18000b6f2  xor     eax, eax
0x18000b6f4  jmp     loc_18000BA7B
0x18000b6f9  mov     eax, [rsi+0Ch]
0x18000b6fc  mov     rcx, r13
0x18000b6ff  mov     rbx, [r15]
0x18000b702  sub     rcx, rax
0x18000b705  sub     rcx, rdx
0x18000b708  sar     rcx, 3
0x18000b70c  mov     eax, ecx
0x18000b70e  mov     ecx, [rsi+10h]
0x18000b711  shl     rax, 3
0x18000b715  add     rcx, rax
0x18000b718  mov     [rbp+flOldProtect], rax
0x18000b71c  xor     eax, eax
0x18000b71e  cmp     [rcx+rdx], rax
0x18000b722  setnl   al
0x18000b725  mov     [rbp+var_30], eax
0x18000b728  test    eax, eax
0x18000b72a  jz      short loc_18000B73F
0x18000b72c  mov     eax, [rcx+rdx]
0x18000b72f  lea     rdx, word_180000002
0x18000b736  add     rax, rdx
0x18000b739  mov     [rbp+lpProcName], rax
0x18000b73d  jmp     short loc_18000B746
0x18000b73f  movzx   eax, word ptr [rcx+rdx]
0x18000b743  mov     dword ptr [rbp+lpProcName], eax
0x18000b746  mov     rax, cs:__pfnDliNotifyHook2
0x18000b74d  xor     edi, edi
0x18000b74f  test    rax, rax
0x18000b752  jz      short loc_18000B772
0x18000b754  lea     rdx, [rbp+var_50]
0x18000b758  xor     ecx, ecx
0x18000b75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75f  mov     rdi, rax
0x18000b762  test    rax, rax
0x18000b765  mov     rax, cs:__pfnDliNotifyHook2
0x18000b76c  jnz     loc_18000BA11
0x18000b772  test    rbx, rbx
0x18000b775  jnz     loc_18000B8B0
0x18000b77b  test    rax, rax
0x18000b77e  jz      short loc_18000B798
0x18000b780  lea     rdx, [rbp+var_50]
0x18000b784  lea     ecx, [rbx+1]
0x18000b787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b78c  mov     rbx, rax
0x18000b78f  test    rax, rax
0x18000b792  jnz     loc_18000B847
0x18000b798  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000b79c  xor     r8d, r8d; dwFlags
0x18000b79f  xor     edx, edx; hFile
0x18000b7a1  call    cs:__imp_LoadLibraryExA
0x18000b7a7  mov     rbx, rax
0x18000b7aa  test    rax, rax
0x18000b7ad  jnz     loc_18000B847
0x18000b7b3  call    cs:__imp_GetLastError
0x18000b7b9  mov     [rbp+var_10], eax
0x18000b7bc  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18000b7c3  test    rax, rax
0x18000b7c6  jz      short loc_18000B7DC
0x18000b7c8  lea     rdx, [rbp+var_50]
0x18000b7cc  lea     ecx, [rbx+3]
0x18000b7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7d4  mov     rbx, rax
0x18000b7d7  test    rax, rax
0x18000b7da  jnz     short loc_18000B847
0x18000b7dc  test    cs:dword_18000D160, 1000h
0x18000b7e6  lea     rax, [rbp+var_50]
0x18000b7ea  mov     [rbp+Arguments], rax
0x18000b7ee  mov     dword ptr [rbp+flOldProtect], 0
0x18000b7f5  jz      short loc_18000B829
0x18000b7f7  lea     rcx, DloadSrwLock; SRWLock
0x18000b7fe  call    cs:__imp_AcquireSRWLockExclusive
0x18000b804  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000b80b  jnz     short loc_18000B81C
0x18000b80d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000b813  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18000b817  call    DloadProtectSection
0x18000b81c  lea     rcx, DloadSrwLock; SRWLock
0x18000b823  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b829  xor     edx, edx; dwExceptionFlags
0x18000b82b  lea     r9, [rbp+Arguments]; lpArguments
0x18000b82f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18000b834  lea     r8d, [rdx+1]; nNumberOfArguments
0x18000b838  call    cs:__imp_RaiseException
0x18000b83e  mov     rax, [rbp+var_18]
0x18000b842  jmp     loc_18000BA7B
0x18000b847  xor     eax, eax
0x18000b849  lock cmpxchg [r15], rbx
0x18000b84e  mov     r15, rax
0x18000b851  jnz     short loc_18000B893
0x18000b853  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b857  jz      short loc_18000B8A9
0x18000b859  cmp     dword ptr [rsi+18h], 0
0x18000b85d  jz      short loc_18000B8A9
0x18000b85f  call    cs:__imp_GetProcessHeap
0x18000b865  mov     edx, 8; dwFlags
0x18000b86a  mov     rcx, rax; hHeap
0x18000b86d  lea     r8d, [rdx+8]; dwBytes
0x18000b871  call    cs:__imp_HeapAlloc
0x18000b877  test    rax, rax
0x18000b87a  jz      short loc_18000B8A9
0x18000b87c  mov     [rax+8], rsi
0x18000b880  mov     rcx, cs:__puiHead
0x18000b887  mov     [rax], rcx
0x18000b88a  mov     cs:__puiHead, rax
0x18000b891  jmp     short loc_18000B8A9
0x18000b893  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b897  jz      short loc_18000B8A2
0x18000b899  mov     rcx, rbx; hLibModule
0x18000b89c  call    cs:__imp_FreeLibrary
0x18000b8a2  cmp     rbx, r15
0x18000b8a5  cmovnz  rbx, r15
0x18000b8a9  mov     rax, cs:__pfnDliNotifyHook2
0x18000b8b0  mov     [rbp+var_20], rbx
0x18000b8b4  test    rax, rax
0x18000b8b7  jz      short loc_18000B8D1
0x18000b8b9  lea     rdx, [rbp+var_50]
0x18000b8bd  mov     ecx, 2
0x18000b8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8c7  mov     rdi, rax
0x18000b8ca  mov     rax, cs:__pfnDliNotifyHook2
0x18000b8d1  test    rdi, rdi
0x18000b8d4  jnz     loc_18000BA0D
0x18000b8da  cmp     [rsi+14h], edi
0x18000b8dd  jz      short loc_18000B912
0x18000b8df  cmp     [rsi+1Ch], edi
0x18000b8e2  jz      short loc_18000B912
0x18000b8e4  movsxd  rcx, dword ptr [rbx+3Ch]
0x18000b8e8  cmp     dword ptr [rcx+rbx], 4550h
0x18000b8ef  jnz     short loc_18000B912
0x18000b8f1  mov     edx, [rbp+arg_0]
0x18000b8f4  cmp     [rcx+rbx+8], edx
0x18000b8f8  jnz     short loc_18000B912
0x18000b8fa  cmp     rbx, [rcx+rbx+30h]
0x18000b8ff  jnz     short loc_18000B912
0x18000b901  mov     rdi, [rbp+flOldProtect]
0x18000b905  mov     rdi, [rdi+r12]
0x18000b909  test    rdi, rdi
0x18000b90c  jnz     loc_18000BA0D
0x18000b912  mov     rdx, [rbp+lpProcName]; lpProcName
0x18000b916  mov     rcx, rbx; hModule
0x18000b919  call    cs:__imp_GetProcAddress
0x18000b91f  mov     rdi, rax
0x18000b922  test    rax, rax
0x18000b925  jnz     loc_18000BA06
0x18000b92b  call    cs:__imp_GetLastError
0x18000b931  mov     [rbp+var_10], eax
0x18000b934  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18000b93b  test    rax, rax
0x18000b93e  jz      short loc_18000B958
0x18000b940  lea     rdx, [rbp+var_50]
0x18000b944  lea     ecx, [rdi+4]
0x18000b947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b94c  mov     rdi, rax
0x18000b94f  test    rax, rax
0x18000b952  jnz     loc_18000BA06
0x18000b958  test    cs:dword_18000D160, 1000h
0x18000b962  lea     rax, [rbp+var_50]
0x18000b966  mov     [rbp+Arguments], rax
0x18000b96a  mov     dword ptr [rbp+flOldProtect], 0
0x18000b971  jz      short loc_18000B9A5
0x18000b973  lea     rcx, DloadSrwLock; SRWLock
0x18000b97a  call    cs:__imp_AcquireSRWLockExclusive
0x18000b980  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000b987  jnz     short loc_18000B998
0x18000b989  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000b98f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18000b993  call    DloadProtectSection
0x18000b998  lea     rcx, DloadSrwLock; SRWLock
0x18000b99f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b9a5  xor     edx, edx; dwExceptionFlags
0x18000b9a7  lea     r9, [rbp+Arguments]; lpArguments
0x18000b9ab  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18000b9b0  lea     r8d, [rdx+1]; nNumberOfArguments
0x18000b9b4  call    cs:__imp_RaiseException
0x18000b9ba  test    cs:dword_18000D160, 1000h
0x18000b9c4  jz      short loc_18000BA02
0x18000b9c6  lea     rcx, DloadSrwLock; SRWLock
0x18000b9cd  call    cs:__imp_AcquireSRWLockExclusive
0x18000b9d3  mov     eax, cs:DloadSectionLockCount
0x18000b9d9  inc     eax
0x18000b9db  mov     cs:DloadSectionLockCount, eax
0x18000b9e1  cmp     eax, 1
0x18000b9e4  jnz     short loc_18000B9F5
0x18000b9e6  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000b9ed  lea     ecx, [rax+3]; flNewProtect
0x18000b9f0  call    DloadProtectSection
0x18000b9f5  lea     rcx, DloadSrwLock; SRWLock
0x18000b9fc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba02  mov     rdi, [rbp+var_18]
0x18000ba06  mov     rax, cs:__pfnDliNotifyHook2
0x18000ba0d  mov     [r13+0], rdi
0x18000ba11  test    rax, rax
0x18000ba14  jz      short loc_18000BA33
0x18000ba16  lea     rdx, [rbp+var_50]
0x18000ba1a  mov     [rbp+var_10], 0
0x18000ba21  mov     ecx, 5
0x18000ba26  mov     [rbp+var_20], rbx
0x18000ba2a  mov     [rbp+var_18], rdi
0x18000ba2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba33  test    cs:dword_18000D160, 1000h
0x18000ba3d  mov     dword ptr [rbp+flOldProtect], 0
0x18000ba44  jz      short loc_18000BA78
0x18000ba46  lea     rcx, DloadSrwLock; SRWLock
0x18000ba4d  call    cs:__imp_AcquireSRWLockExclusive
0x18000ba53  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000ba5a  jnz     short loc_18000BA6B
0x18000ba5c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000ba62  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18000ba66  call    DloadProtectSection
0x18000ba6b  lea     rcx, DloadSrwLock; SRWLock
0x18000ba72  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ba78  mov     rax, rdi
0x18000ba7b  add     rsp, 70h
0x18000ba7f  pop     r15
0x18000ba81  pop     r13
0x18000ba83  pop     r12
0x18000ba85  pop     rdi
0x18000ba86  pop     rsi
0x18000ba87  pop     rbx
0x18000ba88  pop     rbp
0x18000ba89  retn
```
