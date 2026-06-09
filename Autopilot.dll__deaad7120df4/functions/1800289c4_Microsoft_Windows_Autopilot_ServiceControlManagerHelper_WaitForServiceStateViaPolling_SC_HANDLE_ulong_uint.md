# Microsoft::Windows::Autopilot::ServiceControlManagerHelper::WaitForServiceStateViaPolling(SC_HANDLE__ *,ulong,uint)

- ea: `0x1800289c4`
- end: `0x180028a6f`
- name: `?WaitForServiceStateViaPolling@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@KI@Z`
- size: `171`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800286f4`

## callees

- `0x180010764`
- `0x180028624`
- `0x1800289c4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028a0a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028a0a`

## string_xrefs

- `0x180028a22`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x180028a48`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::ServiceControlManagerHelper::WaitForServiceStateViaPolling(
        SC_HANDLE a1)
{
  int v1; // ebx
  int ServiceState; // eax
  unsigned int v4; // edi
  struct _SERVICE_STATUS_PROCESS v6; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  memset(&v6, 0, sizeof(v6));
  v1 = 0;
  while ( 1 )
  {
    ServiceState = Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(a1, &v6);
    v4 = ServiceState;
    if ( ServiceState < 0 )
      break;
    if ( v6.dwCurrentState == 4 )
      return 0;
    Sleep(0x3E8u);
    if ( (unsigned int)++v1 >= 0x3C )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
        (const char *)0x800705B4LL);
      return 2147943860LL;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5D,
    (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
    (const char *)(unsigned int)ServiceState);
  return v4;
}

```

## disassembly

```asm
0x1800289c4  mov     [rsp+arg_0], rbx
0x1800289c9  mov     [rsp+arg_8], rsi
0x1800289ce  push    rdi
0x1800289cf  sub     rsp, 50h
0x1800289d3  xorps   xmm0, xmm0
0x1800289d6  xor     eax, eax
0x1800289d8  movups  xmmword ptr [rsp+58h+var_38.dwServiceType], xmm0; int
0x1800289dd  mov     [rsp+58h+var_38.dwServiceFlags], eax
0x1800289e1  xor     ebx, ebx
0x1800289e3  movups  xmmword ptr [rsp+58h+var_38.dwServiceSpecificExitCode], xmm0
0x1800289e8  mov     rsi, rcx
0x1800289eb  lea     rdx, [rsp+58h+var_38]; struct _SERVICE_STATUS_PROCESS *
0x1800289f0  mov     rcx, rsi; struct SC_HANDLE__ *
0x1800289f3  call    ?GetServiceStateEx@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@PEAU_SERVICE_STATUS_PROCESS@@@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS *)
0x1800289f8  mov     edi, eax
0x1800289fa  test    eax, eax
0x1800289fc  js      short loc_180028A43
0x1800289fe  cmp     [rsp+58h+var_38.dwCurrentState], 4
0x180028a03  jz      short loc_180028A3F
0x180028a05  mov     ecx, 3E8h; dwMilliseconds
0x180028a0a  call    cs:__imp_Sleep
0x180028a11  nop     dword ptr [rax+rax+00h]
0x180028a16  inc     ebx
0x180028a18  cmp     ebx, 3Ch ; '<'
0x180028a1b  jb      short loc_1800289EB
0x180028a1d  mov     rcx, [rsp+58h]; this
0x180028a22  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028a29  mov     ebx, 800705B4h
0x180028a2e  mov     edx, 6Bh ; 'k'; void *
0x180028a33  mov     r9d, ebx; char *
0x180028a36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a3b  mov     eax, ebx
0x180028a3d  jmp     short loc_180028A5E
0x180028a3f  xor     eax, eax
0x180028a41  jmp     short loc_180028A5E
0x180028a43  mov     rcx, [rsp+58h]; this
0x180028a48  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028a4f  mov     r9d, edi; char *
0x180028a52  mov     edx, 5Dh ; ']'; void *
0x180028a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a5c  mov     eax, edi
0x180028a5e  mov     rbx, [rsp+58h+arg_0]
0x180028a63  mov     rsi, [rsp+58h+arg_8]
0x180028a68  add     rsp, 50h
0x180028a6c  pop     rdi
0x180028a6d  retn
```
