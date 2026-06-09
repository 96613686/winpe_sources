# __delayLoadHelper2

- ea: `0x18000e1a0`
- end: `0x18000e66a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `8`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800028c9`
- `0x180002954`
- `0x180002a27`
- `0x180002b06`
- `0x180002bfd`
- `0x180002cd5`
- `0x180002d84`
- `0x180002e1b`

## callees

- `0x180002802`
- `0x18000e0bc`
- `0x18000e1a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e381`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000e381`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e47c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e47c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e4f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e4f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e211`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e403`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e57f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e5dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e652`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e211`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e2b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e403`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e57f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e5dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e652`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e1e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e297`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e3de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e55a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e5ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e62d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e1e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e297`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e3de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e55a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e5ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e62d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e451`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000e451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e43f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e43f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e50b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e50b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e2cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e418`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e594`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e2cc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e418`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e594`

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
0x18000e1a0  push    rbp
0x18000e1a2  push    rbx
0x18000e1a3  push    rsi
0x18000e1a4  push    rdi
0x18000e1a5  push    r12
0x18000e1a7  push    r13
0x18000e1a9  push    r15
0x18000e1ab  mov     rbp, rsp
0x18000e1ae  sub     rsp, 70h
0x18000e1b2  xor     eax, eax
0x18000e1b4  mov     r13, rdx
0x18000e1b7  mov     rsi, rcx
0x18000e1ba  mov     [rbp+var_4C], eax
0x18000e1bd  xor     edx, edx; Val
0x18000e1bf  lea     rcx, [rbp+var_50]; void *
0x18000e1c3  lea     r8d, [rax+44h]; Size
0x18000e1c7  call    memset_0
0x18000e1cc  test    cs:dword_180011160, 1000h
0x18000e1d6  lea     rbx, DloadSrwLock
0x18000e1dd  mov     edi, 1
0x18000e1e2  jz      short loc_18000E217
0x18000e1e4  mov     rcx, rbx; SRWLock
0x18000e1e7  call    cs:__imp_AcquireSRWLockExclusive
0x18000e1ed  mov     eax, cs:DloadSectionLockCount
0x18000e1f3  add     eax, edi
0x18000e1f5  mov     cs:DloadSectionLockCount, eax
0x18000e1fb  cmp     eax, edi
0x18000e1fd  jnz     short loc_18000E20E
0x18000e1ff  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000e206  lea     ecx, [rdi+3]; flNewProtect
0x18000e209  call    DloadProtectSection
0x18000e20e  mov     rcx, rbx; SRWLock
0x18000e211  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e217  mov     eax, [rsi+4]
0x18000e21a  lea     rdx, __ImageBase
0x18000e221  mov     r15d, [rsi+8]
0x18000e225  add     rax, rdx
0x18000e228  mov     r12d, [rsi+14h]
0x18000e22c  add     r15, rdx
0x18000e22f  mov     ecx, [rsi+1Ch]
0x18000e232  add     r12, rdx
0x18000e235  mov     [rbp+lpLibFileName], rax
0x18000e239  mov     eax, [rsi]
0x18000e23b  and     eax, edi
0x18000e23d  mov     [rbp+arg_0], ecx
0x18000e240  mov     [rbp+var_50], 48h ; 'H'
0x18000e247  mov     [rbp+var_48], rsi
0x18000e24b  mov     [rbp+var_40], r13
0x18000e24f  mov     [rbp+var_30], 0
0x18000e256  mov     [rbp+lpProcName], 0
0x18000e25e  mov     [rbp+var_20], 0
0x18000e266  mov     [rbp+var_18], 0
0x18000e26e  mov     [rbp+var_10], 0
0x18000e275  test    al, al
0x18000e277  jnz     short loc_18000E2D9
0x18000e279  test    cs:dword_180011160, 1000h
0x18000e283  lea     rax, [rbp+var_50]
0x18000e287  mov     [rbp+Arguments], rax
0x18000e28b  mov     dword ptr [rbp+flOldProtect], 0
0x18000e292  jz      short loc_18000E2BE
0x18000e294  mov     rcx, rbx; SRWLock
0x18000e297  call    cs:__imp_AcquireSRWLockExclusive
0x18000e29d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000e2a4  jnz     short loc_18000E2B5
0x18000e2a6  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000e2ac  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18000e2b0  call    DloadProtectSection
0x18000e2b5  mov     rcx, rbx; SRWLock
0x18000e2b8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e2be  lea     r9, [rbp+Arguments]; lpArguments
0x18000e2c2  mov     r8d, edi; nNumberOfArguments
0x18000e2c5  xor     edx, edx; dwExceptionFlags
0x18000e2c7  mov     ecx, 0C06D0057h; dwExceptionCode
0x18000e2cc  call    cs:__imp_RaiseException
0x18000e2d2  xor     eax, eax
0x18000e2d4  jmp     loc_18000E65B
0x18000e2d9  mov     eax, [rsi+0Ch]
0x18000e2dc  mov     rcx, r13
0x18000e2df  mov     rbx, [r15]
0x18000e2e2  sub     rcx, rax
0x18000e2e5  sub     rcx, rdx
0x18000e2e8  sar     rcx, 3
0x18000e2ec  mov     eax, ecx
0x18000e2ee  mov     ecx, [rsi+10h]
0x18000e2f1  shl     rax, 3
0x18000e2f5  add     rcx, rax
0x18000e2f8  mov     [rbp+flOldProtect], rax
0x18000e2fc  xor     eax, eax
0x18000e2fe  cmp     [rcx+rdx], rax
0x18000e302  setnl   al
0x18000e305  mov     [rbp+var_30], eax
0x18000e308  test    eax, eax
0x18000e30a  jz      short loc_18000E31F
0x18000e30c  mov     eax, [rcx+rdx]
0x18000e30f  lea     rdx, word_180000002
0x18000e316  add     rax, rdx
0x18000e319  mov     [rbp+lpProcName], rax
0x18000e31d  jmp     short loc_18000E326
0x18000e31f  movzx   eax, word ptr [rcx+rdx]
0x18000e323  mov     dword ptr [rbp+lpProcName], eax
0x18000e326  mov     rax, cs:__pfnDliNotifyHook2
0x18000e32d  xor     edi, edi
0x18000e32f  test    rax, rax
0x18000e332  jz      short loc_18000E352
0x18000e334  lea     rdx, [rbp+var_50]
0x18000e338  xor     ecx, ecx
0x18000e33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e33f  mov     rdi, rax
0x18000e342  test    rax, rax
0x18000e345  mov     rax, cs:__pfnDliNotifyHook2
0x18000e34c  jnz     loc_18000E5F1
0x18000e352  test    rbx, rbx
0x18000e355  jnz     loc_18000E490
0x18000e35b  test    rax, rax
0x18000e35e  jz      short loc_18000E378
0x18000e360  lea     rdx, [rbp+var_50]
0x18000e364  lea     ecx, [rbx+1]
0x18000e367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e36c  mov     rbx, rax
0x18000e36f  test    rax, rax
0x18000e372  jnz     loc_18000E427
0x18000e378  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000e37c  xor     r8d, r8d; dwFlags
0x18000e37f  xor     edx, edx; hFile
0x18000e381  call    cs:__imp_LoadLibraryExA
0x18000e387  mov     rbx, rax
0x18000e38a  test    rax, rax
0x18000e38d  jnz     loc_18000E427
0x18000e393  call    cs:__imp_GetLastError
0x18000e399  mov     [rbp+var_10], eax
0x18000e39c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18000e3a3  test    rax, rax
0x18000e3a6  jz      short loc_18000E3BC
0x18000e3a8  lea     rdx, [rbp+var_50]
0x18000e3ac  lea     ecx, [rbx+3]
0x18000e3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3b4  mov     rbx, rax
0x18000e3b7  test    rax, rax
0x18000e3ba  jnz     short loc_18000E427
0x18000e3bc  test    cs:dword_180011160, 1000h
0x18000e3c6  lea     rax, [rbp+var_50]
0x18000e3ca  mov     [rbp+Arguments], rax
0x18000e3ce  mov     dword ptr [rbp+flOldProtect], 0
0x18000e3d5  jz      short loc_18000E409
0x18000e3d7  lea     rcx, DloadSrwLock; SRWLock
0x18000e3de  call    cs:__imp_AcquireSRWLockExclusive
0x18000e3e4  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000e3eb  jnz     short loc_18000E3FC
0x18000e3ed  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000e3f3  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18000e3f7  call    DloadProtectSection
0x18000e3fc  lea     rcx, DloadSrwLock; SRWLock
0x18000e403  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e409  xor     edx, edx; dwExceptionFlags
0x18000e40b  lea     r9, [rbp+Arguments]; lpArguments
0x18000e40f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18000e414  lea     r8d, [rdx+1]; nNumberOfArguments
0x18000e418  call    cs:__imp_RaiseException
0x18000e41e  mov     rax, [rbp+var_18]
0x18000e422  jmp     loc_18000E65B
0x18000e427  xor     eax, eax
0x18000e429  lock cmpxchg [r15], rbx
0x18000e42e  mov     r15, rax
0x18000e431  jnz     short loc_18000E473
0x18000e433  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e437  jz      short loc_18000E489
0x18000e439  cmp     dword ptr [rsi+18h], 0
0x18000e43d  jz      short loc_18000E489
0x18000e43f  call    cs:__imp_GetProcessHeap
0x18000e445  mov     edx, 8; dwFlags
0x18000e44a  mov     rcx, rax; hHeap
0x18000e44d  lea     r8d, [rdx+8]; dwBytes
0x18000e451  call    cs:__imp_HeapAlloc
0x18000e457  test    rax, rax
0x18000e45a  jz      short loc_18000E489
0x18000e45c  mov     [rax+8], rsi
0x18000e460  mov     rcx, cs:__puiHead
0x18000e467  mov     [rax], rcx
0x18000e46a  mov     cs:__puiHead, rax
0x18000e471  jmp     short loc_18000E489
0x18000e473  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000e477  jz      short loc_18000E482
0x18000e479  mov     rcx, rbx; hLibModule
0x18000e47c  call    cs:__imp_FreeLibrary
0x18000e482  cmp     rbx, r15
0x18000e485  cmovnz  rbx, r15
0x18000e489  mov     rax, cs:__pfnDliNotifyHook2
0x18000e490  mov     [rbp+var_20], rbx
0x18000e494  test    rax, rax
0x18000e497  jz      short loc_18000E4B1
0x18000e499  lea     rdx, [rbp+var_50]
0x18000e49d  mov     ecx, 2
0x18000e4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4a7  mov     rdi, rax
0x18000e4aa  mov     rax, cs:__pfnDliNotifyHook2
0x18000e4b1  test    rdi, rdi
0x18000e4b4  jnz     loc_18000E5ED
0x18000e4ba  cmp     [rsi+14h], edi
0x18000e4bd  jz      short loc_18000E4F2
0x18000e4bf  cmp     [rsi+1Ch], edi
0x18000e4c2  jz      short loc_18000E4F2
0x18000e4c4  movsxd  rcx, dword ptr [rbx+3Ch]
0x18000e4c8  cmp     dword ptr [rcx+rbx], 4550h
0x18000e4cf  jnz     short loc_18000E4F2
0x18000e4d1  mov     edx, [rbp+arg_0]
0x18000e4d4  cmp     [rcx+rbx+8], edx
0x18000e4d8  jnz     short loc_18000E4F2
0x18000e4da  cmp     rbx, [rcx+rbx+30h]
0x18000e4df  jnz     short loc_18000E4F2
0x18000e4e1  mov     rdi, [rbp+flOldProtect]
0x18000e4e5  mov     rdi, [rdi+r12]
0x18000e4e9  test    rdi, rdi
0x18000e4ec  jnz     loc_18000E5ED
0x18000e4f2  mov     rdx, [rbp+lpProcName]; lpProcName
0x18000e4f6  mov     rcx, rbx; hModule
0x18000e4f9  call    cs:__imp_GetProcAddress
0x18000e4ff  mov     rdi, rax
0x18000e502  test    rax, rax
0x18000e505  jnz     loc_18000E5E6
0x18000e50b  call    cs:__imp_GetLastError
0x18000e511  mov     [rbp+var_10], eax
0x18000e514  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18000e51b  test    rax, rax
0x18000e51e  jz      short loc_18000E538
0x18000e520  lea     rdx, [rbp+var_50]
0x18000e524  lea     ecx, [rdi+4]
0x18000e527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e52c  mov     rdi, rax
0x18000e52f  test    rax, rax
0x18000e532  jnz     loc_18000E5E6
0x18000e538  test    cs:dword_180011160, 1000h
0x18000e542  lea     rax, [rbp+var_50]
0x18000e546  mov     [rbp+Arguments], rax
0x18000e54a  mov     dword ptr [rbp+flOldProtect], 0
0x18000e551  jz      short loc_18000E585
0x18000e553  lea     rcx, DloadSrwLock; SRWLock
0x18000e55a  call    cs:__imp_AcquireSRWLockExclusive
0x18000e560  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000e567  jnz     short loc_18000E578
0x18000e569  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000e56f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18000e573  call    DloadProtectSection
0x18000e578  lea     rcx, DloadSrwLock; SRWLock
0x18000e57f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e585  xor     edx, edx; dwExceptionFlags
0x18000e587  lea     r9, [rbp+Arguments]; lpArguments
0x18000e58b  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18000e590  lea     r8d, [rdx+1]; nNumberOfArguments
0x18000e594  call    cs:__imp_RaiseException
0x18000e59a  test    cs:dword_180011160, 1000h
0x18000e5a4  jz      short loc_18000E5E2
0x18000e5a6  lea     rcx, DloadSrwLock; SRWLock
0x18000e5ad  call    cs:__imp_AcquireSRWLockExclusive
0x18000e5b3  mov     eax, cs:DloadSectionLockCount
0x18000e5b9  inc     eax
0x18000e5bb  mov     cs:DloadSectionLockCount, eax
0x18000e5c1  cmp     eax, 1
0x18000e5c4  jnz     short loc_18000E5D5
0x18000e5c6  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000e5cd  lea     ecx, [rax+3]; flNewProtect
0x18000e5d0  call    DloadProtectSection
0x18000e5d5  lea     rcx, DloadSrwLock; SRWLock
0x18000e5dc  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e5e2  mov     rdi, [rbp+var_18]
0x18000e5e6  mov     rax, cs:__pfnDliNotifyHook2
0x18000e5ed  mov     [r13+0], rdi
0x18000e5f1  test    rax, rax
0x18000e5f4  jz      short loc_18000E613
0x18000e5f6  lea     rdx, [rbp+var_50]
0x18000e5fa  mov     [rbp+var_10], 0
0x18000e601  mov     ecx, 5
0x18000e606  mov     [rbp+var_20], rbx
0x18000e60a  mov     [rbp+var_18], rdi
0x18000e60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e613  test    cs:dword_180011160, 1000h
0x18000e61d  mov     dword ptr [rbp+flOldProtect], 0
0x18000e624  jz      short loc_18000E658
0x18000e626  lea     rcx, DloadSrwLock; SRWLock
0x18000e62d  call    cs:__imp_AcquireSRWLockExclusive
0x18000e633  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000e63a  jnz     short loc_18000E64B
0x18000e63c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000e642  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x18000e646  call    DloadProtectSection
0x18000e64b  lea     rcx, DloadSrwLock; SRWLock
0x18000e652  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e658  mov     rax, rdi
0x18000e65b  add     rsp, 70h
0x18000e65f  pop     r15
0x18000e661  pop     r13
0x18000e663  pop     r12
0x18000e665  pop     rdi
0x18000e666  pop     rsi
0x18000e667  pop     rbx
0x18000e668  pop     rbp
0x18000e669  retn
```
