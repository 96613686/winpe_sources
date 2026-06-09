# CMidiXProc::Initialize(ulong *,std::unique_ptr<MEMORY_MAPPED_PIPE,std::default_delete<MEMORY_MAPPED_PIPE>> &,std::unique_ptr<MEMORY_MAPPED_PIPE,std::default_delete<MEMORY_MAPPED_PIPE>> &,IMidiCallback *,__int64,int)

- ea: `0x140046954`
- end: `0x140046b88`
- name: `?Initialize@CMidiXProc@@QEAAJPEAKAEAV?$unique_ptr@UMEMORY_MAPPED_PIPE@@U?$default_delete@UMEMORY_MAPPED_PIPE@@@std@@@std@@1PEAUIMidiCallback@@_JH@Z`
- size: `564`
- prototype: `__int64 __fastcall(char *lpParameter, _DWORD *, _DWORD **, int **, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14001fe88`

## callees

- `0x140005868`
- `0x140008b34`
- `0x14000a694`
- `0x14000a6b4`
- `0x14001fbec`
- `0x14002156c`
- `0x140046954`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140046b42`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140046b42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140046b05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140046b05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046af2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140046ad8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140046ad8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140046afd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140046afd`

## string_xrefs

- `0x140046b76`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall CMidiXProc::Initialize(
        char *lpParameter,
        _DWORD *a2,
        _DWORD **a3,
        int **a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  __int64 v11; // rdx
  _DWORD *v13; // rax
  int v14; // edx
  __int64 v15; // rbx
  _DWORD *v16; // rax
  MEMORY_MAPPED_PIPE *v17; // rbx
  int *v18; // rax
  MEMORY_MAPPED_PIPE *v19; // rbx
  HANDLE Thread; // rsi
  const char *v21; // r9
  char *v22; // rbp
  DWORD LastError; // ebx
  __int64 v24; // rdx
  DWORD v25; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !a2 )
  {
    v11 = 504;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
      (const char *)0x80070057LL,
      dwCreationFlags);
    return 2147942487LL;
  }
  v13 = *a3;
  if ( *a3 )
  {
    if ( !a5 )
    {
      v11 = 506;
      goto LABEL_3;
    }
    if ( (unsigned int)(*v13 - 1) > 1 && *v13 != -1 )
    {
      v11 = 513;
      goto LABEL_3;
    }
  }
  else if ( !*a4 )
  {
    v11 = 505;
    goto LABEL_3;
  }
  if ( *a4 )
  {
    v14 = **a4;
    if ( (unsigned int)(v14 - 1) > 1 && v14 != -1 )
    {
      v11 = 520;
      goto LABEL_3;
    }
  }
  v15 = *((_QWORD *)lpParameter + 11);
  *((_QWORD *)lpParameter + 11) = a5;
  if ( a5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a5 + 8LL))(a5);
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  *((_QWORD *)lpParameter + 12) = a6;
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(lpParameter + 120);
  _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(lpParameter + 128);
  *((_DWORD *)lpParameter + 20) = *a2;
  v16 = *a3;
  *a3 = 0;
  v17 = (MEMORY_MAPPED_PIPE *)*((_QWORD *)lpParameter + 13);
  *((_QWORD *)lpParameter + 13) = v16;
  if ( v17 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v17);
    operator delete(v17);
  }
  v18 = *a4;
  *a4 = 0;
  v19 = (MEMORY_MAPPED_PIPE *)*((_QWORD *)lpParameter + 14);
  *((_QWORD *)lpParameter + 14) = v18;
  if ( v19 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v19);
    operator delete(v19);
  }
  *(_DWORD *)lpParameter = a7;
  if ( *((_QWORD *)lpParameter + 13) )
  {
    Thread = CreateThread(0, 0, CMidiXProc::MidiInWorker, lpParameter, 0, 0);
    v22 = (char *)*((_QWORD *)lpParameter + 17);
    if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v22);
      SetLastError(LastError);
    }
    *((_QWORD *)lpParameter + 17) = Thread;
    if ( (((unsigned __int64)Thread + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v24 = 546;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v24,
               (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
               v21);
    }
    v25 = WaitForSingleObjectEx(*((HANDLE *)lpParameter + 16), 0x3E8u, 0);
    if ( v25 == 258 )
    {
      v24 = 548;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v24,
               (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
               v21);
    }
    if ( v25 )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB0F,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v21);
  }
  *a2 = *((_DWORD *)lpParameter + 20);
  return 0;
}

```

## disassembly

```asm
0x140046954  push    rbx
0x140046956  push    rbp
0x140046957  push    rsi
0x140046958  push    rdi
0x140046959  push    r12
0x14004695b  push    r14
0x14004695d  push    r15
0x14004695f  sub     rsp, 30h
0x140046963  mov     rsi, r9
0x140046966  mov     r14, r8
0x140046969  mov     r15, rdx
0x14004696c  mov     rdi, rcx
0x14004696f  test    rdx, rdx
0x140046972  jnz     short loc_140046999
0x140046974  mov     edx, 1F8h; void *
0x140046979  mov     ebx, 80070057h
0x14004697e  mov     rcx, [rsp+68h]; this
0x140046983  mov     r9d, ebx; char *
0x140046986  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x14004698d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140046992  mov     eax, ebx
0x140046994  jmp     loc_140046B5B
0x140046999  mov     rax, [r8]
0x14004699c  mov     rcx, [rsp+68h+arg_20]
0x1400469a4  test    rax, rax
0x1400469a7  jnz     short loc_1400469B5
0x1400469a9  cmp     [r9], rax
0x1400469ac  jnz     short loc_1400469D7
0x1400469ae  mov     edx, 1F9h
0x1400469b3  jmp     short loc_140046979
0x1400469b5  test    rcx, rcx
0x1400469b8  jnz     short loc_1400469C1
0x1400469ba  mov     edx, 1FAh
0x1400469bf  jmp     short loc_140046979
0x1400469c1  mov     edx, [rax]
0x1400469c3  lea     eax, [rdx-1]
0x1400469c6  cmp     eax, 1
0x1400469c9  jbe     short loc_1400469D7
0x1400469cb  cmp     edx, 0FFFFFFFFh
0x1400469ce  jz      short loc_1400469D7
0x1400469d0  mov     edx, 201h
0x1400469d5  jmp     short loc_140046979
0x1400469d7  mov     rax, [r9]
0x1400469da  test    rax, rax
0x1400469dd  jz      short loc_1400469F5
0x1400469df  mov     edx, [rax]
0x1400469e1  lea     eax, [rdx-1]
0x1400469e4  cmp     eax, 1
0x1400469e7  jbe     short loc_1400469F5
0x1400469e9  cmp     edx, 0FFFFFFFFh
0x1400469ec  jz      short loc_1400469F5
0x1400469ee  mov     edx, 208h
0x1400469f3  jmp     short loc_140046979
0x1400469f5  mov     rbx, [rdi+58h]
0x1400469f9  mov     [rdi+58h], rcx
0x1400469fd  test    rcx, rcx
0x140046a00  jz      short loc_140046A0E
0x140046a02  mov     rax, [rcx]
0x140046a05  mov     rax, [rax+8]
0x140046a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046a0e  test    rbx, rbx
0x140046a11  jz      short loc_140046A23
0x140046a13  mov     rax, [rbx]
0x140046a16  mov     rcx, rbx
0x140046a19  mov     rax, [rax+10h]
0x140046a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046a22  nop
0x140046a23  mov     rax, [rsp+68h+arg_28]
0x140046a2b  mov     [rdi+60h], rax
0x140046a2f  lea     rcx, [rdi+78h]
0x140046a33  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140046a38  lea     r12, [rdi+80h]
0x140046a3f  mov     rcx, r12
0x140046a42  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x140046a47  mov     eax, [r15]
0x140046a4a  mov     [rdi+50h], eax
0x140046a4d  mov     rax, [r14]
0x140046a50  mov     qword ptr [r14], 0
0x140046a57  mov     rbx, [rdi+68h]
0x140046a5b  mov     [rdi+68h], rax
0x140046a5f  mov     ebp, 68h ; 'h'
0x140046a64  test    rbx, rbx
0x140046a67  jz      short loc_140046A7B
0x140046a69  mov     rcx, rbx; this
0x140046a6c  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x140046a71  mov     edx, ebp
0x140046a73  mov     rcx, rbx; Block
0x140046a76  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140046a7b  mov     rax, [rsi]
0x140046a7e  mov     qword ptr [rsi], 0
0x140046a85  mov     rbx, [rdi+70h]
0x140046a89  mov     [rdi+70h], rax
0x140046a8d  test    rbx, rbx
0x140046a90  jz      short loc_140046AA5
0x140046a92  mov     rcx, rbx; this
0x140046a95  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x140046a9a  mov     rdx, rbp
0x140046a9d  mov     rcx, rbx; Block
0x140046aa0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140046aa5  mov     eax, [rsp+68h+arg_30]
0x140046aac  mov     [rdi], eax
0x140046aae  cmp     qword ptr [rdi+68h], 0
0x140046ab3  jz      loc_140046B53
0x140046ab9  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x140046ac2  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x140046aca  mov     r9, rdi; lpParameter
0x140046acd  lea     r8, ?MidiInWorker@CMidiXProc@@CAKPEAX@Z; lpStartAddress
0x140046ad4  xor     edx, edx; dwStackSize
0x140046ad6  xor     ecx, ecx; lpThreadAttributes
0x140046ad8  call    cs:__imp_CreateThread
0x140046ade  mov     rsi, rax
0x140046ae1  mov     rbp, [rdi+88h]
0x140046ae8  lea     rdx, [rbp-1]
0x140046aec  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140046af0  ja      short loc_140046B0B
0x140046af2  call    cs:__imp_GetLastError
0x140046af8  mov     ebx, eax
0x140046afa  mov     rcx, rbp; hObject
0x140046afd  call    cs:__imp_CloseHandle
0x140046b03  mov     ecx, ebx; dwErrCode
0x140046b05  call    cs:__imp_SetLastError
0x140046b0b  mov     [rdi+88h], rsi
0x140046b12  lea     rax, [rsi+1]
0x140046b16  test    rax, 0FFFFFFFFFFFFFFFEh
0x140046b1c  jnz     short loc_140046B36
0x140046b1e  mov     edx, 222h; void *
0x140046b23  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x140046b2a  mov     rcx, [rsp+68h]; this
0x140046b2f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140046b34  jmp     short loc_140046B5B
0x140046b36  xor     r8d, r8d; bAlertable
0x140046b39  mov     edx, 3E8h; dwMilliseconds
0x140046b3e  mov     rcx, [r12]; hHandle
0x140046b42  call    cs:__imp_WaitForSingleObjectEx
0x140046b48  cmp     eax, 102h
0x140046b4d  jz      short loc_140046B6A
0x140046b4f  test    eax, eax
0x140046b51  jnz     short loc_140046B71
0x140046b53  mov     eax, [rdi+50h]
0x140046b56  mov     [r15], eax
0x140046b59  xor     eax, eax
0x140046b5b  add     rsp, 30h
0x140046b5f  pop     r15
0x140046b61  pop     r14
0x140046b63  pop     r12
0x140046b65  pop     rdi
0x140046b66  pop     rsi
0x140046b67  pop     rbp
0x140046b68  pop     rbx
0x140046b69  retn
0x140046b6a  mov     edx, 224h
0x140046b6f  jmp     short loc_140046B23
0x140046b71  mov     rcx, [rsp+68h]; this
0x140046b76  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140046b7d  mov     edx, 0B0Fh; void *
0x140046b82  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
