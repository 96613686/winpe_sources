# __delayLoadHelper2

- ea: `0x18002aee0`
- end: `0x18002b1da`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800258aa`
- `0x180025984`
- `0x180025a54`

## callees

- `0x18002a9bc`
- `0x18002aaa8`
- `0x18002ae30`
- `0x18002aee0`
- `0x18002b3c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002b03f`
- `KERNEL32!GetLastError` at `0x18002b119`
- `KERNEL32!GetLastError` at `0x18002b03f`
- `KERNEL32!GetLastError` at `0x18002b119`
- `KERNEL32!GetProcAddress` at `0x18002b10b`
- `KERNEL32!GetProcAddress` at `0x18002b10b`
- `KERNEL32!FreeLibrary` at `0x18002b0a2`
- `KERNEL32!FreeLibrary` at `0x18002b0a2`
- `KERNEL32!LoadLibraryExA` at `0x18002b031`
- `KERNEL32!LoadLibraryExA` at `0x18002b031`
- `KERNEL32!RaiseException` at `0x18002af8f`
- `KERNEL32!RaiseException` at `0x18002b085`
- `KERNEL32!RaiseException` at `0x18002b15f`
- `KERNEL32!RaiseException` at `0x18002af8f`
- `KERNEL32!RaiseException` at `0x18002b085`
- `KERNEL32!RaiseException` at `0x18002b15f`

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
  sub_18002A9BC(a2, 8u);
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
0x18002aee0  mov     [rsp-28h+arg_8], rbx
0x18002aee5  mov     [rsp-28h+arg_10], rsi
0x18002aeea  mov     [rsp-28h+arg_18], rdi
0x18002aeef  push    rbp
0x18002aef0  push    r12
0x18002aef2  push    r13
0x18002aef4  push    r14
0x18002aef6  push    r15
0x18002aef8  mov     rbp, rsp
0x18002aefb  sub     rsp, 80h
0x18002af02  mov     r15, rdx
0x18002af05  mov     rsi, rcx
0x18002af08  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18002af0d  mov     eax, [rsi+4]
0x18002af10  lea     r8, __NULL_IMPORT_DESCRIPTOR
0x18002af17  mov     r14d, [rsi+8]
0x18002af1b  add     rax, r8
0x18002af1e  mov     edx, [rsi+0Ch]
0x18002af21  add     r14, r8
0x18002af24  mov     ecx, [rsi+10h]
0x18002af27  add     rdx, r8
0x18002af2a  mov     r13d, [rsi+14h]
0x18002af2e  add     rcx, r8
0x18002af31  add     r13, r8
0x18002af34  mov     [rbp+lpLibFileName], rax
0x18002af38  mov     eax, [rsi]
0x18002af3a  xorps   xmm0, xmm0
0x18002af3d  mov     r8d, [rsi+1Ch]
0x18002af41  mov     dword ptr [rbp+Arguments], r8d
0x18002af45  mov     [rbp+var_50], 48h ; 'H'
0x18002af4c  mov     [rbp+var_48], rsi
0x18002af50  mov     [rbp+var_40], r15
0x18002af54  mov     [rbp+var_20], 0
0x18002af5c  mov     [rbp+var_18], 0
0x18002af64  mov     [rbp+var_10], 0
0x18002af6b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x18002af6f  test    al, 1
0x18002af71  jnz     short loc_18002AF9C
0x18002af73  lea     rax, [rbp+var_50]
0x18002af77  mov     [rbp+Arguments], rax
0x18002af7b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18002af80  xor     edx, edx; dwExceptionFlags
0x18002af82  lea     r9, [rbp+Arguments]; lpArguments
0x18002af86  mov     ecx, 0C06D0057h; dwExceptionCode
0x18002af8b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18002af8f  call    cs:__imp_RaiseException
0x18002af95  xor     eax, eax
0x18002af97  jmp     loc_18002B1B9
0x18002af9c  mov     rbx, [r14]
0x18002af9f  mov     r12, r15
0x18002afa2  sub     r12, rdx
0x18002afa5  sar     r12, 3
0x18002afa9  mov     r12d, r12d
0x18002afac  mov     rax, [rcx+r12*8]
0x18002afb0  shr     rax, 3Fh
0x18002afb4  xor     eax, 1
0x18002afb7  mov     dword ptr [rbp+lpProcName], eax
0x18002afba  jz      short loc_18002AFD0
0x18002afbc  mov     eax, [rcx+r12*8]
0x18002afc0  lea     rcx, __NULL_IMPORT_DESCRIPTOR.unused+2
0x18002afc7  add     rax, rcx
0x18002afca  mov     [rbp+lpProcName+8], rax
0x18002afce  jmp     short loc_18002AFD8
0x18002afd0  movzx   eax, word ptr [rcx+r12*8]
0x18002afd5  mov     dword ptr [rbp+lpProcName+8], eax
0x18002afd8  mov     rax, cs:__pfnDliNotifyHook2
0x18002afdf  xor     edi, edi
0x18002afe1  test    rax, rax
0x18002afe4  jz      short loc_18002B005
0x18002afe6  lea     rdx, [rbp+var_50]
0x18002afea  xor     ecx, ecx
0x18002afec  call    cs:__guard_dispatch_icall_fptr
0x18002aff2  mov     rdi, rax
0x18002aff5  test    rax, rax
0x18002aff8  jnz     loc_18002B187
0x18002affe  mov     rax, cs:__pfnDliNotifyHook2
0x18002b005  test    rbx, rbx
0x18002b008  jnz     loc_18002B0AF
0x18002b00e  test    rax, rax
0x18002b011  jz      short loc_18002B028
0x18002b013  lea     rdx, [rbp+var_50]
0x18002b017  lea     ecx, [rbx+1]
0x18002b01a  call    cs:__guard_dispatch_icall_fptr
0x18002b020  mov     rbx, rax
0x18002b023  test    rax, rax
0x18002b026  jnz     short loc_18002B094
0x18002b028  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18002b02c  xor     r8d, r8d; dwFlags
0x18002b02f  xor     edx, edx; hFile
0x18002b031  call    cs:__imp_LoadLibraryExA
0x18002b037  mov     rbx, rax
0x18002b03a  test    rax, rax
0x18002b03d  jnz     short loc_18002B094
0x18002b03f  call    cs:__imp_GetLastError
0x18002b045  mov     [rbp+var_10], eax
0x18002b048  mov     rax, cs:__pfnDliFailureHook2
0x18002b04f  test    rax, rax
0x18002b052  jz      short loc_18002B069
0x18002b054  lea     rdx, [rbp+var_50]
0x18002b058  lea     ecx, [rbx+3]
0x18002b05b  call    cs:__guard_dispatch_icall_fptr
0x18002b061  mov     rbx, rax
0x18002b064  test    rax, rax
0x18002b067  jnz     short loc_18002B094
0x18002b069  lea     rax, [rbp+var_50]
0x18002b06d  mov     [rbp+Arguments], rax
0x18002b071  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18002b076  xor     edx, edx; dwExceptionFlags
0x18002b078  lea     r9, [rbp+Arguments]; lpArguments
0x18002b07c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x18002b081  lea     r8d, [rdx+1]; nNumberOfArguments
0x18002b085  call    cs:__imp_RaiseException
0x18002b08b  mov     rax, [rbp+var_18]
0x18002b08f  jmp     loc_18002B1B9
0x18002b094  mov     rax, rbx
0x18002b097  xchg    rax, [r14]
0x18002b09a  cmp     rax, rbx
0x18002b09d  jnz     short loc_18002B0A8
0x18002b09f  mov     rcx, rbx; hLibModule
0x18002b0a2  call    cs:__imp_FreeLibrary
0x18002b0a8  mov     rax, cs:__pfnDliNotifyHook2
0x18002b0af  mov     [rbp+var_20], rbx
0x18002b0b3  test    rax, rax
0x18002b0b6  jz      short loc_18002B0CA
0x18002b0b8  lea     rdx, [rbp+var_50]
0x18002b0bc  mov     ecx, 2
0x18002b0c1  call    cs:__guard_dispatch_icall_fptr
0x18002b0c7  mov     rdi, rax
0x18002b0ca  test    rdi, rdi
0x18002b0cd  jnz     loc_18002B16E
0x18002b0d3  cmp     [rsi+14h], edi
0x18002b0d6  jz      short loc_18002B104
0x18002b0d8  cmp     [rsi+1Ch], edi
0x18002b0db  jz      short loc_18002B104
0x18002b0dd  movsxd  rax, dword ptr [rbx+3Ch]
0x18002b0e1  cmp     dword ptr [rax+rbx], 4550h
0x18002b0e8  jnz     short loc_18002B104
0x18002b0ea  mov     ecx, dword ptr [rbp+Arguments]
0x18002b0ed  cmp     [rax+rbx+8], ecx
0x18002b0f1  jnz     short loc_18002B104
0x18002b0f3  cmp     rbx, [rax+rbx+30h]
0x18002b0f8  jnz     short loc_18002B104
0x18002b0fa  mov     rdi, [r13+r12*8+0]
0x18002b0ff  test    rdi, rdi
0x18002b102  jnz     short loc_18002B16E
0x18002b104  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x18002b108  mov     rcx, rbx; hModule
0x18002b10b  call    cs:__imp_GetProcAddress
0x18002b111  mov     rdi, rax
0x18002b114  test    rax, rax
0x18002b117  jnz     short loc_18002B16E
0x18002b119  call    cs:__imp_GetLastError
0x18002b11f  mov     [rbp+var_10], eax
0x18002b122  mov     rax, cs:__pfnDliFailureHook2
0x18002b129  test    rax, rax
0x18002b12c  jz      short loc_18002B143
0x18002b12e  lea     rdx, [rbp+var_50]
0x18002b132  lea     ecx, [rdi+4]
0x18002b135  call    cs:__guard_dispatch_icall_fptr
0x18002b13b  mov     rdi, rax
0x18002b13e  test    rax, rax
0x18002b141  jnz     short loc_18002B16E
0x18002b143  lea     rax, [rbp+var_50]
0x18002b147  mov     [rbp+Arguments], rax
0x18002b14b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18002b150  xor     edx, edx; dwExceptionFlags
0x18002b152  lea     r9, [rbp+Arguments]; lpArguments
0x18002b156  mov     ecx, 0C06D007Fh; dwExceptionCode
0x18002b15b  lea     r8d, [rdx+1]; nNumberOfArguments
0x18002b15f  call    cs:__imp_RaiseException
0x18002b165  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x18002b16a  mov     rdi, [rbp+var_18]
0x18002b16e  lea     r8, [rbp+var_60]
0x18002b172  mov     [rbp+var_60], r15
0x18002b176  mov     edx, 8; dwSize
0x18002b17b  mov     [rbp+var_58], rdi
0x18002b17f  mov     rcx, r15; lpAddress
0x18002b182  call    sub_18002A9BC
0x18002b187  mov     rax, cs:__pfnDliNotifyHook2
0x18002b18e  test    rax, rax
0x18002b191  jz      short loc_18002B1B1
0x18002b193  lea     rdx, [rbp+var_50]
0x18002b197  mov     [rbp+var_10], 0
0x18002b19e  mov     ecx, 5
0x18002b1a3  mov     [rbp+var_20], rbx
0x18002b1a7  mov     [rbp+var_18], rdi
0x18002b1ab  call    cs:__guard_dispatch_icall_fptr
0x18002b1b1  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x18002b1b6  mov     rax, rdi
0x18002b1b9  lea     r11, [rsp+80h+var_s0]
0x18002b1c1  mov     rbx, [r11+38h]
0x18002b1c5  mov     rsi, [r11+40h]
0x18002b1c9  mov     rdi, [r11+48h]
0x18002b1cd  mov     rsp, r11
0x18002b1d0  pop     r15
0x18002b1d2  pop     r14
0x18002b1d4  pop     r13
0x18002b1d6  pop     r12
0x18002b1d8  pop     rbp
0x18002b1d9  retn
```
