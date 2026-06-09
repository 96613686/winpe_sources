# __delayLoadHelper2

- ea: `0x18001c650`
- end: `0x18001c98f`
- name: `__delayLoadHelper2`
- size: `831`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030cc5`
- `0x180030d50`
- `0x180030dff`
- `0x180031088`
- `0x180031170`

## callees

- `0x18001c650`
- `0x180096c90`
- `0x180096ea8`
- `0x180096f0c`
- `0x180097e20`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c7ca`
- `KERNEL32!GetLastError` at `0x18001c8e8`
- `KERNEL32!GetLastError` at `0x18001c7ca`
- `KERNEL32!GetLastError` at `0x18001c8e8`
- `KERNEL32!GetProcAddress` at `0x18001c8d4`
- `KERNEL32!GetProcAddress` at `0x18001c8d4`
- `KERNEL32!FreeLibrary` at `0x18001c855`
- `KERNEL32!FreeLibrary` at `0x18001c855`
- `KERNEL32!RaiseException` at `0x18001c6ff`
- `KERNEL32!RaiseException` at `0x18001c815`
- `KERNEL32!RaiseException` at `0x18001c933`
- `KERNEL32!RaiseException` at `0x18001c6ff`
- `KERNEL32!RaiseException` at `0x18001c815`
- `KERNEL32!RaiseException` at `0x18001c933`
- `KERNEL32!LoadLibraryExA` at `0x18001c7b6`
- `KERNEL32!LoadLibraryExA` at `0x18001c7b6`

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
  __int64 v13; // rcx
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v16; // r14
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  struct DelayLoadInfo v20; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+48h] BYREF

  memset(&v20, 0, 0x44u);
  ((void (*)(void))DloadAcquireSectionWriteAccess)();
  v5 = (unsigned __int64)&_ImageBase;
  v6 = (volatile signed __int64 *)((char *)&_ImageBase.unused + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v8 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v20.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v20.cb = 72;
  v20.pidd = a1;
  v20.ppfn = a2;
  v20.dlp.fImportByName = 0;
  memset(&v20.dlp.szProcName, 0, 28);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v20;
    DloadReleaseSectionWriteAccess(dwTimeStamp, &_ImageBase, v4);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v6;
  v12 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v13 = v12 + a1->rvaINT;
  v20.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase.unused + v13) >= 0LL;
  if ( v20.dlp.fImportByName )
  {
    v5 = (unsigned __int64)&_ImageBase.unused + 2;
    v20.dlp.szProcName = (char *)&_ImageBase.unused + *(unsigned int *)((char *)&_ImageBase.unused + v13) + 2;
  }
  else
  {
    v20.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase.unused + v13);
  }
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v20), v14 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(1, &v20)) == 0 )
      {
        Library = LoadLibraryExA(v20.szDll, 0, 0);
        if ( !Library )
        {
          v20.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v20)) == 0 )
          {
            Arguments = (ULONG_PTR)&v20;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v20.pfnCur;
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
      else if ( Library != (HMODULE)-1LL && a1->rvaUnloadIAT )
      {
        NewUnloadInfo(a1);
      }
      v14 = _pfnDliNotifyHook2;
    }
    v20.hmodCur = Library;
    if ( v14 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(2, &v20);
      v14 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v13 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v13) != 17744)
        || (v5 = (unsigned int)Arguments, *(_DWORD *)((char *)Library + v13 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + v13 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v8[v12]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v20.dlp.szProcName);
        if ( !ProcAddress )
        {
          v20.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v20)) == 0 )
          {
            Arguments = (ULONG_PTR)&v20;
            DloadReleaseSectionWriteAccess(v13, v5, v4);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            DloadAcquireSectionWriteAccess(v18, v17, v19);
            ProcAddress = v20.pfnCur;
          }
        }
        v14 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v14 )
  {
    v20.dwLastError = 0;
    v20.hmodCur = Library;
    v20.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(5, &v20);
  }
  DloadReleaseSectionWriteAccess(v13, v5, v4);
  return ProcAddress;
}

```

## disassembly

```asm
0x18001c650  push    rbp
0x18001c652  push    rbx
0x18001c653  push    rsi
0x18001c654  push    rdi
0x18001c655  push    r12
0x18001c657  push    r13
0x18001c659  push    r14
0x18001c65b  push    r15
0x18001c65d  mov     rbp, rsp
0x18001c660  sub     rsp, 78h
0x18001c664  xor     eax, eax
0x18001c666  mov     r12, rdx
0x18001c669  mov     rsi, rcx
0x18001c66c  mov     [rbp+var_54], eax
0x18001c66f  xor     edx, edx; Val
0x18001c671  lea     rcx, [rbp+var_58]; void *
0x18001c675  lea     r8d, [rax+44h]; Size
0x18001c679  call    memset
0x18001c67e  call    DloadAcquireSectionWriteAccess
0x18001c683  mov     eax, [rsi+4]
0x18001c686  lea     rdx, __ImageBase
0x18001c68d  mov     r14d, [rsi+8]
0x18001c691  add     rax, rdx
0x18001c694  mov     r15d, [rsi+14h]
0x18001c698  add     r14, rdx
0x18001c69b  mov     ecx, [rsi+1Ch]
0x18001c69e  add     r15, rdx
0x18001c6a1  mov     [rbp+lpLibFileName], rax
0x18001c6a5  mov     eax, [rsi]
0x18001c6a7  mov     dword ptr [rbp+Arguments], ecx
0x18001c6aa  mov     [rbp+var_58], 48h ; 'H'
0x18001c6b1  mov     [rbp+var_50], rsi
0x18001c6b5  mov     [rbp+var_48], r12
0x18001c6b9  mov     [rbp+var_38], 0
0x18001c6c0  mov     [rbp+lpProcName], 0
0x18001c6c8  mov     [rbp+var_28], 0
0x18001c6d0  mov     [rbp+var_20], 0
0x18001c6d8  mov     [rbp+var_18], 0
0x18001c6df  test    al, 1
0x18001c6e1  jnz     short loc_18001C712
0x18001c6e3  lea     rax, [rbp+var_58]
0x18001c6e7  mov     [rbp+Arguments], rax
0x18001c6eb  call    DloadReleaseSectionWriteAccess
0x18001c6f0  xor     edx, edx; dwExceptionFlags
0x18001c6f2  lea     r9, [rbp+Arguments]; lpArguments
0x18001c6f6  mov     ecx, 0C06D0057h; dwExceptionCode
0x18001c6fb  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001c6ff  call    cs:__imp_RaiseException
0x18001c706  nop     dword ptr [rax+rax+00h]
0x18001c70b  xor     eax, eax
0x18001c70d  jmp     loc_18001C97D
0x18001c712  mov     eax, [rsi+0Ch]
0x18001c715  mov     rcx, r12
0x18001c718  mov     rbx, [r14]
0x18001c71b  sub     rcx, rax
0x18001c71e  sub     rcx, rdx
0x18001c721  sar     rcx, 3
0x18001c725  mov     eax, ecx
0x18001c727  mov     ecx, [rsi+10h]
0x18001c72a  lea     r13, ds:0[rax*8]
0x18001c732  xor     eax, eax
0x18001c734  add     rcx, r13
0x18001c737  cmp     [rcx+rdx], rax
0x18001c73b  setnl   al
0x18001c73e  mov     [rbp+var_38], eax
0x18001c741  test    eax, eax
0x18001c743  jz      short loc_18001C758
0x18001c745  mov     eax, [rcx+rdx]
0x18001c748  lea     rdx, __ImageBase.unused+2
0x18001c74f  add     rax, rdx
0x18001c752  mov     [rbp+lpProcName], rax
0x18001c756  jmp     short loc_18001C75F
0x18001c758  movzx   eax, word ptr [rcx+rdx]
0x18001c75c  mov     dword ptr [rbp+lpProcName], eax
0x18001c75f  mov     rax, cs:__pfnDliNotifyHook2
0x18001c766  xor     edi, edi
0x18001c768  test    rax, rax
0x18001c76b  jz      short loc_18001C78B
0x18001c76d  lea     rdx, [rbp+var_58]
0x18001c771  xor     ecx, ecx
0x18001c773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c778  mov     rdi, rax
0x18001c77b  test    rax, rax
0x18001c77e  mov     rax, cs:__pfnDliNotifyHook2
0x18001c785  jnz     loc_18001C953
0x18001c78b  test    rbx, rbx
0x18001c78e  jnz     loc_18001C86F
0x18001c794  test    rax, rax
0x18001c797  jz      short loc_18001C7AD
0x18001c799  lea     rdx, [rbp+var_58]
0x18001c79d  lea     ecx, [rbx+1]
0x18001c7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7a5  mov     rbx, rax
0x18001c7a8  test    rax, rax
0x18001c7ab  jnz     short loc_18001C82A
0x18001c7ad  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001c7b1  xor     r8d, r8d; dwFlags
0x18001c7b4  xor     edx, edx; hFile
0x18001c7b6  call    cs:__imp_LoadLibraryExA
0x18001c7bd  nop     dword ptr [rax+rax+00h]
0x18001c7c2  mov     rbx, rax
0x18001c7c5  test    rax, rax
0x18001c7c8  jnz     short loc_18001C82A
0x18001c7ca  call    cs:__imp_GetLastError
0x18001c7d1  nop     dword ptr [rax+rax+00h]
0x18001c7d6  mov     [rbp+var_18], eax
0x18001c7d9  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001c7e0  test    rax, rax
0x18001c7e3  jz      short loc_18001C7F9
0x18001c7e5  lea     rdx, [rbp+var_58]
0x18001c7e9  lea     ecx, [rbx+3]
0x18001c7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7f1  mov     rbx, rax
0x18001c7f4  test    rax, rax
0x18001c7f7  jnz     short loc_18001C82A
0x18001c7f9  lea     rax, [rbp+var_58]
0x18001c7fd  mov     [rbp+Arguments], rax
0x18001c801  call    DloadReleaseSectionWriteAccess
0x18001c806  xor     edx, edx; dwExceptionFlags
0x18001c808  lea     r9, [rbp+Arguments]; lpArguments
0x18001c80c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18001c811  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001c815  call    cs:__imp_RaiseException
0x18001c81c  nop     dword ptr [rax+rax+00h]
0x18001c821  mov     rax, [rbp+var_20]
0x18001c825  jmp     loc_18001C97D
0x18001c82a  xor     eax, eax
0x18001c82c  lock cmpxchg [r14], rbx
0x18001c831  mov     r14, rax
0x18001c834  jnz     short loc_18001C84C
0x18001c836  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001c83a  jz      short loc_18001C868
0x18001c83c  cmp     dword ptr [rsi+18h], 0
0x18001c840  jz      short loc_18001C868
0x18001c842  mov     rcx, rsi
0x18001c845  call    NewUnloadInfo
0x18001c84a  jmp     short loc_18001C868
0x18001c84c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001c850  jz      short loc_18001C861
0x18001c852  mov     rcx, rbx; hLibModule
0x18001c855  call    cs:__imp_FreeLibrary
0x18001c85c  nop     dword ptr [rax+rax+00h]
0x18001c861  cmp     rbx, r14
0x18001c864  cmovnz  rbx, r14
0x18001c868  mov     rax, cs:__pfnDliNotifyHook2
0x18001c86f  mov     [rbp+var_28], rbx
0x18001c873  test    rax, rax
0x18001c876  jz      short loc_18001C890
0x18001c878  lea     rdx, [rbp+var_58]
0x18001c87c  mov     ecx, 2
0x18001c881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c886  mov     rdi, rax
0x18001c889  mov     rax, cs:__pfnDliNotifyHook2
0x18001c890  test    rdi, rdi
0x18001c893  jnz     loc_18001C94F
0x18001c899  cmp     [rsi+14h], edi
0x18001c89c  jz      short loc_18001C8CD
0x18001c89e  cmp     [rsi+1Ch], edi
0x18001c8a1  jz      short loc_18001C8CD
0x18001c8a3  movsxd  rcx, dword ptr [rbx+3Ch]
0x18001c8a7  cmp     dword ptr [rcx+rbx], 4550h
0x18001c8ae  jnz     short loc_18001C8CD
0x18001c8b0  mov     edx, dword ptr [rbp+Arguments]
0x18001c8b3  cmp     [rcx+rbx+8], edx
0x18001c8b7  jnz     short loc_18001C8CD
0x18001c8b9  cmp     rbx, [rcx+rbx+30h]
0x18001c8be  jnz     short loc_18001C8CD
0x18001c8c0  mov     rdi, [r15+r13]
0x18001c8c4  test    rdi, rdi
0x18001c8c7  jnz     loc_18001C94F
0x18001c8cd  mov     rdx, [rbp+lpProcName]; lpProcName
0x18001c8d1  mov     rcx, rbx; hModule
0x18001c8d4  call    cs:__imp_GetProcAddress
0x18001c8db  nop     dword ptr [rax+rax+00h]
0x18001c8e0  mov     rdi, rax
0x18001c8e3  test    rax, rax
0x18001c8e6  jnz     short loc_18001C948
0x18001c8e8  call    cs:__imp_GetLastError
0x18001c8ef  nop     dword ptr [rax+rax+00h]
0x18001c8f4  mov     [rbp+var_18], eax
0x18001c8f7  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001c8fe  test    rax, rax
0x18001c901  jz      short loc_18001C917
0x18001c903  lea     rdx, [rbp+var_58]
0x18001c907  lea     ecx, [rdi+4]
0x18001c90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c90f  mov     rdi, rax
0x18001c912  test    rax, rax
0x18001c915  jnz     short loc_18001C948
0x18001c917  lea     rax, [rbp+var_58]
0x18001c91b  mov     [rbp+Arguments], rax
0x18001c91f  call    DloadReleaseSectionWriteAccess
0x18001c924  xor     edx, edx; dwExceptionFlags
0x18001c926  lea     r9, [rbp+Arguments]; lpArguments
0x18001c92a  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18001c92f  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001c933  call    cs:__imp_RaiseException
0x18001c93a  nop     dword ptr [rax+rax+00h]
0x18001c93f  call    DloadAcquireSectionWriteAccess
0x18001c944  mov     rdi, [rbp+var_20]
0x18001c948  mov     rax, cs:__pfnDliNotifyHook2
0x18001c94f  mov     [r12], rdi
0x18001c953  test    rax, rax
0x18001c956  jz      short loc_18001C975
0x18001c958  lea     rdx, [rbp+var_58]
0x18001c95c  mov     [rbp+var_18], 0
0x18001c963  mov     ecx, 5
0x18001c968  mov     [rbp+var_28], rbx
0x18001c96c  mov     [rbp+var_20], rdi
0x18001c970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c975  call    DloadReleaseSectionWriteAccess
0x18001c97a  mov     rax, rdi
0x18001c97d  add     rsp, 78h
0x18001c981  pop     r15
0x18001c983  pop     r14
0x18001c985  pop     r13
0x18001c987  pop     r12
0x18001c989  pop     rdi
0x18001c98a  pop     rsi
0x18001c98b  pop     rbx
0x18001c98c  pop     rbp
0x18001c98d  retn
```
