# FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)

- ea: `0x18002dc40`
- end: `0x18002ddf9`
- name: `?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z`
- size: `441`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct SC_HANDLE__ **, struct SC_HANDLE__ **, unsigned int, DWORD dwDesiredAccess, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002e5ac`
- `0x18002ebe4`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002db3c`
- `0x18002dc40`
- `0x18003d510`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002dcc7`
- `KERNEL32!GetLastError` at `0x18002dd22`
- `KERNEL32!GetLastError` at `0x18002dd77`
- `KERNEL32!GetLastError` at `0x18002dcc7`
- `KERNEL32!GetLastError` at `0x18002dd22`
- `KERNEL32!GetLastError` at `0x18002dd77`
- `ADVAPI32!QueryServiceStatus` at `0x18002dd67`
- `ADVAPI32!QueryServiceStatus` at `0x18002dd67`
- `ADVAPI32!OpenSCManagerW` at `0x18002dcb1`
- `ADVAPI32!OpenSCManagerW` at `0x18002dcb1`
- `ADVAPI32!OpenServiceW` at `0x18002dd0e`
- `ADVAPI32!OpenServiceW` at `0x18002dd0e`

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
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rsi
  SC_HANDLE v11; // rdi
  DWORD LastError; // eax
  DWORD v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  SC_HANDLE v16; // rax
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v9 = OpenSCManagerW(0, 0, 1u);
  v10 = v9;
  if ( v9 )
  {
    v16 = OpenServiceW(v9, L"Fax", dwDesiredAccess);
    v11 = v16;
    if ( v16 )
    {
      if ( a7 )
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !QueryServiceStatus(v16, &ServiceStatus) )
        {
          LastError = GetLastError();
          v13 = LastError;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = 13;
            goto LABEL_21;
          }
          goto LABEL_22;
        }
        *a7 = ServiceStatus.dwCurrentState;
      }
      *a3 = v10;
      v13 = 0;
      *a4 = v11;
      return v13;
    }
    LastError = GetLastError();
    v13 = LastError;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 12;
      goto LABEL_21;
    }
  }
  else
  {
    v11 = 0;
    LastError = GetLastError();
    v13 = LastError;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 11;
LABEL_21:
      WPP_SF_d(v14[2], v15, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    }
  }
LABEL_22:
  if ( v13 )
    FaxCloseService(v10, v11);
  return v13;
}

```

## disassembly

```asm
0x18002dc40  mov     [rsp+arg_0], rbx
0x18002dc45  push    rsi
0x18002dc46  push    rdi
0x18002dc47  push    r12
0x18002dc49  push    r14
0x18002dc4b  push    r15
0x18002dc4d  sub     rsp, 50h
0x18002dc51  mov     rax, cs:__security_cookie
0x18002dc58  xor     rax, rsp
0x18002dc5b  mov     [rsp+78h+var_38], rax
0x18002dc60  mov     edi, [rsp+78h+dwDesiredAccess]
0x18002dc67  mov     r15, r9
0x18002dc6a  mov     rbx, [rsp+78h+arg_30]
0x18002dc72  mov     r14, r8
0x18002dc75  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc7c  lea     r12, WPP_GLOBAL_Control
0x18002dc83  cmp     rcx, r12
0x18002dc86  jz      short loc_18002DCA9
0x18002dc88  test    byte ptr [rcx+1Ch], 2
0x18002dc8c  jz      short loc_18002DCA9
0x18002dc8e  cmp     byte ptr [rcx+19h], 5
0x18002dc92  jb      short loc_18002DCA9
0x18002dc94  mov     rcx, [rcx+10h]
0x18002dc98  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002dc9f  mov     edx, 0Ah
0x18002dca4  call    WPP_SF_
0x18002dca9  xor     edx, edx; lpDatabaseName
0x18002dcab  xor     ecx, ecx; lpMachineName
0x18002dcad  lea     r8d, [rdx+1]; dwDesiredAccess
0x18002dcb1  call    cs:__imp_OpenSCManagerW
0x18002dcb8  nop     dword ptr [rax+rax+00h]
0x18002dcbd  mov     rsi, rax
0x18002dcc0  test    rax, rax
0x18002dcc3  jnz     short loc_18002DD01
0x18002dcc5  xor     edi, edi
0x18002dcc7  call    cs:__imp_GetLastError
0x18002dcce  nop     dword ptr [rax+rax+00h]
0x18002dcd3  mov     ebx, eax
0x18002dcd5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcdc  cmp     rcx, r12
0x18002dcdf  jz      loc_18002DDB5
0x18002dce5  test    byte ptr [rcx+1Ch], 2
0x18002dce9  jz      loc_18002DDB5
0x18002dcef  cmp     byte ptr [rcx+19h], 2
0x18002dcf3  jb      loc_18002DDB5
0x18002dcf9  lea     edx, [rsi+0Bh]
0x18002dcfc  jmp     loc_18002DDA2
0x18002dd01  mov     r8d, edi; dwDesiredAccess
0x18002dd04  lea     rdx, ServiceName; "Fax"
0x18002dd0b  mov     rcx, rsi; hSCManager
0x18002dd0e  call    cs:__imp_OpenServiceW
0x18002dd15  nop     dword ptr [rax+rax+00h]
0x18002dd1a  mov     rdi, rax
0x18002dd1d  test    rax, rax
0x18002dd20  jnz     short loc_18002DD4D
0x18002dd22  call    cs:__imp_GetLastError
0x18002dd29  nop     dword ptr [rax+rax+00h]
0x18002dd2e  mov     ebx, eax
0x18002dd30  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd37  cmp     rcx, r12
0x18002dd3a  jz      short loc_18002DDB5
0x18002dd3c  test    byte ptr [rcx+1Ch], 2
0x18002dd40  jz      short loc_18002DDB5
0x18002dd42  cmp     byte ptr [rcx+19h], 2
0x18002dd46  jb      short loc_18002DDB5
0x18002dd48  lea     edx, [rdi+0Ch]
0x18002dd4b  jmp     short loc_18002DDA2
0x18002dd4d  test    rbx, rbx
0x18002dd50  jz      short loc_18002DDCC
0x18002dd52  xorps   xmm0, xmm0
0x18002dd55  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18002dd5a  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18002dd5f  mov     rcx, rdi; hService
0x18002dd62  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002dd67  call    cs:__imp_QueryServiceStatus
0x18002dd6e  nop     dword ptr [rax+rax+00h]
0x18002dd73  test    eax, eax
0x18002dd75  jnz     short loc_18002DDC6
0x18002dd77  call    cs:__imp_GetLastError
0x18002dd7e  nop     dword ptr [rax+rax+00h]
0x18002dd83  mov     ebx, eax
0x18002dd85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd8c  cmp     rcx, r12
0x18002dd8f  jz      short loc_18002DDB5
0x18002dd91  test    byte ptr [rcx+1Ch], 2
0x18002dd95  jz      short loc_18002DDB5
0x18002dd97  cmp     byte ptr [rcx+19h], 2
0x18002dd9b  jb      short loc_18002DDB5
0x18002dd9d  mov     edx, 0Dh
0x18002dda2  mov     rcx, [rcx+10h]
0x18002dda6  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002ddad  mov     r9d, eax
0x18002ddb0  call    WPP_SF_d
0x18002ddb5  test    ebx, ebx
0x18002ddb7  jz      short loc_18002DDD4
0x18002ddb9  mov     rdx, rdi; SC_HANDLE
0x18002ddbc  mov     rcx, rsi; hSCObject
0x18002ddbf  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x18002ddc4  jmp     short loc_18002DDD4
0x18002ddc6  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x18002ddca  mov     [rbx], eax
0x18002ddcc  mov     [r14], rsi
0x18002ddcf  xor     ebx, ebx
0x18002ddd1  mov     [r15], rdi
0x18002ddd4  mov     eax, ebx
0x18002ddd6  mov     rcx, [rsp+78h+var_38]
0x18002dddb  xor     rcx, rsp; StackCookie
0x18002ddde  call    __security_check_cookie
0x18002dde3  mov     rbx, [rsp+78h+arg_0]
0x18002ddeb  add     rsp, 50h
0x18002ddef  pop     r15
0x18002ddf1  pop     r14
0x18002ddf3  pop     r12
0x18002ddf5  pop     rdi
0x18002ddf6  pop     rsi
0x18002ddf7  retn
```
