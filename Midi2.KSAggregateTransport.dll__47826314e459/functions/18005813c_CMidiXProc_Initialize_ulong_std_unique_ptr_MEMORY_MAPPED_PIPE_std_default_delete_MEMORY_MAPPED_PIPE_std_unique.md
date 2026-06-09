# CMidiXProc::Initialize(ulong *,std::unique_ptr<MEMORY_MAPPED_PIPE,std::default_delete<MEMORY_MAPPED_PIPE>> &,std::unique_ptr<MEMORY_MAPPED_PIPE,std::default_delete<MEMORY_MAPPED_PIPE>> &,IMidiCallback *,__int64,int)

- ea: `0x18005813c`
- end: `0x180058366`
- name: `?Initialize@CMidiXProc@@QEAAJPEAKAEAV?$unique_ptr@UMEMORY_MAPPED_PIPE@@U?$default_delete@UMEMORY_MAPPED_PIPE@@@std@@@std@@1PEAUIMidiCallback@@_JH@Z`
- size: `554`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParameter@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180049100`
- `0x1800494d4`
- `0x180049b78`

## callees

- `0x180005044`
- `0x180008950`
- `0x18000b374`
- `0x18000b394`
- `0x180042480`
- `0x180043a74`
- `0x18005813c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180058327`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180058327`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800582ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800582ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800582d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800582d7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800582bd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800582bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800582e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800582e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidiXProc::Initialize(char *lpParameter, _DWORD *a2, _DWORD **a3, int **a4, __int64 a5, __int64 a6)
{
  __int64 v10; // rdx
  _DWORD *v12; // rax
  int v13; // edx
  __int64 v14; // rbx
  _DWORD *v15; // rax
  MEMORY_MAPPED_PIPE *v16; // rbx
  int *v17; // rax
  MEMORY_MAPPED_PIPE *v18; // rbx
  HANDLE Thread; // rsi
  const char *v20; // r9
  char *v21; // rbp
  DWORD LastError; // ebx
  __int64 v23; // rdx
  DWORD v24; // eax
  unsigned int v25; // r8d
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
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(lpParameter + 120);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(lpParameter + 128);
  *((_DWORD *)lpParameter + 20) = *a2;
  v15 = *a3;
  *a3 = 0;
  v16 = (MEMORY_MAPPED_PIPE *)*((_QWORD *)lpParameter + 13);
  *((_QWORD *)lpParameter + 13) = v15;
  if ( v16 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v16);
    operator delete(v16);
  }
  v17 = *a4;
  *a4 = 0;
  v18 = (MEMORY_MAPPED_PIPE *)*((_QWORD *)lpParameter + 14);
  *((_QWORD *)lpParameter + 14) = v17;
  if ( v18 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v18);
    operator delete(v18);
  }
  *(_DWORD *)lpParameter = 1;
  if ( *((_QWORD *)lpParameter + 13) )
  {
    Thread = CreateThread(0, 0, CMidiXProc::MidiInWorker, lpParameter, 0, 0);
    v21 = (char *)*((_QWORD *)lpParameter + 17);
    if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v21);
      SetLastError(LastError);
    }
    *((_QWORD *)lpParameter + 17) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v23 = 546;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v23,
               (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
               v20);
    }
    v24 = WaitForSingleObjectEx(*((HANDLE *)lpParameter + 16), 0x3E8u, 0);
    if ( v24 == 258 )
    {
      v23 = 548;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v23,
               (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
               v20);
    }
    if ( v24 )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v25, v20);
  }
  *a2 = *((_DWORD *)lpParameter + 20);
  return 0;
}

```

## disassembly

```asm
0x18005813c  push    rbx
0x18005813e  push    rbp
0x18005813f  push    rsi
0x180058140  push    rdi
0x180058141  push    r12
0x180058143  push    r14
0x180058145  push    r15
0x180058147  sub     rsp, 30h
0x18005814b  mov     rsi, r9
0x18005814e  mov     r15, r8
0x180058151  mov     r14, rdx
0x180058154  mov     rdi, rcx
0x180058157  test    rdx, rdx
0x18005815a  jnz     short loc_180058181
0x18005815c  mov     edx, 1F8h; void *
0x180058161  mov     ebx, 80070057h
0x180058166  mov     rcx, [rsp+68h]; this
0x18005816b  mov     r9d, ebx; char *
0x18005816e  lea     r8, aAvcoreMidi2Lib_3; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x180058175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005817a  mov     eax, ebx
0x18005817c  jmp     loc_180058340
0x180058181  mov     rax, [r8]
0x180058184  mov     rcx, [rsp+68h+arg_20]
0x18005818c  test    rax, rax
0x18005818f  jnz     short loc_18005819D
0x180058191  cmp     [r9], rax
0x180058194  jnz     short loc_1800581BF
0x180058196  mov     edx, 1F9h
0x18005819b  jmp     short loc_180058161
0x18005819d  test    rcx, rcx
0x1800581a0  jnz     short loc_1800581A9
0x1800581a2  mov     edx, 1FAh
0x1800581a7  jmp     short loc_180058161
0x1800581a9  mov     edx, [rax]
0x1800581ab  lea     eax, [rdx-1]
0x1800581ae  cmp     eax, 1
0x1800581b1  jbe     short loc_1800581BF
0x1800581b3  cmp     edx, 0FFFFFFFFh
0x1800581b6  jz      short loc_1800581BF
0x1800581b8  mov     edx, 201h
0x1800581bd  jmp     short loc_180058161
0x1800581bf  mov     rax, [r9]
0x1800581c2  test    rax, rax
0x1800581c5  jz      short loc_1800581DD
0x1800581c7  mov     edx, [rax]
0x1800581c9  lea     eax, [rdx-1]
0x1800581cc  cmp     eax, 1
0x1800581cf  jbe     short loc_1800581DD
0x1800581d1  cmp     edx, 0FFFFFFFFh
0x1800581d4  jz      short loc_1800581DD
0x1800581d6  mov     edx, 208h
0x1800581db  jmp     short loc_180058161
0x1800581dd  mov     rbx, [rdi+58h]
0x1800581e1  mov     [rdi+58h], rcx
0x1800581e5  test    rcx, rcx
0x1800581e8  jz      short loc_1800581F6
0x1800581ea  mov     rax, [rcx]
0x1800581ed  mov     rax, [rax+8]
0x1800581f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800581f6  test    rbx, rbx
0x1800581f9  jz      short loc_18005820B
0x1800581fb  mov     rax, [rbx]
0x1800581fe  mov     rcx, rbx
0x180058201  mov     rax, [rax+10h]
0x180058205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005820a  nop
0x18005820b  mov     rax, [rsp+68h+arg_28]
0x180058213  mov     [rdi+60h], rax
0x180058217  lea     rcx, [rdi+78h]
0x18005821b  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180058220  lea     r12, [rdi+80h]
0x180058227  mov     rcx, r12
0x18005822a  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18005822f  mov     eax, [r14]
0x180058232  mov     [rdi+50h], eax
0x180058235  mov     rax, [r15]
0x180058238  mov     qword ptr [r15], 0
0x18005823f  mov     rbx, [rdi+68h]
0x180058243  mov     [rdi+68h], rax
0x180058247  mov     ebp, 68h ; 'h'
0x18005824c  test    rbx, rbx
0x18005824f  jz      short loc_180058263
0x180058251  mov     rcx, rbx; this
0x180058254  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180058259  mov     edx, ebp
0x18005825b  mov     rcx, rbx; Block
0x18005825e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180058263  mov     rax, [rsi]
0x180058266  mov     qword ptr [rsi], 0
0x18005826d  mov     rbx, [rdi+70h]
0x180058271  mov     [rdi+70h], rax
0x180058275  test    rbx, rbx
0x180058278  jz      short loc_18005828D
0x18005827a  mov     rcx, rbx; this
0x18005827d  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180058282  mov     rdx, rbp
0x180058285  mov     rcx, rbx; Block
0x180058288  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005828d  mov     dword ptr [rdi], 1
0x180058293  cmp     qword ptr [rdi+68h], 0
0x180058298  jz      loc_180058338
0x18005829e  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x1800582a7  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800582af  mov     r9, rdi; lpParameter
0x1800582b2  lea     r8, ?MidiInWorker@CMidiXProc@@CAKPEAX@Z; lpStartAddress
0x1800582b9  xor     edx, edx; dwStackSize
0x1800582bb  xor     ecx, ecx; lpThreadAttributes
0x1800582bd  call    cs:__imp_CreateThread
0x1800582c3  mov     rsi, rax
0x1800582c6  mov     rbp, [rdi+88h]
0x1800582cd  lea     rdx, [rbp-1]
0x1800582d1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800582d5  ja      short loc_1800582F0
0x1800582d7  call    cs:__imp_GetLastError
0x1800582dd  mov     ebx, eax
0x1800582df  mov     rcx, rbp; hObject
0x1800582e2  call    cs:__imp_CloseHandle
0x1800582e8  mov     ecx, ebx; dwErrCode
0x1800582ea  call    cs:__imp_SetLastError
0x1800582f0  mov     [rdi+88h], rsi
0x1800582f7  lea     rax, [rsi+1]
0x1800582fb  test    rax, 0FFFFFFFFFFFFFFFEh
0x180058301  jnz     short loc_18005831B
0x180058303  mov     edx, 222h; void *
0x180058308  lea     r8, aAvcoreMidi2Lib_3; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18005830f  mov     rcx, [rsp+68h]; this
0x180058314  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058319  jmp     short loc_180058340
0x18005831b  xor     r8d, r8d; bAlertable
0x18005831e  mov     edx, 3E8h; dwMilliseconds
0x180058323  mov     rcx, [r12]; hHandle
0x180058327  call    cs:__imp_WaitForSingleObjectEx
0x18005832d  cmp     eax, 102h
0x180058332  jz      short loc_18005834F
0x180058334  test    eax, eax
0x180058336  jnz     short loc_180058356
0x180058338  mov     eax, [rdi+50h]
0x18005833b  mov     [r14], eax
0x18005833e  xor     eax, eax
0x180058340  add     rsp, 30h
0x180058344  pop     r15
0x180058346  pop     r14
0x180058348  pop     r12
0x18005834a  pop     rdi
0x18005834b  pop     rsi
0x18005834c  pop     rbp
0x18005834d  pop     rbx
0x18005834e  retn
0x18005834f  mov     edx, 224h
0x180058354  jmp     short loc_180058308
0x180058356  mov     rcx, [rsp+68h]; this
0x18005835b  mov     edx, 0B0Fh; void *
0x180058360  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
