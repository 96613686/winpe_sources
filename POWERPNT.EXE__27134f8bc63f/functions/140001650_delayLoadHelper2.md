# __delayLoadHelper2

- ea: `0x140001650`
- end: `0x14000194a`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1400015d0`
- `0x1400019fe`

## callees

- `0x140001540`
- `0x140001650`
- `0x14000194c`
- `0x140001e10`
- `0x140002090`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400017af`
- `KERNEL32!GetLastError` at `0x140001889`
- `KERNEL32!GetLastError` at `0x1400017af`
- `KERNEL32!GetLastError` at `0x140001889`
- `KERNEL32!GetProcAddress` at `0x14000187b`
- `KERNEL32!GetProcAddress` at `0x14000187b`
- `KERNEL32!LoadLibraryExA` at `0x1400017a1`
- `KERNEL32!LoadLibraryExA` at `0x1400017a1`
- `KERNEL32!FreeLibrary` at `0x140001812`
- `KERNEL32!FreeLibrary` at `0x140001812`
- `KERNEL32!RaiseException` at `0x1400016ff`
- `KERNEL32!RaiseException` at `0x1400017f5`
- `KERNEL32!RaiseException` at `0x1400018cf`
- `KERNEL32!RaiseException` at `0x1400016ff`
- `KERNEL32!RaiseException` at `0x1400017f5`
- `KERNEL32!RaiseException` at `0x1400018cf`

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
  v4 = (volatile __int64 *)((char *)&_NULL_IMPORT_DESCRIPTOR.unused + a1->rvaHmod);
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
    v16.dlp.szProcName = (char *)&_NULL_IMPORT_DESCRIPTOR.unused + *(unsigned int *)&v6[8 * v11] + 2;
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
  sub_140001E10(a2, 8u);
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
0x140001650  mov     [rsp-28h+arg_8], rbx
0x140001655  mov     [rsp-28h+arg_10], rsi
0x14000165a  mov     [rsp-28h+arg_18], rdi
0x14000165f  push    rbp
0x140001660  push    r12
0x140001662  push    r13
0x140001664  push    r14
0x140001666  push    r15
0x140001668  mov     rbp, rsp
0x14000166b  sub     rsp, 80h
0x140001672  mov     r15, rdx
0x140001675  mov     rsi, rcx
0x140001678  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x14000167d  mov     eax, [rsi+4]
0x140001680  lea     r8, __NULL_IMPORT_DESCRIPTOR
0x140001687  mov     r14d, [rsi+8]
0x14000168b  add     rax, r8
0x14000168e  mov     edx, [rsi+0Ch]
0x140001691  add     r14, r8
0x140001694  mov     ecx, [rsi+10h]
0x140001697  add     rdx, r8
0x14000169a  mov     r13d, [rsi+14h]
0x14000169e  add     rcx, r8
0x1400016a1  add     r13, r8
0x1400016a4  mov     [rbp+lpLibFileName], rax
0x1400016a8  mov     eax, [rsi]
0x1400016aa  xorps   xmm0, xmm0
0x1400016ad  mov     r8d, [rsi+1Ch]
0x1400016b1  mov     dword ptr [rbp+Arguments], r8d
0x1400016b5  mov     [rbp+var_50], 48h ; 'H'
0x1400016bc  mov     [rbp+var_48], rsi
0x1400016c0  mov     [rbp+var_40], r15
0x1400016c4  mov     [rbp+var_20], 0
0x1400016cc  mov     [rbp+var_18], 0
0x1400016d4  mov     [rbp+var_10], 0
0x1400016db  movups  xmmword ptr [rbp+lpProcName], xmm0
0x1400016df  test    al, 1
0x1400016e1  jnz     short loc_14000170C
0x1400016e3  lea     rax, [rbp+var_50]
0x1400016e7  mov     [rbp+Arguments], rax
0x1400016eb  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1400016f0  xor     edx, edx; dwExceptionFlags
0x1400016f2  lea     r9, [rbp+Arguments]; lpArguments
0x1400016f6  mov     ecx, 0C06D0057h; dwExceptionCode
0x1400016fb  lea     r8d, [rdx+1]; nNumberOfArguments
0x1400016ff  call    cs:__imp_RaiseException
0x140001705  xor     eax, eax
0x140001707  jmp     loc_140001929
0x14000170c  mov     rbx, [r14]
0x14000170f  mov     r12, r15
0x140001712  sub     r12, rdx
0x140001715  sar     r12, 3
0x140001719  mov     r12d, r12d
0x14000171c  mov     rax, [rcx+r12*8]
0x140001720  shr     rax, 3Fh
0x140001724  xor     eax, 1
0x140001727  mov     dword ptr [rbp+lpProcName], eax
0x14000172a  jz      short loc_140001740
0x14000172c  mov     eax, [rcx+r12*8]
0x140001730  lea     rcx, __NULL_IMPORT_DESCRIPTOR.unused+2
0x140001737  add     rax, rcx
0x14000173a  mov     [rbp+lpProcName+8], rax
0x14000173e  jmp     short loc_140001748
0x140001740  movzx   eax, word ptr [rcx+r12*8]
0x140001745  mov     dword ptr [rbp+lpProcName+8], eax
0x140001748  mov     rax, cs:__pfnDliNotifyHook2
0x14000174f  xor     edi, edi
0x140001751  test    rax, rax
0x140001754  jz      short loc_140001775
0x140001756  lea     rdx, [rbp+var_50]
0x14000175a  xor     ecx, ecx
0x14000175c  call    cs:__guard_dispatch_icall_fptr
0x140001762  mov     rdi, rax
0x140001765  test    rax, rax
0x140001768  jnz     loc_1400018F7
0x14000176e  mov     rax, cs:__pfnDliNotifyHook2
0x140001775  test    rbx, rbx
0x140001778  jnz     loc_14000181F
0x14000177e  test    rax, rax
0x140001781  jz      short loc_140001798
0x140001783  lea     rdx, [rbp+var_50]
0x140001787  lea     ecx, [rbx+1]
0x14000178a  call    cs:__guard_dispatch_icall_fptr
0x140001790  mov     rbx, rax
0x140001793  test    rax, rax
0x140001796  jnz     short loc_140001804
0x140001798  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x14000179c  xor     r8d, r8d; dwFlags
0x14000179f  xor     edx, edx; hFile
0x1400017a1  call    cs:__imp_LoadLibraryExA
0x1400017a7  mov     rbx, rax
0x1400017aa  test    rax, rax
0x1400017ad  jnz     short loc_140001804
0x1400017af  call    cs:__imp_GetLastError
0x1400017b5  mov     [rbp+var_10], eax
0x1400017b8  mov     rax, cs:__pfnDliFailureHook2
0x1400017bf  test    rax, rax
0x1400017c2  jz      short loc_1400017D9
0x1400017c4  lea     rdx, [rbp+var_50]
0x1400017c8  lea     ecx, [rbx+3]
0x1400017cb  call    cs:__guard_dispatch_icall_fptr
0x1400017d1  mov     rbx, rax
0x1400017d4  test    rax, rax
0x1400017d7  jnz     short loc_140001804
0x1400017d9  lea     rax, [rbp+var_50]
0x1400017dd  mov     [rbp+Arguments], rax
0x1400017e1  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1400017e6  xor     edx, edx; dwExceptionFlags
0x1400017e8  lea     r9, [rbp+Arguments]; lpArguments
0x1400017ec  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1400017f1  lea     r8d, [rdx+1]; nNumberOfArguments
0x1400017f5  call    cs:__imp_RaiseException
0x1400017fb  mov     rax, [rbp+var_18]
0x1400017ff  jmp     loc_140001929
0x140001804  mov     rax, rbx
0x140001807  xchg    rax, [r14]
0x14000180a  cmp     rax, rbx
0x14000180d  jnz     short loc_140001818
0x14000180f  mov     rcx, rbx; hLibModule
0x140001812  call    cs:__imp_FreeLibrary
0x140001818  mov     rax, cs:__pfnDliNotifyHook2
0x14000181f  mov     [rbp+var_20], rbx
0x140001823  test    rax, rax
0x140001826  jz      short loc_14000183A
0x140001828  lea     rdx, [rbp+var_50]
0x14000182c  mov     ecx, 2
0x140001831  call    cs:__guard_dispatch_icall_fptr
0x140001837  mov     rdi, rax
0x14000183a  test    rdi, rdi
0x14000183d  jnz     loc_1400018DE
0x140001843  cmp     [rsi+14h], edi
0x140001846  jz      short loc_140001874
0x140001848  cmp     [rsi+1Ch], edi
0x14000184b  jz      short loc_140001874
0x14000184d  movsxd  rax, dword ptr [rbx+3Ch]
0x140001851  cmp     dword ptr [rax+rbx], 4550h
0x140001858  jnz     short loc_140001874
0x14000185a  mov     ecx, dword ptr [rbp+Arguments]
0x14000185d  cmp     [rax+rbx+8], ecx
0x140001861  jnz     short loc_140001874
0x140001863  cmp     rbx, [rax+rbx+30h]
0x140001868  jnz     short loc_140001874
0x14000186a  mov     rdi, [r13+r12*8+0]
0x14000186f  test    rdi, rdi
0x140001872  jnz     short loc_1400018DE
0x140001874  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x140001878  mov     rcx, rbx; hModule
0x14000187b  call    cs:__imp_GetProcAddress
0x140001881  mov     rdi, rax
0x140001884  test    rax, rax
0x140001887  jnz     short loc_1400018DE
0x140001889  call    cs:__imp_GetLastError
0x14000188f  mov     [rbp+var_10], eax
0x140001892  mov     rax, cs:__pfnDliFailureHook2
0x140001899  test    rax, rax
0x14000189c  jz      short loc_1400018B3
0x14000189e  lea     rdx, [rbp+var_50]
0x1400018a2  lea     ecx, [rdi+4]
0x1400018a5  call    cs:__guard_dispatch_icall_fptr
0x1400018ab  mov     rdi, rax
0x1400018ae  test    rax, rax
0x1400018b1  jnz     short loc_1400018DE
0x1400018b3  lea     rax, [rbp+var_50]
0x1400018b7  mov     [rbp+Arguments], rax
0x1400018bb  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1400018c0  xor     edx, edx; dwExceptionFlags
0x1400018c2  lea     r9, [rbp+Arguments]; lpArguments
0x1400018c6  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1400018cb  lea     r8d, [rdx+1]; nNumberOfArguments
0x1400018cf  call    cs:__imp_RaiseException
0x1400018d5  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1400018da  mov     rdi, [rbp+var_18]
0x1400018de  lea     r8, [rbp+var_60]
0x1400018e2  mov     [rbp+var_60], r15
0x1400018e6  mov     edx, 8; dwSize
0x1400018eb  mov     [rbp+var_58], rdi
0x1400018ef  mov     rcx, r15; lpAddress
0x1400018f2  call    sub_140001E10
0x1400018f7  mov     rax, cs:__pfnDliNotifyHook2
0x1400018fe  test    rax, rax
0x140001901  jz      short loc_140001921
0x140001903  lea     rdx, [rbp+var_50]
0x140001907  mov     [rbp+var_10], 0
0x14000190e  mov     ecx, 5
0x140001913  mov     [rbp+var_20], rbx
0x140001917  mov     [rbp+var_18], rdi
0x14000191b  call    cs:__guard_dispatch_icall_fptr
0x140001921  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140001926  mov     rax, rdi
0x140001929  lea     r11, [rsp+80h+var_s0]
0x140001931  mov     rbx, [r11+38h]
0x140001935  mov     rsi, [r11+40h]
0x140001939  mov     rdi, [r11+48h]
0x14000193d  mov     rsp, r11
0x140001940  pop     r15
0x140001942  pop     r14
0x140001944  pop     r13
0x140001946  pop     r12
0x140001948  pop     rbp
0x140001949  retn
```
