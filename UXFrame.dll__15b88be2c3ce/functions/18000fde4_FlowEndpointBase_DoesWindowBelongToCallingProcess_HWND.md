# FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)

- ea: `0x18000fde4`
- end: `0x18000fedf`
- name: `?DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z`
- size: `251`
- prototype: `bool(FlowEndpointBase *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180013e04`

## callees

- `0x180002b20`
- `0x18000e1a4`
- `0x18000f340`
- `0x18000fde4`
- `0x18005a010`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x18000fe89`
- `USER32!GetWindowThreadProcessId` at `0x18000fe89`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x18000fe5d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x18000fe5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fe29`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000fe1b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000fe1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fe9c`

## string_xrefs

- `0x18000fe14`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall FlowEndpointBase::DoesWindowBelongToCallingProcess(FlowEndpointBase *this, HWND a2)
{
  FARPROC ProcAddress; // rax
  HMODULE LibraryW; // rax
  char *v6; // rax
  DWORD ProcessIdOfThread; // eax
  DWORD v8; // ebx
  bool v9; // bl
  FlowEndpointBase *v10; // rcx
  char *v12; // [rsp+20h] [rbp-28h] BYREF
  DWORD dwProcessId; // [rsp+28h] [rbp-20h] BYREF

  ProcAddress = (FARPROC)`FlowEndpointBase::DoesWindowBelongToCallingProcess'::`2'::pfnGetSendMessageThread;
  if ( `FlowEndpointBase::DoesWindowBelongToCallingProcess'::`2'::pfnGetSendMessageThread
    || (LibraryW = LoadLibraryW(L"user32.dll"),
        ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0xAFF),
        (`FlowEndpointBase::DoesWindowBelongToCallingProcess'::`2'::pfnGetSendMessageThread = (__int64)ProcAddress) != 0) )
  {
    v6 = (char *)((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(2048, 0);
    v12 = v6;
    if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( GetLastError() == 5 && FlowEndpointBase::AreRunningLowIl(v10) )
      {
        v9 = 1;
        goto LABEL_13;
      }
    }
    else
    {
      ProcessIdOfThread = GetProcessIdOfThread(v6);
      v8 = ProcessIdOfThread;
      if ( a2 == *((HWND *)this + 5) && *((_DWORD *)this + 12) )
      {
        v9 = ProcessIdOfThread == *((_DWORD *)this + 12);
LABEL_13:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v12);
        LOBYTE(ProcAddress) = v9;
        return (char)ProcAddress;
      }
      dwProcessId = 0;
      if ( GetWindowThreadProcessId(a2, &dwProcessId) )
      {
        v9 = v8 == dwProcessId;
        goto LABEL_13;
      }
    }
    v9 = 0;
    goto LABEL_13;
  }
  return (char)ProcAddress;
}

```

## disassembly

```asm
0x18000fde4  mov     [rsp+arg_0], rbx
0x18000fde9  mov     [rsp+arg_10], rsi
0x18000fdee  push    rdi
0x18000fdef  sub     rsp, 40h
0x18000fdf3  mov     rax, cs:__security_cookie
0x18000fdfa  xor     rax, rsp
0x18000fdfd  mov     [rsp+48h+var_18], rax
0x18000fe02  mov     rsi, rdx
0x18000fe05  mov     rdi, rcx
0x18000fe08  mov     rax, cs:?pfnGetSendMessageThread@?1??DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z@4P6APEAXKH@ZEA; void * (*`FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)'::`2'::pfnGetSendMessageThread)(ulong,int)
0x18000fe0f  test    rax, rax
0x18000fe12  jnz     short loc_18000FE3F
0x18000fe14  lea     rcx, aUser32Dll_0; "user32.dll"
0x18000fe1b  call    cs:__imp_LoadLibraryW
0x18000fe21  mov     edx, 0AFFh; lpProcName
0x18000fe26  mov     rcx, rax; hModule
0x18000fe29  call    cs:__imp_GetProcAddress
0x18000fe2f  mov     cs:?pfnGetSendMessageThread@?1??DoesWindowBelongToCallingProcess@FlowEndpointBase@@IEAA_NPEAUHWND__@@@Z@4P6APEAXKH@ZEA, rax; void * (*`FlowEndpointBase::DoesWindowBelongToCallingProcess(HWND__ *)'::`2'::pfnGetSendMessageThread)(ulong,int)
0x18000fe36  test    rax, rax
0x18000fe39  jz      loc_18000FEC2
0x18000fe3f  xor     edx, edx
0x18000fe41  mov     ecx, 800h
0x18000fe46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe4b  mov     [rsp+48h+var_28], rax
0x18000fe50  lea     rcx, [rax-1]
0x18000fe54  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000fe58  ja      short loc_18000FE9C
0x18000fe5a  mov     rcx, rax; Thread
0x18000fe5d  call    cs:__imp_GetProcessIdOfThread
0x18000fe63  mov     ebx, eax
0x18000fe65  cmp     rsi, [rdi+28h]
0x18000fe69  jnz     short loc_18000FE79
0x18000fe6b  cmp     dword ptr [rdi+30h], 0
0x18000fe6f  jz      short loc_18000FE79
0x18000fe71  cmp     eax, [rdi+30h]
0x18000fe74  setz    bl
0x18000fe77  jmp     short loc_18000FEB6
0x18000fe79  mov     [rsp+48h+dwProcessId], 0
0x18000fe81  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x18000fe86  mov     rcx, rsi; hWnd
0x18000fe89  call    cs:__imp_GetWindowThreadProcessId
0x18000fe8f  test    eax, eax
0x18000fe91  jz      short loc_18000FEB4
0x18000fe93  cmp     ebx, [rsp+48h+dwProcessId]
0x18000fe97  setz    bl
0x18000fe9a  jmp     short loc_18000FEB6
0x18000fe9c  call    cs:__imp_GetLastError
0x18000fea2  cmp     eax, 5
0x18000fea5  jnz     short loc_18000FEB4
0x18000fea7  call    ?AreRunningLowIl@FlowEndpointBase@@IEAA_NXZ; FlowEndpointBase::AreRunningLowIl(void)
0x18000feac  test    al, al
0x18000feae  jz      short loc_18000FEB4
0x18000feb0  mov     bl, 1
0x18000feb2  jmp     short loc_18000FEB6
0x18000feb4  xor     bl, bl
0x18000feb6  lea     rcx, [rsp+48h+var_28]
0x18000febb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000fec0  mov     al, bl
0x18000fec2  mov     rcx, [rsp+48h+var_18]
0x18000fec7  xor     rcx, rsp; StackCookie
0x18000feca  call    __security_check_cookie
0x18000fecf  mov     rbx, [rsp+48h+arg_0]
0x18000fed4  mov     rsi, [rsp+48h+arg_10]
0x18000fed9  add     rsp, 40h
0x18000fedd  pop     rdi
0x18000fede  retn
```
