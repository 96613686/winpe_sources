# DCEngine::Initialize(int,int)

- ea: `0x180112f58`
- end: `0x18011314e`
- name: `?Initialize@DCEngine@@AEAAJHH@Z`
- size: `502`
- prototype: `__int64 __fastcall(DCEngine *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x180119490`

## callees

- `0x18000be80`
- `0x18000bf00`
- `0x1800a1878`
- `0x1800f5c8c`
- `0x1800f9d70`
- `0x18010d704`
- `0x180112f58`
- `0x1801185c8`
- `0x18011cdbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180113020`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180113020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011303f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801130d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011303f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801130d8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801130b9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1801130b9`

## string_xrefs

- `0x1801130fd`: `CreateThread(NULL, 0, StaticExecuteRequests, NULL, 0, NULL)`

## pseudocode

```c
__int64 __fastcall DCEngine::Initialize(DCEngine *this)
{
  _QWORD *v2; // rax
  void *v3; // rcx
  signed int v4; // edi
  CDeclaredConfigurationLogger *v5; // rax
  HANDLE EventW; // rax
  __int64 v7; // rcx
  signed int v8; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  CDeclaredConfigurationLogger *Logger; // rax

  *((_DWORD *)this + 70) = 0;
  v2 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
  if ( v2 )
  {
    *v2 = &DefaultOrchestratorActivityContextStore::`vftable';
    v2[1] = &qword_18018A660;
  }
  v3 = (void *)*((_QWORD *)this + 38);
  *((_QWORD *)this + 38) = v2;
  if ( v3 )
    operator delete(v3);
  if ( *((_QWORD *)this + 38) )
  {
    v4 = DeclaredConfigurations::RequestQueue::Init((DCEngine *)((char *)this + 8));
    if ( v4 >= 0 )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 176,
        EventW);
      if ( ((*((_QWORD *)this + 22) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        std::_List_node<OrchestratorInstanceVariableTag,void *>::_Free_non_head<std::allocator<std::_List_node<OrchestratorInstanceVariableTag,void *>>>(
          v7,
          *((_QWORD *)this + 36));
        **((_QWORD **)this + 36) = *((_QWORD *)this + 36);
        *(_QWORD *)(*((_QWORD *)this + 36) + 8LL) = *((_QWORD *)this + 36);
        *((_QWORD *)this + 37) = 0;
        *((_DWORD *)this + 69) = 1;
        Thread = CreateThread(0, 0, DCEngine::StaticExecuteRequests, 0, 0, 0);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 168,
          Thread);
        if ( ((*((_QWORD *)this + 21) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          return (unsigned int)v4;
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        Logger = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
          Logger,
          L"DCEngine::Initialize",
          L"CreateThread(NULL, 0, StaticExecuteRequests, NULL, 0, NULL)",
          &word_180142E98,
          v4);
      }
      else
      {
        v8 = GetLastError();
        v4 = v8;
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0x80070000;
      }
      if ( v4 >= 0 )
        return (unsigned int)v4;
    }
    else
    {
      v5 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
        v5,
        L"DCEngine::Initialize",
        L"m_requestQueue.Init",
        &word_180142E98,
        v4);
    }
  }
  else
  {
    v4 = -2147024882;
  }
  if ( (unsigned __int64)(*((_QWORD *)this + 21) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    DCEngine::StopRequestsThread(this);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 168,
      0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180112f58  mov     [rsp+arg_8], rbx
0x180112f5d  mov     [rsp+arg_10], rsi
0x180112f62  push    rdi
0x180112f63  sub     rsp, 30h
0x180112f67  mov     rsi, rcx
0x180112f6a  mov     dword ptr [rcx+118h], 0
0x180112f74  mov     ecx, 10h; unsigned __int64
0x180112f79  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180112f80  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180112f85  mov     [rsp+38h+arg_0], rax
0x180112f8a  test    rax, rax
0x180112f8d  jz      short loc_180112FA4
0x180112f8f  lea     rcx, ??_7DefaultOrchestratorActivityContextStore@@6B@; const DefaultOrchestratorActivityContextStore::`vftable'
0x180112f96  mov     [rax], rcx
0x180112f99  lea     rcx, qword_18018A660
0x180112fa0  mov     [rax+8], rcx
0x180112fa4  mov     rcx, [rsi+130h]; Block
0x180112fab  mov     [rsi+130h], rax
0x180112fb2  test    rcx, rcx
0x180112fb5  jz      short loc_180112FC1
0x180112fb7  mov     edx, 8
0x180112fbc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180112fc1  cmp     qword ptr [rsi+130h], 0
0x180112fc9  jnz     short loc_180112FD5
0x180112fcb  mov     edi, 8007000Eh
0x180112fd0  jmp     loc_180113117
0x180112fd5  lea     rcx, [rsi+8]; this
0x180112fd9  call    ?Init@RequestQueue@DeclaredConfigurations@@QEAAJXZ; DeclaredConfigurations::RequestQueue::Init(void)
0x180112fde  mov     edi, eax
0x180112fe0  test    eax, eax
0x180112fe2  jns     short loc_18011300F
0x180112fe4  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180112fe9  lea     r9, word_180142E98; unsigned __int16 *
0x180112ff0  mov     [rsp+38h+dwCreationFlags], edi; int
0x180112ff4  lea     r8, aMRequestqueueI; "m_requestQueue.Init"
0x180112ffb  mov     rcx, rax; this
0x180112ffe  lea     rdx, aDcengineInitia; "DCEngine::Initialize"
0x180113005  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x18011300a  jmp     loc_180113117
0x18011300f  xor     r9d, r9d; lpName
0x180113012  lea     rbx, [rsi+0B0h]
0x180113019  xor     r8d, r8d; bInitialState
0x18011301c  xor     edx, edx; bManualReset
0x18011301e  xor     ecx, ecx; lpEventAttributes
0x180113020  call    cs:__imp_CreateEventW
0x180113026  mov     rdx, rax
0x180113029  mov     rcx, rbx
0x18011302c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180113031  mov     rax, [rbx]
0x180113034  inc     rax
0x180113037  test    rax, 0FFFFFFFFFFFFFFFEh
0x18011303d  jnz     short loc_18011305D
0x18011303f  call    cs:__imp_GetLastError
0x180113045  mov     edi, eax
0x180113047  test    eax, eax
0x180113049  jle     loc_180113113
0x18011304f  movzx   edi, ax
0x180113052  or      edi, 80070000h
0x180113058  jmp     loc_180113113
0x18011305d  mov     rdx, [rsi+120h]
0x180113064  call    ??$_Free_non_head@V?$allocator@U?$_List_node@UOrchestratorInstanceVariableTag@@PEAX@std@@@std@@@?$_List_node@UOrchestratorInstanceVariableTag@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UOrchestratorInstanceVariableTag@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<OrchestratorInstanceVariableTag,void *>::_Free_non_head<std::allocator<std::_List_node<OrchestratorInstanceVariableTag,void *>>>(std::allocator<std::_List_node<OrchestratorInstanceVariableTag,void *>> &,std::_List_node<OrchestratorInstanceVariableTag,void *> *)
0x180113069  mov     rax, [rsi+120h]
0x180113070  lea     r8, ?StaticExecuteRequests@DCEngine@@CAKPEAX@Z; lpStartAddress
0x180113077  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180113080  lea     rbx, [rsi+0A8h]
0x180113087  xor     r9d, r9d; lpParameter
0x18011308a  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180113092  xor     edx, edx; dwStackSize
0x180113094  xor     ecx, ecx; lpThreadAttributes
0x180113096  mov     [rax], rax
0x180113099  mov     rax, [rsi+120h]
0x1801130a0  mov     [rax+8], rax
0x1801130a4  mov     qword ptr [rsi+128h], 0
0x1801130af  mov     dword ptr [rsi+114h], 1
0x1801130b9  call    cs:__imp_CreateThread
0x1801130bf  mov     rdx, rax
0x1801130c2  mov     rcx, rbx
0x1801130c5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801130ca  mov     rax, [rbx]
0x1801130cd  inc     rax
0x1801130d0  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801130d6  jnz     short loc_18011313C
0x1801130d8  call    cs:__imp_GetLastError
0x1801130de  mov     edi, eax
0x1801130e0  test    eax, eax
0x1801130e2  jle     short loc_1801130ED
0x1801130e4  movzx   edi, ax
0x1801130e7  or      edi, 80070000h
0x1801130ed  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801130f2  lea     r9, word_180142E98; unsigned __int16 *
0x1801130f9  mov     [rsp+38h+dwCreationFlags], edi; int
0x1801130fd  lea     r8, aCreatethreadNu; "CreateThread(NULL, 0, StaticExecuteRequ"...
0x180113104  mov     rcx, rax; this
0x180113107  lea     rdx, aDcengineInitia; "DCEngine::Initialize"
0x18011310e  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180113113  test    edi, edi
0x180113115  jns     short loc_18011313C
0x180113117  lea     rbx, [rsi+0A8h]
0x18011311e  mov     rax, [rbx]
0x180113121  dec     rax
0x180113124  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180113128  ja      short loc_18011313C
0x18011312a  mov     rcx, rsi; this
0x18011312d  call    ?StopRequestsThread@DCEngine@@AEAAXXZ; DCEngine::StopRequestsThread(void)
0x180113132  xor     edx, edx
0x180113134  mov     rcx, rbx
0x180113137  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18011313c  mov     rbx, [rsp+38h+arg_8]
0x180113141  mov     eax, edi
0x180113143  mov     rsi, [rsp+38h+arg_10]
0x180113148  add     rsp, 30h
0x18011314c  pop     rdi
0x18011314d  retn
```
