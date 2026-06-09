# NetworkAccountBindingAccessCheck

- ea: `0x18000e6a0`
- end: `0x18000e94d`
- name: `NetworkAccountBindingAccessCheck`
- size: `685`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e960`

## callees

- `0x180008ff0`
- `0x180009850`
- `0x18000a19a`
- `0x18000b6f4`
- `0x18000dc20`
- `0x18000e1e8`
- `0x18000e6a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e7e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000e7e5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e7b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e7f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e7b2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000e7f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e84d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e84d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e86e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e7d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e86e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e77a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e77a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e843`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000e843`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000e761`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000e761`

## pseudocode

```c
__int64 __fastcall NetworkAccountBindingAccessCheck(unsigned __int16 *a1)
{
  PVOID *v2; // rcx
  RPC_STATUS v3; // eax
  DWORD v4; // esi
  signed int NetworkAccountBindingDeviceInterfacePath; // ebx
  HANDLE v6; // rdi
  signed int v7; // eax
  signed int v8; // eax
  HANDLE CurrentProcess; // rax
  signed int v10; // eax
  signed int LastError; // eax
  PVOID *v12; // rcx
  int v13; // eax
  int TokenInformation; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength[4]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[56]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwProcessId; // [rsp+90h] [rbp-70h]
  unsigned __int16 v21[264]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  TokenInformation = 0;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x10) != 0 )
    WPP_SF_(v2[2], 10, &WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids);
  TokenHandle = (void *)-1LL;
  TokenInformation = 0;
  memset_0(v19, 0, 0x68u);
  RpcCallAttributes[1] = 16;
  RpcCallAttributes[0] = 3;
  v3 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v3 )
  {
    v4 = 0;
    if ( v3 != 1725 )
    {
      NetworkAccountBindingDeviceInterfacePath = -2147467259;
      goto LABEL_27;
    }
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      NetworkAccountBindingDeviceInterfacePath = 0;
LABEL_23:
      ReturnLength[0] = 0;
      if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, ReturnLength) )
      {
        LastError = GetLastError();
        NetworkAccountBindingDeviceInterfacePath = LastError;
        if ( LastError > 0 )
          NetworkAccountBindingDeviceInterfacePath = (unsigned __int16)LastError | 0x80070000;
      }
      goto LABEL_27;
    }
    v10 = GetLastError();
    NetworkAccountBindingDeviceInterfacePath = v10;
    if ( v10 > 0 )
      NetworkAccountBindingDeviceInterfacePath = (unsigned __int16)v10 | 0x80070000;
LABEL_20:
    if ( NetworkAccountBindingDeviceInterfacePath < 0 )
      goto LABEL_27;
    goto LABEL_23;
  }
  v4 = dwProcessId;
  NetworkAccountBindingDeviceInterfacePath = 0;
  v6 = OpenProcess(0x1000u, 0, dwProcessId);
  if ( v6 )
    goto LABEL_44;
  v7 = GetLastError();
  NetworkAccountBindingDeviceInterfacePath = v7;
  if ( v7 > 0 )
    NetworkAccountBindingDeviceInterfacePath = (unsigned __int16)v7 | 0x80070000;
  if ( NetworkAccountBindingDeviceInterfacePath >= 0 )
  {
LABEL_44:
    if ( !OpenProcessToken(v6, 8u, &TokenHandle) )
    {
      v8 = GetLastError();
      NetworkAccountBindingDeviceInterfacePath = v8;
      if ( v8 > 0 )
        NetworkAccountBindingDeviceInterfacePath = (unsigned __int16)v8 | 0x80070000;
    }
    CloseHandle(v6);
    goto LABEL_20;
  }
LABEL_27:
  CloseHandle(TokenHandle);
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids,
      (unsigned int)NetworkAccountBindingDeviceInterfacePath);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( NetworkAccountBindingDeviceInterfacePath < 0 || !TokenInformation )
    goto LABEL_38;
  NetworkAccountBindingDeviceInterfacePath = GetNetworkAccountBindingDeviceInterfacePath(a1);
  if ( NetworkAccountBindingDeviceInterfacePath < 0 )
    goto LABEL_37;
  v13 = PrivilegedAppAccessCheck(v4, v21);
  NetworkAccountBindingDeviceInterfacePath = v13;
  if ( v13 >= 0 )
    goto LABEL_37;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)NetworkAccountBindingDeviceInterfacePath;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids,
      (unsigned int)v13);
LABEL_37:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_38:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x10) != 0 )
    WPP_SF_d(
      v12[2],
      15,
      &WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids,
      (unsigned int)NetworkAccountBindingDeviceInterfacePath);
  return (unsigned int)NetworkAccountBindingDeviceInterfacePath;
}

```

## disassembly

```asm
0x18000e6a0  push    rbp
0x18000e6a2  push    rbx
0x18000e6a3  push    rsi
0x18000e6a4  push    rdi
0x18000e6a5  push    r12
0x18000e6a7  push    r14
0x18000e6a9  lea     rbp, [rsp-1E8h]
0x18000e6b1  sub     rsp, 2E8h
0x18000e6b8  mov     rax, cs:__security_cookie
0x18000e6bf  xor     rax, rsp
0x18000e6c2  mov     [rbp+210h+var_40], rax
0x18000e6c9  mov     r14, rcx
0x18000e6cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e6d3  lea     r12, WPP_GLOBAL_Control
0x18000e6da  cmp     rcx, r12
0x18000e6dd  jz      short loc_18000E701
0x18000e6df  test    byte ptr [rcx+1Ch], 10h
0x18000e6e3  jz      short loc_18000E701
0x18000e6e5  mov     rcx, [rcx+10h]
0x18000e6e9  lea     r8, WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids
0x18000e6f0  mov     edx, 0Dh
0x18000e6f5  call    WPP_SF_
0x18000e6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e701  mov     [rsp+310h+TokenInformation], 0
0x18000e709  cmp     rcx, r12
0x18000e70c  jz      short loc_18000E729
0x18000e70e  test    byte ptr [rcx+1Ch], 10h
0x18000e712  jz      short loc_18000E729
0x18000e714  mov     rcx, [rcx+10h]
0x18000e718  lea     r8, WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids
0x18000e71f  mov     edx, 0Ah
0x18000e724  call    WPP_SF_
0x18000e729  xor     edx, edx; Val
0x18000e72b  mov     [rsp+310h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18000e734  lea     rcx, [rsp+310h+var_2B8]; void *
0x18000e739  mov     [rsp+310h+TokenInformation], 0
0x18000e741  lea     r8d, [rdx+68h]; Size
0x18000e745  call    memset_0
0x18000e74a  lea     rdx, [rsp+310h+RpcCallAttributes]; RpcCallAttributes
0x18000e74f  mov     [rsp+310h+var_2BC], 10h
0x18000e757  xor     ecx, ecx; ClientBinding
0x18000e759  mov     [rsp+310h+RpcCallAttributes], 3
0x18000e761  call    cs:__imp_RpcServerInqCallAttributesW
0x18000e767  test    eax, eax
0x18000e769  jnz     short loc_18000E7DC
0x18000e76b  mov     esi, [rbp+210h+dwProcessId]
0x18000e76e  xor     edx, edx; bInheritHandle
0x18000e770  mov     r8d, esi; dwProcessId
0x18000e773  mov     ecx, 1000h; dwDesiredAccess
0x18000e778  xor     ebx, ebx
0x18000e77a  call    cs:__imp_OpenProcess
0x18000e780  mov     rdi, rax
0x18000e783  test    rax, rax
0x18000e786  jnz     short loc_18000E7A5
0x18000e788  call    cs:__imp_GetLastError
0x18000e78e  mov     ebx, eax
0x18000e790  test    eax, eax
0x18000e792  jle     short loc_18000E79D
0x18000e794  movzx   ebx, ax
0x18000e797  or      ebx, 80070000h
0x18000e79d  test    ebx, ebx
0x18000e79f  js      loc_18000E869
0x18000e7a5  lea     r8, [rsp+310h+TokenHandle]; TokenHandle
0x18000e7aa  mov     edx, 8; DesiredAccess
0x18000e7af  mov     rcx, rdi; ProcessHandle
0x18000e7b2  call    cs:__imp_OpenProcessToken
0x18000e7b8  test    eax, eax
0x18000e7ba  jnz     short loc_18000E7D1
0x18000e7bc  call    cs:__imp_GetLastError
0x18000e7c2  mov     ebx, eax
0x18000e7c4  test    eax, eax
0x18000e7c6  jle     short loc_18000E7D1
0x18000e7c8  movzx   ebx, ax
0x18000e7cb  or      ebx, 80070000h
0x18000e7d1  mov     rcx, rdi; hObject
0x18000e7d4  call    cs:__imp_CloseHandle
0x18000e7da  jmp     short loc_18000E815
0x18000e7dc  xor     esi, esi
0x18000e7de  cmp     eax, 6BDh
0x18000e7e3  jnz     short loc_18000E864
0x18000e7e5  call    cs:__imp_GetCurrentProcess
0x18000e7eb  mov     rcx, rax; ProcessHandle
0x18000e7ee  lea     r8, [rsp+310h+TokenHandle]; TokenHandle
0x18000e7f3  lea     edx, [rsi+8]; DesiredAccess
0x18000e7f6  call    cs:__imp_OpenProcessToken
0x18000e7fc  test    eax, eax
0x18000e7fe  jnz     short loc_18000E81B
0x18000e800  call    cs:__imp_GetLastError
0x18000e806  mov     ebx, eax
0x18000e808  test    eax, eax
0x18000e80a  jle     short loc_18000E815
0x18000e80c  movzx   ebx, ax
0x18000e80f  or      ebx, 80070000h
0x18000e815  test    ebx, ebx
0x18000e817  js      short loc_18000E869
0x18000e819  jmp     short loc_18000E81D
0x18000e81b  xor     ebx, ebx
0x18000e81d  mov     rcx, [rsp+310h+TokenHandle]; TokenHandle
0x18000e822  lea     rax, [rsp+310h+var_2D0]
0x18000e827  mov     r9d, 4; TokenInformationLength
0x18000e82d  mov     [rsp+310h+var_2D0], 0
0x18000e835  lea     r8, [rsp+310h+TokenInformation]; TokenInformation
0x18000e83a  mov     [rsp+310h+ReturnLength], rax; ReturnLength
0x18000e83f  lea     edx, [r9+19h]; TokenInformationClass
0x18000e843  call    cs:__imp_GetTokenInformation
0x18000e849  test    eax, eax
0x18000e84b  jnz     short loc_18000E869
0x18000e84d  call    cs:__imp_GetLastError
0x18000e853  mov     ebx, eax
0x18000e855  test    eax, eax
0x18000e857  jle     short loc_18000E869
0x18000e859  movzx   ebx, ax
0x18000e85c  or      ebx, 80070000h
0x18000e862  jmp     short loc_18000E869
0x18000e864  mov     ebx, 80004005h
0x18000e869  mov     rcx, [rsp+310h+TokenHandle]; hObject
0x18000e86e  call    cs:__imp_CloseHandle
0x18000e874  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e87b  cmp     rcx, r12
0x18000e87e  jz      short loc_18000E8A5
0x18000e880  test    byte ptr [rcx+1Ch], 10h
0x18000e884  jz      short loc_18000E8A5
0x18000e886  mov     rcx, [rcx+10h]
0x18000e88a  lea     r8, WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids
0x18000e891  mov     edx, 0Bh
0x18000e896  mov     r9d, ebx
0x18000e899  call    WPP_SF_d
0x18000e89e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8a5  test    ebx, ebx
0x18000e8a7  js      short loc_18000E909
0x18000e8a9  cmp     [rsp+310h+TokenInformation], 0
0x18000e8ae  jz      short loc_18000E909
0x18000e8b0  lea     r8, [rbp+210h+var_250]
0x18000e8b4  mov     edx, 104h
0x18000e8b9  mov     rcx, r14; unsigned __int16 *
0x18000e8bc  call    GetNetworkAccountBindingDeviceInterfacePath
0x18000e8c1  mov     ebx, eax
0x18000e8c3  test    eax, eax
0x18000e8c5  js      short loc_18000E902
0x18000e8c7  lea     rdx, [rbp+210h+var_250]; unsigned __int16 *
0x18000e8cb  mov     ecx, esi; dwProcessId
0x18000e8cd  call    ?PrivilegedAppAccessCheck@@YAJKPEBG@Z; PrivilegedAppAccessCheck(ulong,ushort const *)
0x18000e8d2  mov     ebx, eax
0x18000e8d4  test    eax, eax
0x18000e8d6  jns     short loc_18000E902
0x18000e8d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8df  cmp     rcx, r12
0x18000e8e2  jz      short loc_18000E92C
0x18000e8e4  test    byte ptr [rcx+1Ch], 2
0x18000e8e8  jz      short loc_18000E909
0x18000e8ea  mov     rcx, [rcx+10h]
0x18000e8ee  lea     r8, WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids
0x18000e8f5  mov     edx, 0Eh
0x18000e8fa  mov     r9d, eax
0x18000e8fd  call    WPP_SF_d
0x18000e902  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e909  cmp     rcx, r12
0x18000e90c  jz      short loc_18000E92C
0x18000e90e  test    byte ptr [rcx+1Ch], 10h
0x18000e912  jz      short loc_18000E92C
0x18000e914  mov     rcx, [rcx+10h]
0x18000e918  lea     r8, WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids
0x18000e91f  mov     edx, 0Fh
0x18000e924  mov     r9d, ebx
0x18000e927  call    WPP_SF_d
0x18000e92c  mov     eax, ebx
0x18000e92e  mov     rcx, [rbp+210h+var_40]
0x18000e935  xor     rcx, rsp; StackCookie
0x18000e938  call    __security_check_cookie
0x18000e93d  add     rsp, 2E8h
0x18000e944  pop     r14
0x18000e946  pop     r12
0x18000e948  pop     rdi
0x18000e949  pop     rsi
0x18000e94a  pop     rbx
0x18000e94b  pop     rbp
0x18000e94c  retn
```
