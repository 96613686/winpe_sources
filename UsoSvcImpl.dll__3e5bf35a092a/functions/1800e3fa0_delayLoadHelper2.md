# __delayLoadHelper2

- ea: `0x1800e3fa0`
- end: `0x1800e429a`
- name: `__delayLoadHelper2`
- size: `762`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800e3794`
- `0x1800e42a6`

## callees

- `0x1800e3a54`
- `0x1800e3b48`
- `0x1800e3eec`
- `0x1800e3fa0`
- `0x1800e4650`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800e40f1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800e40f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e41cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e41cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e4162`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e4162`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e404f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e4145`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e421f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e404f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e4145`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e421f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e40ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e41d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e40ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e41d9`

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
  GuardedWrite____delayLoadHelper2_::_2_::_lambda_1___(a2, 8u);
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
0x1800e3fa0  mov     [rsp-28h+arg_8], rbx
0x1800e3fa5  mov     [rsp-28h+arg_10], rsi
0x1800e3faa  mov     [rsp-28h+arg_18], rdi
0x1800e3faf  push    rbp
0x1800e3fb0  push    r12
0x1800e3fb2  push    r13
0x1800e3fb4  push    r14
0x1800e3fb6  push    r15
0x1800e3fb8  mov     rbp, rsp
0x1800e3fbb  sub     rsp, 80h
0x1800e3fc2  mov     r15, rdx
0x1800e3fc5  mov     rsi, rcx
0x1800e3fc8  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1800e3fcd  mov     eax, [rsi+4]
0x1800e3fd0  lea     r8, __ImageBase
0x1800e3fd7  mov     r14d, [rsi+8]
0x1800e3fdb  add     rax, r8
0x1800e3fde  mov     edx, [rsi+0Ch]
0x1800e3fe1  add     r14, r8
0x1800e3fe4  mov     ecx, [rsi+10h]
0x1800e3fe7  add     rdx, r8
0x1800e3fea  mov     r13d, [rsi+14h]
0x1800e3fee  add     rcx, r8
0x1800e3ff1  add     r13, r8
0x1800e3ff4  mov     [rbp+lpLibFileName], rax
0x1800e3ff8  mov     eax, [rsi]
0x1800e3ffa  xorps   xmm0, xmm0
0x1800e3ffd  mov     r8d, [rsi+1Ch]
0x1800e4001  mov     dword ptr [rbp+Arguments], r8d
0x1800e4005  mov     [rbp+var_50], 48h ; 'H'
0x1800e400c  mov     [rbp+var_48], rsi
0x1800e4010  mov     [rbp+var_40], r15
0x1800e4014  mov     [rbp+var_20], 0
0x1800e401c  mov     [rbp+var_18], 0
0x1800e4024  mov     [rbp+var_10], 0
0x1800e402b  movups  xmmword ptr [rbp+lpProcName], xmm0
0x1800e402f  test    al, 1
0x1800e4031  jnz     short loc_1800E405C
0x1800e4033  lea     rax, [rbp+var_50]
0x1800e4037  mov     [rbp+Arguments], rax
0x1800e403b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1800e4040  xor     edx, edx; dwExceptionFlags
0x1800e4042  lea     r9, [rbp+Arguments]; lpArguments
0x1800e4046  mov     ecx, 0C06D0057h; dwExceptionCode
0x1800e404b  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800e404f  call    cs:__imp_RaiseException
0x1800e4055  xor     eax, eax
0x1800e4057  jmp     loc_1800E4279
0x1800e405c  mov     rbx, [r14]
0x1800e405f  mov     r12, r15
0x1800e4062  sub     r12, rdx
0x1800e4065  sar     r12, 3
0x1800e4069  mov     r12d, r12d
0x1800e406c  mov     rax, [rcx+r12*8]
0x1800e4070  shr     rax, 3Fh
0x1800e4074  xor     eax, 1
0x1800e4077  mov     dword ptr [rbp+lpProcName], eax
0x1800e407a  jz      short loc_1800E4090
0x1800e407c  mov     eax, [rcx+r12*8]
0x1800e4080  lea     rcx, word_180000002
0x1800e4087  add     rax, rcx
0x1800e408a  mov     [rbp+lpProcName+8], rax
0x1800e408e  jmp     short loc_1800E4098
0x1800e4090  movzx   eax, word ptr [rcx+r12*8]
0x1800e4095  mov     dword ptr [rbp+lpProcName+8], eax
0x1800e4098  mov     rax, cs:__pfnDliNotifyHook2
0x1800e409f  xor     edi, edi
0x1800e40a1  test    rax, rax
0x1800e40a4  jz      short loc_1800E40C5
0x1800e40a6  lea     rdx, [rbp+var_50]
0x1800e40aa  xor     ecx, ecx
0x1800e40ac  call    cs:__guard_dispatch_icall_fptr
0x1800e40b2  mov     rdi, rax
0x1800e40b5  test    rax, rax
0x1800e40b8  jnz     loc_1800E4247
0x1800e40be  mov     rax, cs:__pfnDliNotifyHook2
0x1800e40c5  test    rbx, rbx
0x1800e40c8  jnz     loc_1800E416F
0x1800e40ce  test    rax, rax
0x1800e40d1  jz      short loc_1800E40E8
0x1800e40d3  lea     rdx, [rbp+var_50]
0x1800e40d7  lea     ecx, [rbx+1]
0x1800e40da  call    cs:__guard_dispatch_icall_fptr
0x1800e40e0  mov     rbx, rax
0x1800e40e3  test    rax, rax
0x1800e40e6  jnz     short loc_1800E4154
0x1800e40e8  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x1800e40ec  xor     r8d, r8d; dwFlags
0x1800e40ef  xor     edx, edx; hFile
0x1800e40f1  call    cs:__imp_LoadLibraryExA
0x1800e40f7  mov     rbx, rax
0x1800e40fa  test    rax, rax
0x1800e40fd  jnz     short loc_1800E4154
0x1800e40ff  call    cs:__imp_GetLastError
0x1800e4105  mov     [rbp+var_10], eax
0x1800e4108  mov     rax, cs:__pfnDliFailureHook2
0x1800e410f  test    rax, rax
0x1800e4112  jz      short loc_1800E4129
0x1800e4114  lea     rdx, [rbp+var_50]
0x1800e4118  lea     ecx, [rbx+3]
0x1800e411b  call    cs:__guard_dispatch_icall_fptr
0x1800e4121  mov     rbx, rax
0x1800e4124  test    rax, rax
0x1800e4127  jnz     short loc_1800E4154
0x1800e4129  lea     rax, [rbp+var_50]
0x1800e412d  mov     [rbp+Arguments], rax
0x1800e4131  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1800e4136  xor     edx, edx; dwExceptionFlags
0x1800e4138  lea     r9, [rbp+Arguments]; lpArguments
0x1800e413c  mov     ecx, 0C06D007Eh; dwExceptionCode
0x1800e4141  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800e4145  call    cs:__imp_RaiseException
0x1800e414b  mov     rax, [rbp+var_18]
0x1800e414f  jmp     loc_1800E4279
0x1800e4154  mov     rax, rbx
0x1800e4157  xchg    rax, [r14]
0x1800e415a  cmp     rax, rbx
0x1800e415d  jnz     short loc_1800E4168
0x1800e415f  mov     rcx, rbx; hLibModule
0x1800e4162  call    cs:__imp_FreeLibrary
0x1800e4168  mov     rax, cs:__pfnDliNotifyHook2
0x1800e416f  mov     [rbp+var_20], rbx
0x1800e4173  test    rax, rax
0x1800e4176  jz      short loc_1800E418A
0x1800e4178  lea     rdx, [rbp+var_50]
0x1800e417c  mov     ecx, 2
0x1800e4181  call    cs:__guard_dispatch_icall_fptr
0x1800e4187  mov     rdi, rax
0x1800e418a  test    rdi, rdi
0x1800e418d  jnz     loc_1800E422E
0x1800e4193  cmp     [rsi+14h], edi
0x1800e4196  jz      short loc_1800E41C4
0x1800e4198  cmp     [rsi+1Ch], edi
0x1800e419b  jz      short loc_1800E41C4
0x1800e419d  movsxd  rax, dword ptr [rbx+3Ch]
0x1800e41a1  cmp     dword ptr [rax+rbx], 4550h
0x1800e41a8  jnz     short loc_1800E41C4
0x1800e41aa  mov     ecx, dword ptr [rbp+Arguments]
0x1800e41ad  cmp     [rax+rbx+8], ecx
0x1800e41b1  jnz     short loc_1800E41C4
0x1800e41b3  cmp     rbx, [rax+rbx+30h]
0x1800e41b8  jnz     short loc_1800E41C4
0x1800e41ba  mov     rdi, [r13+r12*8+0]
0x1800e41bf  test    rdi, rdi
0x1800e41c2  jnz     short loc_1800E422E
0x1800e41c4  mov     rdx, [rbp+lpProcName+8]; lpProcName
0x1800e41c8  mov     rcx, rbx; hModule
0x1800e41cb  call    cs:__imp_GetProcAddress
0x1800e41d1  mov     rdi, rax
0x1800e41d4  test    rax, rax
0x1800e41d7  jnz     short loc_1800E422E
0x1800e41d9  call    cs:__imp_GetLastError
0x1800e41df  mov     [rbp+var_10], eax
0x1800e41e2  mov     rax, cs:__pfnDliFailureHook2
0x1800e41e9  test    rax, rax
0x1800e41ec  jz      short loc_1800E4203
0x1800e41ee  lea     rdx, [rbp+var_50]
0x1800e41f2  lea     ecx, [rdi+4]
0x1800e41f5  call    cs:__guard_dispatch_icall_fptr
0x1800e41fb  mov     rdi, rax
0x1800e41fe  test    rax, rax
0x1800e4201  jnz     short loc_1800E422E
0x1800e4203  lea     rax, [rbp+var_50]
0x1800e4207  mov     [rbp+Arguments], rax
0x1800e420b  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1800e4210  xor     edx, edx; dwExceptionFlags
0x1800e4212  lea     r9, [rbp+Arguments]; lpArguments
0x1800e4216  mov     ecx, 0C06D007Fh; dwExceptionCode
0x1800e421b  lea     r8d, [rdx+1]; nNumberOfArguments
0x1800e421f  call    cs:__imp_RaiseException
0x1800e4225  call    ?DloadAcquireSectionWriteAccess@@YAXXZ; DloadAcquireSectionWriteAccess(void)
0x1800e422a  mov     rdi, [rbp+var_18]
0x1800e422e  lea     r8, [rbp+var_60]
0x1800e4232  mov     [rbp+var_60], r15
0x1800e4236  mov     edx, 8; dwSize
0x1800e423b  mov     [rbp+var_58], rdi
0x1800e423f  mov     rcx, r15; lpAddress
0x1800e4242  call    GuardedWrite____delayLoadHelper2____2____lambda_1___
0x1800e4247  mov     rax, cs:__pfnDliNotifyHook2
0x1800e424e  test    rax, rax
0x1800e4251  jz      short loc_1800E4271
0x1800e4253  lea     rdx, [rbp+var_50]
0x1800e4257  mov     [rbp+var_10], 0
0x1800e425e  mov     ecx, 5
0x1800e4263  mov     [rbp+var_20], rbx
0x1800e4267  mov     [rbp+var_18], rdi
0x1800e426b  call    cs:__guard_dispatch_icall_fptr
0x1800e4271  call    ?DloadReleaseSectionWriteAccess@@YAXXZ; DloadReleaseSectionWriteAccess(void)
0x1800e4276  mov     rax, rdi
0x1800e4279  lea     r11, [rsp+80h+var_s0]
0x1800e4281  mov     rbx, [r11+38h]
0x1800e4285  mov     rsi, [r11+40h]
0x1800e4289  mov     rdi, [r11+48h]
0x1800e428d  mov     rsp, r11
0x1800e4290  pop     r15
0x1800e4292  pop     r14
0x1800e4294  pop     r13
0x1800e4296  pop     r12
0x1800e4298  pop     rbp
0x1800e4299  retn
```
