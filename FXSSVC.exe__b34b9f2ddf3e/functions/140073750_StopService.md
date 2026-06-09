# StopService

- ea: `0x140073750`
- end: `0x140073a97`
- name: `StopService`
- size: `839`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x140039350`
- `0x140073750`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004e68`
- `0x140065d14`
- `0x140065dbc`
- `0x140072518`
- `0x140072604`
- `0x140072798`
- `0x140073750`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!ControlService` at `0x1400739e5`
- `ADVAPI32!ControlService` at `0x1400739e5`
- `ADVAPI32!EnumDependentServicesW` at `0x14007386a`
- `ADVAPI32!EnumDependentServicesW` at `0x14007395f`
- `ADVAPI32!EnumDependentServicesW` at `0x14007386a`
- `ADVAPI32!EnumDependentServicesW` at `0x14007395f`
- `KERNEL32!GetLastError` at `0x140073878`
- `KERNEL32!GetLastError` at `0x140073912`
- `KERNEL32!GetLastError` at `0x140073994`
- `KERNEL32!GetLastError` at `0x140073a0e`
- `KERNEL32!GetLastError` at `0x140073878`
- `KERNEL32!GetLastError` at `0x140073912`
- `KERNEL32!GetLastError` at `0x140073994`
- `KERNEL32!GetLastError` at `0x140073a0e`
- `KERNEL32!SetLastError` at `0x140073a53`
- `KERNEL32!SetLastError` at `0x140073a53`

## pseudocode

```c
__int64 __fastcall StopService(__int64 a1, const unsigned __int16 *a2, int a3, unsigned int a4)
{
  unsigned int v4; // edi
  struct _ENUM_SERVICE_STATUSW *v8; // r15
  const unsigned __int16 *v9; // rcx
  DWORD v10; // eax
  SC_HANDLE v11; // rsi
  DWORD v12; // eax
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  DWORD v15; // eax
  __int64 v16; // rbx
  int v17; // edx
  DWORD LastError; // eax
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-60h]
  DWORD cbBufSize; // [rsp+40h] [rbp-40h] BYREF
  SC_HANDLE hService; // [rsp+48h] [rbp-38h] BYREF
  SC_HANDLE hSCObject; // [rsp+50h] [rbp-30h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+58h] [rbp-28h] BYREF

  v4 = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  hSCObject = 0;
  hService = 0;
  v8 = 0;
  v9 = (const unsigned __int16 *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v10 = FaxOpenService(v9, a2, &hSCObject, &hService, pcbBytesNeeded, 0x2Cu, &ServiceStatus.dwCurrentState);
  v11 = hService;
  if ( v10 )
    goto LABEL_41;
  if ( ServiceStatus.dwCurrentState == 1 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_db036311db36307996a98c23702218b2_Traceguids);
    }
    goto LABEL_11;
  }
  if ( !a3 )
  {
LABEL_34:
    if ( !ControlService(v11, 1u, &ServiceStatus) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      }
      goto LABEL_42;
    }
    if ( !a4 || (v10 = WaitForServiceStopOrStart(v11, v17, a4)) == 0 )
    {
LABEL_11:
      v4 = 1;
      goto LABEL_42;
    }
LABEL_41:
    SetLastError(v10);
    goto LABEL_42;
  }
  LODWORD(hService) = 0;
  cbBufSize = 0;
  if ( !EnumDependentServicesW(v11, 1u, 0, 0, &cbBufSize, (LPDWORD)&hService) )
  {
    v12 = GetLastError();
    if ( v12 != 234 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v14 = 34;
LABEL_19:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_db036311db36307996a98c23702218b2_Traceguids, v12);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
    if ( !cbBufSize )
      goto LABEL_34;
    v8 = (struct _ENUM_SERVICE_STATUSW *)pMemAlloc(cbBufSize);
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v15 = GetLastError();
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_db036311db36307996a98c23702218b2_Traceguids,
          cbBufSize,
          v15);
      }
      goto LABEL_42;
    }
  }
  if ( EnumDependentServicesW(v11, 1u, v8, cbBufSize, &cbBufSize, (LPDWORD)&hService) )
  {
    v16 = 0;
    if ( (_DWORD)hService )
    {
      while ( (unsigned int)StopService(0, v8[v16].lpServiceName, 0) )
      {
        v16 = (unsigned int)(v16 + 1);
        if ( (unsigned int)v16 >= (unsigned int)hService )
          goto LABEL_34;
      }
      goto LABEL_42;
    }
    goto LABEL_34;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v12 = GetLastError();
    v13 = WPP_GLOBAL_Control;
    v14 = 36;
    goto LABEL_19;
  }
LABEL_42:
  pMemFree(v8);
  FaxCloseService(hSCObject, v11);
  return v4;
}

```

## disassembly

```asm
0x140073750  mov     [rsp-28h+arg_0], rbx
0x140073755  mov     [rsp-28h+arg_10], rsi
0x14007375a  push    rbp
0x14007375b  push    rdi
0x14007375c  push    r13
0x14007375e  push    r14
0x140073760  push    r15
0x140073762  mov     rbp, rsp
0x140073765  sub     rsp, 80h
0x14007376c  mov     rax, cs:__security_cookie
0x140073773  xor     rax, rsp
0x140073776  mov     [rbp+var_8], rax
0x14007377a  xor     edi, edi
0x14007377c  xorps   xmm0, xmm0
0x14007377f  movups  xmmword ptr [rbp+ServiceStatus.dwServiceType], xmm0
0x140073783  mov     r14d, r9d
0x140073786  mov     ebx, r8d
0x140073789  movups  xmmword ptr [rbp+ServiceStatus.dwWin32ExitCode], xmm0
0x14007378d  mov     rsi, rdx
0x140073790  mov     [rbp+hSCObject], rdi
0x140073794  mov     [rbp+hService], rdi
0x140073798  xor     r15d, r15d
0x14007379b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400737a2  lea     rax, WPP_GLOBAL_Control
0x1400737a9  cmp     rcx, rax
0x1400737ac  jz      short loc_1400737CD
0x1400737ae  test    byte ptr [rcx+1Ch], 2
0x1400737b2  jz      short loc_1400737CD
0x1400737b4  cmp     byte ptr [rcx+19h], 5
0x1400737b8  jb      short loc_1400737CD
0x1400737ba  mov     rcx, [rcx+10h]
0x1400737be  lea     edx, [rdi+20h]
0x1400737c1  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400737c8  call    WPP_SF_
0x1400737cd  lea     rax, [rbp+ServiceStatus.dwCurrentState]
0x1400737d1  mov     rdx, rsi; unsigned __int16 *
0x1400737d4  mov     [rsp+80h+var_50], rax; unsigned int *
0x1400737d9  lea     r9, [rbp+hService]; struct SC_HANDLE__ **
0x1400737dd  lea     r8, [rbp+hSCObject]; struct SC_HANDLE__ **
0x1400737e1  mov     dword ptr [rsp+80h+lpServicesReturned], 2Ch ; ','; unsigned int
0x1400737e9  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x1400737ee  mov     rsi, [rbp+hService]
0x1400737f2  test    eax, eax
0x1400737f4  jnz     loc_140073A51
0x1400737fa  lea     r13d, [rax+1]
0x1400737fe  cmp     [rbp+ServiceStatus.dwCurrentState], r13d
0x140073802  jnz     short loc_14007383E
0x140073804  mov     rcx, cs:WPP_GLOBAL_Control
0x14007380b  lea     rdx, WPP_GLOBAL_Control
0x140073812  cmp     rcx, rdx
0x140073815  jz      short loc_140073836
0x140073817  test    byte ptr [rcx+1Ch], 2
0x14007381b  jz      short loc_140073836
0x14007381d  cmp     byte ptr [rcx+19h], 5
0x140073821  jb      short loc_140073836
0x140073823  mov     rcx, [rcx+10h]
0x140073827  lea     edx, [rax+21h]
0x14007382a  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140073831  call    WPP_SF_
0x140073836  mov     edi, r13d
0x140073839  jmp     loc_140073A59
0x14007383e  test    ebx, ebx
0x140073840  jz      loc_1400739DB
0x140073846  lea     rax, [rbp+hService]
0x14007384a  mov     dword ptr [rbp+hService], edi
0x14007384d  mov     [rsp+80h+lpServicesReturned], rax; lpServicesReturned
0x140073852  xor     r9d, r9d; cbBufSize
0x140073855  lea     rax, [rbp+cbBufSize]
0x140073859  mov     [rbp+cbBufSize], edi
0x14007385c  xor     r8d, r8d; lpServices
0x14007385f  mov     [rsp+80h+pcbBytesNeeded], rax; pcbBytesNeeded
0x140073864  mov     edx, r13d; dwServiceState
0x140073867  mov     rcx, rsi; hService
0x14007386a  call    cs:__imp_EnumDependentServicesW
0x140073870  test    eax, eax
0x140073872  jnz     loc_140073940
0x140073878  call    cs:__imp_GetLastError
0x14007387e  cmp     eax, 0EAh
0x140073883  jz      short loc_1400738CD
0x140073885  mov     rcx, cs:WPP_GLOBAL_Control
0x14007388c  lea     rdx, WPP_GLOBAL_Control
0x140073893  cmp     rcx, rdx
0x140073896  jz      loc_140073A59
0x14007389c  test    byte ptr [rcx+1Ch], 2
0x1400738a0  jz      loc_140073A59
0x1400738a6  cmp     byte ptr [rcx+19h], 5
0x1400738aa  jb      loc_140073A59
0x1400738b0  mov     edx, 22h ; '"'
0x1400738b5  mov     rcx, [rcx+10h]
0x1400738b9  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400738c0  mov     r9d, eax
0x1400738c3  call    WPP_SF_d
0x1400738c8  jmp     loc_140073A59
0x1400738cd  mov     eax, [rbp+cbBufSize]
0x1400738d0  test    eax, eax
0x1400738d2  jz      loc_1400739DB
0x1400738d8  mov     ecx, eax; dwBytes
0x1400738da  call    pMemAlloc
0x1400738df  mov     r15, rax
0x1400738e2  test    rax, rax
0x1400738e5  jnz     short loc_140073940
0x1400738e7  mov     rax, cs:WPP_GLOBAL_Control
0x1400738ee  lea     rdx, WPP_GLOBAL_Control
0x1400738f5  cmp     rax, rdx
0x1400738f8  jz      loc_140073A59
0x1400738fe  test    byte ptr [rax+1Ch], 2
0x140073902  jz      loc_140073A59
0x140073908  cmp     byte ptr [rax+19h], 5
0x14007390c  jb      loc_140073A59
0x140073912  call    cs:__imp_GetLastError
0x140073918  mov     rcx, cs:WPP_GLOBAL_Control
0x14007391f  lea     edx, [r15+23h]
0x140073923  mov     r9d, [rbp+cbBufSize]
0x140073927  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x14007392e  mov     dword ptr [rsp+80h+pcbBytesNeeded], eax
0x140073932  mov     rcx, [rcx+10h]
0x140073936  call    WPP_SF_dd
0x14007393b  jmp     loc_140073A59
0x140073940  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x140073944  lea     rax, [rbp+hService]
0x140073948  mov     [rsp+80h+lpServicesReturned], rax; lpServicesReturned
0x14007394d  mov     r8, r15; lpServices
0x140073950  lea     rax, [rbp+cbBufSize]
0x140073954  mov     edx, r13d; dwServiceState
0x140073957  mov     rcx, rsi; hService
0x14007395a  mov     [rsp+80h+pcbBytesNeeded], rax; unsigned int
0x14007395f  call    cs:__imp_EnumDependentServicesW
0x140073965  test    eax, eax
0x140073967  jnz     short loc_1400739AB
0x140073969  mov     rax, cs:WPP_GLOBAL_Control
0x140073970  lea     rdx, WPP_GLOBAL_Control
0x140073977  cmp     rax, rdx
0x14007397a  jz      loc_140073A59
0x140073980  test    byte ptr [rax+1Ch], 2
0x140073984  jz      loc_140073A59
0x14007398a  cmp     byte ptr [rax+19h], 5
0x14007398e  jb      loc_140073A59
0x140073994  call    cs:__imp_GetLastError
0x14007399a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400739a1  mov     edx, 24h ; '$'
0x1400739a6  jmp     loc_1400738B5
0x1400739ab  xor     ebx, ebx
0x1400739ad  cmp     dword ptr [rbp+hService], ebx
0x1400739b0  jbe     short loc_1400739DB
0x1400739b2  lea     rdx, [rbx+rbx*2]
0x1400739b6  or      r9d, 0FFFFFFFFh
0x1400739ba  add     rdx, rdx
0x1400739bd  xor     r8d, r8d
0x1400739c0  xor     ecx, ecx
0x1400739c2  mov     rdx, [r15+rdx*8]
0x1400739c6  call    StopService
0x1400739cb  test    eax, eax
0x1400739cd  jz      loc_140073A59
0x1400739d3  add     ebx, r13d
0x1400739d6  cmp     ebx, dword ptr [rbp+hService]
0x1400739d9  jb      short loc_1400739B2
0x1400739db  lea     r8, [rbp+ServiceStatus]; lpServiceStatus
0x1400739df  mov     edx, r13d; dwControl
0x1400739e2  mov     rcx, rsi; hService
0x1400739e5  call    cs:__imp_ControlService
0x1400739eb  test    eax, eax
0x1400739ed  jnz     short loc_140073A35
0x1400739ef  mov     rax, cs:WPP_GLOBAL_Control
0x1400739f6  lea     rdx, WPP_GLOBAL_Control
0x1400739fd  cmp     rax, rdx
0x140073a00  jz      short loc_140073A59
0x140073a02  test    byte ptr [rax+1Ch], 2
0x140073a06  jz      short loc_140073A59
0x140073a08  cmp     byte ptr [rax+19h], 2
0x140073a0c  jb      short loc_140073A59
0x140073a0e  call    cs:__imp_GetLastError
0x140073a14  mov     rcx, cs:WPP_GLOBAL_Control
0x140073a1b  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140073a22  mov     edx, 25h ; '%'
0x140073a27  mov     r9d, eax
0x140073a2a  mov     rcx, [rcx+10h]
0x140073a2e  call    WPP_SF_d
0x140073a33  jmp     short loc_140073A59
0x140073a35  test    r14d, r14d
0x140073a38  jz      loc_140073836
0x140073a3e  mov     r8d, r14d; unsigned int
0x140073a41  mov     rcx, rsi; hService
0x140073a44  call    ?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z; WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)
0x140073a49  test    eax, eax
0x140073a4b  jz      loc_140073836
0x140073a51  mov     ecx, eax; dwErrCode
0x140073a53  call    cs:__imp_SetLastError
0x140073a59  mov     rcx, r15; lpMem
0x140073a5c  call    pMemFree
0x140073a61  mov     rcx, [rbp+hSCObject]; hSCObject
0x140073a65  mov     rdx, rsi; SC_HANDLE
0x140073a68  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x140073a6d  mov     eax, edi
0x140073a6f  mov     rcx, [rbp+var_8]
0x140073a73  xor     rcx, rsp; StackCookie
0x140073a76  call    __security_check_cookie
0x140073a7b  lea     r11, [rsp+80h+var_s0]
0x140073a83  mov     rbx, [r11+30h]
0x140073a87  mov     rsi, [r11+40h]
0x140073a8b  mov     rsp, r11
0x140073a8e  pop     r15
0x140073a90  pop     r14
0x140073a92  pop     r13
0x140073a94  pop     rdi
0x140073a95  pop     rbp
0x140073a96  retn
```
