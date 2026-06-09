# Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS *)

- ea: `0x1800275d8`
- end: `0x18002766b`
- name: `?GetServiceStateEx@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@PEAU_SERVICE_STATUS_PROCESS@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, struct _SERVICE_STATUS_PROCESS *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002769c`
- `0x180027934`

## callees

- `0x1800045b0`
- `0x1800105d4`
- `0x1800275d8`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002761e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18002761e`

## string_xrefs

- `0x18002762d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`

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
0x1800275d8  push    rbx
0x1800275da  sub     rsp, 70h
0x1800275de  mov     rax, cs:__security_cookie
0x1800275e5  xor     rax, rsp
0x1800275e8  mov     [rsp+78h+var_18], rax
0x1800275ed  xor     eax, eax
0x1800275ef  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x1800275f4  xorps   xmm0, xmm0
0x1800275f7  mov     [rsp+78h+var_20], eax
0x1800275fb  mov     [rsp+78h+var_48], eax
0x1800275ff  mov     rbx, rdx
0x180027602  lea     rax, [rsp+78h+var_48]
0x180027607  mov     r9d, 24h ; '$'; cbBufSize
0x18002760d  xor     edx, edx; InfoLevel
0x18002760f  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180027614  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x180027619  movups  [rsp+78h+var_30], xmm0
0x18002761e  call    cs:__imp_QueryServiceStatusEx
0x180027624  test    eax, eax
0x180027626  jnz     short loc_18002763E
0x180027628  mov     rcx, [rsp+78h]; this
0x18002762d  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027634  lea     edx, [rax+50h]; void *
0x180027637  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002763c  jmp     short loc_180027658
0x18002763e  mov     eax, [rsp+78h+var_20]
0x180027642  movups  xmm0, xmmword ptr [rsp+78h+Buffer]
0x180027647  movups  xmm1, [rsp+78h+var_30]
0x18002764c  movups  xmmword ptr [rbx], xmm0
0x18002764f  movups  xmmword ptr [rbx+10h], xmm1
0x180027653  mov     [rbx+20h], eax
0x180027656  xor     eax, eax
0x180027658  mov     rcx, [rsp+78h+var_18]
0x18002765d  xor     rcx, rsp; StackCookie
0x180027660  call    __security_check_cookie
0x180027665  add     rsp, 70h
0x180027669  pop     rbx
0x18002766a  retn
```
