# __delayLoadHelper2

- ea: `0x18000af70`
- end: `0x18000b2c9`
- name: `__delayLoadHelper2`
- size: `857`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800136e0`

## callees

- `0x18000af70`
- `0x18000b2d0`
- `0x18000b328`
- `0x180022634`
- `0x180022792`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b0b8`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000b0b8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000b1cd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18000b1cd`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18000b140`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18000b140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b14e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b14e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b248`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b0ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b193`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b293`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b0ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b193`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b293`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  __int16 *v6; // rdx
  volatile signed __int64 *v7; // r14
  __int64 dwTimeStamp; // rcx
  char *v9; // r15
  DWORD grAttrs; // eax
  HMODULE Library; // rbx
  __int64 v12; // r13
  __int64 v13; // rcx
  PfnDliHook v14; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  signed __int64 v17; // r14
  struct DelayLoadInfo v18; // [rsp+20h] [rbp-58h] BYREF
  ULONG_PTR Arguments; // [rsp+C0h] [rbp+48h] BYREF

  *(&v18.cb + 1) = 0;
  memset_0(&v18, 0, 0x44u);
  DloadAcquireSectionWriteAccess();
  v6 = &_ImageBase;
  v7 = (volatile signed __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  dwTimeStamp = a1->dwTimeStamp;
  v9 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v18.szDll = (char *)&_ImageBase + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = dwTimeStamp;
  v18.cb = 72;
  v18.pidd = a1;
  v18.ppfn = a2;
  v18.dlp.fImportByName = 0;
  memset(&v18.dlp.szProcName, 0, 28);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v18;
    DloadReleaseSectionWriteAccess(dwTimeStamp, &_ImageBase, v4, v5, *(_QWORD *)&v18.cb, v18.pidd, v18.ppfn);
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v7;
  v12 = 8LL * (unsigned int)(((char *)a2 - a1->rvaIAT - (char *)&_ImageBase) >> 3);
  v13 = v12 + a1->rvaINT;
  v18.dlp.fImportByName = *(_QWORD *)((char *)&_ImageBase + v13) >= 0LL;
  if ( v18.dlp.fImportByName )
  {
    v6 = &word_180000002;
    v18.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v13);
  }
  else
  {
    v18.dlp.dwOrdinal = *(unsigned __int16 *)((char *)&_ImageBase + v13);
  }
  v14 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( !_pfnDliNotifyHook2 || (ProcAddress = _pfnDliNotifyHook2(0, &v18), v14 = _pfnDliNotifyHook2, !ProcAddress) )
  {
    if ( !Library )
    {
      if ( !v14 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(1, &v18)) == 0 )
      {
        Library = LoadLibraryExA(v18.szDll, 0, 0);
        if ( !Library )
        {
          v18.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2 || (Library = (HMODULE)_pfnDefaultDliFailureHook2(3, &v18)) == 0 )
          {
            Arguments = (ULONG_PTR)&v18;
            DloadReleaseSectionWriteAccess(v13, v6, v4, v5, *(_QWORD *)&v18.cb, v18.pidd, v18.ppfn);
            RaiseException(0xC06D007E, 0, 1u, &Arguments);
            return v18.pfnCur;
          }
        }
      }
      v17 = _InterlockedCompareExchange64(v7, (signed __int64)Library, 0);
      if ( v17 )
      {
        if ( Library != (HMODULE)-1LL )
          FreeLibrary(Library);
        if ( Library != (HMODULE)v17 )
          Library = (HMODULE)v17;
      }
      else if ( Library != (HMODULE)-1LL && a1->rvaUnloadIAT )
      {
        NewUnloadInfo(a1);
      }
      v14 = _pfnDliNotifyHook2;
    }
    v18.hmodCur = Library;
    if ( v14 )
    {
      ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(2, &v18);
      v14 = _pfnDliNotifyHook2;
    }
    if ( !ProcAddress )
    {
      if ( !a1->rvaBoundIAT
        || !a1->dwTimeStamp
        || (v13 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v13) != 17744)
        || (v6 = (__int16 *)(unsigned int)Arguments, *(_DWORD *)((char *)Library + v13 + 8) != (_DWORD)Arguments)
        || Library != *(HMODULE *)((char *)Library + v13 + 48)
        || (ProcAddress = *(INT_PTR (__stdcall **)())&v9[v12]) == 0 )
      {
        ProcAddress = GetProcAddress(Library, v18.dlp.szProcName);
        if ( !ProcAddress )
        {
          v18.dwLastError = GetLastError();
          if ( !_pfnDefaultDliFailureHook2
            || (ProcAddress = (INT_PTR (__stdcall *)())_pfnDefaultDliFailureHook2(4, &v18)) == 0 )
          {
            Arguments = (ULONG_PTR)&v18;
            DloadReleaseSectionWriteAccess(v13, v6, v4, v5, *(_QWORD *)&v18.cb, v18.pidd, v18.ppfn);
            RaiseException(0xC06D007F, 0, 1u, &Arguments);
            DloadAcquireSectionWriteAccess();
            ProcAddress = v18.pfnCur;
          }
        }
        v14 = _pfnDliNotifyHook2;
      }
    }
    *a2 = ProcAddress;
  }
  if ( v14 )
  {
    v18.dwLastError = 0;
    v18.hmodCur = Library;
    v18.pfnCur = ProcAddress;
    ((void (__fastcall *)(__int64, struct DelayLoadInfo *))v14)(5, &v18);
  }
  DloadReleaseSectionWriteAccess(v13, v6, v4, v5, *(_QWORD *)&v18.cb, v18.pidd, v18.ppfn);
  return ProcAddress;
}

```

## disassembly

```asm
0x18000af70  push    rbp
0x18000af72  push    rbx
0x18000af73  push    rsi
0x18000af74  push    rdi
0x18000af75  push    r12
0x18000af77  push    r13
0x18000af79  push    r14
0x18000af7b  push    r15
0x18000af7d  mov     rbp, rsp
0x18000af80  sub     rsp, 78h
0x18000af84  xor     eax, eax
0x18000af86  mov     r12, rdx
0x18000af89  mov     rsi, rcx
0x18000af8c  mov     [rbp+var_54], eax
0x18000af8f  xor     edx, edx; Val
0x18000af91  lea     rcx, [rbp+var_58]; void *
0x18000af95  lea     r8d, [rax+44h]; Size
0x18000af99  call    memset_0
0x18000af9e  call    DloadAcquireSectionWriteAccess
0x18000afa3  mov     eax, [rsi+4]
0x18000afa6  lea     rdx, __ImageBase
0x18000afad  mov     r14d, [rsi+8]
0x18000afb1  add     rax, rdx
0x18000afb4  mov     r15d, [rsi+14h]
0x18000afb8  add     r14, rdx
0x18000afbb  mov     ecx, [rsi+1Ch]
0x18000afbe  add     r15, rdx
0x18000afc1  mov     [rbp+lpLibFileName], rax
0x18000afc5  mov     eax, [rsi]
0x18000afc7  mov     dword ptr [rbp+Arguments], ecx
0x18000afca  mov     [rbp+var_58], 48h ; 'H'
0x18000afd1  mov     [rbp+var_50], rsi
0x18000afd5  mov     [rbp+var_48], r12
0x18000afd9  mov     [rbp+var_38], 0
0x18000afe0  mov     [rbp+lpProcName], 0
0x18000afe8  mov     [rbp+var_28], 0
0x18000aff0  mov     [rbp+var_20], 0
0x18000aff8  mov     [rbp+var_18], 0
0x18000afff  test    al, 1
0x18000b001  jz      loc_18000B0D3
0x18000b007  mov     eax, [rsi+0Ch]
0x18000b00a  mov     rcx, r12
0x18000b00d  mov     rbx, [r14]
0x18000b010  sub     rcx, rax
0x18000b013  sub     rcx, rdx
0x18000b016  sar     rcx, 3
0x18000b01a  mov     eax, ecx
0x18000b01c  mov     ecx, [rsi+10h]
0x18000b01f  lea     r13, ds:0[rax*8]
0x18000b027  xor     eax, eax
0x18000b029  add     rcx, r13
0x18000b02c  cmp     [rcx+rdx], rax
0x18000b030  setnl   al
0x18000b033  mov     [rbp+var_38], eax
0x18000b036  test    eax, eax
0x18000b038  jz      short loc_18000B09E
0x18000b03a  mov     eax, [rcx+rdx]
0x18000b03d  lea     rdx, word_180000002
0x18000b044  add     rax, rdx
0x18000b047  mov     [rbp+lpProcName], rax
0x18000b04b  mov     rax, cs:__pfnDliNotifyHook2
0x18000b052  xor     edi, edi
0x18000b054  test    rax, rax
0x18000b057  jnz     loc_18000B0F9
0x18000b05d  test    rbx, rbx
0x18000b060  jz      loc_18000B11C
0x18000b066  mov     [rbp+var_28], rbx
0x18000b06a  test    rax, rax
0x18000b06d  jnz     loc_18000B1E6
0x18000b073  test    rdi, rdi
0x18000b076  jz      short loc_18000B0A7
0x18000b078  mov     [r12], rdi
0x18000b07c  test    rax, rax
0x18000b07f  jnz     loc_18000B2A7
0x18000b085  call    DloadReleaseSectionWriteAccess
0x18000b08a  mov     rax, rdi
0x18000b08d  add     rsp, 78h
0x18000b091  pop     r15
0x18000b093  pop     r14
0x18000b095  pop     r13
0x18000b097  pop     r12
0x18000b099  pop     rdi
0x18000b09a  pop     rsi
0x18000b09b  pop     rbx
0x18000b09c  pop     rbp
0x18000b09d  retn
0x18000b09e  movzx   eax, word ptr [rcx+rdx]
0x18000b0a2  mov     dword ptr [rbp+lpProcName], eax
0x18000b0a5  jmp     short loc_18000B04B
0x18000b0a7  cmp     dword ptr [rsi+14h], 0
0x18000b0ab  jnz     loc_18000B203
0x18000b0b1  mov     rdx, [rbp+lpProcName]; lpProcName
0x18000b0b5  mov     rcx, rbx; hModule
0x18000b0b8  call    cs:__imp_GetProcAddress
0x18000b0be  mov     rdi, rax
0x18000b0c1  test    rax, rax
0x18000b0c4  jz      loc_18000B248
0x18000b0ca  mov     rax, cs:__pfnDliNotifyHook2
0x18000b0d1  jmp     short loc_18000B078
0x18000b0d3  lea     rax, [rbp+var_58]
0x18000b0d7  mov     [rbp+Arguments], rax
0x18000b0db  call    DloadReleaseSectionWriteAccess
0x18000b0e0  xor     edx, edx; dwExceptionFlags
0x18000b0e2  lea     r9, [rbp+Arguments]; lpArguments
0x18000b0e6  mov     ecx, 0C06D0057h; dwExceptionCode
0x18000b0eb  lea     r8d, [rdx+1]; nNumberOfArguments
0x18000b0ef  call    cs:__imp_RaiseException
0x18000b0f5  xor     eax, eax
0x18000b0f7  jmp     short loc_18000B08D
0x18000b0f9  lea     rdx, [rbp+var_58]
0x18000b0fd  xor     ecx, ecx
0x18000b0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b104  mov     rdi, rax
0x18000b107  test    rax, rax
0x18000b10a  mov     rax, cs:__pfnDliNotifyHook2
0x18000b111  jnz     loc_18000B07C
0x18000b117  jmp     loc_18000B05D
0x18000b11c  test    rax, rax
0x18000b11f  jz      short loc_18000B137
0x18000b121  lea     rdx, [rbp+var_58]
0x18000b125  mov     ecx, 1
0x18000b12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b12f  mov     rbx, rax
0x18000b132  test    rax, rax
0x18000b135  jnz     short loc_18000B1A2
0x18000b137  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000b13b  xor     r8d, r8d; dwFlags
0x18000b13e  xor     edx, edx; hFile
0x18000b140  call    cs:__imp_LoadLibraryExA
0x18000b146  mov     rbx, rax
0x18000b149  test    rax, rax
0x18000b14c  jnz     short loc_18000B1A2
0x18000b14e  call    cs:__imp_GetLastError
0x18000b154  mov     [rbp+var_18], eax
0x18000b157  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18000b15e  test    rax, rax
0x18000b161  jz      short loc_18000B177
0x18000b163  lea     rdx, [rbp+var_58]
0x18000b167  lea     ecx, [rbx+3]
0x18000b16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b16f  mov     rbx, rax
0x18000b172  test    rax, rax
0x18000b175  jnz     short loc_18000B1A2
0x18000b177  lea     rax, [rbp+var_58]
0x18000b17b  mov     [rbp+Arguments], rax
0x18000b17f  call    DloadReleaseSectionWriteAccess
0x18000b184  xor     edx, edx; dwExceptionFlags
0x18000b186  lea     r9, [rbp+Arguments]; lpArguments
0x18000b18a  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18000b18f  lea     r8d, [rdx+1]; nNumberOfArguments
0x18000b193  call    cs:__imp_RaiseException
0x18000b199  mov     rax, [rbp+var_20]
0x18000b19d  jmp     loc_18000B08D
0x18000b1a2  xor     eax, eax
0x18000b1a4  lock cmpxchg [r14], rbx
0x18000b1a9  mov     r14, rax
0x18000b1ac  jnz     short loc_18000B1C4
0x18000b1ae  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b1b2  jz      short loc_18000B1DA
0x18000b1b4  cmp     dword ptr [rsi+18h], 0
0x18000b1b8  jz      short loc_18000B1DA
0x18000b1ba  mov     rcx, rsi
0x18000b1bd  call    NewUnloadInfo
0x18000b1c2  jmp     short loc_18000B1DA
0x18000b1c4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b1c8  jz      short loc_18000B1D3
0x18000b1ca  mov     rcx, rbx; hLibModule
0x18000b1cd  call    cs:__imp_FreeLibrary
0x18000b1d3  cmp     rbx, r14
0x18000b1d6  cmovnz  rbx, r14
0x18000b1da  mov     rax, cs:__pfnDliNotifyHook2
0x18000b1e1  jmp     loc_18000B066
0x18000b1e6  lea     rdx, [rbp+var_58]
0x18000b1ea  mov     ecx, 2
0x18000b1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1f4  mov     rdi, rax
0x18000b1f7  mov     rax, cs:__pfnDliNotifyHook2
0x18000b1fe  jmp     loc_18000B073
0x18000b203  cmp     dword ptr [rsi+1Ch], 0
0x18000b207  jz      loc_18000B0B1
0x18000b20d  movsxd  rcx, dword ptr [rbx+3Ch]
0x18000b211  cmp     dword ptr [rcx+rbx], 4550h
0x18000b218  jnz     loc_18000B0B1
0x18000b21e  mov     edx, dword ptr [rbp+Arguments]
0x18000b221  cmp     [rcx+rbx+8], edx
0x18000b225  jnz     loc_18000B0B1
0x18000b22b  cmp     rbx, [rcx+rbx+30h]
0x18000b230  jnz     loc_18000B0B1
0x18000b236  mov     rdi, [r15+r13]
0x18000b23a  test    rdi, rdi
0x18000b23d  jnz     loc_18000B078
0x18000b243  jmp     loc_18000B0B1
0x18000b248  call    cs:__imp_GetLastError
0x18000b24e  mov     [rbp+var_18], eax
0x18000b251  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18000b258  test    rax, rax
0x18000b25b  jz      short loc_18000B277
0x18000b25d  lea     rdx, [rbp+var_58]
0x18000b261  mov     ecx, 4
0x18000b266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b26b  mov     rdi, rax
0x18000b26e  test    rax, rax
0x18000b271  jnz     loc_18000B0CA
0x18000b277  lea     rax, [rbp+var_58]
0x18000b27b  mov     [rbp+Arguments], rax
0x18000b27f  call    DloadReleaseSectionWriteAccess
0x18000b284  xor     edx, edx; dwExceptionFlags
0x18000b286  lea     r9, [rbp+Arguments]; lpArguments
0x18000b28a  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18000b28f  lea     r8d, [rdx+1]; nNumberOfArguments
0x18000b293  call    cs:__imp_RaiseException
0x18000b299  call    DloadAcquireSectionWriteAccess
0x18000b29e  mov     rdi, [rbp+var_20]
0x18000b2a2  jmp     loc_18000B0CA
0x18000b2a7  lea     rdx, [rbp+var_58]
0x18000b2ab  mov     [rbp+var_18], 0
0x18000b2b2  mov     ecx, 5
0x18000b2b7  mov     [rbp+var_28], rbx
0x18000b2bb  mov     [rbp+var_20], rdi
0x18000b2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c4  jmp     loc_18000B085
```
