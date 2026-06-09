# CMidiXProc::Initialize(ulong *,std::unique_ptr<MEMORY_MAPPED_PIPE,std::default_delete<MEMORY_MAPPED_PIPE>> &,std::unique_ptr<MEMORY_MAPPED_PIPE,std::default_delete<MEMORY_MAPPED_PIPE>> &,IMidiCallback *,__int64,int)

- ea: `0x18000f144`
- end: `0x18000f42f`
- name: `?Initialize@CMidiXProc@@QEAAJPEAKAEAV?$unique_ptr@UMEMORY_MAPPED_PIPE@@U?$default_delete@UMEMORY_MAPPED_PIPE@@@std@@@std@@1PEAUIMidiCallback@@_JH@Z`
- size: `747`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParameter@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180012b04`

## callees

- `0x180002494`
- `0x18000568c`
- `0x180005c78`
- `0x180007e04`
- `0x180007e24`
- `0x180009014`
- `0x18000d3e4`
- `0x18000f144`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f3cf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000f3cf`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f22d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f284`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f22d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000f284`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f265`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f2bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f38f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f265`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f2bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f38f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f23b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f24a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f37c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f23b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f24a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f37c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000f362`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000f362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f2af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f255`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f2af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f387`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidiXProc::Initialize(
        LPVOID lpParameter,
        _DWORD *a2,
        _DWORD **a3,
        int **a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // rdx
  _DWORD *v12; // rax
  int v13; // edx
  __int64 v14; // rbx
  wil::details *v15; // rcx
  HANDLE Event; // rsi
  void *v17; // rbx
  DWORD LastError; // ebp
  unsigned int v19; // r8d
  const char *v20; // r9
  wil::details *v21; // rcx
  HANDLE v22; // rsi
  void *v23; // rbx
  DWORD v24; // ebp
  unsigned int v25; // r8d
  const char *v26; // r9
  _DWORD *v27; // rax
  MEMORY_MAPPED_PIPE *v28; // rbx
  int *v29; // rax
  MEMORY_MAPPED_PIPE *v30; // rbx
  HANDLE Thread; // rsi
  const char *v32; // r9
  char *v33; // rbp
  DWORD v34; // ebx
  __int64 v35; // rdx
  DWORD v36; // eax
  unsigned int v37; // r8d
  DWORD dwCreationFlags; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a2 )
  {
    v10 = 504;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
      (const char *)0x80070057LL,
      dwCreationFlags);
    return 2147942487LL;
  }
  v12 = *a3;
  if ( *a3 )
  {
    if ( !a5 )
    {
      v10 = 506;
      goto LABEL_3;
    }
    if ( (unsigned int)(*v12 - 1) > 1 && *v12 != -1 )
    {
      v10 = 513;
      goto LABEL_3;
    }
  }
  else if ( !*a4 )
  {
    v10 = 505;
    goto LABEL_3;
  }
  if ( *a4 )
  {
    v13 = **a4;
    if ( (unsigned int)(v13 - 1) > 1 && v13 != -1 )
    {
      v10 = 520;
      goto LABEL_3;
    }
  }
  v14 = *((_QWORD *)lpParameter + 11);
  *((_QWORD *)lpParameter + 11) = a5;
  if ( a5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  *((_QWORD *)lpParameter + 12) = a6;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Event )
  {
    GetLastError();
    v17 = (void *)*((_QWORD *)lpParameter + 15);
    if ( v17 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v17) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v19, v20);
      SetLastError(LastError);
    }
    *((_QWORD *)lpParameter + 15) = Event;
  }
  else
  {
    wil::details::GetLastErrorFailHr(v15);
  }
  v22 = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( v22 )
  {
    GetLastError();
    v23 = (void *)*((_QWORD *)lpParameter + 16);
    if ( v23 )
    {
      v24 = GetLastError();
      if ( !CloseHandle(v23) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v25, v26);
      SetLastError(v24);
    }
    *((_QWORD *)lpParameter + 16) = v22;
  }
  else
  {
    wil::details::GetLastErrorFailHr(v21);
  }
  *((_DWORD *)lpParameter + 20) = *a2;
  v27 = *a3;
  *a3 = 0;
  v28 = (MEMORY_MAPPED_PIPE *)*((_QWORD *)lpParameter + 13);
  *((_QWORD *)lpParameter + 13) = v27;
  if ( v28 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v28);
    operator delete(v28);
  }
  v29 = *a4;
  *a4 = 0;
  v30 = (MEMORY_MAPPED_PIPE *)*((_QWORD *)lpParameter + 14);
  *((_QWORD *)lpParameter + 14) = v29;
  if ( v30 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v30);
    operator delete(v30);
  }
  *(_DWORD *)lpParameter = 0;
  if ( *((_QWORD *)lpParameter + 13) )
  {
    Thread = CreateThread(0, 0, CMidiXProc::MidiInWorker, lpParameter, 0, 0);
    v33 = (char *)*((_QWORD *)lpParameter + 17);
    if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v34 = GetLastError();
      CloseHandle(v33);
      SetLastError(v34);
    }
    *((_QWORD *)lpParameter + 17) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v35 = 546;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v35,
               (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
               v32);
    }
    v36 = WaitForSingleObjectEx(*((HANDLE *)lpParameter + 16), 0x3E8u, 0);
    if ( v36 == 258 )
    {
      v35 = 548;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v35,
               (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
               v32);
    }
    if ( v36 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v37, v32);
  }
  *a2 = *((_DWORD *)lpParameter + 20);
  return 0;
}

```

## disassembly

```asm
0x18000f144  push    rbx
0x18000f146  push    rbp
0x18000f147  push    rsi
0x18000f148  push    rdi
0x18000f149  push    r12
0x18000f14b  push    r14
0x18000f14d  push    r15
0x18000f14f  sub     rsp, 30h
0x18000f153  mov     r14, r9
0x18000f156  mov     r15, r8
0x18000f159  mov     r12, rdx
0x18000f15c  mov     rdi, rcx
0x18000f15f  test    rdx, rdx
0x18000f162  jnz     short loc_18000F189
0x18000f164  mov     edx, 1F8h; void *
0x18000f169  mov     ebx, 80070057h
0x18000f16e  mov     rcx, [rsp+68h]; this
0x18000f173  mov     r9d, ebx; char *
0x18000f176  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18000f17d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f182  mov     eax, ebx
0x18000f184  jmp     loc_18000F3E9
0x18000f189  mov     rax, [r8]
0x18000f18c  mov     rcx, [rsp+68h+arg_20]
0x18000f194  test    rax, rax
0x18000f197  jnz     short loc_18000F1A5
0x18000f199  cmp     [r9], rax
0x18000f19c  jnz     short loc_18000F1C7
0x18000f19e  mov     edx, 1F9h
0x18000f1a3  jmp     short loc_18000F169
0x18000f1a5  test    rcx, rcx
0x18000f1a8  jnz     short loc_18000F1B1
0x18000f1aa  mov     edx, 1FAh
0x18000f1af  jmp     short loc_18000F169
0x18000f1b1  mov     edx, [rax]
0x18000f1b3  lea     eax, [rdx-1]
0x18000f1b6  cmp     eax, 1
0x18000f1b9  jbe     short loc_18000F1C7
0x18000f1bb  cmp     edx, 0FFFFFFFFh
0x18000f1be  jz      short loc_18000F1C7
0x18000f1c0  mov     edx, 201h
0x18000f1c5  jmp     short loc_18000F169
0x18000f1c7  mov     rax, [r9]
0x18000f1ca  test    rax, rax
0x18000f1cd  jz      short loc_18000F1E5
0x18000f1cf  mov     edx, [rax]
0x18000f1d1  lea     eax, [rdx-1]
0x18000f1d4  cmp     eax, 1
0x18000f1d7  jbe     short loc_18000F1E5
0x18000f1d9  cmp     edx, 0FFFFFFFFh
0x18000f1dc  jz      short loc_18000F1E5
0x18000f1de  mov     edx, 208h
0x18000f1e3  jmp     short loc_18000F169
0x18000f1e5  mov     rbx, [rdi+58h]
0x18000f1e9  mov     [rdi+58h], rcx
0x18000f1ed  test    rcx, rcx
0x18000f1f0  jz      short loc_18000F1FE
0x18000f1f2  mov     rax, [rcx]
0x18000f1f5  mov     rax, [rax+8]
0x18000f1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1fe  test    rbx, rbx
0x18000f201  jz      short loc_18000F213
0x18000f203  mov     rax, [rbx]
0x18000f206  mov     rcx, rbx
0x18000f209  mov     rax, [rax+10h]
0x18000f20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f212  nop
0x18000f213  mov     rax, [rsp+68h+arg_28]
0x18000f21b  mov     [rdi+60h], rax
0x18000f21f  xor     edx, edx; lpName
0x18000f221  xor     ecx, ecx; lpEventAttributes
0x18000f223  mov     r9d, 1F0003h; dwDesiredAccess
0x18000f229  lea     r8d, [rdx+1]; dwFlags
0x18000f22d  call    cs:__imp_CreateEventExW
0x18000f233  mov     rsi, rax
0x18000f236  test    rax, rax
0x18000f239  jz      short loc_18000F271
0x18000f23b  call    cs:__imp_GetLastError
0x18000f241  mov     rbx, [rdi+78h]
0x18000f245  test    rbx, rbx
0x18000f248  jz      short loc_18000F26B
0x18000f24a  call    cs:__imp_GetLastError
0x18000f250  mov     ebp, eax
0x18000f252  mov     rcx, rbx; hObject
0x18000f255  call    cs:__imp_CloseHandle
0x18000f25b  test    eax, eax
0x18000f25d  jz      loc_18000F40F
0x18000f263  mov     ecx, ebp; dwErrCode
0x18000f265  call    cs:__imp_SetLastError
0x18000f26b  mov     [rdi+78h], rsi
0x18000f26f  jmp     short loc_18000F276
0x18000f271  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f276  xor     edx, edx; lpName
0x18000f278  xor     ecx, ecx; lpEventAttributes
0x18000f27a  mov     r9d, 1F0003h; dwDesiredAccess
0x18000f280  lea     r8d, [rdx+1]; dwFlags
0x18000f284  call    cs:__imp_CreateEventExW
0x18000f28a  mov     rsi, rax
0x18000f28d  test    rax, rax
0x18000f290  jz      short loc_18000F2CE
0x18000f292  call    cs:__imp_GetLastError
0x18000f298  mov     rbx, [rdi+80h]
0x18000f29f  test    rbx, rbx
0x18000f2a2  jz      short loc_18000F2C5
0x18000f2a4  call    cs:__imp_GetLastError
0x18000f2aa  mov     ebp, eax
0x18000f2ac  mov     rcx, rbx; hObject
0x18000f2af  call    cs:__imp_CloseHandle
0x18000f2b5  test    eax, eax
0x18000f2b7  jz      loc_18000F41F
0x18000f2bd  mov     ecx, ebp; dwErrCode
0x18000f2bf  call    cs:__imp_SetLastError
0x18000f2c5  mov     [rdi+80h], rsi
0x18000f2cc  jmp     short loc_18000F2D3
0x18000f2ce  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000f2d3  mov     eax, [r12]
0x18000f2d7  mov     [rdi+50h], eax
0x18000f2da  mov     rax, [r15]
0x18000f2dd  mov     qword ptr [r15], 0
0x18000f2e4  mov     rbx, [rdi+68h]
0x18000f2e8  mov     [rdi+68h], rax
0x18000f2ec  mov     esi, 68h ; 'h'
0x18000f2f1  test    rbx, rbx
0x18000f2f4  jz      short loc_18000F308
0x18000f2f6  mov     rcx, rbx; this
0x18000f2f9  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18000f2fe  mov     edx, esi
0x18000f300  mov     rcx, rbx; Block
0x18000f303  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f308  mov     rax, [r14]
0x18000f30b  mov     qword ptr [r14], 0
0x18000f312  mov     rbx, [rdi+70h]
0x18000f316  mov     [rdi+70h], rax
0x18000f31a  test    rbx, rbx
0x18000f31d  jz      short loc_18000F332
0x18000f31f  mov     rcx, rbx; this
0x18000f322  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18000f327  mov     rdx, rsi
0x18000f32a  mov     rcx, rbx; Block
0x18000f32d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f332  mov     dword ptr [rdi], 0
0x18000f338  cmp     qword ptr [rdi+68h], 0
0x18000f33d  jz      loc_18000F3E0
0x18000f343  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18000f34c  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18000f354  mov     r9, rdi; lpParameter
0x18000f357  lea     r8, ?MidiInWorker@CMidiXProc@@CAKPEAX@Z; lpStartAddress
0x18000f35e  xor     edx, edx; dwStackSize
0x18000f360  xor     ecx, ecx; lpThreadAttributes
0x18000f362  call    cs:__imp_CreateThread
0x18000f368  mov     rsi, rax
0x18000f36b  mov     rbp, [rdi+88h]
0x18000f372  lea     rdx, [rbp-1]
0x18000f376  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000f37a  ja      short loc_18000F395
0x18000f37c  call    cs:__imp_GetLastError
0x18000f382  mov     ebx, eax
0x18000f384  mov     rcx, rbp; hObject
0x18000f387  call    cs:__imp_CloseHandle
0x18000f38d  mov     ecx, ebx; dwErrCode
0x18000f38f  call    cs:__imp_SetLastError
0x18000f395  mov     [rdi+88h], rsi
0x18000f39c  lea     rax, [rsi+1]
0x18000f3a0  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000f3a6  jnz     short loc_18000F3C0
0x18000f3a8  mov     edx, 222h; void *
0x18000f3ad  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18000f3b4  mov     rcx, [rsp+68h]; this
0x18000f3b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f3be  jmp     short loc_18000F3E9
0x18000f3c0  xor     r8d, r8d; bAlertable
0x18000f3c3  mov     edx, 3E8h; dwMilliseconds
0x18000f3c8  mov     rcx, [rdi+80h]; hHandle
0x18000f3cf  call    cs:__imp_WaitForSingleObjectEx
0x18000f3d5  cmp     eax, 102h
0x18000f3da  jz      short loc_18000F3F8
0x18000f3dc  test    eax, eax
0x18000f3de  jnz     short loc_18000F3FF
0x18000f3e0  mov     eax, [rdi+50h]
0x18000f3e3  mov     [r12], eax
0x18000f3e7  xor     eax, eax
0x18000f3e9  add     rsp, 30h
0x18000f3ed  pop     r15
0x18000f3ef  pop     r14
0x18000f3f1  pop     r12
0x18000f3f3  pop     rdi
0x18000f3f4  pop     rsi
0x18000f3f5  pop     rbp
0x18000f3f6  pop     rbx
0x18000f3f7  retn
0x18000f3f8  mov     edx, 224h
0x18000f3fd  jmp     short loc_18000F3AD
0x18000f3ff  mov     rcx, [rsp+68h]; this
0x18000f404  mov     edx, 0B0Fh; void *
0x18000f409  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18000f40f  mov     rcx, [rsp+68h]; this
0x18000f414  mov     edx, 0A0Bh; void *
0x18000f419  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000f41f  mov     rcx, [rsp+68h]; this
0x18000f424  mov     edx, 0A0Bh; void *
0x18000f429  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
