# __delayLoadHelper2

- ea: `0x18001e080`
- end: `0x18001e3bf`
- name: `__delayLoadHelper2`
- size: `831`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002cdb5`
- `0x18002ce40`
- `0x18002ceef`
- `0x18002d178`
- `0x18002d260`

## callees

- `0x18001e080`
- `0x180098b3c`
- `0x180098d54`
- `0x180098db8`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e1fa`
- `KERNEL32!GetLastError` at `0x18001e318`
- `KERNEL32!GetLastError` at `0x18001e1fa`
- `KERNEL32!GetLastError` at `0x18001e318`
- `KERNEL32!GetProcAddress` at `0x18001e304`
- `KERNEL32!GetProcAddress` at `0x18001e304`
- `KERNEL32!FreeLibrary` at `0x18001e285`
- `KERNEL32!FreeLibrary` at `0x18001e285`
- `KERNEL32!RaiseException` at `0x18001e12f`
- `KERNEL32!RaiseException` at `0x18001e245`
- `KERNEL32!RaiseException` at `0x18001e363`
- `KERNEL32!RaiseException` at `0x18001e12f`
- `KERNEL32!RaiseException` at `0x18001e245`
- `KERNEL32!RaiseException` at `0x18001e363`
- `KERNEL32!LoadLibraryExA` at `0x18001e1e6`
- `KERNEL32!LoadLibraryExA` at `0x18001e1e6`

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
0x18001e080  push    rbp
0x18001e082  push    rbx
0x18001e083  push    rsi
0x18001e084  push    rdi
0x18001e085  push    r12
0x18001e087  push    r13
0x18001e089  push    r14
0x18001e08b  push    r15
0x18001e08d  mov     rbp, rsp
0x18001e090  sub     rsp, 78h
0x18001e094  xor     eax, eax
0x18001e096  mov     r12, rdx
0x18001e099  mov     rsi, rcx
0x18001e09c  mov     [rbp+var_54], eax
0x18001e09f  xor     edx, edx; Val
0x18001e0a1  lea     rcx, [rbp+var_58]; void *
0x18001e0a5  lea     r8d, [rax+44h]; Size
0x18001e0a9  call    memset
0x18001e0ae  call    DloadAcquireSectionWriteAccess
0x18001e0b3  mov     eax, [rsi+4]
0x18001e0b6  lea     rdx, __ImageBase
0x18001e0bd  mov     r14d, [rsi+8]
0x18001e0c1  add     rax, rdx
0x18001e0c4  mov     r15d, [rsi+14h]
0x18001e0c8  add     r14, rdx
0x18001e0cb  mov     ecx, [rsi+1Ch]
0x18001e0ce  add     r15, rdx
0x18001e0d1  mov     [rbp+lpLibFileName], rax
0x18001e0d5  mov     eax, [rsi]
0x18001e0d7  mov     dword ptr [rbp+Arguments], ecx
0x18001e0da  mov     [rbp+var_58], 48h ; 'H'
0x18001e0e1  mov     [rbp+var_50], rsi
0x18001e0e5  mov     [rbp+var_48], r12
0x18001e0e9  mov     [rbp+var_38], 0
0x18001e0f0  mov     [rbp+lpProcName], 0
0x18001e0f8  mov     [rbp+var_28], 0
0x18001e100  mov     [rbp+var_20], 0
0x18001e108  mov     [rbp+var_18], 0
0x18001e10f  test    al, 1
0x18001e111  jnz     short loc_18001E142
0x18001e113  lea     rax, [rbp+var_58]
0x18001e117  mov     [rbp+Arguments], rax
0x18001e11b  call    DloadReleaseSectionWriteAccess
0x18001e120  xor     edx, edx; dwExceptionFlags
0x18001e122  lea     r9, [rbp+Arguments]; lpArguments
0x18001e126  mov     ecx, 0C06D0057h; dwExceptionCode
0x18001e12b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001e12f  call    cs:__imp_RaiseException
0x18001e136  nop     dword ptr [rax+rax+00h]
0x18001e13b  xor     eax, eax
0x18001e13d  jmp     loc_18001E3AD
0x18001e142  mov     eax, [rsi+0Ch]
0x18001e145  mov     rcx, r12
0x18001e148  mov     rbx, [r14]
0x18001e14b  sub     rcx, rax
0x18001e14e  sub     rcx, rdx
0x18001e151  sar     rcx, 3
0x18001e155  mov     eax, ecx
0x18001e157  mov     ecx, [rsi+10h]
0x18001e15a  lea     r13, ds:0[rax*8]
0x18001e162  xor     eax, eax
0x18001e164  add     rcx, r13
0x18001e167  cmp     [rcx+rdx], rax
0x18001e16b  setnl   al
0x18001e16e  mov     [rbp+var_38], eax
0x18001e171  test    eax, eax
0x18001e173  jz      short loc_18001E188
0x18001e175  mov     eax, [rcx+rdx]
0x18001e178  lea     rdx, __ImageBase.unused+2
0x18001e17f  add     rax, rdx
0x18001e182  mov     [rbp+lpProcName], rax
0x18001e186  jmp     short loc_18001E18F
0x18001e188  movzx   eax, word ptr [rcx+rdx]
0x18001e18c  mov     dword ptr [rbp+lpProcName], eax
0x18001e18f  mov     rax, cs:__pfnDliNotifyHook2
0x18001e196  xor     edi, edi
0x18001e198  test    rax, rax
0x18001e19b  jz      short loc_18001E1BB
0x18001e19d  lea     rdx, [rbp+var_58]
0x18001e1a1  xor     ecx, ecx
0x18001e1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a8  mov     rdi, rax
0x18001e1ab  test    rax, rax
0x18001e1ae  mov     rax, cs:__pfnDliNotifyHook2
0x18001e1b5  jnz     loc_18001E383
0x18001e1bb  test    rbx, rbx
0x18001e1be  jnz     loc_18001E29F
0x18001e1c4  test    rax, rax
0x18001e1c7  jz      short loc_18001E1DD
0x18001e1c9  lea     rdx, [rbp+var_58]
0x18001e1cd  lea     ecx, [rbx+1]
0x18001e1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1d5  mov     rbx, rax
0x18001e1d8  test    rax, rax
0x18001e1db  jnz     short loc_18001E25A
0x18001e1dd  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001e1e1  xor     r8d, r8d; dwFlags
0x18001e1e4  xor     edx, edx; hFile
0x18001e1e6  call    cs:__imp_LoadLibraryExA
0x18001e1ed  nop     dword ptr [rax+rax+00h]
0x18001e1f2  mov     rbx, rax
0x18001e1f5  test    rax, rax
0x18001e1f8  jnz     short loc_18001E25A
0x18001e1fa  call    cs:__imp_GetLastError
0x18001e201  nop     dword ptr [rax+rax+00h]
0x18001e206  mov     [rbp+var_18], eax
0x18001e209  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001e210  test    rax, rax
0x18001e213  jz      short loc_18001E229
0x18001e215  lea     rdx, [rbp+var_58]
0x18001e219  lea     ecx, [rbx+3]
0x18001e21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e221  mov     rbx, rax
0x18001e224  test    rax, rax
0x18001e227  jnz     short loc_18001E25A
0x18001e229  lea     rax, [rbp+var_58]
0x18001e22d  mov     [rbp+Arguments], rax
0x18001e231  call    DloadReleaseSectionWriteAccess
0x18001e236  xor     edx, edx; dwExceptionFlags
0x18001e238  lea     r9, [rbp+Arguments]; lpArguments
0x18001e23c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18001e241  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001e245  call    cs:__imp_RaiseException
0x18001e24c  nop     dword ptr [rax+rax+00h]
0x18001e251  mov     rax, [rbp+var_20]
0x18001e255  jmp     loc_18001E3AD
0x18001e25a  xor     eax, eax
0x18001e25c  lock cmpxchg [r14], rbx
0x18001e261  mov     r14, rax
0x18001e264  jnz     short loc_18001E27C
0x18001e266  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001e26a  jz      short loc_18001E298
0x18001e26c  cmp     dword ptr [rsi+18h], 0
0x18001e270  jz      short loc_18001E298
0x18001e272  mov     rcx, rsi
0x18001e275  call    NewUnloadInfo
0x18001e27a  jmp     short loc_18001E298
0x18001e27c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001e280  jz      short loc_18001E291
0x18001e282  mov     rcx, rbx; hLibModule
0x18001e285  call    cs:__imp_FreeLibrary
0x18001e28c  nop     dword ptr [rax+rax+00h]
0x18001e291  cmp     rbx, r14
0x18001e294  cmovnz  rbx, r14
0x18001e298  mov     rax, cs:__pfnDliNotifyHook2
0x18001e29f  mov     [rbp+var_28], rbx
0x18001e2a3  test    rax, rax
0x18001e2a6  jz      short loc_18001E2C0
0x18001e2a8  lea     rdx, [rbp+var_58]
0x18001e2ac  mov     ecx, 2
0x18001e2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2b6  mov     rdi, rax
0x18001e2b9  mov     rax, cs:__pfnDliNotifyHook2
0x18001e2c0  test    rdi, rdi
0x18001e2c3  jnz     loc_18001E37F
0x18001e2c9  cmp     [rsi+14h], edi
0x18001e2cc  jz      short loc_18001E2FD
0x18001e2ce  cmp     [rsi+1Ch], edi
0x18001e2d1  jz      short loc_18001E2FD
0x18001e2d3  movsxd  rcx, dword ptr [rbx+3Ch]
0x18001e2d7  cmp     dword ptr [rcx+rbx], 4550h
0x18001e2de  jnz     short loc_18001E2FD
0x18001e2e0  mov     edx, dword ptr [rbp+Arguments]
0x18001e2e3  cmp     [rcx+rbx+8], edx
0x18001e2e7  jnz     short loc_18001E2FD
0x18001e2e9  cmp     rbx, [rcx+rbx+30h]
0x18001e2ee  jnz     short loc_18001E2FD
0x18001e2f0  mov     rdi, [r15+r13]
0x18001e2f4  test    rdi, rdi
0x18001e2f7  jnz     loc_18001E37F
0x18001e2fd  mov     rdx, [rbp+lpProcName]; lpProcName
0x18001e301  mov     rcx, rbx; hModule
0x18001e304  call    cs:__imp_GetProcAddress
0x18001e30b  nop     dword ptr [rax+rax+00h]
0x18001e310  mov     rdi, rax
0x18001e313  test    rax, rax
0x18001e316  jnz     short loc_18001E378
0x18001e318  call    cs:__imp_GetLastError
0x18001e31f  nop     dword ptr [rax+rax+00h]
0x18001e324  mov     [rbp+var_18], eax
0x18001e327  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18001e32e  test    rax, rax
0x18001e331  jz      short loc_18001E347
0x18001e333  lea     rdx, [rbp+var_58]
0x18001e337  lea     ecx, [rdi+4]
0x18001e33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e33f  mov     rdi, rax
0x18001e342  test    rax, rax
0x18001e345  jnz     short loc_18001E378
0x18001e347  lea     rax, [rbp+var_58]
0x18001e34b  mov     [rbp+Arguments], rax
0x18001e34f  call    DloadReleaseSectionWriteAccess
0x18001e354  xor     edx, edx; dwExceptionFlags
0x18001e356  lea     r9, [rbp+Arguments]; lpArguments
0x18001e35a  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18001e35f  lea     r8d, [rdx+1]; nNumberOfArguments
0x18001e363  call    cs:__imp_RaiseException
0x18001e36a  nop     dword ptr [rax+rax+00h]
0x18001e36f  call    DloadAcquireSectionWriteAccess
0x18001e374  mov     rdi, [rbp+var_20]
0x18001e378  mov     rax, cs:__pfnDliNotifyHook2
0x18001e37f  mov     [r12], rdi
0x18001e383  test    rax, rax
0x18001e386  jz      short loc_18001E3A5
0x18001e388  lea     rdx, [rbp+var_58]
0x18001e38c  mov     [rbp+var_18], 0
0x18001e393  mov     ecx, 5
0x18001e398  mov     [rbp+var_28], rbx
0x18001e39c  mov     [rbp+var_20], rdi
0x18001e3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3a5  call    DloadReleaseSectionWriteAccess
0x18001e3aa  mov     rax, rdi
0x18001e3ad  add     rsp, 78h
0x18001e3b1  pop     r15
0x18001e3b3  pop     r14
0x18001e3b5  pop     r13
0x18001e3b7  pop     r12
0x18001e3b9  pop     rdi
0x18001e3ba  pop     rsi
0x18001e3bb  pop     rbx
0x18001e3bc  pop     rbp
0x18001e3bd  retn
```
