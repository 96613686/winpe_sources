# Print::Driver::CPrinterExtensionServer::EnableEventsImpl(_GUID)

- ea: `0x18007ebe0`
- end: `0x18007ee18`
- name: `?EnableEventsImpl@CPrinterExtensionServer@Driver@Print@@AEAAXU_GUID@@@Z`
- size: `568`
- prototype: `void __fastcall(Print::Driver::CPrinterExtensionServer *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18007ea70`

## callees

- `0x180003400`
- `0x180004558`
- `0x180004564`
- `0x18000f830`
- `0x1800197b4`
- `0x18007ebe0`
- `0x18007f25c`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007ec6e`
- `KERNEL32!CloseHandle` at `0x18007ec6e`
- `KERNEL32!OpenProcess` at `0x18007ec51`
- `KERNEL32!OpenProcess` at `0x18007ec51`
- `KERNEL32!GetProcessId` at `0x18007ec81`
- `KERNEL32!GetProcessId` at `0x18007ec81`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007ec30`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007ec30`
- `ole32!CoRevertToSelf` at `0x18007ece5`
- `ole32!CoRevertToSelf` at `0x18007ece5`
- `ole32!CoImpersonateClient` at `0x18007ec93`
- `ole32!CoImpersonateClient` at `0x18007ec93`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Print::Driver::CPrinterExtensionServer::EnableEventsImpl(
        Print::Driver::CPrinterExtensionServer *this,
        struct _GUID *a2)
{
  RPC_STATUS v4; // edi
  HANDLE v5; // rdi
  char *v6; // rcx
  HRESULT v7; // eax
  Print::Driver::CPrinterExtensionServer *v8; // rcx
  int v9; // ebx
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-71h] BYREF
  __int64 v11; // [rsp+48h] [rbp-51h]
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v13[56]; // [rsp+58h] [rbp-41h] BYREF
  DWORD dwProcessId; // [rsp+90h] [rbp-9h]

  v11 = -2;
  memset_0(v13, 0, 0x68u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 16;
  v4 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0xBu,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v4);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v4);
    throw (hr_error *)pExceptionObject;
  }
  v5 = OpenProcess(0x400u, 0, dwProcessId);
  v6 = (char *)*((_QWORD *)this + 14);
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v6);
  *((_QWORD *)this + 14) = v5;
  *((_DWORD *)this + 32) = GetProcessId(v5);
  v7 = CoImpersonateClient();
  if ( v7 < 0 )
  {
    hr_error::hr_error((hr_error *)pExceptionObject, v7);
    throw (hr_error *)pExceptionObject;
  }
  if ( *((_BYTE *)this + 132) )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0xCu,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        -2147483634);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, -2147483634);
    throw (hr_error *)pExceptionObject;
  }
  *(struct _GUID *)((char *)this + 136) = *a2;
  Print::Driver::CPrinterExtensionServer::GetLogonSessionId(v8, (struct _LUID *)this + 21);
  v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 5) + 24LL))((char *)this + 40);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        0xDu,
        (const GUID *)WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        v9);
    }
    hr_error::hr_error((hr_error *)pExceptionObject, v9);
    throw (hr_error *)pExceptionObject;
  }
  if ( CoRevertToSelf() < 0 )
    __int2c();
}

```

## disassembly

```asm
0x18007ebe0  push    rbp
0x18007ebe2  push    rbx
0x18007ebe3  push    rsi
0x18007ebe4  push    rdi
0x18007ebe5  lea     rbp, [rsp-3Fh]
0x18007ebea  sub     rsp, 0D8h
0x18007ebf1  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFEh
0x18007ebf9  mov     rax, cs:__security_cookie
0x18007ec00  xor     rax, rsp
0x18007ec03  mov     [rbp+57h+var_30], rax
0x18007ec07  mov     rsi, rdx
0x18007ec0a  mov     rbx, rcx
0x18007ec0d  xor     edx, edx; Val
0x18007ec0f  lea     r8d, [rdx+68h]; Size
0x18007ec13  lea     rcx, [rbp+57h+var_98]; void *
0x18007ec17  call    memset_0
0x18007ec1c  mov     [rbp+57h+RpcCallAttributes], 2
0x18007ec23  mov     [rbp+57h+var_9C], 10h
0x18007ec2a  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18007ec2e  xor     ecx, ecx; ClientBinding
0x18007ec30  call    cs:__imp_RpcServerInqCallAttributesW
0x18007ec37  nop     dword ptr [rax+rax+00h]
0x18007ec3c  mov     edi, eax
0x18007ec3e  test    eax, eax
0x18007ec40  jnz     loc_18007ED5D
0x18007ec46  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x18007ec4a  xor     edx, edx; bInheritHandle
0x18007ec4c  mov     ecx, 400h; dwDesiredAccess
0x18007ec51  call    cs:__imp_OpenProcess
0x18007ec58  nop     dword ptr [rax+rax+00h]
0x18007ec5d  mov     rdi, rax
0x18007ec60  mov     rcx, [rbx+70h]; hObject
0x18007ec64  lea     rdx, [rcx-1]
0x18007ec68  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007ec6c  ja      short loc_18007EC7A
0x18007ec6e  call    cs:__imp_CloseHandle
0x18007ec75  nop     dword ptr [rax+rax+00h]
0x18007ec7a  mov     [rbx+70h], rdi
0x18007ec7e  mov     rcx, rdi; Process
0x18007ec81  call    cs:__imp_GetProcessId
0x18007ec88  nop     dword ptr [rax+rax+00h]
0x18007ec8d  mov     [rbx+80h], eax
0x18007ec93  call    cs:__imp_CoImpersonateClient
0x18007ec9a  nop     dword ptr [rax+rax+00h]
0x18007ec9f  test    eax, eax
0x18007eca1  js      loc_18007EDAA
0x18007eca7  mov     [rbp+57h+var_D0], 1
0x18007ecab  cmp     byte ptr [rbx+84h], 0
0x18007ecb2  jnz     loc_18007EDC6
0x18007ecb8  movaps  xmm0, xmmword ptr [rsi]
0x18007ecbb  movdqu  xmmword ptr [rbx+88h], xmm0
0x18007ecc3  lea     rdx, [rbx+0A8h]; struct _LUID *
0x18007ecca  call    ?GetLogonSessionId@CPrinterExtensionServer@Driver@Print@@AEAAXPEAU_LUID@@@Z; Print::Driver::CPrinterExtensionServer::GetLogonSessionId(_LUID *)
0x18007eccf  lea     rcx, [rbx+28h]
0x18007ecd3  mov     rax, [rcx]
0x18007ecd6  mov     rax, [rax+18h]
0x18007ecda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ecdf  mov     ebx, eax
0x18007ece1  test    eax, eax
0x18007ece3  js      short loc_18007ED10
0x18007ece5  call    cs:__imp_CoRevertToSelf
0x18007ecec  nop     dword ptr [rax+rax+00h]
0x18007ecf1  test    eax, eax
0x18007ecf3  jns     short loc_18007ECF7
0x18007ecf5  int     2Ch; Windows NT - assertion failure
0x18007ecf7  mov     rcx, [rbp+57h+var_30]
0x18007ecfb  xor     rcx, rsp; StackCookie
0x18007ecfe  call    __security_check_cookie
0x18007ed03  add     rsp, 0D8h
0x18007ed0a  pop     rdi
0x18007ed0b  pop     rsi
0x18007ed0c  pop     rbx
0x18007ed0d  pop     rbp
0x18007ed0e  retn
0x18007ed10  lea     rax, WPP_GLOBAL_Control
0x18007ed17  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed1e  cmp     rcx, rax
0x18007ed21  jz      short loc_18007ED41
0x18007ed23  test    byte ptr [rcx+44h], 1
0x18007ed27  jz      short loc_18007ED41
0x18007ed29  mov     edx, 0Dh
0x18007ed2e  mov     r9d, ebx
0x18007ed31  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007ed38  mov     rcx, [rcx+38h]
0x18007ed3c  call    WPP_SF_d
0x18007ed41  mov     edx, ebx; int
0x18007ed43  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007ed47  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007ed4c  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007ed53  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007ed57  call    _CxxThrowException_0
0x18007ed5d  lea     rax, WPP_GLOBAL_Control
0x18007ed64  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed6b  cmp     rcx, rax
0x18007ed6e  jz      short loc_18007ED8E
0x18007ed70  test    byte ptr [rcx+44h], 1
0x18007ed74  jz      short loc_18007ED8E
0x18007ed76  mov     edx, 0Bh
0x18007ed7b  mov     r9d, edi
0x18007ed7e  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007ed85  mov     rcx, [rcx+38h]
0x18007ed89  call    WPP_SF_d
0x18007ed8e  mov     edx, edi; int
0x18007ed90  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007ed94  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007ed99  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007eda0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007eda4  call    _CxxThrowException_0
0x18007edaa  mov     edx, eax; int
0x18007edac  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007edb0  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007edb5  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007edbc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007edc0  call    _CxxThrowException_0
0x18007edc6  lea     rax, WPP_GLOBAL_Control
0x18007edcd  mov     ebx, 8000000Eh
0x18007edd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007edd9  cmp     rcx, rax
0x18007eddc  jz      short loc_18007EDFC
0x18007edde  test    byte ptr [rcx+44h], 1
0x18007ede2  jz      short loc_18007EDFC
0x18007ede4  mov     edx, 0Ch
0x18007ede9  mov     r9d, ebx
0x18007edec  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007edf3  mov     rcx, [rcx+38h]
0x18007edf7  call    WPP_SF_d
0x18007edfc  mov     edx, ebx; int
0x18007edfe  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007ee02  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007ee07  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007ee0e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007ee12  call    _CxxThrowException_0
```
