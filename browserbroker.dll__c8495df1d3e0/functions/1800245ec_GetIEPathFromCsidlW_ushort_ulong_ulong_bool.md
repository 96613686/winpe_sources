# GetIEPathFromCsidlW(ushort *,ulong,ulong,bool)

- ea: `0x1800245ec`
- end: `0x1800247b1`
- name: `?GetIEPathFromCsidlW@@YA_NPEAGKK_N@Z`
- size: `453`
- prototype: `bool __fastcall(unsigned __int16 *, unsigned int, unsigned int, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation`

## callers

- `0x18000a7e0`
- `0x18000c3a0`
- `0x18000c640`

## callees

- `0x180002ce0`
- `0x180003eeb`
- `0x18000d17c`
- `0x1800245ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002465a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002465a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800246b8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002473d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002475a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800246b8`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002473d`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002475a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180024642`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180024642`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180024692`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180024692`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180024668`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x180024668`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800246ff`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x1800246ff`

## pseudocode

```c
char __fastcall GetIEPathFromCsidlW(unsigned __int16 *a1, __int64 a2, int a3, char a4)
{
  char v7; // di
  HANDLE CurrentProcess; // rax
  WINBOOL Wow64Process; // [rsp+20h] [rbp-E0h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Dst[264]; // [rsp+60h] [rbp-A0h] BYREF

  v7 = 0;
  InitOnceExecuteOnce(&InitOnce, InitOnceDeviceFamily, 0, 0);
  if ( !byte_18003FD64 )
  {
    Wow64Process = 0;
    CurrentProcess = GetCurrentProcess();
    IsWow64Process(CurrentProcess, &Wow64Process);
    if ( Wow64Process && a3 == 38 )
    {
      if ( ExpandEnvironmentStringsW(L"%ProgramW6432%\\Internet Explorer", Dst, 0x104u) - 1 <= 0x103
        && (!a4 || PathCchAppend(Dst, 0x104u, L"IEXPLORE.EXE") >= 0)
        && StringCchCopyW(a1, 0x104u, Dst) >= 0 )
      {
        return 1;
      }
    }
    else
    {
      memset(&SystemInfo, 0, sizeof(SystemInfo));
      GetNativeSystemInfo(&SystemInfo);
      if ( !SystemInfo.wProcessorArchitecture && a3 == 42 )
        a3 = 38;
      if ( SHGetSpecialFolderPathW_0(0, Dst, a3, 0)
        && PathCchAppend(Dst, 0x104u, L"Internet Explorer\\") >= 0
        && (!a4 || PathCchAppend(Dst, 0x104u, L"IEXPLORE.EXE") >= 0) )
      {
        return StringCchCopyW(a1, 0x104u, Dst) >= 0;
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800245ec  mov     [rsp-8+arg_8], rbx
0x1800245f1  mov     [rsp-8+arg_18], rsi
0x1800245f6  push    rbp
0x1800245f7  push    rdi
0x1800245f8  push    r12
0x1800245fa  push    r14
0x1800245fc  push    r15
0x1800245fe  lea     rbp, [rsp-180h]
0x180024606  sub     rsp, 280h
0x18002460d  mov     rax, cs:__security_cookie
0x180024614  xor     rax, rsp
0x180024617  mov     [rbp+1A0h+var_30], rax
0x18002461e  mov     sil, r9b
0x180024621  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180024628  mov     ebx, r8d
0x18002462b  mov     r14, rcx
0x18002462e  xor     r15d, r15d
0x180024631  lea     rcx, InitOnce; InitOnce
0x180024638  xor     r9d, r9d; Context
0x18002463b  movzx   edi, r15b
0x18002463f  xor     r8d, r8d; Parameter
0x180024642  call    cs:__imp_InitOnceExecuteOnce
0x180024648  cmp     cs:byte_18003FD64, r15b
0x18002464f  jnz     loc_180024783
0x180024655  mov     [rsp+2A0h+Wow64Process], r15d
0x18002465a  call    cs:__imp_GetCurrentProcess
0x180024660  mov     rcx, rax; hProcess
0x180024663  lea     rdx, [rsp+2A0h+Wow64Process]; Wow64Process
0x180024668  call    cs:__imp_IsWow64Process
0x18002466e  lea     r12d, [r15+26h]
0x180024672  cmp     [rsp+2A0h+Wow64Process], r15d
0x180024677  jz      short loc_1800246E8
0x180024679  cmp     ebx, r12d
0x18002467c  jnz     short loc_1800246E8
0x18002467e  mov     ebx, 104h
0x180024683  lea     rdx, [rsp+2A0h+Dst]; lpDst
0x180024688  mov     r8d, ebx; nSize
0x18002468b  lea     rcx, Src; "%ProgramW6432%\\Internet Explorer"
0x180024692  call    cs:__imp_ExpandEnvironmentStringsW
0x180024698  dec     eax
0x18002469a  cmp     eax, 103h
0x18002469f  ja      loc_180024783
0x1800246a5  test    sil, sil
0x1800246a8  jz      short loc_1800246C6
0x1800246aa  lea     r8, aIexploreExe; "IEXPLORE.EXE"
0x1800246b1  mov     edx, ebx; cchPath
0x1800246b3  lea     rcx, [rsp+2A0h+Dst]; pszPath
0x1800246b8  call    cs:__imp_PathCchAppend
0x1800246be  test    eax, eax
0x1800246c0  js      loc_180024783
0x1800246c6  lea     r8, [rsp+2A0h+Dst]; unsigned __int16 *
0x1800246cb  mov     rdx, rbx; unsigned __int64
0x1800246ce  mov     rcx, r14; unsigned __int16 *
0x1800246d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800246d6  test    eax, eax
0x1800246d8  js      loc_180024783
0x1800246de  mov     edi, 1
0x1800246e3  jmp     loc_180024783
0x1800246e8  xorps   xmm0, xmm0
0x1800246eb  lea     rcx, [rsp+2A0h+SystemInfo]; lpSystemInfo
0x1800246f0  movups  xmmword ptr [rsp+2A0h+SystemInfo], xmm0
0x1800246f5  movups  xmmword ptr [rsp+2A0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800246fa  movups  xmmword ptr [rsp+2A0h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800246ff  call    cs:__imp_GetNativeSystemInfo
0x180024705  cmp     word ptr [rsp+2A0h+SystemInfo], r15w
0x18002470b  jnz     short loc_180024714
0x18002470d  cmp     ebx, 2Ah ; '*'
0x180024710  cmovz   ebx, r12d
0x180024714  xor     r9d, r9d; fCreate
0x180024717  lea     rdx, [rsp+2A0h+Dst]; pszPath
0x18002471c  mov     r8d, ebx; csidl
0x18002471f  xor     ecx, ecx; hwnd
0x180024721  call    SHGetSpecialFolderPathW_0
0x180024726  test    eax, eax
0x180024728  jz      short loc_180024783
0x18002472a  mov     ebx, 104h
0x18002472f  lea     r8, aInternetExplor; "Internet Explorer\\"
0x180024736  mov     edx, ebx; cchPath
0x180024738  lea     rcx, [rsp+2A0h+Dst]; pszPath
0x18002473d  call    cs:__imp_PathCchAppend
0x180024743  test    eax, eax
0x180024745  js      short loc_180024783
0x180024747  test    sil, sil
0x18002474a  jz      short loc_180024764
0x18002474c  lea     r8, aIexploreExe; "IEXPLORE.EXE"
0x180024753  mov     edx, ebx; cchPath
0x180024755  lea     rcx, [rsp+2A0h+Dst]; pszPath
0x18002475a  call    cs:__imp_PathCchAppend
0x180024760  test    eax, eax
0x180024762  js      short loc_180024783
0x180024764  lea     r8, [rsp+2A0h+Dst]; unsigned __int16 *
0x180024769  mov     rdx, rbx; unsigned __int64
0x18002476c  mov     rcx, r14; unsigned __int16 *
0x18002476f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024774  mov     ecx, edi
0x180024776  test    eax, eax
0x180024778  mov     edi, 1
0x18002477d  cmovns  ecx, edi
0x180024780  mov     dil, cl
0x180024783  mov     al, dil
0x180024786  mov     rcx, [rbp+1A0h+var_30]
0x18002478d  xor     rcx, rsp; StackCookie
0x180024790  call    __security_check_cookie
0x180024795  lea     r11, [rsp+2A0h+var_20]
0x18002479d  mov     rbx, [r11+38h]
0x1800247a1  mov     rsi, [r11+48h]
0x1800247a5  mov     rsp, r11
0x1800247a8  pop     r15
0x1800247aa  pop     r14
0x1800247ac  pop     r12
0x1800247ae  pop     rdi
0x1800247af  pop     rbp
0x1800247b0  retn
```
