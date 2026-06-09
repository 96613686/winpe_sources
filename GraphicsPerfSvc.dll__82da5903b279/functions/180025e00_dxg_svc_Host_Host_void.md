# dxg::svc::Host::~Host(void)

- ea: `0x180025e00`
- end: `0x180025eb4`
- name: `??1Host@svc@dxg@@QEAA@XZ`
- size: `180`
- prototype: `void __fastcall(LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011630`
- `0x18002f9b4`

## callees

- `0x180010f1c`
- `0x180010f3c`
- `0x18001bfb0`
- `0x180025e00`
- `0x180031010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025e68`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180025e68`

## string_xrefs

- `0x180025e45`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`
- `0x180025e77`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`
- `0x180025e9c`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`

## pseudocode

```c
void __fastcall dxg::svc::Host::~Host(LPSERVICE_STATUS lpServiceStatus)
{
  __int64 (*v2)(void); // rax
  unsigned int v3; // eax
  const char *v4; // r9
  unsigned int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( lpServiceStatus->dwCurrentState == 2 )
  {
    if ( g::ServiceThreadPoolWaitHandle )
    {
      v2 = (__int64 (*)(void))*((_QWORD *)g::ServiceHostSharedGlobals + 27);
      g::ServiceThreadPoolWaitHandle = 0;
      v3 = v2();
      if ( v3 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x62,
          (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
          (const char *)v3,
          v5);
    }
    *(_QWORD *)&lpServiceStatus->dwCurrentState = 1;
    if ( !SetServiceStatus(g::StatusHandle, lpServiceStatus) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
        v4);
  }
  else if ( lpServiceStatus->dwCurrentState != 4 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
      (const char *)0x8000FFFFLL,
      v5);
  }
}

```

## disassembly

```asm
0x180025e00  push    rbx; int
0x180025e02  sub     rsp, 20h
0x180025e06  mov     rbx, rcx
0x180025e09  cmp     dword ptr [rcx+4], 2
0x180025e0d  jnz     short loc_180025E8B
0x180025e0f  mov     rcx, cs:?ServiceThreadPoolWaitHandle@g@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>> g::ServiceThreadPoolWaitHandle
0x180025e16  test    rcx, rcx
0x180025e19  jz      short loc_180025E56
0x180025e1b  mov     rax, cs:?ServiceHostSharedGlobals@g@@3PEAU_SVCHOST_GLOBAL_DATA_EX_V1@@EA; _SVCHOST_GLOBAL_DATA_EX_V1 * g::ServiceHostSharedGlobals
0x180025e22  mov     rax, [rax+0D8h]
0x180025e29  mov     cs:?ServiceThreadPoolWaitHandle@g@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?UnregisterWait@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&UnregisterWait(void *)>>> g::ServiceThreadPoolWaitHandle
0x180025e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e39  test    eax, eax
0x180025e3b  jz      short loc_180025E56
0x180025e3d  mov     rcx, [rsp+28h]; this
0x180025e42  mov     r9d, eax; char *
0x180025e45  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180025e4c  mov     edx, 62h ; 'b'; void *
0x180025e51  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180025e56  mov     qword ptr [rbx+4], 1
0x180025e5e  mov     rdx, rbx; lpServiceStatus
0x180025e61  mov     rcx, cs:?StatusHandle@g@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180025e68  call    cs:__imp_SetServiceStatus
0x180025e6e  test    eax, eax
0x180025e70  jnz     short loc_180025EAE
0x180025e72  mov     rcx, [rsp+28h]; this
0x180025e77  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180025e7e  lea     edx, [rax+66h]; void *
0x180025e81  add     rsp, 20h
0x180025e85  pop     rbx
0x180025e86  jmp     ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180025e8b  cmp     dword ptr [rcx+4], 4
0x180025e8f  jz      short loc_180025EAE
0x180025e91  mov     rcx, [rsp+28h]; this
0x180025e96  mov     r9d, 8000FFFFh; char *
0x180025e9c  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180025ea3  mov     edx, 6Ah ; 'j'; void *
0x180025ea8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025ead  nop
0x180025eae  add     rsp, 20h
0x180025eb2  pop     rbx
0x180025eb3  retn
```
