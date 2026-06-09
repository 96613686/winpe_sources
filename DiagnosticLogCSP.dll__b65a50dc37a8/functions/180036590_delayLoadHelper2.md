# __delayLoadHelper2

- ea: `0x180036590`
- end: `0x180036adf`
- name: `__delayLoadHelper2`
- size: `1359`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002716`
- `0x1800027d7`

## callees

- `0x18000265c`
- `0x1800364a0`
- `0x180036590`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800368b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800368b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036937`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180036937`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003678f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003678f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800367a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003694f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800367a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003694f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800366d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003683e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800369ea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800366d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003683e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800369ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800365d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036693`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800367f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800369a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036a09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036a95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800365d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036693`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800367f8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800369a4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036a09`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180036a95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036607`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800366ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800369cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036ac0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036607`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800366ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800369cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036a3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180036ac0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036883`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036883`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003686b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003686b`

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
0x180036590  push    rbp
0x180036592  push    rbx
0x180036593  push    rsi
0x180036594  push    rdi
0x180036595  push    r12
0x180036597  push    r13
0x180036599  push    r15
0x18003659b  mov     rbp, rsp
0x18003659e  sub     rsp, 70h
0x1800365a2  xor     eax, eax
0x1800365a4  mov     r13, rdx
0x1800365a7  mov     rsi, rcx
0x1800365aa  mov     [rbp+var_4C], eax
0x1800365ad  xor     edx, edx; Val
0x1800365af  lea     rcx, [rbp+var_50]; void *
0x1800365b3  lea     r8d, [rax+44h]; Size
0x1800365b7  call    memset_0
0x1800365bc  test    cs:dword_18003A130, 1000h
0x1800365c6  lea     rbx, DloadSrwLock
0x1800365cd  mov     edi, 1
0x1800365d2  jz      short loc_180036613
0x1800365d4  mov     rcx, rbx; SRWLock
0x1800365d7  call    cs:__imp_AcquireSRWLockExclusive
0x1800365de  nop     dword ptr [rax+rax+00h]
0x1800365e3  mov     eax, cs:DloadSectionLockCount
0x1800365e9  add     eax, edi
0x1800365eb  mov     cs:DloadSectionLockCount, eax
0x1800365f1  cmp     eax, edi
0x1800365f3  jnz     short loc_180036604
0x1800365f5  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800365fc  lea     ecx, [rdi+3]; flNewProtect
0x1800365ff  call    DloadProtectSection
0x180036604  mov     rcx, rbx; SRWLock
0x180036607  call    cs:__imp_ReleaseSRWLockExclusive
0x18003660e  nop     dword ptr [rax+rax+00h]
0x180036613  mov     eax, [rsi+4]
0x180036616  lea     rdx, __ImageBase
0x18003661d  mov     r15d, [rsi+8]
0x180036621  add     rax, rdx
0x180036624  mov     r12d, [rsi+14h]
0x180036628  add     r15, rdx
0x18003662b  mov     ecx, [rsi+1Ch]
0x18003662e  add     r12, rdx
0x180036631  mov     [rbp+lpLibFileName], rax
0x180036635  mov     eax, [rsi]
0x180036637  and     eax, edi
0x180036639  mov     [rbp+arg_0], ecx
0x18003663c  mov     [rbp+var_50], 48h ; 'H'
0x180036643  mov     [rbp+var_48], rsi
0x180036647  mov     [rbp+var_40], r13
0x18003664b  mov     [rbp+var_30], 0
0x180036652  mov     [rbp+lpProcName], 0
0x18003665a  mov     [rbp+var_20], 0
0x180036662  mov     [rbp+var_18], 0
0x18003666a  mov     [rbp+var_10], 0
0x180036671  test    al, al
0x180036673  jnz     short loc_1800366E7
0x180036675  test    cs:dword_18003A130, 1000h
0x18003667f  lea     rax, [rbp+var_50]
0x180036683  mov     [rbp+Arguments], rax
0x180036687  mov     dword ptr [rbp+flOldProtect], 0
0x18003668e  jz      short loc_1800366C6
0x180036690  mov     rcx, rbx; SRWLock
0x180036693  call    cs:__imp_AcquireSRWLockExclusive
0x18003669a  nop     dword ptr [rax+rax+00h]
0x18003669f  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800366a6  jnz     short loc_1800366B7
0x1800366a8  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800366ae  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800366b2  call    DloadProtectSection
0x1800366b7  mov     rcx, rbx; SRWLock
0x1800366ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1800366c1  nop     dword ptr [rax+rax+00h]
0x1800366c6  lea     r9, [rbp+Arguments]; lpArguments
0x1800366ca  mov     r8d, edi; nNumberOfArguments
0x1800366cd  xor     edx, edx; dwExceptionFlags
0x1800366cf  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800366d4  call    cs:__imp_RaiseException
0x1800366db  nop     dword ptr [rax+rax+00h]
0x1800366e0  xor     eax, eax
0x1800366e2  jmp     loc_180036ACF
0x1800366e7  mov     eax, [rsi+0Ch]
0x1800366ea  mov     rcx, r13
0x1800366ed  mov     rbx, [r15]
0x1800366f0  sub     rcx, rax
0x1800366f3  sub     rcx, rdx
0x1800366f6  sar     rcx, 3
0x1800366fa  mov     eax, ecx
0x1800366fc  mov     ecx, [rsi+10h]
0x1800366ff  shl     rax, 3
0x180036703  add     rcx, rax
0x180036706  mov     [rbp+flOldProtect], rax
0x18003670a  xor     eax, eax
0x18003670c  cmp     [rcx+rdx], rax
0x180036710  setnl   al
0x180036713  mov     [rbp+var_30], eax
0x180036716  test    eax, eax
0x180036718  jz      short loc_18003672D
0x18003671a  mov     eax, [rcx+rdx]
0x18003671d  lea     rdx, word_180000002
0x180036724  add     rax, rdx
0x180036727  mov     [rbp+lpProcName], rax
0x18003672b  jmp     short loc_180036734
0x18003672d  movzx   eax, word ptr [rcx+rdx]
0x180036731  mov     dword ptr [rbp+lpProcName], eax
0x180036734  mov     rax, cs:__pfnDliNotifyHook2
0x18003673b  xor     edi, edi
0x18003673d  test    rax, rax
0x180036740  jz      short loc_180036760
0x180036742  lea     rdx, [rbp+var_50]
0x180036746  xor     ecx, ecx
0x180036748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003674d  mov     rdi, rax
0x180036750  test    rax, rax
0x180036753  mov     rax, cs:__pfnDliNotifyHook2
0x18003675a  jnz     loc_180036A59
0x180036760  test    rbx, rbx
0x180036763  jnz     loc_1800368CE
0x180036769  test    rax, rax
0x18003676c  jz      short loc_180036786
0x18003676e  lea     rdx, [rbp+var_50]
0x180036772  lea     ecx, [rbx+1]
0x180036775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003677a  mov     rbx, rax
0x18003677d  test    rax, rax
0x180036780  jnz     loc_180036853
0x180036786  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18003678a  xor     r8d, r8d; dwFlags
0x18003678d  xor     edx, edx; hFile
0x18003678f  call    cs:__imp_LoadLibraryExA
0x180036796  nop     dword ptr [rax+rax+00h]
0x18003679b  mov     rbx, rax
0x18003679e  test    rax, rax
0x1800367a1  jnz     loc_180036853
0x1800367a7  call    cs:__imp_GetLastError
0x1800367ae  nop     dword ptr [rax+rax+00h]
0x1800367b3  mov     [rbp+var_10], eax
0x1800367b6  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800367bd  test    rax, rax
0x1800367c0  jz      short loc_1800367D6
0x1800367c2  lea     rdx, [rbp+var_50]
0x1800367c6  lea     ecx, [rbx+3]
0x1800367c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800367ce  mov     rbx, rax
0x1800367d1  test    rax, rax
0x1800367d4  jnz     short loc_180036853
0x1800367d6  test    cs:dword_18003A130, 1000h
0x1800367e0  lea     rax, [rbp+var_50]
0x1800367e4  mov     [rbp+Arguments], rax
0x1800367e8  mov     dword ptr [rbp+flOldProtect], 0
0x1800367ef  jz      short loc_18003682F
0x1800367f1  lea     rcx, DloadSrwLock; SRWLock
0x1800367f8  call    cs:__imp_AcquireSRWLockExclusive
0x1800367ff  nop     dword ptr [rax+rax+00h]
0x180036804  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18003680b  jnz     short loc_18003681C
0x18003680d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180036813  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180036817  call    DloadProtectSection
0x18003681c  lea     rcx, DloadSrwLock; SRWLock
0x180036823  call    cs:__imp_ReleaseSRWLockExclusive
0x18003682a  nop     dword ptr [rax+rax+00h]
0x18003682f  xor     edx, edx; dwExceptionFlags
0x180036831  lea     r9, [rbp+Arguments]; lpArguments
0x180036835  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18003683a  lea     r8d, [rdx+1]; nNumberOfArguments
0x18003683e  call    cs:__imp_RaiseException
0x180036845  nop     dword ptr [rax+rax+00h]
0x18003684a  mov     rax, [rbp+var_18]
0x18003684e  jmp     loc_180036ACF
0x180036853  xor     eax, eax
0x180036855  lock cmpxchg [r15], rbx
0x18003685a  mov     r15, rax
0x18003685d  jnz     short loc_1800368AB
0x18003685f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180036863  jz      short loc_1800368C7
0x180036865  cmp     dword ptr [rsi+18h], 0
0x180036869  jz      short loc_1800368C7
0x18003686b  call    cs:__imp_GetProcessHeap
0x180036872  nop     dword ptr [rax+rax+00h]
0x180036877  mov     edx, 8; dwFlags
0x18003687c  mov     rcx, rax; hHeap
0x18003687f  lea     r8d, [rdx+8]; dwBytes
0x180036883  call    cs:__imp_HeapAlloc
0x18003688a  nop     dword ptr [rax+rax+00h]
0x18003688f  test    rax, rax
0x180036892  jz      short loc_1800368C7
0x180036894  mov     [rax+8], rsi
0x180036898  mov     rcx, cs:__puiHead
0x18003689f  mov     [rax], rcx
0x1800368a2  mov     cs:__puiHead, rax
0x1800368a9  jmp     short loc_1800368C7
0x1800368ab  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800368af  jz      short loc_1800368C0
0x1800368b1  mov     rcx, rbx; hLibModule
0x1800368b4  call    cs:__imp_FreeLibrary
0x1800368bb  nop     dword ptr [rax+rax+00h]
0x1800368c0  cmp     rbx, r15
0x1800368c3  cmovnz  rbx, r15
0x1800368c7  mov     rax, cs:__pfnDliNotifyHook2
0x1800368ce  mov     [rbp+var_20], rbx
0x1800368d2  test    rax, rax
0x1800368d5  jz      short loc_1800368EF
0x1800368d7  lea     rdx, [rbp+var_50]
0x1800368db  mov     ecx, 2
0x1800368e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800368e5  mov     rdi, rax
0x1800368e8  mov     rax, cs:__pfnDliNotifyHook2
0x1800368ef  test    rdi, rdi
0x1800368f2  jnz     loc_180036A55
0x1800368f8  cmp     [rsi+14h], edi
0x1800368fb  jz      short loc_180036930
0x1800368fd  cmp     [rsi+1Ch], edi
0x180036900  jz      short loc_180036930
0x180036902  movsxd  rcx, dword ptr [rbx+3Ch]
0x180036906  cmp     dword ptr [rcx+rbx], 4550h
0x18003690d  jnz     short loc_180036930
0x18003690f  mov     edx, [rbp+arg_0]
0x180036912  cmp     [rcx+rbx+8], edx
0x180036916  jnz     short loc_180036930
0x180036918  cmp     rbx, [rcx+rbx+30h]
0x18003691d  jnz     short loc_180036930
0x18003691f  mov     rdi, [rbp+flOldProtect]
0x180036923  mov     rdi, [rdi+r12]
0x180036927  test    rdi, rdi
0x18003692a  jnz     loc_180036A55
0x180036930  mov     rdx, [rbp+lpProcName]; lpProcName
0x180036934  mov     rcx, rbx; hModule
0x180036937  call    cs:__imp_GetProcAddress
0x18003693e  nop     dword ptr [rax+rax+00h]
0x180036943  mov     rdi, rax
0x180036946  test    rax, rax
0x180036949  jnz     loc_180036A4E
0x18003694f  call    cs:__imp_GetLastError
0x180036956  nop     dword ptr [rax+rax+00h]
0x18003695b  mov     [rbp+var_10], eax
0x18003695e  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180036965  test    rax, rax
0x180036968  jz      short loc_180036982
0x18003696a  lea     rdx, [rbp+var_50]
0x18003696e  lea     ecx, [rdi+4]
0x180036971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036976  mov     rdi, rax
0x180036979  test    rax, rax
0x18003697c  jnz     loc_180036A4E
0x180036982  test    cs:dword_18003A130, 1000h
0x18003698c  lea     rax, [rbp+var_50]
0x180036990  mov     [rbp+Arguments], rax
0x180036994  mov     dword ptr [rbp+flOldProtect], 0
0x18003699b  jz      short loc_1800369DB
0x18003699d  lea     rcx, DloadSrwLock; SRWLock
0x1800369a4  call    cs:__imp_AcquireSRWLockExclusive
0x1800369ab  nop     dword ptr [rax+rax+00h]
0x1800369b0  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800369b7  jnz     short loc_1800369C8
0x1800369b9  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800369bf  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800369c3  call    DloadProtectSection
0x1800369c8  lea     rcx, DloadSrwLock; SRWLock
0x1800369cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800369d6  nop     dword ptr [rax+rax+00h]
0x1800369db  xor     edx, edx; dwExceptionFlags
0x1800369dd  lea     r9, [rbp+Arguments]; lpArguments
0x1800369e1  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800369e6  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800369ea  call    cs:__imp_RaiseException
0x1800369f1  nop     dword ptr [rax+rax+00h]
0x1800369f6  test    cs:dword_18003A130, 1000h
0x180036a00  jz      short loc_180036A4A
0x180036a02  lea     rcx, DloadSrwLock; SRWLock
0x180036a09  call    cs:__imp_AcquireSRWLockExclusive
0x180036a10  nop     dword ptr [rax+rax+00h]
0x180036a15  mov     eax, cs:DloadSectionLockCount
0x180036a1b  inc     eax
0x180036a1d  mov     cs:DloadSectionLockCount, eax
0x180036a23  cmp     eax, 1
0x180036a26  jnz     short loc_180036A37
0x180036a28  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180036a2f  lea     ecx, [rax+3]; flNewProtect
0x180036a32  call    DloadProtectSection
0x180036a37  lea     rcx, DloadSrwLock; SRWLock
0x180036a3e  call    cs:__imp_ReleaseSRWLockExclusive
0x180036a45  nop     dword ptr [rax+rax+00h]
0x180036a4a  mov     rdi, [rbp+var_18]
0x180036a4e  mov     rax, cs:__pfnDliNotifyHook2
0x180036a55  mov     [r13+0], rdi
0x180036a59  test    rax, rax
0x180036a5c  jz      short loc_180036A7B
0x180036a5e  lea     rdx, [rbp+var_50]
0x180036a62  mov     [rbp+var_10], 0
0x180036a69  mov     ecx, 5
0x180036a6e  mov     [rbp+var_20], rbx
0x180036a72  mov     [rbp+var_18], rdi
0x180036a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036a7b  test    cs:dword_18003A130, 1000h
0x180036a85  mov     dword ptr [rbp+flOldProtect], 0
0x180036a8c  jz      short loc_180036ACC
0x180036a8e  lea     rcx, DloadSrwLock; SRWLock
0x180036a95  call    cs:__imp_AcquireSRWLockExclusive
0x180036a9c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
