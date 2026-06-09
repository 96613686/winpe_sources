# ServiceHandler

- ea: `0x180026210`
- end: `0x180026296`
- name: `ServiceHandler`
- size: `134`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180003ab0`
- `0x180010f1c`
- `0x180026074`
- `0x180026210`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002625f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002625f`

## string_xrefs

- `0x18002626e`: `onecoreuap\windows\directx\dxg\common\servicehelpers\host.cpp`

## pseudocode

```c
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD v4; // ecx
  DWORD v5; // ecx
  const char *v7; // r9
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  v4 = dwControl - 1;
  if ( !v4 )
  {
LABEL_5:
    ServiceStatus.dwServiceType = 16;
    *(_QWORD *)&ServiceStatus.dwCurrentState = 3;
    if ( !SetServiceStatus(g::StatusHandle, &ServiceStatus) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\windows\\directx\\dxg\\common\\servicehelpers\\host.cpp",
        v7);
    dxg::svc::Host::ShutdownService();
    return 0;
  }
  v5 = v4 - 3;
  if ( v5 )
  {
    if ( v5 != 1 )
      return 120;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180026210  sub     rsp, 58h
0x180026214  mov     rax, cs:__security_cookie
0x18002621b  xor     rax, rsp
0x18002621e  mov     [rsp+58h+var_18], rax
0x180026223  xorps   xmm0, xmm0
0x180026226  movdqu  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002622c  sub     ecx, 1
0x18002622f  jz      short loc_180026242
0x180026231  sub     ecx, 3
0x180026234  jz      short loc_180026282
0x180026236  cmp     ecx, 1
0x180026239  jz      short loc_180026242
0x18002623b  mov     eax, 78h ; 'x'
0x180026240  jmp     short loc_180026284
0x180026242  mov     rcx, cs:?StatusHandle@g@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180026249  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002624e  mov     [rsp+58h+ServiceStatus.dwServiceType], 10h
0x180026256  mov     qword ptr [rsp+58h+ServiceStatus.dwCurrentState], 3
0x18002625f  call    cs:__imp_SetServiceStatus
0x180026265  test    eax, eax
0x180026267  jnz     short loc_18002627D
0x180026269  mov     rcx, [rsp+58h]; this
0x18002626e  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\directx\\dxg\\comm"...
0x180026275  lea     edx, [rax+25h]; void *
0x180026278  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002627d  call    ?ShutdownService@Host@svc@dxg@@SAXXZ; dxg::svc::Host::ShutdownService(void)
0x180026282  xor     eax, eax
0x180026284  mov     rcx, [rsp+58h+var_18]
0x180026289  xor     rcx, rsp; StackCookie
0x18002628c  call    __security_check_cookie
0x180026291  add     rsp, 58h
0x180026295  retn
```
