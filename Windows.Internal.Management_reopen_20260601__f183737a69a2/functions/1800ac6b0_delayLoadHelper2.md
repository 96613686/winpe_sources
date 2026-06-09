# __delayLoadHelper2

- ea: `0x1800ac6b0`
- end: `0x1800aca25`
- name: `__delayLoadHelper2`
- size: `885`
- prototype: ``
- caller_count: `21`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005b3d`
- `0x180005bda`
- `0x180005cd1`
- `0x180005e58`
- `0x180005f07`
- `0x180005f92`
- `0x18000601d`
- `0x180006146`
- `0x1800061d1`
- `0x180006292`
- `0x18000631d`
- `0x1800063cc`
- `0x180006469`
- `0x180006506`
- `0x1800065b5`
- `0x180006640`
- `0x1800066cb`
- `0x180006768`
- `0x1800067f3`
- `0x180007cb1`
- `0x180007d4e`

## callees

- `0x180005a74`
- `0x1800ac428`
- `0x1800ac648`
- `0x1800ac6b0`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac96a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ac96a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ac8eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800ac8eb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800ac816`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800ac816`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ac8ba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ac8ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ac8a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ac8a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac82a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac82a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac97e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac75f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac875`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac9c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac75f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac875`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800ac9c9`

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
0x1800ac6b0  push    rbp
0x1800ac6b2  push    rbx
0x1800ac6b3  push    rsi
0x1800ac6b4  push    rdi
0x1800ac6b5  push    r12
0x1800ac6b7  push    r13
0x1800ac6b9  push    r14
0x1800ac6bb  push    r15
0x1800ac6bd  mov     rbp, rsp
0x1800ac6c0  sub     rsp, 78h
0x1800ac6c4  xor     eax, eax
0x1800ac6c6  mov     r12, rdx
0x1800ac6c9  mov     rsi, rcx
0x1800ac6cc  mov     [rbp+var_54], eax
0x1800ac6cf  xor     edx, edx; Val
0x1800ac6d1  lea     rcx, [rbp+var_58]; void *
0x1800ac6d5  lea     r8d, [rax+44h]; Size
0x1800ac6d9  call    memset_0
0x1800ac6de  call    DloadAcquireSectionWriteAccess
0x1800ac6e3  mov     eax, [rsi+4]
0x1800ac6e6  lea     rdx, __ImageBase
0x1800ac6ed  mov     r14d, [rsi+8]
0x1800ac6f1  add     rax, rdx
0x1800ac6f4  mov     r15d, [rsi+14h]
0x1800ac6f8  add     r14, rdx
0x1800ac6fb  mov     ecx, [rsi+1Ch]
0x1800ac6fe  add     r15, rdx
0x1800ac701  mov     [rbp+lpLibFileName], rax
0x1800ac705  mov     eax, [rsi]
0x1800ac707  mov     dword ptr [rbp+Arguments], ecx
0x1800ac70a  mov     [rbp+var_58], 48h ; 'H'
0x1800ac711  mov     [rbp+var_50], rsi
0x1800ac715  mov     [rbp+var_48], r12
0x1800ac719  mov     [rbp+var_38], 0
0x1800ac720  mov     [rbp+lpProcName], 0
0x1800ac728  mov     [rbp+var_28], 0
0x1800ac730  mov     [rbp+var_20], 0
0x1800ac738  mov     [rbp+var_18], 0
0x1800ac73f  test    al, 1
0x1800ac741  jnz     short loc_1800AC772
0x1800ac743  lea     rax, [rbp+var_58]
0x1800ac747  mov     [rbp+Arguments], rax
0x1800ac74b  call    DloadReleaseSectionWriteAccess
0x1800ac750  xor     edx, edx; dwExceptionFlags
0x1800ac752  lea     r9, [rbp+Arguments]; lpArguments
0x1800ac756  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800ac75b  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800ac75f  call    cs:__imp_RaiseException
0x1800ac766  nop     dword ptr [rax+rax+00h]
0x1800ac76b  xor     eax, eax
0x1800ac76d  jmp     loc_1800ACA13
0x1800ac772  mov     eax, [rsi+0Ch]
0x1800ac775  mov     rcx, r12
0x1800ac778  mov     rbx, [r14]
0x1800ac77b  sub     rcx, rax
0x1800ac77e  sub     rcx, rdx
0x1800ac781  sar     rcx, 3
0x1800ac785  mov     eax, ecx
0x1800ac787  mov     ecx, [rsi+10h]
0x1800ac78a  lea     r13, ds:0[rax*8]
0x1800ac792  xor     eax, eax
0x1800ac794  add     rcx, r13
0x1800ac797  cmp     [rcx+rdx], rax
0x1800ac79b  setnl   al
0x1800ac79e  mov     [rbp+var_38], eax
0x1800ac7a1  test    eax, eax
0x1800ac7a3  jz      short loc_1800AC7B8
0x1800ac7a5  mov     eax, [rcx+rdx]
0x1800ac7a8  lea     rdx, __ImageBase.unused+2
0x1800ac7af  add     rax, rdx
0x1800ac7b2  mov     [rbp+lpProcName], rax
0x1800ac7b6  jmp     short loc_1800AC7BF
0x1800ac7b8  movzx   eax, word ptr [rcx+rdx]
0x1800ac7bc  mov     dword ptr [rbp+lpProcName], eax
0x1800ac7bf  mov     rax, cs:__pfnDliNotifyHook2
0x1800ac7c6  xor     edi, edi
0x1800ac7c8  test    rax, rax
0x1800ac7cb  jz      short loc_1800AC7EB
0x1800ac7cd  lea     rdx, [rbp+var_58]
0x1800ac7d1  xor     ecx, ecx
0x1800ac7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac7d8  mov     rdi, rax
0x1800ac7db  test    rax, rax
0x1800ac7de  mov     rax, cs:__pfnDliNotifyHook2
0x1800ac7e5  jnz     loc_1800AC9E9
0x1800ac7eb  test    rbx, rbx
0x1800ac7ee  jnz     loc_1800AC905
0x1800ac7f4  test    rax, rax
0x1800ac7f7  jz      short loc_1800AC80D
0x1800ac7f9  lea     rdx, [rbp+var_58]
0x1800ac7fd  lea     ecx, [rbx+1]
0x1800ac800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac805  mov     rbx, rax
0x1800ac808  test    rax, rax
0x1800ac80b  jnz     short loc_1800AC88A
0x1800ac80d  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800ac811  xor     r8d, r8d; dwFlags
0x1800ac814  xor     edx, edx; hFile
0x1800ac816  call    cs:__imp_LoadLibraryExA
0x1800ac81d  nop     dword ptr [rax+rax+00h]
0x1800ac822  mov     rbx, rax
0x1800ac825  test    rax, rax
0x1800ac828  jnz     short loc_1800AC88A
0x1800ac82a  call    cs:__imp_GetLastError
0x1800ac831  nop     dword ptr [rax+rax+00h]
0x1800ac836  mov     [rbp+var_18], eax
0x1800ac839  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800ac840  test    rax, rax
0x1800ac843  jz      short loc_1800AC859
0x1800ac845  lea     rdx, [rbp+var_58]
0x1800ac849  lea     ecx, [rbx+3]
0x1800ac84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac851  mov     rbx, rax
0x1800ac854  test    rax, rax
0x1800ac857  jnz     short loc_1800AC88A
0x1800ac859  lea     rax, [rbp+var_58]
0x1800ac85d  mov     [rbp+Arguments], rax
0x1800ac861  call    DloadReleaseSectionWriteAccess
0x1800ac866  xor     edx, edx; dwExceptionFlags
0x1800ac868  lea     r9, [rbp+Arguments]; lpArguments
0x1800ac86c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800ac871  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800ac875  call    cs:__imp_RaiseException
0x1800ac87c  nop     dword ptr [rax+rax+00h]
0x1800ac881  mov     rax, [rbp+var_20]
0x1800ac885  jmp     loc_1800ACA13
0x1800ac88a  xor     eax, eax
0x1800ac88c  lock cmpxchg [r14], rbx
0x1800ac891  mov     r14, rax
0x1800ac894  jnz     short loc_1800AC8E2
0x1800ac896  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800ac89a  jz      short loc_1800AC8FE
0x1800ac89c  cmp     dword ptr [rsi+18h], 0
0x1800ac8a0  jz      short loc_1800AC8FE
0x1800ac8a2  call    cs:__imp_GetProcessHeap
0x1800ac8a9  nop     dword ptr [rax+rax+00h]
0x1800ac8ae  mov     edx, 8; dwFlags
0x1800ac8b3  mov     rcx, rax; hHeap
0x1800ac8b6  lea     r8d, [rdx+8]; dwBytes
0x1800ac8ba  call    cs:__imp_HeapAlloc
0x1800ac8c1  nop     dword ptr [rax+rax+00h]
0x1800ac8c6  test    rax, rax
0x1800ac8c9  jz      short loc_1800AC8FE
0x1800ac8cb  mov     [rax+8], rsi
0x1800ac8cf  mov     rcx, cs:__puiHead
0x1800ac8d6  mov     [rax], rcx
0x1800ac8d9  mov     cs:__puiHead, rax
0x1800ac8e0  jmp     short loc_1800AC8FE
0x1800ac8e2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800ac8e6  jz      short loc_1800AC8F7
0x1800ac8e8  mov     rcx, rbx; hLibModule
0x1800ac8eb  call    cs:__imp_FreeLibrary
0x1800ac8f2  nop     dword ptr [rax+rax+00h]
0x1800ac8f7  cmp     rbx, r14
0x1800ac8fa  cmovnz  rbx, r14
0x1800ac8fe  mov     rax, cs:__pfnDliNotifyHook2
0x1800ac905  mov     [rbp+var_28], rbx
0x1800ac909  test    rax, rax
0x1800ac90c  jz      short loc_1800AC926
0x1800ac90e  lea     rdx, [rbp+var_58]
0x1800ac912  mov     ecx, 2
0x1800ac917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac91c  mov     rdi, rax
0x1800ac91f  mov     rax, cs:__pfnDliNotifyHook2
0x1800ac926  test    rdi, rdi
0x1800ac929  jnz     loc_1800AC9E5
0x1800ac92f  cmp     [rsi+14h], edi
0x1800ac932  jz      short loc_1800AC963
0x1800ac934  cmp     [rsi+1Ch], edi
0x1800ac937  jz      short loc_1800AC963
0x1800ac939  movsxd  rcx, dword ptr [rbx+3Ch]
0x1800ac93d  cmp     dword ptr [rcx+rbx], 4550h
0x1800ac944  jnz     short loc_1800AC963
0x1800ac946  mov     edx, dword ptr [rbp+Arguments]
0x1800ac949  cmp     [rcx+rbx+8], edx
0x1800ac94d  jnz     short loc_1800AC963
0x1800ac94f  cmp     rbx, [rcx+rbx+30h]
0x1800ac954  jnz     short loc_1800AC963
0x1800ac956  mov     rdi, [r15+r13]
0x1800ac95a  test    rdi, rdi
0x1800ac95d  jnz     loc_1800AC9E5
0x1800ac963  mov     rdx, [rbp+lpProcName]; lpProcName
0x1800ac967  mov     rcx, rbx; hModule
0x1800ac96a  call    cs:__imp_GetProcAddress
0x1800ac971  nop     dword ptr [rax+rax+00h]
0x1800ac976  mov     rdi, rax
0x1800ac979  test    rax, rax
0x1800ac97c  jnz     short loc_1800AC9DE
0x1800ac97e  call    cs:__imp_GetLastError
0x1800ac985  nop     dword ptr [rax+rax+00h]
0x1800ac98a  mov     [rbp+var_18], eax
0x1800ac98d  mov     rax, cs:__pfnDefaultDliFailureHook2
0x1800ac994  test    rax, rax
0x1800ac997  jz      short loc_1800AC9AD
0x1800ac999  lea     rdx, [rbp+var_58]
0x1800ac99d  lea     ecx, [rdi+4]
0x1800ac9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac9a5  mov     rdi, rax
0x1800ac9a8  test    rax, rax
0x1800ac9ab  jnz     short loc_1800AC9DE
0x1800ac9ad  lea     rax, [rbp+var_58]
0x1800ac9b1  mov     [rbp+Arguments], rax
0x1800ac9b5  call    DloadReleaseSectionWriteAccess
0x1800ac9ba  xor     edx, edx; dwExceptionFlags
0x1800ac9bc  lea     r9, [rbp+Arguments]; lpArguments
0x1800ac9c0  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800ac9c5  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800ac9c9  call    cs:__imp_RaiseException
0x1800ac9d0  nop     dword ptr [rax+rax+00h]
0x1800ac9d5  call    DloadAcquireSectionWriteAccess
0x1800ac9da  mov     rdi, [rbp+var_20]
0x1800ac9de  mov     rax, cs:__pfnDliNotifyHook2
0x1800ac9e5  mov     [r12], rdi
0x1800ac9e9  test    rax, rax
0x1800ac9ec  jz      short loc_1800ACA0B
0x1800ac9ee  lea     rdx, [rbp+var_58]
0x1800ac9f2  mov     [rbp+var_18], 0
0x1800ac9f9  mov     ecx, 5
0x1800ac9fe  mov     [rbp+var_28], rbx
0x1800aca02  mov     [rbp+var_20], rdi
0x1800aca06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aca0b  call    DloadReleaseSectionWriteAccess
0x1800aca10  mov     rax, rdi
0x1800aca13  add     rsp, 78h
0x1800aca17  pop     r15
0x1800aca19  pop     r14
0x1800aca1b  pop     r13
0x1800aca1d  pop     r12
0x1800aca1f  pop     rdi
0x1800aca20  pop     rsi
0x1800aca21  pop     rbx
0x1800aca22  pop     rbp
0x1800aca23  retn
```
