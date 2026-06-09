# CommonUtil::HrControlService(SC_HANDLE__ *,ulong,_SERVICE_STATUS *)

- ea: `0x140015e60`
- end: `0x140016064`
- name: `?HrControlService@CommonUtil@@YAJPEAUSC_HANDLE__@@KPEAU_SERVICE_STATUS@@@Z`
- size: `516`
- prototype: `__int64 __fastcall(SC_HANDLE hService, struct SC_HANDLE__ *this, LPSERVICE_STATUS lpServiceStatus, struct _SERVICE_STATUS *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140016538`
- `0x1400f5998`
- `0x1400f60dc`

## callees

- `0x140015e60`
- `0x140016b34`
- `0x140017334`
- `0x140017738`
- `0x14003a5c0`
- `0x1400934f8`
- `0x1400f5934`
- `0x140166990`

## import_xrefs

- `ADVAPI32!ControlService` at `0x140015ec0`
- `ADVAPI32!ControlService` at `0x140015ec0`
- `ADVAPI32!QueryServiceConfigW` at `0x140015f44`
- `ADVAPI32!QueryServiceConfigW` at `0x140015ff7`
- `ADVAPI32!QueryServiceConfigW` at `0x140015f44`
- `ADVAPI32!QueryServiceConfigW` at `0x140015ff7`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrControlService(
        SC_HANDLE hService,
        struct SC_HANDLE__ *this,
        LPSERVICE_STATUS lpServiceStatus,
        struct _SERVICE_STATUS *a4)
{
  LPSERVICE_STATUS v4; // rdi
  unsigned int v5; // r14d
  unsigned int v7; // edx
  unsigned int LastFailure; // ebx
  unsigned int v9; // edx
  const wchar_t *v11; // rbx
  const wchar_t *v12; // r9
  struct _QUERY_SERVICE_CONFIGW ServiceConfig[8]; // [rsp+50h] [rbp-B0h] BYREF
  DWORD pcbBytesNeeded; // [rsp+250h] [rbp+150h] BYREF
  __int128 v15; // [rsp+258h] [rbp+158h] BYREF
  __int64 v16; // [rsp+268h] [rbp+168h]
  int v17; // [rsp+270h] [rbp+170h]

  v4 = (LPSERVICE_STATUS)&v15;
  v16 = 0;
  v17 = 0;
  if ( lpServiceStatus )
    v4 = lpServiceStatus;
  v5 = (unsigned int)this;
  v15 = 0;
  if ( ControlService(hService, (DWORD)this, v4) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v11 = CommonUtil::ServiceControlToString((CommonUtil *)v5, v7);
      memset(ServiceConfig, 0, sizeof(ServiceConfig));
      pcbBytesNeeded = 0;
      if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
      {
        LODWORD(v12) = ServiceConfig[0].lpDisplayName;
      }
      else
      {
        HrGetLastFailure();
        v12 = L"<unknown>";
        ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
      }
      WPP_SF_SS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        17,
        (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
        (_DWORD)v12,
        (__int64)v11);
    }
    return 0;
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      CommonUtil::ServiceStateToString((CommonUtil *)v4->dwCurrentState, WPP_GLOBAL_Control);
      CommonUtil::ServiceControlToString((CommonUtil *)v5, v9);
      memset(ServiceConfig, 0, sizeof(ServiceConfig));
      pcbBytesNeeded = 0;
      if ( !QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
      {
        HrGetLastFailure();
        ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
      }
      WPP_SF_SSdSLL(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids);
    }
    return LastFailure;
  }
}

```

## disassembly

```asm
0x140015e60  mov     [rsp-8+arg_18], rbx
0x140015e65  push    rbp
0x140015e66  push    rsi
0x140015e67  push    rdi
0x140015e68  push    r12
0x140015e6a  push    r13
0x140015e6c  push    r14
0x140015e6e  push    r15
0x140015e70  lea     rbp, [rsp-180h]
0x140015e78  sub     rsp, 280h
0x140015e7f  mov     rax, cs:__security_cookie
0x140015e86  xor     rax, rsp
0x140015e89  mov     [rbp+1B0h+var_38], rax
0x140015e90  xor     eax, eax
0x140015e92  lea     rdi, [rbp+1B0h+var_58]
0x140015e99  test    r8, r8
0x140015e9c  mov     [rbp+1B0h+var_48], rax
0x140015ea3  xorps   xmm0, xmm0
0x140015ea6  mov     [rbp+1B0h+var_40], eax
0x140015eac  cmovnz  rdi, r8
0x140015eb0  mov     r14d, edx
0x140015eb3  mov     r8, rdi; lpServiceStatus
0x140015eb6  mov     rsi, rcx
0x140015eb9  movups  [rbp+1B0h+var_58], xmm0
0x140015ec0  call    cs:__imp_ControlService
0x140015ec6  test    eax, eax
0x140015ec8  jnz     loc_140015F9F
0x140015ece  call    HrGetLastFailure
0x140015ed3  mov     ebx, eax
0x140015ed5  mov     rdx, cs:WPP_GLOBAL_Control; unsigned int
0x140015edc  lea     rcx, WPP_GLOBAL_Control
0x140015ee3  cmp     rdx, rcx
0x140015ee6  jz      loc_140015F98
0x140015eec  test    byte ptr [rdx+1Ch], 1
0x140015ef0  jz      loc_140015F98
0x140015ef6  mov     ecx, [rdi+4]; this
0x140015ef9  mov     r15d, [rdi+14h]
0x140015efd  mov     r12d, [rdi+8]
0x140015f01  call    ?ServiceStateToString@CommonUtil@@YAPEB_WK@Z; CommonUtil::ServiceStateToString(ulong)
0x140015f06  mov     ecx, r14d; this
0x140015f09  mov     r13, rax
0x140015f0c  call    ?ServiceControlToString@CommonUtil@@YAPEB_WK@Z; CommonUtil::ServiceControlToString(ulong)
0x140015f11  mov     edi, 200h
0x140015f16  lea     rcx, [rsp+2B0h+ServiceConfig]; void *
0x140015f1b  mov     r8d, edi; Size
0x140015f1e  xor     edx, edx; Val
0x140015f20  mov     r14, rax
0x140015f23  call    memset
0x140015f28  lea     r9, [rbp+1B0h+pcbBytesNeeded]; pcbBytesNeeded
0x140015f2f  mov     [rbp+1B0h+pcbBytesNeeded], 0
0x140015f39  mov     r8d, edi; cbBufSize
0x140015f3c  lea     rdx, [rsp+2B0h+ServiceConfig]; lpServiceConfig
0x140015f41  mov     rcx, rsi; hService
0x140015f44  call    cs:__imp_QueryServiceConfigW
0x140015f4a  test    eax, eax
0x140015f4c  jnz     short loc_140015F60
0x140015f4e  call    HrGetLastFailure
0x140015f53  lea     r9, aUnknown_1; "<unknown>"
0x140015f5a  mov     [rbp+1B0h+ServiceConfig.lpDisplayName], r9
0x140015f5e  jmp     short loc_140015F64
0x140015f60  mov     r9, [rbp+1B0h+ServiceConfig.lpDisplayName]
0x140015f64  mov     rcx, cs:WPP_GLOBAL_Control
0x140015f6b  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140015f72  mov     [rsp+2B0h+var_270], r15d
0x140015f77  mov     edx, 10h
0x140015f7c  mov     [rsp+2B0h+var_278], r12d
0x140015f81  mov     [rsp+2B0h+var_280], r13
0x140015f86  mov     rcx, [rcx+10h]
0x140015f8a  mov     [rsp+2B0h+var_288], ebx
0x140015f8e  mov     [rsp+2B0h+var_290], r14
0x140015f93  call    WPP_SF_SSdSLL
0x140015f98  mov     eax, ebx
0x140015f9a  jmp     loc_14001603A
0x140015f9f  mov     rax, cs:WPP_GLOBAL_Control
0x140015fa6  lea     rcx, WPP_GLOBAL_Control
0x140015fad  cmp     rax, rcx
0x140015fb0  jz      loc_140016038
0x140015fb6  test    byte ptr [rax+1Ch], 4
0x140015fba  jz      short loc_140016038
0x140015fbc  mov     ecx, r14d; this
0x140015fbf  call    ?ServiceControlToString@CommonUtil@@YAPEB_WK@Z; CommonUtil::ServiceControlToString(ulong)
0x140015fc4  mov     edi, 200h
0x140015fc9  lea     rcx, [rsp+2B0h+ServiceConfig]; void *
0x140015fce  mov     r8d, edi; Size
0x140015fd1  xor     edx, edx; Val
0x140015fd3  mov     rbx, rax
0x140015fd6  call    memset
0x140015fdb  lea     r9, [rbp+1B0h+pcbBytesNeeded]; pcbBytesNeeded
0x140015fe2  mov     [rbp+1B0h+pcbBytesNeeded], 0
0x140015fec  mov     r8d, edi; cbBufSize
0x140015fef  lea     rdx, [rsp+2B0h+ServiceConfig]; lpServiceConfig
0x140015ff4  mov     rcx, rsi; hService
0x140015ff7  call    cs:__imp_QueryServiceConfigW
0x140015ffd  test    eax, eax
0x140015fff  jnz     short loc_140016013
0x140016001  call    HrGetLastFailure
0x140016006  lea     r9, aUnknown_1; "<unknown>"
0x14001600d  mov     [rbp+1B0h+ServiceConfig.lpDisplayName], r9
0x140016011  jmp     short loc_140016017
0x140016013  mov     r9, [rbp+1B0h+ServiceConfig.lpDisplayName]
0x140016017  mov     rcx, cs:WPP_GLOBAL_Control
0x14001601e  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016025  mov     edx, 11h
0x14001602a  mov     [rsp+2B0h+var_290], rbx
0x14001602f  mov     rcx, [rcx+10h]
0x140016033  call    WPP_SF_SS
0x140016038  xor     eax, eax
0x14001603a  mov     rcx, [rbp+1B0h+var_38]
0x140016041  xor     rcx, rsp; StackCookie
0x140016044  call    __security_check_cookie
0x140016049  mov     rbx, [rsp+2B0h+arg_18]
0x140016051  add     rsp, 280h
0x140016058  pop     r15
0x14001605a  pop     r14
0x14001605c  pop     r13
0x14001605e  pop     r12
0x140016060  pop     rdi
0x140016061  pop     rsi
0x140016062  pop     rbp
0x140016063  retn
```
