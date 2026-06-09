# __delayLoadHelper2

- ea: `0x180025030`
- end: `0x1800254cc`
- name: `__delayLoadHelper2`
- size: `1180`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800275a5`

## callees

- `0x180024f30`
- `0x180025030`
- `0x180027910`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800252c2`
- `KERNEL32!HeapAlloc` at `0x1800252c2`
- `KERNEL32!GetProcessHeap` at `0x1800252b0`
- `KERNEL32!GetProcessHeap` at `0x1800252b0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180025069`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002511d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002524e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800253c1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180025414`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002548b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180025069`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002511d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002524e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800253c1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180025414`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002548b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180025093`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002513e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180025273`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800253e6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180025443`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800254b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180025093`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002513e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180025273`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800253e6`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180025443`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800254b0`
- `KERNEL32!LoadLibraryExA` at `0x1800251f7`
- `KERNEL32!LoadLibraryExA` at `0x1800251f7`
- `KERNEL32!RaiseException` at `0x180025152`
- `KERNEL32!RaiseException` at `0x180025288`
- `KERNEL32!RaiseException` at `0x1800253fb`
- `KERNEL32!RaiseException` at `0x180025152`
- `KERNEL32!RaiseException` at `0x180025288`
- `KERNEL32!RaiseException` at `0x1800253fb`
- `KERNEL32!GetLastError` at `0x180025209`
- `KERNEL32!GetLastError` at `0x180025378`
- `KERNEL32!GetLastError` at `0x180025209`
- `KERNEL32!GetLastError` at `0x180025378`
- `KERNEL32!GetProcAddress` at `0x180025366`
- `KERNEL32!GetProcAddress` at `0x180025366`
- `KERNEL32!FreeLibrary` at `0x1800252ed`
- `KERNEL32!FreeLibrary` at `0x1800252ed`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, char *a2)
{
  char *v4; // r9
  int v5; // ecx
  const CHAR *v6; // rax
  volatile signed __int64 *v7; // r15
  __int64 rvaINT; // rdx
  char *v9; // r8
  char *v10; // rdx
  HMODULE Library; // rbx
  __int64 v13; // r12
  bool v14; // zf
  FARPROC ProcAddress; // rdi
  signed __int64 v16; // r15
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v18; // rax
  __int64 v19; // rax
  int v20; // [rsp+20h] [rbp-59h] BYREF
  const ImgDelayDescr *v21; // [rsp+28h] [rbp-51h]
  char *v22; // [rsp+30h] [rbp-49h]
  LPCSTR lpLibFileName; // [rsp+38h] [rbp-41h]
  BOOL v24; // [rsp+40h] [rbp-39h]
  LPCSTR lpProcName; // [rsp+48h] [rbp-31h]
  HMODULE v26; // [rsp+50h] [rbp-29h]
  INT_PTR (__stdcall *v27)(); // [rsp+58h] [rbp-21h]
  DWORD LastError; // [rsp+60h] [rbp-19h]
  DWORD v29; // [rsp+70h] [rbp-9h] BYREF
  ULONG_PTR Arguments; // [rsp+78h] [rbp-1h] BYREF
  ULONG_PTR v31; // [rsp+80h] [rbp+7h] BYREF
  char *v32; // [rsp+88h] [rbp+Fh]
  ULONG_PTR v33[8]; // [rsp+90h] [rbp+17h] BYREF
  DWORD dwTimeStamp; // [rsp+E0h] [rbp+67h]
  DWORD flOldProtect; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD v36; // [rsp+F0h] [rbp+77h] BYREF
  DWORD v37; // [rsp+F8h] [rbp+7Fh] BYREF

  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( ++DloadSectionLockCount == 1 )
    DloadProtectSection(4u, &DloadSectionOldProtection);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  lpProcName = 0;
  v4 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v5 = a1->grAttrs & 1;
  v6 = (char *)&_ImageBase + a1->rvaDLLName;
  v7 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  rvaINT = a1->rvaINT;
  v9 = (char *)&_ImageBase + a1->rvaIAT;
  v24 = 0;
  v10 = (char *)&_ImageBase + rvaINT;
  v26 = 0;
  v27 = 0;
  LastError = 0;
  v32 = v4;
  dwTimeStamp = a1->dwTimeStamp;
  v20 = 72;
  v21 = a1;
  v22 = a2;
  lpLibFileName = v6;
  if ( !(_BYTE)v5 )
  {
    Arguments = (ULONG_PTR)&v20;
    AcquireSRWLockExclusive(&DloadSrwLock);
    if ( !--DloadSectionLockCount )
      DloadProtectSection(DloadSectionOldProtection, &flOldProtect);
    ReleaseSRWLockExclusive(&DloadSrwLock);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v7;
  v13 = (unsigned int)((a2 - v9) >> 3);
  v14 = *(__int64 *)&v10[8 * v13] < 0;
  v24 = *(_QWORD *)&v10[8 * v13] >= 0LL;
  if ( v14 )
    LODWORD(lpProcName) = *(unsigned __int16 *)&v10[8 * v13];
  else
    lpProcName = (char *)&word_180000002 + *(unsigned int *)&v10[8 * v13];
  ProcAddress = 0;
  if ( !_pfnDefaultDliFailureHook2 || (ProcAddress = (FARPROC)_pfnDefaultDliFailureHook2(0, &v20)) == 0 )
  {
    if ( !Library )
    {
      if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(1, &v20)) == 0 )
      {
        Library = LoadLibraryExA(lpLibFileName, 0, 0);
        if ( !Library )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v20)) == 0 )
          {
            v31 = (ULONG_PTR)&v20;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, &v36);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007E, 0, 1u, &v31);
            return v27;
          }
        }
      }
      v16 = _InterlockedCompareExchange64(v7, (signed __int64)Library, 0);
      if ( v16 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v16 )
          Library = (HMODULE)v16;
      }
      else if ( Library != (HMODULE)-1LL )
      {
        if ( a1->rvaUnloadIAT )
        {
          ProcessHeap = GetProcessHeap();
          v18 = (struct UnloadInfo *)HeapAlloc(ProcessHeap, 8u, 0x10u);
          if ( v18 )
          {
            v18->pidd = a1;
            v18->puiNext = _puiHead;
            _puiHead = v18;
          }
        }
      }
    }
    v26 = Library;
    if ( _pfnDefaultDliFailureHook2 )
      ProcAddress = (FARPROC)_pfnDefaultDliFailureHook2(2, &v20);
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v19 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v19) != 17744)
        || *(_DWORD *)((char *)Library + v19 + 8) != dwTimeStamp
        || Library != *(HMODULE *)((char *)Library + v19 + 48)
        || (ProcAddress = *(FARPROC *)&v32[8 * v13]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, lpProcName);
        if ( !ProcAddress )
        {
          LastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (ProcAddress = (FARPROC)_pfnDefaultDliFailureHook2(4, &v20)) == 0 )
          {
            v33[0] = (ULONG_PTR)&v20;
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( !--DloadSectionLockCount )
              DloadProtectSection(DloadSectionOldProtection, &v37);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            RaiseException(0xC06D007F, 0, 1u, v33);
            AcquireSRWLockExclusive(&DloadSrwLock);
            if ( ++DloadSectionLockCount == 1 )
              DloadProtectSection(4u, &DloadSectionOldProtection);
            ReleaseSRWLockExclusive(&DloadSrwLock);
            ProcAddress = v27;
          }
        }
      }
    }
    *(_QWORD *)a2 = ProcAddress;
  }
  if ( _pfnDefaultDliFailureHook2 )
  {
    LastError = 0;
    v26 = Library;
    v27 = ProcAddress;
    _pfnDefaultDliFailureHook2(5, &v20);
  }
  AcquireSRWLockExclusive(&DloadSrwLock);
  if ( !--DloadSectionLockCount )
    DloadProtectSection(DloadSectionOldProtection, &v29);
  ReleaseSRWLockExclusive(&DloadSrwLock);
  return ProcAddress;
}

```

## disassembly

```asm
0x180025030  push    rbp
0x180025032  push    rbx
0x180025033  push    rdi
0x180025034  push    r12
0x180025036  push    r13
0x180025038  push    r14
0x18002503a  push    r15
0x18002503c  lea     rbp, [rsp-27h]
0x180025041  sub     rsp, 0A0h
0x180025048  test    cs:dword_18002A0B0, 1000h
0x180025052  lea     rbx, DloadSrwLock
0x180025059  mov     r13, rdx
0x18002505c  mov     r14, rcx
0x18002505f  mov     edi, 1
0x180025064  jz      short loc_180025099
0x180025066  mov     rcx, rbx; SRWLock
0x180025069  call    cs:__imp_AcquireSRWLockExclusive
0x18002506f  mov     eax, cs:DloadSectionLockCount
0x180025075  add     eax, edi
0x180025077  mov     cs:DloadSectionLockCount, eax
0x18002507d  cmp     eax, edi
0x18002507f  jnz     short loc_180025090
0x180025081  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180025088  lea     ecx, [rdi+3]; flNewProtect
0x18002508b  call    DloadProtectSection
0x180025090  mov     rcx, rbx; SRWLock
0x180025093  call    cs:__imp_ReleaseSRWLockExclusive
0x180025099  and     [rbp+57h+lpProcName], 0
0x18002509e  lea     r10, __ImageBase
0x1800250a5  mov     r9d, [r14+14h]
0x1800250a9  mov     ecx, [r14]
0x1800250ac  add     r9, r10
0x1800250af  mov     eax, [r14+4]
0x1800250b3  and     ecx, edi
0x1800250b5  mov     r15d, [r14+8]
0x1800250b9  add     rax, r10
0x1800250bc  mov     r8d, [r14+0Ch]
0x1800250c0  add     r15, r10
0x1800250c3  mov     edx, [r14+10h]
0x1800250c7  add     r8, r10
0x1800250ca  and     [rbp+57h+var_90], 0
0x1800250ce  add     rdx, r10
0x1800250d1  and     dword ptr [rbp+57h+lpProcName], 0
0x1800250d5  and     [rbp+57h+var_80], 0
0x1800250da  and     [rbp+57h+var_78], 0
0x1800250df  and     [rbp+57h+var_70], 0
0x1800250e3  mov     [rbp+57h+var_48], r9
0x1800250e7  mov     r9d, [r14+1Ch]
0x1800250eb  mov     [rbp+57h+arg_0], r9d
0x1800250ef  mov     [rbp+57h+var_B0], 48h ; 'H'
0x1800250f6  mov     [rbp+57h+var_A8], r14
0x1800250fa  mov     [rbp+57h+var_A0], r13
0x1800250fe  mov     [rbp+57h+lpLibFileName], rax
0x180025102  test    cl, cl
0x180025104  jnz     short loc_18002515F
0x180025106  test    cs:dword_18002A0B0, 1000h
0x180025110  lea     rax, [rbp+57h+var_B0]
0x180025114  mov     [rbp+57h+Arguments], rax
0x180025118  jz      short loc_180025144
0x18002511a  mov     rcx, rbx; SRWLock
0x18002511d  call    cs:__imp_AcquireSRWLockExclusive
0x180025123  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18002512a  jnz     short loc_18002513B
0x18002512c  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180025132  lea     rdx, [rbp+57h+flOldProtect]; lpflOldProtect
0x180025136  call    DloadProtectSection
0x18002513b  mov     rcx, rbx; SRWLock
0x18002513e  call    cs:__imp_ReleaseSRWLockExclusive
0x180025144  lea     r9, [rbp+57h+Arguments]; lpArguments
0x180025148  mov     r8d, edi; nNumberOfArguments
0x18002514b  xor     edx, edx; dwExceptionFlags
0x18002514d  mov     ecx, 0C06D0057h; dwExceptionCode
0x180025152  call    cs:__imp_RaiseException
0x180025158  xor     eax, eax
0x18002515a  jmp     loc_1800254B9
0x18002515f  mov     rbx, [r15]
0x180025162  mov     r12, r13
0x180025165  sub     r12, r8
0x180025168  sar     r12, 3
0x18002516c  mov     r12d, r12d
0x18002516f  mov     rax, [rdx+r12*8]
0x180025173  shr     rax, 3Fh
0x180025177  xor     eax, edi
0x180025179  mov     [rbp+57h+var_90], eax
0x18002517c  jz      short loc_180025192
0x18002517e  mov     eax, [rdx+r12*8]
0x180025182  lea     rcx, word_180000002
0x180025189  add     rax, rcx
0x18002518c  mov     [rbp+57h+lpProcName], rax
0x180025190  jmp     short loc_18002519A
0x180025192  movzx   eax, word ptr [rdx+r12*8]
0x180025197  mov     dword ptr [rbp+57h+lpProcName], eax
0x18002519a  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800251a1  xor     edi, edi
0x1800251a3  test    rax, rax
0x1800251a6  jz      short loc_1800251C0
0x1800251a8  lea     rdx, [rbp+57h+var_B0]
0x1800251ac  xor     ecx, ecx
0x1800251ae  call    cs:__guard_dispatch_icall_fptr
0x1800251b4  mov     rdi, rax
0x1800251b7  test    rax, rax
0x1800251ba  jnz     loc_180025451
0x1800251c0  test    rbx, rbx
0x1800251c3  jnz     loc_1800252FA
0x1800251c9  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800251d0  test    rax, rax
0x1800251d3  jz      short loc_1800251EE
0x1800251d5  lea     rdx, [rbp+57h+var_B0]
0x1800251d9  lea     ecx, [rbx+1]
0x1800251dc  call    cs:__guard_dispatch_icall_fptr
0x1800251e2  mov     rbx, rax
0x1800251e5  test    rax, rax
0x1800251e8  jnz     loc_180025297
0x1800251ee  mov     rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x1800251f2  xor     r8d, r8d; dwFlags
0x1800251f5  xor     edx, edx; hFile
0x1800251f7  call    cs:__imp_LoadLibraryExA
0x1800251fd  mov     rbx, rax
0x180025200  test    rax, rax
0x180025203  jnz     loc_180025297
0x180025209  call    cs:__imp_GetLastError
0x18002520f  mov     [rbp+57h+var_70], eax
0x180025212  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180025219  test    rax, rax
0x18002521c  jz      short loc_180025233
0x18002521e  lea     rdx, [rbp+57h+var_B0]
0x180025222  lea     ecx, [rbx+3]
0x180025225  call    cs:__guard_dispatch_icall_fptr
0x18002522b  mov     rbx, rax
0x18002522e  test    rax, rax
0x180025231  jnz     short loc_180025297
0x180025233  test    cs:dword_18002A0B0, 1000h
0x18002523d  lea     rax, [rbp+57h+var_B0]
0x180025241  mov     [rbp+57h+var_50], rax
0x180025245  jz      short loc_180025279
0x180025247  lea     rcx, DloadSrwLock; SRWLock
0x18002524e  call    cs:__imp_AcquireSRWLockExclusive
0x180025254  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x18002525b  jnz     short loc_18002526C
0x18002525d  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x180025263  lea     rdx, [rbp+57h+arg_10]; lpflOldProtect
0x180025267  call    DloadProtectSection
0x18002526c  lea     rcx, DloadSrwLock; SRWLock
0x180025273  call    cs:__imp_ReleaseSRWLockExclusive
0x180025279  xor     edx, edx; dwExceptionFlags
0x18002527b  lea     r9, [rbp+57h+var_50]; lpArguments
0x18002527f  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180025284  lea     r8d, [rdx+1]; nNumberOfArguments
0x180025288  call    cs:__imp_RaiseException
0x18002528e  mov     rax, [rbp+57h+var_78]
0x180025292  jmp     loc_1800254B9
0x180025297  xor     eax, eax
0x180025299  lock cmpxchg [r15], rbx
0x18002529e  mov     r15, rax
0x1800252a1  jnz     short loc_1800252E4
0x1800252a3  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800252a7  jz      short loc_1800252FA
0x1800252a9  cmp     dword ptr [r14+18h], 0
0x1800252ae  jz      short loc_1800252FA
0x1800252b0  call    cs:__imp_GetProcessHeap
0x1800252b6  mov     edx, 8; dwFlags
0x1800252bb  mov     rcx, rax; hHeap
0x1800252be  lea     r8d, [rdx+8]; dwBytes
0x1800252c2  call    cs:__imp_HeapAlloc
0x1800252c8  test    rax, rax
0x1800252cb  jz      short loc_1800252FA
0x1800252cd  mov     [rax+8], r14
0x1800252d1  mov     rcx, cs:__puiHead
0x1800252d8  mov     [rax], rcx
0x1800252db  mov     cs:__puiHead, rax
0x1800252e2  jmp     short loc_1800252FA
0x1800252e4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800252e8  jz      short loc_1800252F3
0x1800252ea  mov     rcx, rbx; hLibModule
0x1800252ed  call    cs:__imp_FreeLibrary
0x1800252f3  cmp     rbx, r15
0x1800252f6  cmovnz  rbx, r15
0x1800252fa  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180025301  mov     [rbp+57h+var_80], rbx
0x180025305  test    rax, rax
0x180025308  jz      short loc_18002531C
0x18002530a  lea     rdx, [rbp+57h+var_B0]
0x18002530e  mov     ecx, 2
0x180025313  call    cs:__guard_dispatch_icall_fptr
0x180025319  mov     rdi, rax
0x18002531c  test    rdi, rdi
0x18002531f  jnz     loc_18002544D
0x180025325  cmp     [r14+14h], edi
0x180025329  jz      short loc_18002535F
0x18002532b  cmp     [r14+1Ch], edi
0x18002532f  jz      short loc_18002535F
0x180025331  movsxd  rax, dword ptr [rbx+3Ch]
0x180025335  cmp     dword ptr [rax+rbx], 4550h
0x18002533c  jnz     short loc_18002535F
0x18002533e  mov     ecx, [rbp+57h+arg_0]
0x180025341  cmp     [rax+rbx+8], ecx
0x180025345  jnz     short loc_18002535F
0x180025347  cmp     rbx, [rax+rbx+30h]
0x18002534c  jnz     short loc_18002535F
0x18002534e  mov     rdi, [rbp+57h+var_48]
0x180025352  mov     rdi, [rdi+r12*8]
0x180025356  test    rdi, rdi
0x180025359  jnz     loc_18002544D
0x18002535f  mov     rdx, [rbp+57h+lpProcName]; lpProcName
0x180025363  mov     rcx, rbx; hModule
0x180025366  call    cs:__imp_GetProcAddress
0x18002536c  mov     rdi, rax
0x18002536f  test    rax, rax
0x180025372  jnz     loc_18002544D
0x180025378  call    cs:__imp_GetLastError
0x18002537e  mov     [rbp+57h+var_70], eax
0x180025381  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180025388  test    rax, rax
0x18002538b  jz      short loc_1800253A6
0x18002538d  lea     rdx, [rbp+57h+var_B0]
0x180025391  lea     ecx, [rdi+4]
0x180025394  call    cs:__guard_dispatch_icall_fptr
0x18002539a  mov     rdi, rax
0x18002539d  test    rax, rax
0x1800253a0  jnz     loc_18002544D
0x1800253a6  test    cs:dword_18002A0B0, 1000h
0x1800253b0  lea     rax, [rbp+57h+var_B0]
0x1800253b4  mov     [rbp+57h+var_40], rax
0x1800253b8  jz      short loc_1800253EC
0x1800253ba  lea     rcx, DloadSrwLock; SRWLock
0x1800253c1  call    cs:__imp_AcquireSRWLockExclusive
0x1800253c7  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x1800253ce  jnz     short loc_1800253DF
0x1800253d0  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800253d6  lea     rdx, [rbp+57h+arg_18]; lpflOldProtect
0x1800253da  call    DloadProtectSection
0x1800253df  lea     rcx, DloadSrwLock; SRWLock
0x1800253e6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800253ec  xor     edx, edx; dwExceptionFlags
0x1800253ee  lea     r9, [rbp+57h+var_40]; lpArguments
0x1800253f2  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800253f7  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800253fb  call    cs:__imp_RaiseException
0x180025401  test    cs:dword_18002A0B0, 1000h
0x18002540b  jz      short loc_180025449
0x18002540d  lea     rcx, DloadSrwLock; SRWLock
0x180025414  call    cs:__imp_AcquireSRWLockExclusive
0x18002541a  mov     eax, cs:DloadSectionLockCount
0x180025420  inc     eax
0x180025422  mov     cs:DloadSectionLockCount, eax
0x180025428  cmp     eax, 1
0x18002542b  jnz     short loc_18002543C
0x18002542d  lea     rdx, DloadSectionOldProtection; lpflOldProtect
0x180025434  lea     ecx, [rax+3]; flNewProtect
0x180025437  call    DloadProtectSection
0x18002543c  lea     rcx, DloadSrwLock; SRWLock
0x180025443  call    cs:__imp_ReleaseSRWLockExclusive
0x180025449  mov     rdi, [rbp+57h+var_78]
0x18002544d  mov     [r13+0], rdi
0x180025451  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180025458  test    rax, rax
0x18002545b  jz      short loc_180025478
0x18002545d  and     [rbp+57h+var_70], 0
0x180025461  lea     rdx, [rbp+57h+var_B0]
0x180025465  mov     ecx, 5
0x18002546a  mov     [rbp+57h+var_80], rbx
0x18002546e  mov     [rbp+57h+var_78], rdi
0x180025472  call    cs:__guard_dispatch_icall_fptr
0x180025478  test    cs:dword_18002A0B0, 1000h
0x180025482  jz      short loc_1800254B6
0x180025484  lea     rcx, DloadSrwLock; SRWLock
0x18002548b  call    cs:__imp_AcquireSRWLockExclusive
0x180025491  add     cs:DloadSectionLockCount, 0FFFFFFFFh
0x180025498  jnz     short loc_1800254A9
0x18002549a  mov     ecx, cs:DloadSectionOldProtection; flNewProtect
0x1800254a0  lea     rdx, [rbp+57h+var_60]; lpflOldProtect
0x1800254a4  call    DloadProtectSection
0x1800254a9  lea     rcx, DloadSrwLock; SRWLock
0x1800254b0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800254b6  mov     rax, rdi
0x1800254b9  add     rsp, 0A0h
0x1800254c0  pop     r15
0x1800254c2  pop     r14
0x1800254c4  pop     r13
0x1800254c6  pop     r12
0x1800254c8  pop     rdi
0x1800254c9  pop     rbx
0x1800254ca  pop     rbp
0x1800254cb  retn
```
