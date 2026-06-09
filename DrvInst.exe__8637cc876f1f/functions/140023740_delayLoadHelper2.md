# __delayLoadHelper2

- ea: `0x140023740`
- end: `0x140023a74`
- name: `__delayLoadHelper2`
- size: `820`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `13`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001e90`
- `0x140001f1b`
- `0x14000200e`
- `0x1400020ab`
- `0x140002136`
- `0x1400021f7`
- `0x1400022ca`
- `0x140002355`
- `0x14000246a`
- `0x140002507`
- `0x1400025e2`
- `0x14000281e`
- `0x14000295d`

## callees

- `0x1400234e8`
- `0x1400236e8`
- `0x140023740`
- `0x140045eea`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400239cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400239cc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140023957`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140023957`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1400238a0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1400238a0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002392c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14002392c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002391a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14002391a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400237ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400238f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140023a1f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400237ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400238f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140023a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400238ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400239da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400238ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400239da`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  __int16 *v5; // rdx
  volatile signed __int64 *v6; // r14
  __int64 dwTimeStamp; // rcx
  char *v8; // r15
  DWORD grAttrs; // eax
  HMODULE Library; // rbx
  __int64 v12; // r13
  PUnloadInfo v13; // rcx
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v16; // r14
  HANDLE ProcessHeap; // rax
  struct UnloadInfo *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  struct DelayLoadInfo v22; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+48h] BYREF

  *(&v22.cb + 1) = 0;
  memset_0(&v22, 0, 0x44u);
  ((void (*)(void))DloadAcquireSectionWriteAccess)();
  v5 = &_ImageBase;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v8 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v22.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v22.cb = 72;
  v22.pidd = a1;
  v22.ppfn = a2;
  v22.dlp.fImportByName = 0;
  memset(&v22.dlp.szProcName, 0, 28);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v22;
    DloadReleaseSectionWriteAccess(dwTimeStamp, &_ImageBase, v4);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v6;
  v12 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v13 = (PUnloadInfo)(v12 + a1->rvaINT);
  v22.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + (_QWORD)v13) >= 0LL;
  if ( v22.dlp.fImportByName )
  {
    v5 = &word_140000002;
    v22.dlp.szProcName = (char *)&word_140000002 + *(unsigned int *)((char *)&_ImageBase + (_QWORD)v13);
  }
  else
  {
    v22.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + (_QWORD)v13);
  }
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v22), v14 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(1, &v22)) == 0 )
      {
        Library = LoadLibraryExA(v22.szDll, 0, 0);
        if ( !Library )
        {
          v22.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v22)) == 0 )
          {
            Arguments = (ULONG_PTR)&v22;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v22.pfnCur;
          }
        }
      }
      v16 = _InterlockedCompareExchange64(v6, (signed __int64)Library, 0);
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
            v13 = _puiHead;
            v18->puiNext = _puiHead;
            _puiHead = v18;
          }
        }
      }
      v14 = _pfnDliNotifyHook2;
    }
    v22.hmodCur = Library;
    if ( v14 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(2, &v22);
      v14 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v13 = (PUnloadInfo)*((int *)Library + 15), *(_DWORD *)((char *)Library + (_QWORD)v13) != 17744)
        || (v5 = (__int16 *)(unsigned int)Arguments, *(_DWORD *)((char *)Library + (_QWORD)v13 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + (_QWORD)v13 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v8[v12]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v22.dlp.szProcName);
        if ( !ProcAddress )
        {
          v22.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v22)) == 0 )
          {
            Arguments = (ULONG_PTR)&v22;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            DloadAcquireSectionWriteAccess(v20, v19, v21);
            ProcAddress = v22.pfnCur;
          }
        }
        v14 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v14 )
  {
    v22.dwLastError = 0;
    v22.hmodCur = Library;
    v22.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(5, &v22);
  }
  DloadReleaseSectionWriteAccess(v13, v5, v4);
  return ProcAddress;
}

```

## disassembly

```asm
0x140023740  push    rbp
0x140023742  push    rbx
0x140023743  push    rsi
0x140023744  push    rdi
0x140023745  push    r12
0x140023747  push    r13
0x140023749  push    r14
0x14002374b  push    r15
0x14002374d  mov     rbp, rsp
0x140023750  sub     rsp, 78h
0x140023754  xor     eax, eax
0x140023756  mov     r12, rdx
0x140023759  mov     rsi, rcx
0x14002375c  mov     [rbp+var_54], eax
0x14002375f  xor     edx, edx; Val
0x140023761  lea     rcx, [rbp+var_58]; void *
0x140023765  lea     r8d, [rax+44h]; Size
0x140023769  call    memset_0
0x14002376e  call    DloadAcquireSectionWriteAccess
0x140023773  mov     eax, [rsi+4]
0x140023776  lea     rdx, __ImageBase
0x14002377d  mov     r14d, [rsi+8]
0x140023781  add     rax, rdx
0x140023784  mov     r15d, [rsi+14h]
0x140023788  add     r14, rdx
0x14002378b  mov     ecx, [rsi+1Ch]
0x14002378e  add     r15, rdx
0x140023791  mov     [rbp+lpLibFileName], rax
0x140023795  mov     eax, [rsi]
0x140023797  mov     dword ptr [rbp+Arguments], ecx
0x14002379a  mov     [rbp+var_58], 48h ; 'H'
0x1400237a1  mov     [rbp+var_50], rsi
0x1400237a5  mov     [rbp+var_48], r12
0x1400237a9  mov     [rbp+var_38], 0
0x1400237b0  mov     [rbp+lpProcName], 0
0x1400237b8  mov     [rbp+var_28], 0
0x1400237c0  mov     [rbp+var_20], 0
0x1400237c8  mov     [rbp+var_18], 0
0x1400237cf  test    al, 1
0x1400237d1  jnz     short loc_1400237FC
0x1400237d3  lea     rax, [rbp+var_58]
0x1400237d7  mov     [rbp+Arguments], rax
0x1400237db  call    DloadReleaseSectionWriteAccess
0x1400237e0  xor     edx, edx; dwExceptionFlags
0x1400237e2  lea     r9, [rbp+Arguments]; lpArguments
0x1400237e6  mov     ecx, 0C06D0057h; dwExceptionCode
0x1400237eb  lea     r8d, [rdx+1]; nNumberOfArguments
0x1400237ef  call    cs:__imp_RaiseException
0x1400237f5  xor     eax, eax
0x1400237f7  jmp     loc_140023A63
0x1400237fc  mov     eax, [rsi+0Ch]
0x1400237ff  mov     rcx, r12
0x140023802  mov     rbx, [r14]
0x140023805  sub     rcx, rax
0x140023808  sub     rcx, rdx
0x14002380b  sar     rcx, 3
0x14002380f  mov     eax, ecx
0x140023811  mov     ecx, [rsi+10h]
0x140023814  lea     r13, ds:0[rax*8]
0x14002381c  xor     eax, eax
0x14002381e  add     rcx, r13
0x140023821  cmp     [rcx+rdx], rax
0x140023825  setnl   al
0x140023828  mov     [rbp+var_38], eax
0x14002382b  test    eax, eax
0x14002382d  jz      short loc_140023842
0x14002382f  mov     eax, [rcx+rdx]
0x140023832  lea     rdx, word_140000002
0x140023839  add     rax, rdx
0x14002383c  mov     [rbp+lpProcName], rax
0x140023840  jmp     short loc_140023849
0x140023842  movzx   eax, word ptr [rcx+rdx]
0x140023846  mov     dword ptr [rbp+lpProcName], eax
0x140023849  mov     rax, cs:__pfnDliNotifyHook2
0x140023850  xor     edi, edi
0x140023852  test    rax, rax
0x140023855  jz      short loc_140023875
0x140023857  lea     rdx, [rbp+var_58]
0x14002385b  xor     ecx, ecx
0x14002385d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023862  mov     rdi, rax
0x140023865  test    rax, rax
0x140023868  mov     rax, cs:__pfnDliNotifyHook2
0x14002386f  jnz     loc_140023A39
0x140023875  test    rbx, rbx
0x140023878  jnz     loc_14002396B
0x14002387e  test    rax, rax
0x140023881  jz      short loc_140023897
0x140023883  lea     rdx, [rbp+var_58]
0x140023887  lea     ecx, [rbx+1]
0x14002388a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002388f  mov     rbx, rax
0x140023892  test    rax, rax
0x140023895  jnz     short loc_140023902
0x140023897  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x14002389b  xor     r8d, r8d; dwFlags
0x14002389e  xor     edx, edx; hFile
0x1400238a0  call    cs:__imp_LoadLibraryExA
0x1400238a6  mov     rbx, rax
0x1400238a9  test    rax, rax
0x1400238ac  jnz     short loc_140023902
0x1400238ae  call    cs:__imp_GetLastError
0x1400238b4  mov     [rbp+var_18], eax
0x1400238b7  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1400238be  test    rax, rax
0x1400238c1  jz      short loc_1400238D7
0x1400238c3  lea     rdx, [rbp+var_58]
0x1400238c7  lea     ecx, [rbx+3]
0x1400238ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400238cf  mov     rbx, rax
0x1400238d2  test    rax, rax
0x1400238d5  jnz     short loc_140023902
0x1400238d7  lea     rax, [rbp+var_58]
0x1400238db  mov     [rbp+Arguments], rax
0x1400238df  call    DloadReleaseSectionWriteAccess
0x1400238e4  xor     edx, edx; dwExceptionFlags
0x1400238e6  lea     r9, [rbp+Arguments]; lpArguments
0x1400238ea  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1400238ef  lea     r8d, [rdx+1]; nNumberOfArguments
0x1400238f3  call    cs:__imp_RaiseException
0x1400238f9  mov     rax, [rbp+var_20]
0x1400238fd  jmp     loc_140023A63
0x140023902  xor     eax, eax
0x140023904  lock cmpxchg [r14], rbx
0x140023909  mov     r14, rax
0x14002390c  jnz     short loc_14002394E
0x14002390e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140023912  jz      short loc_140023964
0x140023914  cmp     dword ptr [rsi+18h], 0
0x140023918  jz      short loc_140023964
0x14002391a  call    cs:__imp_GetProcessHeap
0x140023920  mov     edx, 8; dwFlags
0x140023925  mov     rcx, rax; hHeap
0x140023928  lea     r8d, [rdx+8]; dwBytes
0x14002392c  call    cs:__imp_HeapAlloc
0x140023932  test    rax, rax
0x140023935  jz      short loc_140023964
0x140023937  mov     [rax+8], rsi
0x14002393b  mov     rcx, cs:__puiHead
0x140023942  mov     [rax], rcx
0x140023945  mov     cs:__puiHead, rax
0x14002394c  jmp     short loc_140023964
0x14002394e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140023952  jz      short loc_14002395D
0x140023954  mov     rcx, rbx; hLibModule
0x140023957  call    cs:__imp_FreeLibrary
0x14002395d  cmp     rbx, r14
0x140023960  cmovnz  rbx, r14
0x140023964  mov     rax, cs:__pfnDliNotifyHook2
0x14002396b  mov     [rbp+var_28], rbx
0x14002396f  test    rax, rax
0x140023972  jz      short loc_14002398C
0x140023974  lea     rdx, [rbp+var_58]
0x140023978  mov     ecx, 2
0x14002397d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023982  mov     rdi, rax
0x140023985  mov     rax, cs:__pfnDliNotifyHook2
0x14002398c  test    rdi, rdi
0x14002398f  jnz     loc_140023A35
0x140023995  cmp     [rsi+14h], edi
0x140023998  jz      short loc_1400239C5
0x14002399a  cmp     [rsi+1Ch], edi
0x14002399d  jz      short loc_1400239C5
0x14002399f  movsxd  rcx, dword ptr [rbx+3Ch]
0x1400239a3  cmp     dword ptr [rcx+rbx], 4550h
0x1400239aa  jnz     short loc_1400239C5
0x1400239ac  mov     edx, dword ptr [rbp+Arguments]
0x1400239af  cmp     [rcx+rbx+8], edx
0x1400239b3  jnz     short loc_1400239C5
0x1400239b5  cmp     rbx, [rcx+rbx+30h]
0x1400239ba  jnz     short loc_1400239C5
0x1400239bc  mov     rdi, [r15+r13]
0x1400239c0  test    rdi, rdi
0x1400239c3  jnz     short loc_140023A35
0x1400239c5  mov     rdx, [rbp+lpProcName]; lpProcName
0x1400239c9  mov     rcx, rbx; hModule
0x1400239cc  call    cs:__imp_GetProcAddress
0x1400239d2  mov     rdi, rax
0x1400239d5  test    rax, rax
0x1400239d8  jnz     short loc_140023A2E
0x1400239da  call    cs:__imp_GetLastError
0x1400239e0  mov     [rbp+var_18], eax
0x1400239e3  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1400239ea  test    rax, rax
0x1400239ed  jz      short loc_140023A03
0x1400239ef  lea     rdx, [rbp+var_58]
0x1400239f3  lea     ecx, [rdi+4]
0x1400239f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400239fb  mov     rdi, rax
0x1400239fe  test    rax, rax
0x140023a01  jnz     short loc_140023A2E
0x140023a03  lea     rax, [rbp+var_58]
0x140023a07  mov     [rbp+Arguments], rax
0x140023a0b  call    DloadReleaseSectionWriteAccess
0x140023a10  xor     edx, edx; dwExceptionFlags
0x140023a12  lea     r9, [rbp+Arguments]; lpArguments
0x140023a16  mov     ecx, 0C06D007Fh; dwExceptionCode
0x140023a1b  lea     r8d, [rdx+1]; nNumberOfArguments
0x140023a1f  call    cs:__imp_RaiseException
0x140023a25  call    DloadAcquireSectionWriteAccess
0x140023a2a  mov     rdi, [rbp+var_20]
0x140023a2e  mov     rax, cs:__pfnDliNotifyHook2
0x140023a35  mov     [r12], rdi
0x140023a39  test    rax, rax
0x140023a3c  jz      short loc_140023A5B
0x140023a3e  lea     rdx, [rbp+var_58]
0x140023a42  mov     [rbp+var_18], 0
0x140023a49  mov     ecx, 5
0x140023a4e  mov     [rbp+var_28], rbx
0x140023a52  mov     [rbp+var_20], rdi
0x140023a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023a5b  call    DloadReleaseSectionWriteAccess
0x140023a60  mov     rax, rdi
0x140023a63  add     rsp, 78h
0x140023a67  pop     r15
0x140023a69  pop     r14
0x140023a6b  pop     r13
0x140023a6d  pop     r12
0x140023a6f  pop     rdi
0x140023a70  pop     rsi
0x140023a71  pop     rbx
0x140023a72  pop     rbp
0x140023a73  retn
```
