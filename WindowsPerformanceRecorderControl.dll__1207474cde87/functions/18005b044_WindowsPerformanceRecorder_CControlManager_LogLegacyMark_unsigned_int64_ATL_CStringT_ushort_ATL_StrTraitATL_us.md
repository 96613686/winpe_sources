# WindowsPerformanceRecorder::CControlManager::LogLegacyMark(unsigned __int64,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,short)

- ea: `0x18005b044`
- end: `0x18005b1ea`
- name: `?LogLegacyMark@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@F@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005a1f0`

## callees

- `0x18000829c`
- `0x18001e6e0`
- `0x18004a170`
- `0x18004b39c`
- `0x18004b494`
- `0x18004f964`
- `0x18005b044`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b0db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b13c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b1b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b1c2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b0db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b13c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b1b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005b1c2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005b0c3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005b0c3`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18005b14e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18005b14e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18005b163`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18005b163`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18005b128`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18005b128`

## string_xrefs

- `0x18005b08a`: `COMGUARD`
- `0x18005b182`: `COMGUARD`
- `0x18005b147`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::LogLegacyMark(
        __int64 a1,
        __int64 a2,
        LPCWCH *a3,
        __int16 a4)
{
  unsigned int v7; // edi
  int v8; // edi
  unsigned int v9; // ebp
  CHAR *v10; // rax
  CHAR *v11; // rbx
  unsigned int Error; // eax
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v15; // edi
  const char *cbMultiByte; // [rsp+28h] [rbp-80h]
  const char *cbMultiBytea; // [rsp+28h] [rbp-80h]
  _BYTE v19[8]; // [rsp+48h] [rbp-60h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-58h]

  WindowsPerformanceRecorder::Impl::CAutoPrivilege::CAutoPrivilege(
    (WindowsPerformanceRecorder::Impl::CAutoPrivilege *)v19,
    20,
    1u);
  v7 = v20;
  if ( v20 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "LogLegacyMark",
      (const char *)0x617,
      v20,
      "COMGUARD",
      cbMultiByte);
  }
  else
  {
    v8 = *((_DWORD *)*a3 - 4) + 1;
    v9 = *((_DWORD *)*a3 - 4) + 5;
    v10 = (CHAR *)malloc(v9);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, v9);
      if ( a4 )
        *(_DWORD *)v11 = 1;
      if ( WideCharToMultiByte(0, 0x400u, *a3, v8, v11 + 4, v8, 0, 0) )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        if ( !ModuleHandleW || (ProcAddress = GetProcAddress(ModuleHandleW, "EtwSetMark")) == 0 )
        {
          free(v11);
          v7 = 1;
          goto LABEL_16;
        }
        v15 = ((__int64 (__fastcall *)(__int64, CHAR *, _QWORD))ProcAddress)(a2, v11, v9);
        if ( !v15 )
        {
          free(v11);
          v7 = 0;
          goto LABEL_16;
        }
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          "LogLegacyMark",
          (const char *)0x64B,
          v15,
          "COMGUARD",
          cbMultiBytea);
        Error = ATL::AtlHresultFromWin32(v15);
      }
      else
      {
        Error = ATL::AtlHresultFromLastError();
      }
      v7 = Error;
      free(v11);
    }
    else
    {
      free(0);
      v7 = -2147024882;
    }
  }
LABEL_16:
  WindowsPerformanceRecorder::Impl::CAutoPrivilege::~CAutoPrivilege((WindowsPerformanceRecorder::Impl::CAutoPrivilege *)v19);
  return v7;
}

```

## disassembly

```asm
0x18005b044  mov     [rsp+arg_0], rcx
0x18005b049  push    rbx
0x18005b04a  push    rbp
0x18005b04b  push    rsi
0x18005b04c  push    rdi
0x18005b04d  push    r12
0x18005b04f  push    r13
0x18005b051  push    r14
0x18005b053  push    r15
0x18005b055  sub     rsp, 68h
0x18005b059  mov     [rsp+0A8h+var_68], 0FFFFFFFFFFFFFFFEh
0x18005b062  movzx   r15d, r9w
0x18005b066  mov     r14, r8
0x18005b069  mov     r12, rdx
0x18005b06c  mov     r8b, 1; unsigned __int8
0x18005b06f  mov     edx, 14h; unsigned int
0x18005b074  lea     rcx, [rsp+0A8h+var_60]; this
0x18005b079  call    ??0CAutoPrivilege@Impl@WindowsPerformanceRecorder@@QEAA@KE@Z; WindowsPerformanceRecorder::Impl::CAutoPrivilege::CAutoPrivilege(ulong,uchar)
0x18005b07e  nop
0x18005b07f  mov     edi, [rsp+0A8h+var_58]
0x18005b083  xor     r13d, r13d
0x18005b086  test    edi, edi
0x18005b088  jz      short loc_18005B0B4
0x18005b08a  lea     rax, aComguard; "COMGUARD"
0x18005b091  mov     [rsp+0A8h+lpMultiByteStr], rax; Format
0x18005b096  mov     r9d, edi; unsigned int
0x18005b099  mov     r8d, 617h; char *
0x18005b09f  lea     rdx, aLoglegacymark; "LogLegacyMark"
0x18005b0a6  lea     ecx, [r13+2]; this
0x18005b0aa  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005b0af  jmp     loc_18005B1CD
0x18005b0b4  mov     rax, [r14]
0x18005b0b7  mov     edi, [rax-10h]
0x18005b0ba  inc     edi
0x18005b0bc  lea     ebp, [rdi+4]
0x18005b0bf  mov     esi, ebp
0x18005b0c1  mov     ecx, ebp; Size
0x18005b0c3  call    cs:__imp_malloc
0x18005b0c9  mov     rbx, rax
0x18005b0cc  mov     [rsp+0A8h+arg_0], rax
0x18005b0d4  test    rax, rax
0x18005b0d7  jnz     short loc_18005B0EB
0x18005b0d9  xor     ecx, ecx; Block
0x18005b0db  call    cs:__imp_free
0x18005b0e1  mov     edi, 8007000Eh
0x18005b0e6  jmp     loc_18005B1CD
0x18005b0eb  mov     r8, rsi; Size
0x18005b0ee  xor     edx, edx; Val
0x18005b0f0  mov     rcx, rbx; void *
0x18005b0f3  call    memset_0
0x18005b0f8  test    r15w, r15w
0x18005b0fc  jz      short loc_18005B104
0x18005b0fe  mov     dword ptr [rbx], 1
0x18005b104  lea     rax, [rbx+4]
0x18005b108  mov     [rsp+0A8h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18005b10d  mov     [rsp+0A8h+lpDefaultChar], r13; lpDefaultChar
0x18005b112  mov     dword ptr [rsp+0A8h+cbMultiByte], edi; char *
0x18005b116  mov     [rsp+0A8h+lpMultiByteStr], rax; lpMultiByteStr
0x18005b11b  mov     r9d, edi; cchWideChar
0x18005b11e  mov     r8, [r14]; lpWideCharStr
0x18005b121  mov     edx, 400h; dwFlags
0x18005b126  xor     ecx, ecx; CodePage
0x18005b128  call    cs:__imp_WideCharToMultiByte
0x18005b12e  test    eax, eax
0x18005b130  jnz     short loc_18005B147
0x18005b132  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18005b137  mov     edi, eax
0x18005b139  mov     rcx, rbx; Block
0x18005b13c  call    cs:__imp_free
0x18005b142  jmp     loc_18005B1CD
0x18005b147  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18005b14e  call    cs:__imp_GetModuleHandleW
0x18005b154  test    rax, rax
0x18005b157  jz      short loc_18005B1BF
0x18005b159  lea     rdx, aEtwsetmark; "EtwSetMark"
0x18005b160  mov     rcx, rax; hModule
0x18005b163  call    cs:__imp_GetProcAddress
0x18005b169  test    rax, rax
0x18005b16c  jz      short loc_18005B1BF
0x18005b16e  mov     r8d, ebp
0x18005b171  mov     rdx, rbx
0x18005b174  mov     rcx, r12
0x18005b177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b17c  mov     edi, eax
0x18005b17e  test    eax, eax
0x18005b180  jz      short loc_18005B1B1
0x18005b182  lea     rax, aComguard; "COMGUARD"
0x18005b189  mov     [rsp+0A8h+lpMultiByteStr], rax; Format
0x18005b18e  mov     r9d, edi; unsigned int
0x18005b191  mov     r8d, 64Bh; char *
0x18005b197  lea     rdx, aLoglegacymark; "LogLegacyMark"
0x18005b19e  mov     ecx, 2; this
0x18005b1a3  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005b1a8  mov     ecx, edi; unsigned int
0x18005b1aa  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18005b1af  jmp     short loc_18005B137
0x18005b1b1  mov     rcx, rbx; Block
0x18005b1b4  call    cs:__imp_free
0x18005b1ba  mov     edi, r13d
0x18005b1bd  jmp     short loc_18005B1CD
0x18005b1bf  mov     rcx, rbx; Block
0x18005b1c2  call    cs:__imp_free
0x18005b1c8  mov     edi, 1
0x18005b1cd  lea     rcx, [rsp+0A8h+var_60]; this
0x18005b1d2  call    ??1CAutoPrivilege@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoPrivilege::~CAutoPrivilege(void)
0x18005b1d7  mov     eax, edi
0x18005b1d9  add     rsp, 68h
0x18005b1dd  pop     r15
0x18005b1df  pop     r14
0x18005b1e1  pop     r13
0x18005b1e3  pop     r12
0x18005b1e5  pop     rdi
0x18005b1e6  pop     rsi
0x18005b1e7  pop     rbp
0x18005b1e8  pop     rbx
0x18005b1e9  retn
```
