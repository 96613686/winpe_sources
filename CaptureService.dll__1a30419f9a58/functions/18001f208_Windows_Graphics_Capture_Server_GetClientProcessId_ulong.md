# Windows::Graphics::Capture::Server::GetClientProcessId(ulong *)

- ea: `0x18001f208`
- end: `0x18001f280`
- name: `?GetClientProcessId@Server@Capture@Graphics@Windows@@YAJPEAK@Z`
- size: `120`
- prototype: `int(Windows::Graphics::Capture::Server *__hidden this, unsigned int *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18001ca68`
- `0x18001d350`
- `0x18001d4b0`
- `0x18001e964`
- `0x18001ea40`

## callees

- `0x18000907c`
- `0x18000dec8`
- `0x18001f160`
- `0x18001f208`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001f23d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001f23d`

## string_xrefs

- `0x18001f252`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Graphics::Capture::Server::GetClientProcessId(
        Windows::Graphics::Capture::Server *this,
        unsigned int *a2)
{
  int ClientProcessHandle; // eax
  unsigned int v4; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  DWORD ProcessId; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE Process; // [rsp+38h] [rbp+10h] BYREF

  Process = 0;
  ClientProcessHandle = Windows::Graphics::Capture::Server::GetClientProcessHandle(&Process);
  v4 = ClientProcessHandle;
  if ( ClientProcessHandle >= 0 )
  {
    ProcessId = GetProcessId(Process);
    if ( ProcessId )
    {
      *(_DWORD *)this = ProcessId;
      v4 = 0;
      goto LABEL_7;
    }
    v4 = -2147467259;
    v5 = 2147500037LL;
    v6 = 47;
  }
  else
  {
    v5 = (unsigned int)ClientProcessHandle;
    v6 = 40;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
    (const char *)v5,
    v9);
LABEL_7:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Process);
  return v4;
}

```

## disassembly

```asm
0x18001f208  mov     [rsp+arg_0], rbx
0x18001f20d  push    rdi; int
0x18001f20e  sub     rsp, 20h
0x18001f212  mov     rdi, rcx
0x18001f215  mov     [rsp+28h+Process], 0
0x18001f21e  lea     rcx, [rsp+28h+Process]
0x18001f223  call    ?GetClientProcessHandle@Server@Capture@Graphics@Windows@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Graphics::Capture::Server::GetClientProcessHandle(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x18001f228  mov     ebx, eax
0x18001f22a  test    eax, eax
0x18001f22c  jns     short loc_18001F238
0x18001f22e  mov     r9d, eax
0x18001f231  mov     edx, 28h ; '('
0x18001f236  jmp     short loc_18001F252
0x18001f238  mov     rcx, [rsp+28h+Process]; Process
0x18001f23d  call    cs:__imp_GetProcessId
0x18001f243  test    eax, eax
0x18001f245  jnz     short loc_18001F265
0x18001f247  mov     ebx, 80004005h
0x18001f24c  mov     r9d, ebx; char *
0x18001f24f  lea     edx, [rax+2Fh]; void *
0x18001f252  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001f259  mov     rcx, [rsp+28h]; this
0x18001f25e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f263  jmp     short loc_18001F269
0x18001f265  mov     [rdi], eax
0x18001f267  xor     ebx, ebx
0x18001f269  lea     rcx, [rsp+28h+Process]
0x18001f26e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001f273  mov     eax, ebx
0x18001f275  mov     rbx, [rsp+28h+arg_0]
0x18001f27a  add     rsp, 20h
0x18001f27e  pop     rdi
0x18001f27f  retn
```
