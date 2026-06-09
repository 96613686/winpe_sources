# EnableStdIO(void)

- ea: `0x180082660`
- end: `0x180082899`
- name: `?EnableStdIO@@YAXXZ`
- size: `569`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006750`
- `0x180010b40`

## callees

- `0x180015230`
- `0x18001a210`
- `0x180024ea8`
- `0x180082660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800826a5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180082702`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180082797`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180082831`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800826a5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180082702`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180082797`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x180082831`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008269a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800826f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008278c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180082826`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008269a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800826f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008278c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180082826`
- `api-ms-win-core-console-l1-1-0!AllocConsole` at `0x180082679`
- `api-ms-win-core-console-l1-1-0!AllocConsole` at `0x180082679`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x180082892`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1800826b0`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180082745`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1800827df`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1800826b0`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x180082745`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x1800827df`
- `msvcrt!_open_osfhandle` at `0x1800826be`
- `msvcrt!_open_osfhandle` at `0x180082753`
- `msvcrt!_open_osfhandle` at `0x1800827ed`
- `msvcrt!_open_osfhandle` at `0x1800826be`
- `msvcrt!_open_osfhandle` at `0x180082753`
- `msvcrt!_open_osfhandle` at `0x1800827ed`
- `msvcrt!setvbuf` at `0x18008273a`
- `msvcrt!setvbuf` at `0x1800827d4`
- `msvcrt!setvbuf` at `0x180082869`
- `msvcrt!setvbuf` at `0x18008273a`
- `msvcrt!setvbuf` at `0x1800827d4`
- `msvcrt!setvbuf` at `0x180082869`
- `msvcrt!_fdopen` at `0x1800826cd`
- `msvcrt!_fdopen` at `0x180082762`
- `msvcrt!_fdopen` at `0x1800827fc`
- `msvcrt!_fdopen` at `0x1800826cd`
- `msvcrt!_fdopen` at `0x180082762`
- `msvcrt!_fdopen` at `0x1800827fc`

## string_xrefs

- `0x1800826e1`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180082776`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x180082810`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x1800826e8`: `_fdopen failed`
- `0x18008277d`: `_fdopen failed`
- `0x180082817`: `_fdopen failed`

## pseudocode

```c
void EnableStdIO(void)
{
  HANDLE CurrentProcess; // rax
  signed int StdHandle; // eax
  int v2; // eax
  FILE *v3; // rbx
  HANDLE v4; // rax
  __int128 v5; // xmm6
  __int128 v6; // xmm7
  __int128 v7; // xmm8
  FILE *v8; // rax
  FILE *v9; // rax
  signed int v10; // eax
  int v11; // eax
  FILE *v12; // rbx
  HANDLE v13; // rax
  __int128 v14; // xmm6
  __int128 v15; // xmm7
  __int128 v16; // xmm8
  FILE *v17; // rax
  FILE *v18; // rax
  signed int v19; // eax
  int v20; // eax
  FILE *v21; // rbx
  HANDLE v22; // rax
  __int128 v23; // xmm6
  __int128 v24; // xmm7
  __int128 v25; // xmm8
  FILE *v26; // rax
  FILE *v27; // rax
  char *v28; // [rsp+20h] [rbp-48h]

  if ( !AllocConsole() )
  {
    locprint(1u, 0xC0001108, 0, 0, v28);
    CurrentProcess = GetCurrentProcess();
    TerminateProcess(CurrentProcess, 1u);
  }
  StdHandle = (unsigned int)GetStdHandle(0xFFFFFFF5);
  v2 = _open_osfhandle(StdHandle, 0x4000);
  v3 = _fdopen(v2, "w");
  if ( !v3 )
  {
    TraceFile(14, "_fdopen failed", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0x557u);
    v4 = GetCurrentProcess();
    TerminateProcess(v4, 1u);
  }
  v5 = *(_OWORD *)&v3->_ptr;
  v6 = *(_OWORD *)&v3->_base;
  v7 = *(_OWORD *)&v3->_charbuf;
  v8 = _acrt_iob_func(1u);
  *(_OWORD *)&v8->_ptr = v5;
  *(_OWORD *)&v8->_base = v6;
  *(_OWORD *)&v8->_charbuf = v7;
  v9 = _acrt_iob_func(1u);
  setvbuf(v9, 0, 4, 0);
  v10 = (unsigned int)GetStdHandle(0xFFFFFFF4);
  v11 = _open_osfhandle(v10, 0x4000);
  v12 = _fdopen(v11, "w");
  if ( !v12 )
  {
    TraceFile(14, "_fdopen failed", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0x567u);
    v13 = GetCurrentProcess();
    TerminateProcess(v13, 1u);
  }
  v14 = *(_OWORD *)&v12->_ptr;
  v15 = *(_OWORD *)&v12->_base;
  v16 = *(_OWORD *)&v12->_charbuf;
  v17 = _acrt_iob_func(2u);
  *(_OWORD *)&v17->_ptr = v14;
  *(_OWORD *)&v17->_base = v15;
  *(_OWORD *)&v17->_charbuf = v16;
  v18 = _acrt_iob_func(2u);
  setvbuf(v18, 0, 4, 0);
  v19 = (unsigned int)GetStdHandle(0xFFFFFFF6);
  v20 = _open_osfhandle(v19, 0x4000);
  v21 = _fdopen(v20, "r");
  if ( !v21 )
  {
    TraceFile(14, "_fdopen failed", "com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp", 0x577u);
    v22 = GetCurrentProcess();
    TerminateProcess(v22, 1u);
  }
  v23 = *(_OWORD *)&v21->_ptr;
  v24 = *(_OWORD *)&v21->_base;
  v25 = *(_OWORD *)&v21->_charbuf;
  v26 = _acrt_iob_func(0);
  *(_OWORD *)&v26->_ptr = v23;
  *(_OWORD *)&v26->_base = v24;
  *(_OWORD *)&v26->_charbuf = v25;
  v27 = _acrt_iob_func(0);
  setvbuf(v27, 0, 4, 0);
  SetConsoleCtrlHandler((PHANDLER_ROUTINE)DtcConsoleHandlerRoutine, 1);
}

```

## disassembly

```asm
0x180082660  mov     rax, rsp
0x180082663  mov     [rax+8], rbx
0x180082667  push    rdi
0x180082668  sub     rsp, 60h
0x18008266c  movaps  xmmword ptr [rax-18h], xmm6
0x180082670  movaps  xmmword ptr [rax-28h], xmm7
0x180082674  movaps  xmmword ptr [rax-38h], xmm8
0x180082679  call    cs:__imp_AllocConsole
0x18008267f  mov     edi, 1
0x180082684  test    eax, eax
0x180082686  jnz     short loc_1800826AB
0x180082688  xor     r9d, r9d; void *
0x18008268b  xor     r8d, r8d; unsigned int
0x18008268e  mov     edx, 0C0001108h; unsigned int
0x180082693  mov     ecx, edi; unsigned int
0x180082695  call    ?locprint@@YAXKKKPEAXPEAD@Z; locprint(ulong,ulong,ulong,void *,char *)
0x18008269a  call    cs:__imp_GetCurrentProcess
0x1800826a0  mov     rcx, rax; hProcess
0x1800826a3  mov     edx, edi; uExitCode
0x1800826a5  call    cs:__imp_TerminateProcess
0x1800826ab  mov     ecx, 0FFFFFFF5h; nStdHandle
0x1800826b0  call    cs:__imp_GetStdHandle
0x1800826b6  movsxd  rcx, eax; OSFileHandle
0x1800826b9  mov     edx, 4000h; Flags
0x1800826be  call    cs:__imp__open_osfhandle
0x1800826c4  mov     ecx, eax; FileHandle
0x1800826c6  lea     rdx, aW; "w"
0x1800826cd  call    cs:__imp__fdopen
0x1800826d3  mov     rbx, rax
0x1800826d6  test    rax, rax
0x1800826d9  jnz     short loc_180082708
0x1800826db  mov     r9d, 557h; unsigned int
0x1800826e1  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x1800826e8  lea     rdx, aFdopenFailed; "_fdopen failed"
0x1800826ef  lea     ecx, [rax+0Eh]; int
0x1800826f2  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800826f7  call    cs:__imp_GetCurrentProcess
0x1800826fd  mov     rcx, rax; hProcess
0x180082700  mov     edx, edi; uExitCode
0x180082702  call    cs:__imp_TerminateProcess
0x180082708  movups  xmm6, xmmword ptr [rbx]
0x18008270b  mov     ecx, edi; Ix
0x18008270d  movups  xmm7, xmmword ptr [rbx+10h]
0x180082711  movups  xmm8, xmmword ptr [rbx+20h]
0x180082716  call    __acrt_iob_func
0x18008271b  mov     ecx, edi; Ix
0x18008271d  movups  xmmword ptr [rax], xmm6
0x180082720  movups  xmmword ptr [rax+10h], xmm7
0x180082724  movups  xmmword ptr [rax+20h], xmm8
0x180082729  call    __acrt_iob_func
0x18008272e  xor     r9d, r9d; Size
0x180082731  mov     rcx, rax; Stream
0x180082734  xor     edx, edx; Buffer
0x180082736  lea     r8d, [r9+4]; Mode
0x18008273a  call    cs:__imp_setvbuf
0x180082740  mov     ecx, 0FFFFFFF4h; nStdHandle
0x180082745  call    cs:__imp_GetStdHandle
0x18008274b  movsxd  rcx, eax; OSFileHandle
0x18008274e  mov     edx, 4000h; Flags
0x180082753  call    cs:__imp__open_osfhandle
0x180082759  mov     ecx, eax; FileHandle
0x18008275b  lea     rdx, aW; "w"
0x180082762  call    cs:__imp__fdopen
0x180082768  mov     rbx, rax
0x18008276b  test    rax, rax
0x18008276e  jnz     short loc_18008279D
0x180082770  mov     r9d, 567h; unsigned int
0x180082776  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18008277d  lea     rdx, aFdopenFailed; "_fdopen failed"
0x180082784  lea     ecx, [rax+0Eh]; int
0x180082787  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18008278c  call    cs:__imp_GetCurrentProcess
0x180082792  mov     rcx, rax; hProcess
0x180082795  mov     edx, edi; uExitCode
0x180082797  call    cs:__imp_TerminateProcess
0x18008279d  movups  xmm6, xmmword ptr [rbx]
0x1800827a0  movups  xmm7, xmmword ptr [rbx+10h]
0x1800827a4  movups  xmm8, xmmword ptr [rbx+20h]
0x1800827a9  mov     ebx, 2
0x1800827ae  mov     ecx, ebx; Ix
0x1800827b0  call    __acrt_iob_func
0x1800827b5  mov     ecx, ebx; Ix
0x1800827b7  movups  xmmword ptr [rax], xmm6
0x1800827ba  movups  xmmword ptr [rax+10h], xmm7
0x1800827be  movups  xmmword ptr [rax+20h], xmm8
0x1800827c3  call    __acrt_iob_func
0x1800827c8  mov     rcx, rax; Stream
0x1800827cb  lea     r8d, [rbx+2]; Mode
0x1800827cf  xor     r9d, r9d; Size
0x1800827d2  xor     edx, edx; Buffer
0x1800827d4  call    cs:__imp_setvbuf
0x1800827da  mov     ecx, 0FFFFFFF6h; nStdHandle
0x1800827df  call    cs:__imp_GetStdHandle
0x1800827e5  movsxd  rcx, eax; OSFileHandle
0x1800827e8  mov     edx, 4000h; Flags
0x1800827ed  call    cs:__imp__open_osfhandle
0x1800827f3  mov     ecx, eax; FileHandle
0x1800827f5  lea     rdx, aR; "r"
0x1800827fc  call    cs:__imp__fdopen
0x180082802  mov     rbx, rax
0x180082805  test    rax, rax
0x180082808  jnz     short loc_180082837
0x18008280a  mov     r9d, 577h; unsigned int
0x180082810  lea     r8, aComComplusDtcD_7; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x180082817  lea     rdx, aFdopenFailed; "_fdopen failed"
0x18008281e  lea     ecx, [rax+0Eh]; int
0x180082821  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180082826  call    cs:__imp_GetCurrentProcess
0x18008282c  mov     rcx, rax; hProcess
0x18008282f  mov     edx, edi; uExitCode
0x180082831  call    cs:__imp_TerminateProcess
0x180082837  movups  xmm6, xmmword ptr [rbx]
0x18008283a  xor     ecx, ecx; Ix
0x18008283c  movups  xmm7, xmmword ptr [rbx+10h]
0x180082840  movups  xmm8, xmmword ptr [rbx+20h]
0x180082845  call    __acrt_iob_func
0x18008284a  xor     ecx, ecx; Ix
0x18008284c  movups  xmmword ptr [rax], xmm6
0x18008284f  movups  xmmword ptr [rax+10h], xmm7
0x180082853  movups  xmmword ptr [rax+20h], xmm8
0x180082858  call    __acrt_iob_func
0x18008285d  xor     r9d, r9d; Size
0x180082860  mov     rcx, rax; Stream
0x180082863  xor     edx, edx; Buffer
0x180082865  lea     r8d, [r9+4]; Mode
0x180082869  call    cs:__imp_setvbuf
0x18008286f  mov     edx, edi
0x180082871  lea     rcx, ?DtcConsoleHandlerRoutine@@YAHK@Z; DtcConsoleHandlerRoutine(ulong)
0x180082878  mov     rbx, [rsp+68h+arg_0]
0x18008287d  movaps  xmm6, [rsp+68h+var_18]
0x180082882  movaps  xmm7, [rsp+68h+var_28]
0x180082887  movaps  xmm8, [rsp+68h+var_38]
0x18008288d  add     rsp, 60h
0x180082891  pop     rdi
0x180082892  jmp     cs:__imp_SetConsoleCtrlHandler
```
