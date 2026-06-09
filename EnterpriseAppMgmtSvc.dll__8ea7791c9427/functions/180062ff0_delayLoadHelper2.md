# __delayLoadHelper2

- ea: `0x180062ff0`
- end: `0x1800634ba`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a0c`
- `0x180002ab5`
- `0x180002bb2`
- `0x180002e35`
- `0x180002ed2`
- `0x180003000`

## callees

- `0x180062f0c`
- `0x180062ff0`
- `0x180066db2`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063349`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180063349`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800631d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800631d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800632cc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800632cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800632a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800632a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006328f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006328f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006335b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006335b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006311c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063268`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800633e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006311c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063268`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800633e4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063061`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063108`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063253`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800633cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006342c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800634a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063061`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063108`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063253`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800633cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006342c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800634a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063037`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800630e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006322e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800633aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800633fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006347d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180063037`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800630e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006322e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800633aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800633fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006347d`

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
0x180062ff0  push    rbp
0x180062ff2  push    rbx
0x180062ff3  push    rsi
0x180062ff4  push    rdi
0x180062ff5  push    r12
0x180062ff7  push    r13
0x180062ff9  push    r15
0x180062ffb  mov     rbp, rsp
0x180062ffe  sub     rsp, 70h
0x180063002  xor     eax, eax
0x180063004  mov     r13, rdx
0x180063007  mov     rsi, rcx
0x18006300a  mov     [rbp+var_4C], eax
0x18006300d  xor     edx, edx; Val
0x18006300f  lea     rcx, [rbp+var_50]; void *
0x180063013  lea     r8d, [rax+44h]; Size
0x180063017  call    memset_0
0x18006301c  test    cs:dword_18006BA70, 1000h
0x180063026  lea     rbx, DloadSrwLock
0x18006302d  mov     edi, 1
0x180063032  jz      short loc_180063067
0x180063034  mov     rcx, rbx; SRWLock
0x180063037  call    cs:__imp_AcquireSRWLockExclusive
0x18006303d  mov     eax, cs:DloadSectionLockCount
0x180063043  add     eax, edi
0x180063045  mov     cs:DloadSectionLockCount, eax
0x18006304b  cmp     eax, edi
0x18006304d  jnz     short loc_18006305E
0x18006304f  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180063056  lea     ecx, [rdi+3]; flNewProtect
0x180063059  call    DloadProtectSection
0x18006305e  mov     rcx, rbx; SRWLock
0x180063061  call    cs:__imp_ReleaseSRWLockExclusive
0x180063067  mov     eax, [rsi+4]
0x18006306a  lea     rdx, __ImageBase
0x180063071  mov     r15d, [rsi+8]
0x180063075  add     rax, rdx
0x180063078  mov     r12d, [rsi+14h]
0x18006307c  add     r15, rdx
0x18006307f  mov     ecx, [rsi+1Ch]
0x180063082  add     r12, rdx
0x180063085  mov     [rbp+lpLibFileName], rax
0x180063089  mov     eax, [rsi]
0x18006308b  and     eax, edi
0x18006308d  mov     [rbp+arg_0], ecx
0x180063090  mov     [rbp+var_50], 48h ; 'H'
0x180063097  mov     [rbp+var_48], rsi
0x18006309b  mov     [rbp+var_40], r13
0x18006309f  mov     [rbp+var_30], 0
0x1800630a6  mov     [rbp+lpProcName], 0
0x1800630ae  mov     [rbp+var_20], 0
0x1800630b6  mov     [rbp+var_18], 0
0x1800630be  mov     [rbp+var_10], 0
0x1800630c5  test    al, al
0x1800630c7  jnz     short loc_180063129
0x1800630c9  test    cs:dword_18006BA70, 1000h
0x1800630d3  lea     rax, [rbp+var_50]
0x1800630d7  mov     [rbp+Arguments], rax
0x1800630db  mov     dword ptr [rbp+flOldProtect], 0
0x1800630e2  jz      short loc_18006310E
0x1800630e4  mov     rcx, rbx; SRWLock
0x1800630e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800630ed  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800630f4  jnz     short loc_180063105
0x1800630f6  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800630fc  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180063100  call    DloadProtectSection
0x180063105  mov     rcx, rbx; SRWLock
0x180063108  call    cs:__imp_ReleaseSRWLockExclusive
0x18006310e  lea     r9, [rbp+Arguments]; lpArguments
0x180063112  mov     r8d, edi; nNumberOfArguments
0x180063115  xor     edx, edx; dwExceptionFlags
0x180063117  mov     ecx, 0C06D0057h; dwExceptionCode
0x18006311c  call    cs:__imp_RaiseException
0x180063122  xor     eax, eax
0x180063124  jmp     loc_1800634AB
0x180063129  mov     eax, [rsi+0Ch]
0x18006312c  mov     rcx, r13
0x18006312f  mov     rbx, [r15]
0x180063132  sub     rcx, rax
0x180063135  sub     rcx, rdx
0x180063138  sar     rcx, 3
0x18006313c  mov     eax, ecx
0x18006313e  mov     ecx, [rsi+10h]
0x180063141  shl     rax, 3
0x180063145  add     rcx, rax
0x180063148  mov     [rbp+flOldProtect], rax
0x18006314c  xor     eax, eax
0x18006314e  cmp     [rcx+rdx], rax
0x180063152  setnl   al
0x180063155  mov     [rbp+var_30], eax
0x180063158  test    eax, eax
0x18006315a  jz      short loc_18006316F
0x18006315c  mov     eax, [rcx+rdx]
0x18006315f  lea     rdx, word_180000002
0x180063166  add     rax, rdx
0x180063169  mov     [rbp+lpProcName], rax
0x18006316d  jmp     short loc_180063176
0x18006316f  movzx   eax, word ptr [rcx+rdx]
0x180063173  mov     dword ptr [rbp+lpProcName], eax
0x180063176  mov     rax, cs:__pfnDliNotifyHook2
0x18006317d  xor     edi, edi
0x18006317f  test    rax, rax
0x180063182  jz      short loc_1800631A2
0x180063184  lea     rdx, [rbp+var_50]
0x180063188  xor     ecx, ecx
0x18006318a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006318f  mov     rdi, rax
0x180063192  test    rax, rax
0x180063195  mov     rax, cs:__pfnDliNotifyHook2
0x18006319c  jnz     loc_180063441
0x1800631a2  test    rbx, rbx
0x1800631a5  jnz     loc_1800632E0
0x1800631ab  test    rax, rax
0x1800631ae  jz      short loc_1800631C8
0x1800631b0  lea     rdx, [rbp+var_50]
0x1800631b4  lea     ecx, [rbx+1]
0x1800631b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631bc  mov     rbx, rax
0x1800631bf  test    rax, rax
0x1800631c2  jnz     loc_180063277
0x1800631c8  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800631cc  xor     r8d, r8d; dwFlags
0x1800631cf  xor     edx, edx; hFile
0x1800631d1  call    cs:__imp_LoadLibraryExA
0x1800631d7  mov     rbx, rax
0x1800631da  test    rax, rax
0x1800631dd  jnz     loc_180063277
0x1800631e3  call    cs:__imp_GetLastError
0x1800631e9  mov     [rbp+var_10], eax
0x1800631ec  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800631f3  test    rax, rax
0x1800631f6  jz      short loc_18006320C
0x1800631f8  lea     rdx, [rbp+var_50]
0x1800631fc  lea     ecx, [rbx+3]
0x1800631ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063204  mov     rbx, rax
0x180063207  test    rax, rax
0x18006320a  jnz     short loc_180063277
0x18006320c  test    cs:dword_18006BA70, 1000h
0x180063216  lea     rax, [rbp+var_50]
0x18006321a  mov     [rbp+Arguments], rax
0x18006321e  mov     dword ptr [rbp+flOldProtect], 0
0x180063225  jz      short loc_180063259
0x180063227  lea     rcx, DloadSrwLock; SRWLock
0x18006322e  call    cs:__imp_AcquireSRWLockExclusive
0x180063234  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18006323b  jnz     short loc_18006324C
0x18006323d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180063243  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180063247  call    DloadProtectSection
0x18006324c  lea     rcx, DloadSrwLock; SRWLock
0x180063253  call    cs:__imp_ReleaseSRWLockExclusive
0x180063259  xor     edx, edx; dwExceptionFlags
0x18006325b  lea     r9, [rbp+Arguments]; lpArguments
0x18006325f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180063264  lea     r8d, [rdx+1]; nNumberOfArguments
0x180063268  call    cs:__imp_RaiseException
0x18006326e  mov     rax, [rbp+var_18]
0x180063272  jmp     loc_1800634AB
0x180063277  xor     eax, eax
0x180063279  lock cmpxchg [r15], rbx
0x18006327e  mov     r15, rax
0x180063281  jnz     short loc_1800632C3
0x180063283  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180063287  jz      short loc_1800632D9
0x180063289  cmp     dword ptr [rsi+18h], 0
0x18006328d  jz      short loc_1800632D9
0x18006328f  call    cs:__imp_GetProcessHeap
0x180063295  mov     edx, 8; dwFlags
0x18006329a  mov     rcx, rax; hHeap
0x18006329d  lea     r8d, [rdx+8]; dwBytes
0x1800632a1  call    cs:__imp_HeapAlloc
0x1800632a7  test    rax, rax
0x1800632aa  jz      short loc_1800632D9
0x1800632ac  mov     [rax+8], rsi
0x1800632b0  mov     rcx, cs:__puiHead
0x1800632b7  mov     [rax], rcx
0x1800632ba  mov     cs:__puiHead, rax
0x1800632c1  jmp     short loc_1800632D9
0x1800632c3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800632c7  jz      short loc_1800632D2
0x1800632c9  mov     rcx, rbx; hLibModule
0x1800632cc  call    cs:__imp_FreeLibrary
0x1800632d2  cmp     rbx, r15
0x1800632d5  cmovnz  rbx, r15
0x1800632d9  mov     rax, cs:__pfnDliNotifyHook2
0x1800632e0  mov     [rbp+var_20], rbx
0x1800632e4  test    rax, rax
0x1800632e7  jz      short loc_180063301
0x1800632e9  lea     rdx, [rbp+var_50]
0x1800632ed  mov     ecx, 2
0x1800632f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632f7  mov     rdi, rax
0x1800632fa  mov     rax, cs:__pfnDliNotifyHook2
0x180063301  test    rdi, rdi
0x180063304  jnz     loc_18006343D
0x18006330a  cmp     [rsi+14h], edi
0x18006330d  jz      short loc_180063342
0x18006330f  cmp     [rsi+1Ch], edi
0x180063312  jz      short loc_180063342
0x180063314  movsxd  rcx, dword ptr [rbx+3Ch]
0x180063318  cmp     dword ptr [rcx+rbx], 4550h
0x18006331f  jnz     short loc_180063342
0x180063321  mov     edx, [rbp+arg_0]
0x180063324  cmp     [rcx+rbx+8], edx
0x180063328  jnz     short loc_180063342
0x18006332a  cmp     rbx, [rcx+rbx+30h]
0x18006332f  jnz     short loc_180063342
0x180063331  mov     rdi, [rbp+flOldProtect]
0x180063335  mov     rdi, [rdi+r12]
0x180063339  test    rdi, rdi
0x18006333c  jnz     loc_18006343D
0x180063342  mov     rdx, [rbp+lpProcName]; lpProcName
0x180063346  mov     rcx, rbx; hModule
0x180063349  call    cs:__imp_GetProcAddress
0x18006334f  mov     rdi, rax
0x180063352  test    rax, rax
0x180063355  jnz     loc_180063436
0x18006335b  call    cs:__imp_GetLastError
0x180063361  mov     [rbp+var_10], eax
0x180063364  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18006336b  test    rax, rax
0x18006336e  jz      short loc_180063388
0x180063370  lea     rdx, [rbp+var_50]
0x180063374  lea     ecx, [rdi+4]
0x180063377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006337c  mov     rdi, rax
0x18006337f  test    rax, rax
0x180063382  jnz     loc_180063436
0x180063388  test    cs:dword_18006BA70, 1000h
0x180063392  lea     rax, [rbp+var_50]
0x180063396  mov     [rbp+Arguments], rax
0x18006339a  mov     dword ptr [rbp+flOldProtect], 0
0x1800633a1  jz      short loc_1800633D5
0x1800633a3  lea     rcx, DloadSrwLock; SRWLock
0x1800633aa  call    cs:__imp_AcquireSRWLockExclusive
0x1800633b0  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800633b7  jnz     short loc_1800633C8
0x1800633b9  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800633bf  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800633c3  call    DloadProtectSection
0x1800633c8  lea     rcx, DloadSrwLock; SRWLock
0x1800633cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800633d5  xor     edx, edx; dwExceptionFlags
0x1800633d7  lea     r9, [rbp+Arguments]; lpArguments
0x1800633db  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800633e0  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800633e4  call    cs:__imp_RaiseException
0x1800633ea  test    cs:dword_18006BA70, 1000h
0x1800633f4  jz      short loc_180063432
0x1800633f6  lea     rcx, DloadSrwLock; SRWLock
0x1800633fd  call    cs:__imp_AcquireSRWLockExclusive
0x180063403  mov     eax, cs:DloadSectionLockCount
0x180063409  inc     eax
0x18006340b  mov     cs:DloadSectionLockCount, eax
0x180063411  cmp     eax, 1
0x180063414  jnz     short loc_180063425
0x180063416  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18006341d  lea     ecx, [rax+3]; flNewProtect
0x180063420  call    DloadProtectSection
0x180063425  lea     rcx, DloadSrwLock; SRWLock
0x18006342c  call    cs:__imp_ReleaseSRWLockExclusive
0x180063432  mov     rdi, [rbp+var_18]
0x180063436  mov     rax, cs:__pfnDliNotifyHook2
0x18006343d  mov     [r13+0], rdi
0x180063441  test    rax, rax
0x180063444  jz      short loc_180063463
0x180063446  lea     rdx, [rbp+var_50]
0x18006344a  mov     [rbp+var_10], 0
0x180063451  mov     ecx, 5
0x180063456  mov     [rbp+var_20], rbx
0x18006345a  mov     [rbp+var_18], rdi
0x18006345e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063463  test    cs:dword_18006BA70, 1000h
0x18006346d  mov     dword ptr [rbp+flOldProtect], 0
0x180063474  jz      short loc_1800634A8
0x180063476  lea     rcx, DloadSrwLock; SRWLock
0x18006347d  call    cs:__imp_AcquireSRWLockExclusive
0x180063483  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18006348a  jnz     short loc_18006349B
0x18006348c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180063492  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180063496  call    DloadProtectSection
0x18006349b  lea     rcx, DloadSrwLock; SRWLock
0x1800634a2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800634a8  mov     rax, rdi
0x1800634ab  add     rsp, 70h
0x1800634af  pop     r15
0x1800634b1  pop     r13
0x1800634b3  pop     r12
0x1800634b5  pop     rdi
0x1800634b6  pop     rsi
0x1800634b7  pop     rbx
0x1800634b8  pop     rbp
0x1800634b9  retn
```
