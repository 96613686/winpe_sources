# __delayLoadHelper2

- ea: `0x180082850`
- end: `0x180082d1a`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800072b5`
- `0x18000739a`
- `0x180007425`

## callees

- `0x180007018`
- `0x180082768`
- `0x180082850`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180082a31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180082a31`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082b2c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082b2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180082ba9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180082ba9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800828c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082968`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082ab3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082c2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082c8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082d02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800828c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082968`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082ab3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082c2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082c8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082d02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082897`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082947`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082a8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082c0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082c5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082cdd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082897`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082947`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082a8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082c0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082c5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180082cdd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082b01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180082b01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082aef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180082aef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008297c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180082ac8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180082c44`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008297c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180082ac8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180082c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082bbb`

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
0x180082850  push    rbp
0x180082852  push    rbx
0x180082853  push    rsi
0x180082854  push    rdi
0x180082855  push    r12
0x180082857  push    r13
0x180082859  push    r15
0x18008285b  mov     rbp, rsp
0x18008285e  sub     rsp, 70h
0x180082862  xor     eax, eax
0x180082864  mov     r13, rdx
0x180082867  mov     rsi, rcx
0x18008286a  mov     [rbp+var_4C], eax
0x18008286d  xor     edx, edx; Val
0x18008286f  lea     rcx, [rbp+var_50]; void *
0x180082873  lea     r8d, [rax+44h]; Size
0x180082877  call    memset_0
0x18008287c  test    cs:dword_18008A0F0, 1000h
0x180082886  lea     rbx, DloadSrwLock
0x18008288d  mov     edi, 1
0x180082892  jz      short loc_1800828C7
0x180082894  mov     rcx, rbx; SRWLock
0x180082897  call    cs:__imp_AcquireSRWLockExclusive
0x18008289d  mov     eax, cs:DloadSectionLockCount
0x1800828a3  add     eax, edi
0x1800828a5  mov     cs:DloadSectionLockCount, eax
0x1800828ab  cmp     eax, edi
0x1800828ad  jnz     short loc_1800828BE
0x1800828af  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800828b6  lea     ecx, [rdi+3]; flNewProtect
0x1800828b9  call    DloadProtectSection
0x1800828be  mov     rcx, rbx; SRWLock
0x1800828c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800828c7  mov     eax, [rsi+4]
0x1800828ca  lea     rdx, __ImageBase
0x1800828d1  mov     r15d, [rsi+8]
0x1800828d5  add     rax, rdx
0x1800828d8  mov     r12d, [rsi+14h]
0x1800828dc  add     r15, rdx
0x1800828df  mov     ecx, [rsi+1Ch]
0x1800828e2  add     r12, rdx
0x1800828e5  mov     [rbp+lpLibFileName], rax
0x1800828e9  mov     eax, [rsi]
0x1800828eb  and     eax, edi
0x1800828ed  mov     [rbp+arg_0], ecx
0x1800828f0  mov     [rbp+var_50], 48h ; 'H'
0x1800828f7  mov     [rbp+var_48], rsi
0x1800828fb  mov     [rbp+var_40], r13
0x1800828ff  mov     [rbp+var_30], 0
0x180082906  mov     [rbp+lpProcName], 0
0x18008290e  mov     [rbp+var_20], 0
0x180082916  mov     [rbp+var_18], 0
0x18008291e  mov     [rbp+var_10], 0
0x180082925  test    al, al
0x180082927  jnz     short loc_180082989
0x180082929  test    cs:dword_18008A0F0, 1000h
0x180082933  lea     rax, [rbp+var_50]
0x180082937  mov     [rbp+Arguments], rax
0x18008293b  mov     dword ptr [rbp+flOldProtect], 0
0x180082942  jz      short loc_18008296E
0x180082944  mov     rcx, rbx; SRWLock
0x180082947  call    cs:__imp_AcquireSRWLockExclusive
0x18008294d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180082954  jnz     short loc_180082965
0x180082956  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18008295c  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180082960  call    DloadProtectSection
0x180082965  mov     rcx, rbx; SRWLock
0x180082968  call    cs:__imp_ReleaseSRWLockExclusive
0x18008296e  lea     r9, [rbp+Arguments]; lpArguments
0x180082972  mov     r8d, edi; nNumberOfArguments
0x180082975  xor     edx, edx; dwExceptionFlags
0x180082977  mov     ecx, 0C06D0057h; dwExceptionCode
0x18008297c  call    cs:__imp_RaiseException
0x180082982  xor     eax, eax
0x180082984  jmp     loc_180082D0B
0x180082989  mov     eax, [rsi+0Ch]
0x18008298c  mov     rcx, r13
0x18008298f  mov     rbx, [r15]
0x180082992  sub     rcx, rax
0x180082995  sub     rcx, rdx
0x180082998  sar     rcx, 3
0x18008299c  mov     eax, ecx
0x18008299e  mov     ecx, [rsi+10h]
0x1800829a1  shl     rax, 3
0x1800829a5  add     rcx, rax
0x1800829a8  mov     [rbp+flOldProtect], rax
0x1800829ac  xor     eax, eax
0x1800829ae  cmp     [rcx+rdx], rax
0x1800829b2  setnl   al
0x1800829b5  mov     [rbp+var_30], eax
0x1800829b8  test    eax, eax
0x1800829ba  jz      short loc_1800829CF
0x1800829bc  mov     eax, [rcx+rdx]
0x1800829bf  lea     rdx, word_180000002
0x1800829c6  add     rax, rdx
0x1800829c9  mov     [rbp+lpProcName], rax
0x1800829cd  jmp     short loc_1800829D6
0x1800829cf  movzx   eax, word ptr [rcx+rdx]
0x1800829d3  mov     dword ptr [rbp+lpProcName], eax
0x1800829d6  mov     rax, cs:__pfnDliNotifyHook2
0x1800829dd  xor     edi, edi
0x1800829df  test    rax, rax
0x1800829e2  jz      short loc_180082A02
0x1800829e4  lea     rdx, [rbp+var_50]
0x1800829e8  xor     ecx, ecx
0x1800829ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800829ef  mov     rdi, rax
0x1800829f2  test    rax, rax
0x1800829f5  mov     rax, cs:__pfnDliNotifyHook2
0x1800829fc  jnz     loc_180082CA1
0x180082a02  test    rbx, rbx
0x180082a05  jnz     loc_180082B40
0x180082a0b  test    rax, rax
0x180082a0e  jz      short loc_180082A28
0x180082a10  lea     rdx, [rbp+var_50]
0x180082a14  lea     ecx, [rbx+1]
0x180082a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a1c  mov     rbx, rax
0x180082a1f  test    rax, rax
0x180082a22  jnz     loc_180082AD7
0x180082a28  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180082a2c  xor     r8d, r8d; dwFlags
0x180082a2f  xor     edx, edx; hFile
0x180082a31  call    cs:__imp_LoadLibraryExA
0x180082a37  mov     rbx, rax
0x180082a3a  test    rax, rax
0x180082a3d  jnz     loc_180082AD7
0x180082a43  call    cs:__imp_GetLastError
0x180082a49  mov     [rbp+var_10], eax
0x180082a4c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180082a53  test    rax, rax
0x180082a56  jz      short loc_180082A6C
0x180082a58  lea     rdx, [rbp+var_50]
0x180082a5c  lea     ecx, [rbx+3]
0x180082a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a64  mov     rbx, rax
0x180082a67  test    rax, rax
0x180082a6a  jnz     short loc_180082AD7
0x180082a6c  test    cs:dword_18008A0F0, 1000h
0x180082a76  lea     rax, [rbp+var_50]
0x180082a7a  mov     [rbp+Arguments], rax
0x180082a7e  mov     dword ptr [rbp+flOldProtect], 0
0x180082a85  jz      short loc_180082AB9
0x180082a87  lea     rcx, DloadSrwLock; SRWLock
0x180082a8e  call    cs:__imp_AcquireSRWLockExclusive
0x180082a94  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180082a9b  jnz     short loc_180082AAC
0x180082a9d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180082aa3  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180082aa7  call    DloadProtectSection
0x180082aac  lea     rcx, DloadSrwLock; SRWLock
0x180082ab3  call    cs:__imp_ReleaseSRWLockExclusive
0x180082ab9  xor     edx, edx; dwExceptionFlags
0x180082abb  lea     r9, [rbp+Arguments]; lpArguments
0x180082abf  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180082ac4  lea     r8d, [rdx+1]; nNumberOfArguments
0x180082ac8  call    cs:__imp_RaiseException
0x180082ace  mov     rax, [rbp+var_18]
0x180082ad2  jmp     loc_180082D0B
0x180082ad7  xor     eax, eax
0x180082ad9  lock cmpxchg [r15], rbx
0x180082ade  mov     r15, rax
0x180082ae1  jnz     short loc_180082B23
0x180082ae3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180082ae7  jz      short loc_180082B39
0x180082ae9  cmp     dword ptr [rsi+18h], 0
0x180082aed  jz      short loc_180082B39
0x180082aef  call    cs:__imp_GetProcessHeap
0x180082af5  mov     edx, 8; dwFlags
0x180082afa  mov     rcx, rax; hHeap
0x180082afd  lea     r8d, [rdx+8]; dwBytes
0x180082b01  call    cs:__imp_HeapAlloc
0x180082b07  test    rax, rax
0x180082b0a  jz      short loc_180082B39
0x180082b0c  mov     [rax+8], rsi
0x180082b10  mov     rcx, cs:__puiHead
0x180082b17  mov     [rax], rcx
0x180082b1a  mov     cs:__puiHead, rax
0x180082b21  jmp     short loc_180082B39
0x180082b23  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180082b27  jz      short loc_180082B32
0x180082b29  mov     rcx, rbx; hLibModule
0x180082b2c  call    cs:__imp_FreeLibrary
0x180082b32  cmp     rbx, r15
0x180082b35  cmovnz  rbx, r15
0x180082b39  mov     rax, cs:__pfnDliNotifyHook2
0x180082b40  mov     [rbp+var_20], rbx
0x180082b44  test    rax, rax
0x180082b47  jz      short loc_180082B61
0x180082b49  lea     rdx, [rbp+var_50]
0x180082b4d  mov     ecx, 2
0x180082b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b57  mov     rdi, rax
0x180082b5a  mov     rax, cs:__pfnDliNotifyHook2
0x180082b61  test    rdi, rdi
0x180082b64  jnz     loc_180082C9D
0x180082b6a  cmp     [rsi+14h], edi
0x180082b6d  jz      short loc_180082BA2
0x180082b6f  cmp     [rsi+1Ch], edi
0x180082b72  jz      short loc_180082BA2
0x180082b74  movsxd  rcx, dword ptr [rbx+3Ch]
0x180082b78  cmp     dword ptr [rcx+rbx], 4550h
0x180082b7f  jnz     short loc_180082BA2
0x180082b81  mov     edx, [rbp+arg_0]
0x180082b84  cmp     [rcx+rbx+8], edx
0x180082b88  jnz     short loc_180082BA2
0x180082b8a  cmp     rbx, [rcx+rbx+30h]
0x180082b8f  jnz     short loc_180082BA2
0x180082b91  mov     rdi, [rbp+flOldProtect]
0x180082b95  mov     rdi, [rdi+r12]
0x180082b99  test    rdi, rdi
0x180082b9c  jnz     loc_180082C9D
0x180082ba2  mov     rdx, [rbp+lpProcName]; lpProcName
0x180082ba6  mov     rcx, rbx; hModule
0x180082ba9  call    cs:__imp_GetProcAddress
0x180082baf  mov     rdi, rax
0x180082bb2  test    rax, rax
0x180082bb5  jnz     loc_180082C96
0x180082bbb  call    cs:__imp_GetLastError
0x180082bc1  mov     [rbp+var_10], eax
0x180082bc4  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180082bcb  test    rax, rax
0x180082bce  jz      short loc_180082BE8
0x180082bd0  lea     rdx, [rbp+var_50]
0x180082bd4  lea     ecx, [rdi+4]
0x180082bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082bdc  mov     rdi, rax
0x180082bdf  test    rax, rax
0x180082be2  jnz     loc_180082C96
0x180082be8  test    cs:dword_18008A0F0, 1000h
0x180082bf2  lea     rax, [rbp+var_50]
0x180082bf6  mov     [rbp+Arguments], rax
0x180082bfa  mov     dword ptr [rbp+flOldProtect], 0
0x180082c01  jz      short loc_180082C35
0x180082c03  lea     rcx, DloadSrwLock; SRWLock
0x180082c0a  call    cs:__imp_AcquireSRWLockExclusive
0x180082c10  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180082c17  jnz     short loc_180082C28
0x180082c19  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180082c1f  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180082c23  call    DloadProtectSection
0x180082c28  lea     rcx, DloadSrwLock; SRWLock
0x180082c2f  call    cs:__imp_ReleaseSRWLockExclusive
0x180082c35  xor     edx, edx; dwExceptionFlags
0x180082c37  lea     r9, [rbp+Arguments]; lpArguments
0x180082c3b  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180082c40  lea     r8d, [rdx+1]; nNumberOfArguments
0x180082c44  call    cs:__imp_RaiseException
0x180082c4a  test    cs:dword_18008A0F0, 1000h
0x180082c54  jz      short loc_180082C92
0x180082c56  lea     rcx, DloadSrwLock; SRWLock
0x180082c5d  call    cs:__imp_AcquireSRWLockExclusive
0x180082c63  mov     eax, cs:DloadSectionLockCount
0x180082c69  inc     eax
0x180082c6b  mov     cs:DloadSectionLockCount, eax
0x180082c71  cmp     eax, 1
0x180082c74  jnz     short loc_180082C85
0x180082c76  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180082c7d  lea     ecx, [rax+3]; flNewProtect
0x180082c80  call    DloadProtectSection
0x180082c85  lea     rcx, DloadSrwLock; SRWLock
0x180082c8c  call    cs:__imp_ReleaseSRWLockExclusive
0x180082c92  mov     rdi, [rbp+var_18]
0x180082c96  mov     rax, cs:__pfnDliNotifyHook2
0x180082c9d  mov     [r13+0], rdi
0x180082ca1  test    rax, rax
0x180082ca4  jz      short loc_180082CC3
0x180082ca6  lea     rdx, [rbp+var_50]
0x180082caa  mov     [rbp+var_10], 0
0x180082cb1  mov     ecx, 5
0x180082cb6  mov     [rbp+var_20], rbx
0x180082cba  mov     [rbp+var_18], rdi
0x180082cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082cc3  test    cs:dword_18008A0F0, 1000h
0x180082ccd  mov     dword ptr [rbp+flOldProtect], 0
0x180082cd4  jz      short loc_180082D08
0x180082cd6  lea     rcx, DloadSrwLock; SRWLock
0x180082cdd  call    cs:__imp_AcquireSRWLockExclusive
0x180082ce3  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180082cea  jnz     short loc_180082CFB
0x180082cec  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180082cf2  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180082cf6  call    DloadProtectSection
0x180082cfb  lea     rcx, DloadSrwLock; SRWLock
0x180082d02  call    cs:__imp_ReleaseSRWLockExclusive
0x180082d08  mov     rax, rdi
0x180082d0b  add     rsp, 70h
0x180082d0f  pop     r15
0x180082d11  pop     r13
0x180082d13  pop     r12
0x180082d15  pop     rdi
0x180082d16  pop     rsi
0x180082d17  pop     rbx
0x180082d18  pop     rbp
0x180082d19  retn
```
