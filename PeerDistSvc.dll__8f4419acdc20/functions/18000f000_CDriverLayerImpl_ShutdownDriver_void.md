# CDriverLayerImpl::ShutdownDriver(void)

- ea: `0x18000f000`
- end: `0x18000f2ee`
- name: `?ShutdownDriver@CDriverLayerImpl@@AEAAJXZ`
- size: `750`
- prototype: `__int64 __fastcall(CDriverLayerImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000ed50`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000f000`
- `0x18000fae8`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f083`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f213`
- `ADVAPI32!OpenSCManagerW` at `0x18000f075`
- `ADVAPI32!OpenSCManagerW` at `0x18000f075`
- `ADVAPI32!OpenServiceW` at `0x18000f0d8`
- `ADVAPI32!OpenServiceW` at `0x18000f0d8`
- `ADVAPI32!CloseServiceHandle` at `0x18000f135`
- `ADVAPI32!CloseServiceHandle` at `0x18000f291`
- `ADVAPI32!CloseServiceHandle` at `0x18000f29a`
- `ADVAPI32!CloseServiceHandle` at `0x18000f135`
- `ADVAPI32!CloseServiceHandle` at `0x18000f291`
- `ADVAPI32!CloseServiceHandle` at `0x18000f29a`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000f168`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000f168`
- `ADVAPI32!ControlService` at `0x18000f209`
- `ADVAPI32!ControlService` at `0x18000f209`

## pseudocode

```c
__int64 __fastcall CDriverLayerImpl::ShutdownDriver(CDriverLayerImpl *this)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // r14
  signed int LastError; // eax
  unsigned int v6; // ebx
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  SC_HANDLE v9; // rsi
  signed int v10; // eax
  CDriverLayerImpl *v11; // rcx
  signed int v12; // eax
  CHostedCacheMsgEncoding *v13; // rcx
  __int64 v14; // rdx
  unsigned int v15; // r9d
  signed int v16; // eax
  unsigned int pcbBytesNeeded; // [rsp+20h] [rbp-59h]
  unsigned int v18; // [rsp+28h] [rbp-51h]
  DWORD v19[4]; // [rsp+30h] [rbp-49h] BYREF
  _SERVICE_STATUS_PROCESS v20; // [rsp+40h] [rbp-39h] BYREF
  BYTE Buffer[16]; // [rsp+70h] [rbp-9h] BYREF
  __int128 v22; // [rsp+80h] [rbp+7h]
  DWORD v23; // [rsp+90h] [rbp+17h]

  if ( !*((_BYTE *)this + 56) )
    return 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 33, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids);
  }
  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      return v6;
    }
    v8 = 34;
    goto LABEL_48;
  }
  v9 = OpenServiceW(v3, L"PeerDistKM", 0x24u);
  if ( !v9 )
  {
    v10 = GetLastError();
    v6 = v10;
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 35, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, v6);
    }
    CloseServiceHandle(v4);
    return v6;
  }
  v23 = 0;
  v19[0] = 0;
  *(_OWORD *)Buffer = 0;
  v22 = 0;
  if ( !QueryServiceStatusEx(v9, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, v19) )
  {
    v12 = GetLastError();
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_44;
    }
    v14 = 36;
    goto LABEL_29;
  }
  if ( *(_DWORD *)&Buffer[4] != 1 )
  {
    v15 = 3;
    if ( *(_DWORD *)&Buffer[4] == 3 )
    {
      *(_OWORD *)&v20.dwServiceType = *(_OWORD *)Buffer;
      *(_OWORD *)&v20.dwServiceSpecificExitCode = v22;
    }
    else
    {
      if ( !ControlService(v9, 1u, (LPSERVICE_STATUS)Buffer) )
      {
        v16 = GetLastError();
        v6 = v16;
        if ( v16 > 0 )
          v6 = (unsigned __int16)v16 | 0x80070000;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_44;
        }
        v14 = 37;
LABEL_29:
        WPP_SF_d(*((_QWORD *)v13 + 12), v14, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, v6);
        goto LABEL_44;
      }
      *(_OWORD *)&v20.dwServiceType = *(_OWORD *)Buffer;
      v15 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)Buffer, 4));
      *(_OWORD *)&v20.dwServiceSpecificExitCode = v22;
    }
    v20.dwServiceFlags = v23;
    v6 = CDriverLayerImpl::WaitForServiceStatus(v11, v9, &v20, v15, pcbBytesNeeded, v18);
    if ( (v6 & 0x80000000) == 0 )
      *((_BYTE *)this + 56) = 0;
    goto LABEL_44;
  }
  v6 = 0;
  *((_BYTE *)this + 56) = 0;
LABEL_44:
  CloseServiceHandle(v9);
  CloseServiceHandle(v4);
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 105) < 4u )
  {
    return v6;
  }
  v8 = 38;
LABEL_48:
  WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000f000  push    rbp
0x18000f002  push    rbx
0x18000f003  push    rsi
0x18000f004  push    rdi
0x18000f005  push    r13
0x18000f007  push    r14
0x18000f009  lea     rbp, [rsp-2Fh]
0x18000f00e  sub     rsp, 0A8h
0x18000f015  mov     rax, cs:__security_cookie
0x18000f01c  xor     rax, rsp
0x18000f01f  mov     [rbp+57h+var_38], rax
0x18000f023  cmp     byte ptr [rcx+38h], 0
0x18000f027  mov     rdi, rcx
0x18000f02a  jnz     short loc_18000F033
0x18000f02c  xor     eax, eax
0x18000f02e  jmp     loc_18000F2D2
0x18000f033  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f03a  lea     rsi, WPP_GLOBAL_Control
0x18000f041  mov     r13d, 800h
0x18000f047  cmp     rcx, rsi
0x18000f04a  jz      short loc_18000F06D
0x18000f04c  test    [rcx+6Ch], r13d
0x18000f050  jz      short loc_18000F06D
0x18000f052  cmp     byte ptr [rcx+69h], 4
0x18000f056  jb      short loc_18000F06D
0x18000f058  mov     rcx, [rcx+60h]
0x18000f05c  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000f063  mov     edx, 21h ; '!'
0x18000f068  call    WPP_SF_
0x18000f06d  xor     edx, edx; lpDatabaseName
0x18000f06f  xor     ecx, ecx; lpMachineName
0x18000f071  lea     r8d, [rdx+1]; dwDesiredAccess
0x18000f075  call    cs:__imp_OpenSCManagerW
0x18000f07b  mov     r14, rax
0x18000f07e  test    rax, rax
0x18000f081  jnz     short loc_18000F0C6
0x18000f083  call    cs:__imp_GetLastError
0x18000f089  mov     ebx, eax
0x18000f08b  test    eax, eax
0x18000f08d  jle     short loc_18000F098
0x18000f08f  movzx   ebx, ax
0x18000f092  or      ebx, 80070000h
0x18000f098  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f09f  cmp     rcx, rsi
0x18000f0a2  jz      loc_18000F2D0
0x18000f0a8  test    [rcx+6Ch], r13d
0x18000f0ac  jz      loc_18000F2D0
0x18000f0b2  cmp     byte ptr [rcx+69h], 1
0x18000f0b6  jb      loc_18000F2D0
0x18000f0bc  mov     edx, 22h ; '"'
0x18000f0c1  jmp     loc_18000F2BD
0x18000f0c6  mov     ebx, 24h ; '$'
0x18000f0cb  lea     rdx, ServiceName; "PeerDistKM"
0x18000f0d2  mov     r8d, ebx; dwDesiredAccess
0x18000f0d5  mov     rcx, r14; hSCManager
0x18000f0d8  call    cs:__imp_OpenServiceW
0x18000f0de  mov     rsi, rax
0x18000f0e1  test    rax, rax
0x18000f0e4  jnz     short loc_18000F140
0x18000f0e6  call    cs:__imp_GetLastError
0x18000f0ec  mov     ebx, eax
0x18000f0ee  test    eax, eax
0x18000f0f0  jle     short loc_18000F0FB
0x18000f0f2  movzx   ebx, ax
0x18000f0f5  or      ebx, 80070000h
0x18000f0fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f102  lea     rdi, WPP_GLOBAL_Control
0x18000f109  cmp     rcx, rdi
0x18000f10c  jz      short loc_18000F132
0x18000f10e  test    [rcx+6Ch], r13d
0x18000f112  jz      short loc_18000F132
0x18000f114  cmp     byte ptr [rcx+69h], 1
0x18000f118  jb      short loc_18000F132
0x18000f11a  mov     rcx, [rcx+60h]
0x18000f11e  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000f125  mov     edx, 23h ; '#'
0x18000f12a  mov     r9d, ebx
0x18000f12d  call    WPP_SF_d
0x18000f132  mov     rcx, r14; hSCObject
0x18000f135  call    cs:__imp_CloseServiceHandle
0x18000f13b  jmp     loc_18000F2D0
0x18000f140  xor     eax, eax
0x18000f142  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18000f146  xorps   xmm0, xmm0
0x18000f149  mov     [rbp+57h+var_40], eax
0x18000f14c  mov     [rbp+57h+var_A0], eax
0x18000f14f  mov     r9d, ebx; cbBufSize
0x18000f152  lea     rax, [rbp+57h+var_A0]
0x18000f156  xor     edx, edx; InfoLevel
0x18000f158  mov     rcx, rsi; hService
0x18000f15b  mov     [rsp+0D0h+pcbBytesNeeded], rax; unsigned int
0x18000f160  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x18000f164  movups  [rbp+57h+var_50], xmm0
0x18000f168  call    cs:__imp_QueryServiceStatusEx
0x18000f16e  test    eax, eax
0x18000f170  jnz     short loc_18000F1CF
0x18000f172  call    cs:__imp_GetLastError
0x18000f178  mov     ebx, eax
0x18000f17a  test    eax, eax
0x18000f17c  jle     short loc_18000F187
0x18000f17e  movzx   ebx, ax
0x18000f181  or      ebx, 80070000h
0x18000f187  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f18e  lea     rdi, WPP_GLOBAL_Control
0x18000f195  cmp     rcx, rdi
0x18000f198  jz      loc_18000F28E
0x18000f19e  test    [rcx+6Ch], r13d
0x18000f1a2  jz      loc_18000F28E
0x18000f1a8  cmp     byte ptr [rcx+69h], 1
0x18000f1ac  jb      loc_18000F28E
0x18000f1b2  mov     edx, 24h ; '$'
0x18000f1b7  mov     rcx, [rcx+60h]
0x18000f1bb  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000f1c2  mov     r9d, ebx
0x18000f1c5  call    WPP_SF_d
0x18000f1ca  jmp     loc_18000F28E
0x18000f1cf  cmp     dword ptr [rbp+57h+Buffer+4], 1
0x18000f1d3  jnz     short loc_18000F1DF
0x18000f1d5  xor     ebx, ebx
0x18000f1d7  mov     [rdi+38h], bl
0x18000f1da  jmp     loc_18000F287
0x18000f1df  mov     r9d, 3
0x18000f1e5  cmp     dword ptr [rbp+57h+Buffer+4], r9d
0x18000f1e9  jnz     short loc_18000F1FD
0x18000f1eb  movups  xmm0, xmmword ptr [rbp+57h+Buffer]
0x18000f1ef  movups  xmm1, [rbp+57h+var_50]
0x18000f1f3  movaps  xmmword ptr [rbp+57h+var_90.dwServiceType], xmm0
0x18000f1f7  movaps  xmmword ptr [rbp+57h+var_90.dwServiceSpecificExitCode], xmm1
0x18000f1fb  jmp     short loc_18000F26B
0x18000f1fd  lea     r8, [rbp+57h+Buffer]; lpServiceStatus
0x18000f201  mov     edx, 1; dwControl
0x18000f206  mov     rcx, rsi; hService
0x18000f209  call    cs:__imp_ControlService
0x18000f20f  test    eax, eax
0x18000f211  jnz     short loc_18000F251
0x18000f213  call    cs:__imp_GetLastError
0x18000f219  mov     ebx, eax
0x18000f21b  test    eax, eax
0x18000f21d  jle     short loc_18000F228
0x18000f21f  movzx   ebx, ax
0x18000f222  or      ebx, 80070000h
0x18000f228  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f22f  lea     rdi, WPP_GLOBAL_Control
0x18000f236  cmp     rcx, rdi
0x18000f239  jz      short loc_18000F28E
0x18000f23b  test    [rcx+6Ch], r13d
0x18000f23f  jz      short loc_18000F28E
0x18000f241  cmp     byte ptr [rcx+69h], 1
0x18000f245  jb      short loc_18000F28E
0x18000f247  mov     edx, 25h ; '%'
0x18000f24c  jmp     loc_18000F1B7
0x18000f251  movups  xmm1, xmmword ptr [rbp+57h+Buffer]
0x18000f255  movups  xmm0, [rbp+57h+var_50]
0x18000f259  movaps  xmmword ptr [rbp+57h+var_90.dwServiceType], xmm1
0x18000f25d  psrldq  xmm1, 4
0x18000f262  movd    r9d, xmm1; unsigned int
0x18000f267  movaps  xmmword ptr [rbp+57h+var_90.dwServiceSpecificExitCode], xmm0
0x18000f26b  mov     eax, [rbp+57h+var_40]
0x18000f26e  lea     r8, [rbp+57h+var_90]; struct _SERVICE_STATUS_PROCESS
0x18000f272  mov     rdx, rsi; struct SC_HANDLE__ *
0x18000f275  mov     [rbp+57h+var_90.dwServiceFlags], eax
0x18000f278  call    ?WaitForServiceStatus@CDriverLayerImpl@@AEAAJQEAUSC_HANDLE__@@U_SERVICE_STATUS_PROCESS@@KKK@Z; CDriverLayerImpl::WaitForServiceStatus(SC_HANDLE__ * const,_SERVICE_STATUS_PROCESS,ulong,ulong,ulong)
0x18000f27d  mov     ebx, eax
0x18000f27f  test    eax, eax
0x18000f281  js      short loc_18000F287
0x18000f283  mov     byte ptr [rdi+38h], 0
0x18000f287  lea     rdi, WPP_GLOBAL_Control
0x18000f28e  mov     rcx, rsi; hSCObject
0x18000f291  call    cs:__imp_CloseServiceHandle
0x18000f297  mov     rcx, r14; hSCObject
0x18000f29a  call    cs:__imp_CloseServiceHandle
0x18000f2a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2a7  cmp     rcx, rdi
0x18000f2aa  jz      short loc_18000F2D0
0x18000f2ac  test    [rcx+6Ch], r13d
0x18000f2b0  jz      short loc_18000F2D0
0x18000f2b2  cmp     byte ptr [rcx+69h], 4
0x18000f2b6  jb      short loc_18000F2D0
0x18000f2b8  mov     edx, 26h ; '&'
0x18000f2bd  mov     rcx, [rcx+60h]
0x18000f2c1  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000f2c8  mov     r9d, ebx
0x18000f2cb  call    WPP_SF_d
0x18000f2d0  mov     eax, ebx
0x18000f2d2  mov     rcx, [rbp+57h+var_38]
0x18000f2d6  xor     rcx, rsp; StackCookie
0x18000f2d9  call    __security_check_cookie
0x18000f2de  add     rsp, 0A8h
0x18000f2e5  pop     r14
0x18000f2e7  pop     r13
0x18000f2e9  pop     rdi
0x18000f2ea  pop     rsi
0x18000f2eb  pop     rbx
0x18000f2ec  pop     rbp
0x18000f2ed  retn
```
