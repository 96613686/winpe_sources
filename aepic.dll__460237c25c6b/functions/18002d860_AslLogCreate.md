# AslLogCreate

- ea: `0x18002d860`
- end: `0x18002db61`
- name: `AslLogCreate`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800022d0`

## callees

- `0x180005890`
- `0x18002d5e4`
- `0x18002d718`
- `0x18002d860`
- `0x18002e0f4`
- `0x18002e1a8`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002d9a3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18002d9a3`
- `ntdll!RtlInitializeCriticalSection` at `0x18002d8cc`
- `ntdll!RtlInitializeCriticalSection` at `0x18002d8cc`
- `ntdll!EtwEventRegister` at `0x18002d92e`
- `ntdll!EtwEventRegister` at `0x18002d92e`
- `ntdll!RtlAllocateHeap` at `0x18002d8a5`
- `ntdll!RtlAllocateHeap` at `0x18002d8a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002d947`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002d947`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d96e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002da97`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002d96e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002da97`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d9d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002da69`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002d9d1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002da69`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d9e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002da81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d9e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002da81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d94d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d94d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002dac5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002dac5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002da0c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002da31`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002da0c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002da31`

## string_xrefs

- `0x18002d9c5`: `ntdll.dll`
- `0x18002da5b`: `ntdll.dll`
- `0x18002da05`: `%OSDataDrive%\SystemData\Temp`
- `0x18002da2a`: `%TEMP%`
- `0x18002daa7`: `%s\Temp`

## pseudocode

```c
__int64 AslLogCreate()
{
  char *Heap; // rax
  _QWORD *v1; // rbx
  int v2; // edi
  PVOID ProcessHeap; // rcx
  HMODULE v4; // rbp
  wchar_t *v6; // rax
  WCHAR *v7; // rsi
  HMODULE Library; // rax
  unsigned __int8 (*v9)(void); // rax
  __int64 v10; // rdi
  HMODULE v11; // rax
  HMODULE v12; // r14
  __int64 (*ProcAddress)(void); // rax
  __int64 v14; // r8
  unsigned int v15; // r10d
  DWORD CurrentProcessId; // [rsp+30h] [rbp-478h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-468h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-258h] BYREF

  AslLogger = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2D8u);
  v1 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  *((_QWORD *)Heap + 90) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 104));
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_OWORD *)v1 + 9) = 0;
  *((_OWORD *)v1 + 10) = 0;
  *((_OWORD *)v1 + 11) = 0;
  if ( !ProcessHeap )
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v1[18] = ProcessHeap;
  v1[21] = 4096;
  EtwEventRegister(AE_LOG, 0, 0, v1 + 89);
  GetModuleFileNameW(0, Filename, 0x104u);
  if ( GetLastError() )
  {
    v4 = 0;
LABEL_7:
    v2 = -1073741823;
LABEL_8:
    AslLogDelete(v1);
    goto LABEL_9;
  }
  v6 = wcsrchr(Filename, 0x5Cu);
  if ( v6 )
    v7 = v6 + 1;
  else
    v7 = Filename;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v4 = Library;
  if ( Library && (v9 = (unsigned __int8 (*)(void))GetProcAddress(Library, "RtlIsStateSeparationEnabled")) != 0 && v9() )
  {
    if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
    {
      goto LABEL_7;
    }
  }
  else
  {
    v10 = (__int64)qword_1801228E8;
    if ( !qword_1801228E8 )
    {
      v10 = 2147352624;
      v11 = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v12 = v11;
      if ( v11 )
      {
        ProcAddress = GetProcAddress(v11, "RtlGetNtSystemRoot");
        if ( ProcAddress )
          v10 = ProcAddress();
        FreeLibrary(v12);
      }
      qword_1801228E8 = (void *)v10;
    }
    v2 = RtlStringCchPrintfW(Dst, 0x104u, L"%s\\Temp", v10);
    if ( v2 < 0 )
      goto LABEL_8;
  }
  CurrentProcessId = GetCurrentProcessId();
  v2 = RtlStringCchPrintfW(
         (unsigned __int16 *)v1 + 96,
         0x104u,
         L"%s\\AslLog_%S_%s_%d.txt",
         Dst,
         "aepic",
         v7,
         CurrentProcessId);
  if ( v2 < 0 )
    goto LABEL_8;
  *v1 = v1 + 1;
  *(_DWORD *)(*v1 + 80LL) = AslLogGetDefaultFlags();
  RtlStringCopyWorkerA(*v1, 64, v14, "aepic");
  v15 = *((_DWORD *)v1 + 40);
  if ( v15 <= 0x1000 )
  {
    v15 = 4096;
LABEL_35:
    *(_DWORD *)(*v1 + 76LL) = v15;
    goto LABEL_36;
  }
  if ( v15 == (v15 & -v15) )
    goto LABEL_35;
LABEL_36:
  v2 = 0;
  AslLogger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18002d860  push    rbx
0x18002d862  push    rbp
0x18002d863  push    rsi
0x18002d864  push    rdi
0x18002d865  push    r14
0x18002d867  push    r15
0x18002d869  sub     rsp, 478h
0x18002d870  mov     rax, cs:__security_cookie
0x18002d877  xor     rax, rsp
0x18002d87a  mov     [rsp+4A8h+var_48], rax
0x18002d882  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger AslLogger
0x18002d88d  mov     edx, 8; Flags
0x18002d892  mov     rcx, gs:60h
0x18002d89b  mov     r8d, 2D8h; Size
0x18002d8a1  mov     rcx, [rcx+30h]; HeapHandle
0x18002d8a5  call    cs:__imp_RtlAllocateHeap
0x18002d8ab  mov     rbx, rax
0x18002d8ae  test    rax, rax
0x18002d8b1  jnz     short loc_18002D8BD
0x18002d8b3  mov     edi, 0C0000017h
0x18002d8b8  jmp     loc_18002D974
0x18002d8bd  lea     rcx, [rax+68h]; CriticalSection
0x18002d8c1  mov     qword ptr [rax+2D0h], 0
0x18002d8cc  call    cs:__imp_RtlInitializeCriticalSection
0x18002d8d2  mov     rax, gs:60h
0x18002d8db  xorps   xmm0, xmm0
0x18002d8de  mov     rcx, [rax+30h]
0x18002d8e2  movups  xmmword ptr [rbx+90h], xmm0
0x18002d8e9  movups  xmmword ptr [rbx+0A0h], xmm0
0x18002d8f0  movups  xmmword ptr [rbx+0B0h], xmm0
0x18002d8f7  test    rcx, rcx
0x18002d8fa  jnz     short loc_18002D909
0x18002d8fc  mov     rax, gs:60h
0x18002d905  mov     rcx, [rax+30h]
0x18002d909  mov     [rbx+90h], rcx
0x18002d910  lea     r9, [rbx+2C8h]
0x18002d917  lea     rcx, AE_LOG
0x18002d91e  mov     qword ptr [rbx+0A8h], 1000h
0x18002d929  xor     r8d, r8d
0x18002d92c  xor     edx, edx
0x18002d92e  call    cs:__imp_EtwEventRegister
0x18002d934  mov     r15d, 104h
0x18002d93a  lea     rdx, [rsp+4A8h+Filename]; lpFilename
0x18002d942  mov     r8d, r15d; nSize
0x18002d945  xor     ecx, ecx; hModule
0x18002d947  call    cs:__imp_GetModuleFileNameW
0x18002d94d  call    cs:__imp_GetLastError
0x18002d953  test    eax, eax
0x18002d955  jz      short loc_18002D996
0x18002d957  xor     ebp, ebp
0x18002d959  mov     edi, 0C0000001h
0x18002d95e  mov     rcx, rbx
0x18002d961  call    AslLogDelete
0x18002d966  test    rbp, rbp
0x18002d969  jz      short loc_18002D974
0x18002d96b  mov     rcx, rbp; hLibModule
0x18002d96e  call    cs:__imp_FreeLibrary
0x18002d974  mov     eax, edi
0x18002d976  mov     rcx, [rsp+4A8h+var_48]
0x18002d97e  xor     rcx, rsp; StackCookie
0x18002d981  call    __security_check_cookie
0x18002d986  add     rsp, 478h
0x18002d98d  pop     r15
0x18002d98f  pop     r14
0x18002d991  pop     rdi
0x18002d992  pop     rsi
0x18002d993  pop     rbp
0x18002d994  pop     rbx
0x18002d995  retn
0x18002d996  mov     edx, 5Ch ; '\'; Ch
0x18002d99b  lea     rcx, [rsp+4A8h+Filename]; Str
0x18002d9a3  call    cs:__imp_wcsrchr
0x18002d9a9  mov     rsi, rax
0x18002d9ac  test    rax, rax
0x18002d9af  jnz     short loc_18002D9BB
0x18002d9b1  lea     rsi, [rsp+4A8h+Filename]
0x18002d9b9  jmp     short loc_18002D9BF
0x18002d9bb  add     rsi, 2
0x18002d9bf  mov     r14d, 800h
0x18002d9c5  lea     rcx, LibFileName; "ntdll.dll"
0x18002d9cc  mov     r8d, r14d; dwFlags
0x18002d9cf  xor     edx, edx; hFile
0x18002d9d1  call    cs:__imp_LoadLibraryExW
0x18002d9d7  mov     rbp, rax
0x18002d9da  test    rax, rax
0x18002d9dd  jz      short loc_18002DA4C
0x18002d9df  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18002d9e6  mov     rcx, rax; hModule
0x18002d9e9  call    cs:__imp_GetProcAddress
0x18002d9ef  test    rax, rax
0x18002d9f2  jz      short loc_18002DA4C
0x18002d9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9f9  test    al, al
0x18002d9fb  jz      short loc_18002DA4C
0x18002d9fd  mov     r8d, r15d; nSize
0x18002da00  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x18002da05  lea     rcx, Src; "%OSDataDrive%\\SystemData\\Temp"
0x18002da0c  call    cs:__imp_ExpandEnvironmentStringsW
0x18002da12  test    eax, eax
0x18002da14  jz      short loc_18002DA22
0x18002da16  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x18002da1c  jnz     loc_18002DAC5
0x18002da22  mov     r8d, r15d; nSize
0x18002da25  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x18002da2a  lea     rcx, aTemp; "%TEMP%"
0x18002da31  call    cs:__imp_ExpandEnvironmentStringsW
0x18002da37  test    eax, eax
0x18002da39  jz      loc_18002D959
0x18002da3f  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x18002da45  jnz     short loc_18002DAC5
0x18002da47  jmp     loc_18002D959
0x18002da4c  mov     rdi, cs:qword_1801228E8
0x18002da53  test    rdi, rdi
0x18002da56  jnz     short loc_18002DAA4
0x18002da58  mov     r8d, r14d; dwFlags
0x18002da5b  lea     rcx, LibFileName; "ntdll.dll"
0x18002da62  xor     edx, edx; hFile
0x18002da64  mov     edi, 7FFE0030h
0x18002da69  call    cs:__imp_LoadLibraryExW
0x18002da6f  mov     r14, rax
0x18002da72  test    rax, rax
0x18002da75  jz      short loc_18002DA9D
0x18002da77  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18002da7e  mov     rcx, rax; hModule
0x18002da81  call    cs:__imp_GetProcAddress
0x18002da87  test    rax, rax
0x18002da8a  jz      short loc_18002DA94
0x18002da8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da91  mov     rdi, rax
0x18002da94  mov     rcx, r14; hLibModule
0x18002da97  call    cs:__imp_FreeLibrary
0x18002da9d  mov     cs:qword_1801228E8, rdi
0x18002daa4  mov     r9, rdi
0x18002daa7  lea     r8, aSTemp; "%s\\Temp"
0x18002daae  mov     rdx, r15; unsigned __int64
0x18002dab1  lea     rcx, [rsp+4A8h+Dst]; unsigned __int16 *
0x18002dab6  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002dabb  mov     edi, eax
0x18002dabd  test    eax, eax
0x18002dabf  js      loc_18002D95E
0x18002dac5  call    cs:__imp_GetCurrentProcessId
0x18002dacb  mov     [rsp+4A8h+var_478], eax
0x18002dacf  lea     rcx, [rbx+0C0h]; unsigned __int16 *
0x18002dad6  mov     [rsp+4A8h+var_480], rsi
0x18002dadb  mov     rdx, r15; unsigned __int64
0x18002dade  lea     rsi, aAepic_0; "aepic"
0x18002dae5  lea     r9, [rsp+4A8h+Dst]
0x18002daea  mov     [rsp+4A8h+var_488], rsi
0x18002daef  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x18002daf6  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002dafb  mov     edi, eax
0x18002dafd  test    eax, eax
0x18002daff  js      loc_18002D95E
0x18002db05  lea     rax, [rbx+8]
0x18002db09  mov     [rbx], rax
0x18002db0c  call    AslLogGetDefaultFlags
0x18002db11  mov     rcx, [rbx]
0x18002db14  mov     r9, rsi
0x18002db17  mov     edx, 40h ; '@'
0x18002db1c  mov     [rcx+50h], eax
0x18002db1f  mov     rcx, [rbx]
0x18002db22  call    RtlStringCopyWorkerA
0x18002db27  mov     r10d, [rbx+0A0h]
0x18002db2e  cmp     r10d, 1000h
0x18002db35  jbe     short loc_18002DB46
0x18002db37  mov     eax, r10d
0x18002db3a  neg     eax
0x18002db3c  and     eax, r10d
0x18002db3f  cmp     r10d, eax
0x18002db42  jnz     short loc_18002DB53
0x18002db44  jmp     short loc_18002DB4C
0x18002db46  mov     r10d, 1000h
0x18002db4c  mov     rax, [rbx]
0x18002db4f  mov     [rax+4Ch], r10d
0x18002db53  xor     edi, edi
0x18002db55  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger AslLogger
0x18002db5c  jmp     loc_18002D966
```
