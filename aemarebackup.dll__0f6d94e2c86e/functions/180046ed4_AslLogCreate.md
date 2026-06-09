# AslLogCreate

- ea: `0x180046ed4`
- end: `0x180047197`
- name: `AslLogCreate`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002020`

## callees

- `0x180004ea0`
- `0x180005b90`
- `0x180005be0`
- `0x180005bf0`
- `0x180046a04`
- `0x180046ed4`
- `0x18004795c`
- `0x180047a10`
- `0x18004c2a0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180047012`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180047012`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046fdf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180046fdf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180046fb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180046fb9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004703d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004703d`
- `ntdll!RtlAllocateHeap` at `0x180046f17`
- `ntdll!RtlAllocateHeap` at `0x180046f17`
- `ntdll!EtwEventRegister` at `0x180046fa0`
- `ntdll!EtwEventRegister` at `0x180046fa0`
- `ntdll!RtlInitializeCriticalSection` at `0x180046f3e`
- `ntdll!RtlInitializeCriticalSection` at `0x180046f3e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180047077`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180047098`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180047077`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180047098`

## string_xrefs

- `0x180047030`: `ntdll.dll`
- `0x180047070`: `%OSDataDrive%\SystemData\Temp`
- `0x180047091`: `%TEMP%`
- `0x1800470bb`: `%s\Temp`

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
  *((_QWORD *)v1 + 18) = ProcessHeap;
  *((_QWORD *)v1 + 21) = 4096;
  EtwEventRegister(AE_LOG, 0, 0, v1 + 712);
  GetModuleFileNameW(0, Filename, 0x104u);
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
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
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
  v11 = "AeMareBackup";
  v2 = RtlStringCchPrintfW(v1 + 192, 260, L"%s\\AslLog_%S_%s_%d.txt", Dst, "AeMareBackup", v18, CurrentProcessId_0);
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
  AslLogger = v1;
LABEL_9:
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180046ed4  push    rbx
0x180046ed6  push    rbp
0x180046ed7  push    rsi
0x180046ed8  push    rdi
0x180046ed9  push    r15
0x180046edb  sub     rsp, 470h
0x180046ee2  mov     rax, cs:__security_cookie
0x180046ee9  xor     rax, rsp
0x180046eec  mov     [rsp+498h+var_38], rax
0x180046ef4  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger AslLogger
0x180046eff  mov     edx, 8; Flags
0x180046f04  mov     rcx, gs:60h
0x180046f0d  mov     r8d, 2D8h; Size
0x180046f13  mov     rcx, [rcx+30h]; HeapHandle
0x180046f17  call    cs:__imp_RtlAllocateHeap
0x180046f1d  mov     rbx, rax
0x180046f20  test    rax, rax
0x180046f23  jnz     short loc_180046F2F
0x180046f25  mov     edi, 0C0000017h
0x180046f2a  jmp     loc_180046FE5
0x180046f2f  lea     rcx, [rax+68h]; CriticalSection
0x180046f33  mov     qword ptr [rax+2D0h], 0
0x180046f3e  call    cs:__imp_RtlInitializeCriticalSection
0x180046f44  mov     rax, gs:60h
0x180046f4d  xorps   xmm0, xmm0
0x180046f50  mov     rcx, [rax+30h]
0x180046f54  movups  xmmword ptr [rbx+90h], xmm0
0x180046f5b  movups  xmmword ptr [rbx+0A0h], xmm0
0x180046f62  movups  xmmword ptr [rbx+0B0h], xmm0
0x180046f69  test    rcx, rcx
0x180046f6c  jnz     short loc_180046F7B
0x180046f6e  mov     rax, gs:60h
0x180046f77  mov     rcx, [rax+30h]
0x180046f7b  mov     [rbx+90h], rcx
0x180046f82  mov     qword ptr [rbx+0A8h], 1000h
0x180046f8d  lea     r9, [rbx+2C8h]
0x180046f94  xor     r8d, r8d
0x180046f97  xor     edx, edx
0x180046f99  lea     rcx, AE_LOG
0x180046fa0  call    cs:__imp_EtwEventRegister
0x180046fa6  mov     r15d, 104h
0x180046fac  lea     rdx, [rsp+498h+Filename]; lpFilename
0x180046fb4  mov     r8d, r15d; nSize
0x180046fb7  xor     ecx, ecx; hModule
0x180046fb9  call    cs:__imp_GetModuleFileNameW
0x180046fbf  call    GetLastError_0
0x180046fc4  test    eax, eax
0x180046fc6  jz      short loc_180047005
0x180046fc8  xor     ebp, ebp
0x180046fca  mov     edi, 0C0000001h
0x180046fcf  mov     rcx, rbx; P
0x180046fd2  call    AslLogDelete
0x180046fd7  test    rbp, rbp
0x180046fda  jz      short loc_180046FE5
0x180046fdc  mov     rcx, rbp; hLibModule
0x180046fdf  call    cs:__imp_FreeLibrary
0x180046fe5  mov     eax, edi
0x180046fe7  mov     rcx, [rsp+498h+var_38]
0x180046fef  xor     rcx, rsp; StackCookie
0x180046ff2  call    __security_check_cookie
0x180046ff7  add     rsp, 470h
0x180046ffe  pop     r15
0x180047000  pop     rdi
0x180047001  pop     rsi
0x180047002  pop     rbp
0x180047003  pop     rbx
0x180047004  retn
0x180047005  mov     edx, 5Ch ; '\'; Ch
0x18004700a  lea     rcx, [rsp+498h+Filename]; Str
0x180047012  call    cs:__imp_wcsrchr
0x180047018  mov     rsi, rax
0x18004701b  test    rax, rax
0x18004701e  jnz     short loc_18004702A
0x180047020  lea     rsi, [rsp+498h+Filename]
0x180047028  jmp     short loc_18004702E
0x18004702a  add     rsi, 2
0x18004702e  xor     edx, edx; hFile
0x180047030  lea     rcx, LibFileName; "ntdll.dll"
0x180047037  mov     r8d, 800h; dwFlags
0x18004703d  call    cs:__imp_LoadLibraryExW
0x180047043  mov     rbp, rax
0x180047046  test    rax, rax
0x180047049  jz      short loc_1800470B3
0x18004704b  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x180047052  mov     rcx, rax; hModule
0x180047055  call    GetProcAddress_0
0x18004705a  test    rax, rax
0x18004705d  jz      short loc_1800470B3
0x18004705f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047064  test    al, al
0x180047066  jz      short loc_1800470B3
0x180047068  mov     r8d, r15d; nSize
0x18004706b  lea     rdx, [rsp+498h+Dst]; lpDst
0x180047070  lea     rcx, aOsdatadriveSys; "%OSDataDrive%\\SystemData\\Temp"
0x180047077  call    cs:__imp_ExpandEnvironmentStringsW
0x18004707d  test    eax, eax
0x18004707f  jz      short loc_180047089
0x180047081  cmp     [rsp+498h+Dst], 25h ; '%'
0x180047087  jnz     short loc_1800470D9
0x180047089  mov     r8d, r15d; nSize
0x18004708c  lea     rdx, [rsp+498h+Dst]; lpDst
0x180047091  lea     rcx, aTemp; "%TEMP%"
0x180047098  call    cs:__imp_ExpandEnvironmentStringsW
0x18004709e  test    eax, eax
0x1800470a0  jz      loc_180046FCA
0x1800470a6  cmp     [rsp+498h+Dst], 25h ; '%'
0x1800470ac  jnz     short loc_1800470D9
0x1800470ae  jmp     loc_180046FCA
0x1800470b3  call    AslPathGetNtSystemRoot
0x1800470b8  mov     r9, rax
0x1800470bb  lea     r8, aSTemp; "%s\\Temp"
0x1800470c2  mov     rdx, r15
0x1800470c5  lea     rcx, [rsp+498h+Dst]
0x1800470ca  call    RtlStringCchPrintfW
0x1800470cf  mov     edi, eax
0x1800470d1  test    eax, eax
0x1800470d3  js      loc_180046FCF
0x1800470d9  call    GetCurrentProcessId_0
0x1800470de  mov     [rsp+498h+var_468], eax
0x1800470e2  lea     rcx, [rbx+0C0h]
0x1800470e9  mov     [rsp+498h+var_470], rsi
0x1800470ee  lea     r9, [rsp+498h+Dst]
0x1800470f3  lea     rsi, aAemarebackup; "AeMareBackup"
0x1800470fa  mov     rdx, r15
0x1800470fd  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x180047104  mov     [rsp+498h+var_478], rsi
0x180047109  call    RtlStringCchPrintfW
0x18004710e  mov     edi, eax
0x180047110  test    eax, eax
0x180047112  js      loc_180046FCF
0x180047118  lea     rax, [rbx+8]
0x18004711c  mov     [rbx], rax
0x18004711f  call    AslLogGetDefaultFlags
0x180047124  mov     rcx, [rbx]
0x180047127  mov     edx, 40h ; '@'
0x18004712c  mov     [rcx+50h], eax
0x18004712f  mov     eax, 7FFFFFFEh
0x180047134  mov     rcx, [rbx]
0x180047137  test    rax, rax
0x18004713a  jz      short loc_180047156
0x18004713c  mov     r8b, [rsi]
0x18004713f  test    r8b, r8b
0x180047142  jz      short loc_180047156
0x180047144  mov     [rcx], r8b
0x180047147  inc     rsi
0x18004714a  inc     rcx
0x18004714d  dec     rax
0x180047150  sub     rdx, 1
0x180047154  jnz     short loc_180047137
0x180047156  test    rdx, rdx
0x180047159  lea     rax, [rcx-1]
0x18004715d  cmovnz  rax, rcx
0x180047161  mov     byte ptr [rax], 0
0x180047164  mov     ecx, [rbx+0A0h]
0x18004716a  cmp     ecx, 1000h
0x180047170  jbe     short loc_18004717E
0x180047172  mov     eax, ecx
0x180047174  neg     eax
0x180047176  and     eax, ecx
0x180047178  cmp     ecx, eax
0x18004717a  jnz     short loc_180047189
0x18004717c  jmp     short loc_180047183
0x18004717e  mov     ecx, 1000h
0x180047183  mov     rax, [rbx]
0x180047186  mov     [rax+4Ch], ecx
0x180047189  xor     edi, edi
0x18004718b  mov     cs:?AslLogger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger AslLogger
0x180047192  jmp     loc_180046FD7
```
