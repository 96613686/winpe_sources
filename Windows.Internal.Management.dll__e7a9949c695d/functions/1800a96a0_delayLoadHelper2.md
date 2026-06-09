# __delayLoadHelper2

- ea: `0x1800a96a0`
- end: `0x1800a99d4`
- name: `__delayLoadHelper2`
- size: `820`
- prototype: ``
- caller_count: `21`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800059cd`
- `0x180005a6a`
- `0x180005b61`
- `0x180005ce8`
- `0x180005d97`
- `0x180005e22`
- `0x180005ead`
- `0x180005fd6`
- `0x180006061`
- `0x180006122`
- `0x1800061ad`
- `0x18000625c`
- `0x1800062f9`
- `0x180006396`
- `0x180006445`
- `0x1800064d0`
- `0x18000655b`
- `0x1800065f8`
- `0x180006683`
- `0x180007b41`
- `0x180007bde`

## callees

- `0x180005904`
- `0x1800a9444`
- `0x1800a9644`
- `0x1800a96a0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a992c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a992c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800a9800`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800a9800`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a98b7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a98b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a988c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a988c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a987a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a987a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a974f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a9853`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a997f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a974f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a9853`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a997f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a980e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a993a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a980e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a993a`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  unsigned __int64 v5; // rdx
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
  v5 = (unsigned __int64)&_ImageBase;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase.unused + a1->rvaHmod);
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
  v22.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase.unused + (_QWORD)v13) >= 0LL;
  if ( v22.dlp.fImportByName )
  {
    v5 = (unsigned __int64)&_ImageBase.unused + 2;
    v22.dlp.szProcName = (char *)&_ImageBase.unused + *(unsigned int *)((char *)&_ImageBase.unused + (_QWORD)v13) + 2;
  }
  else
  {
    v22.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase.unused + (_QWORD)v13);
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
        || (v5 = (unsigned int)Arguments, *(_DWORD *)((char *)Library + (_QWORD)v13 + 8) != (_DWORD)Arguments)
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
0x1800a96a0  push    rbp
0x1800a96a2  push    rbx
0x1800a96a3  push    rsi
0x1800a96a4  push    rdi
0x1800a96a5  push    r12
0x1800a96a7  push    r13
0x1800a96a9  push    r14
0x1800a96ab  push    r15
0x1800a96ad  mov     rbp, rsp
0x1800a96b0  sub     rsp, 78h
0x1800a96b4  xor     eax, eax
0x1800a96b6  mov     r12, rdx
0x1800a96b9  mov     rsi, rcx
0x1800a96bc  mov     [rbp+var_54], eax
0x1800a96bf  xor     edx, edx; Val
0x1800a96c1  lea     rcx, [rbp+var_58]; void *
0x1800a96c5  lea     r8d, [rax+44h]; Size
0x1800a96c9  call    memset_0
0x1800a96ce  call    DloadAcquireSectionWriteAccess
0x1800a96d3  mov     eax, [rsi+4]
0x1800a96d6  lea     rdx, __ImageBase
0x1800a96dd  mov     r14d, [rsi+8]
0x1800a96e1  add     rax, rdx
0x1800a96e4  mov     r15d, [rsi+14h]
0x1800a96e8  add     r14, rdx
0x1800a96eb  mov     ecx, [rsi+1Ch]
0x1800a96ee  add     r15, rdx
0x1800a96f1  mov     [rbp+lpLibFileName], rax
0x1800a96f5  mov     eax, [rsi]
0x1800a96f7  mov     dword ptr [rbp+Arguments], ecx
0x1800a96fa  mov     [rbp+var_58], 48h ; 'H'
0x1800a9701  mov     [rbp+var_50], rsi
0x1800a9705  mov     [rbp+var_48], r12
0x1800a9709  mov     [rbp+var_38], 0
0x1800a9710  mov     [rbp+lpProcName], 0
0x1800a9718  mov     [rbp+var_28], 0
0x1800a9720  mov     [rbp+var_20], 0
0x1800a9728  mov     [rbp+var_18], 0
0x1800a972f  test    al, 1
0x1800a9731  jnz     short loc_1800A975C
0x1800a9733  lea     rax, [rbp+var_58]
0x1800a9737  mov     [rbp+Arguments], rax
0x1800a973b  call    DloadReleaseSectionWriteAccess
0x1800a9740  xor     edx, edx; dwExceptionFlags
0x1800a9742  lea     r9, [rbp+Arguments]; lpArguments
0x1800a9746  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800a974b  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800a974f  call    cs:__imp_RaiseException
0x1800a9755  xor     eax, eax
0x1800a9757  jmp     loc_1800A99C3
0x1800a975c  mov     eax, [rsi+0Ch]
0x1800a975f  mov     rcx, r12
0x1800a9762  mov     rbx, [r14]
0x1800a9765  sub     rcx, rax
0x1800a9768  sub     rcx, rdx
0x1800a976b  sar     rcx, 3
0x1800a976f  mov     eax, ecx
0x1800a9771  mov     ecx, [rsi+10h]
0x1800a9774  lea     r13, ds:0[rax*8]
0x1800a977c  xor     eax, eax
0x1800a977e  add     rcx, r13
0x1800a9781  cmp     [rcx+rdx], rax
0x1800a9785  setnl   al
0x1800a9788  mov     [rbp+var_38], eax
0x1800a978b  test    eax, eax
0x1800a978d  jz      short loc_1800A97A2
0x1800a978f  mov     eax, [rcx+rdx]
0x1800a9792  lea     rdx, __ImageBase.unused+2
0x1800a9799  add     rax, rdx
0x1800a979c  mov     [rbp+lpProcName], rax
0x1800a97a0  jmp     short loc_1800A97A9
0x1800a97a2  movzx   eax, word ptr [rcx+rdx]
0x1800a97a6  mov     dword ptr [rbp+lpProcName], eax
0x1800a97a9  mov     rax, cs:__pfnDliNotifyHook2
0x1800a97b0  xor     edi, edi
0x1800a97b2  test    rax, rax
0x1800a97b5  jz      short loc_1800A97D5
0x1800a97b7  lea     rdx, [rbp+var_58]
0x1800a97bb  xor     ecx, ecx
0x1800a97bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a97c2  mov     rdi, rax
0x1800a97c5  test    rax, rax
0x1800a97c8  mov     rax, cs:__pfnDliNotifyHook2
0x1800a97cf  jnz     loc_1800A9999
0x1800a97d5  test    rbx, rbx
0x1800a97d8  jnz     loc_1800A98CB
0x1800a97de  test    rax, rax
0x1800a97e1  jz      short loc_1800A97F7
0x1800a97e3  lea     rdx, [rbp+var_58]
0x1800a97e7  lea     ecx, [rbx+1]
0x1800a97ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a97ef  mov     rbx, rax
0x1800a97f2  test    rax, rax
0x1800a97f5  jnz     short loc_1800A9862
0x1800a97f7  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800a97fb  xor     r8d, r8d; dwFlags
0x1800a97fe  xor     edx, edx; hFile
0x1800a9800  call    cs:__imp_LoadLibraryExA
0x1800a9806  mov     rbx, rax
0x1800a9809  test    rax, rax
0x1800a980c  jnz     short loc_1800A9862
0x1800a980e  call    cs:__imp_GetLastError
0x1800a9814  mov     [rbp+var_18], eax
0x1800a9817  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800a981e  test    rax, rax
0x1800a9821  jz      short loc_1800A9837
0x1800a9823  lea     rdx, [rbp+var_58]
0x1800a9827  lea     ecx, [rbx+3]
0x1800a982a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a982f  mov     rbx, rax
0x1800a9832  test    rax, rax
0x1800a9835  jnz     short loc_1800A9862
0x1800a9837  lea     rax, [rbp+var_58]
0x1800a983b  mov     [rbp+Arguments], rax
0x1800a983f  call    DloadReleaseSectionWriteAccess
0x1800a9844  xor     edx, edx; dwExceptionFlags
0x1800a9846  lea     r9, [rbp+Arguments]; lpArguments
0x1800a984a  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800a984f  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800a9853  call    cs:__imp_RaiseException
0x1800a9859  mov     rax, [rbp+var_20]
0x1800a985d  jmp     loc_1800A99C3
0x1800a9862  xor     eax, eax
0x1800a9864  lock cmpxchg [r14], rbx
0x1800a9869  mov     r14, rax
0x1800a986c  jnz     short loc_1800A98AE
0x1800a986e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a9872  jz      short loc_1800A98C4
0x1800a9874  cmp     dword ptr [rsi+18h], 0
0x1800a9878  jz      short loc_1800A98C4
0x1800a987a  call    cs:__imp_GetProcessHeap
0x1800a9880  mov     edx, 8; dwFlags
0x1800a9885  mov     rcx, rax; hHeap
0x1800a9888  lea     r8d, [rdx+8]; dwBytes
0x1800a988c  call    cs:__imp_HeapAlloc
0x1800a9892  test    rax, rax
0x1800a9895  jz      short loc_1800A98C4
0x1800a9897  mov     [rax+8], rsi
0x1800a989b  mov     rcx, cs:__puiHead
0x1800a98a2  mov     [rax], rcx
0x1800a98a5  mov     cs:__puiHead, rax
0x1800a98ac  jmp     short loc_1800A98C4
0x1800a98ae  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800a98b2  jz      short loc_1800A98BD
0x1800a98b4  mov     rcx, rbx; hLibModule
0x1800a98b7  call    cs:__imp_FreeLibrary
0x1800a98bd  cmp     rbx, r14
0x1800a98c0  cmovnz  rbx, r14
0x1800a98c4  mov     rax, cs:__pfnDliNotifyHook2
0x1800a98cb  mov     [rbp+var_28], rbx
0x1800a98cf  test    rax, rax
0x1800a98d2  jz      short loc_1800A98EC
0x1800a98d4  lea     rdx, [rbp+var_58]
0x1800a98d8  mov     ecx, 2
0x1800a98dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a98e2  mov     rdi, rax
0x1800a98e5  mov     rax, cs:__pfnDliNotifyHook2
0x1800a98ec  test    rdi, rdi
0x1800a98ef  jnz     loc_1800A9995
0x1800a98f5  cmp     [rsi+14h], edi
0x1800a98f8  jz      short loc_1800A9925
0x1800a98fa  cmp     [rsi+1Ch], edi
0x1800a98fd  jz      short loc_1800A9925
0x1800a98ff  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800a9903  cmp     dword ptr [rcx+rbx], 4550h
0x1800a990a  jnz     short loc_1800A9925
0x1800a990c  mov     edx, dword ptr [rbp+Arguments]
0x1800a990f  cmp     [rcx+rbx+8], edx
0x1800a9913  jnz     short loc_1800A9925
0x1800a9915  cmp     rbx, [rcx+rbx+30h]
0x1800a991a  jnz     short loc_1800A9925
0x1800a991c  mov     rdi, [r15+r13]
0x1800a9920  test    rdi, rdi
0x1800a9923  jnz     short loc_1800A9995
0x1800a9925  mov     rdx, [rbp+lpProcName]; lpProcName
0x1800a9929  mov     rcx, rbx; hModule
0x1800a992c  call    cs:__imp_GetProcAddress
0x1800a9932  mov     rdi, rax
0x1800a9935  test    rax, rax
0x1800a9938  jnz     short loc_1800A998E
0x1800a993a  call    cs:__imp_GetLastError
0x1800a9940  mov     [rbp+var_18], eax
0x1800a9943  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800a994a  test    rax, rax
0x1800a994d  jz      short loc_1800A9963
0x1800a994f  lea     rdx, [rbp+var_58]
0x1800a9953  lea     ecx, [rdi+4]
0x1800a9956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a995b  mov     rdi, rax
0x1800a995e  test    rax, rax
0x1800a9961  jnz     short loc_1800A998E
0x1800a9963  lea     rax, [rbp+var_58]
0x1800a9967  mov     [rbp+Arguments], rax
0x1800a996b  call    DloadReleaseSectionWriteAccess
0x1800a9970  xor     edx, edx; dwExceptionFlags
0x1800a9972  lea     r9, [rbp+Arguments]; lpArguments
0x1800a9976  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800a997b  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800a997f  call    cs:__imp_RaiseException
0x1800a9985  call    DloadAcquireSectionWriteAccess
0x1800a998a  mov     rdi, [rbp+var_20]
0x1800a998e  mov     rax, cs:__pfnDliNotifyHook2
0x1800a9995  mov     [r12], rdi
0x1800a9999  test    rax, rax
0x1800a999c  jz      short loc_1800A99BB
0x1800a999e  lea     rdx, [rbp+var_58]
0x1800a99a2  mov     [rbp+var_18], 0
0x1800a99a9  mov     ecx, 5
0x1800a99ae  mov     [rbp+var_28], rbx
0x1800a99b2  mov     [rbp+var_20], rdi
0x1800a99b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a99bb  call    DloadReleaseSectionWriteAccess
0x1800a99c0  mov     rax, rdi
0x1800a99c3  add     rsp, 78h
0x1800a99c7  pop     r15
0x1800a99c9  pop     r14
0x1800a99cb  pop     r13
0x1800a99cd  pop     r12
0x1800a99cf  pop     rdi
0x1800a99d0  pop     rsi
0x1800a99d1  pop     rbx
0x1800a99d2  pop     rbp
0x1800a99d3  retn
```
