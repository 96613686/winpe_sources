# AslLogCreate

- ea: `0x180023ed4`
- end: `0x18002420d`
- name: `AslLogCreate`
- size: `825`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800855c8`

## callees

- `0x180023ed4`
- `0x180024214`
- `0x1800242cc`
- `0x180024ae0`
- `0x180024ca8`
- `0x180056904`
- `0x1800569b9`
- `0x1800569d7`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180024047`
- `msvcrt!wcsrchr` at `0x180024047`
- `ntdll!RtlInitializeCriticalSection` at `0x180023f69`
- `ntdll!RtlInitializeCriticalSection` at `0x180023f69`
- `ntdll!EtwEventRegister` at `0x180023fcb`
- `ntdll!EtwEventRegister` at `0x180023fcb`
- `ntdll!RtlAllocateHeap` at `0x180023f42`
- `ntdll!RtlAllocateHeap` at `0x180023f42`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180023fe1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180023fe1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024075`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024116`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024075`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180024116`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024007`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024144`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024007`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180024144`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002412e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002412e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800240b2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800240da`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800240b2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800240da`

## string_xrefs

- `0x180024154`: `%s\Temp`
- `0x180024069`: `ntdll.dll`
- `0x180024108`: `ntdll.dll`
- `0x1800240ab`: `%OSDataDrive%\SystemData\Temp`
- `0x1800240d3`: `%TEMP%`

## pseudocode

```c
__int64 __fastcall AslLogCreate(_QWORD *a1, __int64 a2, unsigned int a3)
{
  unsigned __int64 v6; // rax
  int v7; // edi
  char *Heap; // rax
  _QWORD *v9; // rbx
  PVOID ProcessHeap; // rcx
  HMODULE v11; // rbp
  wchar_t *v13; // rax
  WCHAR *v14; // rsi
  HMODULE Library; // rax
  unsigned __int8 (*RtlIsStateSeparationEnabled)(void); // rax
  __int64 v17; // rdi
  HMODULE v18; // rax
  HMODULE v19; // r14
  __int64 (*ProcAddress)(void); // rax
  __int64 v21; // r8
  unsigned int v22; // ecx
  DWORD CurrentProcessId_0; // [rsp+30h] [rbp-478h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-468h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-258h] BYREF

  *a1 = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_BYTE *)(a2 + v6) );
  if ( v6 >= 0x40 )
    return (unsigned int)-1073741811;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2D8u);
  v9 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  *((_QWORD *)Heap + 90) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 104));
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_OWORD *)v9 + 9) = 0;
  *((_OWORD *)v9 + 10) = 0;
  *((_OWORD *)v9 + 11) = 0;
  if ( !ProcessHeap )
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
  v9[18] = ProcessHeap;
  v9[21] = 4096;
  EtwEventRegister(&AE_LOG, 0, 0, v9 + 89);
  GetModuleFileNameW(0, Filename, 0x104u);
  if ( GetLastError_0() )
  {
    v11 = 0;
LABEL_11:
    v7 = -1073741823;
LABEL_12:
    AslLogDelete(v9);
    goto LABEL_13;
  }
  v13 = wcsrchr(Filename, 0x5Cu);
  if ( v13 )
    v14 = v13 + 1;
  else
    v14 = Filename;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v11 = Library;
  if ( Library
    && (RtlIsStateSeparationEnabled = (unsigned __int8 (*)(void))GetProcAddress_0(
                                                                   Library,
                                                                   "RtlIsStateSeparationEnabled")) != 0
    && RtlIsStateSeparationEnabled() )
  {
    if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
    {
      goto LABEL_11;
    }
  }
  else
  {
    v17 = (__int64)qword_18015BF38;
    if ( !qword_18015BF38 )
    {
      v17 = 2147352624;
      v18 = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v19 = v18;
      if ( v18 )
      {
        ProcAddress = GetProcAddress(v18, "RtlGetNtSystemRoot");
        if ( ProcAddress )
          v17 = ProcAddress();
        FreeLibrary(v19);
      }
      qword_18015BF38 = (wchar_t *)v17;
    }
    v7 = RtlStringCchPrintfW(Dst, 0x104u, L"%s\\Temp", v17);
    if ( v7 < 0 )
      goto LABEL_12;
  }
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v7 = RtlStringCchPrintfW(
         (unsigned __int16 *)v9 + 96,
         0x104u,
         L"%s\\AslLog_%S_%s_%d.txt",
         Dst,
         a2,
         v14,
         CurrentProcessId_0);
  if ( v7 < 0 )
    goto LABEL_12;
  *v9 = v9 + 1;
  *(_DWORD *)(*v9 + 80LL) = AslLogGetDefaultFlags();
  RtlStringCopyWorkerA(*v9, 64, v21, a2);
  if ( a3 )
  {
    v22 = *((_DWORD *)v9 + 40);
    if ( a3 >= v22 )
    {
      v22 = a3;
    }
    else if ( !v22 )
    {
      goto LABEL_43;
    }
    if ( v22 == (v22 & -v22) )
      *(_DWORD *)(*v9 + 76LL) = v22;
    goto LABEL_43;
  }
  *(_DWORD *)(*v9 + 76LL) = 0;
LABEL_43:
  v7 = 0;
  *a1 = v9;
LABEL_13:
  if ( v11 )
    FreeLibrary(v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023ed4  mov     [rsp+arg_10], rbx
0x180023ed9  push    rbp
0x180023eda  push    rsi
0x180023edb  push    rdi
0x180023edc  push    r12
0x180023ede  push    r13
0x180023ee0  push    r14
0x180023ee2  push    r15
0x180023ee4  sub     rsp, 470h
0x180023eeb  mov     rax, cs:__security_cookie
0x180023ef2  xor     rax, rsp
0x180023ef5  mov     [rsp+4A8h+var_48], rax
0x180023efd  mov     r15d, r8d
0x180023f00  mov     qword ptr [rcx], 0
0x180023f07  mov     r12, rdx
0x180023f0a  mov     r13, rcx
0x180023f0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023f11  inc     rax
0x180023f14  cmp     byte ptr [rdx+rax], 0
0x180023f18  jnz     short loc_180023F11
0x180023f1a  cmp     rax, 40h ; '@'
0x180023f1e  jb      short loc_180023F2A
0x180023f20  mov     edi, 0C000000Dh
0x180023f25  jmp     loc_18002400D
0x180023f2a  mov     rcx, gs:60h
0x180023f33  mov     edx, 8; Flags
0x180023f38  mov     r8d, 2D8h; Size
0x180023f3e  mov     rcx, [rcx+30h]; HeapHandle
0x180023f42  call    cs:__imp_RtlAllocateHeap
0x180023f48  mov     rbx, rax
0x180023f4b  test    rax, rax
0x180023f4e  jnz     short loc_180023F5A
0x180023f50  mov     edi, 0C0000017h
0x180023f55  jmp     loc_18002400D
0x180023f5a  lea     rcx, [rax+68h]; CriticalSection
0x180023f5e  mov     qword ptr [rax+2D0h], 0
0x180023f69  call    cs:__imp_RtlInitializeCriticalSection
0x180023f6f  mov     rax, gs:60h
0x180023f78  xorps   xmm0, xmm0
0x180023f7b  mov     rcx, [rax+30h]
0x180023f7f  movups  xmmword ptr [rbx+90h], xmm0
0x180023f86  movups  xmmword ptr [rbx+0A0h], xmm0
0x180023f8d  movups  xmmword ptr [rbx+0B0h], xmm0
0x180023f94  test    rcx, rcx
0x180023f97  jnz     short loc_180023FA6
0x180023f99  mov     rax, gs:60h
0x180023fa2  mov     rcx, [rax+30h]
0x180023fa6  mov     [rbx+90h], rcx
0x180023fad  lea     r9, [rbx+2C8h]
0x180023fb4  lea     rcx, AE_LOG
0x180023fbb  mov     qword ptr [rbx+0A8h], 1000h
0x180023fc6  xor     r8d, r8d
0x180023fc9  xor     edx, edx
0x180023fcb  call    cs:__imp_EtwEventRegister
0x180023fd1  mov     r8d, 104h; nSize
0x180023fd7  lea     rdx, [rsp+4A8h+Filename]; lpFilename
0x180023fdf  xor     ecx, ecx; hModule
0x180023fe1  call    cs:__imp_GetModuleFileNameW
0x180023fe7  call    GetLastError_0
0x180023fec  test    eax, eax
0x180023fee  jz      short loc_18002403A
0x180023ff0  xor     ebp, ebp
0x180023ff2  mov     edi, 0C0000001h
0x180023ff7  mov     rcx, rbx
0x180023ffa  call    AslLogDelete
0x180023fff  test    rbp, rbp
0x180024002  jz      short loc_18002400D
0x180024004  mov     rcx, rbp; hLibModule
0x180024007  call    cs:__imp_FreeLibrary
0x18002400d  mov     eax, edi
0x18002400f  mov     rcx, [rsp+4A8h+var_48]
0x180024017  xor     rcx, rsp; StackCookie
0x18002401a  call    __security_check_cookie
0x18002401f  mov     rbx, [rsp+4A8h+arg_10]
0x180024027  add     rsp, 470h
0x18002402e  pop     r15
0x180024030  pop     r14
0x180024032  pop     r13
0x180024034  pop     r12
0x180024036  pop     rdi
0x180024037  pop     rsi
0x180024038  pop     rbp
0x180024039  retn
0x18002403a  mov     edx, 5Ch ; '\'; Ch
0x18002403f  lea     rcx, [rsp+4A8h+Filename]; Str
0x180024047  call    cs:__imp_wcsrchr
0x18002404d  mov     rsi, rax
0x180024050  test    rax, rax
0x180024053  jnz     short loc_18002405F
0x180024055  lea     rsi, [rsp+4A8h+Filename]
0x18002405d  jmp     short loc_180024063
0x18002405f  add     rsi, 2
0x180024063  mov     r14d, 800h
0x180024069  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180024070  mov     r8d, r14d; dwFlags
0x180024073  xor     edx, edx; hFile
0x180024075  call    cs:__imp_LoadLibraryExW
0x18002407b  mov     rbp, rax
0x18002407e  test    rax, rax
0x180024081  jz      short loc_1800240F9
0x180024083  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18002408a  mov     rcx, rax; hModule
0x18002408d  call    GetProcAddress_0
0x180024092  test    rax, rax
0x180024095  jz      short loc_1800240F9
0x180024097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002409c  test    al, al
0x18002409e  jz      short loc_1800240F9
0x1800240a0  mov     r8d, 104h; nSize
0x1800240a6  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x1800240ab  lea     rcx, aOsdatadriveSys; "%OSDataDrive%\\SystemData\\Temp"
0x1800240b2  call    cs:__imp_ExpandEnvironmentStringsW
0x1800240b8  test    eax, eax
0x1800240ba  jz      short loc_1800240C8
0x1800240bc  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x1800240c2  jnz     loc_180024174
0x1800240c8  mov     r8d, 104h; nSize
0x1800240ce  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x1800240d3  lea     rcx, aTemp; "%TEMP%"
0x1800240da  call    cs:__imp_ExpandEnvironmentStringsW
0x1800240e0  test    eax, eax
0x1800240e2  jz      loc_180023FF2
0x1800240e8  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x1800240ee  jnz     loc_180024174
0x1800240f4  jmp     loc_180023FF2
0x1800240f9  mov     rdi, cs:qword_18015BF38
0x180024100  test    rdi, rdi
0x180024103  jnz     short loc_180024151
0x180024105  mov     r8d, r14d; dwFlags
0x180024108  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18002410f  xor     edx, edx; hFile
0x180024111  mov     edi, 7FFE0030h
0x180024116  call    cs:__imp_LoadLibraryExW
0x18002411c  mov     r14, rax
0x18002411f  test    rax, rax
0x180024122  jz      short loc_18002414A
0x180024124  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18002412b  mov     rcx, rax; hModule
0x18002412e  call    cs:__imp_GetProcAddress
0x180024134  test    rax, rax
0x180024137  jz      short loc_180024141
0x180024139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002413e  mov     rdi, rax
0x180024141  mov     rcx, r14; hLibModule
0x180024144  call    cs:__imp_FreeLibrary
0x18002414a  mov     cs:qword_18015BF38, rdi
0x180024151  mov     r9, rdi
0x180024154  lea     r8, aSTemp; "%s\\Temp"
0x18002415b  mov     edx, 104h; unsigned __int64
0x180024160  lea     rcx, [rsp+4A8h+Dst]; unsigned __int16 *
0x180024165  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002416a  mov     edi, eax
0x18002416c  test    eax, eax
0x18002416e  js      loc_180023FF7
0x180024174  call    GetCurrentProcessId_0
0x180024179  mov     [rsp+4A8h+var_478], eax
0x18002417d  lea     rcx, [rbx+0C0h]; unsigned __int16 *
0x180024184  mov     [rsp+4A8h+var_480], rsi
0x180024189  lea     r9, [rsp+4A8h+Dst]
0x18002418e  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x180024195  mov     [rsp+4A8h+var_488], r12
0x18002419a  mov     edx, 104h; unsigned __int64
0x18002419f  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800241a4  mov     edi, eax
0x1800241a6  test    eax, eax
0x1800241a8  js      loc_180023FF7
0x1800241ae  lea     rax, [rbx+8]
0x1800241b2  mov     [rbx], rax
0x1800241b5  call    AslLogGetDefaultFlags
0x1800241ba  mov     rcx, [rbx]
0x1800241bd  mov     r9, r12
0x1800241c0  mov     edx, 40h ; '@'
0x1800241c5  mov     [rcx+50h], eax
0x1800241c8  mov     rcx, [rbx]
0x1800241cb  call    RtlStringCopyWorkerA
0x1800241d0  test    r15d, r15d
0x1800241d3  jnz     short loc_1800241DE
0x1800241d5  mov     rax, [rbx]
0x1800241d8  mov     [rax+4Ch], r15d
0x1800241dc  jmp     short loc_180024202
0x1800241de  mov     ecx, [rbx+0A0h]
0x1800241e4  cmp     r15d, ecx
0x1800241e7  jnb     short loc_1800241EF
0x1800241e9  test    ecx, ecx
0x1800241eb  jnz     short loc_1800241F2
0x1800241ed  jmp     short loc_180024202
0x1800241ef  mov     ecx, r15d
0x1800241f2  mov     eax, ecx
0x1800241f4  neg     eax
0x1800241f6  and     eax, ecx
0x1800241f8  cmp     ecx, eax
0x1800241fa  jnz     short loc_180024202
0x1800241fc  mov     rax, [rbx]
0x1800241ff  mov     [rax+4Ch], ecx
0x180024202  xor     edi, edi
0x180024204  mov     [r13+0], rbx
0x180024208  jmp     loc_180023FFF
```
