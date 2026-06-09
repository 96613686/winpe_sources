# __delayLoadHelper2

- ea: `0x1800081c0`
- end: `0x180008689`
- name: `__delayLoadHelper2`
- size: `1225`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800094ca`
- `0x180009555`
- `0x18000966c`

## callees

- `0x1800080d0`
- `0x1800081c0`
- `0x18000941c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000849b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000849b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008518`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008518`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800083a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800083a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008207`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800083fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008579`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800085cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000864c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008207`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800082b7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800083fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008579`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800085cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000864c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008231`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800082d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008422`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000859e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800085fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008671`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008231`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800082d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008422`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000859e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800085fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000845e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000845e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008470`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000852a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000852a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008437`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800085b3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800082ec`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008437`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800085b3`

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
  bool v11; // zf
  PfnDliHook v12; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v14; // r15
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v16; // rax
  __int64 v17; // rcx
  struct DelayLoadInfo v18; // [rsp+20h] [rbp-50h] BYREF
  DWORD v19; // [rsp+B0h] [rbp+40h]
  __int64 flOldProtect; // [rsp+B8h] [rbp+48h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+50h] BYREF

  *(&v18.cb + 1) = 0;
  memset_0(&v18, 0, 0x44u);
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  v4 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v6 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v18.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  v7 = a1->grAttrs & 1;
  v19 = dwTimeStamp;
  v18.cb = 72;
  v18.pidd = a1;
  v18.ppfn = a2;
  v18.dlp.fImportByName = 0;
  memset(&v18.dlp.szProcName, 0, 28);
  if ( !(_BYTE)v7 )
  {
    Arguments = (ULONG_PTR)&v18;
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
  v11 = *(__int64 *)((char *)&_ImageBase + v10) < 0;
  v18.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + v10) >= 0LL;
  if ( v11 )
    v18.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + v10);
  else
    v18.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v10);
  v12 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v18), v12 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v12 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v12)(1, &v18)) == 0 )
      {
        Library = LoadLibraryExA(v18.szDll, 0, 0);
        if ( !Library )
        {
          v18.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v18)) == 0 )
          {
            Arguments = (ULONG_PTR)&v18;
            LODWORD(flOldProtect) = 0;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, (PDWORD)&flOldProtect);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v18.pfnCur;
          }
        }
      }
      v14 = _InterlockedCompareExchange64(v4, (signed __int64)Library, 0);
      if ( v14 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v14 )
          Library = (HMODULE)v14;
      }
      else if ( Library != (HMODULE)-1LL )
      {
        if ( a1->rvaUnloadIAT )
        {
          ProcessHeap = GetProcessHeap();
          v16 = (struct UnloadInfo *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          if ( v16 )
          {
            v16->pidd = a1;
            v16->puiNext = _puiHead;
            _puiHead = v16;
          }
        }
      }
      v12 = _pfnDliNotifyHook2;
    }
    v18.hmodCur = Library;
    if ( v12 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v12)(2, &v18);
      v12 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v17 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v17) != 17744)
        || *(_DWORD *)((char *)Library + v17 + 8) != v19
        || Library != *(HMODULE *)((char *)Library + v17 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v6[flOldProtect]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v18.dlp.szProcName);
        if ( !ProcAddress )
        {
          v18.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v18)) == 0 )
          {
            Arguments = (ULONG_PTR)&v18;
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
            ProcAddress = v18.pfnCur;
          }
        }
        v12 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v12 )
  {
    v18.dwLastError = 0;
    v18.hmodCur = Library;
    v18.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v12)(5, &v18);
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
0x1800081c0  push    rbp
0x1800081c2  push    rbx
0x1800081c3  push    rsi
0x1800081c4  push    rdi
0x1800081c5  push    r12
0x1800081c7  push    r13
0x1800081c9  push    r15
0x1800081cb  mov     rbp, rsp
0x1800081ce  sub     rsp, 70h
0x1800081d2  xor     eax, eax
0x1800081d4  mov     r13, rdx
0x1800081d7  mov     rsi, rcx
0x1800081da  mov     [rbp+var_4C], eax
0x1800081dd  xor     edx, edx; Val
0x1800081df  lea     rcx, [rbp+var_50]; void *
0x1800081e3  lea     r8d, [rax+44h]; Size
0x1800081e7  call    memset_0
0x1800081ec  test    cs:dword_18000B0D0, 1000h
0x1800081f6  lea     rbx, DloadSrwLock
0x1800081fd  mov     edi, 1
0x180008202  jz      short loc_180008237
0x180008204  mov     rcx, rbx; SRWLock
0x180008207  call    cs:__imp_AcquireSRWLockExclusive
0x18000820d  mov     eax, cs:DloadSectionLockCount
0x180008213  add     eax, edi
0x180008215  mov     cs:DloadSectionLockCount, eax
0x18000821b  cmp     eax, edi
0x18000821d  jnz     short loc_18000822E
0x18000821f  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180008226  lea     ecx, [rdi+3]; flNewProtect
0x180008229  call    DloadProtectSection
0x18000822e  mov     rcx, rbx; SRWLock
0x180008231  call    cs:__imp_ReleaseSRWLockExclusive
0x180008237  mov     eax, [rsi+4]
0x18000823a  lea     rdx, __ImageBase
0x180008241  mov     r15d, [rsi+8]
0x180008245  add     rax, rdx
0x180008248  mov     r12d, [rsi+14h]
0x18000824c  add     r15, rdx
0x18000824f  mov     ecx, [rsi+1Ch]
0x180008252  add     r12, rdx
0x180008255  mov     [rbp+lpLibFileName], rax
0x180008259  mov     eax, [rsi]
0x18000825b  and     eax, edi
0x18000825d  mov     [rbp+arg_0], ecx
0x180008260  mov     [rbp+var_50], 48h ; 'H'
0x180008267  mov     [rbp+var_48], rsi
0x18000826b  mov     [rbp+var_40], r13
0x18000826f  mov     [rbp+var_30], 0
0x180008276  mov     [rbp+lpProcName], 0
0x18000827e  mov     [rbp+var_20], 0
0x180008286  mov     [rbp+var_18], 0
0x18000828e  mov     [rbp+var_10], 0
0x180008295  test    al, al
0x180008297  jnz     short loc_1800082F9
0x180008299  test    cs:dword_18000B0D0, 1000h
0x1800082a3  lea     rax, [rbp+var_50]
0x1800082a7  mov     [rbp+Arguments], rax
0x1800082ab  mov     dword ptr [rbp+flOldProtect], 0
0x1800082b2  jz      short loc_1800082DE
0x1800082b4  mov     rcx, rbx; SRWLock
0x1800082b7  call    cs:__imp_AcquireSRWLockExclusive
0x1800082bd  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800082c4  jnz     short loc_1800082D5
0x1800082c6  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800082cc  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800082d0  call    DloadProtectSection
0x1800082d5  mov     rcx, rbx; SRWLock
0x1800082d8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800082de  lea     r9, [rbp+Arguments]; lpArguments
0x1800082e2  mov     r8d, edi; nNumberOfArguments
0x1800082e5  xor     edx, edx; dwExceptionFlags
0x1800082e7  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800082ec  call    cs:__imp_RaiseException
0x1800082f2  xor     eax, eax
0x1800082f4  jmp     loc_18000867A
0x1800082f9  mov     eax, [rsi+0Ch]
0x1800082fc  mov     rcx, r13
0x1800082ff  mov     rbx, [r15]
0x180008302  sub     rcx, rax
0x180008305  sub     rcx, rdx
0x180008308  sar     rcx, 3
0x18000830c  mov     eax, ecx
0x18000830e  mov     ecx, [rsi+10h]
0x180008311  shl     rax, 3
0x180008315  add     rcx, rax
0x180008318  mov     [rbp+flOldProtect], rax
0x18000831c  mov     rax, [rcx+rdx]
0x180008320  shr     rax, 3Fh
0x180008324  xor     eax, edi
0x180008326  mov     [rbp+var_30], eax
0x180008329  jz      short loc_18000833E
0x18000832b  mov     eax, [rcx+rdx]
0x18000832e  lea     rdx, word_180000002
0x180008335  add     rax, rdx
0x180008338  mov     [rbp+lpProcName], rax
0x18000833c  jmp     short loc_180008345
0x18000833e  movzx   eax, word ptr [rcx+rdx]
0x180008342  mov     dword ptr [rbp+lpProcName], eax
0x180008345  mov     rax, cs:__pfnDliNotifyHook2
0x18000834c  xor     edi, edi
0x18000834e  test    rax, rax
0x180008351  jz      short loc_180008371
0x180008353  lea     rdx, [rbp+var_50]
0x180008357  xor     ecx, ecx
0x180008359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000835e  mov     rdi, rax
0x180008361  test    rax, rax
0x180008364  mov     rax, cs:__pfnDliNotifyHook2
0x18000836b  jnz     loc_180008610
0x180008371  test    rbx, rbx
0x180008374  jnz     loc_1800084AF
0x18000837a  test    rax, rax
0x18000837d  jz      short loc_180008397
0x18000837f  lea     rdx, [rbp+var_50]
0x180008383  lea     ecx, [rbx+1]
0x180008386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000838b  mov     rbx, rax
0x18000838e  test    rax, rax
0x180008391  jnz     loc_180008446
0x180008397  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000839b  xor     r8d, r8d; dwFlags
0x18000839e  xor     edx, edx; hFile
0x1800083a0  call    cs:__imp_LoadLibraryExA
0x1800083a6  mov     rbx, rax
0x1800083a9  test    rax, rax
0x1800083ac  jnz     loc_180008446
0x1800083b2  call    cs:__imp_GetLastError
0x1800083b8  mov     [rbp+var_10], eax
0x1800083bb  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800083c2  test    rax, rax
0x1800083c5  jz      short loc_1800083DB
0x1800083c7  lea     rdx, [rbp+var_50]
0x1800083cb  lea     ecx, [rbx+3]
0x1800083ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d3  mov     rbx, rax
0x1800083d6  test    rax, rax
0x1800083d9  jnz     short loc_180008446
0x1800083db  test    cs:dword_18000B0D0, 1000h
0x1800083e5  lea     rax, [rbp+var_50]
0x1800083e9  mov     [rbp+Arguments], rax
0x1800083ed  mov     dword ptr [rbp+flOldProtect], 0
0x1800083f4  jz      short loc_180008428
0x1800083f6  lea     rcx, DloadSrwLock; SRWLock
0x1800083fd  call    cs:__imp_AcquireSRWLockExclusive
0x180008403  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18000840a  jnz     short loc_18000841B
0x18000840c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180008412  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180008416  call    DloadProtectSection
0x18000841b  lea     rcx, DloadSrwLock; SRWLock
0x180008422  call    cs:__imp_ReleaseSRWLockExclusive
0x180008428  xor     edx, edx; dwExceptionFlags
0x18000842a  lea     r9, [rbp+Arguments]; lpArguments
0x18000842e  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180008433  lea     r8d, [rdx+1]; nNumberOfArguments
0x180008437  call    cs:__imp_RaiseException
0x18000843d  mov     rax, [rbp+var_18]
0x180008441  jmp     loc_18000867A
0x180008446  xor     eax, eax
0x180008448  lock cmpxchg [r15], rbx
0x18000844d  mov     r15, rax
0x180008450  jnz     short loc_180008492
0x180008452  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008456  jz      short loc_1800084A8
0x180008458  cmp     dword ptr [rsi+18h], 0
0x18000845c  jz      short loc_1800084A8
0x18000845e  call    cs:__imp_GetProcessHeap
0x180008464  mov     edx, 8; dwFlags
0x180008469  mov     rcx, rax; hHeap
0x18000846c  lea     r8d, [rdx+8]; dwBytes
0x180008470  call    cs:__imp_HeapAlloc
0x180008476  test    rax, rax
0x180008479  jz      short loc_1800084A8
0x18000847b  mov     [rax+8], rsi
0x18000847f  mov     rcx, cs:__puiHead
0x180008486  mov     [rax], rcx
0x180008489  mov     cs:__puiHead, rax
0x180008490  jmp     short loc_1800084A8
0x180008492  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180008496  jz      short loc_1800084A1
0x180008498  mov     rcx, rbx; hLibModule
0x18000849b  call    cs:__imp_FreeLibrary
0x1800084a1  cmp     rbx, r15
0x1800084a4  cmovnz  rbx, r15
0x1800084a8  mov     rax, cs:__pfnDliNotifyHook2
0x1800084af  mov     [rbp+var_20], rbx
0x1800084b3  test    rax, rax
0x1800084b6  jz      short loc_1800084D0
0x1800084b8  lea     rdx, [rbp+var_50]
0x1800084bc  mov     ecx, 2
0x1800084c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084c6  mov     rdi, rax
0x1800084c9  mov     rax, cs:__pfnDliNotifyHook2
0x1800084d0  test    rdi, rdi
0x1800084d3  jnz     loc_18000860C
0x1800084d9  cmp     [rsi+14h], edi
0x1800084dc  jz      short loc_180008511
0x1800084de  cmp     [rsi+1Ch], edi
0x1800084e1  jz      short loc_180008511
0x1800084e3  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800084e7  cmp     dword ptr [rcx+rbx], 4550h
0x1800084ee  jnz     short loc_180008511
0x1800084f0  mov     edx, [rbp+arg_0]
0x1800084f3  cmp     [rcx+rbx+8], edx
0x1800084f7  jnz     short loc_180008511
0x1800084f9  cmp     rbx, [rcx+rbx+30h]
0x1800084fe  jnz     short loc_180008511
0x180008500  mov     rdi, [rbp+flOldProtect]
0x180008504  mov     rdi, [rdi+r12]
0x180008508  test    rdi, rdi
0x18000850b  jnz     loc_18000860C
0x180008511  mov     rdx, [rbp+lpProcName]; lpProcName
0x180008515  mov     rcx, rbx; hModule
0x180008518  call    cs:__imp_GetProcAddress
0x18000851e  mov     rdi, rax
0x180008521  test    rax, rax
0x180008524  jnz     loc_180008605
0x18000852a  call    cs:__imp_GetLastError
0x180008530  mov     [rbp+var_10], eax
0x180008533  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18000853a  test    rax, rax
0x18000853d  jz      short loc_180008557
0x18000853f  lea     rdx, [rbp+var_50]
0x180008543  lea     ecx, [rdi+4]
0x180008546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000854b  mov     rdi, rax
0x18000854e  test    rax, rax
0x180008551  jnz     loc_180008605
0x180008557  test    cs:dword_18000B0D0, 1000h
0x180008561  lea     rax, [rbp+var_50]
0x180008565  mov     [rbp+Arguments], rax
0x180008569  mov     dword ptr [rbp+flOldProtect], 0
0x180008570  jz      short loc_1800085A4
0x180008572  lea     rcx, DloadSrwLock; SRWLock
0x180008579  call    cs:__imp_AcquireSRWLockExclusive
0x18000857f  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180008586  jnz     short loc_180008597
0x180008588  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000858e  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180008592  call    DloadProtectSection
0x180008597  lea     rcx, DloadSrwLock; SRWLock
0x18000859e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800085a4  xor     edx, edx; dwExceptionFlags
0x1800085a6  lea     r9, [rbp+Arguments]; lpArguments
0x1800085aa  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800085af  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800085b3  call    cs:__imp_RaiseException
0x1800085b9  test    cs:dword_18000B0D0, 1000h
0x1800085c3  jz      short loc_180008601
0x1800085c5  lea     rcx, DloadSrwLock; SRWLock
0x1800085cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800085d2  mov     eax, cs:DloadSectionLockCount
0x1800085d8  inc     eax
0x1800085da  mov     cs:DloadSectionLockCount, eax
0x1800085e0  cmp     eax, 1
0x1800085e3  jnz     short loc_1800085F4
0x1800085e5  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800085ec  lea     ecx, [rax+3]; flNewProtect
0x1800085ef  call    DloadProtectSection
0x1800085f4  lea     rcx, DloadSrwLock; SRWLock
0x1800085fb  call    cs:__imp_ReleaseSRWLockExclusive
0x180008601  mov     rdi, [rbp+var_18]
0x180008605  mov     rax, cs:__pfnDliNotifyHook2
0x18000860c  mov     [r13+0], rdi
0x180008610  test    rax, rax
0x180008613  jz      short loc_180008632
0x180008615  lea     rdx, [rbp+var_50]
0x180008619  mov     [rbp+var_10], 0
0x180008620  mov     ecx, 5
0x180008625  mov     [rbp+var_20], rbx
0x180008629  mov     [rbp+var_18], rdi
0x18000862d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008632  test    cs:dword_18000B0D0, 1000h
0x18000863c  mov     dword ptr [rbp+flOldProtect], 0
0x180008643  jz      short loc_180008677
0x180008645  lea     rcx, DloadSrwLock; SRWLock
0x18000864c  call    cs:__imp_AcquireSRWLockExclusive
0x180008652  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180008659  jnz     short loc_18000866A
0x18000865b  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180008661  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180008665  call    DloadProtectSection
0x18000866a  lea     rcx, DloadSrwLock; SRWLock
0x180008671  call    cs:__imp_ReleaseSRWLockExclusive
0x180008677  mov     rax, rdi
0x18000867a  add     rsp, 70h
0x18000867e  pop     r15
0x180008680  pop     r13
0x180008682  pop     r12
0x180008684  pop     rdi
0x180008685  pop     rsi
0x180008686  pop     rbx
0x180008687  pop     rbp
0x180008688  retn
```
