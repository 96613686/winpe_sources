# CScriptPlayerHelper::VibrateAsync(ulong)

- ea: `0x1800cb708`
- end: `0x1800cb845`
- name: `?VibrateAsync@CScriptPlayerHelper@@QEAAJK@Z`
- size: `317`
- prototype: `__int64 __fastcall(CScriptPlayerHelper *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800cae14`

## callees

- `0x180007f30`
- `0x18000a9cc`
- `0x180010a90`
- `0x1800525ec`
- `0x180087ea4`
- `0x180087ed0`
- `0x1800cb708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cb7f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800cb7f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800cb75a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800cb75a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cb797`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800cb797`

## pseudocode

```c
__int64 __fastcall CScriptPlayerHelper::VibrateAsync(CScriptPlayerHelper *this, int a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  HANDLE Event; // rax
  const char *v7; // r9
  void *v8; // rbx
  __int64 v9; // rdx
  HANDLE Thread; // rax
  _QWORD *v11; // rsi
  unsigned int LastError; // ebx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-28h]
  _QWORD v15[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HANDLE v17; // [rsp+60h] [rbp+18h] BYREF

  v4 = operator new[](0x18u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\scriptplayerhelper.cpp",
      (const char *)0x8007000ELL,
      dwCreationFlags);
    return LastError;
  }
  *v4 = 0;
  *((_DWORD *)v4 + 2) = 0;
  *v4 = this;
  *((_DWORD *)v4 + 2) = a2;
  Event = CreateEventExW(0, 0, 0, 0x100002u);
  v17 = Event;
  v8 = Event;
  if ( Event )
  {
    v5[2] = Event;
    Thread = CreateThread(0, 0, CScriptPlayerHelper::VibrateAsyncThreadProc, v5, 0, 0);
    v11 = (_QWORD *)((char *)this + 128);
    v15[0] = Thread;
    if ( v11 != v15 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v11,
        Thread);
      v15[0] = 0;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v15);
    if ( *v11 )
    {
      WaitForSingleObject(v8, 0xFFFFFFFF);
      LastError = 0;
      goto LABEL_10;
    }
    v9 = 550;
  }
  else
  {
    v9 = 546;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v9,
                (unsigned int)"avcore\\audiocore\\client\\audioplayer\\lib\\scriptplayerhelper.cpp",
                v7);
LABEL_10:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
  operator delete(v5, 0x18u);
  return LastError;
}

```

## disassembly

```asm
0x1800cb708  mov     [rsp+arg_0], rbx
0x1800cb70d  mov     [rsp+arg_8], rsi
0x1800cb712  push    rdi
0x1800cb713  sub     rsp, 40h
0x1800cb717  mov     ebx, edx
0x1800cb719  mov     rsi, rcx
0x1800cb71c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800cb723  mov     ecx, 18h; unsigned __int64
0x1800cb728  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800cb72d  mov     rdi, rax
0x1800cb730  test    rax, rax
0x1800cb733  jz      loc_1800CB815
0x1800cb739  mov     qword ptr [rax], 0
0x1800cb740  mov     r9d, 100002h; dwDesiredAccess
0x1800cb746  mov     dword ptr [rax+8], 0
0x1800cb74d  xor     r8d, r8d; dwFlags
0x1800cb750  mov     [rax], rsi
0x1800cb753  xor     edx, edx; lpName
0x1800cb755  xor     ecx, ecx; lpEventAttributes
0x1800cb757  mov     [rax+8], ebx
0x1800cb75a  call    cs:__imp_CreateEventExW
0x1800cb760  mov     [rsp+48h+arg_10], rax
0x1800cb765  mov     rbx, rax
0x1800cb768  test    rax, rax
0x1800cb76b  jnz     short loc_1800CB774
0x1800cb76d  mov     edx, 222h
0x1800cb772  jmp     short loc_1800CB7D9
0x1800cb774  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x1800cb77d  lea     r8, ?VibrateAsyncThreadProc@CScriptPlayerHelper@@SAKPEAX@Z; lpStartAddress
0x1800cb784  mov     r9, rdi; lpParameter
0x1800cb787  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800cb78f  xor     edx, edx; dwStackSize
0x1800cb791  mov     [rdi+10h], rbx
0x1800cb795  xor     ecx, ecx; lpThreadAttributes
0x1800cb797  call    cs:__imp_CreateThread
0x1800cb79d  lea     rcx, [rsp+48h+var_18]
0x1800cb7a2  sub     rsi, 0FFFFFFFFFFFFFF80h
0x1800cb7a6  mov     [rsp+48h+var_18], rax
0x1800cb7ab  cmp     rsi, rcx
0x1800cb7ae  jz      short loc_1800CB7C4
0x1800cb7b0  mov     rdx, rax
0x1800cb7b3  mov     rcx, rsi
0x1800cb7b6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800cb7bb  mov     [rsp+48h+var_18], 0
0x1800cb7c4  lea     rcx, [rsp+48h+var_18]
0x1800cb7c9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800cb7ce  cmp     qword ptr [rsi], 0
0x1800cb7d2  jnz     short loc_1800CB7EE
0x1800cb7d4  mov     edx, 226h; void *
0x1800cb7d9  mov     rcx, [rsp+48h]; this
0x1800cb7de  lea     r8, aAvcoreAudiocor_48; "avcore\\audiocore\\client\\audioplayer"...
0x1800cb7e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800cb7ea  mov     ebx, eax
0x1800cb7ec  jmp     short loc_1800CB7FC
0x1800cb7ee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800cb7f1  mov     rcx, rbx; hHandle
0x1800cb7f4  call    cs:__imp_WaitForSingleObject
0x1800cb7fa  xor     ebx, ebx
0x1800cb7fc  lea     rcx, [rsp+48h+arg_10]
0x1800cb801  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800cb806  mov     edx, 18h; unsigned __int64
0x1800cb80b  mov     rcx, rdi; void *
0x1800cb80e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800cb813  jmp     short loc_1800CB833
0x1800cb815  mov     rcx, [rsp+48h]; this
0x1800cb81a  lea     r8, aAvcoreAudiocor_48; "avcore\\audiocore\\client\\audioplayer"...
0x1800cb821  mov     ebx, 8007000Eh
0x1800cb826  mov     edx, 21Dh; void *
0x1800cb82b  mov     r9d, ebx; char *
0x1800cb82e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb833  mov     rsi, [rsp+48h+arg_8]
0x1800cb838  mov     eax, ebx
0x1800cb83a  mov     rbx, [rsp+48h+arg_0]
0x1800cb83f  add     rsp, 40h
0x1800cb843  pop     rdi
0x1800cb844  retn
```
