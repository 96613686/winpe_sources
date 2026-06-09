# AslLogCreate

- ea: `0x180017794`
- end: `0x180017aee`
- name: `AslLogCreate`
- size: `858`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180017334`
- `0x180017658`
- `0x18001bfe8`
- `0x18002ac10`

## callees

- `0x180016814`
- `0x180017794`
- `0x180017af4`
- `0x18001860c`
- `0x1800188d0`
- `0x180039a72`
- `0x180039a96`
- `0x180039aae`
- `0x180039aba`
- `0x180039b24`
- `0x1800591b0`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x18001781d`
- `ntdll!RtlInitializeCriticalSection` at `0x18001781d`
- `ntdll!EtwEventRegister` at `0x180017876`
- `ntdll!EtwEventRegister` at `0x180017876`
- `ntdll!RtlAllocateHeap` at `0x1800177fc`
- `ntdll!RtlAllocateHeap` at `0x1800177fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800178d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017a19`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800178d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180017a19`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800179a4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017a47`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800179a4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180017a47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017a31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017a31`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017aa7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017acf`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017aa7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180017acf`

## string_xrefs

- `0x1800178c4`: `ntdll.dll`
- `0x180017a0b`: `ntdll.dll`
- `0x180017912`: `%s\Temp`
- `0x180017aa0`: `%OSDataDrive%\SystemData\Temp`
- `0x180017ac8`: `%TEMP%`

## pseudocode

```c
__int64 __fastcall AslLogCreate(_QWORD *a1, __int64 a2, unsigned int a3)
{
  unsigned __int64 v6; // rax
  char *Heap; // rax
  _DWORD *v8; // rbx
  PVOID ProcessHeap; // rcx
  wchar_t *v10; // rax
  WCHAR *v11; // rsi
  HMODULE Library; // rax
  HMODULE v13; // rbp
  unsigned __int8 (*RtlIsStateSeparationEnabled)(void); // rax
  __int64 v15; // rdi
  int v16; // edi
  __int64 v17; // r8
  unsigned int v19; // ecx
  HMODULE v20; // rax
  HMODULE v21; // r14
  __int64 (*ProcAddress)(void); // rax
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
  v8 = Heap;
  if ( !Heap )
    return (unsigned int)-1073741801;
  *((_QWORD *)Heap + 90) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(Heap + 104));
  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_OWORD *)v8 + 9) = 0;
  *((_OWORD *)v8 + 10) = 0;
  *((_OWORD *)v8 + 11) = 0;
  if ( !ProcessHeap )
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
  *((_QWORD *)v8 + 18) = ProcessHeap;
  *((_QWORD *)v8 + 21) = 4096;
  EtwEventRegister(AE_LOG, 0, 0, v8 + 178);
  GetModuleFileNameW_0(0, Filename, 0x104u);
  if ( GetLastError_0() )
  {
    v13 = 0;
    goto LABEL_23;
  }
  v10 = wcsrchr_0(Filename, 0x5Cu);
  if ( v10 )
    v11 = v10 + 1;
  else
    v11 = Filename;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  v13 = Library;
  if ( !Library
    || (RtlIsStateSeparationEnabled = (unsigned __int8 (*)(void))GetProcAddress_0(
                                                                   Library,
                                                                   "RtlIsStateSeparationEnabled")) == 0
    || !RtlIsStateSeparationEnabled() )
  {
    v15 = (__int64)String1;
    if ( !String1 )
    {
      v15 = 2147352624;
      v20 = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
      v21 = v20;
      if ( v20 )
      {
        ProcAddress = GetProcAddress(v20, "RtlGetNtSystemRoot");
        if ( ProcAddress )
          v15 = ProcAddress();
        FreeLibrary(v21);
      }
      String1 = (wchar_t *)v15;
    }
    v16 = RtlStringCchPrintfW(Dst, 0x104u, L"%s\\Temp", v15);
    if ( v16 < 0 )
      goto LABEL_24;
    goto LABEL_15;
  }
  if ( (!ExpandEnvironmentStringsW(L"%OSDataDrive%\\SystemData\\Temp", Dst, 0x104u) || Dst[0] == 37)
    && (!ExpandEnvironmentStringsW(L"%TEMP%", Dst, 0x104u) || Dst[0] == 37) )
  {
LABEL_23:
    v16 = -1073741823;
    goto LABEL_24;
  }
LABEL_15:
  CurrentProcessId_0 = GetCurrentProcessId_0();
  v16 = RtlStringCchPrintfW(
          (unsigned __int16 *)v8 + 96,
          0x104u,
          L"%s\\AslLog_%S_%s_%d.txt",
          Dst,
          a2,
          v11,
          CurrentProcessId_0);
  if ( v16 >= 0 )
  {
    *(_QWORD *)v8 = v8 + 2;
    *(_DWORD *)(*(_QWORD *)v8 + 80LL) = AslLogGetDefaultFlags();
    RtlStringCopyWorkerA(*(_QWORD *)v8, 64, v17, a2);
    if ( !a3 )
    {
      *(_DWORD *)(*(_QWORD *)v8 + 76LL) = 0;
LABEL_18:
      v16 = 0;
      *a1 = v8;
      goto LABEL_19;
    }
    v19 = v8[40];
    if ( a3 < v19 )
    {
      if ( !v19 )
        goto LABEL_18;
    }
    else
    {
      v19 = a3;
    }
    if ( v19 == (v19 & -v19) )
      *(_DWORD *)(*(_QWORD *)v8 + 76LL) = v19;
    goto LABEL_18;
  }
LABEL_24:
  AslLogDelete(v8);
LABEL_19:
  if ( v13 )
    FreeLibrary(v13);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180017794  mov     [rsp+arg_10], rbx
0x180017799  push    rbp
0x18001779a  push    rsi
0x18001779b  push    rdi
0x18001779c  push    r12
0x18001779e  push    r13
0x1800177a0  push    r14
0x1800177a2  push    r15
0x1800177a4  sub     rsp, 470h
0x1800177ab  mov     rax, cs:__security_cookie
0x1800177b2  xor     rax, rsp
0x1800177b5  mov     [rsp+4A8h+var_48], rax
0x1800177bd  mov     r15d, r8d
0x1800177c0  mov     qword ptr [rcx], 0
0x1800177c7  mov     r12, rdx
0x1800177ca  mov     r13, rcx
0x1800177cd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800177d1  inc     rax
0x1800177d4  cmp     byte ptr [rdx+rax], 0
0x1800177d8  jnz     short loc_1800177D1
0x1800177da  cmp     rax, 40h ; '@'
0x1800177de  jnb     loc_180017A6F
0x1800177e4  mov     rcx, gs:60h
0x1800177ed  mov     edx, 8; Flags
0x1800177f2  mov     r8d, 2D8h; Size
0x1800177f8  mov     rcx, [rcx+30h]; HeapHandle
0x1800177fc  call    cs:__imp_RtlAllocateHeap
0x180017802  mov     rbx, rax
0x180017805  test    rax, rax
0x180017808  jz      loc_180017A79
0x18001780e  lea     rcx, [rax+68h]; CriticalSection
0x180017812  mov     qword ptr [rax+2D0h], 0
0x18001781d  call    cs:__imp_RtlInitializeCriticalSection
0x180017823  mov     rax, gs:60h
0x18001782c  xorps   xmm0, xmm0
0x18001782f  mov     rcx, [rax+30h]
0x180017833  movups  xmmword ptr [rbx+90h], xmm0
0x18001783a  movups  xmmword ptr [rbx+0A0h], xmm0
0x180017841  movups  xmmword ptr [rbx+0B0h], xmm0
0x180017848  test    rcx, rcx
0x18001784b  jz      loc_180017A83
0x180017851  mov     [rbx+90h], rcx
0x180017858  lea     r9, [rbx+2C8h]
0x18001785f  lea     rcx, AE_LOG
0x180017866  mov     qword ptr [rbx+0A8h], 1000h
0x180017871  xor     r8d, r8d
0x180017874  xor     edx, edx
0x180017876  call    cs:__imp_EtwEventRegister
0x18001787c  mov     r8d, 104h; nSize
0x180017882  lea     rdx, [rsp+4A8h+Filename]; lpFilename
0x18001788a  xor     ecx, ecx; hModule
0x18001788c  call    GetModuleFileNameW_0
0x180017891  call    GetLastError_0
0x180017896  test    eax, eax
0x180017898  jnz     loc_1800179D7
0x18001789e  lea     edx, [rax+5Ch]; Ch
0x1800178a1  lea     rcx, [rsp+4A8h+Filename]; Str
0x1800178a9  call    wcsrchr_0
0x1800178ae  mov     rsi, rax
0x1800178b1  test    rax, rax
0x1800178b4  jz      loc_180017A59
0x1800178ba  add     rsi, 2
0x1800178be  mov     r14d, 800h
0x1800178c4  lea     rcx, LibFileName; "ntdll.dll"
0x1800178cb  mov     r8d, r14d; dwFlags
0x1800178ce  xor     edx, edx; hFile
0x1800178d0  call    cs:__imp_LoadLibraryExW
0x1800178d6  mov     rbp, rax
0x1800178d9  test    rax, rax
0x1800178dc  jz      short loc_1800178FF
0x1800178de  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x1800178e5  mov     rcx, rax; hModule
0x1800178e8  call    GetProcAddress_0
0x1800178ed  test    rax, rax
0x1800178f0  jz      short loc_1800178FF
0x1800178f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178f7  test    al, al
0x1800178f9  jnz     loc_180017A95
0x1800178ff  mov     rdi, cs:String1
0x180017906  test    rdi, rdi
0x180017909  jz      loc_180017A08
0x18001790f  mov     r9, rdi
0x180017912  lea     r8, aSTemp; "%s\\Temp"
0x180017919  mov     edx, 104h; unsigned __int64
0x18001791e  lea     rcx, [rsp+4A8h+Dst]; unsigned __int16 *
0x180017923  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017928  mov     edi, eax
0x18001792a  test    eax, eax
0x18001792c  js      loc_1800179DE
0x180017932  call    GetCurrentProcessId_0
0x180017937  mov     [rsp+4A8h+var_478], eax
0x18001793b  lea     rcx, [rbx+0C0h]; unsigned __int16 *
0x180017942  mov     [rsp+4A8h+var_480], rsi
0x180017947  lea     r9, [rsp+4A8h+Dst]
0x18001794c  lea     r8, aSAsllogSSDTxt; "%s\\AslLog_%S_%s_%d.txt"
0x180017953  mov     [rsp+4A8h+var_488], r12
0x180017958  mov     edx, 104h; unsigned __int64
0x18001795d  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017962  mov     edi, eax
0x180017964  test    eax, eax
0x180017966  js      short loc_1800179DE
0x180017968  lea     rax, [rbx+8]
0x18001796c  mov     [rbx], rax
0x18001796f  call    AslLogGetDefaultFlags
0x180017974  mov     rcx, [rbx]
0x180017977  mov     r9, r12
0x18001797a  mov     edx, 40h ; '@'
0x18001797f  mov     [rcx+50h], eax
0x180017982  mov     rcx, [rbx]
0x180017985  call    RtlStringCopyWorkerA
0x18001798a  test    r15d, r15d
0x18001798d  jnz     short loc_1800179E8
0x18001798f  mov     rax, [rbx]
0x180017992  mov     [rax+4Ch], r15d
0x180017996  xor     edi, edi
0x180017998  mov     [r13+0], rbx
0x18001799c  test    rbp, rbp
0x18001799f  jz      short loc_1800179AA
0x1800179a1  mov     rcx, rbp; hLibModule
0x1800179a4  call    cs:__imp_FreeLibrary
0x1800179aa  mov     eax, edi
0x1800179ac  mov     rcx, [rsp+4A8h+var_48]
0x1800179b4  xor     rcx, rsp; StackCookie
0x1800179b7  call    __security_check_cookie
0x1800179bc  mov     rbx, [rsp+4A8h+arg_10]
0x1800179c4  add     rsp, 470h
0x1800179cb  pop     r15
0x1800179cd  pop     r14
0x1800179cf  pop     r13
0x1800179d1  pop     r12
0x1800179d3  pop     rdi
0x1800179d4  pop     rsi
0x1800179d5  pop     rbp
0x1800179d6  retn
0x1800179d7  xor     ebp, ebp
0x1800179d9  mov     edi, 0C0000001h
0x1800179de  mov     rcx, rbx
0x1800179e1  call    AslLogDelete
0x1800179e6  jmp     short loc_18001799C
0x1800179e8  mov     ecx, [rbx+0A0h]
0x1800179ee  cmp     r15d, ecx
0x1800179f1  jb      short loc_180017A66
0x1800179f3  mov     ecx, r15d
0x1800179f6  mov     eax, ecx
0x1800179f8  neg     eax
0x1800179fa  and     eax, ecx
0x1800179fc  cmp     ecx, eax
0x1800179fe  jnz     short loc_180017996
0x180017a00  mov     rax, [rbx]
0x180017a03  mov     [rax+4Ch], ecx
0x180017a06  jmp     short loc_180017996
0x180017a08  mov     r8d, r14d; dwFlags
0x180017a0b  lea     rcx, LibFileName; "ntdll.dll"
0x180017a12  xor     edx, edx; hFile
0x180017a14  mov     edi, 7FFE0030h
0x180017a19  call    cs:__imp_LoadLibraryExW
0x180017a1f  mov     r14, rax
0x180017a22  test    rax, rax
0x180017a25  jz      short loc_180017A4D
0x180017a27  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180017a2e  mov     rcx, rax; hModule
0x180017a31  call    cs:__imp_GetProcAddress
0x180017a37  test    rax, rax
0x180017a3a  jz      short loc_180017A44
0x180017a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a41  mov     rdi, rax
0x180017a44  mov     rcx, r14; hLibModule
0x180017a47  call    cs:__imp_FreeLibrary
0x180017a4d  mov     cs:String1, rdi
0x180017a54  jmp     loc_18001790F
0x180017a59  lea     rsi, [rsp+4A8h+Filename]
0x180017a61  jmp     loc_1800178BE
0x180017a66  test    ecx, ecx
0x180017a68  jnz     short loc_1800179F6
0x180017a6a  jmp     loc_180017996
0x180017a6f  mov     edi, 0C000000Dh
0x180017a74  jmp     loc_1800179AA
0x180017a79  mov     edi, 0C0000017h
0x180017a7e  jmp     loc_1800179AA
0x180017a83  mov     rax, gs:60h
0x180017a8c  mov     rcx, [rax+30h]
0x180017a90  jmp     loc_180017851
0x180017a95  mov     r8d, 104h; nSize
0x180017a9b  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x180017aa0  lea     rcx, aOsdatadriveSys; "%OSDataDrive%\\SystemData\\Temp"
0x180017aa7  call    cs:__imp_ExpandEnvironmentStringsW
0x180017aad  test    eax, eax
0x180017aaf  jz      short loc_180017ABD
0x180017ab1  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x180017ab7  jnz     loc_180017932
0x180017abd  mov     r8d, 104h; nSize
0x180017ac3  lea     rdx, [rsp+4A8h+Dst]; lpDst
0x180017ac8  lea     rcx, aTemp; "%TEMP%"
0x180017acf  call    cs:__imp_ExpandEnvironmentStringsW
0x180017ad5  test    eax, eax
0x180017ad7  jz      loc_1800179D9
0x180017add  cmp     [rsp+4A8h+Dst], 25h ; '%'
0x180017ae3  jnz     loc_180017932
0x180017ae9  jmp     loc_1800179D9
```
