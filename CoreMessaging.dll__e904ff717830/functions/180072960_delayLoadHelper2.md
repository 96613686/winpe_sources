# __delayLoadHelper2

- ea: `0x180072960`
- end: `0x180072cdb`
- name: `__delayLoadHelper2`
- size: `891`
- prototype: ``
- caller_count: `19`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009e0ae`
- `0x18009e15d`
- `0x18009e21e`
- `0x18009e393`
- `0x18009e41e`
- `0x18009e4bb`
- `0x18009e5a6`
- `0x18009e9a4`
- `0x18009ea41`
- `0x18009eade`
- `0x18009ebf9`
- `0x18009ec96`
- `0x18009ed45`
- `0x18009edd0`
- `0x18009ee6d`
- `0x18009eef8`
- `0x18009efb9`
- `0x18009f0c2`
- `0x18009f1ef`

## callees

- `0x180072960`
- `0x180072ce4`
- `0x180072d3c`
- `0x18009e054`
- `0x1800c65b0`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180072bf0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180072bf0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180072ad7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180072ad7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072aaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180072aaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072c5a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072b31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072bcb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072ca5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072b31`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072bcb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072ca5`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  __int64 v4; // r8
  __int64 v5; // r9
  unsigned __int64 v6; // rdx
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
  v6 = (unsigned __int64)&_ImageBase;
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
    v6 = (unsigned __int64)&word_180000002;
    v18.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)((char *)&_ImageBase + v13);
  }
  else
  {
    v18.dlp.dwOrdinal = *(char16_t *)((char *)&_ImageBase + v13);
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
        || (v6 = (unsigned int)Arguments, *(_DWORD *)((char *)Library + v13 + 8) != (_DWORD)Arguments)
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
0x180072960  push    rbp
0x180072962  push    rbx
0x180072963  push    rsi
0x180072964  push    rdi
0x180072965  push    r12
0x180072967  push    r13
0x180072969  push    r14
0x18007296b  push    r15
0x18007296d  mov     rbp, rsp
0x180072970  sub     rsp, 78h
0x180072974  xor     eax, eax
0x180072976  mov     r12, rdx
0x180072979  mov     rsi, rcx
0x18007297c  mov     [rbp+var_54], eax
0x18007297f  xor     edx, edx; Val
0x180072981  lea     rcx, [rbp+var_58]; void *
0x180072985  lea     r8d, [rax+44h]; Size
0x180072989  call    memset_0
0x18007298e  call    DloadAcquireSectionWriteAccess
0x180072993  mov     eax, [rsi+4]
0x180072996  lea     rdx, __ImageBase
0x18007299d  mov     r14d, [rsi+8]
0x1800729a1  add     rax, rdx
0x1800729a4  mov     r15d, [rsi+14h]
0x1800729a8  add     r14, rdx
0x1800729ab  mov     ecx, [rsi+1Ch]
0x1800729ae  add     r15, rdx
0x1800729b1  mov     [rbp+lpLibFileName], rax
0x1800729b5  mov     eax, [rsi]
0x1800729b7  mov     dword ptr [rbp+Arguments], ecx
0x1800729ba  mov     [rbp+var_58], 48h ; 'H'
0x1800729c1  mov     [rbp+var_50], rsi
0x1800729c5  mov     [rbp+var_48], r12
0x1800729c9  mov     [rbp+var_38], 0
0x1800729d0  mov     [rbp+lpProcName], 0
0x1800729d8  mov     [rbp+var_28], 0
0x1800729e0  mov     [rbp+var_20], 0
0x1800729e8  mov     [rbp+var_18], 0
0x1800729ef  test    al, 1
0x1800729f1  jz      loc_180072B15
0x1800729f7  mov     eax, [rsi+0Ch]
0x1800729fa  mov     rcx, r12
0x1800729fd  mov     rbx, [r14]
0x180072a00  sub     rcx, rax
0x180072a03  sub     rcx, rdx
0x180072a06  sar     rcx, 3
0x180072a0a  mov     eax, ecx
0x180072a0c  mov     ecx, [rsi+10h]
0x180072a0f  lea     r13, ds:0[rax*8]
0x180072a17  xor     eax, eax
0x180072a19  add     rcx, r13
0x180072a1c  cmp     [rcx+rdx], rax
0x180072a20  setnl   al
0x180072a23  mov     [rbp+var_38], eax
0x180072a26  test    eax, eax
0x180072a28  jz      short loc_180072A8A
0x180072a2a  mov     eax, [rcx+rdx]
0x180072a2d  lea     rdx, word_180000002
0x180072a34  add     rax, rdx
0x180072a37  mov     [rbp+lpProcName], rax
0x180072a3b  mov     rax, cs:__pfnDliNotifyHook2
0x180072a42  xor     edi, edi
0x180072a44  test    rax, rax
0x180072a47  jnz     loc_180072B3E
0x180072a4d  test    rbx, rbx
0x180072a50  jz      short loc_180072AC5
0x180072a52  mov     [rbp+var_28], rbx
0x180072a56  test    rax, rax
0x180072a59  jnz     loc_180072C02
0x180072a5f  test    rdi, rdi
0x180072a62  jz      short loc_180072A93
0x180072a64  mov     [r12], rdi
0x180072a68  test    rax, rax
0x180072a6b  jnz     loc_180072CB9
0x180072a71  call    DloadReleaseSectionWriteAccess
0x180072a76  mov     rax, rdi
0x180072a79  add     rsp, 78h
0x180072a7d  pop     r15
0x180072a7f  pop     r14
0x180072a81  pop     r13
0x180072a83  pop     r12
0x180072a85  pop     rdi
0x180072a86  pop     rsi
0x180072a87  pop     rbx
0x180072a88  pop     rbp
0x180072a89  retn
0x180072a8a  movzx   eax, word ptr [rcx+rdx]
0x180072a8e  mov     dword ptr [rbp+lpProcName], eax
0x180072a91  jmp     short loc_180072A3B
0x180072a93  cmp     dword ptr [rsi+14h], 0
0x180072a97  jz      short loc_180072AA3
0x180072a99  cmp     dword ptr [rsi+1Ch], 0
0x180072a9d  jnz     loc_180072C1F
0x180072aa3  mov     rdx, [rbp+lpProcName]; lpProcName
0x180072aa7  mov     rcx, rbx; hModule
0x180072aaa  call    cs:__imp_GetProcAddress
0x180072ab0  mov     rdi, rax
0x180072ab3  test    rax, rax
0x180072ab6  jz      loc_180072C5A
0x180072abc  mov     rax, cs:__pfnDliNotifyHook2
0x180072ac3  jmp     short loc_180072A64
0x180072ac5  test    rax, rax
0x180072ac8  jnz     loc_180072B61
0x180072ace  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180072ad2  xor     r8d, r8d; dwFlags
0x180072ad5  xor     edx, edx; hFile
0x180072ad7  call    cs:__imp_LoadLibraryExA
0x180072add  mov     rbx, rax
0x180072ae0  test    rax, rax
0x180072ae3  jz      loc_180072B80
0x180072ae9  xor     eax, eax
0x180072aeb  lock cmpxchg [r14], rbx
0x180072af0  mov     r14, rax
0x180072af3  jnz     loc_180072BE7
0x180072af9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180072afd  jz      short loc_180072B09
0x180072aff  cmp     dword ptr [rsi+18h], 0
0x180072b03  jnz     loc_180072BDA
0x180072b09  mov     rax, cs:__pfnDliNotifyHook2
0x180072b10  jmp     loc_180072A52
0x180072b15  lea     rax, [rbp+var_58]
0x180072b19  mov     [rbp+Arguments], rax
0x180072b1d  call    DloadReleaseSectionWriteAccess
0x180072b22  xor     edx, edx; dwExceptionFlags
0x180072b24  lea     r9, [rbp+Arguments]; lpArguments
0x180072b28  mov     ecx, 0C06D0057h; dwExceptionCode
0x180072b2d  lea     r8d, [rdx+1]; nNumberOfArguments
0x180072b31  call    cs:__imp_RaiseException
0x180072b37  xor     eax, eax
0x180072b39  jmp     loc_180072A79
0x180072b3e  lea     rdx, [rbp+var_58]
0x180072b42  xor     ecx, ecx
0x180072b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b49  mov     rdi, rax
0x180072b4c  test    rax, rax
0x180072b4f  mov     rax, cs:__pfnDliNotifyHook2
0x180072b56  jnz     loc_180072A68
0x180072b5c  jmp     loc_180072A4D
0x180072b61  lea     rdx, [rbp+var_58]
0x180072b65  mov     ecx, 1
0x180072b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b6f  mov     rbx, rax
0x180072b72  test    rax, rax
0x180072b75  jnz     loc_180072AE9
0x180072b7b  jmp     loc_180072ACE
0x180072b80  call    cs:__imp_GetLastError
0x180072b86  mov     [rbp+var_18], eax
0x180072b89  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180072b90  test    rax, rax
0x180072b93  jz      short loc_180072BAF
0x180072b95  lea     rdx, [rbp+var_58]
0x180072b99  mov     ecx, 3
0x180072b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ba3  mov     rbx, rax
0x180072ba6  test    rax, rax
0x180072ba9  jnz     loc_180072AE9
0x180072baf  lea     rax, [rbp+var_58]
0x180072bb3  mov     [rbp+Arguments], rax
0x180072bb7  call    DloadReleaseSectionWriteAccess
0x180072bbc  xor     edx, edx; dwExceptionFlags
0x180072bbe  lea     r9, [rbp+Arguments]; lpArguments
0x180072bc2  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180072bc7  lea     r8d, [rdx+1]; nNumberOfArguments
0x180072bcb  call    cs:__imp_RaiseException
0x180072bd1  mov     rax, [rbp+var_20]
0x180072bd5  jmp     loc_180072A79
0x180072bda  mov     rcx, rsi
0x180072bdd  call    NewUnloadInfo
0x180072be2  jmp     loc_180072B09
0x180072be7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180072beb  jz      short loc_180072BF6
0x180072bed  mov     rcx, rbx; hLibModule
0x180072bf0  call    cs:__imp_FreeLibrary
0x180072bf6  cmp     rbx, r14
0x180072bf9  cmovnz  rbx, r14
0x180072bfd  jmp     loc_180072B09
0x180072c02  lea     rdx, [rbp+var_58]
0x180072c06  mov     ecx, 2
0x180072c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c10  mov     rdi, rax
0x180072c13  mov     rax, cs:__pfnDliNotifyHook2
0x180072c1a  jmp     loc_180072A5F
0x180072c1f  movsxd  rcx, dword ptr [rbx+3Ch]
0x180072c23  cmp     dword ptr [rcx+rbx], 4550h
0x180072c2a  jnz     loc_180072AA3
0x180072c30  mov     edx, dword ptr [rbp+Arguments]
0x180072c33  cmp     [rcx+rbx+8], edx
0x180072c37  jnz     loc_180072AA3
0x180072c3d  cmp     rbx, [rcx+rbx+30h]
0x180072c42  jnz     loc_180072AA3
0x180072c48  mov     rdi, [r15+r13]
0x180072c4c  test    rdi, rdi
0x180072c4f  jnz     loc_180072A64
0x180072c55  jmp     loc_180072AA3
0x180072c5a  call    cs:__imp_GetLastError
0x180072c60  mov     [rbp+var_18], eax
0x180072c63  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180072c6a  test    rax, rax
0x180072c6d  jz      short loc_180072C89
0x180072c6f  lea     rdx, [rbp+var_58]
0x180072c73  mov     ecx, 4
0x180072c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c7d  mov     rdi, rax
0x180072c80  test    rax, rax
0x180072c83  jnz     loc_180072ABC
0x180072c89  lea     rax, [rbp+var_58]
0x180072c8d  mov     [rbp+Arguments], rax
0x180072c91  call    DloadReleaseSectionWriteAccess
0x180072c96  xor     edx, edx; dwExceptionFlags
0x180072c98  lea     r9, [rbp+Arguments]; lpArguments
0x180072c9c  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180072ca1  lea     r8d, [rdx+1]; nNumberOfArguments
0x180072ca5  call    cs:__imp_RaiseException
0x180072cab  call    DloadAcquireSectionWriteAccess
0x180072cb0  mov     rdi, [rbp+var_20]
0x180072cb4  jmp     loc_180072ABC
0x180072cb9  lea     rdx, [rbp+var_58]
0x180072cbd  mov     [rbp+var_18], 0
0x180072cc4  mov     ecx, 5
0x180072cc9  mov     [rbp+var_28], rbx
0x180072ccd  mov     [rbp+var_20], rdi
0x180072cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072cd6  jmp     loc_180072A71
```
