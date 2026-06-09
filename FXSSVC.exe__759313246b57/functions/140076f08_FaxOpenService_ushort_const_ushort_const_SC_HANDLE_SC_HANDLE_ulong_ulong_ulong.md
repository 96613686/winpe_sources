# FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)

- ea: `0x140076f08`
- end: `0x1400770b8`
- name: `?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z`
- size: `432`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, struct SC_HANDLE__ **, struct SC_HANDLE__ **, unsigned int, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140077814`
- `0x1400781f0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140076e04`
- `0x140076f08`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!QueryServiceStatus` at `0x14007702c`
- `ADVAPI32!QueryServiceStatus` at `0x14007702c`
- `ADVAPI32!OpenSCManagerW` at `0x140076f7a`
- `ADVAPI32!OpenSCManagerW` at `0x140076f7a`
- `ADVAPI32!OpenServiceW` at `0x140076fd3`
- `ADVAPI32!OpenServiceW` at `0x140076fd3`
- `KERNEL32!GetLastError` at `0x140076f90`
- `KERNEL32!GetLastError` at `0x140076fe7`
- `KERNEL32!GetLastError` at `0x14007703c`
- `KERNEL32!GetLastError` at `0x140076f90`
- `KERNEL32!GetLastError` at `0x140076fe7`
- `KERNEL32!GetLastError` at `0x14007703c`

## pseudocode

```c
__int64 __fastcall FaxOpenService(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct SC_HANDLE__ **a3,
        struct SC_HANDLE__ **a4,
        unsigned int a5,
        DWORD dwDesiredAccess,
        unsigned int *a7)
{
  SC_HANDLE v10; // rax
  SC_HANDLE v11; // rsi
  SC_HANDLE v12; // rdi
  DWORD LastError; // eax
  DWORD v14; // ebx
  CMapDeviceId *v15; // rcx
  __int64 v16; // rdx
  SC_HANDLE v17; // rax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v10 = OpenSCManagerW(0, 0, 1u);
  v11 = v10;
  if ( v10 )
  {
    v17 = OpenServiceW(v10, a2, dwDesiredAccess);
    v12 = v17;
    if ( v17 )
    {
      if ( a7 )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !QueryServiceStatus(v17, &ServiceStatus) )
        {
          LastError = GetLastError();
          v14 = LastError;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = 13;
            goto LABEL_21;
          }
          goto LABEL_22;
        }
        *a7 = ServiceStatus.dwCurrentState;
      }
      *a3 = v11;
      v14 = 0;
      *a4 = v12;
      return v14;
    }
    LastError = GetLastError();
    v14 = LastError;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 12;
      goto LABEL_21;
    }
  }
  else
  {
    v12 = 0;
    LastError = GetLastError();
    v14 = LastError;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = 11;
LABEL_21:
      WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    }
  }
LABEL_22:
  if ( v14 )
    FaxCloseService(v11, v12);
  return v14;
}

```

## disassembly

```asm
0x140076f08  push    rbx
0x140076f0a  push    rbp
0x140076f0b  push    rsi
0x140076f0c  push    rdi
0x140076f0d  push    r13
0x140076f0f  push    r14
0x140076f11  push    r15
0x140076f13  sub     rsp, 50h
0x140076f17  mov     rax, cs:__security_cookie
0x140076f1e  xor     rax, rsp
0x140076f21  mov     [rsp+88h+var_48], rax
0x140076f26  mov     ebp, [rsp+88h+dwDesiredAccess]
0x140076f2d  mov     r15, r9
0x140076f30  mov     rbx, [rsp+88h+arg_30]
0x140076f38  mov     r14, r8
0x140076f3b  mov     rdi, rdx
0x140076f3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140076f45  lea     r13, WPP_GLOBAL_Control
0x140076f4c  cmp     rcx, r13
0x140076f4f  jz      short loc_140076F72
0x140076f51  test    byte ptr [rcx+1Ch], 2
0x140076f55  jz      short loc_140076F72
0x140076f57  cmp     byte ptr [rcx+19h], 5
0x140076f5b  jb      short loc_140076F72
0x140076f5d  mov     rcx, [rcx+10h]
0x140076f61  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140076f68  mov     edx, 0Ah
0x140076f6d  call    WPP_SF_
0x140076f72  xor     edx, edx; lpDatabaseName
0x140076f74  xor     ecx, ecx; lpMachineName
0x140076f76  lea     r8d, [rdx+1]; dwDesiredAccess
0x140076f7a  call    cs:__imp_OpenSCManagerW
0x140076f81  nop     dword ptr [rax+rax+00h]
0x140076f86  mov     rsi, rax
0x140076f89  test    rax, rax
0x140076f8c  jnz     short loc_140076FCA
0x140076f8e  xor     edi, edi
0x140076f90  call    cs:__imp_GetLastError
0x140076f97  nop     dword ptr [rax+rax+00h]
0x140076f9c  mov     ebx, eax
0x140076f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140076fa5  cmp     rcx, r13
0x140076fa8  jz      loc_14007707A
0x140076fae  test    byte ptr [rcx+1Ch], 2
0x140076fb2  jz      loc_14007707A
0x140076fb8  cmp     byte ptr [rcx+19h], 2
0x140076fbc  jb      loc_14007707A
0x140076fc2  lea     edx, [rsi+0Bh]
0x140076fc5  jmp     loc_140077067
0x140076fca  mov     r8d, ebp; dwDesiredAccess
0x140076fcd  mov     rdx, rdi; lpServiceName
0x140076fd0  mov     rcx, rsi; hSCManager
0x140076fd3  call    cs:__imp_OpenServiceW
0x140076fda  nop     dword ptr [rax+rax+00h]
0x140076fdf  mov     rdi, rax
0x140076fe2  test    rax, rax
0x140076fe5  jnz     short loc_140077012
0x140076fe7  call    cs:__imp_GetLastError
0x140076fee  nop     dword ptr [rax+rax+00h]
0x140076ff3  mov     ebx, eax
0x140076ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x140076ffc  cmp     rcx, r13
0x140076fff  jz      short loc_14007707A
0x140077001  test    byte ptr [rcx+1Ch], 2
0x140077005  jz      short loc_14007707A
0x140077007  cmp     byte ptr [rcx+19h], 2
0x14007700b  jb      short loc_14007707A
0x14007700d  lea     edx, [rdi+0Ch]
0x140077010  jmp     short loc_140077067
0x140077012  test    rbx, rbx
0x140077015  jz      short loc_140077091
0x140077017  xorps   xmm0, xmm0
0x14007701a  lea     rdx, [rsp+88h+ServiceStatus]; lpServiceStatus
0x14007701f  movups  xmmword ptr [rsp+88h+ServiceStatus.dwServiceType], xmm0
0x140077024  mov     rcx, rdi; hService
0x140077027  movups  xmmword ptr [rsp+88h+ServiceStatus.dwWin32ExitCode], xmm0
0x14007702c  call    cs:__imp_QueryServiceStatus
0x140077033  nop     dword ptr [rax+rax+00h]
0x140077038  test    eax, eax
0x14007703a  jnz     short loc_14007708B
0x14007703c  call    cs:__imp_GetLastError
0x140077043  nop     dword ptr [rax+rax+00h]
0x140077048  mov     ebx, eax
0x14007704a  mov     rcx, cs:WPP_GLOBAL_Control
0x140077051  cmp     rcx, r13
0x140077054  jz      short loc_14007707A
0x140077056  test    byte ptr [rcx+1Ch], 2
0x14007705a  jz      short loc_14007707A
0x14007705c  cmp     byte ptr [rcx+19h], 2
0x140077060  jb      short loc_14007707A
0x140077062  mov     edx, 0Dh
0x140077067  mov     rcx, [rcx+10h]
0x14007706b  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077072  mov     r9d, eax
0x140077075  call    WPP_SF_d
0x14007707a  test    ebx, ebx
0x14007707c  jz      short loc_140077099
0x14007707e  mov     rdx, rdi; SC_HANDLE
0x140077081  mov     rcx, rsi; hSCObject
0x140077084  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x140077089  jmp     short loc_140077099
0x14007708b  mov     eax, [rsp+88h+ServiceStatus.dwCurrentState]
0x14007708f  mov     [rbx], eax
0x140077091  mov     [r14], rsi
0x140077094  xor     ebx, ebx
0x140077096  mov     [r15], rdi
0x140077099  mov     eax, ebx
0x14007709b  mov     rcx, [rsp+88h+var_48]
0x1400770a0  xor     rcx, rsp; StackCookie
0x1400770a3  call    __security_check_cookie
0x1400770a8  add     rsp, 50h
0x1400770ac  pop     r15
0x1400770ae  pop     r14
0x1400770b0  pop     r13
0x1400770b2  pop     rdi
0x1400770b3  pop     rsi
0x1400770b4  pop     rbp
0x1400770b5  pop     rbx
0x1400770b6  retn
```
