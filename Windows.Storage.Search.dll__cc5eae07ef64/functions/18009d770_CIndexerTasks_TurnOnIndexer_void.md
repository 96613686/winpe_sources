# CIndexerTasks::TurnOnIndexer(void)

- ea: `0x18009d770`
- end: `0x18009d875`
- name: `?TurnOnIndexer@CIndexerTasks@@UEAAJXZ`
- size: `261`
- prototype: `__int64 __fastcall(CIndexerTasks *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x18006c6bc`
- `0x18009d770`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d854`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d85d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d854`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18009d85d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009d787`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18009d787`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009d7b4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18009d7b4`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009d83c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18009d83c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18009d81f`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18009d81f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall CIndexerTasks::TurnOnIndexer(CIndexerTasks *this)
{
  SC_HANDLE v1; // rsi
  int Error; // ebx
  SC_HANDLE v3; // rdi

  v1 = OpenSCManagerW(0, 0, 1u);
  if ( v1 || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v3 = OpenServiceW(v1, L"wsearch", 0x12u);
    if ( v3 || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( ChangeServiceConfigW(v3, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        if ( StartServiceW(v3, 0, 0) )
          Error = 0;
        else
          Error = ResultFromKnownLastError();
      }
      CloseServiceHandle(v3);
    }
    CloseServiceHandle(v1);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18009d770  mov     [rsp+arg_0], rbx
0x18009d775  mov     [rsp+arg_8], rsi
0x18009d77a  push    rdi
0x18009d77b  sub     rsp, 60h
0x18009d77f  xor     edx, edx; lpDatabaseName
0x18009d781  xor     ecx, ecx; lpMachineName
0x18009d783  lea     r8d, [rdx+1]; dwDesiredAccess
0x18009d787  call    cs:__imp_OpenSCManagerW
0x18009d78d  mov     rsi, rax
0x18009d790  test    rax, rax
0x18009d793  jnz     short loc_18009D7A4
0x18009d795  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18009d79a  mov     ebx, eax
0x18009d79c  test    eax, eax
0x18009d79e  js      loc_18009D863
0x18009d7a4  mov     r8d, 12h; dwDesiredAccess
0x18009d7aa  lea     rdx, ServiceName; "wsearch"
0x18009d7b1  mov     rcx, rsi; hSCManager
0x18009d7b4  call    cs:__imp_OpenServiceW
0x18009d7ba  mov     rdi, rax
0x18009d7bd  test    rax, rax
0x18009d7c0  jnz     short loc_18009D7D1
0x18009d7c2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18009d7c7  mov     ebx, eax
0x18009d7c9  test    eax, eax
0x18009d7cb  js      loc_18009D85A
0x18009d7d1  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18009d7da  or      edx, 0FFFFFFFFh; dwServiceType
0x18009d7dd  mov     [rsp+68h+lpPassword], 0; lpPassword
0x18009d7e6  mov     r9d, edx; dwErrorControl
0x18009d7e9  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x18009d7f2  mov     r8d, 2; dwStartType
0x18009d7f8  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x18009d801  mov     rcx, rdi; hService
0x18009d804  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18009d80d  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18009d816  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18009d81f  call    cs:__imp_ChangeServiceConfigW
0x18009d825  test    eax, eax
0x18009d827  jnz     short loc_18009D834
0x18009d829  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18009d82e  mov     ebx, eax
0x18009d830  test    eax, eax
0x18009d832  js      short loc_18009D851
0x18009d834  xor     r8d, r8d; lpServiceArgVectors
0x18009d837  xor     edx, edx; dwNumServiceArgs
0x18009d839  mov     rcx, rdi; hService
0x18009d83c  call    cs:__imp_StartServiceW
0x18009d842  test    eax, eax
0x18009d844  jz      short loc_18009D84A
0x18009d846  xor     ebx, ebx
0x18009d848  jmp     short loc_18009D851
0x18009d84a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18009d84f  mov     ebx, eax
0x18009d851  mov     rcx, rdi; hSCObject
0x18009d854  call    cs:__imp_CloseServiceHandle
0x18009d85a  mov     rcx, rsi; hSCObject
0x18009d85d  call    cs:__imp_CloseServiceHandle
0x18009d863  mov     rsi, [rsp+68h+arg_8]
0x18009d868  mov     eax, ebx
0x18009d86a  mov     rbx, [rsp+68h+arg_0]
0x18009d86f  add     rsp, 60h
0x18009d873  pop     rdi
0x18009d874  retn
```
