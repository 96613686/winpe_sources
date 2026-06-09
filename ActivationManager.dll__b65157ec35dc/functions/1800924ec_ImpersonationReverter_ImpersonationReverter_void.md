# ImpersonationReverter::ImpersonationReverter(void)

- ea: `0x1800924ec`
- end: `0x180092597`
- name: `??0ImpersonationReverter@@AEAA@XZ`
- size: `171`
- prototype: `ImpersonationReverter *__fastcall(ImpersonationReverter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800925a0`

## callees

- `0x18003f63c`
- `0x18007638c`
- `0x1800924ec`
- `0x1800925c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009254b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009254b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009256a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18009256a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180092535`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180092535`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009251e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009251e`

## string_xrefs

- `0x180092579`: `onecore\base\appmodel\execmodel\desktopappx\sharedlib\securityutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ImpersonationReverter *__fastcall ImpersonationReverter::ImpersonationReverter(ImpersonationReverter *this)
{
  HANDLE CurrentThread; // rax
  BOOL v3; // ebx
  DWORD LastError; // eax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  char *v9; // [rsp+20h] [rbp-28h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-20h] BYREF
  char v11; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_BYTE *)this = 1;
  *((_QWORD *)this + 1) = 0;
  v9 = (char *)this + 8;
  TokenHandle = 0;
  v11 = 1;
  CurrentThread = GetCurrentThread();
  v3 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v9);
  if ( v3 )
  {
    if ( !SetThreadToken(0, 0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\securityutils.cpp",
        v7);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Win32(retaddr, v5, v6, (const char *)LastError, (unsigned int)v9);
  }
  return this;
}

```

## disassembly

```asm
0x1800924ec  mov     r11, rsp
0x1800924ef  mov     [r11+10h], rbx
0x1800924f3  mov     [r11+8], rcx
0x1800924f7  push    rdi
0x1800924f8  sub     rsp, 40h
0x1800924fc  mov     rdi, rcx
0x1800924ff  mov     byte ptr [rcx], 1
0x180092502  lea     rax, [rcx+8]
0x180092506  mov     qword ptr [rax], 0
0x18009250d  mov     [r11-28h], rax
0x180092511  mov     qword ptr [r11-20h], 0
0x180092519  mov     [rsp+48h+var_18], 1
0x18009251e  call    cs:__imp_GetCurrentThread
0x180092524  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180092529  mov     edx, 0Ch; DesiredAccess
0x18009252e  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180092532  mov     rcx, rax; ThreadHandle
0x180092535  call    cs:__imp_OpenThreadToken
0x18009253b  mov     ebx, eax
0x18009253d  lea     rcx, [rsp+48h+var_28]
0x180092542  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180092547  test    ebx, ebx
0x180092549  jnz     short loc_180092566
0x18009254b  call    cs:__imp_GetLastError
0x180092551  cmp     eax, 3F0h
0x180092556  jz      short loc_180092589
0x180092558  mov     rcx, [rsp+48h]; this
0x18009255d  mov     r9d, eax; char *
0x180092560  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180092566  xor     edx, edx; Token
0x180092568  xor     ecx, ecx; Thread
0x18009256a  call    cs:__imp_SetThreadToken
0x180092570  mov     rcx, [rsp+48h]; this
0x180092575  test    eax, eax
0x180092577  jnz     short loc_180092589
0x180092579  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\execmodel\\des"...
0x180092580  lea     edx, [rax+3Eh]; void *
0x180092583  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180092589  mov     rax, rdi
0x18009258c  mov     rbx, [rsp+48h+arg_8]
0x180092591  add     rsp, 40h
0x180092595  pop     rdi
0x180092596  retn
```
