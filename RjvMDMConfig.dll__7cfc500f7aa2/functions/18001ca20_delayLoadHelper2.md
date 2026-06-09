# __delayLoadHelper2

- ea: `0x18001ca20`
- end: `0x18001cd95`
- name: `__delayLoadHelper2`
- size: `885`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002b1a`
- `0x180002bc9`
- `0x180002ccc`

## callees

- `0x1800026d8`
- `0x18001c798`
- `0x18001c9b8`
- `0x18001ca20`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cb9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cacf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cbe5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cd39`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cacf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cbe5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cd39`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001cc5b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001cc5b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ccda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001ccda`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001cb86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001cb86`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cc2a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001cc2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cc12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001cc12`

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
    v5 = &word_180000002;
    v22.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + (_QWORD)v13);
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
0x18001ca20  push    rbp
0x18001ca22  push    rbx
0x18001ca23  push    rsi
0x18001ca24  push    rdi
0x18001ca25  push    r12
0x18001ca27  push    r13
0x18001ca29  push    r14
0x18001ca2b  push    r15
0x18001ca2d  mov     rbp, rsp
0x18001ca30  sub     rsp, 78h
0x18001ca34  xor     eax, eax
0x18001ca36  mov     r12, rdx
0x18001ca39  mov     rsi, rcx
0x18001ca3c  mov     [rbp+var_54], eax
0x18001ca3f  xor     edx, edx; Val
0x18001ca41  lea     rcx, [rbp+var_58]; void *
0x18001ca45  lea     r8d, [rax+44h]; Size
0x18001ca49  call    memset_0
0x18001ca4e  call    DloadAcquireSectionWriteAccess
0x18001ca53  mov     eax, [rsi+4]
0x18001ca56  lea     rdx, __ImageBase
0x18001ca5d  mov     r14d, [rsi+8]
0x18001ca61  add     rax, rdx
0x18001ca64  mov     r15d, [rsi+14h]
0x18001ca68  add     r14, rdx
0x18001ca6b  mov     ecx, [rsi+1Ch]
0x18001ca6e  add     r15, rdx
0x18001ca71  mov     [rbp+lpLibFileName], rax
0x18001ca75  mov     eax, [rsi]
0x18001ca77  mov     dword ptr [rbp+Arguments], ecx
0x18001ca7a  mov     [rbp+var_58], 48h ; 'H'
0x18001ca81  mov     [rbp+var_50], rsi
0x18001ca85  mov     [rbp+var_48], r12
0x18001ca89  mov     [rbp+var_38], 0
0x18001ca90  mov     [rbp+lpProcName], 0
0x18001ca98  mov     [rbp+var_28], 0
0x18001caa0  mov     [rbp+var_20], 0
0x18001caa8  mov     [rbp+var_18], 0
0x18001caaf  test    al, 1
0x18001cab1  jnz     short loc_18001CAE2
0x18001cab3  lea     rax, [rbp+var_58]
0x18001cab7  mov     [rbp+Arguments], rax
0x18001cabb  call    DloadReleaseSectionWriteAccess
0x18001cac0  xor     edx, edx; dwExceptionFlags
0x18001cac2  lea     r9, [rbp+Arguments]; lpArguments
0x18001cac6  mov     ecx, 0C06D0057h; dwExceptionCode
0x18001cacb  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001cacf  call    cs:__imp_RaiseException
0x18001cad6  nop     dword ptr [rax+rax+00h]
0x18001cadb  xor     eax, eax
0x18001cadd  jmp     loc_18001CD83
0x18001cae2  mov     eax, [rsi+0Ch]
0x18001cae5  mov     rcx, r12
0x18001cae8  mov     rbx, [r14]
0x18001caeb  sub     rcx, rax
0x18001caee  sub     rcx, rdx
0x18001caf1  sar     rcx, 3
0x18001caf5  mov     eax, ecx
0x18001caf7  mov     ecx, [rsi+10h]
0x18001cafa  lea     r13, ds:0[rax*8]
0x18001cb02  xor     eax, eax
0x18001cb04  add     rcx, r13
0x18001cb07  cmp     [rcx+rdx], rax
0x18001cb0b  setnl   al
0x18001cb0e  mov     [rbp+var_38], eax
0x18001cb11  test    eax, eax
0x18001cb13  jz      short loc_18001CB28
0x18001cb15  mov     eax, [rcx+rdx]
0x18001cb18  lea     rdx, word_180000002
0x18001cb1f  add     rax, rdx
0x18001cb22  mov     [rbp+lpProcName], rax
0x18001cb26  jmp     short loc_18001CB2F
0x18001cb28  movzx   eax, word ptr [rcx+rdx]
0x18001cb2c  mov     dword ptr [rbp+lpProcName], eax
0x18001cb2f  mov     rax, cs:__pfnDliNotifyHook2
0x18001cb36  xor     edi, edi
0x18001cb38  test    rax, rax
0x18001cb3b  jz      short loc_18001CB5B
0x18001cb3d  lea     rdx, [rbp+var_58]
0x18001cb41  xor     ecx, ecx
0x18001cb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb48  mov     rdi, rax
0x18001cb4b  test    rax, rax
0x18001cb4e  mov     rax, cs:__pfnDliNotifyHook2
0x18001cb55  jnz     loc_18001CD59
0x18001cb5b  test    rbx, rbx
0x18001cb5e  jnz     loc_18001CC75
0x18001cb64  test    rax, rax
0x18001cb67  jz      short loc_18001CB7D
0x18001cb69  lea     rdx, [rbp+var_58]
0x18001cb6d  lea     ecx, [rbx+1]
0x18001cb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb75  mov     rbx, rax
0x18001cb78  test    rax, rax
0x18001cb7b  jnz     short loc_18001CBFA
0x18001cb7d  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001cb81  xor     r8d, r8d; dwFlags
0x18001cb84  xor     edx, edx; hFile
0x18001cb86  call    cs:__imp_LoadLibraryExA
0x18001cb8d  nop     dword ptr [rax+rax+00h]
0x18001cb92  mov     rbx, rax
0x18001cb95  test    rax, rax
0x18001cb98  jnz     short loc_18001CBFA
0x18001cb9a  call    cs:__imp_GetLastError
0x18001cba1  nop     dword ptr [rax+rax+00h]
0x18001cba6  mov     [rbp+var_18], eax
0x18001cba9  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001cbb0  test    rax, rax
0x18001cbb3  jz      short loc_18001CBC9
0x18001cbb5  lea     rdx, [rbp+var_58]
0x18001cbb9  lea     ecx, [rbx+3]
0x18001cbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbc1  mov     rbx, rax
0x18001cbc4  test    rax, rax
0x18001cbc7  jnz     short loc_18001CBFA
0x18001cbc9  lea     rax, [rbp+var_58]
0x18001cbcd  mov     [rbp+Arguments], rax
0x18001cbd1  call    DloadReleaseSectionWriteAccess
0x18001cbd6  xor     edx, edx; dwExceptionFlags
0x18001cbd8  lea     r9, [rbp+Arguments]; lpArguments
0x18001cbdc  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18001cbe1  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001cbe5  call    cs:__imp_RaiseException
0x18001cbec  nop     dword ptr [rax+rax+00h]
0x18001cbf1  mov     rax, [rbp+var_20]
0x18001cbf5  jmp     loc_18001CD83
0x18001cbfa  xor     eax, eax
0x18001cbfc  lock cmpxchg [r14], rbx
0x18001cc01  mov     r14, rax
0x18001cc04  jnz     short loc_18001CC52
0x18001cc06  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001cc0a  jz      short loc_18001CC6E
0x18001cc0c  cmp     dword ptr [rsi+18h], 0
0x18001cc10  jz      short loc_18001CC6E
0x18001cc12  call    cs:__imp_GetProcessHeap
0x18001cc19  nop     dword ptr [rax+rax+00h]
0x18001cc1e  mov     edx, 8; dwFlags
0x18001cc23  mov     rcx, rax; hHeap
0x18001cc26  lea     r8d, [rdx+8]; dwBytes
0x18001cc2a  call    cs:__imp_HeapAlloc
0x18001cc31  nop     dword ptr [rax+rax+00h]
0x18001cc36  test    rax, rax
0x18001cc39  jz      short loc_18001CC6E
0x18001cc3b  mov     [rax+8], rsi
0x18001cc3f  mov     rcx, cs:__puiHead
0x18001cc46  mov     [rax], rcx
0x18001cc49  mov     cs:__puiHead, rax
0x18001cc50  jmp     short loc_18001CC6E
0x18001cc52  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001cc56  jz      short loc_18001CC67
0x18001cc58  mov     rcx, rbx; hLibModule
0x18001cc5b  call    cs:__imp_FreeLibrary
0x18001cc62  nop     dword ptr [rax+rax+00h]
0x18001cc67  cmp     rbx, r14
0x18001cc6a  cmovnz  rbx, r14
0x18001cc6e  mov     rax, cs:__pfnDliNotifyHook2
0x18001cc75  mov     [rbp+var_28], rbx
0x18001cc79  test    rax, rax
0x18001cc7c  jz      short loc_18001CC96
0x18001cc7e  lea     rdx, [rbp+var_58]
0x18001cc82  mov     ecx, 2
0x18001cc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc8c  mov     rdi, rax
0x18001cc8f  mov     rax, cs:__pfnDliNotifyHook2
0x18001cc96  test    rdi, rdi
0x18001cc99  jnz     loc_18001CD55
0x18001cc9f  cmp     [rsi+14h], edi
0x18001cca2  jz      short loc_18001CCD3
0x18001cca4  cmp     [rsi+1Ch], edi
0x18001cca7  jz      short loc_18001CCD3
0x18001cca9  movsxd  rcx, dword ptr [rbx+3Ch]
0x18001ccad  cmp     dword ptr [rcx+rbx], 4550h
0x18001ccb4  jnz     short loc_18001CCD3
0x18001ccb6  mov     edx, dword ptr [rbp+Arguments]
0x18001ccb9  cmp     [rcx+rbx+8], edx
0x18001ccbd  jnz     short loc_18001CCD3
0x18001ccbf  cmp     rbx, [rcx+rbx+30h]
0x18001ccc4  jnz     short loc_18001CCD3
0x18001ccc6  mov     rdi, [r15+r13]
0x18001ccca  test    rdi, rdi
0x18001cccd  jnz     loc_18001CD55
0x18001ccd3  mov     rdx, [rbp+lpProcName]; lpProcName
0x18001ccd7  mov     rcx, rbx; hModule
0x18001ccda  call    cs:__imp_GetProcAddress
0x18001cce1  nop     dword ptr [rax+rax+00h]
0x18001cce6  mov     rdi, rax
0x18001cce9  test    rax, rax
0x18001ccec  jnz     short loc_18001CD4E
0x18001ccee  call    cs:__imp_GetLastError
0x18001ccf5  nop     dword ptr [rax+rax+00h]
0x18001ccfa  mov     [rbp+var_18], eax
0x18001ccfd  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001cd04  test    rax, rax
0x18001cd07  jz      short loc_18001CD1D
0x18001cd09  lea     rdx, [rbp+var_58]
0x18001cd0d  lea     ecx, [rdi+4]
0x18001cd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd15  mov     rdi, rax
0x18001cd18  test    rax, rax
0x18001cd1b  jnz     short loc_18001CD4E
0x18001cd1d  lea     rax, [rbp+var_58]
0x18001cd21  mov     [rbp+Arguments], rax
0x18001cd25  call    DloadReleaseSectionWriteAccess
0x18001cd2a  xor     edx, edx; dwExceptionFlags
0x18001cd2c  lea     r9, [rbp+Arguments]; lpArguments
0x18001cd30  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18001cd35  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001cd39  call    cs:__imp_RaiseException
0x18001cd40  nop     dword ptr [rax+rax+00h]
0x18001cd45  call    DloadAcquireSectionWriteAccess
0x18001cd4a  mov     rdi, [rbp+var_20]
0x18001cd4e  mov     rax, cs:__pfnDliNotifyHook2
0x18001cd55  mov     [r12], rdi
0x18001cd59  test    rax, rax
0x18001cd5c  jz      short loc_18001CD7B
0x18001cd5e  lea     rdx, [rbp+var_58]
0x18001cd62  mov     [rbp+var_18], 0
0x18001cd69  mov     ecx, 5
0x18001cd6e  mov     [rbp+var_28], rbx
0x18001cd72  mov     [rbp+var_20], rdi
0x18001cd76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd7b  call    DloadReleaseSectionWriteAccess
0x18001cd80  mov     rax, rdi
0x18001cd83  add     rsp, 78h
0x18001cd87  pop     r15
0x18001cd89  pop     r14
0x18001cd8b  pop     r13
0x18001cd8d  pop     r12
0x18001cd8f  pop     rdi
0x18001cd90  pop     rsi
0x18001cd91  pop     rbx
0x18001cd92  pop     rbp
0x18001cd93  retn
```
