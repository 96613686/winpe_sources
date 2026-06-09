# __delayLoadHelper2

- ea: `0x140002d30`
- end: `0x14000302a`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140001691`
- `0x14000173b`

## callees

- `0x140001020`
- `0x140002810`
- `0x1400028fc`
- `0x140002c84`
- `0x140002d30`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140002f5b`
- `KERNEL32!GetProcAddress` at `0x140002f5b`
- `KERNEL32!FreeLibrary` at `0x140002ef2`
- `KERNEL32!FreeLibrary` at `0x140002ef2`
- `KERNEL32!LoadLibraryExA` at `0x140002e81`
- `KERNEL32!LoadLibraryExA` at `0x140002e81`
- `KERNEL32!GetLastError` at `0x140002e8f`
- `KERNEL32!GetLastError` at `0x140002f69`
- `KERNEL32!GetLastError` at `0x140002e8f`
- `KERNEL32!GetLastError` at `0x140002f69`
- `KERNEL32!RaiseException` at `0x140002ddf`
- `KERNEL32!RaiseException` at `0x140002ed5`
- `KERNEL32!RaiseException` at `0x140002faf`
- `KERNEL32!RaiseException` at `0x140002ddf`
- `KERNEL32!RaiseException` at `0x140002ed5`
- `KERNEL32!RaiseException` at `0x140002faf`

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
  sub_140002810(a2, 8u);
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
0x140002d30  mov     [rsp-28h+arg_8], rbx
0x140002d35  mov     [rsp-28h+arg_10], rsi
0x140002d3a  mov     [rsp-28h+arg_18], rdi
0x140002d3f  push    rbp
0x140002d40  push    r12
0x140002d42  push    r13
0x140002d44  push    r14
0x140002d46  push    r15
0x140002d48  mov     rbp, rsp
0x140002d4b  sub     rsp, 80h
0x140002d52  mov     r15, rdx
0x140002d55  mov     rsi, rcx
0x140002d58  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x140002d5d  mov     eax, [rsi+4]
0x140002d60  lea     r8, __NULL_IMPORT_DESCRIPTOR
0x140002d67  mov     r14d, [rsi+8]
0x140002d6b  add     rax, r8
0x140002d6e  mov     edx, [rsi+0Ch]
0x140002d71  add     r14, r8
0x140002d74  mov     ecx, [rsi+10h]
0x140002d77  add     rdx, r8
0x140002d7a  mov     r13d, [rsi+14h]
0x140002d7e  add     rcx, r8
0x140002d81  add     r13, r8
0x140002d84  mov     [rbp+lpLibFileName], rax
0x140002d88  mov     eax, [rsi]
0x140002d8a  xorps   xmm0, xmm0
0x140002d8d  mov     r8d, [rsi+1Ch]
0x140002d91  mov     dword ptr [rbp+Arguments], r8d
0x140002d95  mov     [rbp+var_50], 48h ; 'H'
0x140002d9c  mov     [rbp+var_48], rsi
0x140002da0  mov     [rbp+var_40], r15
0x140002da4  mov     [rbp+var_20], 0
0x140002dac  mov     [rbp+var_18], 0
0x140002db4  mov     [rbp+var_10], 0
0x140002dbb  movups  xmmword ptr [rbp+lpProcName], xmm0
0x140002dbf  test    al, 1
0x140002dc1  jnz     short loc_140002DEC
0x140002dc3  lea     rax, [rbp+var_50]
0x140002dc7  mov     [rbp+Arguments], rax
0x140002dcb  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140002dd0  xor     edx, edx; dwExceptionFlags
0x140002dd2  lea     r9, [rbp+Arguments]; lpArguments
0x140002dd6  mov     ecx, 0C06D0057h; dwExceptionCode
0x140002ddb  lea     r8d, [rdx+1]; nNumberOfArguments
0x140002ddf  call    cs:__imp_RaiseException
0x140002de5  xor     eax, eax
0x140002de7  jmp     loc_140003009
0x140002dec  mov     rbx, [r14]
0x140002def  mov     r12, r15
0x140002df2  sub     r12, rdx
0x140002df5  sar     r12, 3
0x140002df9  mov     r12d, r12d
0x140002dfc  mov     rax, [rcx+r12*8]
0x140002e00  shr     rax, 3Fh
0x140002e04  xor     eax, 1
0x140002e07  mov     dword ptr [rbp+lpProcName], eax
0x140002e0a  jz      short loc_140002E20
0x140002e0c  mov     eax, [rcx+r12*8]
0x140002e10  lea     rcx, __NULL_IMPORT_DESCRIPTOR.unused+2
0x140002e17  add     rax, rcx
0x140002e1a  mov     [rbp+lpProcName+8], rax
0x140002e1e  jmp     short loc_140002E28
0x140002e20  movzx   eax, word ptr [rcx+r12*8]
0x140002e25  mov     dword ptr [rbp+lpProcName+8], eax
0x140002e28  mov     rax, cs:__pfnDliNotifyHook2
0x140002e2f  xor     edi, edi
0x140002e31  test    rax, rax
0x140002e34  jz      short loc_140002E55
0x140002e36  lea     rdx, [rbp+var_50]
0x140002e3a  xor     ecx, ecx
0x140002e3c  call    cs:__guard_dispatch_icall_fptr
0x140002e42  mov     rdi, rax
0x140002e45  test    rax, rax
0x140002e48  jnz     loc_140002FD7
0x140002e4e  mov     rax, cs:__pfnDliNotifyHook2
0x140002e55  test    rbx, rbx
0x140002e58  jnz     loc_140002EFF
0x140002e5e  test    rax, rax
0x140002e61  jz      short loc_140002E78
0x140002e63  lea     rdx, [rbp+var_50]
0x140002e67  lea     ecx, [rbx+1]
0x140002e6a  call    cs:__guard_dispatch_icall_fptr
0x140002e70  mov     rbx, rax
0x140002e73  test    rax, rax
0x140002e76  jnz     short loc_140002EE4
0x140002e78  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x140002e7c  xor     r8d, r8d; dwFlags
0x140002e7f  xor     edx, edx; hFile
0x140002e81  call    cs:__imp_LoadLibraryExA
0x140002e87  mov     rbx, rax
0x140002e8a  test    rax, rax
0x140002e8d  jnz     short loc_140002EE4
0x140002e8f  call    cs:__imp_GetLastError
0x140002e95  mov     [rbp+var_10], eax
0x140002e98  mov     rax, cs:__pfnDliFailureHook2
0x140002e9f  test    rax, rax
0x140002ea2  jz      short loc_140002EB9
0x140002ea4  lea     rdx, [rbp+var_50]
0x140002ea8  lea     ecx, [rbx+3]
0x140002eab  call    cs:__guard_dispatch_icall_fptr
0x140002eb1  mov     rbx, rax
0x140002eb4  test    rax, rax
0x140002eb7  jnz     short loc_140002EE4
0x140002eb9  lea     rax, [rbp+var_50]
0x140002ebd  mov     [rbp+Arguments], rax
0x140002ec1  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140002ec6  xor     edx, edx; dwExceptionFlags
0x140002ec8  lea     r9, [rbp+Arguments]; lpArguments
0x140002ecc  mov     ecx, 0C06D007Eh; dwExceptionCode
0x140002ed1  lea     r8d, [rdx+1]; nNumberOfArguments
0x140002ed5  call    cs:__imp_RaiseException
0x140002edb  mov     rax, [rbp+var_18]
0x140002edf  jmp     loc_140003009
0x140002ee4  mov     rax, rbx
0x140002ee7  xchg    rax, [r14]
0x140002eea  cmp     rax, rbx
0x140002eed  jnz     short loc_140002EF8
0x140002eef  mov     rcx, rbx; hLibModule
0x140002ef2  call    cs:__imp_FreeLibrary
0x140002ef8  mov     rax, cs:__pfnDliNotifyHook2
0x140002eff  mov     [rbp+var_20], rbx
0x140002f03  test    rax, rax
0x140002f06  jz      short loc_140002F1A
0x140002f08  lea     rdx, [rbp+var_50]
0x140002f0c  mov     ecx, 2
0x140002f11  call    cs:__guard_dispatch_icall_fptr
0x140002f17  mov     rdi, rax
0x140002f1a  test    rdi, rdi
0x140002f1d  jnz     loc_140002FBE
0x140002f23  cmp     [rsi+14h], edi
0x140002f26  jz      short loc_140002F54
0x140002f28  cmp     [rsi+1Ch], edi
0x140002f2b  jz      short loc_140002F54
0x140002f2d  movsxd  rax, dword ptr [rbx+3Ch]
0x140002f31  cmp     dword ptr [rax+rbx], 4550h
0x140002f38  jnz     short loc_140002F54
0x140002f3a  mov     ecx, dword ptr [rbp+Arguments]
0x140002f3d  cmp     [rax+rbx+8], ecx
0x140002f41  jnz     short loc_140002F54
0x140002f43  cmp     rbx, [rax+rbx+30h]
0x140002f48  jnz     short loc_140002F54
0x140002f4a  mov     rdi, [r13+r12*8+0]
0x140002f4f  test    rdi, rdi
0x140002f52  jnz     short loc_140002FBE
0x140002f54  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x140002f58  mov     rcx, rbx; hModule
0x140002f5b  call    cs:__imp_GetProcAddress
0x140002f61  mov     rdi, rax
0x140002f64  test    rax, rax
0x140002f67  jnz     short loc_140002FBE
0x140002f69  call    cs:__imp_GetLastError
0x140002f6f  mov     [rbp+var_10], eax
0x140002f72  mov     rax, cs:__pfnDliFailureHook2
0x140002f79  test    rax, rax
0x140002f7c  jz      short loc_140002F93
0x140002f7e  lea     rdx, [rbp+var_50]
0x140002f82  lea     ecx, [rdi+4]
0x140002f85  call    cs:__guard_dispatch_icall_fptr
0x140002f8b  mov     rdi, rax
0x140002f8e  test    rax, rax
0x140002f91  jnz     short loc_140002FBE
0x140002f93  lea     rax, [rbp+var_50]
0x140002f97  mov     [rbp+Arguments], rax
0x140002f9b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140002fa0  xor     edx, edx; dwExceptionFlags
0x140002fa2  lea     r9, [rbp+Arguments]; lpArguments
0x140002fa6  mov     ecx, 0C06D007Fh; dwExceptionCode
0x140002fab  lea     r8d, [rdx+1]; nNumberOfArguments
0x140002faf  call    cs:__imp_RaiseException
0x140002fb5  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x140002fba  mov     rdi, [rbp+var_18]
0x140002fbe  lea     r8, [rbp+var_60]
0x140002fc2  mov     [rbp+var_60], r15
0x140002fc6  mov     edx, 8; dwSize
0x140002fcb  mov     [rbp+var_58], rdi
0x140002fcf  mov     rcx, r15; lpAddress
0x140002fd2  call    sub_140002810
0x140002fd7  mov     rax, cs:__pfnDliNotifyHook2
0x140002fde  test    rax, rax
0x140002fe1  jz      short loc_140003001
0x140002fe3  lea     rdx, [rbp+var_50]
0x140002fe7  mov     [rbp+var_10], 0
0x140002fee  mov     ecx, 5
0x140002ff3  mov     [rbp+var_20], rbx
0x140002ff7  mov     [rbp+var_18], rdi
0x140002ffb  call    cs:__guard_dispatch_icall_fptr
0x140003001  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x140003006  mov     rax, rdi
0x140003009  lea     r11, [rsp+80h+var_s0]
0x140003011  mov     rbx, [r11+38h]
0x140003015  mov     rsi, [r11+40h]
0x140003019  mov     rdi, [r11+48h]
0x14000301d  mov     rsp, r11
0x140003020  pop     r15
0x140003022  pop     r14
0x140003024  pop     r13
0x140003026  pop     r12
0x140003028  pop     rbp
0x140003029  retn
```
