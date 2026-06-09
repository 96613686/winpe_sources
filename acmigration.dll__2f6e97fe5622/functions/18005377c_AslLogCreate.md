# AslLogCreate

- ea: `0x18005377c`
- end: `0x180053a60`
- name: `AslLogCreate`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001700`

## callees

- `0x180001cf0`
- `0x180002a8b`
- `0x180002aaf`
- `0x180002abb`
- `0x180002b03`
- `0x180002b0f`
- `0x180002b63`
- `0x18005364c`
- `0x18005377c`
- `0x180054224`
- `0x1800542d8`
- `0x18005a404`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800538de`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800538de`
- `KERNEL32!GetModuleFileNameW` at `0x180053886`
- `KERNEL32!GetModuleFileNameW` at `0x180053886`
- `KERNEL32!GetProcessHeap` at `0x180053816`
- `KERNEL32!GetProcessHeap` at `0x180053816`
- `ntdll!RtlAllocateHeap` at `0x1800537bf`
- `ntdll!RtlAllocateHeap` at `0x1800537bf`
- `ntdll!RtlInitializeCriticalSection` at `0x1800537e6`
- `ntdll!RtlInitializeCriticalSection` at `0x1800537e6`
- `ntdll!EtwEventRegister` at `0x18005386d`
- `ntdll!EtwEventRegister` at `0x18005386d`

## string_xrefs

- `0x1800538fc`: `ntdll.dll`
- `0x18005395b`: `%TEMP%`
- `0x18005393b`: `%OSDataDrive%\SystemData\Temp`
- `0x180053984`: `%s\Temp`

## pseudocode

```c
__int64 AslLogCreate()
{
  char *Heap; // rax
  char *v1; // rbx
  int v2; // edi
  PVOID ProcessHeap; // rax
  HMODULE v4; // rbp
  wchar_t *v6; // rax
  WCHAR *v7; // rsi
  HMODULE Library; // rax
  unsigned __int8 (*ProcAddress)(void); // rax
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
    ProcessHeap = GetProcessHeap();
  *((_QWORD *)v1 + 18) = ProcessHeap;
  *((_QWORD *)v1 + 19) = 0;
  *((_QWORD *)v1 + 20) = 0;
  *((_QWORD *)v1 + 21) = 4096;
  *((_QWORD *)v1 + 22) = 0;
  *((_QWORD *)v1 + 23) = 0;
  EtwEventRegister(&AE_LOG, 0, 0, v1 + 712);
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
  Library = LoadLibraryExW_0(L"ntdll.dll", 0, 0x800u);
  v4 = Library;
  if ( Library
    && (ProcAddress = (unsigned __int8 (*)(void))WINRT_IMPL_GetProcAddress(Library, "RtlIsStateSeparationEnabled")) != 0
    && ProcAddress() )
  {
    if ( (!ExpandEnvironmentStringsW_0(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
      && (!ExpandEnvironmentStringsW_0(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
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
  v11 = "acmigration";
  v2 = RtlStringCchPrintfW(v1 + 192, 260, L"%s\\AslLog_%S_%s_%d.txt", Dst, "acmigration", v18, CurrentProcessId_0);
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
  g_Logger = v1;
LABEL_9:
  if ( v4 )
    WINRT_IMPL_FreeLibrary(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005377c  push    rbx
0x18005377e  push    rbp
0x18005377f  push    rsi
0x180053780  push    rdi
0x180053781  push    r15
0x180053783  sub     rsp, 470h
0x18005378a  mov     rax, cs:__security_cookie
0x180053791  xor     rax, rsp
0x180053794  mov     [rsp+498h+var_38], rax
0x18005379c  mov     cs:?g_Logger@@3VAslLogGlobalLogger@@A, 0; AslLogGlobalLogger g_Logger
0x1800537a7  mov     edx, 8; Flags
0x1800537ac  mov     rcx, gs:60h
0x1800537b5  mov     r8d, 2D8h; Size
0x1800537bb  mov     rcx, [rcx+30h]; HeapHandle
0x1800537bf  call    cs:__imp_RtlAllocateHeap
0x1800537c5  mov     rbx, rax
0x1800537c8  test    rax, rax
0x1800537cb  jnz     short loc_1800537D7
0x1800537cd  mov     edi, 0C0000017h
0x1800537d2  jmp     loc_1800538B1
0x1800537d7  lea     rcx, [rax+68h]; CriticalSection
0x1800537db  mov     qword ptr [rax+2D0h], 0
0x1800537e6  call    cs:__imp_RtlInitializeCriticalSection
0x1800537ec  mov     rax, gs:60h
0x1800537f5  xorps   xmm0, xmm0
0x1800537f8  mov     rax, [rax+30h]
0x1800537fc  movups  xmmword ptr [rbx+90h], xmm0
0x180053803  movups  xmmword ptr [rbx+0A0h], xmm0
0x18005380a  movups  xmmword ptr [rbx+0B0h], xmm0
0x180053811  test    rax, rax
0x180053814  jnz     short loc_18005381C
0x180053816  call    cs:__imp_GetProcessHeap
0x18005381c  mov     [rbx+90h], rax
0x180053823  mov     qword ptr [rbx+98h], 0
0x18005382e  mov     qword ptr [rbx+0A0h], 0
0x180053839  mov     qword ptr [rbx+0A8h], 1000h
0x180053844  mov     qword ptr [rbx+0B0h], 0
0x18005384f  mov     qword ptr [rbx+0B8h], 0
0x18005385a  lea     r9, [rbx+2C8h]
0x180053861  xor     r8d, r8d
0x180053864  xor     edx, edx
0x180053866  lea     rcx, AE_LOG
0x18005386d  call    cs:__imp_EtwEventRegister
0x180053873  mov     r15d, 104h
0x180053879  lea     rdx, [rsp+498h+Filename]; lpFilename
0x180053881  mov     r8d, r15d; nSize
0x180053884  xor     ecx, ecx; hModule
0x180053886  call    cs:__imp_GetModuleFileNameW
0x18005388c  call    GetLastError_0
0x180053891  test    eax, eax
0x180053893  jz      short loc_1800538D1
0x180053895  xor     ebp, ebp
0x180053897  mov     edi, 0C0000001h
0x18005389c  mov     rcx, rbx; P
0x18005389f  call    AslLogDelete
0x1800538a4  test    rbp, rbp
0x1800538a7  jz      short loc_1800538B1
0x1800538a9  mov     rcx, rbp; hLibModule
0x1800538ac  call    WINRT_IMPL_FreeLibrary
0x1800538b1  mov     eax, edi
0x1800538b3  mov     rcx, [rsp+498h+var_38]
0x1800538bb  xor     rcx, rsp; StackCookie
0x1800538be  call    __security_check_cookie
0x1800538c3  add     rsp, 470h
0x1800538ca  pop     r15
0x1800538cc  pop     rdi
0x1800538cd  pop     rsi
0x1800538ce  pop     rbp
0x1800538cf  pop     rbx
0x1800538d0  retn
0x1800538d1  mov     edx, 5Ch ; '\'; Ch
0x1800538d6  lea     rcx, [rsp+498h+Filename]; Str
0x1800538de  call    cs:__imp_wcsrchr
0x1800538e4  mov     rsi, rax
0x1800538e7  test    rax, rax
0x1800538ea  jnz     short loc_1800538F6
0x1800538ec  lea     rsi, [rsp+498h+Filename]
0x1800538f4  jmp     short loc_1800538FA
0x1800538f6  add     rsi, 2
0x1800538fa  xor     edx, edx; hFile
0x1800538fc  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180053903  mov     r8d, 800h; dwFlags
0x180053909  call    LoadLibraryExW_0
0x18005390e  mov     rbp, rax
0x180053911  test    rax, rax
0x180053914  jz      short loc_18005397C
0x180053916  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x18005391d  mov     rcx, rax; hModule
0x180053920  call    WINRT_IMPL_GetProcAddress
0x180053925  test    rax, rax
0x180053928  jz      short loc_18005397C
0x18005392a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005392f  test    al, al
0x180053931  jz      short loc_18005397C
0x180053933  mov     r8d, r15d; nSize
0x180053936  lea     rdx, [rsp+498h+Dst]; lpDst
0x18005393b  lea     rcx, aOsdatadriveSys; "%OSDataDrive%\\SystemData\\Temp"
0x180053942  call    ExpandEnvironmentStringsW_0
0x180053947  test    eax, eax
0x180053949  jz      short loc_180053953
0x18005394b  cmp     [rsp+498h+Dst], 25h ; '%'
0x180053951  jnz     short loc_1800539A2
0x180053953  mov     r8d, r15d; nSize
0x180053956  lea     rdx, [rsp+498h+Dst]; lpDst
0x18005395b  lea     rcx, aTemp; "%TEMP%"
0x180053962  call    ExpandEnvironmentStringsW_0
0x180053967  test    eax, eax
0x180053969  jz      loc_180053897
0x18005396f  cmp     [rsp+498h+Dst], 25h ; '%'
0x180053975  jnz     short loc_1800539A2
0x180053977  jmp     loc_180053897
0x18005397c  call    AslPathGetNtSystemRoot
0x180053981  mov     r9, rax
0x180053984  lea     r8, aSTemp; "%s\\Temp"
0x18005398b  mov     rdx, r15
0x18005398e  lea     rcx, [rsp+498h+Dst]
0x180053993  call    RtlStringCchPrintfW
0x180053998  mov     edi, eax
0x18005399a  test    eax, eax
0x18005399c  js      loc_18005389C
0x1800539a2  call    GetCurrentProcessId_0
0x1800539a7  mov     [rsp+498h+var_468], eax
0x1800539ab  lea     rcx, [rbx+0C0h]
0x1800539b2  mov     [rsp+498h+var_470], rsi
0x1800539b7  lea     r9, [rsp+498h+Dst]
0x1800539bc  lea     rsi, aAcmigration; "acmigration"
0x1800539c3  mov     rdx, r15
0x1800539c6  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x1800539cd  mov     [rsp+498h+var_478], rsi
0x1800539d2  call    RtlStringCchPrintfW
0x1800539d7  mov     edi, eax
0x1800539d9  test    eax, eax
0x1800539db  js      loc_18005389C
0x1800539e1  lea     rax, [rbx+8]
0x1800539e5  mov     [rbx], rax
0x1800539e8  call    AslLogGetDefaultFlags
0x1800539ed  mov     rcx, [rbx]
0x1800539f0  mov     edx, 40h ; '@'
0x1800539f5  mov     [rcx+50h], eax
0x1800539f8  mov     eax, 7FFFFFFEh
0x1800539fd  mov     rcx, [rbx]
0x180053a00  test    rax, rax
0x180053a03  jz      short loc_180053A1F
0x180053a05  mov     r8b, [rsi]
0x180053a08  test    r8b, r8b
0x180053a0b  jz      short loc_180053A1F
0x180053a0d  mov     [rcx], r8b
0x180053a10  inc     rsi
0x180053a13  inc     rcx
0x180053a16  dec     rax
0x180053a19  sub     rdx, 1
0x180053a1d  jnz     short loc_180053A00
0x180053a1f  test    rdx, rdx
0x180053a22  lea     rax, [rcx-1]
0x180053a26  cmovnz  rax, rcx
0x180053a2a  mov     byte ptr [rax], 0
0x180053a2d  mov     ecx, [rbx+0A0h]
0x180053a33  cmp     ecx, 1000h
0x180053a39  jbe     short loc_180053A47
0x180053a3b  mov     eax, ecx
0x180053a3d  neg     eax
0x180053a3f  and     eax, ecx
0x180053a41  cmp     ecx, eax
0x180053a43  jnz     short loc_180053A52
0x180053a45  jmp     short loc_180053A4C
0x180053a47  mov     ecx, 1000h
0x180053a4c  mov     rax, [rbx]
0x180053a4f  mov     [rax+4Ch], ecx
0x180053a52  xor     edi, edi
0x180053a54  mov     cs:?g_Logger@@3VAslLogGlobalLogger@@A, rbx; AslLogGlobalLogger g_Logger
0x180053a5b  jmp     loc_1800538A4
```
