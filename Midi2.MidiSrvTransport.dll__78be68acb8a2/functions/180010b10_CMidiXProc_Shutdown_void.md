# CMidiXProc::Shutdown(void)

- ea: `0x180010b10`
- end: `0x180010c1f`
- name: `?Shutdown@CMidiXProc@@QEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(CMidiXProc *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18000d190`
- `0x180011b40`
- `0x1800138f8`

## callees

- `0x180002494`
- `0x180007e04`
- `0x180009014`
- `0x18000d3e4`
- `0x18000d854`
- `0x180010b10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010b3f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010b3f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010b57`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010b57`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ba0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010b98`

## pseudocode

```c
__int64 __fastcall CMidiXProc::Shutdown(void **this)
{
  __int64 v2; // r8
  const char *v3; // r9
  const char *v4; // r9
  char *v6; // rsi
  DWORD LastError; // ebx
  MEMORY_MAPPED_PIPE *v8; // rbx
  MEMORY_MAPPED_PIPE *v9; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  DisableMmcss(this + 9);
  if ( (char *)this[17] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( !SetEvent(this[15]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v2, v3);
    if ( WaitForSingleObject(this[17], 0xFFFFFFFF) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x23D,
               (unsigned int)"avcore\\midi2\\libs\\midixproc\\midixproc.cpp",
               v4);
    v6 = (char *)this[17];
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      CloseHandle(v6);
      SetLastError(LastError);
    }
    this[17] = 0;
  }
  v8 = (MEMORY_MAPPED_PIPE *)this[13];
  this[13] = 0;
  if ( v8 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v8);
    operator delete(v8);
  }
  v9 = (MEMORY_MAPPED_PIPE *)this[14];
  this[14] = 0;
  if ( v9 )
  {
    MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v9);
    operator delete(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180010b10  mov     [rsp+arg_0], rbx
0x180010b15  mov     [rsp+arg_8], rsi
0x180010b1a  push    rdi
0x180010b1b  sub     rsp, 20h
0x180010b1f  mov     rdi, rcx
0x180010b22  add     rcx, 48h ; 'H'
0x180010b26  call    ?DisableMmcss@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?AvRevertMmThreadCharacteristics@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; DisableMmcss(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&AvRevertMmThreadCharacteristics(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180010b2b  mov     rax, [rdi+88h]
0x180010b32  dec     rax
0x180010b35  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010b39  ja      short loc_180010BB1
0x180010b3b  mov     rcx, [rdi+78h]; hEvent
0x180010b3f  call    cs:__imp_SetEvent
0x180010b45  test    eax, eax
0x180010b47  jz      loc_180010C0F
0x180010b4d  mov     rcx, [rdi+88h]; hHandle
0x180010b54  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180010b57  call    cs:__imp_WaitForSingleObject
0x180010b5d  test    eax, eax
0x180010b5f  jz      short loc_180010B7C
0x180010b61  mov     rcx, [rsp+28h]; this
0x180010b66  lea     r8, aAvcoreMidi2Lib_0; "avcore\\midi2\\libs\\midixproc\\midixpr"...
0x180010b6d  mov     edx, 23Dh; void *
0x180010b72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010b77  jmp     loc_180010BFF
0x180010b7c  mov     rsi, [rdi+88h]
0x180010b83  lea     rax, [rsi-1]
0x180010b87  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010b8b  ja      short loc_180010BA6
0x180010b8d  call    cs:__imp_GetLastError
0x180010b93  mov     rcx, rsi; hObject
0x180010b96  mov     ebx, eax
0x180010b98  call    cs:__imp_CloseHandle
0x180010b9e  mov     ecx, ebx; dwErrCode
0x180010ba0  call    cs:__imp_SetLastError
0x180010ba6  mov     qword ptr [rdi+88h], 0
0x180010bb1  mov     rbx, [rdi+68h]
0x180010bb5  mov     esi, 68h ; 'h'
0x180010bba  mov     qword ptr [rdi+68h], 0
0x180010bc2  test    rbx, rbx
0x180010bc5  jz      short loc_180010BD9
0x180010bc7  mov     rcx, rbx; this
0x180010bca  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180010bcf  mov     edx, esi
0x180010bd1  mov     rcx, rbx; Block
0x180010bd4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010bd9  mov     rbx, [rdi+70h]
0x180010bdd  mov     qword ptr [rdi+70h], 0
0x180010be5  test    rbx, rbx
0x180010be8  jz      short loc_180010BFD
0x180010bea  mov     rcx, rbx; this
0x180010bed  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180010bf2  mov     rdx, rsi
0x180010bf5  mov     rcx, rbx; Block
0x180010bf8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010bfd  xor     eax, eax
0x180010bff  mov     rbx, [rsp+28h+arg_0]
0x180010c04  mov     rsi, [rsp+28h+arg_8]
0x180010c09  add     rsp, 20h
0x180010c0d  pop     rdi
0x180010c0e  retn
0x180010c0f  mov     rcx, [rsp+28h]; this
0x180010c14  mov     edx, 0A01h; void *
0x180010c19  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
