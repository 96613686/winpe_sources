# __delayLoadHelper2

- ea: `0x180009080`
- end: `0x1800095cf`
- name: `__delayLoadHelper2`
- size: `1359`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001bb0`

## callees

- `0x180008f90`
- `0x180009080`
- `0x18000967e`
- `0x18000a010`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x18000927f`
- `KERNEL32!LoadLibraryExA` at `0x18000927f`
- `KERNEL32!RaiseException` at `0x1800091c4`
- `KERNEL32!RaiseException` at `0x18000932e`
- `KERNEL32!RaiseException` at `0x1800094da`
- `KERNEL32!RaiseException` at `0x1800091c4`
- `KERNEL32!RaiseException` at `0x18000932e`
- `KERNEL32!RaiseException` at `0x1800094da`
- `KERNEL32!FreeLibrary` at `0x1800093a4`
- `KERNEL32!FreeLibrary` at `0x1800093a4`
- `KERNEL32!GetProcAddress` at `0x180009427`
- `KERNEL32!GetProcAddress` at `0x180009427`
- `KERNEL32!HeapAlloc` at `0x180009373`
- `KERNEL32!HeapAlloc` at `0x180009373`
- `KERNEL32!GetProcessHeap` at `0x18000935b`
- `KERNEL32!GetProcessHeap` at `0x18000935b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800090c7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009183`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800092e8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009494`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800094f9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009585`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800090c7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009183`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800092e8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009494`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800094f9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180009585`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800090f7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800091aa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009313`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800094bf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000952e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800095b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800090f7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800091aa`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180009313`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800094bf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000952e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800095b0`
- `KERNEL32!GetLastError` at `0x180009297`
- `KERNEL32!GetLastError` at `0x18000943f`
- `KERNEL32!GetLastError` at `0x180009297`
- `KERNEL32!GetLastError` at `0x18000943f`

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
  v4 = (volatile signed __int64 *)((char *)_ImageBase + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v6 = (char *)_ImageBase + a1->rvaBoundIAT;
  v17.szDll = (char *)_ImageBase + a1->rvaDLLName;
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
  v10 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)_ImageBase) >> 3) + a1->rvaINT;
  flOldProtect = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)_ImageBase) >> 3);
  v17.dlp.fImportByName = *(_QWORD *)((char *)_ImageBase + v10) >= 0LL;
  if ( v17.dlp.fImportByName )
    v17.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)_ImageBase + v10);
  else
    v17.dlp.dwOrdinal = *(unsigned __int16 *)((char *)_ImageBase + v10);
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
0x180009080  push    rbp
0x180009082  push    rbx
0x180009083  push    rsi
0x180009084  push    rdi
0x180009085  push    r12
0x180009087  push    r13
0x180009089  push    r15
0x18000908b  mov     rbp, rsp
0x18000908e  sub     rsp, 70h
0x180009092  xor     eax, eax
0x180009094  mov     r13, rdx
0x180009097  mov     rsi, rcx
0x18000909a  mov     [rbp+var_4C], eax
0x18000909d  xor     edx, edx; Val
0x18000909f  lea     rcx, [rbp+var_50]; void *
0x1800090a3  lea     r8d, [rax+44h]; Size
0x1800090a7  call    memset_0
0x1800090ac  test    cs:dword_18000B0A0, 1000h
0x1800090b6  lea     rbx, DloadSrwLock
0x1800090bd  mov     edi, 1
0x1800090c2  jz      short loc_180009103
0x1800090c4  mov     rcx, rbx; SRWLock
0x1800090c7  call    cs:__imp_AcquireSRWLockExclusive
0x1800090ce  nop     dword ptr [rax+rax+00h]
0x1800090d3  mov     eax, cs:DloadSectionLockCount
0x1800090d9  add     eax, edi
0x1800090db  mov     cs:DloadSectionLockCount, eax
0x1800090e1  cmp     eax, edi
0x1800090e3  jnz     short loc_1800090F4
0x1800090e5  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x1800090ec  lea     ecx, [rdi+3]; flNewProtect
0x1800090ef  call    DloadProtectSection
0x1800090f4  mov     rcx, rbx; SRWLock
0x1800090f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800090fe  nop     dword ptr [rax+rax+00h]
0x180009103  mov     eax, [rsi+4]
0x180009106  lea     rdx, __ImageBase
0x18000910d  mov     r15d, [rsi+8]
0x180009111  add     rax, rdx
0x180009114  mov     r12d, [rsi+14h]
0x180009118  add     r15, rdx
0x18000911b  mov     ecx, [rsi+1Ch]
0x18000911e  add     r12, rdx
0x180009121  mov     [rbp+lpLibFileName], rax
0x180009125  mov     eax, [rsi]
0x180009127  and     eax, edi
0x180009129  mov     [rbp+arg_0], ecx
0x18000912c  mov     [rbp+var_50], 48h ; 'H'
0x180009133  mov     [rbp+var_48], rsi
0x180009137  mov     [rbp+var_40], r13
0x18000913b  mov     [rbp+var_30], 0
0x180009142  mov     [rbp+lpProcName], 0
0x18000914a  mov     [rbp+var_20], 0
0x180009152  mov     [rbp+var_18], 0
0x18000915a  mov     [rbp+var_10], 0
0x180009161  test    al, al
0x180009163  jnz     short loc_1800091D7
0x180009165  test    cs:dword_18000B0A0, 1000h
0x18000916f  lea     rax, [rbp+var_50]
0x180009173  mov     [rbp+Arguments], rax
0x180009177  mov     dword ptr [rbp+flOldProtect], 0
0x18000917e  jz      short loc_1800091B6
0x180009180  mov     rcx, rbx; SRWLock
0x180009183  call    cs:__imp_AcquireSRWLockExclusive
0x18000918a  nop     dword ptr [rax+rax+00h]
0x18000918f  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180009196  jnz     short loc_1800091A7
0x180009198  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x18000919e  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800091a2  call    DloadProtectSection
0x1800091a7  mov     rcx, rbx; SRWLock
0x1800091aa  call    cs:__imp_ReleaseSRWLockExclusive
0x1800091b1  nop     dword ptr [rax+rax+00h]
0x1800091b6  lea     r9, [rbp+Arguments]; lpArguments
0x1800091ba  mov     r8d, edi; nNumberOfArguments
0x1800091bd  xor     edx, edx; dwExceptionFlags
0x1800091bf  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800091c4  call    cs:__imp_RaiseException
0x1800091cb  nop     dword ptr [rax+rax+00h]
0x1800091d0  xor     eax, eax
0x1800091d2  jmp     loc_1800095BF
0x1800091d7  mov     eax, [rsi+0Ch]
0x1800091da  mov     rcx, r13
0x1800091dd  mov     rbx, [r15]
0x1800091e0  sub     rcx, rax
0x1800091e3  sub     rcx, rdx
0x1800091e6  sar     rcx, 3
0x1800091ea  mov     eax, ecx
0x1800091ec  mov     ecx, [rsi+10h]
0x1800091ef  shl     rax, 3
0x1800091f3  add     rcx, rax
0x1800091f6  mov     [rbp+flOldProtect], rax
0x1800091fa  xor     eax, eax
0x1800091fc  cmp     [rcx+rdx], rax
0x180009200  setnl   al
0x180009203  mov     [rbp+var_30], eax
0x180009206  test    eax, eax
0x180009208  jz      short loc_18000921D
0x18000920a  mov     eax, [rcx+rdx]
0x18000920d  lea     rdx, word_180000002
0x180009214  add     rax, rdx
0x180009217  mov     [rbp+lpProcName], rax
0x18000921b  jmp     short loc_180009224
0x18000921d  movzx   eax, word ptr [rcx+rdx]
0x180009221  mov     dword ptr [rbp+lpProcName], eax
0x180009224  mov     rax, cs:__pfnDliNotifyHook2
0x18000922b  xor     edi, edi
0x18000922d  test    rax, rax
0x180009230  jz      short loc_180009250
0x180009232  lea     rdx, [rbp+var_50]
0x180009236  xor     ecx, ecx
0x180009238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000923d  mov     rdi, rax
0x180009240  test    rax, rax
0x180009243  mov     rax, cs:__pfnDliNotifyHook2
0x18000924a  jnz     loc_180009549
0x180009250  test    rbx, rbx
0x180009253  jnz     loc_1800093BE
0x180009259  test    rax, rax
0x18000925c  jz      short loc_180009276
0x18000925e  lea     rdx, [rbp+var_50]
0x180009262  lea     ecx, [rbx+1]
0x180009265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000926a  mov     rbx, rax
0x18000926d  test    rax, rax
0x180009270  jnz     loc_180009343
0x180009276  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000927a  xor     r8d, r8d; dwFlags
0x18000927d  xor     edx, edx; hFile
0x18000927f  call    cs:__imp_LoadLibraryExA
0x180009286  nop     dword ptr [rax+rax+00h]
0x18000928b  mov     rbx, rax
0x18000928e  test    rax, rax
0x180009291  jnz     loc_180009343
0x180009297  call    cs:__imp_GetLastError
0x18000929e  nop     dword ptr [rax+rax+00h]
0x1800092a3  mov     [rbp+var_10], eax
0x1800092a6  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800092ad  test    rax, rax
0x1800092b0  jz      short loc_1800092C6
0x1800092b2  lea     rdx, [rbp+var_50]
0x1800092b6  lea     ecx, [rbx+3]
0x1800092b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092be  mov     rbx, rax
0x1800092c1  test    rax, rax
0x1800092c4  jnz     short loc_180009343
0x1800092c6  test    cs:dword_18000B0A0, 1000h
0x1800092d0  lea     rax, [rbp+var_50]
0x1800092d4  mov     [rbp+Arguments], rax
0x1800092d8  mov     dword ptr [rbp+flOldProtect], 0
0x1800092df  jz      short loc_18000931F
0x1800092e1  lea     rcx, DloadSrwLock; SRWLock
0x1800092e8  call    cs:__imp_AcquireSRWLockExclusive
0x1800092ef  nop     dword ptr [rax+rax+00h]
0x1800092f4  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800092fb  jnz     short loc_18000930C
0x1800092fd  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180009303  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x180009307  call    DloadProtectSection
0x18000930c  lea     rcx, DloadSrwLock; SRWLock
0x180009313  call    cs:__imp_ReleaseSRWLockExclusive
0x18000931a  nop     dword ptr [rax+rax+00h]
0x18000931f  xor     edx, edx; dwExceptionFlags
0x180009321  lea     r9, [rbp+Arguments]; lpArguments
0x180009325  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18000932a  lea     r8d, [rdx+1]; nNumberOfArguments
0x18000932e  call    cs:__imp_RaiseException
0x180009335  nop     dword ptr [rax+rax+00h]
0x18000933a  mov     rax, [rbp+var_18]
0x18000933e  jmp     loc_1800095BF
0x180009343  xor     eax, eax
0x180009345  lock cmpxchg [r15], rbx
0x18000934a  mov     r15, rax
0x18000934d  jnz     short loc_18000939B
0x18000934f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180009353  jz      short loc_1800093B7
0x180009355  cmp     dword ptr [rsi+18h], 0
0x180009359  jz      short loc_1800093B7
0x18000935b  call    cs:__imp_GetProcessHeap
0x180009362  nop     dword ptr [rax+rax+00h]
0x180009367  mov     edx, 8; dwFlags
0x18000936c  mov     rcx, rax; hHeap
0x18000936f  lea     r8d, [rdx+8]; dwBytes
0x180009373  call    cs:__imp_HeapAlloc
0x18000937a  nop     dword ptr [rax+rax+00h]
0x18000937f  test    rax, rax
0x180009382  jz      short loc_1800093B7
0x180009384  mov     [rax+8], rsi
0x180009388  mov     rcx, cs:__puiHead
0x18000938f  mov     [rax], rcx
0x180009392  mov     cs:__puiHead, rax
0x180009399  jmp     short loc_1800093B7
0x18000939b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000939f  jz      short loc_1800093B0
0x1800093a1  mov     rcx, rbx; hLibModule
0x1800093a4  call    cs:__imp_FreeLibrary
0x1800093ab  nop     dword ptr [rax+rax+00h]
0x1800093b0  cmp     rbx, r15
0x1800093b3  cmovnz  rbx, r15
0x1800093b7  mov     rax, cs:__pfnDliNotifyHook2
0x1800093be  mov     [rbp+var_20], rbx
0x1800093c2  test    rax, rax
0x1800093c5  jz      short loc_1800093DF
0x1800093c7  lea     rdx, [rbp+var_50]
0x1800093cb  mov     ecx, 2
0x1800093d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093d5  mov     rdi, rax
0x1800093d8  mov     rax, cs:__pfnDliNotifyHook2
0x1800093df  test    rdi, rdi
0x1800093e2  jnz     loc_180009545
0x1800093e8  cmp     [rsi+14h], edi
0x1800093eb  jz      short loc_180009420
0x1800093ed  cmp     [rsi+1Ch], edi
0x1800093f0  jz      short loc_180009420
0x1800093f2  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800093f6  cmp     dword ptr [rcx+rbx], 4550h
0x1800093fd  jnz     short loc_180009420
0x1800093ff  mov     edx, [rbp+arg_0]
0x180009402  cmp     [rcx+rbx+8], edx
0x180009406  jnz     short loc_180009420
0x180009408  cmp     rbx, [rcx+rbx+30h]
0x18000940d  jnz     short loc_180009420
0x18000940f  mov     rdi, [rbp+flOldProtect]
0x180009413  mov     rdi, [rdi+r12]
0x180009417  test    rdi, rdi
0x18000941a  jnz     loc_180009545
0x180009420  mov     rdx, [rbp+lpProcName]; lpProcName
0x180009424  mov     rcx, rbx; hModule
0x180009427  call    cs:__imp_GetProcAddress
0x18000942e  nop     dword ptr [rax+rax+00h]
0x180009433  mov     rdi, rax
0x180009436  test    rax, rax
0x180009439  jnz     loc_18000953E
0x18000943f  call    cs:__imp_GetLastError
0x180009446  nop     dword ptr [rax+rax+00h]
0x18000944b  mov     [rbp+var_10], eax
0x18000944e  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180009455  test    rax, rax
0x180009458  jz      short loc_180009472
0x18000945a  lea     rdx, [rbp+var_50]
0x18000945e  lea     ecx, [rdi+4]
0x180009461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009466  mov     rdi, rax
0x180009469  test    rax, rax
0x18000946c  jnz     loc_18000953E
0x180009472  test    cs:dword_18000B0A0, 1000h
0x18000947c  lea     rax, [rbp+var_50]
0x180009480  mov     [rbp+Arguments], rax
0x180009484  mov     dword ptr [rbp+flOldProtect], 0
0x18000948b  jz      short loc_1800094CB
0x18000948d  lea     rcx, DloadSrwLock; SRWLock
0x180009494  call    cs:__imp_AcquireSRWLockExclusive
0x18000949b  nop     dword ptr [rax+rax+00h]
0x1800094a0  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800094a7  jnz     short loc_1800094B8
0x1800094a9  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800094af  lea     rdx, [rbp+flOldProtect]; lpflOldProtect
0x1800094b3  call    DloadProtectSection
0x1800094b8  lea     rcx, DloadSrwLock; SRWLock
0x1800094bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800094c6  nop     dword ptr [rax+rax+00h]
0x1800094cb  xor     edx, edx; dwExceptionFlags
0x1800094cd  lea     r9, [rbp+Arguments]; lpArguments
0x1800094d1  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800094d6  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800094da  call    cs:__imp_RaiseException
0x1800094e1  nop     dword ptr [rax+rax+00h]
0x1800094e6  test    cs:dword_18000B0A0, 1000h
0x1800094f0  jz      short loc_18000953A
0x1800094f2  lea     rcx, DloadSrwLock; SRWLock
0x1800094f9  call    cs:__imp_AcquireSRWLockExclusive
0x180009500  nop     dword ptr [rax+rax+00h]
0x180009505  mov     eax, cs:DloadSectionLockCount
0x18000950b  inc     eax
0x18000950d  mov     cs:DloadSectionLockCount, eax
0x180009513  cmp     eax, 1
0x180009516  jnz     short loc_180009527
0x180009518  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x18000951f  lea     ecx, [rax+3]; flNewProtect
0x180009522  call    DloadProtectSection
0x180009527  lea     rcx, DloadSrwLock; SRWLock
0x18000952e  call    cs:__imp_ReleaseSRWLockExclusive
0x180009535  nop     dword ptr [rax+rax+00h]
0x18000953a  mov     rdi, [rbp+var_18]
0x18000953e  mov     rax, cs:__pfnDliNotifyHook2
0x180009545  mov     [r13+0], rdi
0x180009549  test    rax, rax
0x18000954c  jz      short loc_18000956B
0x18000954e  lea     rdx, [rbp+var_50]
0x180009552  mov     [rbp+var_10], 0
0x180009559  mov     ecx, 5
0x18000955e  mov     [rbp+var_20], rbx
0x180009562  mov     [rbp+var_18], rdi
0x180009566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000956b  test    cs:dword_18000B0A0, 1000h
0x180009575  mov     dword ptr [rbp+flOldProtect], 0
0x18000957c  jz      short loc_1800095BC
0x18000957e  lea     rcx, DloadSrwLock; SRWLock
0x180009585  call    cs:__imp_AcquireSRWLockExclusive
0x18000958c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
