# __delayLoadHelper2

- ea: `0x180046dc0`
- end: `0x1800470f4`
- name: `__delayLoadHelper2`
- size: `820`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009442`

## callees

- `0x1800093c4`
- `0x180046b5c`
- `0x180046d5c`
- `0x180046dc0`
- `0x18004a010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180046e6f`
- `KERNEL32!RaiseException` at `0x180046f73`
- `KERNEL32!RaiseException` at `0x18004709f`
- `KERNEL32!RaiseException` at `0x180046e6f`
- `KERNEL32!RaiseException` at `0x180046f73`
- `KERNEL32!RaiseException` at `0x18004709f`
- `KERNEL32!LoadLibraryExA` at `0x180046f20`
- `KERNEL32!LoadLibraryExA` at `0x180046f20`
- `KERNEL32!FreeLibrary` at `0x180046fd7`
- `KERNEL32!FreeLibrary` at `0x180046fd7`
- `KERNEL32!GetProcessHeap` at `0x180046f9a`
- `KERNEL32!GetProcessHeap` at `0x180046f9a`
- `KERNEL32!GetProcAddress` at `0x18004704c`
- `KERNEL32!GetProcAddress` at `0x18004704c`
- `KERNEL32!HeapAlloc` at `0x180046fac`
- `KERNEL32!HeapAlloc` at `0x180046fac`
- `KERNEL32!GetLastError` at `0x180046f2e`
- `KERNEL32!GetLastError` at `0x18004705a`
- `KERNEL32!GetLastError` at `0x180046f2e`
- `KERNEL32!GetLastError` at `0x18004705a`

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
0x180046dc0  push    rbp
0x180046dc2  push    rbx
0x180046dc3  push    rsi
0x180046dc4  push    rdi
0x180046dc5  push    r12
0x180046dc7  push    r13
0x180046dc9  push    r14
0x180046dcb  push    r15
0x180046dcd  mov     rbp, rsp
0x180046dd0  sub     rsp, 78h
0x180046dd4  xor     eax, eax
0x180046dd6  mov     r12, rdx
0x180046dd9  mov     rsi, rcx
0x180046ddc  mov     [rbp+var_54], eax
0x180046ddf  xor     edx, edx; Val
0x180046de1  lea     rcx, [rbp+var_58]; void *
0x180046de5  lea     r8d, [rax+44h]; Size
0x180046de9  call    memset_0
0x180046dee  call    DloadAcquireSectionWriteAccess
0x180046df3  mov     eax, [rsi+4]
0x180046df6  lea     rdx, __ImageBase
0x180046dfd  mov     r14d, [rsi+8]
0x180046e01  add     rax, rdx
0x180046e04  mov     r15d, [rsi+14h]
0x180046e08  add     r14, rdx
0x180046e0b  mov     ecx, [rsi+1Ch]
0x180046e0e  add     r15, rdx
0x180046e11  mov     [rbp+lpLibFileName], rax
0x180046e15  mov     eax, [rsi]
0x180046e17  mov     dword ptr [rbp+Arguments], ecx
0x180046e1a  mov     [rbp+var_58], 48h ; 'H'
0x180046e21  mov     [rbp+var_50], rsi
0x180046e25  mov     [rbp+var_48], r12
0x180046e29  mov     [rbp+var_38], 0
0x180046e30  mov     [rbp+lpProcName], 0
0x180046e38  mov     [rbp+var_28], 0
0x180046e40  mov     [rbp+var_20], 0
0x180046e48  mov     [rbp+var_18], 0
0x180046e4f  test    al, 1
0x180046e51  jnz     short loc_180046E7C
0x180046e53  lea     rax, [rbp+var_58]
0x180046e57  mov     [rbp+Arguments], rax
0x180046e5b  call    DloadReleaseSectionWriteAccess
0x180046e60  xor     edx, edx; dwExceptionFlags
0x180046e62  lea     r9, [rbp+Arguments]; lpArguments
0x180046e66  mov     ecx, 0C06D0057h; dwExceptionCode
0x180046e6b  lea     r8d, [rdx+1]; nNumberOfArguments
0x180046e6f  call    cs:__imp_RaiseException
0x180046e75  xor     eax, eax
0x180046e77  jmp     loc_1800470E3
0x180046e7c  mov     eax, [rsi+0Ch]
0x180046e7f  mov     rcx, r12
0x180046e82  mov     rbx, [r14]
0x180046e85  sub     rcx, rax
0x180046e88  sub     rcx, rdx
0x180046e8b  sar     rcx, 3
0x180046e8f  mov     eax, ecx
0x180046e91  mov     ecx, [rsi+10h]
0x180046e94  lea     r13, ds:0[rax*8]
0x180046e9c  xor     eax, eax
0x180046e9e  add     rcx, r13
0x180046ea1  cmp     [rcx+rdx], rax
0x180046ea5  setnl   al
0x180046ea8  mov     [rbp+var_38], eax
0x180046eab  test    eax, eax
0x180046ead  jz      short loc_180046EC2
0x180046eaf  mov     eax, [rcx+rdx]
0x180046eb2  lea     rdx, word_180000002
0x180046eb9  add     rax, rdx
0x180046ebc  mov     [rbp+lpProcName], rax
0x180046ec0  jmp     short loc_180046EC9
0x180046ec2  movzx   eax, word ptr [rcx+rdx]
0x180046ec6  mov     dword ptr [rbp+lpProcName], eax
0x180046ec9  mov     rax, cs:__pfnDliNotifyHook2
0x180046ed0  xor     edi, edi
0x180046ed2  test    rax, rax
0x180046ed5  jz      short loc_180046EF5
0x180046ed7  lea     rdx, [rbp+var_58]
0x180046edb  xor     ecx, ecx
0x180046edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ee2  mov     rdi, rax
0x180046ee5  test    rax, rax
0x180046ee8  mov     rax, cs:__pfnDliNotifyHook2
0x180046eef  jnz     loc_1800470B9
0x180046ef5  test    rbx, rbx
0x180046ef8  jnz     loc_180046FEB
0x180046efe  test    rax, rax
0x180046f01  jz      short loc_180046F17
0x180046f03  lea     rdx, [rbp+var_58]
0x180046f07  lea     ecx, [rbx+1]
0x180046f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f0f  mov     rbx, rax
0x180046f12  test    rax, rax
0x180046f15  jnz     short loc_180046F82
0x180046f17  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x180046f1b  xor     r8d, r8d; dwFlags
0x180046f1e  xor     edx, edx; hFile
0x180046f20  call    cs:__imp_LoadLibraryExA
0x180046f26  mov     rbx, rax
0x180046f29  test    rax, rax
0x180046f2c  jnz     short loc_180046F82
0x180046f2e  call    cs:__imp_GetLastError
0x180046f34  mov     [rbp+var_18], eax
0x180046f37  mov     rax, cs:__pfnDefaultDliFailureHook2
0x180046f3e  test    rax, rax
0x180046f41  jz      short loc_180046F57
0x180046f43  lea     rdx, [rbp+var_58]
0x180046f47  lea     ecx, [rbx+3]
0x180046f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f4f  mov     rbx, rax
0x180046f52  test    rax, rax
0x180046f55  jnz     short loc_180046F82
0x180046f57  lea     rax, [rbp+var_58]
0x180046f5b  mov     [rbp+Arguments], rax
0x180046f5f  call    DloadReleaseSectionWriteAccess
0x180046f64  xor     edx, edx; dwExceptionFlags
0x180046f66  lea     r9, [rbp+Arguments]; lpArguments
0x180046f6a  mov     ecx, 0C06D007Eh; dwExceptionCode
0x180046f6f  lea     r8d, [rdx+1]; nNumberOfArguments
0x180046f73  call    cs:__imp_RaiseException
0x180046f79  mov     rax, [rbp+var_20]
0x180046f7d  jmp     loc_1800470E3
0x180046f82  xor     eax, eax
0x180046f84  lock cmpxchg [r14], rbx
0x180046f89  mov     r14, rax
0x180046f8c  jnz     short loc_180046FCE
0x180046f8e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180046f92  jz      short loc_180046FE4
0x180046f94  cmp     dword ptr [rsi+18h], 0
0x180046f98  jz      short loc_180046FE4
0x180046f9a  call    cs:__imp_GetProcessHeap
0x180046fa0  mov     edx, 8; dwFlags
0x180046fa5  mov     rcx, rax; hHeap
0x180046fa8  lea     r8d, [rdx+8]; dwBytes
0x180046fac  call    cs:__imp_HeapAlloc
0x180046fb2  test    rax, rax
0x180046fb5  jz      short loc_180046FE4
0x180046fb7  mov     [rax+8], rsi
0x180046fbb  mov     rcx, cs:__puiHead
0x180046fc2  mov     [rax], rcx
0x180046fc5  mov     cs:__puiHead, rax
0x180046fcc  jmp     short loc_180046FE4
0x180046fce  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180046fd2  jz      short loc_180046FDD
0x180046fd4  mov     rcx, rbx; hLibModule
0x180046fd7  call    cs:__imp_FreeLibrary
0x180046fdd  cmp     rbx, r14
0x180046fe0  cmovnz  rbx, r14
0x180046fe4  mov     rax, cs:__pfnDliNotifyHook2
0x180046feb  mov     [rbp+var_28], rbx
0x180046fef  test    rax, rax
0x180046ff2  jz      short loc_18004700C
0x180046ff4  lea     rdx, [rbp+var_58]
0x180046ff8  mov     ecx, 2
0x180046ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047002  mov     rdi, rax
0x180047005  mov     rax, cs:__pfnDliNotifyHook2
0x18004700c  test    rdi, rdi
0x18004700f  jnz     loc_1800470B5
0x180047015  cmp     [rsi+14h], edi
0x180047018  jz      short loc_180047045
0x18004701a  cmp     [rsi+1Ch], edi
0x18004701d  jz      short loc_180047045
0x18004701f  movsxd  rcx, dword ptr [rbx+3Ch]
0x180047023  cmp     dword ptr [rcx+rbx], 4550h
0x18004702a  jnz     short loc_180047045
0x18004702c  mov     edx, dword ptr [rbp+Arguments]
0x18004702f  cmp     [rcx+rbx+8], edx
0x180047033  jnz     short loc_180047045
0x180047035  cmp     rbx, [rcx+rbx+30h]
0x18004703a  jnz     short loc_180047045
0x18004703c  mov     rdi, [r15+r13]
0x180047040  test    rdi, rdi
0x180047043  jnz     short loc_1800470B5
0x180047045  mov     rdx, [rbp+lpProcName]; lpProcName
0x180047049  mov     rcx, rbx; hModule
0x18004704c  call    cs:__imp_GetProcAddress
0x180047052  mov     rdi, rax
0x180047055  test    rax, rax
0x180047058  jnz     short loc_1800470AE
0x18004705a  call    cs:__imp_GetLastError
0x180047060  mov     [rbp+var_18], eax
0x180047063  mov     rax, cs:__pfnDefaultDliFailureHook2
0x18004706a  test    rax, rax
0x18004706d  jz      short loc_180047083
0x18004706f  lea     rdx, [rbp+var_58]
0x180047073  lea     ecx, [rdi+4]
0x180047076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004707b  mov     rdi, rax
0x18004707e  test    rax, rax
0x180047081  jnz     short loc_1800470AE
0x180047083  lea     rax, [rbp+var_58]
0x180047087  mov     [rbp+Arguments], rax
0x18004708b  call    DloadReleaseSectionWriteAccess
0x180047090  xor     edx, edx; dwExceptionFlags
0x180047092  lea     r9, [rbp+Arguments]; lpArguments
0x180047096  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18004709b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18004709f  call    cs:__imp_RaiseException
0x1800470a5  call    DloadAcquireSectionWriteAccess
0x1800470aa  mov     rdi, [rbp+var_20]
0x1800470ae  mov     rax, cs:__pfnDliNotifyHook2
0x1800470b5  mov     [r12], rdi
0x1800470b9  test    rax, rax
0x1800470bc  jz      short loc_1800470DB
0x1800470be  lea     rdx, [rbp+var_58]
0x1800470c2  mov     [rbp+var_18], 0
0x1800470c9  mov     ecx, 5
0x1800470ce  mov     [rbp+var_28], rbx
0x1800470d2  mov     [rbp+var_20], rdi
0x1800470d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800470db  call    DloadReleaseSectionWriteAccess
0x1800470e0  mov     rax, rdi
0x1800470e3  add     rsp, 78h
0x1800470e7  pop     r15
0x1800470e9  pop     r14
0x1800470eb  pop     r13
0x1800470ed  pop     r12
0x1800470ef  pop     rdi
0x1800470f0  pop     rsi
0x1800470f1  pop     rbx
0x1800470f2  pop     rbp
0x1800470f3  retn
```
