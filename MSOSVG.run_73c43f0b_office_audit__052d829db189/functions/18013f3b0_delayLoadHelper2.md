# __delayLoadHelper2

- ea: `0x18013f3b0`
- end: `0x18013f6aa`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18013cc7a`

## callees

- `0x18013ee88`
- `0x18013ef74`
- `0x18013f2fc`
- `0x18013f3b0`
- `0x18013f810`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18013f50f`
- `KERNEL32!GetLastError` at `0x18013f5e9`
- `KERNEL32!GetLastError` at `0x18013f50f`
- `KERNEL32!GetLastError` at `0x18013f5e9`
- `KERNEL32!LoadLibraryExA` at `0x18013f501`
- `KERNEL32!LoadLibraryExA` at `0x18013f501`
- `KERNEL32!FreeLibrary` at `0x18013f572`
- `KERNEL32!FreeLibrary` at `0x18013f572`
- `KERNEL32!RaiseException` at `0x18013f45f`
- `KERNEL32!RaiseException` at `0x18013f555`
- `KERNEL32!RaiseException` at `0x18013f62f`
- `KERNEL32!RaiseException` at `0x18013f45f`
- `KERNEL32!RaiseException` at `0x18013f555`
- `KERNEL32!RaiseException` at `0x18013f62f`
- `KERNEL32!GetProcAddress` at `0x18013f5db`
- `KERNEL32!GetProcAddress` at `0x18013f5db`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(const ImgDelayDescr *a1, FARPROC *a2)
{
  volatile __int64 *v4; // r14
  char *v5; // rdx
  char *v6; // rcx
  char *v7; // r13
  DWORD grAttrs; // eax
  HMODULE Library; // rbx
  __int64 v11; // r12
  bool v12; // zf
  PfnDliHook v13; // rax
  INT_PTR (__stdcall *ProcAddress)(); // rdi
  __int64 v15; // rax
  struct DelayLoadInfo v16; // [rsp+30h] [rbp-50h] BYREF
  ULONG_PTR Arguments; // [rsp+B0h] [rbp+30h] BYREF

  DloadAcquireSectionWriteAccess();
  v4 = (volatile __int64 *)((char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaHmod);
  v5 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaIAT;
  v6 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaINT;
  v7 = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaBoundIAT;
  v16.szDll = (char *)&_NULL_IMPORT_DESCRIPTOR + a1->rvaDLLName;
  grAttrs = a1->grAttrs;
  LODWORD(Arguments) = a1->dwTimeStamp;
  v16.cb = 72;
  v16.pidd = a1;
  v16.ppfn = a2;
  memset(&v16.dlp, 0, 36);
  if ( (grAttrs & 1) == 0 )
  {
    Arguments = (ULONG_PTR)&v16;
    DloadReleaseSectionWriteAccess();
    RaiseException(0xC06D0057, 0, 1u, &Arguments);
    return 0;
  }
  Library = (HMODULE)*v4;
  v11 = (unsigned int)(((char *)a2 - v5) >> 3);
  v12 = *(__int64 *)&v6[8 * v11] < 0;
  v16.dlp.fImportByName = *(_QWORD *)&v6[8 * v11] >= 0LL;
  if ( v12 )
    v16.dlp.dwOrdinal = *(unsigned __int16 *)&v6[8 * v11];
  else
    v16.dlp.szProcName = (char *)&word_180000002 + *(unsigned int *)&v6[8 * v11];
  v13 = _pfnDliNotifyHook2;
  ProcAddress = 0;
  if ( _pfnDliNotifyHook2 )
  {
    ProcAddress = _pfnDliNotifyHook2(0, &v16);
    if ( ProcAddress )
      goto LABEL_33;
    v13 = _pfnDliNotifyHook2;
  }
  if ( !Library )
  {
    if ( !v13 || (Library = (HMODULE)((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v13)(1, &v16)) == 0 )
    {
      Library = LoadLibraryExA(v16.szDll, 0, 0);
      if ( !Library )
      {
        v16.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (Library = (HMODULE)_pfnDliFailureHook2(3u, &v16)) == 0 )
        {
          Arguments = (ULONG_PTR)&v16;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007E, 0, 1u, &Arguments);
          return v16.pfnCur;
        }
      }
    }
    if ( (HMODULE)_InterlockedExchange64(v4, (__int64)Library) == Library )
      FreeLibrary(Library);
    v13 = _pfnDliNotifyHook2;
  }
  v16.hmodCur = Library;
  if ( v13 )
    ProcAddress = (INT_PTR (__stdcall *)())((__int64 (__fastcall *)(__int64, struct DelayLoadInfo *))v13)(2, &v16);
  if ( !ProcAddress )
  {
    if ( !a1->rvaBoundIAT
      || !a1->dwTimeStamp
      || (v15 = *((int *)Library + 15), *(_DWORD *)((char *)Library + v15) != 17744)
      || *(_DWORD *)((char *)Library + v15 + 8) != (_DWORD)Arguments
      || Library != *(HMODULE *)((char *)Library + v15 + 48)
      || (ProcAddress = *(INT_PTR (__stdcall **)())&v7[8 * v11]) == 0 )
    {
      ProcAddress = GetProcAddress(Library, v16.dlp.szProcName);
      if ( !ProcAddress )
      {
        v16.dwLastError = GetLastError();
        if ( !_pfnDliFailureHook2 || (ProcAddress = _pfnDliFailureHook2(4u, &v16)) == 0 )
        {
          Arguments = (ULONG_PTR)&v16;
          DloadReleaseSectionWriteAccess();
          RaiseException(0xC06D007F, 0, 1u, &Arguments);
          DloadAcquireSectionWriteAccess();
          ProcAddress = v16.pfnCur;
        }
      }
    }
  }
  sub_18013EE88(a2, 8u);
LABEL_33:
  if ( _pfnDliNotifyHook2 )
  {
    v16.dwLastError = 0;
    v16.hmodCur = Library;
    v16.pfnCur = ProcAddress;
    _pfnDliNotifyHook2(5u, &v16);
  }
  DloadReleaseSectionWriteAccess();
  return ProcAddress;
}

```

## disassembly

```asm
0x18013f3b0  mov     [rsp-28h+arg_8], rbx
0x18013f3b5  mov     [rsp-28h+arg_10], rsi
0x18013f3ba  mov     [rsp-28h+arg_18], rdi
0x18013f3bf  push    rbp
0x18013f3c0  push    r12
0x18013f3c2  push    r13
0x18013f3c4  push    r14
0x18013f3c6  push    r15
0x18013f3c8  mov     rbp, rsp
0x18013f3cb  sub     rsp, 80h
0x18013f3d2  mov     r15, rdx
0x18013f3d5  mov     rsi, rcx
0x18013f3d8  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18013f3dd  mov     eax, [rsi+4]
0x18013f3e0  lea     r8, __NULL_IMPORT_DESCRIPTOR
0x18013f3e7  mov     r14d, [rsi+8]
0x18013f3eb  add     rax, r8
0x18013f3ee  mov     edx, [rsi+0Ch]
0x18013f3f1  add     r14, r8
0x18013f3f4  mov     ecx, [rsi+10h]
0x18013f3f7  add     rdx, r8
0x18013f3fa  mov     r13d, [rsi+14h]
0x18013f3fe  add     rcx, r8
0x18013f401  add     r13, r8
0x18013f404  mov     [rbp+lpLibFileName], rax
0x18013f408  mov     eax, [rsi]
0x18013f40a  xorps   xmm0, xmm0
0x18013f40d  mov     r8d, [rsi+1Ch]
0x18013f411  mov     dword ptr [rbp+Arguments], r8d
0x18013f415  mov     [rbp+var_50], 48h ; 'H'
0x18013f41c  mov     [rbp+var_48], rsi
0x18013f420  mov     [rbp+var_40], r15
0x18013f424  mov     [rbp+var_20], 0
0x18013f42c  mov     [rbp+var_18], 0
0x18013f434  mov     [rbp+var_10], 0
0x18013f43b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18013f43f  test    al, 1
0x18013f441  jnz     short loc_18013F46C
0x18013f443  lea     rax, [rbp+var_50]
0x18013f447  mov     [rbp+Arguments], rax
0x18013f44b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18013f450  xor     edx, edx; dwExceptionFlags
0x18013f452  lea     r9, [rbp+Arguments]; lpArguments
0x18013f456  mov     ecx, 0C06D0057h; dwExceptionCode
0x18013f45b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18013f45f  call    cs:__imp_RaiseException
0x18013f465  xor     eax, eax
0x18013f467  jmp     loc_18013F689
0x18013f46c  mov     rbx, [r14]
0x18013f46f  mov     r12, r15
0x18013f472  sub     r12, rdx
0x18013f475  sar     r12, 3
0x18013f479  mov     r12d, r12d
0x18013f47c  mov     rax, [rcx+r12*8]
0x18013f480  shr     rax, 3Fh
0x18013f484  xor     eax, 1
0x18013f487  mov     dword ptr [rbp+lpProcName], eax
0x18013f48a  jz      short loc_18013F4A0
0x18013f48c  mov     eax, [rcx+r12*8]
0x18013f490  lea     rcx, word_180000002
0x18013f497  add     rax, rcx
0x18013f49a  mov     [rbp+lpProcName+8], rax
0x18013f49e  jmp     short loc_18013F4A8
0x18013f4a0  movzx   eax, word ptr [rcx+r12*8]
0x18013f4a5  mov     dword ptr [rbp+lpProcName+8], eax
0x18013f4a8  mov     rax, cs:__pfnDliNotifyHook2
0x18013f4af  xor     edi, edi
0x18013f4b1  test    rax, rax
0x18013f4b4  jz      short loc_18013F4D5
0x18013f4b6  lea     rdx, [rbp+var_50]
0x18013f4ba  xor     ecx, ecx
0x18013f4bc  call    cs:__guard_dispatch_icall_fptr
0x18013f4c2  mov     rdi, rax
0x18013f4c5  test    rax, rax
0x18013f4c8  jnz     loc_18013F657
0x18013f4ce  mov     rax, cs:__pfnDliNotifyHook2
0x18013f4d5  test    rbx, rbx
0x18013f4d8  jnz     loc_18013F57F
0x18013f4de  test    rax, rax
0x18013f4e1  jz      short loc_18013F4F8
0x18013f4e3  lea     rdx, [rbp+var_50]
0x18013f4e7  lea     ecx, [rbx+1]
0x18013f4ea  call    cs:__guard_dispatch_icall_fptr
0x18013f4f0  mov     rbx, rax
0x18013f4f3  test    rax, rax
0x18013f4f6  jnz     short loc_18013F564
0x18013f4f8  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18013f4fc  xor     r8d, r8d; dwFlags
0x18013f4ff  xor     edx, edx; hFile
0x18013f501  call    cs:__imp_LoadLibraryExA
0x18013f507  mov     rbx, rax
0x18013f50a  test    rax, rax
0x18013f50d  jnz     short loc_18013F564
0x18013f50f  call    cs:__imp_GetLastError
0x18013f515  mov     [rbp+var_10], eax
0x18013f518  mov     rax, cs:__pfnDliFailureHook2
0x18013f51f  test    rax, rax
0x18013f522  jz      short loc_18013F539
0x18013f524  lea     rdx, [rbp+var_50]
0x18013f528  lea     ecx, [rbx+3]
0x18013f52b  call    cs:__guard_dispatch_icall_fptr
0x18013f531  mov     rbx, rax
0x18013f534  test    rax, rax
0x18013f537  jnz     short loc_18013F564
0x18013f539  lea     rax, [rbp+var_50]
0x18013f53d  mov     [rbp+Arguments], rax
0x18013f541  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18013f546  xor     edx, edx; dwExceptionFlags
0x18013f548  lea     r9, [rbp+Arguments]; lpArguments
0x18013f54c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18013f551  lea     r8d, [rdx+1]; nNumberOfArguments
0x18013f555  call    cs:__imp_RaiseException
0x18013f55b  mov     rax, [rbp+var_18]
0x18013f55f  jmp     loc_18013F689
0x18013f564  mov     rax, rbx
0x18013f567  xchg    rax, [r14]
0x18013f56a  cmp     rax, rbx
0x18013f56d  jnz     short loc_18013F578
0x18013f56f  mov     rcx, rbx; hLibModule
0x18013f572  call    cs:__imp_FreeLibrary
0x18013f578  mov     rax, cs:__pfnDliNotifyHook2
0x18013f57f  mov     [rbp+var_20], rbx
0x18013f583  test    rax, rax
0x18013f586  jz      short loc_18013F59A
0x18013f588  lea     rdx, [rbp+var_50]
0x18013f58c  mov     ecx, 2
0x18013f591  call    cs:__guard_dispatch_icall_fptr
0x18013f597  mov     rdi, rax
0x18013f59a  test    rdi, rdi
0x18013f59d  jnz     loc_18013F63E
0x18013f5a3  cmp     [rsi+14h], edi
0x18013f5a6  jz      short loc_18013F5D4
0x18013f5a8  cmp     [rsi+1Ch], edi
0x18013f5ab  jz      short loc_18013F5D4
0x18013f5ad  movsxd  rax, dword ptr [rbx+3Ch]
0x18013f5b1  cmp     dword ptr [rax+rbx], 4550h
0x18013f5b8  jnz     short loc_18013F5D4
0x18013f5ba  mov     ecx, dword ptr [rbp+Arguments]
0x18013f5bd  cmp     [rax+rbx+8], ecx
0x18013f5c1  jnz     short loc_18013F5D4
0x18013f5c3  cmp     rbx, [rax+rbx+30h]
0x18013f5c8  jnz     short loc_18013F5D4
0x18013f5ca  mov     rdi, [r13+r12*8+0]
0x18013f5cf  test    rdi, rdi
0x18013f5d2  jnz     short loc_18013F63E
0x18013f5d4  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x18013f5d8  mov     rcx, rbx; hModule
0x18013f5db  call    cs:__imp_GetProcAddress
0x18013f5e1  mov     rdi, rax
0x18013f5e4  test    rax, rax
0x18013f5e7  jnz     short loc_18013F63E
0x18013f5e9  call    cs:__imp_GetLastError
0x18013f5ef  mov     [rbp+var_10], eax
0x18013f5f2  mov     rax, cs:__pfnDliFailureHook2
0x18013f5f9  test    rax, rax
0x18013f5fc  jz      short loc_18013F613
0x18013f5fe  lea     rdx, [rbp+var_50]
0x18013f602  lea     ecx, [rdi+4]
0x18013f605  call    cs:__guard_dispatch_icall_fptr
0x18013f60b  mov     rdi, rax
0x18013f60e  test    rax, rax
0x18013f611  jnz     short loc_18013F63E
0x18013f613  lea     rax, [rbp+var_50]
0x18013f617  mov     [rbp+Arguments], rax
0x18013f61b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18013f620  xor     edx, edx; dwExceptionFlags
0x18013f622  lea     r9, [rbp+Arguments]; lpArguments
0x18013f626  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18013f62b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18013f62f  call    cs:__imp_RaiseException
0x18013f635  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18013f63a  mov     rdi, [rbp+var_18]
0x18013f63e  lea     r8, [rbp+var_60]
0x18013f642  mov     [rbp+var_60], r15
0x18013f646  mov     edx, 8; dwSize
0x18013f64b  mov     [rbp+var_58], rdi
0x18013f64f  mov     rcx, r15; lpAddress
0x18013f652  call    sub_18013EE88
0x18013f657  mov     rax, cs:__pfnDliNotifyHook2
0x18013f65e  test    rax, rax
0x18013f661  jz      short loc_18013F681
0x18013f663  lea     rdx, [rbp+var_50]
0x18013f667  mov     [rbp+var_10], 0
0x18013f66e  mov     ecx, 5
0x18013f673  mov     [rbp+var_20], rbx
0x18013f677  mov     [rbp+var_18], rdi
0x18013f67b  call    cs:__guard_dispatch_icall_fptr
0x18013f681  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18013f686  mov     rax, rdi
0x18013f689  lea     r11, [rsp+80h+var_s0]
0x18013f691  mov     rbx, [r11+38h]
0x18013f695  mov     rsi, [r11+40h]
0x18013f699  mov     rdi, [r11+48h]
0x18013f69d  mov     rsp, r11
0x18013f6a0  pop     r15
0x18013f6a2  pop     r14
0x18013f6a4  pop     r13
0x18013f6a6  pop     r12
0x18013f6a8  pop     rbp
0x18013f6a9  retn
```
