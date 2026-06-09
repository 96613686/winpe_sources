# CDriverLayerImpl::StartDriver(void)

- ea: `0x18000f5c0`
- end: `0x18000f89e`
- name: `?StartDriver@CDriverLayerImpl@@AEAAJXZ`
- size: `734`
- prototype: `__int64 __fastcall(CDriverLayerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000f8a4`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000f5c0`
- `0x18000fae8`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f72f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f63f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f72f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f7f7`
- `ADVAPI32!OpenSCManagerW` at `0x18000f631`
- `ADVAPI32!OpenSCManagerW` at `0x18000f631`
- `ADVAPI32!OpenServiceW` at `0x18000f692`
- `ADVAPI32!OpenServiceW` at `0x18000f692`
- `ADVAPI32!CloseServiceHandle` at `0x18000f6ef`
- `ADVAPI32!CloseServiceHandle` at `0x18000f835`
- `ADVAPI32!CloseServiceHandle` at `0x18000f83e`
- `ADVAPI32!CloseServiceHandle` at `0x18000f6ef`
- `ADVAPI32!CloseServiceHandle` at `0x18000f835`
- `ADVAPI32!CloseServiceHandle` at `0x18000f83e`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000f725`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000f725`
- `ADVAPI32!StartServiceW` at `0x18000f7ed`
- `ADVAPI32!StartServiceW` at `0x18000f7ed`

## pseudocode

```c
__int64 __fastcall CDriverLayerImpl::StartDriver(CDriverLayerImpl *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rsi
  signed int LastError; // eax
  unsigned int v5; // ebx
  CHostedCacheMsgEncoding *v6; // rcx
  __int64 v7; // rdx
  SC_HANDLE v8; // r14
  signed int v9; // eax
  CDriverLayerImpl *v10; // rcx
  signed int v11; // eax
  CHostedCacheMsgEncoding *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  signed int v16; // eax
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-49h]
  unsigned int v19; // [rsp+28h] [rbp-41h]
  DWORD v20[4]; // [rsp+30h] [rbp-39h] BYREF
  struct _SERVICE_STATUS_PROCESS v21; // [rsp+40h] [rbp-29h] BYREF
  struct _SERVICE_STATUS_PROCESS Buffer; // [rsp+70h] [rbp+7h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids);
  }
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v7 = 27;
LABEL_50:
      WPP_SF_d(*((_QWORD *)v6 + 12), v7, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  v8 = OpenServiceW(v2, L"PeerDistKM", 0x14u);
  if ( !v8 )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v5 = 0;
    if ( v9 != -2147023836 )
      v5 = v9;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 28, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, v5);
    }
    CloseServiceHandle(v3);
    return v5;
  }
  v20[0] = 0;
  memset(&Buffer, 0, sizeof(Buffer));
  if ( QueryServiceStatusEx(v8, SC_STATUS_PROCESS_INFO, (LPBYTE)&Buffer, 0x24u, v20) )
  {
    v5 = 0;
    if ( Buffer.dwCurrentState == 4 )
      goto LABEL_45;
    if ( Buffer.dwCurrentState == 3 )
    {
      v21 = Buffer;
      v15 = CDriverLayerImpl::WaitForServiceStatus(v10, v8, &v21, 3u, pcbBytesNeeded, v19);
      v5 = v15;
      if ( v15 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v13 = 30;
          v14 = (unsigned int)v15;
          goto LABEL_30;
        }
        goto LABEL_46;
      }
    }
    if ( StartServiceW(v8, 0, 0) )
    {
LABEL_45:
      *((_BYTE *)this + 56) = 1;
      goto LABEL_46;
    }
    v16 = GetLastError();
    v5 = v16;
    if ( v16 > 0 )
      v5 = (unsigned __int16)v16 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v13 = 31;
      goto LABEL_29;
    }
  }
  else
  {
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v13 = 29;
LABEL_29:
      v14 = v5;
LABEL_30:
      WPP_SF_d(*((_QWORD *)v12 + 12), v13, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, v14);
    }
  }
LABEL_46:
  CloseServiceHandle(v8);
  CloseServiceHandle(v3);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    v7 = 32;
    goto LABEL_50;
  }
  return v5;
}

```

## disassembly

```asm
0x18000f5c0  mov     [rsp-8+arg_8], rbx
0x18000f5c5  mov     [rsp-8+arg_10], rsi
0x18000f5ca  push    rbp
0x18000f5cb  push    rdi
0x18000f5cc  push    r12
0x18000f5ce  push    r13
0x18000f5d0  push    r14
0x18000f5d2  lea     rbp, [rsp-37h]
0x18000f5d7  sub     rsp, 0A0h
0x18000f5de  mov     rax, cs:__security_cookie
0x18000f5e5  xor     rax, rsp
0x18000f5e8  mov     [rbp+57h+var_28], rax
0x18000f5ec  mov     rdi, rcx
0x18000f5ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5f6  lea     r13, WPP_GLOBAL_Control
0x18000f5fd  mov     r12d, 800h
0x18000f603  cmp     rcx, r13
0x18000f606  jz      short loc_18000F629
0x18000f608  test    [rcx+6Ch], r12d
0x18000f60c  jz      short loc_18000F629
0x18000f60e  cmp     byte ptr [rcx+69h], 4
0x18000f612  jb      short loc_18000F629
0x18000f614  mov     rcx, [rcx+60h]
0x18000f618  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000f61f  mov     edx, 1Ah
0x18000f624  call    WPP_SF_
0x18000f629  xor     edx, edx; lpDatabaseName
0x18000f62b  xor     ecx, ecx; lpMachineName
0x18000f62d  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000f631  call    cs:__imp_OpenSCManagerW
0x18000f637  mov     rsi, rax
0x18000f63a  test    rax, rax
0x18000f63d  jnz     short loc_18000F682
0x18000f63f  call    cs:__imp_GetLastError
0x18000f645  mov     ebx, eax
0x18000f647  test    eax, eax
0x18000f649  jle     short loc_18000F654
0x18000f64b  movzx   ebx, ax
0x18000f64e  or      ebx, 80070000h
0x18000f654  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f65b  cmp     rcx, r13
0x18000f65e  jz      loc_18000F874
0x18000f664  test    [rcx+6Ch], r12d
0x18000f668  jz      loc_18000F874
0x18000f66e  cmp     byte ptr [rcx+69h], 1
0x18000f672  jb      loc_18000F874
0x18000f678  mov     edx, 1Bh
0x18000f67d  jmp     loc_18000F861
0x18000f682  mov     r8d, 14h; dwDesiredAccess
0x18000f688  lea     rdx, ServiceName; "PeerDistKM"
0x18000f68f  mov     rcx, rsi; hSCManager
0x18000f692  call    cs:__imp_OpenServiceW
0x18000f698  mov     r14, rax
0x18000f69b  test    rax, rax
0x18000f69e  jnz     short loc_18000F6FA
0x18000f6a0  call    cs:__imp_GetLastError
0x18000f6a6  test    eax, eax
0x18000f6a8  jle     short loc_18000F6B2
0x18000f6aa  movzx   eax, ax
0x18000f6ad  or      eax, 80070000h
0x18000f6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6b9  xor     ebx, ebx
0x18000f6bb  cmp     eax, 80070424h
0x18000f6c0  cmovnz  ebx, eax
0x18000f6c3  cmp     rcx, r13
0x18000f6c6  jz      short loc_18000F6EC
0x18000f6c8  test    [rcx+6Ch], r12d
0x18000f6cc  jz      short loc_18000F6EC
0x18000f6ce  cmp     byte ptr [rcx+69h], 1
0x18000f6d2  jb      short loc_18000F6EC
0x18000f6d4  mov     rcx, [rcx+60h]
0x18000f6d8  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000f6df  mov     edx, 1Ch
0x18000f6e4  mov     r9d, ebx
0x18000f6e7  call    WPP_SF_d
0x18000f6ec  mov     rcx, rsi; hSCObject
0x18000f6ef  call    cs:__imp_CloseServiceHandle
0x18000f6f5  jmp     loc_18000F874
0x18000f6fa  xor     eax, eax
0x18000f6fc  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18000f700  xorps   xmm0, xmm0
0x18000f703  mov     [rbp+57h+var_30], eax
0x18000f706  mov     [rbp+57h+var_90], eax
0x18000f709  mov     r9d, 24h ; '$'; cbBufSize
0x18000f70f  lea     rax, [rbp+57h+var_90]
0x18000f713  xor     edx, edx; InfoLevel
0x18000f715  mov     rcx, r14; hService
0x18000f718  mov     [rsp+0C0h+pcbBytesNeeded], rax; unsigned int
0x18000f71d  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18000f721  movups  [rbp+57h+var_40], xmm0
0x18000f725  call    cs:__imp_QueryServiceStatusEx
0x18000f72b  test    eax, eax
0x18000f72d  jnz     short loc_18000F785
0x18000f72f  call    cs:__imp_GetLastError
0x18000f735  mov     ebx, eax
0x18000f737  test    eax, eax
0x18000f739  jle     short loc_18000F744
0x18000f73b  movzx   ebx, ax
0x18000f73e  or      ebx, 80070000h
0x18000f744  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f74b  cmp     rcx, r13
0x18000f74e  jz      loc_18000F832
0x18000f754  test    [rcx+6Ch], r12d
0x18000f758  jz      loc_18000F832
0x18000f75e  cmp     byte ptr [rcx+69h], 1
0x18000f762  jb      loc_18000F832
0x18000f768  mov     edx, 1Dh
0x18000f76d  mov     r9d, ebx
0x18000f770  mov     rcx, [rcx+60h]
0x18000f774  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000f77b  call    WPP_SF_d
0x18000f780  jmp     loc_18000F832
0x18000f785  xor     ebx, ebx
0x18000f787  cmp     dword ptr [rbp+57h+Buffer+4], 4
0x18000f78b  jz      loc_18000F82E
0x18000f791  lea     r9d, [rbx+3]; unsigned int
0x18000f795  cmp     dword ptr [rbp+57h+Buffer+4], r9d
0x18000f799  jnz     short loc_18000F7E5
0x18000f79b  movups  xmm0, xmmword ptr [rbp+57h+Buffer]
0x18000f79f  mov     eax, [rbp+57h+var_30]
0x18000f7a2  lea     r8, [rbp+57h+var_80]; struct _SERVICE_STATUS_PROCESS
0x18000f7a6  movups  xmm1, [rbp+57h+var_40]
0x18000f7aa  mov     rdx, r14; struct SC_HANDLE__ *
0x18000f7ad  mov     [rbp+57h+var_80.dwServiceFlags], eax
0x18000f7b0  movaps  xmmword ptr [rbp+57h+var_80.dwServiceType], xmm0
0x18000f7b4  movaps  xmmword ptr [rbp+57h+var_80.dwServiceSpecificExitCode], xmm1
0x18000f7b8  call    ?WaitForServiceStatus@CDriverLayerImpl@@AEAAJQEAUSC_HANDLE__@@U_SERVICE_STATUS_PROCESS@@KKK@Z; CDriverLayerImpl::WaitForServiceStatus(SC_HANDLE__ * const,_SERVICE_STATUS_PROCESS,ulong,ulong,ulong)
0x18000f7bd  mov     ebx, eax
0x18000f7bf  test    eax, eax
0x18000f7c1  jns     short loc_18000F7E5
0x18000f7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7ca  cmp     rcx, r13
0x18000f7cd  jz      short loc_18000F832
0x18000f7cf  test    [rcx+6Ch], r12d
0x18000f7d3  jz      short loc_18000F832
0x18000f7d5  cmp     byte ptr [rcx+69h], 1
0x18000f7d9  jb      short loc_18000F832
0x18000f7db  mov     edx, 1Eh
0x18000f7e0  mov     r9d, eax
0x18000f7e3  jmp     short loc_18000F770
0x18000f7e5  xor     r8d, r8d; lpServiceArgVectors
0x18000f7e8  xor     edx, edx; dwNumServiceArgs
0x18000f7ea  mov     rcx, r14; hService
0x18000f7ed  call    cs:__imp_StartServiceW
0x18000f7f3  test    eax, eax
0x18000f7f5  jnz     short loc_18000F82E
0x18000f7f7  call    cs:__imp_GetLastError
0x18000f7fd  mov     ebx, eax
0x18000f7ff  test    eax, eax
0x18000f801  jle     short loc_18000F80C
0x18000f803  movzx   ebx, ax
0x18000f806  or      ebx, 80070000h
0x18000f80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f813  cmp     rcx, r13
0x18000f816  jz      short loc_18000F832
0x18000f818  test    [rcx+6Ch], r12d
0x18000f81c  jz      short loc_18000F832
0x18000f81e  cmp     byte ptr [rcx+69h], 1
0x18000f822  jb      short loc_18000F832
0x18000f824  mov     edx, 1Fh
0x18000f829  jmp     loc_18000F76D
0x18000f82e  mov     byte ptr [rdi+38h], 1
0x18000f832  mov     rcx, r14; hSCObject
0x18000f835  call    cs:__imp_CloseServiceHandle
0x18000f83b  mov     rcx, rsi; hSCObject
0x18000f83e  call    cs:__imp_CloseServiceHandle
0x18000f844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f84b  cmp     rcx, r13
0x18000f84e  jz      short loc_18000F874
0x18000f850  test    [rcx+6Ch], r12d
0x18000f854  jz      short loc_18000F874
0x18000f856  cmp     byte ptr [rcx+69h], 4
0x18000f85a  jb      short loc_18000F874
0x18000f85c  mov     edx, 20h ; ' '
0x18000f861  mov     rcx, [rcx+60h]
0x18000f865  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000f86c  mov     r9d, ebx
0x18000f86f  call    WPP_SF_d
0x18000f874  mov     eax, ebx
0x18000f876  mov     rcx, [rbp+57h+var_28]
0x18000f87a  xor     rcx, rsp; StackCookie
0x18000f87d  call    __security_check_cookie
0x18000f882  lea     r11, [rsp+0C0h+var_20]
0x18000f88a  mov     rbx, [r11+38h]
0x18000f88e  mov     rsi, [r11+40h]
0x18000f892  mov     rsp, r11
0x18000f895  pop     r14
0x18000f897  pop     r13
0x18000f899  pop     r12
0x18000f89b  pop     rdi
0x18000f89c  pop     rbp
0x18000f89d  retn
```
