# ServiceStopCallback(void *,uchar)

- ea: `0x180025f90`
- end: `0x18002603b`
- name: `?ServiceStopCallback@@YAXPEAXE@Z`
- size: `171`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ab0`
- `0x180010f1c`
- `0x18001bfb0`
- `0x180025f90`
- `0x180031010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002600b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002600b`

## string_xrefs

- `0x180025fd1`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`
- `0x18002601a`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`

## pseudocode

```c
void __fastcall ServiceStopCallback(void *a1)
{
  HANDLE v1; // rcx
  __int64 (__fastcall *v2)(HANDLE); // rax
  unsigned int v3; // eax
  const char *v4; // r9
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = g::ServiceThreadPoolWaitHandle;
  v2 = (__int64 (__fastcall *)(HANDLE))*((_QWORD *)g::ServiceHostSharedGlobals + 27);
  g::ServiceThreadPoolWaitHandle = 0;
  v3 = v2(v1);
  if ( v3 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
      (const char *)v3,
      ServiceStatus.dwServiceType);
  ServiceStatus.dwServiceType = 16;
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 1;
  if ( !SetServiceStatus(g::StatusHandle, &ServiceStatus) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
      v4);
}

```

## disassembly

```asm
0x180025f90  sub     rsp, 58h
0x180025f94  mov     rax, cs:__security_cookie
0x180025f9b  xor     rax, rsp
0x180025f9e  mov     [rsp+58h+var_18], rax
0x180025fa3  mov     rax, cs:?ServiceHostSharedGlobals@g@@3PEAU_SVCHOST_GLOBAL_DATA_EX_V1@@EA; _SVCHOST_GLOBAL_DATA_EX_V1 * g::ServiceHostSharedGlobals
0x180025faa  mov     rcx, cs:?ServiceThreadPoolWaitHandle@g@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>> g::ServiceThreadPoolWaitHandle
0x180025fb1  mov     rax, [rax+0D8h]
0x180025fb8  mov     cs:?ServiceThreadPoolWaitHandle@g@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>> g::ServiceThreadPoolWaitHandle
0x180025fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fc8  test    eax, eax
0x180025fca  jz      short loc_180025FE5
0x180025fcc  mov     rcx, [rsp+58h]; this
0x180025fd1  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180025fd8  mov     r9d, eax; char *
0x180025fdb  mov     edx, 34h ; '4'; void *
0x180025fe0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180025fe5  mov     rcx, cs:?StatusHandle@g@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180025fec  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180025ff1  xorps   xmm0, xmm0
0x180025ff4  mov     [rsp+58h+ServiceStatus.dwServiceType], 10h
0x180025ffc  movdqu  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180026002  mov     qword ptr [rsp+58h+ServiceStatus.dwCurrentState], 1
0x18002600b  call    cs:__imp_SetServiceStatus
0x180026011  test    eax, eax
0x180026013  jnz     short loc_180026029
0x180026015  mov     rcx, [rsp+58h]; this
0x18002601a  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180026021  lea     edx, [rax+3Ah]; void *
0x180026024  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180026029  mov     rcx, [rsp+58h+var_18]
0x18002602e  xor     rcx, rsp; StackCookie
0x180026031  call    __security_check_cookie
0x180026036  add     rsp, 58h
0x18002603a  retn
```
