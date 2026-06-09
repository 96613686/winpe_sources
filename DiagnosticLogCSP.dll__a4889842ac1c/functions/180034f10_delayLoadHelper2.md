# __delayLoadHelper2

- ea: `0x180034f10`
- end: `0x1800353da`
- name: `__delayLoadHelper2`
- size: `1226`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800026e6`
- `0x1800027a7`

## callees

- `0x18000262c`
- `0x180034e20`
- `0x180034f10`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800351ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800351ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035269`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180035269`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800350f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800350f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003527b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003527b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003503c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035188`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035304`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003503c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035188`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180035304`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034f57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035007`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003514e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800352ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003531d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003539d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180034f57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035007`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003514e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800352ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003531d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003539d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180034f81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035028`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035173`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800352ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003534c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800353c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180034f81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035028`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035173`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800352ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003534c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800353c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800351c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800351c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800351af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800351af`

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
0x180034f10  push    rbp
0x180034f12  push    rbx
0x180034f13  push    rsi
0x180034f14  push    rdi
0x180034f15  push    r12
0x180034f17  push    r13
0x180034f19  push    r15
0x180034f1b  mov     rbp, rsp
0x180034f1e  sub     rsp, 70h
0x180034f22  xor     eax, eax
0x180034f24  mov     r13, rdx
0x180034f27  mov     rsi, rcx
0x180034f2a  mov     [rbp+var_4C], eax
0x180034f2d  xor     edx, edx; Val
0x180034f2f  lea     rcx, [rbp+var_50]; void *
0x180034f33  lea     r8d, [rax+44h]; Size
0x180034f37  call    memset_0
0x180034f3c  test    cs:dword_180038130, 1000h
0x180034f46  lea     rbx, DloadSrwLock
0x180034f4d  mov     edi, 1
0x180034f52  jz      short loc_180034F87
0x180034f54  mov     rcx, rbx; SRWLock
0x180034f57  call    cs:__imp_AcquireSRWLockExclusive
0x180034f5d  mov     eax, cs:DloadSectionLockCount
0x180034f63  add     eax, edi
0x180034f65  mov     cs:DloadSectionLockCount, eax
0x180034f6b  cmp     eax, edi
0x180034f6d  jnz     short loc_180034F7E
0x180034f6f  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180034f76  lea     ecx, [rdi+3]; flNewProtect
0x180034f79  call    DloadProtectSection
0x180034f7e  mov     rcx, rbx; SRWLock
0x180034f81  call    cs:__imp_ReleaseSRWLockExclusive
0x180034f87  mov     eax, [rsi+4]
0x180034f8a  lea     rdx, __ImageBase
0x180034f91  mov     r15d, [rsi+8]
0x180034f95  add     rax, rdx
0x180034f98  mov     r12d, [rsi+14h]
0x180034f9c  add     r15, rdx
0x180034f9f  mov     ecx, [rsi+1Ch]
0x180034fa2  add     r12, rdx
0x180034fa5  mov     [rbp+lpLibFileName], rax
0x180034fa9  mov     eax, [rsi]
0x180034fab  and     eax, edi
0x180034fad  mov     [rbp+arg_0], ecx
0x180034fb0  mov     [rbp+var_50], 48h ; 'H'
0x180034fb7  mov     [rbp+var_48], rsi
0x180034fbb  mov     [rbp+var_40], r13
0x180034fbf  mov     [rbp+var_30], 0
0x180034fc6  mov     [rbp+lpProcName], 0
0x180034fce  mov     [rbp+var_20], 0
0x180034fd6  mov     [rbp+var_18], 0
0x180034fde  mov     [rbp+var_10], 0
0x180034fe5  test    al, al
0x180034fe7  jnz     short loc_180035049
0x180034fe9  test    cs:dword_180038130, 1000h
0x180034ff3  lea     rax, [rbp+var_50]
0x180034ff7  mov     [rbp+Arguments], rax
0x180034ffb  mov     dword ptr [rbp+flOldProtect], 0
0x180035002  jz      short loc_18003502E
0x180035004  mov     rcx, rbx; SRWLock
0x180035007  call    cs:__imp_AcquireSRWLockExclusive
0x18003500d  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180035014  jnz     short loc_180035025
0x180035016  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18003501c  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180035020  call    DloadProtectSection
0x180035025  mov     rcx, rbx; SRWLock
0x180035028  call    cs:__imp_ReleaseSRWLockExclusive
0x18003502e  lea     r9, [rbp+Arguments]; lpArguments
0x180035032  mov     r8d, edi; nNumberOfArguments
0x180035035  xor     edx, edx; dwExceptionFlags
0x180035037  mov     ecx, 0C06D0057h; dwExceptionCode
0x18003503c  call    cs:__imp_RaiseException
0x180035042  xor     eax, eax
0x180035044  jmp     loc_1800353CB
0x180035049  mov     eax, [rsi+0Ch]
0x18003504c  mov     rcx, r13
0x18003504f  mov     rbx, [r15]
0x180035052  sub     rcx, rax
0x180035055  sub     rcx, rdx
0x180035058  sar     rcx, 3
0x18003505c  mov     eax, ecx
0x18003505e  mov     ecx, [rsi+10h]
0x180035061  shl     rax, 3
0x180035065  add     rcx, rax
0x180035068  mov     [rbp+flOldProtect], rax
0x18003506c  xor     eax, eax
0x18003506e  cmp     [rcx+rdx], rax
0x180035072  setnl   al
0x180035075  mov     [rbp+var_30], eax
0x180035078  test    eax, eax
0x18003507a  jz      short loc_18003508F
0x18003507c  mov     eax, [rcx+rdx]
0x18003507f  lea     rdx, word_180000002
0x180035086  add     rax, rdx
0x180035089  mov     [rbp+lpProcName], rax
0x18003508d  jmp     short loc_180035096
0x18003508f  movzx   eax, word ptr [rcx+rdx]
0x180035093  mov     dword ptr [rbp+lpProcName], eax
0x180035096  mov     rax, cs:__pfnDliNotifyHook2
0x18003509d  xor     edi, edi
0x18003509f  test    rax, rax
0x1800350a2  jz      short loc_1800350C2
0x1800350a4  lea     rdx, [rbp+var_50]
0x1800350a8  xor     ecx, ecx
0x1800350aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350af  mov     rdi, rax
0x1800350b2  test    rax, rax
0x1800350b5  mov     rax, cs:__pfnDliNotifyHook2
0x1800350bc  jnz     loc_180035361
0x1800350c2  test    rbx, rbx
0x1800350c5  jnz     loc_180035200
0x1800350cb  test    rax, rax
0x1800350ce  jz      short loc_1800350E8
0x1800350d0  lea     rdx, [rbp+var_50]
0x1800350d4  lea     ecx, [rbx+1]
0x1800350d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350dc  mov     rbx, rax
0x1800350df  test    rax, rax
0x1800350e2  jnz     loc_180035197
0x1800350e8  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800350ec  xor     r8d, r8d; dwFlags
0x1800350ef  xor     edx, edx; hFile
0x1800350f1  call    cs:__imp_LoadLibraryExA
0x1800350f7  mov     rbx, rax
0x1800350fa  test    rax, rax
0x1800350fd  jnz     loc_180035197
0x180035103  call    cs:__imp_GetLastError
0x180035109  mov     [rbp+var_10], eax
0x18003510c  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180035113  test    rax, rax
0x180035116  jz      short loc_18003512C
0x180035118  lea     rdx, [rbp+var_50]
0x18003511c  lea     ecx, [rbx+3]
0x18003511f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035124  mov     rbx, rax
0x180035127  test    rax, rax
0x18003512a  jnz     short loc_180035197
0x18003512c  test    cs:dword_180038130, 1000h
0x180035136  lea     rax, [rbp+var_50]
0x18003513a  mov     [rbp+Arguments], rax
0x18003513e  mov     dword ptr [rbp+flOldProtect], 0
0x180035145  jz      short loc_180035179
0x180035147  lea     rcx, DloadSrwLock; SRWLock
0x18003514e  call    cs:__imp_AcquireSRWLockExclusive
0x180035154  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18003515b  jnz     short loc_18003516C
0x18003515d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180035163  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180035167  call    DloadProtectSection
0x18003516c  lea     rcx, DloadSrwLock; SRWLock
0x180035173  call    cs:__imp_ReleaseSRWLockExclusive
0x180035179  xor     edx, edx; dwExceptionFlags
0x18003517b  lea     r9, [rbp+Arguments]; lpArguments
0x18003517f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180035184  lea     r8d, [rdx+1]; nNumberOfArguments
0x180035188  call    cs:__imp_RaiseException
0x18003518e  mov     rax, [rbp+var_18]
0x180035192  jmp     loc_1800353CB
0x180035197  xor     eax, eax
0x180035199  lock cmpxchg [r15], rbx
0x18003519e  mov     r15, rax
0x1800351a1  jnz     short loc_1800351E3
0x1800351a3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800351a7  jz      short loc_1800351F9
0x1800351a9  cmp     dword ptr [rsi+18h], 0
0x1800351ad  jz      short loc_1800351F9
0x1800351af  call    cs:__imp_GetProcessHeap
0x1800351b5  mov     edx, 8; dwFlags
0x1800351ba  mov     rcx, rax; hHeap
0x1800351bd  lea     r8d, [rdx+8]; dwBytes
0x1800351c1  call    cs:__imp_HeapAlloc
0x1800351c7  test    rax, rax
0x1800351ca  jz      short loc_1800351F9
0x1800351cc  mov     [rax+8], rsi
0x1800351d0  mov     rcx, cs:__puiHead
0x1800351d7  mov     [rax], rcx
0x1800351da  mov     cs:__puiHead, rax
0x1800351e1  jmp     short loc_1800351F9
0x1800351e3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800351e7  jz      short loc_1800351F2
0x1800351e9  mov     rcx, rbx; hLibModule
0x1800351ec  call    cs:__imp_FreeLibrary
0x1800351f2  cmp     rbx, r15
0x1800351f5  cmovnz  rbx, r15
0x1800351f9  mov     rax, cs:__pfnDliNotifyHook2
0x180035200  mov     [rbp+var_20], rbx
0x180035204  test    rax, rax
0x180035207  jz      short loc_180035221
0x180035209  lea     rdx, [rbp+var_50]
0x18003520d  mov     ecx, 2
0x180035212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035217  mov     rdi, rax
0x18003521a  mov     rax, cs:__pfnDliNotifyHook2
0x180035221  test    rdi, rdi
0x180035224  jnz     loc_18003535D
0x18003522a  cmp     [rsi+14h], edi
0x18003522d  jz      short loc_180035262
0x18003522f  cmp     [rsi+1Ch], edi
0x180035232  jz      short loc_180035262
0x180035234  movsxd  rcx, dword ptr [rbx+3Ch]
0x180035238  cmp     dword ptr [rcx+rbx], 4550h
0x18003523f  jnz     short loc_180035262
0x180035241  mov     edx, [rbp+arg_0]
0x180035244  cmp     [rcx+rbx+8], edx
0x180035248  jnz     short loc_180035262
0x18003524a  cmp     rbx, [rcx+rbx+30h]
0x18003524f  jnz     short loc_180035262
0x180035251  mov     rdi, [rbp+flOldProtect]
0x180035255  mov     rdi, [rdi+r12]
0x180035259  test    rdi, rdi
0x18003525c  jnz     loc_18003535D
0x180035262  mov     rdx, [rbp+lpProcName]; lpProcName
0x180035266  mov     rcx, rbx; hModule
0x180035269  call    cs:__imp_GetProcAddress
0x18003526f  mov     rdi, rax
0x180035272  test    rax, rax
0x180035275  jnz     loc_180035356
0x18003527b  call    cs:__imp_GetLastError
0x180035281  mov     [rbp+var_10], eax
0x180035284  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18003528b  test    rax, rax
0x18003528e  jz      short loc_1800352A8
0x180035290  lea     rdx, [rbp+var_50]
0x180035294  lea     ecx, [rdi+4]
0x180035297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003529c  mov     rdi, rax
0x18003529f  test    rax, rax
0x1800352a2  jnz     loc_180035356
0x1800352a8  test    cs:dword_180038130, 1000h
0x1800352b2  lea     rax, [rbp+var_50]
0x1800352b6  mov     [rbp+Arguments], rax
0x1800352ba  mov     dword ptr [rbp+flOldProtect], 0
0x1800352c1  jz      short loc_1800352F5
0x1800352c3  lea     rcx, DloadSrwLock; SRWLock
0x1800352ca  call    cs:__imp_AcquireSRWLockExclusive
0x1800352d0  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800352d7  jnz     short loc_1800352E8
0x1800352d9  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800352df  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800352e3  call    DloadProtectSection
0x1800352e8  lea     rcx, DloadSrwLock; SRWLock
0x1800352ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800352f5  xor     edx, edx; dwExceptionFlags
0x1800352f7  lea     r9, [rbp+Arguments]; lpArguments
0x1800352fb  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180035300  lea     r8d, [rdx+1]; nNumberOfArguments
0x180035304  call    cs:__imp_RaiseException
0x18003530a  test    cs:dword_180038130, 1000h
0x180035314  jz      short loc_180035352
0x180035316  lea     rcx, DloadSrwLock; SRWLock
0x18003531d  call    cs:__imp_AcquireSRWLockExclusive
0x180035323  mov     eax, cs:DloadSectionLockCount
0x180035329  inc     eax
0x18003532b  mov     cs:DloadSectionLockCount, eax
0x180035331  cmp     eax, 1
0x180035334  jnz     short loc_180035345
0x180035336  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18003533d  lea     ecx, [rax+3]; flNewProtect
0x180035340  call    DloadProtectSection
0x180035345  lea     rcx, DloadSrwLock; SRWLock
0x18003534c  call    cs:__imp_ReleaseSRWLockExclusive
0x180035352  mov     rdi, [rbp+var_18]
0x180035356  mov     rax, cs:__pfnDliNotifyHook2
0x18003535d  mov     [r13+0], rdi
0x180035361  test    rax, rax
0x180035364  jz      short loc_180035383
0x180035366  lea     rdx, [rbp+var_50]
0x18003536a  mov     [rbp+var_10], 0
0x180035371  mov     ecx, 5
0x180035376  mov     [rbp+var_20], rbx
0x18003537a  mov     [rbp+var_18], rdi
0x18003537e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035383  test    cs:dword_180038130, 1000h
0x18003538d  mov     dword ptr [rbp+flOldProtect], 0
0x180035394  jz      short loc_1800353C8
0x180035396  lea     rcx, DloadSrwLock; SRWLock
0x18003539d  call    cs:__imp_AcquireSRWLockExclusive
0x1800353a3  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800353aa  jnz     short loc_1800353BB
0x1800353ac  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800353b2  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800353b6  call    DloadProtectSection
0x1800353bb  lea     rcx, DloadSrwLock; SRWLock
0x1800353c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800353c8  mov     rax, rdi
0x1800353cb  add     rsp, 70h
0x1800353cf  pop     r15
0x1800353d1  pop     r13
0x1800353d3  pop     r12
0x1800353d5  pop     rdi
0x1800353d6  pop     rsi
0x1800353d7  pop     rbx
0x1800353d8  pop     rbp
0x1800353d9  retn
```
