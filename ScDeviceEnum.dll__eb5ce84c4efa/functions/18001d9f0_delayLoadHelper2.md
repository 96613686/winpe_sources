# __delayLoadHelper2

- ea: `0x18001d9f0`
- end: `0x18001dd24`
- name: `__delayLoadHelper2`
- size: `820`
- prototype: `FARPROC __fastcall(const ImgDelayDescr *, FARPROC *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002196`

## callees

- `0x18001d790`
- `0x18001d990`
- `0x18001d9f0`
- `0x18001dfe2`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dc7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001dc7c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001db50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001db50`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001dc07`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001dc07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dbca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001dbca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dbdc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001dbdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dc8a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001da9f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dba3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dccf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001da9f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dba3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dccf`

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
0x18001d9f0  push    rbp
0x18001d9f2  push    rbx
0x18001d9f3  push    rsi
0x18001d9f4  push    rdi
0x18001d9f5  push    r12
0x18001d9f7  push    r13
0x18001d9f9  push    r14
0x18001d9fb  push    r15
0x18001d9fd  mov     rbp, rsp
0x18001da00  sub     rsp, 78h
0x18001da04  xor     eax, eax
0x18001da06  mov     r12, rdx
0x18001da09  mov     rsi, rcx
0x18001da0c  mov     [rbp+var_54], eax
0x18001da0f  xor     edx, edx; Val
0x18001da11  lea     rcx, [rbp+var_58]; void *
0x18001da15  lea     r8d, [rax+44h]; Size
0x18001da19  call    memset_0
0x18001da1e  call    DloadAcquireSectionWriteAccess
0x18001da23  mov     eax, [rsi+4]
0x18001da26  lea     rdx, __ImageBase
0x18001da2d  mov     r14d, [rsi+8]
0x18001da31  add     rax, rdx
0x18001da34  mov     r15d, [rsi+14h]
0x18001da38  add     r14, rdx
0x18001da3b  mov     ecx, [rsi+1Ch]
0x18001da3e  add     r15, rdx
0x18001da41  mov     [rbp+lpLibFileName], rax
0x18001da45  mov     eax, [rsi]
0x18001da47  mov     dword ptr [rbp+Arguments], ecx
0x18001da4a  mov     [rbp+var_58], 48h ; 'H'
0x18001da51  mov     [rbp+var_50], rsi
0x18001da55  mov     [rbp+var_48], r12
0x18001da59  mov     [rbp+var_38], 0
0x18001da60  mov     [rbp+lpProcName], 0
0x18001da68  mov     [rbp+var_28], 0
0x18001da70  mov     [rbp+var_20], 0
0x18001da78  mov     [rbp+var_18], 0
0x18001da7f  test    al, 1
0x18001da81  jnz     short loc_18001DAAC
0x18001da83  lea     rax, [rbp+var_58]
0x18001da87  mov     [rbp+Arguments], rax
0x18001da8b  call    DloadReleaseSectionWriteAccess
0x18001da90  xor     edx, edx; dwExceptionFlags
0x18001da92  lea     r9, [rbp+Arguments]; lpArguments
0x18001da96  mov     ecx, 0C06D0057h; dwExceptionCode
0x18001da9b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001da9f  call    cs:__imp_RaiseException
0x18001daa5  xor     eax, eax
0x18001daa7  jmp     loc_18001DD13
0x18001daac  mov     eax, [rsi+0Ch]
0x18001daaf  mov     rcx, r12
0x18001dab2  mov     rbx, [r14]
0x18001dab5  sub     rcx, rax
0x18001dab8  sub     rcx, rdx
0x18001dabb  sar     rcx, 3
0x18001dabf  mov     eax, ecx
0x18001dac1  mov     ecx, [rsi+10h]
0x18001dac4  lea     r13, ds:0[rax*8]
0x18001dacc  xor     eax, eax
0x18001dace  add     rcx, r13
0x18001dad1  cmp     [rcx+rdx], rax
0x18001dad5  setnl   al
0x18001dad8  mov     [rbp+var_38], eax
0x18001dadb  test    eax, eax
0x18001dadd  jz      short loc_18001DAF2
0x18001dadf  mov     eax, [rcx+rdx]
0x18001dae2  lea     rdx, word_180000002
0x18001dae9  add     rax, rdx
0x18001daec  mov     [rbp+lpProcName], rax
0x18001daf0  jmp     short loc_18001DAF9
0x18001daf2  movzx   eax, word ptr [rcx+rdx]
0x18001daf6  mov     dword ptr [rbp+lpProcName], eax
0x18001daf9  mov     rax, cs:__pfnDliNotifyHook2
0x18001db00  xor     edi, edi
0x18001db02  test    rax, rax
0x18001db05  jz      short loc_18001DB25
0x18001db07  lea     rdx, [rbp+var_58]
0x18001db0b  xor     ecx, ecx
0x18001db0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db12  mov     rdi, rax
0x18001db15  test    rax, rax
0x18001db18  mov     rax, cs:__pfnDliNotifyHook2
0x18001db1f  jnz     loc_18001DCE9
0x18001db25  test    rbx, rbx
0x18001db28  jnz     loc_18001DC1B
0x18001db2e  test    rax, rax
0x18001db31  jz      short loc_18001DB47
0x18001db33  lea     rdx, [rbp+var_58]
0x18001db37  lea     ecx, [rbx+1]
0x18001db3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db3f  mov     rbx, rax
0x18001db42  test    rax, rax
0x18001db45  jnz     short loc_18001DBB2
0x18001db47  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001db4b  xor     r8d, r8d; dwFlags
0x18001db4e  xor     edx, edx; hFile
0x18001db50  call    cs:__imp_LoadLibraryExA
0x18001db56  mov     rbx, rax
0x18001db59  test    rax, rax
0x18001db5c  jnz     short loc_18001DBB2
0x18001db5e  call    cs:__imp_GetLastError
0x18001db64  mov     [rbp+var_18], eax
0x18001db67  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001db6e  test    rax, rax
0x18001db71  jz      short loc_18001DB87
0x18001db73  lea     rdx, [rbp+var_58]
0x18001db77  lea     ecx, [rbx+3]
0x18001db7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db7f  mov     rbx, rax
0x18001db82  test    rax, rax
0x18001db85  jnz     short loc_18001DBB2
0x18001db87  lea     rax, [rbp+var_58]
0x18001db8b  mov     [rbp+Arguments], rax
0x18001db8f  call    DloadReleaseSectionWriteAccess
0x18001db94  xor     edx, edx; dwExceptionFlags
0x18001db96  lea     r9, [rbp+Arguments]; lpArguments
0x18001db9a  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18001db9f  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001dba3  call    cs:__imp_RaiseException
0x18001dba9  mov     rax, [rbp+var_20]
0x18001dbad  jmp     loc_18001DD13
0x18001dbb2  xor     eax, eax
0x18001dbb4  lock cmpxchg [r14], rbx
0x18001dbb9  mov     r14, rax
0x18001dbbc  jnz     short loc_18001DBFE
0x18001dbbe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001dbc2  jz      short loc_18001DC14
0x18001dbc4  cmp     dword ptr [rsi+18h], 0
0x18001dbc8  jz      short loc_18001DC14
0x18001dbca  call    cs:__imp_GetProcessHeap
0x18001dbd0  mov     edx, 8; dwFlags
0x18001dbd5  mov     rcx, rax; hHeap
0x18001dbd8  lea     r8d, [rdx+8]; dwBytes
0x18001dbdc  call    cs:__imp_HeapAlloc
0x18001dbe2  test    rax, rax
0x18001dbe5  jz      short loc_18001DC14
0x18001dbe7  mov     [rax+8], rsi
0x18001dbeb  mov     rcx, cs:__puiHead
0x18001dbf2  mov     [rax], rcx
0x18001dbf5  mov     cs:__puiHead, rax
0x18001dbfc  jmp     short loc_18001DC14
0x18001dbfe  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001dc02  jz      short loc_18001DC0D
0x18001dc04  mov     rcx, rbx; hLibModule
0x18001dc07  call    cs:__imp_FreeLibrary
0x18001dc0d  cmp     rbx, r14
0x18001dc10  cmovnz  rbx, r14
0x18001dc14  mov     rax, cs:__pfnDliNotifyHook2
0x18001dc1b  mov     [rbp+var_28], rbx
0x18001dc1f  test    rax, rax
0x18001dc22  jz      short loc_18001DC3C
0x18001dc24  lea     rdx, [rbp+var_58]
0x18001dc28  mov     ecx, 2
0x18001dc2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc32  mov     rdi, rax
0x18001dc35  mov     rax, cs:__pfnDliNotifyHook2
0x18001dc3c  test    rdi, rdi
0x18001dc3f  jnz     loc_18001DCE5
0x18001dc45  cmp     [rsi+14h], edi
0x18001dc48  jz      short loc_18001DC75
0x18001dc4a  cmp     [rsi+1Ch], edi
0x18001dc4d  jz      short loc_18001DC75
0x18001dc4f  movsxd  rcx, dword ptr [rbx+3Ch]
0x18001dc53  cmp     dword ptr [rcx+rbx], 4550h
0x18001dc5a  jnz     short loc_18001DC75
0x18001dc5c  mov     edx, dword ptr [rbp+Arguments]
0x18001dc5f  cmp     [rcx+rbx+8], edx
0x18001dc63  jnz     short loc_18001DC75
0x18001dc65  cmp     rbx, [rcx+rbx+30h]
0x18001dc6a  jnz     short loc_18001DC75
0x18001dc6c  mov     rdi, [r15+r13]
0x18001dc70  test    rdi, rdi
0x18001dc73  jnz     short loc_18001DCE5
0x18001dc75  mov     rdx, [rbp+lpProcName]; lpProcName
0x18001dc79  mov     rcx, rbx; hModule
0x18001dc7c  call    cs:__imp_GetProcAddress
0x18001dc82  mov     rdi, rax
0x18001dc85  test    rax, rax
0x18001dc88  jnz     short loc_18001DCDE
0x18001dc8a  call    cs:__imp_GetLastError
0x18001dc90  mov     [rbp+var_18], eax
0x18001dc93  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001dc9a  test    rax, rax
0x18001dc9d  jz      short loc_18001DCB3
0x18001dc9f  lea     rdx, [rbp+var_58]
0x18001dca3  lea     ecx, [rdi+4]
0x18001dca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcab  mov     rdi, rax
0x18001dcae  test    rax, rax
0x18001dcb1  jnz     short loc_18001DCDE
0x18001dcb3  lea     rax, [rbp+var_58]
0x18001dcb7  mov     [rbp+Arguments], rax
0x18001dcbb  call    DloadReleaseSectionWriteAccess
0x18001dcc0  xor     edx, edx; dwExceptionFlags
0x18001dcc2  lea     r9, [rbp+Arguments]; lpArguments
0x18001dcc6  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18001dccb  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001dccf  call    cs:__imp_RaiseException
0x18001dcd5  call    DloadAcquireSectionWriteAccess
0x18001dcda  mov     rdi, [rbp+var_20]
0x18001dcde  mov     rax, cs:__pfnDliNotifyHook2
0x18001dce5  mov     [r12], rdi
0x18001dce9  test    rax, rax
0x18001dcec  jz      short loc_18001DD0B
0x18001dcee  lea     rdx, [rbp+var_58]
0x18001dcf2  mov     [rbp+var_18], 0
0x18001dcf9  mov     ecx, 5
0x18001dcfe  mov     [rbp+var_28], rbx
0x18001dd02  mov     [rbp+var_20], rdi
0x18001dd06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd0b  call    DloadReleaseSectionWriteAccess
0x18001dd10  mov     rax, rdi
0x18001dd13  add     rsp, 78h
0x18001dd17  pop     r15
0x18001dd19  pop     r14
0x18001dd1b  pop     r13
0x18001dd1d  pop     r12
0x18001dd1f  pop     rdi
0x18001dd20  pop     rsi
0x18001dd21  pop     rbx
0x18001dd22  pop     rbp
0x18001dd23  retn
```
