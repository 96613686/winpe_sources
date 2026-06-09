# AslLogCreate

- ea: `0x18001304c`
- end: `0x18001330c`
- name: `AslLogCreate`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800025d0`

## callees

- `0x180002bf0`
- `0x1800039f0`
- `0x180003a40`
- `0x180003a50`
- `0x180003ad0`
- `0x180003adc`
- `0x180003ae8`
- `0x180012f1c`
- `0x18001304c`
- `0x180013ad0`
- `0x180013b84`
- `0x1800167d4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180013188`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180013188`
- `ntdll!EtwEventRegister` at `0x180013118`
- `ntdll!EtwEventRegister` at `0x180013118`
- `ntdll!RtlInitializeCriticalSection` at `0x1800130b6`
- `ntdll!RtlInitializeCriticalSection` at `0x1800130b6`
- `ntdll!RtlAllocateHeap` at `0x18001308f`
- `ntdll!RtlAllocateHeap` at `0x18001308f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800131ec`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001320d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800131ec`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001320d`

## string_xrefs

- `0x1800131a6`: `ntdll.dll`
- `0x1800131e5`: `%OSDataDrive%\SystemData\Temp`
- `0x180013206`: `%TEMP%`
- `0x180013230`: `%s\Temp`

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
  unsigned __int8 (*RtlIsStateSeparationEnabled)(void); // rax
  __int64 NtSystemRoot; // rax
  const char *v11; // rsi
  int DefaultFlags; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  _BYTE *v15; // rcx
  _BYTE *v16; // rax
  unsigned int v17; // ecx
  WCHAR *v18; // [rsp+28h] [rbp-470h]
  DWORD CurrentProcessId_0; // [rsp+30h] [rbp-468h]
  WCHAR Dst[264]; // [rsp+40h] [rbp-458h] BYREF
  WCHAR Filename[264]; // [rsp+250h] [rbp-248h] BYREF

  g_invSvcAslLogger = 0;
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
    NtSystemRoot = AslPathGetNtSystemRoot();
    v2 = RtlStringCchPrintfW(Dst, 260, L"%s\\Temp", NtSystemRoot);
    if ( v2 < 0 )
      goto LABEL_8;
  }
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v18 = v7;
  v11 = "InventorySvc";
  v2 = RtlStringCchPrintfW(v1 + 192, 260, L"%s\\AslLog_%S_%s_%d.txt", Dst, "InventorySvc", v18, CurrentProcessId_0);
  if ( v2 < 0 )
    goto LABEL_8;
  *(_QWORD *)v1 = v1 + 8;
  DefaultFlags = AslLogGetDefaultFlags();
  v13 = 64;
  *(_DWORD *)(*(_QWORD *)v1 + 80LL) = DefaultFlags;
  v14 = 2147483646;
  v15 = *(_BYTE **)v1;
  do
  {
    if ( !v14 )
      break;
    if ( !*v11 )
      break;
    *v15++ = *v11++;
    --v14;
    --v13;
  }
  while ( v13 );
  v16 = v15 - 1;
  if ( v13 )
    v16 = v15;
  *v16 = 0;
  v17 = *((_DWORD *)v1 + 40);
  if ( v17 <= 0x1000 )
  {
    v17 = 4096;
LABEL_35:
    *(_DWORD *)(*(_QWORD *)v1 + 76LL) = v17;
    goto LABEL_36;
  }
  if ( v17 == (v17 & -v17) )
    goto LABEL_35;
LABEL_36:
  v2 = 0;
  g_invSvcAslLogger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary_0(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001304c  push    rbx
0x18001304e  push    rbp
0x18001304f  push    rsi
0x180013050  push    rdi
0x180013051  push    r15
0x180013053  sub     rsp, 470h
0x18001305a  mov     rax, cs:__security_cookie
0x180013061  xor     rax, rsp
0x180013064  mov     [rsp+498h+var_38], rax
0x18001306c  mov     cs:?g_invSvcAslLogger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger g_invSvcAslLogger
0x180013077  mov     edx, 8; Flags
0x18001307c  mov     rcx, gs:60h
0x180013085  mov     r8d, 2D8h; Size
0x18001308b  mov     rcx, [rcx+30h]; HeapHandle
0x18001308f  call    cs:__imp_RtlAllocateHeap
0x180013095  mov     rbx, rax
0x180013098  test    rax, rax
0x18001309b  jnz     short loc_1800130A7
0x18001309d  mov     edi, 0C0000017h
0x1800130a2  jmp     loc_18001315B
0x1800130a7  lea     rcx, [rax+68h]; CriticalSection
0x1800130ab  mov     qword ptr [rax+2D0h], 0
0x1800130b6  call    cs:__imp_RtlInitializeCriticalSection
0x1800130bc  mov     rax, gs:60h
0x1800130c5  xorps   xmm0, xmm0
0x1800130c8  mov     rcx, [rax+30h]
0x1800130cc  movups  xmmword ptr [rbx+90h], xmm0
0x1800130d3  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800130da  movups  xmmword ptr [rbx+0B0h], xmm0
0x1800130e1  test    rcx, rcx
0x1800130e4  jnz     short loc_1800130F3
0x1800130e6  mov     rax, gs:60h
0x1800130ef  mov     rcx, [rax+30h]
0x1800130f3  mov     [rbx+90h], rcx
0x1800130fa  mov     qword ptr [rbx+0A8h], 1000h
0x180013105  lea     r9, [rbx+2C8h]
0x18001310c  xor     r8d, r8d
0x18001310f  xor     edx, edx
0x180013111  lea     rcx, AE_LOG
0x180013118  call    cs:__imp_EtwEventRegister
0x18001311e  mov     r15d, 104h
0x180013124  lea     rdx, [rsp+498h+Filename]; lpFilename
0x18001312c  mov     r8d, r15d; nSize
0x18001312f  xor     ecx, ecx; hModule
0x180013131  call    GetModuleFileNameW_0
0x180013136  call    GetLastError_0
0x18001313b  test    eax, eax
0x18001313d  jz      short loc_18001317B
0x18001313f  xor     ebp, ebp
0x180013141  mov     edi, 0C0000001h
0x180013146  mov     rcx, rbx; P
0x180013149  call    AslLogDelete
0x18001314e  test    rbp, rbp
0x180013151  jz      short loc_18001315B
0x180013153  mov     rcx, rbp; hLibModule
0x180013156  call    FreeLibrary_0
0x18001315b  mov     eax, edi
0x18001315d  mov     rcx, [rsp+498h+var_38]
0x180013165  xor     rcx, rsp; StackCookie
0x180013168  call    __security_check_cookie
0x18001316d  add     rsp, 470h
0x180013174  pop     r15
0x180013176  pop     rdi
0x180013177  pop     rsi
0x180013178  pop     rbp
0x180013179  pop     rbx
0x18001317a  retn
0x18001317b  mov     edx, 5Ch ; '\'; Ch
0x180013180  lea     rcx, [rsp+498h+Filename]; Str
0x180013188  call    cs:__imp_wcsrchr
0x18001318e  mov     rsi, rax
0x180013191  test    rax, rax
0x180013194  jnz     short loc_1800131A0
0x180013196  lea     rsi, [rsp+498h+Filename]
0x18001319e  jmp     short loc_1800131A4
0x1800131a0  add     rsi, 2
0x1800131a4  xor     edx, edx; hFile
0x1800131a6  lea     rcx, LibFileName; "ntdll.dll"
0x1800131ad  mov     r8d, 800h; dwFlags
0x1800131b3  call    LoadLibraryExW_0
0x1800131b8  mov     rbp, rax
0x1800131bb  test    rax, rax
0x1800131be  jz      short loc_180013228
0x1800131c0  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x1800131c7  mov     rcx, rax; hModule
0x1800131ca  call    GetProcAddress_0
0x1800131cf  test    rax, rax
0x1800131d2  jz      short loc_180013228
0x1800131d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131d9  test    al, al
0x1800131db  jz      short loc_180013228
0x1800131dd  mov     r8d, r15d; nSize
0x1800131e0  lea     rdx, [rsp+498h+Dst]; lpDst
0x1800131e5  lea     rcx, Src; "%OSDataDrive%\\SystemData\\Temp"
0x1800131ec  call    cs:__imp_ExpandEnvironmentStringsW
0x1800131f2  test    eax, eax
0x1800131f4  jz      short loc_1800131FE
0x1800131f6  cmp     [rsp+498h+Dst], 25h ; '%'
0x1800131fc  jnz     short loc_18001324E
0x1800131fe  mov     r8d, r15d; nSize
0x180013201  lea     rdx, [rsp+498h+Dst]; lpDst
0x180013206  lea     rcx, aTemp; "%TEMP%"
0x18001320d  call    cs:__imp_ExpandEnvironmentStringsW
0x180013213  test    eax, eax
0x180013215  jz      loc_180013141
0x18001321b  cmp     [rsp+498h+Dst], 25h ; '%'
0x180013221  jnz     short loc_18001324E
0x180013223  jmp     loc_180013141
0x180013228  call    AslPathGetNtSystemRoot
0x18001322d  mov     r9, rax
0x180013230  lea     r8, aSTemp; "%s\\Temp"
0x180013237  mov     rdx, r15
0x18001323a  lea     rcx, [rsp+498h+Dst]
0x18001323f  call    RtlStringCchPrintfW
0x180013244  mov     edi, eax
0x180013246  test    eax, eax
0x180013248  js      loc_180013146
0x18001324e  call    GetCurrentProcessId_0
0x180013253  mov     [rsp+498h+var_468], eax
0x180013257  lea     rcx, [rbx+0C0h]
0x18001325e  mov     [rsp+498h+var_470], rsi
0x180013263  lea     r9, [rsp+498h+Dst]
0x180013268  lea     rsi, aInventorysvc_0; "InventorySvc"
0x18001326f  mov     rdx, r15
0x180013272  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x180013279  mov     [rsp+498h+var_478], rsi
0x18001327e  call    RtlStringCchPrintfW
0x180013283  mov     edi, eax
0x180013285  test    eax, eax
0x180013287  js      loc_180013146
0x18001328d  lea     rax, [rbx+8]
0x180013291  mov     [rbx], rax
0x180013294  call    AslLogGetDefaultFlags
0x180013299  mov     rcx, [rbx]
0x18001329c  mov     edx, 40h ; '@'
0x1800132a1  mov     [rcx+50h], eax
0x1800132a4  mov     eax, 7FFFFFFEh
0x1800132a9  mov     rcx, [rbx]
0x1800132ac  test    rax, rax
0x1800132af  jz      short loc_1800132CB
0x1800132b1  mov     r8b, [rsi]
0x1800132b4  test    r8b, r8b
0x1800132b7  jz      short loc_1800132CB
0x1800132b9  mov     [rcx], r8b
0x1800132bc  inc     rsi
0x1800132bf  inc     rcx
0x1800132c2  dec     rax
0x1800132c5  sub     rdx, 1
0x1800132c9  jnz     short loc_1800132AC
0x1800132cb  test    rdx, rdx
0x1800132ce  lea     rax, [rcx-1]
0x1800132d2  cmovnz  rax, rcx
0x1800132d6  mov     byte ptr [rax], 0
0x1800132d9  mov     ecx, [rbx+0A0h]
0x1800132df  cmp     ecx, 1000h
0x1800132e5  jbe     short loc_1800132F3
0x1800132e7  mov     eax, ecx
0x1800132e9  neg     eax
0x1800132eb  and     eax, ecx
0x1800132ed  cmp     ecx, eax
0x1800132ef  jnz     short loc_1800132FE
0x1800132f1  jmp     short loc_1800132F8
0x1800132f3  mov     ecx, 1000h
0x1800132f8  mov     rax, [rbx]
0x1800132fb  mov     [rax+4Ch], ecx
0x1800132fe  xor     edi, edi
0x180013300  mov     cs:?g_invSvcAslLogger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger g_invSvcAslLogger
0x180013307  jmp     loc_18001314E
```
