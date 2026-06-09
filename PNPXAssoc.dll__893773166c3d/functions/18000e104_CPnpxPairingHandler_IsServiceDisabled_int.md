# CPnpxPairingHandler::IsServiceDisabled(int *)

- ea: `0x18000e104`
- end: `0x18000e32f`
- name: `?IsServiceDisabled@CPnpxPairingHandler@@IEAAJPEAH@Z`
- size: `555`
- prototype: `__int64 __fastcall(CPnpxPairingHandler *__hidden this, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18000dbc0`
- `0x18000e9d0`

## callees

- `0x1800019bc`
- `0x1800019c8`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000e104`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e1b1`
- `KERNEL32!GetLastError` at `0x18000e1e9`
- `KERNEL32!GetLastError` at `0x18000e21a`
- `KERNEL32!GetLastError` at `0x18000e29c`
- `KERNEL32!GetLastError` at `0x18000e1b1`
- `KERNEL32!GetLastError` at `0x18000e1e9`
- `KERNEL32!GetLastError` at `0x18000e21a`
- `KERNEL32!GetLastError` at `0x18000e29c`
- `ADVAPI32!OpenSCManagerW` at `0x18000e19d`
- `ADVAPI32!OpenSCManagerW` at `0x18000e19d`
- `ADVAPI32!CloseServiceHandle` at `0x18000e259`
- `ADVAPI32!CloseServiceHandle` at `0x18000e267`
- `ADVAPI32!CloseServiceHandle` at `0x18000e259`
- `ADVAPI32!CloseServiceHandle` at `0x18000e267`
- `ADVAPI32!QueryServiceConfigW` at `0x18000e20c`
- `ADVAPI32!QueryServiceConfigW` at `0x18000e292`
- `ADVAPI32!QueryServiceConfigW` at `0x18000e20c`
- `ADVAPI32!QueryServiceConfigW` at `0x18000e292`
- `ADVAPI32!OpenServiceW` at `0x18000e1db`
- `ADVAPI32!OpenServiceW` at `0x18000e1db`

## string_xrefs

- `0x18000e194`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CPnpxPairingHandler::IsServiceDisabled(CPnpxPairingHandler *this, int *a2)
{
  _QWORD *v3; // rcx
  SC_HANDLE v4; // rbp
  signed int LastError; // eax
  unsigned int v6; // ebx
  SC_HANDLE v7; // rsi
  signed int v8; // eax
  signed int v9; // eax
  struct _QUERY_SERVICE_CONFIGW *v10; // rax
  struct _QUERY_SERVICE_CONFIGW *v11; // rdi
  _QWORD *v12; // rcx
  int v13; // eax
  bool v14; // cf
  signed int v15; // eax
  DWORD pcbBytesNeeded; // [rsp+68h] [rbp+10h] BYREF

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  pcbBytesNeeded = 0;
  if ( v3 != &WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) >= 4u )
    WPP_SF_sq(v3[2], 45, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  *a2 = 0;
  v4 = OpenSCManagerW(0, L"ServicesActive", 1u);
  if ( !v4 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 )
      goto LABEL_37;
  }
  v7 = OpenServiceW(v4, L"IPBusEnum", 1u);
  if ( !v7 )
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v6 )
      goto LABEL_21;
  }
  if ( QueryServiceConfigW(v7, 0, 0, &pcbBytesNeeded) )
  {
    v6 = -2147467259;
    goto LABEL_21;
  }
  v9 = GetLastError();
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( v6 == -2147024774 )
  {
    v10 = (struct _QUERY_SERVICE_CONFIGW *)operator new[](pcbBytesNeeded);
    v11 = v10;
    if ( !v10 )
    {
      v6 = -2147024882;
      goto LABEL_21;
    }
    v6 = 0;
    if ( QueryServiceConfigW(v7, v10, pcbBytesNeeded, &pcbBytesNeeded) )
      goto LABEL_32;
    v15 = GetLastError();
    v6 = v15;
    if ( v15 > 0 )
      v6 = (unsigned __int16)v15 | 0x80070000;
  }
  else
  {
    v11 = 0;
  }
  if ( !v6 )
  {
LABEL_32:
    if ( v11->dwStartType == 4 )
      *a2 = 1;
  }
  if ( v11 )
    operator delete[](v11);
LABEL_21:
  if ( v4 )
    CloseServiceHandle(v4);
  if ( v7 )
    CloseServiceHandle(v7);
  if ( v6 )
  {
LABEL_37:
    v12 = WPP_GLOBAL_Control;
    v13 = 0;
    v14 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
    goto LABEL_38;
  }
  v12 = WPP_GLOBAL_Control;
  v13 = 0;
  v14 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
LABEL_38:
  if ( v12 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v13) = !v14;
    if ( v13 )
      WPP_SF_sqd(v12[2], 46, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x18000e104  mov     [rsp+arg_0], rbx
0x18000e109  mov     [rsp+arg_10], rbp
0x18000e10e  push    rsi
0x18000e10f  push    rdi
0x18000e110  push    r12
0x18000e112  push    r14
0x18000e114  push    r15
0x18000e116  sub     rsp, 30h
0x18000e11a  mov     r15, rdx
0x18000e11d  mov     r14, rcx
0x18000e120  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e127  lea     rdi, WPP_GLOBAL_Control
0x18000e12e  cmp     rcx, rdi
0x18000e131  jz      short loc_18000E15A
0x18000e133  cmp     byte ptr [rcx+19h], 4
0x18000e137  jb      short loc_18000E15A
0x18000e139  mov     rcx, [rcx+10h]
0x18000e13d  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000e144  mov     edx, 2Ch ; ','
0x18000e149  mov     [rsp+58h+var_38], r14
0x18000e14e  call    WPP_SF_sq
0x18000e153  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e15a  mov     [rsp+58h+pcbBytesNeeded], 0
0x18000e162  cmp     rcx, rdi
0x18000e165  jz      short loc_18000E187
0x18000e167  cmp     byte ptr [rcx+19h], 4
0x18000e16b  jb      short loc_18000E187
0x18000e16d  mov     rcx, [rcx+10h]
0x18000e171  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000e178  mov     edx, 2Dh ; '-'
0x18000e17d  mov     [rsp+58h+var_38], r14
0x18000e182  call    WPP_SF_sq
0x18000e187  mov     r8d, 1; dwDesiredAccess
0x18000e18d  mov     dword ptr [r15], 0
0x18000e194  lea     rdx, DatabaseName; "ServicesActive"
0x18000e19b  xor     ecx, ecx; lpMachineName
0x18000e19d  call    cs:__imp_OpenSCManagerW
0x18000e1a3  mov     rbp, rax
0x18000e1a6  mov     r12d, 80070000h
0x18000e1ac  test    rax, rax
0x18000e1af  jnz     short loc_18000E1CB
0x18000e1b1  call    cs:__imp_GetLastError
0x18000e1b7  mov     ebx, eax
0x18000e1b9  test    eax, eax
0x18000e1bb  jle     short loc_18000E1C3
0x18000e1bd  movzx   ebx, ax
0x18000e1c0  or      ebx, r12d
0x18000e1c3  test    ebx, ebx
0x18000e1c5  jnz     loc_18000E2DF
0x18000e1cb  mov     r8d, 1; dwDesiredAccess
0x18000e1d1  lea     rdx, ServiceName; "IPBusEnum"
0x18000e1d8  mov     rcx, rbp; hSCManager
0x18000e1db  call    cs:__imp_OpenServiceW
0x18000e1e1  mov     rsi, rax
0x18000e1e4  test    rax, rax
0x18000e1e7  jnz     short loc_18000E1FF
0x18000e1e9  call    cs:__imp_GetLastError
0x18000e1ef  mov     ebx, eax
0x18000e1f1  test    eax, eax
0x18000e1f3  jle     short loc_18000E1FB
0x18000e1f5  movzx   ebx, ax
0x18000e1f8  or      ebx, r12d
0x18000e1fb  test    ebx, ebx
0x18000e1fd  jnz     short loc_18000E251
0x18000e1ff  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x18000e204  xor     r8d, r8d; cbBufSize
0x18000e207  xor     edx, edx; lpServiceConfig
0x18000e209  mov     rcx, rsi; hService
0x18000e20c  call    cs:__imp_QueryServiceConfigW
0x18000e212  test    eax, eax
0x18000e214  jnz     loc_18000E2D5
0x18000e21a  call    cs:__imp_GetLastError
0x18000e220  mov     ebx, eax
0x18000e222  test    eax, eax
0x18000e224  jle     short loc_18000E22C
0x18000e226  movzx   ebx, ax
0x18000e229  or      ebx, r12d
0x18000e22c  cmp     ebx, 8007007Ah
0x18000e232  jnz     short loc_18000E2B0
0x18000e234  mov     ecx, [rsp+58h+pcbBytesNeeded]; unsigned __int64
0x18000e238  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000e23d  mov     rdi, rax
0x18000e240  test    rax, rax
0x18000e243  jnz     short loc_18000E280
0x18000e245  mov     ebx, 8007000Eh
0x18000e24a  lea     rdi, WPP_GLOBAL_Control
0x18000e251  test    rbp, rbp
0x18000e254  jz      short loc_18000E25F
0x18000e256  mov     rcx, rbp; hSCObject
0x18000e259  call    cs:__imp_CloseServiceHandle
0x18000e25f  test    rsi, rsi
0x18000e262  jz      short loc_18000E26D
0x18000e264  mov     rcx, rsi; hSCObject
0x18000e267  call    cs:__imp_CloseServiceHandle
0x18000e26d  test    ebx, ebx
0x18000e26f  jnz     short loc_18000E2DF
0x18000e271  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e278  xor     eax, eax
0x18000e27a  cmp     byte ptr [rcx+19h], 4
0x18000e27e  jmp     short loc_18000E2EC
0x18000e280  mov     r8d, [rsp+58h+pcbBytesNeeded]; cbBufSize
0x18000e285  lea     r9, [rsp+58h+pcbBytesNeeded]; pcbBytesNeeded
0x18000e28a  mov     rdx, rax; lpServiceConfig
0x18000e28d  mov     rcx, rsi; hService
0x18000e290  xor     ebx, ebx
0x18000e292  call    cs:__imp_QueryServiceConfigW
0x18000e298  test    eax, eax
0x18000e29a  jnz     short loc_18000E2B6
0x18000e29c  call    cs:__imp_GetLastError
0x18000e2a2  mov     ebx, eax
0x18000e2a4  test    eax, eax
0x18000e2a6  jle     short loc_18000E2B2
0x18000e2a8  movzx   ebx, ax
0x18000e2ab  or      ebx, r12d
0x18000e2ae  jmp     short loc_18000E2B2
0x18000e2b0  xor     edi, edi
0x18000e2b2  test    ebx, ebx
0x18000e2b4  jnz     short loc_18000E2C3
0x18000e2b6  cmp     dword ptr [rdi+4], 4
0x18000e2ba  jnz     short loc_18000E2C3
0x18000e2bc  mov     dword ptr [r15], 1
0x18000e2c3  test    rdi, rdi
0x18000e2c6  jz      short loc_18000E24A
0x18000e2c8  mov     rcx, rdi; Block
0x18000e2cb  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000e2d0  jmp     loc_18000E24A
0x18000e2d5  mov     ebx, 80004005h
0x18000e2da  jmp     loc_18000E251
0x18000e2df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2e6  xor     eax, eax
0x18000e2e8  cmp     byte ptr [rcx+19h], 2
0x18000e2ec  setnb   al
0x18000e2ef  cmp     rcx, rdi
0x18000e2f2  jz      short loc_18000E316
0x18000e2f4  test    eax, eax
0x18000e2f6  jz      short loc_18000E316
0x18000e2f8  mov     rcx, [rcx+10h]
0x18000e2fc  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000e303  mov     edx, 2Eh ; '.'
0x18000e308  mov     [rsp+58h+var_30], ebx
0x18000e30c  mov     [rsp+58h+var_38], r14
0x18000e311  call    WPP_SF_sqd
0x18000e316  mov     rbp, [rsp+58h+arg_10]
0x18000e31b  mov     eax, ebx
0x18000e31d  mov     rbx, [rsp+58h+arg_0]
0x18000e322  add     rsp, 30h
0x18000e326  pop     r15
0x18000e328  pop     r14
0x18000e32a  pop     r12
0x18000e32c  pop     rdi
0x18000e32d  pop     rsi
0x18000e32e  retn
```
