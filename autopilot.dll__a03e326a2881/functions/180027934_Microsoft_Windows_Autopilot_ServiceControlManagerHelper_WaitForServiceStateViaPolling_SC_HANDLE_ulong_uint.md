# Microsoft::Windows::Autopilot::ServiceControlManagerHelper::WaitForServiceStateViaPolling(SC_HANDLE__ *,ulong,uint)

- ea: `0x180027934`
- end: `0x1800279d8`
- name: `?WaitForServiceStateViaPolling@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@KI@Z`
- size: `164`
- prototype: `__int64 __fastcall(struct SC_HANDLE__ *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002769c`

## callees

- `0x1800105f4`
- `0x1800275d8`
- `0x180027934`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002797a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002797a`

## string_xrefs

- `0x18002798c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x1800279b2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`

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
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
        (const char *)0x800705B4LL,
        v6.dwServiceType);
      return 2147943860LL;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5D,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
    (const char *)(unsigned int)ServiceState,
    v6.dwServiceType);
  return v4;
}

```

## disassembly

```asm
0x180027934  mov     [rsp+arg_0], rbx
0x180027939  mov     [rsp+arg_8], rsi
0x18002793e  push    rdi
0x18002793f  sub     rsp, 50h
0x180027943  xorps   xmm0, xmm0
0x180027946  xor     eax, eax
0x180027948  movups  xmmword ptr [rsp+58h+var_38.dwServiceType], xmm0; int
0x18002794d  mov     [rsp+58h+var_38.dwServiceFlags], eax
0x180027951  xor     ebx, ebx
0x180027953  movups  xmmword ptr [rsp+58h+var_38.dwServiceSpecificExitCode], xmm0
0x180027958  mov     rsi, rcx
0x18002795b  lea     rdx, [rsp+58h+var_38]; struct _SERVICE_STATUS_PROCESS *
0x180027960  mov     rcx, rsi; struct SC_HANDLE__ *
0x180027963  call    ?GetServiceStateEx@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@PEAU_SERVICE_STATUS_PROCESS@@@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS *)
0x180027968  mov     edi, eax
0x18002796a  test    eax, eax
0x18002796c  js      short loc_1800279AD
0x18002796e  cmp     [rsp+58h+var_38.dwCurrentState], 4
0x180027973  jz      short loc_1800279A9
0x180027975  mov     ecx, 3E8h; dwMilliseconds
0x18002797a  call    cs:__imp_Sleep
0x180027980  inc     ebx
0x180027982  cmp     ebx, 3Ch ; '<'
0x180027985  jb      short loc_18002795B
0x180027987  mov     rcx, [rsp+58h]; this
0x18002798c  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027993  mov     ebx, 800705B4h
0x180027998  mov     edx, 6Bh ; 'k'; void *
0x18002799d  mov     r9d, ebx; char *
0x1800279a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279a5  mov     eax, ebx
0x1800279a7  jmp     short loc_1800279C8
0x1800279a9  xor     eax, eax
0x1800279ab  jmp     short loc_1800279C8
0x1800279ad  mov     rcx, [rsp+58h]; this
0x1800279b2  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800279b9  mov     r9d, edi; char *
0x1800279bc  mov     edx, 5Dh ; ']'; void *
0x1800279c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800279c6  mov     eax, edi
0x1800279c8  mov     rbx, [rsp+58h+arg_0]
0x1800279cd  mov     rsi, [rsp+58h+arg_8]
0x1800279d2  add     rsp, 50h
0x1800279d6  pop     rdi
0x1800279d7  retn
```
