# Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS *)

- ea: `0x180028624`
- end: `0x1800286be`
- name: `?GetServiceStateEx@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@PEAU_SERVICE_STATUS_PROCESS@@@Z`
- size: `154`
- prototype: `__int64 __fastcall(SC_HANDLE, struct _SERVICE_STATUS_PROCESS *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800286f4`
- `0x1800289c4`

## callees

- `0x1800045d0`
- `0x180010744`
- `0x180028624`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002866a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002866a`

## string_xrefs

- `0x18002867f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(
        SC_HANDLE a1,
        struct _SERVICE_STATUS_PROCESS *a2)
{
  const char *v3; // r9
  DWORD v5; // eax
  __int128 v6; // xmm1
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+48h] [rbp-30h]
  DWORD v10; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v10 = 0;
  pcbBytesNeeded = 0;
  *(_OWORD *)Buffer = 0;
  v9 = 0;
  if ( !QueryServiceStatusEx(a1, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x50,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
             v3);
  v5 = v10;
  v6 = v9;
  *(_OWORD *)&a2->dwServiceType = *(_OWORD *)Buffer;
  *(_OWORD *)&a2->dwServiceSpecificExitCode = v6;
  a2->dwServiceFlags = v5;
  return 0;
}

```

## disassembly

```asm
0x180028624  push    rbx
0x180028626  sub     rsp, 70h
0x18002862a  mov     rax, cs:__security_cookie
0x180028631  xor     rax, rsp
0x180028634  mov     [rsp+78h+var_18], rax
0x180028639  xor     eax, eax
0x18002863b  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x180028640  xorps   xmm0, xmm0
0x180028643  mov     [rsp+78h+var_20], eax
0x180028647  mov     [rsp+78h+var_48], eax
0x18002864b  mov     rbx, rdx
0x18002864e  lea     rax, [rsp+78h+var_48]
0x180028653  mov     r9d, 24h ; '$'; cbBufSize
0x180028659  xor     edx, edx; InfoLevel
0x18002865b  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180028660  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180028665  movups  [rsp+78h+var_30], xmm0
0x18002866a  call    cs:__imp_QueryServiceStatusEx
0x180028671  nop     dword ptr [rax+rax+00h]
0x180028676  test    eax, eax
0x180028678  jnz     short loc_180028690
0x18002867a  mov     rcx, [rsp+78h]; this
0x18002867f  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028686  lea     edx, [rax+50h]; void *
0x180028689  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002868e  jmp     short loc_1800286AA
0x180028690  mov     eax, [rsp+78h+var_20]
0x180028694  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x180028699  movups  xmm1, [rsp+78h+var_30]
0x18002869e  movups  xmmword ptr [rbx], xmm0
0x1800286a1  movups  xmmword ptr [rbx+10h], xmm1
0x1800286a5  mov     [rbx+20h], eax
0x1800286a8  xor     eax, eax
0x1800286aa  mov     rcx, [rsp+78h+var_18]
0x1800286af  xor     rcx, rsp; StackCookie
0x1800286b2  call    __security_check_cookie
0x1800286b7  add     rsp, 70h
0x1800286bb  pop     rbx
0x1800286bc  retn
```
