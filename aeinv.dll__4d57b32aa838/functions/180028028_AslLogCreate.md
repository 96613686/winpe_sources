# AslLogCreate

- ea: `0x180028028`
- end: `0x180028323`
- name: `AslLogCreate`
- size: `763`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002d30`

## callees

- `0x180027028`
- `0x180028028`
- `0x18002832c`
- `0x18002c984`
- `0x1800508d4`
- `0x180059920`
- `0x18005ab10`
- `0x18005ab30`
- `0x18005ab60`
- `0x18005abac`
- `0x18005ac90`
- `0x18005acdc`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028168`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028168`
- `ntdll!EtwEventRegister` at `0x1800280f6`
- `ntdll!EtwEventRegister` at `0x1800280f6`
- `ntdll!RtlInitializeCriticalSection` at `0x180028094`
- `ntdll!RtlInitializeCriticalSection` at `0x180028094`
- `ntdll!RtlAllocateHeap` at `0x18002806d`
- `ntdll!RtlAllocateHeap` at `0x18002806d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800281cf`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800281f4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800281cf`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800281f4`
- `KERNEL32!LoadLibraryExW` at `0x18002822c`
- `KERNEL32!LoadLibraryExW` at `0x18002822c`
- `KERNEL32!FreeLibrary` at `0x18002825a`
- `KERNEL32!FreeLibrary` at `0x18002825a`
- `KERNEL32!GetProcAddress` at `0x180028244`
- `KERNEL32!GetProcAddress` at `0x180028244`

## string_xrefs

- `0x18002818a`: `ntdll.dll`
- `0x18002821e`: `ntdll.dll`
- `0x18002826a`: `%s\Temp`
- `0x1800281c8`: `%OSDataDrive%\SystemData\Temp`
- `0x1800281ed`: `%TEMP%`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
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
  unsigned __int8 (*RtlIsStateSeparationEnabled)(void); // rax
  __int64 v10; // rdi
  HMODULE v11; // rax
  HMODULE v12; // r14
  __int64 (*ProcAddress)(void); // rax
  __int64 v14; // r8
  unsigned int v15; // r10d
  DWORD CurrentProcessId_0; // [rsp+30h] [rbp-478h]
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
  GetModuleFileNameW_0(0, Filename, 0x104u);
  if ( GetLastError_0() )
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
  Library = LoadLibraryExW_0(L"ntdll.dll", 0, 0x800u);
  v4 = Library;
  if ( Library
    && (RtlIsStateSeparationEnabled = (unsigned __int8 (*)(void))GetProcAddress_0(
                                                                   Library,
                                                                   "RtlIsStateSeparationEnabled")) != 0
    && RtlIsStateSeparationEnabled() )
  {
    if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
    {
      goto LABEL_7;
    }
  }
  else
  {
    v10 = (__int64)qword_180183C08;
    if ( !qword_180183C08 )
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
      qword_180183C08 = (wchar_t *)v10;
    }
    v2 = RtlStringCchPrintfW(Dst, 0x104u, L"%s\\Temp", v10);
    if ( v2 < 0 )
      goto LABEL_8;
  }
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v2 = RtlStringCchPrintfW(
         (unsigned __int16 *)v1 + 96,
         0x104u,
         L"%s\\AslLog_%S_%s_%d.txt",
         Dst,
         "aeinv",
         v7,
         CurrentProcessId_0);
  if ( v2 < 0 )
    goto LABEL_8;
  *v1 = v1 + 1;
  *(_DWORD *)(*v1 + 80LL) = AslLogGetDefaultFlags();
  RtlStringCopyWorkerA(*v1, 64, v14, "aeinv");
  v15 = *((_DWORD *)v1 + 40);
  if ( v15 <= 0x1000 )
  {
    v15 = 4096;
  }
  else if ( v15 != (v15 & -v15) )
  {
    goto LABEL_36;
  }
  *(_DWORD *)(*v1 + 76LL) = v15;
LABEL_36:
  v2 = 0;
  AslLogger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary_0(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180028028  push    rbx
0x18002802a  push    rbp
0x18002802b  push    rsi
0x18002802c  push    rdi
0x18002802d  push    r14
0x18002802f  push    r15
0x180028031  sub     rsp, 478h
0x180028038  mov     rax, cs:__security_cookie
0x18002803f  xor     rax, rsp
0x180028042  mov     [rsp+4A8h+var_48], rax
0x18002804a  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger AslLogger
0x180028055  mov     edx, 8; Flags
0x18002805a  mov     rcx, gs:60h
0x180028063  mov     r8d, 2D8h; Size
0x180028069  mov     rcx, [rcx+30h]; HeapHandle
0x18002806d  call    cs:__imp_RtlAllocateHeap
0x180028073  mov     rbx, rax
0x180028076  test    rax, rax
0x180028079  jnz     short loc_180028085
0x18002807b  mov     edi, 0C0000017h
0x180028080  jmp     loc_180028139
0x180028085  lea     rcx, [rax+68h]; CriticalSection
0x180028089  mov     qword ptr [rax+2D0h], 0
0x180028094  call    cs:__imp_RtlInitializeCriticalSection
0x18002809a  mov     rax, gs:60h
0x1800280a3  xorps   xmm0, xmm0
0x1800280a6  mov     rcx, [rax+30h]
0x1800280aa  movups  xmmword ptr [rbx+90h], xmm0
0x1800280b1  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800280b8  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800280bf  test    rcx, rcx
0x1800280c2  jnz     short loc_1800280D1
0x1800280c4  mov     rax, gs:60h
0x1800280cd  mov     rcx, [rax+30h]
0x1800280d1  mov     [rbx+90h], rcx
0x1800280d8  lea     r9, [rbx+2C8h]
0x1800280df  lea     rcx, AE_LOG
0x1800280e6  mov     qword ptr [rbx+0A8h], 1000h
0x1800280f1  xor     r8d, r8d
0x1800280f4  xor     edx, edx
0x1800280f6  call    cs:__imp_EtwEventRegister
0x1800280fc  mov     r15d, 104h
0x180028102  lea     rdx, [rsp+4A8h+Filename]; lpFilename
0x18002810a  mov     r8d, r15d; nSize
0x18002810d  xor     ecx, ecx; hModule
0x18002810f  call    GetModuleFileNameW_0
0x180028114  call    GetLastError_0
0x180028119  test    eax, eax
0x18002811b  jz      short loc_18002815B
0x18002811d  xor     ebp, ebp
0x18002811f  mov     edi, 0C0000001h
0x180028124  mov     rcx, rbx
0x180028127  call    AslLogDelete
0x18002812c  test    rbp, rbp
0x18002812f  jz      short loc_180028139
0x180028131  mov     rcx, rbp; hLibModule
0x180028134  call    FreeLibrary_0
0x180028139  mov     eax, edi
0x18002813b  mov     rcx, [rsp+4A8h+var_48]
0x180028143  xor     rcx, rsp; StackCookie
0x180028146  call    __security_check_cookie
0x18002814b  add     rsp, 478h
0x180028152  pop     r15
0x180028154  pop     r14
0x180028156  pop     rdi
0x180028157  pop     rsi
0x180028158  pop     rbp
0x180028159  pop     rbx
0x18002815a  retn
0x18002815b  mov     edx, 5Ch ; '\'; Ch
0x180028160  lea     rcx, [rsp+4A8h+Filename]; Str
0x180028168  call    cs:__imp_wcsrchr
0x18002816e  mov     rsi, rax
0x180028171  test    rax, rax
0x180028174  jnz     short loc_180028180
0x180028176  lea     rsi, [rsp+4A8h+Filename]
0x18002817e  jmp     short loc_180028184
0x180028180  add     rsi, 2
0x180028184  mov     r14d, 800h
0x18002818a  lea     rcx, LibFileName; "ntdll.dll"
0x180028191  mov     r8d, r14d; dwFlags
0x180028194  xor     edx, edx; hFile
0x180028196  call    LoadLibraryExW_0
0x18002819b  mov     rbp, rax
0x18002819e  test    rax, rax
0x1800281a1  jz      short loc_18002820F
0x1800281a3  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x1800281aa  mov     rcx, rax; hModule
0x1800281ad  call    GetProcAddress_0
0x1800281b2  test    rax, rax
0x1800281b5  jz      short loc_18002820F
0x1800281b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281bc  test    al, al
0x1800281be  jz      short loc_18002820F
0x1800281c0  mov     r8d, r15d; nSize
0x1800281c3  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x1800281c8  lea     rcx, Src; "%OSDataDrive%\\SystemData\\Temp"
0x1800281cf  call    cs:__imp_ExpandEnvironmentStringsW
0x1800281d5  test    eax, eax
0x1800281d7  jz      short loc_1800281E5
0x1800281d9  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x1800281df  jnz     loc_180028288
0x1800281e5  mov     r8d, r15d; nSize
0x1800281e8  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x1800281ed  lea     rcx, aTemp; "%TEMP%"
0x1800281f4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800281fa  test    eax, eax
0x1800281fc  jz      loc_18002811F
0x180028202  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x180028208  jnz     short loc_180028288
0x18002820a  jmp     loc_18002811F
0x18002820f  mov     rdi, cs:qword_180183C08
0x180028216  test    rdi, rdi
0x180028219  jnz     short loc_180028267
0x18002821b  mov     r8d, r14d; dwFlags
0x18002821e  lea     rcx, LibFileName; "ntdll.dll"
0x180028225  xor     edx, edx; hFile
0x180028227  mov     edi, 7FFE0030h
0x18002822c  call    cs:__imp_LoadLibraryExW
0x180028232  mov     r14, rax
0x180028235  test    rax, rax
0x180028238  jz      short loc_180028260
0x18002823a  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180028241  mov     rcx, rax; hModule
0x180028244  call    cs:__imp_GetProcAddress
0x18002824a  test    rax, rax
0x18002824d  jz      short loc_180028257
0x18002824f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028254  mov     rdi, rax
0x180028257  mov     rcx, r14; hLibModule
0x18002825a  call    cs:__imp_FreeLibrary
0x180028260  mov     cs:qword_180183C08, rdi
0x180028267  mov     r9, rdi
0x18002826a  lea     r8, aSTemp; "%s\\Temp"
0x180028271  mov     rdx, r15; unsigned __int64
0x180028274  lea     rcx, [rsp+4A8h+Dst]; unsigned __int16 *
0x180028279  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002827e  mov     edi, eax
0x180028280  test    eax, eax
0x180028282  js      loc_180028124
0x180028288  call    GetCurrentProcessId_0
0x18002828d  mov     [rsp+4A8h+var_478], eax
0x180028291  lea     rcx, [rbx+0C0h]; unsigned __int16 *
0x180028298  mov     [rsp+4A8h+var_480], rsi
0x18002829d  lea     r9, [rsp+4A8h+Dst]
0x1800282a2  lea     rsi, aAeinv; "aeinv"
0x1800282a9  mov     rdx, r15; unsigned __int64
0x1800282ac  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x1800282b3  mov     [rsp+4A8h+var_488], rsi
0x1800282b8  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800282bd  mov     edi, eax
0x1800282bf  test    eax, eax
0x1800282c1  js      loc_180028124
0x1800282c7  lea     rax, [rbx+8]
0x1800282cb  mov     [rbx], rax
0x1800282ce  call    AslLogGetDefaultFlags
0x1800282d3  mov     rcx, [rbx]
0x1800282d6  mov     r9, rsi
0x1800282d9  mov     edx, 40h ; '@'
0x1800282de  mov     [rcx+50h], eax
0x1800282e1  mov     rcx, [rbx]
0x1800282e4  call    RtlStringCopyWorkerA
0x1800282e9  mov     r10d, [rbx+0A0h]
0x1800282f0  cmp     r10d, 1000h
0x1800282f7  jbe     short loc_180028308
0x1800282f9  mov     eax, r10d
0x1800282fc  neg     eax
0x1800282fe  and     eax, r10d
0x180028301  cmp     r10d, eax
0x180028304  jz      short loc_18002830E
0x180028306  jmp     short loc_180028315
0x180028308  mov     r10d, 1000h
0x18002830e  mov     rax, [rbx]
0x180028311  mov     [rax+4Ch], r10d
0x180028315  xor     edi, edi
0x180028317  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger AslLogger
0x18002831e  jmp     loc_18002812C
```
