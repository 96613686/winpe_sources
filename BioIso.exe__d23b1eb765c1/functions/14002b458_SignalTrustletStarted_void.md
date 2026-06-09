# SignalTrustletStarted(void)

- ea: `0x14002b458`
- end: `0x14002b4d1`
- name: `?SignalTrustletStarted@@YAJXZ`
- size: `121`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002bc98`

## callees

- `0x14002826c`
- `0x14002aa74`
- `0x14002b458`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14002b46a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14002b46a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002b492`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002b492`

## string_xrefs

- `0x14002b4ac`: `onecore\ds\security\biometrics\service\trustlet\exe\main.cpp`
- `0x14002b460`: `Global\BioIsoServiceReadyEvent_9AEB5736_E826_4EFE_ABD5_8BDED2257629`

## pseudocode

```c
__int64 SignalTrustletStarted(void)
{
  HANDLE v0; // rax
  const char *v1; // r9
  __int64 v2; // rdx
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HANDLE v6; // [rsp+30h] [rbp+8h] BYREF

  v0 = OpenEventW(2u, 0, L"Global\\BioIsoServiceReadyEvent_9AEB5736_E826_4EFE_ABD5_8BDED2257629");
  v6 = v0;
  if ( (((unsigned __int64)v0 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( SetEvent(v0) )
    {
      LastError = 0;
      goto LABEL_7;
    }
    v2 = 199;
  }
  else
  {
    v2 = 195;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v2,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\main.cpp",
                v1);
LABEL_7:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v6);
  return LastError;
}

```

## disassembly

```asm
0x14002b458  push    rbx
0x14002b45a  sub     rsp, 20h
0x14002b45e  xor     edx, edx; bInheritHandle
0x14002b460  lea     r8, Name; "Global\\BioIsoServiceReadyEvent_9AEB573"...
0x14002b467  lea     ecx, [rdx+2]; dwDesiredAccess
0x14002b46a  call    cs:__imp_OpenEventW
0x14002b471  nop     dword ptr [rax+rax+00h]
0x14002b476  mov     [rsp+28h+arg_0], rax
0x14002b47b  lea     rcx, [rax+1]
0x14002b47f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14002b486  jnz     short loc_14002B48F
0x14002b488  mov     edx, 0C3h
0x14002b48d  jmp     short loc_14002B4A7
0x14002b48f  mov     rcx, rax; hEvent
0x14002b492  call    cs:__imp_SetEvent
0x14002b499  nop     dword ptr [rax+rax+00h]
0x14002b49e  test    eax, eax
0x14002b4a0  jnz     short loc_14002B4BC
0x14002b4a2  mov     edx, 0C7h; void *
0x14002b4a7  mov     rcx, [rsp+28h]; this
0x14002b4ac  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\biometrics\\serv"...
0x14002b4b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14002b4b8  mov     ebx, eax
0x14002b4ba  jmp     short loc_14002B4BE
0x14002b4bc  xor     ebx, ebx
0x14002b4be  lea     rcx, [rsp+28h+arg_0]
0x14002b4c3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002b4c8  mov     eax, ebx
0x14002b4ca  add     rsp, 20h
0x14002b4ce  pop     rbx
0x14002b4cf  retn
```
