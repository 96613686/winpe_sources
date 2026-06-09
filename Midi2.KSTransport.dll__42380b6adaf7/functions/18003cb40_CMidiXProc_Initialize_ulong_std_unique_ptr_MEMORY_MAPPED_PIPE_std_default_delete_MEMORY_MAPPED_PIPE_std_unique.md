# CMidiXProc::Initialize(ulong *,std::unique_ptr<MEMORY_MAPPED_PIPE,std::default_delete<MEMORY_MAPPED_PIPE>> &,std::unique_ptr<MEMORY_MAPPED_PIPE,std::default_delete<MEMORY_MAPPED_PIPE>> &,IMidiCallback *,__int64,int)

- ea: `0x18003cb40`
- end: `0x18003cd6a`
- name: `?Initialize@CMidiXProc@@QEAAJPEAKAEAV?$unique_ptr@UMEMORY_MAPPED_PIPE@@U?$default_delete@UMEMORY_MAPPED_PIPE@@@std@@@std@@1PEAUIMidiCallback@@_JH@Z`
- size: `554`
- prototype: `__int64 __usercall@<rax>(LPVOID lpParameter@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800285a0`
- `0x180028994`
- `0x180029038`

## callees

- `0x180004434`
- `0x180007dd0`
- `0x18000a7f4`
- `0x18000a814`
- `0x180010f30`
- `0x18002a3c0`
- `0x18003cb40`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003cd2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003cd2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ccee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ccee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ccdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ccdb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003ccc1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003ccc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cce6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003cce6`

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
0x18003cb40  push    rbx
0x18003cb42  push    rbp
0x18003cb43  push    rsi
0x18003cb44  push    rdi
0x18003cb45  push    r12
0x18003cb47  push    r14
0x18003cb49  push    r15
0x18003cb4b  sub     rsp, 30h
0x18003cb4f  mov     rsi, r9
0x18003cb52  mov     r15, r8
0x18003cb55  mov     r14, rdx
0x18003cb58  mov     rdi, rcx
0x18003cb5b  test    rdx, rdx
0x18003cb5e  jnz     short loc_18003CB85
0x18003cb60  mov     edx, 1F8h; void *
0x18003cb65  mov     ebx, 80070057h
0x18003cb6a  mov     rcx, [rsp+68h]; this
0x18003cb6f  mov     r9d, ebx; char *
0x18003cb72  lea     r8, aAvcoreMidi2Lib_3; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18003cb79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003cb7e  mov     eax, ebx
0x18003cb80  jmp     loc_18003CD44
0x18003cb85  mov     rax, [r8]
0x18003cb88  mov     rcx, [rsp+68h+arg_20]
0x18003cb90  test    rax, rax
0x18003cb93  jnz     short loc_18003CBA1
0x18003cb95  cmp     [r9], rax
0x18003cb98  jnz     short loc_18003CBC3
0x18003cb9a  mov     edx, 1F9h
0x18003cb9f  jmp     short loc_18003CB65
0x18003cba1  test    rcx, rcx
0x18003cba4  jnz     short loc_18003CBAD
0x18003cba6  mov     edx, 1FAh
0x18003cbab  jmp     short loc_18003CB65
0x18003cbad  mov     edx, [rax]
0x18003cbaf  lea     eax, [rdx-1]
0x18003cbb2  cmp     eax, 1
0x18003cbb5  jbe     short loc_18003CBC3
0x18003cbb7  cmp     edx, 0FFFFFFFFh
0x18003cbba  jz      short loc_18003CBC3
0x18003cbbc  mov     edx, 201h
0x18003cbc1  jmp     short loc_18003CB65
0x18003cbc3  mov     rax, [r9]
0x18003cbc6  test    rax, rax
0x18003cbc9  jz      short loc_18003CBE1
0x18003cbcb  mov     edx, [rax]
0x18003cbcd  lea     eax, [rdx-1]
0x18003cbd0  cmp     eax, 1
0x18003cbd3  jbe     short loc_18003CBE1
0x18003cbd5  cmp     edx, 0FFFFFFFFh
0x18003cbd8  jz      short loc_18003CBE1
0x18003cbda  mov     edx, 208h
0x18003cbdf  jmp     short loc_18003CB65
0x18003cbe1  mov     rbx, [rdi+58h]
0x18003cbe5  mov     [rdi+58h], rcx
0x18003cbe9  test    rcx, rcx
0x18003cbec  jz      short loc_18003CBFA
0x18003cbee  mov     rax, [rcx]
0x18003cbf1  mov     rax, [rax+8]
0x18003cbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbfa  test    rbx, rbx
0x18003cbfd  jz      short loc_18003CC0F
0x18003cbff  mov     rax, [rbx]
0x18003cc02  mov     rcx, rbx
0x18003cc05  mov     rax, [rax+10h]
0x18003cc09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc0e  nop
0x18003cc0f  mov     rax, [rsp+68h+arg_28]
0x18003cc17  mov     [rdi+60h], rax
0x18003cc1b  lea     rcx, [rdi+78h]
0x18003cc1f  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003cc24  lea     r12, [rdi+80h]
0x18003cc2b  mov     rcx, r12
0x18003cc2e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003cc33  mov     eax, [r14]
0x18003cc36  mov     [rdi+50h], eax
0x18003cc39  mov     rax, [r15]
0x18003cc3c  mov     qword ptr [r15], 0
0x18003cc43  mov     rbx, [rdi+68h]
0x18003cc47  mov     [rdi+68h], rax
0x18003cc4b  mov     ebp, 68h ; 'h'
0x18003cc50  test    rbx, rbx
0x18003cc53  jz      short loc_18003CC67
0x18003cc55  mov     rcx, rbx; this
0x18003cc58  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18003cc5d  mov     edx, ebp
0x18003cc5f  mov     rcx, rbx; Block
0x18003cc62  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003cc67  mov     rax, [rsi]
0x18003cc6a  mov     qword ptr [rsi], 0
0x18003cc71  mov     rbx, [rdi+70h]
0x18003cc75  mov     [rdi+70h], rax
0x18003cc79  test    rbx, rbx
0x18003cc7c  jz      short loc_18003CC91
0x18003cc7e  mov     rcx, rbx; this
0x18003cc81  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x18003cc86  mov     rdx, rbp
0x18003cc89  mov     rcx, rbx; Block
0x18003cc8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003cc91  mov     dword ptr [rdi], 1
0x18003cc97  cmp     qword ptr [rdi+68h], 0
0x18003cc9c  jz      loc_18003CD3C
0x18003cca2  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x18003ccab  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x18003ccb3  mov     r9, rdi; lpParameter
0x18003ccb6  lea     r8, ?MidiInWorker@CMidiXProc@@CAKPEAX@Z; lpStartAddress
0x18003ccbd  xor     edx, edx; dwStackSize
0x18003ccbf  xor     ecx, ecx; lpThreadAttributes
0x18003ccc1  call    cs:__imp_CreateThread
0x18003ccc7  mov     rsi, rax
0x18003ccca  mov     rbp, [rdi+88h]
0x18003ccd1  lea     rdx, [rbp-1]
0x18003ccd5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003ccd9  ja      short loc_18003CCF4
0x18003ccdb  call    cs:__imp_GetLastError
0x18003cce1  mov     ebx, eax
0x18003cce3  mov     rcx, rbp; hObject
0x18003cce6  call    cs:__imp_CloseHandle
0x18003ccec  mov     ecx, ebx; dwErrCode
0x18003ccee  call    cs:__imp_SetLastError
0x18003ccf4  mov     [rdi+88h], rsi
0x18003ccfb  lea     rax, [rsi+1]
0x18003ccff  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003cd05  jnz     short loc_18003CD1F
0x18003cd07  mov     edx, 222h; void *
0x18003cd0c  lea     r8, aAvcoreMidi2Lib_3; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x18003cd13  mov     rcx, [rsp+68h]; this
0x18003cd18  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003cd1d  jmp     short loc_18003CD44
0x18003cd1f  xor     r8d, r8d; bAlertable
0x18003cd22  mov     edx, 3E8h; dwMilliseconds
0x18003cd27  mov     rcx, [r12]; hHandle
0x18003cd2b  call    cs:__imp_WaitForSingleObjectEx
0x18003cd31  cmp     eax, 102h
0x18003cd36  jz      short loc_18003CD53
0x18003cd38  test    eax, eax
0x18003cd3a  jnz     short loc_18003CD5A
0x18003cd3c  mov     eax, [rdi+50h]
0x18003cd3f  mov     [r14], eax
0x18003cd42  xor     eax, eax
0x18003cd44  add     rsp, 30h
0x18003cd48  pop     r15
0x18003cd4a  pop     r14
0x18003cd4c  pop     r12
0x18003cd4e  pop     rdi
0x18003cd4f  pop     rsi
0x18003cd50  pop     rbp
0x18003cd51  pop     rbx
0x18003cd52  retn
0x18003cd53  mov     edx, 224h
0x18003cd58  jmp     short loc_18003CD0C
0x18003cd5a  mov     rcx, [rsp+68h]; this
0x18003cd5f  mov     edx, 0B0Fh; void *
0x18003cd64  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
