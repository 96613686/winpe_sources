# __delayLoadHelper2

- ea: `0x1800686a0`
- end: `0x180068bef`
- name: `__delayLoadHelper2`
- size: `1359`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002a5c`
- `0x180002b05`
- `0x180002c02`
- `0x180002e85`
- `0x180002f22`
- `0x180003050`

## callees

- `0x1800685b4`
- `0x1800686a0`
- `0x18006c8d2`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068a47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068a47`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006889f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18006889f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800689c4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800689c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068993`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180068993`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006897b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006897b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068a5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800688b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068a5f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800687e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006894e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068afa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800687e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006894e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180068afa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068717`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800687ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068933`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068adf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068b4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068bd0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068717`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800687ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068933`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068adf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068b4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068bd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800686e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800687a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068908`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068ab4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068b19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068ba5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800686e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800687a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068908`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068ab4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068b19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180068ba5`

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
0x1800686a0  push    rbp
0x1800686a2  push    rbx
0x1800686a3  push    rsi
0x1800686a4  push    rdi
0x1800686a5  push    r12
0x1800686a7  push    r13
0x1800686a9  push    r15
0x1800686ab  mov     rbp, rsp
0x1800686ae  sub     rsp, 70h
0x1800686b2  xor     eax, eax
0x1800686b4  mov     r13, rdx
0x1800686b7  mov     rsi, rcx
0x1800686ba  mov     [rbp+var_4C], eax
0x1800686bd  xor     edx, edx; Val
0x1800686bf  lea     rcx, [rbp+var_50]; void *
0x1800686c3  lea     r8d, [rax+44h]; Size
0x1800686c7  call    memset_0
0x1800686cc  test    cs:dword_180071A70, 1000h
0x1800686d6  lea     rbx, DloadSrwLock
0x1800686dd  mov     edi, 1
0x1800686e2  jz      short loc_180068723
0x1800686e4  mov     rcx, rbx; SRWLock
0x1800686e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800686ee  nop     dword ptr [rax+rax+00h]
0x1800686f3  mov     eax, cs:DloadSectionLockCount
0x1800686f9  add     eax, edi
0x1800686fb  mov     cs:DloadSectionLockCount, eax
0x180068701  cmp     eax, edi
0x180068703  jnz     short loc_180068714
0x180068705  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18006870c  lea     ecx, [rdi+3]; flNewProtect
0x18006870f  call    DloadProtectSection
0x180068714  mov     rcx, rbx; SRWLock
0x180068717  call    cs:__imp_ReleaseSRWLockExclusive
0x18006871e  nop     dword ptr [rax+rax+00h]
0x180068723  mov     eax, [rsi+4]
0x180068726  lea     rdx, __ImageBase
0x18006872d  mov     r15d, [rsi+8]
0x180068731  add     rax, rdx
0x180068734  mov     r12d, [rsi+14h]
0x180068738  add     r15, rdx
0x18006873b  mov     ecx, [rsi+1Ch]
0x18006873e  add     r12, rdx
0x180068741  mov     [rbp+lpLibFileName], rax
0x180068745  mov     eax, [rsi]
0x180068747  and     eax, edi
0x180068749  mov     [rbp+arg_0], ecx
0x18006874c  mov     [rbp+var_50], 48h ; 'H'
0x180068753  mov     [rbp+var_48], rsi
0x180068757  mov     [rbp+var_40], r13
0x18006875b  mov     [rbp+var_30], 0
0x180068762  mov     [rbp+lpProcName], 0
0x18006876a  mov     [rbp+var_20], 0
0x180068772  mov     [rbp+var_18], 0
0x18006877a  mov     [rbp+var_10], 0
0x180068781  test    al, al
0x180068783  jnz     short loc_1800687F7
0x180068785  test    cs:dword_180071A70, 1000h
0x18006878f  lea     rax, [rbp+var_50]
0x180068793  mov     [rbp+Arguments], rax
0x180068797  mov     dword ptr [rbp+flOldProtect], 0
0x18006879e  jz      short loc_1800687D6
0x1800687a0  mov     rcx, rbx; SRWLock
0x1800687a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800687aa  nop     dword ptr [rax+rax+00h]
0x1800687af  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800687b6  jnz     short loc_1800687C7
0x1800687b8  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800687be  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800687c2  call    DloadProtectSection
0x1800687c7  mov     rcx, rbx; SRWLock
0x1800687ca  call    cs:__imp_ReleaseSRWLockExclusive
0x1800687d1  nop     dword ptr [rax+rax+00h]
0x1800687d6  lea     r9, [rbp+Arguments]; lpArguments
0x1800687da  mov     r8d, edi; nNumberOfArguments
0x1800687dd  xor     edx, edx; dwExceptionFlags
0x1800687df  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800687e4  call    cs:__imp_RaiseException
0x1800687eb  nop     dword ptr [rax+rax+00h]
0x1800687f0  xor     eax, eax
0x1800687f2  jmp     loc_180068BDF
0x1800687f7  mov     eax, [rsi+0Ch]
0x1800687fa  mov     rcx, r13
0x1800687fd  mov     rbx, [r15]
0x180068800  sub     rcx, rax
0x180068803  sub     rcx, rdx
0x180068806  sar     rcx, 3
0x18006880a  mov     eax, ecx
0x18006880c  mov     ecx, [rsi+10h]
0x18006880f  shl     rax, 3
0x180068813  add     rcx, rax
0x180068816  mov     [rbp+flOldProtect], rax
0x18006881a  xor     eax, eax
0x18006881c  cmp     [rcx+rdx], rax
0x180068820  setnl   al
0x180068823  mov     [rbp+var_30], eax
0x180068826  test    eax, eax
0x180068828  jz      short loc_18006883D
0x18006882a  mov     eax, [rcx+rdx]
0x18006882d  lea     rdx, word_180000002
0x180068834  add     rax, rdx
0x180068837  mov     [rbp+lpProcName], rax
0x18006883b  jmp     short loc_180068844
0x18006883d  movzx   eax, word ptr [rcx+rdx]
0x180068841  mov     dword ptr [rbp+lpProcName], eax
0x180068844  mov     rax, cs:__pfnDliNotifyHook2
0x18006884b  xor     edi, edi
0x18006884d  test    rax, rax
0x180068850  jz      short loc_180068870
0x180068852  lea     rdx, [rbp+var_50]
0x180068856  xor     ecx, ecx
0x180068858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006885d  mov     rdi, rax
0x180068860  test    rax, rax
0x180068863  mov     rax, cs:__pfnDliNotifyHook2
0x18006886a  jnz     loc_180068B69
0x180068870  test    rbx, rbx
0x180068873  jnz     loc_1800689DE
0x180068879  test    rax, rax
0x18006887c  jz      short loc_180068896
0x18006887e  lea     rdx, [rbp+var_50]
0x180068882  lea     ecx, [rbx+1]
0x180068885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006888a  mov     rbx, rax
0x18006888d  test    rax, rax
0x180068890  jnz     loc_180068963
0x180068896  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18006889a  xor     r8d, r8d; dwFlags
0x18006889d  xor     edx, edx; hFile
0x18006889f  call    cs:__imp_LoadLibraryExA
0x1800688a6  nop     dword ptr [rax+rax+00h]
0x1800688ab  mov     rbx, rax
0x1800688ae  test    rax, rax
0x1800688b1  jnz     loc_180068963
0x1800688b7  call    cs:__imp_GetLastError
0x1800688be  nop     dword ptr [rax+rax+00h]
0x1800688c3  mov     [rbp+var_10], eax
0x1800688c6  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800688cd  test    rax, rax
0x1800688d0  jz      short loc_1800688E6
0x1800688d2  lea     rdx, [rbp+var_50]
0x1800688d6  lea     ecx, [rbx+3]
0x1800688d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688de  mov     rbx, rax
0x1800688e1  test    rax, rax
0x1800688e4  jnz     short loc_180068963
0x1800688e6  test    cs:dword_180071A70, 1000h
0x1800688f0  lea     rax, [rbp+var_50]
0x1800688f4  mov     [rbp+Arguments], rax
0x1800688f8  mov     dword ptr [rbp+flOldProtect], 0
0x1800688ff  jz      short loc_18006893F
0x180068901  lea     rcx, DloadSrwLock; SRWLock
0x180068908  call    cs:__imp_AcquireSRWLockExclusive
0x18006890f  nop     dword ptr [rax+rax+00h]
0x180068914  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18006891b  jnz     short loc_18006892C
0x18006891d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180068923  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180068927  call    DloadProtectSection
0x18006892c  lea     rcx, DloadSrwLock; SRWLock
0x180068933  call    cs:__imp_ReleaseSRWLockExclusive
0x18006893a  nop     dword ptr [rax+rax+00h]
0x18006893f  xor     edx, edx; dwExceptionFlags
0x180068941  lea     r9, [rbp+Arguments]; lpArguments
0x180068945  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18006894a  lea     r8d, [rdx+1]; nNumberOfArguments
0x18006894e  call    cs:__imp_RaiseException
0x180068955  nop     dword ptr [rax+rax+00h]
0x18006895a  mov     rax, [rbp+var_18]
0x18006895e  jmp     loc_180068BDF
0x180068963  xor     eax, eax
0x180068965  lock cmpxchg [r15], rbx
0x18006896a  mov     r15, rax
0x18006896d  jnz     short loc_1800689BB
0x18006896f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180068973  jz      short loc_1800689D7
0x180068975  cmp     dword ptr [rsi+18h], 0
0x180068979  jz      short loc_1800689D7
0x18006897b  call    cs:__imp_GetProcessHeap
0x180068982  nop     dword ptr [rax+rax+00h]
0x180068987  mov     edx, 8; dwFlags
0x18006898c  mov     rcx, rax; hHeap
0x18006898f  lea     r8d, [rdx+8]; dwBytes
0x180068993  call    cs:__imp_HeapAlloc
0x18006899a  nop     dword ptr [rax+rax+00h]
0x18006899f  test    rax, rax
0x1800689a2  jz      short loc_1800689D7
0x1800689a4  mov     [rax+8], rsi
0x1800689a8  mov     rcx, cs:__puiHead
0x1800689af  mov     [rax], rcx
0x1800689b2  mov     cs:__puiHead, rax
0x1800689b9  jmp     short loc_1800689D7
0x1800689bb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800689bf  jz      short loc_1800689D0
0x1800689c1  mov     rcx, rbx; hLibModule
0x1800689c4  call    cs:__imp_FreeLibrary
0x1800689cb  nop     dword ptr [rax+rax+00h]
0x1800689d0  cmp     rbx, r15
0x1800689d3  cmovnz  rbx, r15
0x1800689d7  mov     rax, cs:__pfnDliNotifyHook2
0x1800689de  mov     [rbp+var_20], rbx
0x1800689e2  test    rax, rax
0x1800689e5  jz      short loc_1800689FF
0x1800689e7  lea     rdx, [rbp+var_50]
0x1800689eb  mov     ecx, 2
0x1800689f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689f5  mov     rdi, rax
0x1800689f8  mov     rax, cs:__pfnDliNotifyHook2
0x1800689ff  test    rdi, rdi
0x180068a02  jnz     loc_180068B65
0x180068a08  cmp     [rsi+14h], edi
0x180068a0b  jz      short loc_180068A40
0x180068a0d  cmp     [rsi+1Ch], edi
0x180068a10  jz      short loc_180068A40
0x180068a12  movsxd  rcx, dword ptr [rbx+3Ch]
0x180068a16  cmp     dword ptr [rcx+rbx], 4550h
0x180068a1d  jnz     short loc_180068A40
0x180068a1f  mov     edx, [rbp+arg_0]
0x180068a22  cmp     [rcx+rbx+8], edx
0x180068a26  jnz     short loc_180068A40
0x180068a28  cmp     rbx, [rcx+rbx+30h]
0x180068a2d  jnz     short loc_180068A40
0x180068a2f  mov     rdi, [rbp+flOldProtect]
0x180068a33  mov     rdi, [rdi+r12]
0x180068a37  test    rdi, rdi
0x180068a3a  jnz     loc_180068B65
0x180068a40  mov     rdx, [rbp+lpProcName]; lpProcName
0x180068a44  mov     rcx, rbx; hModule
0x180068a47  call    cs:__imp_GetProcAddress
0x180068a4e  nop     dword ptr [rax+rax+00h]
0x180068a53  mov     rdi, rax
0x180068a56  test    rax, rax
0x180068a59  jnz     loc_180068B5E
0x180068a5f  call    cs:__imp_GetLastError
0x180068a66  nop     dword ptr [rax+rax+00h]
0x180068a6b  mov     [rbp+var_10], eax
0x180068a6e  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180068a75  test    rax, rax
0x180068a78  jz      short loc_180068A92
0x180068a7a  lea     rdx, [rbp+var_50]
0x180068a7e  lea     ecx, [rdi+4]
0x180068a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068a86  mov     rdi, rax
0x180068a89  test    rax, rax
0x180068a8c  jnz     loc_180068B5E
0x180068a92  test    cs:dword_180071A70, 1000h
0x180068a9c  lea     rax, [rbp+var_50]
0x180068aa0  mov     [rbp+Arguments], rax
0x180068aa4  mov     dword ptr [rbp+flOldProtect], 0
0x180068aab  jz      short loc_180068AEB
0x180068aad  lea     rcx, DloadSrwLock; SRWLock
0x180068ab4  call    cs:__imp_AcquireSRWLockExclusive
0x180068abb  nop     dword ptr [rax+rax+00h]
0x180068ac0  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180068ac7  jnz     short loc_180068AD8
0x180068ac9  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180068acf  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180068ad3  call    DloadProtectSection
0x180068ad8  lea     rcx, DloadSrwLock; SRWLock
0x180068adf  call    cs:__imp_ReleaseSRWLockExclusive
0x180068ae6  nop     dword ptr [rax+rax+00h]
0x180068aeb  xor     edx, edx; dwExceptionFlags
0x180068aed  lea     r9, [rbp+Arguments]; lpArguments
0x180068af1  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180068af6  lea     r8d, [rdx+1]; nNumberOfArguments
0x180068afa  call    cs:__imp_RaiseException
0x180068b01  nop     dword ptr [rax+rax+00h]
0x180068b06  test    cs:dword_180071A70, 1000h
0x180068b10  jz      short loc_180068B5A
0x180068b12  lea     rcx, DloadSrwLock; SRWLock
0x180068b19  call    cs:__imp_AcquireSRWLockExclusive
0x180068b20  nop     dword ptr [rax+rax+00h]
0x180068b25  mov     eax, cs:DloadSectionLockCount
0x180068b2b  inc     eax
0x180068b2d  mov     cs:DloadSectionLockCount, eax
0x180068b33  cmp     eax, 1
0x180068b36  jnz     short loc_180068B47
0x180068b38  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180068b3f  lea     ecx, [rax+3]; flNewProtect
0x180068b42  call    DloadProtectSection
0x180068b47  lea     rcx, DloadSrwLock; SRWLock
0x180068b4e  call    cs:__imp_ReleaseSRWLockExclusive
0x180068b55  nop     dword ptr [rax+rax+00h]
0x180068b5a  mov     rdi, [rbp+var_18]
0x180068b5e  mov     rax, cs:__pfnDliNotifyHook2
0x180068b65  mov     [r13+0], rdi
0x180068b69  test    rax, rax
0x180068b6c  jz      short loc_180068B8B
0x180068b6e  lea     rdx, [rbp+var_50]
0x180068b72  mov     [rbp+var_10], 0
0x180068b79  mov     ecx, 5
0x180068b7e  mov     [rbp+var_20], rbx
0x180068b82  mov     [rbp+var_18], rdi
0x180068b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068b8b  test    cs:dword_180071A70, 1000h
0x180068b95  mov     dword ptr [rbp+flOldProtect], 0
0x180068b9c  jz      short loc_180068BDC
0x180068b9e  lea     rcx, DloadSrwLock; SRWLock
0x180068ba5  call    cs:__imp_AcquireSRWLockExclusive
0x180068bac  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
