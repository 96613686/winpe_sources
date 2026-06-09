# __delayLoadHelper2

- ea: `0x1803a18e0`
- end: `0x1803a1bda`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `10`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18039da06`
- `0x1803a1c36`
- `0x1803a1cc7`
- `0x1803a1d4c`
- `0x1803a1def`
- `0x1803a1e7a`
- `0x1803a1f0c`
- `0x1804f9716`
- `0x1804f9866`
- `0x1804f9926`

## callees

- `0x1803a13b8`
- `0x1803a14a4`
- `0x1803a182c`
- `0x1803a18e0`
- `0x1804f99e0`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x1803a1a31`
- `KERNEL32!LoadLibraryExA` at `0x1803a1a31`
- `KERNEL32!RaiseException` at `0x1803a198f`
- `KERNEL32!RaiseException` at `0x1803a1a85`
- `KERNEL32!RaiseException` at `0x1803a1b5f`
- `KERNEL32!RaiseException` at `0x1803a198f`
- `KERNEL32!RaiseException` at `0x1803a1a85`
- `KERNEL32!RaiseException` at `0x1803a1b5f`
- `KERNEL32!GetLastError` at `0x1803a1a3f`
- `KERNEL32!GetLastError` at `0x1803a1b19`
- `KERNEL32!GetLastError` at `0x1803a1a3f`
- `KERNEL32!GetLastError` at `0x1803a1b19`
- `KERNEL32!FreeLibrary` at `0x1803a1aa2`
- `KERNEL32!FreeLibrary` at `0x1803a1aa2`
- `KERNEL32!GetProcAddress` at `0x1803a1b0b`
- `KERNEL32!GetProcAddress` at `0x1803a1b0b`

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
  v4 = (volatile __int64 *)((char *)&_ImageBase + a1->rvaHmod);
  v5 = (char *)&_ImageBase + a1->rvaIAT;
  v6 = (char *)&_ImageBase + a1->rvaINT;
  v7 = (char *)&_ImageBase + a1->rvaBoundIAT;
  v16.szDll = (char *)&_ImageBase + a1->rvaDLLName;
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
  sub_1803A13B8(a2, 8u);
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
0x1803a18e0  mov     [rsp-28h+arg_8], rbx
0x1803a18e5  mov     [rsp-28h+arg_10], rsi
0x1803a18ea  mov     [rsp-28h+arg_18], rdi
0x1803a18ef  push    rbp
0x1803a18f0  push    r12
0x1803a18f2  push    r13
0x1803a18f4  push    r14
0x1803a18f6  push    r15
0x1803a18f8  mov     rbp, rsp
0x1803a18fb  sub     rsp, 80h
0x1803a1902  mov     r15, rdx
0x1803a1905  mov     rsi, rcx
0x1803a1908  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1803a190d  mov     eax, [rsi+4]
0x1803a1910  lea     r8, __ImageBase
0x1803a1917  mov     r14d, [rsi+8]
0x1803a191b  add     rax, r8
0x1803a191e  mov     edx, [rsi+0Ch]
0x1803a1921  add     r14, r8
0x1803a1924  mov     ecx, [rsi+10h]
0x1803a1927  add     rdx, r8
0x1803a192a  mov     r13d, [rsi+14h]
0x1803a192e  add     rcx, r8
0x1803a1931  add     r13, r8
0x1803a1934  mov     [rbp+lpLibFileName], rax
0x1803a1938  mov     eax, [rsi]
0x1803a193a  xorps   xmm0, xmm0
0x1803a193d  mov     r8d, [rsi+1Ch]
0x1803a1941  mov     dword ptr [rbp+Arguments], r8d
0x1803a1945  mov     [rbp+var_50], 48h ; 'H'
0x1803a194c  mov     [rbp+var_48], rsi
0x1803a1950  mov     [rbp+var_40], r15
0x1803a1954  mov     [rbp+var_20], 0
0x1803a195c  mov     [rbp+var_18], 0
0x1803a1964  mov     [rbp+var_10], 0
0x1803a196b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x1803a196f  test    al, 1
0x1803a1971  jnz     short loc_1803A199C
0x1803a1973  lea     rax, [rbp+var_50]
0x1803a1977  mov     [rbp+Arguments], rax
0x1803a197b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1803a1980  xor     edx, edx; dwExceptionFlags
0x1803a1982  lea     r9, [rbp+Arguments]; lpArguments
0x1803a1986  mov     ecx, 0C06D0057h; dwExceptionCode
0x1803a198b  lea     r8d, [rdx+1]; nNumberOfArguments
0x1803a198f  call    cs:__imp_RaiseException
0x1803a1995  xor     eax, eax
0x1803a1997  jmp     loc_1803A1BB9
0x1803a199c  mov     rbx, [r14]
0x1803a199f  mov     r12, r15
0x1803a19a2  sub     r12, rdx
0x1803a19a5  sar     r12, 3
0x1803a19a9  mov     r12d, r12d
0x1803a19ac  mov     rax, [rcx+r12*8]
0x1803a19b0  shr     rax, 3Fh
0x1803a19b4  xor     eax, 1
0x1803a19b7  mov     dword ptr [rbp+lpProcName], eax
0x1803a19ba  jz      short loc_1803A19D0
0x1803a19bc  mov     eax, [rcx+r12*8]
0x1803a19c0  lea     rcx, word_180000002
0x1803a19c7  add     rax, rcx
0x1803a19ca  mov     [rbp+lpProcName+8], rax
0x1803a19ce  jmp     short loc_1803A19D8
0x1803a19d0  movzx   eax, word ptr [rcx+r12*8]
0x1803a19d5  mov     dword ptr [rbp+lpProcName+8], eax
0x1803a19d8  mov     rax, cs:__pfnDliNotifyHook2
0x1803a19df  xor     edi, edi
0x1803a19e1  test    rax, rax
0x1803a19e4  jz      short loc_1803A1A05
0x1803a19e6  lea     rdx, [rbp+var_50]
0x1803a19ea  xor     ecx, ecx
0x1803a19ec  call    cs:__guard_dispatch_icall_fptr
0x1803a19f2  mov     rdi, rax
0x1803a19f5  test    rax, rax
0x1803a19f8  jnz     loc_1803A1B87
0x1803a19fe  mov     rax, cs:__pfnDliNotifyHook2
0x1803a1a05  test    rbx, rbx
0x1803a1a08  jnz     loc_1803A1AAF
0x1803a1a0e  test    rax, rax
0x1803a1a11  jz      short loc_1803A1A28
0x1803a1a13  lea     rdx, [rbp+var_50]
0x1803a1a17  lea     ecx, [rbx+1]
0x1803a1a1a  call    cs:__guard_dispatch_icall_fptr
0x1803a1a20  mov     rbx, rax
0x1803a1a23  test    rax, rax
0x1803a1a26  jnz     short loc_1803A1A94
0x1803a1a28  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1803a1a2c  xor     r8d, r8d; dwFlags
0x1803a1a2f  xor     edx, edx; hFile
0x1803a1a31  call    cs:__imp_LoadLibraryExA
0x1803a1a37  mov     rbx, rax
0x1803a1a3a  test    rax, rax
0x1803a1a3d  jnz     short loc_1803A1A94
0x1803a1a3f  call    cs:__imp_GetLastError
0x1803a1a45  mov     [rbp+var_10], eax
0x1803a1a48  mov     rax, cs:__pfnDliFailureHook2
0x1803a1a4f  test    rax, rax
0x1803a1a52  jz      short loc_1803A1A69
0x1803a1a54  lea     rdx, [rbp+var_50]
0x1803a1a58  lea     ecx, [rbx+3]
0x1803a1a5b  call    cs:__guard_dispatch_icall_fptr
0x1803a1a61  mov     rbx, rax
0x1803a1a64  test    rax, rax
0x1803a1a67  jnz     short loc_1803A1A94
0x1803a1a69  lea     rax, [rbp+var_50]
0x1803a1a6d  mov     [rbp+Arguments], rax
0x1803a1a71  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1803a1a76  xor     edx, edx; dwExceptionFlags
0x1803a1a78  lea     r9, [rbp+Arguments]; lpArguments
0x1803a1a7c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1803a1a81  lea     r8d, [rdx+1]; nNumberOfArguments
0x1803a1a85  call    cs:__imp_RaiseException
0x1803a1a8b  mov     rax, [rbp+var_18]
0x1803a1a8f  jmp     loc_1803A1BB9
0x1803a1a94  mov     rax, rbx
0x1803a1a97  xchg    rax, [r14]
0x1803a1a9a  cmp     rax, rbx
0x1803a1a9d  jnz     short loc_1803A1AA8
0x1803a1a9f  mov     rcx, rbx; hLibModule
0x1803a1aa2  call    cs:__imp_FreeLibrary
0x1803a1aa8  mov     rax, cs:__pfnDliNotifyHook2
0x1803a1aaf  mov     [rbp+var_20], rbx
0x1803a1ab3  test    rax, rax
0x1803a1ab6  jz      short loc_1803A1ACA
0x1803a1ab8  lea     rdx, [rbp+var_50]
0x1803a1abc  mov     ecx, 2
0x1803a1ac1  call    cs:__guard_dispatch_icall_fptr
0x1803a1ac7  mov     rdi, rax
0x1803a1aca  test    rdi, rdi
0x1803a1acd  jnz     loc_1803A1B6E
0x1803a1ad3  cmp     [rsi+14h], edi
0x1803a1ad6  jz      short loc_1803A1B04
0x1803a1ad8  cmp     [rsi+1Ch], edi
0x1803a1adb  jz      short loc_1803A1B04
0x1803a1add  movsxd  rax, dword ptr [rbx+3Ch]
0x1803a1ae1  cmp     dword ptr [rax+rbx], 4550h
0x1803a1ae8  jnz     short loc_1803A1B04
0x1803a1aea  mov     ecx, dword ptr [rbp+Arguments]
0x1803a1aed  cmp     [rax+rbx+8], ecx
0x1803a1af1  jnz     short loc_1803A1B04
0x1803a1af3  cmp     rbx, [rax+rbx+30h]
0x1803a1af8  jnz     short loc_1803A1B04
0x1803a1afa  mov     rdi, [r13+r12*8+0]
0x1803a1aff  test    rdi, rdi
0x1803a1b02  jnz     short loc_1803A1B6E
0x1803a1b04  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x1803a1b08  mov     rcx, rbx; hModule
0x1803a1b0b  call    cs:__imp_GetProcAddress
0x1803a1b11  mov     rdi, rax
0x1803a1b14  test    rax, rax
0x1803a1b17  jnz     short loc_1803A1B6E
0x1803a1b19  call    cs:__imp_GetLastError
0x1803a1b1f  mov     [rbp+var_10], eax
0x1803a1b22  mov     rax, cs:__pfnDliFailureHook2
0x1803a1b29  test    rax, rax
0x1803a1b2c  jz      short loc_1803A1B43
0x1803a1b2e  lea     rdx, [rbp+var_50]
0x1803a1b32  lea     ecx, [rdi+4]
0x1803a1b35  call    cs:__guard_dispatch_icall_fptr
0x1803a1b3b  mov     rdi, rax
0x1803a1b3e  test    rax, rax
0x1803a1b41  jnz     short loc_1803A1B6E
0x1803a1b43  lea     rax, [rbp+var_50]
0x1803a1b47  mov     [rbp+Arguments], rax
0x1803a1b4b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1803a1b50  xor     edx, edx; dwExceptionFlags
0x1803a1b52  lea     r9, [rbp+Arguments]; lpArguments
0x1803a1b56  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1803a1b5b  lea     r8d, [rdx+1]; nNumberOfArguments
0x1803a1b5f  call    cs:__imp_RaiseException
0x1803a1b65  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1803a1b6a  mov     rdi, [rbp+var_18]
0x1803a1b6e  lea     r8, [rbp+var_60]
0x1803a1b72  mov     [rbp+var_60], r15
0x1803a1b76  mov     edx, 8; dwSize
0x1803a1b7b  mov     [rbp+var_58], rdi
0x1803a1b7f  mov     rcx, r15; lpAddress
0x1803a1b82  call    sub_1803A13B8
0x1803a1b87  mov     rax, cs:__pfnDliNotifyHook2
0x1803a1b8e  test    rax, rax
0x1803a1b91  jz      short loc_1803A1BB1
0x1803a1b93  lea     rdx, [rbp+var_50]
0x1803a1b97  mov     [rbp+var_10], 0
0x1803a1b9e  mov     ecx, 5
0x1803a1ba3  mov     [rbp+var_20], rbx
0x1803a1ba7  mov     [rbp+var_18], rdi
0x1803a1bab  call    cs:__guard_dispatch_icall_fptr
0x1803a1bb1  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1803a1bb6  mov     rax, rdi
0x1803a1bb9  lea     r11, [rsp+80h+var_s0]
0x1803a1bc1  mov     rbx, [r11+38h]
0x1803a1bc5  mov     rsi, [r11+40h]
0x1803a1bc9  mov     rdi, [r11+48h]
0x1803a1bcd  mov     rsp, r11
0x1803a1bd0  pop     r15
0x1803a1bd2  pop     r14
0x1803a1bd4  pop     r13
0x1803a1bd6  pop     r12
0x1803a1bd8  pop     rbp
0x1803a1bd9  retn
```
