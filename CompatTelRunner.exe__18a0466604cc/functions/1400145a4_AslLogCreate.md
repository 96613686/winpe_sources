# AslLogCreate

- ea: `0x1400145a4`
- end: `0x14001486a`
- name: `AslLogCreate`
- size: `710`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400017a0`

## callees

- `0x140001ba0`
- `0x140014474`
- `0x1400145a4`
- `0x140015034`
- `0x1400150e8`
- `0x1400166c8`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400146e3`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400146e3`
- `ntdll!EtwEventRegister` at `0x140014670`
- `ntdll!EtwEventRegister` at `0x140014670`
- `ntdll!RtlInitializeCriticalSection` at `0x14001460e`
- `ntdll!RtlInitializeCriticalSection` at `0x14001460e`
- `ntdll!RtlAllocateHeap` at `0x1400145e7`
- `ntdll!RtlAllocateHeap` at `0x1400145e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014726`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014726`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001470e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001470e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140014689`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140014689`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400146b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400146b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001468f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001468f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400147ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400147ab`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140014749`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14001476a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140014749`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14001476a`

## string_xrefs

- `0x140014701`: `ntdll.dll`
- `0x1400147c4`: `compattelrunner`
- `0x140014742`: `%OSDataDrive%\SystemData\Temp`
- `0x140014763`: `%TEMP%`
- `0x14001478d`: `%s\Temp`

## pseudocode

```c
__int64 AslLogCreate()
{
  char *Heap; // rax
  char *v1; // rbx
  int v2; // edi
  PVOID ProcessHeap; // rcx
  HMODULE v4; // rbp
  wchar_t *v6; // rax
  WCHAR *v7; // rsi
  HMODULE Library; // rax
  __int64 v9; // rcx
  unsigned __int8 (*ProcAddress)(void); // rax
  __int64 NtSystemRoot; // rax
  const char *v12; // rsi
  int DefaultFlags; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  _BYTE *v16; // rcx
  _BYTE *v17; // rax
  unsigned int v18; // ecx
  WCHAR *v19; // [rsp+28h] [rbp-470h]
  DWORD CurrentProcessId; // [rsp+30h] [rbp-468h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-248h] BYREF

  g_Logger = 0;
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
  *((_QWORD *)v1 + 18) = ProcessHeap;
  *((_QWORD *)v1 + 21) = 4096;
  EtwEventRegister(AE_LOG, 0, 0, v1 + 712);
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
  if ( Library
    && (ProcAddress = (unsigned __int8 (*)(void))GetProcAddress(Library, "RtlIsStateSeparationEnabled")) != 0
    && ProcAddress() )
  {
    if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
    {
      goto LABEL_7;
    }
  }
  else
  {
    NtSystemRoot = AslPathGetNtSystemRoot(v9);
    v2 = RtlStringCchPrintfW(Dst, 0x104u, L"%s\\Temp", NtSystemRoot);
    if ( v2 < 0 )
      goto LABEL_8;
  }
  CurrentProcessId = GetCurrentProcessId();
  v19 = v7;
  v12 = "compattelrunner";
  v2 = RtlStringCchPrintfW(
         (unsigned __int16 *)v1 + 96,
         0x104u,
         L"%s\\AslLog_%S_%s_%d.txt",
         Dst,
         "compattelrunner",
         v19,
         CurrentProcessId);
  if ( v2 < 0 )
    goto LABEL_8;
  *(_QWORD *)v1 = v1 + 8;
  DefaultFlags = AslLogGetDefaultFlags();
  v14 = 64;
  *(_DWORD *)(*(_QWORD *)v1 + 80LL) = DefaultFlags;
  v15 = 2147483646;
  v16 = *(_BYTE **)v1;
  do
  {
    if ( !v15 )
      break;
    if ( !*v12 )
      break;
    *v16++ = *v12++;
    --v15;
    --v14;
  }
  while ( v14 );
  v17 = v16 - 1;
  if ( v14 )
    v17 = v16;
  *v17 = 0;
  v18 = *((_DWORD *)v1 + 40);
  if ( v18 <= 0x1000 )
  {
    v18 = 4096;
LABEL_35:
    *(_DWORD *)(*(_QWORD *)v1 + 76LL) = v18;
    goto LABEL_36;
  }
  if ( v18 == (v18 & -v18) )
    goto LABEL_35;
LABEL_36:
  v2 = 0;
  g_Logger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400145a4  push    rbx
0x1400145a6  push    rbp
0x1400145a7  push    rsi
0x1400145a8  push    rdi
0x1400145a9  push    r15
0x1400145ab  sub     rsp, 470h
0x1400145b2  mov     rax, cs:__security_cookie
0x1400145b9  xor     rax, rsp
0x1400145bc  mov     [rsp+498h+var_38], rax
0x1400145c4  mov     cs:?g_Logger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger g_Logger
0x1400145cf  mov     edx, 8; Flags
0x1400145d4  mov     rcx, gs:60h
0x1400145dd  mov     r8d, 2D8h; Size
0x1400145e3  mov     rcx, [rcx+30h]; HeapHandle
0x1400145e7  call    cs:__imp_RtlAllocateHeap
0x1400145ed  mov     rbx, rax
0x1400145f0  test    rax, rax
0x1400145f3  jnz     short loc_1400145FF
0x1400145f5  mov     edi, 0C0000017h
0x1400145fa  jmp     loc_1400146B6
0x1400145ff  lea     rcx, [rax+68h]; CriticalSection
0x140014603  mov     qword ptr [rax+2D0h], 0
0x14001460e  call    cs:__imp_RtlInitializeCriticalSection
0x140014614  mov     rax, gs:60h
0x14001461d  xorps   xmm0, xmm0
0x140014620  mov     rcx, [rax+30h]
0x140014624  movups  xmmword ptr [rbx+90h], xmm0
0x14001462b  movups  xmmword ptr [rbx+0A0h], xmm0
0x140014632  movups  xmmword ptr [rbx+0B0h], xmm0
0x140014639  test    rcx, rcx
0x14001463c  jnz     short loc_14001464B
0x14001463e  mov     rax, gs:60h
0x140014647  mov     rcx, [rax+30h]
0x14001464b  mov     [rbx+90h], rcx
0x140014652  mov     qword ptr [rbx+0A8h], 1000h
0x14001465d  lea     r9, [rbx+2C8h]
0x140014664  xor     r8d, r8d
0x140014667  xor     edx, edx
0x140014669  lea     rcx, AE_LOG
0x140014670  call    cs:__imp_EtwEventRegister
0x140014676  mov     r15d, 104h
0x14001467c  lea     rdx, [rsp+498h+Filename]; lpFilename
0x140014684  mov     r8d, r15d; nSize
0x140014687  xor     ecx, ecx; hModule
0x140014689  call    cs:__imp_GetModuleFileNameW
0x14001468f  call    cs:__imp_GetLastError
0x140014695  test    eax, eax
0x140014697  jz      short loc_1400146D6
0x140014699  xor     ebp, ebp
0x14001469b  mov     edi, 0C0000001h
0x1400146a0  mov     rcx, rbx; P
0x1400146a3  call    AslLogDelete
0x1400146a8  test    rbp, rbp
0x1400146ab  jz      short loc_1400146B6
0x1400146ad  mov     rcx, rbp; hLibModule
0x1400146b0  call    cs:__imp_FreeLibrary
0x1400146b6  mov     eax, edi
0x1400146b8  mov     rcx, [rsp+498h+var_38]
0x1400146c0  xor     rcx, rsp; StackCookie
0x1400146c3  call    __security_check_cookie
0x1400146c8  add     rsp, 470h
0x1400146cf  pop     r15
0x1400146d1  pop     rdi
0x1400146d2  pop     rsi
0x1400146d3  pop     rbp
0x1400146d4  pop     rbx
0x1400146d5  retn
0x1400146d6  mov     edx, 5Ch ; '\'; Ch
0x1400146db  lea     rcx, [rsp+498h+Filename]; Str
0x1400146e3  call    cs:__imp_wcsrchr
0x1400146e9  mov     rsi, rax
0x1400146ec  test    rax, rax
0x1400146ef  jnz     short loc_1400146FB
0x1400146f1  lea     rsi, [rsp+498h+Filename]
0x1400146f9  jmp     short loc_1400146FF
0x1400146fb  add     rsi, 2
0x1400146ff  xor     edx, edx; hFile
0x140014701  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140014708  mov     r8d, 800h; dwFlags
0x14001470e  call    cs:__imp_LoadLibraryExW
0x140014714  mov     rbp, rax
0x140014717  test    rax, rax
0x14001471a  jz      short loc_140014785
0x14001471c  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x140014723  mov     rcx, rax; hModule
0x140014726  call    cs:__imp_GetProcAddress
0x14001472c  test    rax, rax
0x14001472f  jz      short loc_140014785
0x140014731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014736  test    al, al
0x140014738  jz      short loc_140014785
0x14001473a  mov     r8d, r15d; nSize
0x14001473d  lea     rdx, [rsp+498h+Dst]; lpDst
0x140014742  lea     rcx, Src; "%OSDataDrive%\\SystemData\\Temp"
0x140014749  call    cs:__imp_ExpandEnvironmentStringsW
0x14001474f  test    eax, eax
0x140014751  jz      short loc_14001475B
0x140014753  cmp     [rsp+498h+Dst], 25h ; '%'
0x140014759  jnz     short loc_1400147AB
0x14001475b  mov     r8d, r15d; nSize
0x14001475e  lea     rdx, [rsp+498h+Dst]; lpDst
0x140014763  lea     rcx, aTemp; "%TEMP%"
0x14001476a  call    cs:__imp_ExpandEnvironmentStringsW
0x140014770  test    eax, eax
0x140014772  jz      loc_14001469B
0x140014778  cmp     [rsp+498h+Dst], 25h ; '%'
0x14001477e  jnz     short loc_1400147AB
0x140014780  jmp     loc_14001469B
0x140014785  call    AslPathGetNtSystemRoot
0x14001478a  mov     r9, rax
0x14001478d  lea     r8, aSTemp; "%s\\Temp"
0x140014794  mov     rdx, r15; unsigned __int64
0x140014797  lea     rcx, [rsp+498h+Dst]; unsigned __int16 *
0x14001479c  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400147a1  mov     edi, eax
0x1400147a3  test    eax, eax
0x1400147a5  js      loc_1400146A0
0x1400147ab  call    cs:__imp_GetCurrentProcessId
0x1400147b1  mov     [rsp+498h+var_468], eax
0x1400147b5  lea     rcx, [rbx+0C0h]; unsigned __int16 *
0x1400147bc  mov     [rsp+498h+var_470], rsi
0x1400147c1  mov     rdx, r15; unsigned __int64
0x1400147c4  lea     rsi, aCompattelrunne; "compattelrunner"
0x1400147cb  lea     r9, [rsp+498h+Dst]
0x1400147d0  mov     [rsp+498h+var_478], rsi
0x1400147d5  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x1400147dc  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400147e1  mov     edi, eax
0x1400147e3  test    eax, eax
0x1400147e5  js      loc_1400146A0
0x1400147eb  lea     rax, [rbx+8]
0x1400147ef  mov     [rbx], rax
0x1400147f2  call    AslLogGetDefaultFlags
0x1400147f7  mov     rcx, [rbx]
0x1400147fa  mov     edx, 40h ; '@'
0x1400147ff  mov     [rcx+50h], eax
0x140014802  mov     eax, 7FFFFFFEh
0x140014807  mov     rcx, [rbx]
0x14001480a  test    rax, rax
0x14001480d  jz      short loc_140014829
0x14001480f  mov     r8b, [rsi]
0x140014812  test    r8b, r8b
0x140014815  jz      short loc_140014829
0x140014817  mov     [rcx], r8b
0x14001481a  inc     rsi
0x14001481d  inc     rcx
0x140014820  dec     rax
0x140014823  sub     rdx, 1
0x140014827  jnz     short loc_14001480A
0x140014829  test    rdx, rdx
0x14001482c  lea     rax, [rcx-1]
0x140014830  cmovnz  rax, rcx
0x140014834  mov     byte ptr [rax], 0
0x140014837  mov     ecx, [rbx+0A0h]
0x14001483d  cmp     ecx, 1000h
0x140014843  jbe     short loc_140014851
0x140014845  mov     eax, ecx
0x140014847  neg     eax
0x140014849  and     eax, ecx
0x14001484b  cmp     ecx, eax
0x14001484d  jnz     short loc_14001485C
0x14001484f  jmp     short loc_140014856
0x140014851  mov     ecx, 1000h
0x140014856  mov     rax, [rbx]
0x140014859  mov     [rax+4Ch], ecx
0x14001485c  xor     edi, edi
0x14001485e  mov     cs:?g_Logger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger g_Logger
0x140014865  jmp     loc_1400146A8
```
