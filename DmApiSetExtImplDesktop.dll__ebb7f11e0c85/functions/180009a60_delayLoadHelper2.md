# __delayLoadHelper2

- ea: `0x180009a60`
- end: `0x180009dd5`
- name: `__delayLoadHelper2`
- size: `885`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c76`
- `0x180001d5b`
- `0x180001df8`
- `0x180001e83`
- `0x180001f56`
- `0x180002005`
- `0x180002090`
- `0x180002190`

## callees

- `0x1800097d0`
- `0x1800099f0`
- `0x180009a60`
- `0x180009efe`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009c9b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180009c9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d1a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009d1a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180009bc6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180009bc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c52`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c6a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009c6a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009b0f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009c25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009d79`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009b0f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009c25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d2e`

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
0x180009a60  push    rbp
0x180009a62  push    rbx
0x180009a63  push    rsi
0x180009a64  push    rdi
0x180009a65  push    r12
0x180009a67  push    r13
0x180009a69  push    r14
0x180009a6b  push    r15
0x180009a6d  mov     rbp, rsp
0x180009a70  sub     rsp, 78h
0x180009a74  xor     eax, eax
0x180009a76  mov     r12, rdx
0x180009a79  mov     rsi, rcx
0x180009a7c  mov     [rbp+var_54], eax
0x180009a7f  xor     edx, edx; Val
0x180009a81  lea     rcx, [rbp+var_58]; void *
0x180009a85  lea     r8d, [rax+44h]; Size
0x180009a89  call    memset_0
0x180009a8e  call    DloadAcquireSectionWriteAccess
0x180009a93  mov     eax, [rsi+4]
0x180009a96  lea     rdx, __ImageBase
0x180009a9d  mov     r14d, [rsi+8]
0x180009aa1  add     rax, rdx
0x180009aa4  mov     r15d, [rsi+14h]
0x180009aa8  add     r14, rdx
0x180009aab  mov     ecx, [rsi+1Ch]
0x180009aae  add     r15, rdx
0x180009ab1  mov     [rbp+lpLibFileName], rax
0x180009ab5  mov     eax, [rsi]
0x180009ab7  mov     dword ptr [rbp+Arguments], ecx
0x180009aba  mov     [rbp+var_58], 48h ; 'H'
0x180009ac1  mov     [rbp+var_50], rsi
0x180009ac5  mov     [rbp+var_48], r12
0x180009ac9  mov     [rbp+var_38], 0
0x180009ad0  mov     [rbp+lpProcName], 0
0x180009ad8  mov     [rbp+var_28], 0
0x180009ae0  mov     [rbp+var_20], 0
0x180009ae8  mov     [rbp+var_18], 0
0x180009aef  test    al, 1
0x180009af1  jnz     short loc_180009B22
0x180009af3  lea     rax, [rbp+var_58]
0x180009af7  mov     [rbp+Arguments], rax
0x180009afb  call    DloadReleaseSectionWriteAccess
0x180009b00  xor     edx, edx; dwExceptionFlags
0x180009b02  lea     r9, [rbp+Arguments]; lpArguments
0x180009b06  mov     ecx, 0C06D0057h; dwExceptionCode
0x180009b0b  lea     r8d, [rdx+1]; nNumberOfArguments
0x180009b0f  call    cs:__imp_RaiseException
0x180009b16  nop     dword ptr [rax+rax+00h]
0x180009b1b  xor     eax, eax
0x180009b1d  jmp     loc_180009DC3
0x180009b22  mov     eax, [rsi+0Ch]
0x180009b25  mov     rcx, r12
0x180009b28  mov     rbx, [r14]
0x180009b2b  sub     rcx, rax
0x180009b2e  sub     rcx, rdx
0x180009b31  sar     rcx, 3
0x180009b35  mov     eax, ecx
0x180009b37  mov     ecx, [rsi+10h]
0x180009b3a  lea     r13, ds:0[rax*8]
0x180009b42  xor     eax, eax
0x180009b44  add     rcx, r13
0x180009b47  cmp     [rcx+rdx], rax
0x180009b4b  setnl   al
0x180009b4e  mov     [rbp+var_38], eax
0x180009b51  test    eax, eax
0x180009b53  jz      short loc_180009B68
0x180009b55  mov     eax, [rcx+rdx]
0x180009b58  lea     rdx, word_180000002
0x180009b5f  add     rax, rdx
0x180009b62  mov     [rbp+lpProcName], rax
0x180009b66  jmp     short loc_180009B6F
0x180009b68  movzx   eax, word ptr [rcx+rdx]
0x180009b6c  mov     dword ptr [rbp+lpProcName], eax
0x180009b6f  mov     rax, cs:__pfnDliNotifyHook2
0x180009b76  xor     edi, edi
0x180009b78  test    rax, rax
0x180009b7b  jz      short loc_180009B9B
0x180009b7d  lea     rdx, [rbp+var_58]
0x180009b81  xor     ecx, ecx
0x180009b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b88  mov     rdi, rax
0x180009b8b  test    rax, rax
0x180009b8e  mov     rax, cs:__pfnDliNotifyHook2
0x180009b95  jnz     loc_180009D99
0x180009b9b  test    rbx, rbx
0x180009b9e  jnz     loc_180009CB5
0x180009ba4  test    rax, rax
0x180009ba7  jz      short loc_180009BBD
0x180009ba9  lea     rdx, [rbp+var_58]
0x180009bad  lea     ecx, [rbx+1]
0x180009bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb5  mov     rbx, rax
0x180009bb8  test    rax, rax
0x180009bbb  jnz     short loc_180009C3A
0x180009bbd  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180009bc1  xor     r8d, r8d; dwFlags
0x180009bc4  xor     edx, edx; hFile
0x180009bc6  call    cs:__imp_LoadLibraryExA
0x180009bcd  nop     dword ptr [rax+rax+00h]
0x180009bd2  mov     rbx, rax
0x180009bd5  test    rax, rax
0x180009bd8  jnz     short loc_180009C3A
0x180009bda  call    cs:__imp_GetLastError
0x180009be1  nop     dword ptr [rax+rax+00h]
0x180009be6  mov     [rbp+var_18], eax
0x180009be9  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180009bf0  test    rax, rax
0x180009bf3  jz      short loc_180009C09
0x180009bf5  lea     rdx, [rbp+var_58]
0x180009bf9  lea     ecx, [rbx+3]
0x180009bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c01  mov     rbx, rax
0x180009c04  test    rax, rax
0x180009c07  jnz     short loc_180009C3A
0x180009c09  lea     rax, [rbp+var_58]
0x180009c0d  mov     [rbp+Arguments], rax
0x180009c11  call    DloadReleaseSectionWriteAccess
0x180009c16  xor     edx, edx; dwExceptionFlags
0x180009c18  lea     r9, [rbp+Arguments]; lpArguments
0x180009c1c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180009c21  lea     r8d, [rdx+1]; nNumberOfArguments
0x180009c25  call    cs:__imp_RaiseException
0x180009c2c  nop     dword ptr [rax+rax+00h]
0x180009c31  mov     rax, [rbp+var_20]
0x180009c35  jmp     loc_180009DC3
0x180009c3a  xor     eax, eax
0x180009c3c  lock cmpxchg [r14], rbx
0x180009c41  mov     r14, rax
0x180009c44  jnz     short loc_180009C92
0x180009c46  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180009c4a  jz      short loc_180009CAE
0x180009c4c  cmp     dword ptr [rsi+18h], 0
0x180009c50  jz      short loc_180009CAE
0x180009c52  call    cs:__imp_GetProcessHeap
0x180009c59  nop     dword ptr [rax+rax+00h]
0x180009c5e  mov     edx, 8; dwFlags
0x180009c63  mov     rcx, rax; hHeap
0x180009c66  lea     r8d, [rdx+8]; dwBytes
0x180009c6a  call    cs:__imp_HeapAlloc
0x180009c71  nop     dword ptr [rax+rax+00h]
0x180009c76  test    rax, rax
0x180009c79  jz      short loc_180009CAE
0x180009c7b  mov     [rax+8], rsi
0x180009c7f  mov     rcx, cs:__puiHead
0x180009c86  mov     [rax], rcx
0x180009c89  mov     cs:__puiHead, rax
0x180009c90  jmp     short loc_180009CAE
0x180009c92  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180009c96  jz      short loc_180009CA7
0x180009c98  mov     rcx, rbx; hLibModule
0x180009c9b  call    cs:__imp_FreeLibrary
0x180009ca2  nop     dword ptr [rax+rax+00h]
0x180009ca7  cmp     rbx, r14
0x180009caa  cmovnz  rbx, r14
0x180009cae  mov     rax, cs:__pfnDliNotifyHook2
0x180009cb5  mov     [rbp+var_28], rbx
0x180009cb9  test    rax, rax
0x180009cbc  jz      short loc_180009CD6
0x180009cbe  lea     rdx, [rbp+var_58]
0x180009cc2  mov     ecx, 2
0x180009cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ccc  mov     rdi, rax
0x180009ccf  mov     rax, cs:__pfnDliNotifyHook2
0x180009cd6  test    rdi, rdi
0x180009cd9  jnz     loc_180009D95
0x180009cdf  cmp     [rsi+14h], edi
0x180009ce2  jz      short loc_180009D13
0x180009ce4  cmp     [rsi+1Ch], edi
0x180009ce7  jz      short loc_180009D13
0x180009ce9  movsxd  rcx, dword ptr [rbx+3Ch]
0x180009ced  cmp     dword ptr [rcx+rbx], 4550h
0x180009cf4  jnz     short loc_180009D13
0x180009cf6  mov     edx, dword ptr [rbp+Arguments]
0x180009cf9  cmp     [rcx+rbx+8], edx
0x180009cfd  jnz     short loc_180009D13
0x180009cff  cmp     rbx, [rcx+rbx+30h]
0x180009d04  jnz     short loc_180009D13
0x180009d06  mov     rdi, [r15+r13]
0x180009d0a  test    rdi, rdi
0x180009d0d  jnz     loc_180009D95
0x180009d13  mov     rdx, [rbp+lpProcName]; lpProcName
0x180009d17  mov     rcx, rbx; hModule
0x180009d1a  call    cs:__imp_GetProcAddress
0x180009d21  nop     dword ptr [rax+rax+00h]
0x180009d26  mov     rdi, rax
0x180009d29  test    rax, rax
0x180009d2c  jnz     short loc_180009D8E
0x180009d2e  call    cs:__imp_GetLastError
0x180009d35  nop     dword ptr [rax+rax+00h]
0x180009d3a  mov     [rbp+var_18], eax
0x180009d3d  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180009d44  test    rax, rax
0x180009d47  jz      short loc_180009D5D
0x180009d49  lea     rdx, [rbp+var_58]
0x180009d4d  lea     ecx, [rdi+4]
0x180009d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d55  mov     rdi, rax
0x180009d58  test    rax, rax
0x180009d5b  jnz     short loc_180009D8E
0x180009d5d  lea     rax, [rbp+var_58]
0x180009d61  mov     [rbp+Arguments], rax
0x180009d65  call    DloadReleaseSectionWriteAccess
0x180009d6a  xor     edx, edx; dwExceptionFlags
0x180009d6c  lea     r9, [rbp+Arguments]; lpArguments
0x180009d70  mov     ecx, 0C06D007Fh; dwExceptionCode
0x180009d75  lea     r8d, [rdx+1]; nNumberOfArguments
0x180009d79  call    cs:__imp_RaiseException
0x180009d80  nop     dword ptr [rax+rax+00h]
0x180009d85  call    DloadAcquireSectionWriteAccess
0x180009d8a  mov     rdi, [rbp+var_20]
0x180009d8e  mov     rax, cs:__pfnDliNotifyHook2
0x180009d95  mov     [r12], rdi
0x180009d99  test    rax, rax
0x180009d9c  jz      short loc_180009DBB
0x180009d9e  lea     rdx, [rbp+var_58]
0x180009da2  mov     [rbp+var_18], 0
0x180009da9  mov     ecx, 5
0x180009dae  mov     [rbp+var_28], rbx
0x180009db2  mov     [rbp+var_20], rdi
0x180009db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dbb  call    DloadReleaseSectionWriteAccess
0x180009dc0  mov     rax, rdi
0x180009dc3  add     rsp, 78h
0x180009dc7  pop     r15
0x180009dc9  pop     r14
0x180009dcb  pop     r13
0x180009dcd  pop     r12
0x180009dcf  pop     rdi
0x180009dd0  pop     rsi
0x180009dd1  pop     rbx
0x180009dd2  pop     rbp
0x180009dd3  retn
```
