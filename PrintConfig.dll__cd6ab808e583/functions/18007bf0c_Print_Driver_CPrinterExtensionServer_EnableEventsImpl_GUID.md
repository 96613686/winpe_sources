# Print::Driver::CPrinterExtensionServer::EnableEventsImpl(_GUID)

- ea: `0x18007bf0c`
- end: `0x18007c11f`
- name: `?EnableEventsImpl@CPrinterExtensionServer@Driver@Print@@AEAAXU_GUID@@@Z`
- size: `531`
- prototype: `void __fastcall(Print::Driver::CPrinterExtensionServer *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18007bda0`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180004424`
- `0x18000f380`
- `0x180018bbc`
- `0x18007bf0c`
- `0x18007c54c`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18007bf8e`
- `KERNEL32!CloseHandle` at `0x18007bf8e`
- `KERNEL32!OpenProcess` at `0x18007bf77`
- `KERNEL32!OpenProcess` at `0x18007bf77`
- `KERNEL32!GetProcessId` at `0x18007bf9b`
- `KERNEL32!GetProcessId` at `0x18007bf9b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007bf5c`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18007bf5c`
- `ole32!CoRevertToSelf` at `0x18007bff3`
- `ole32!CoRevertToSelf` at `0x18007bff3`
- `ole32!CoImpersonateClient` at `0x18007bfa7`
- `ole32!CoImpersonateClient` at `0x18007bfa7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Print::Driver::CPrinterExtensionServer::EnableEventsImpl(
        Print::Driver::CPrinterExtensionServer *this,
        struct _GUID *a2)
{
  unsigned int v4; // edi
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, v4);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids, 2147483662LL);
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
        13,
        WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids,
        (unsigned int)v9);
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
0x18007bf0c  push    rbp
0x18007bf0e  push    rbx
0x18007bf0f  push    rsi
0x18007bf10  push    rdi
0x18007bf11  lea     rbp, [rsp-3Fh]
0x18007bf16  sub     rsp, 0D8h
0x18007bf1d  mov     [rbp+57h+var_A8], 0FFFFFFFFFFFFFFFEh
0x18007bf25  mov     rax, cs:__security_cookie
0x18007bf2c  xor     rax, rsp
0x18007bf2f  mov     [rbp+57h+var_30], rax
0x18007bf33  mov     rsi, rdx
0x18007bf36  mov     rbx, rcx
0x18007bf39  xor     edx, edx; Val
0x18007bf3b  lea     r8d, [rdx+68h]; Size
0x18007bf3f  lea     rcx, [rbp+57h+var_98]; void *
0x18007bf43  call    memset_0
0x18007bf48  mov     [rbp+57h+RpcCallAttributes], 2
0x18007bf4f  mov     [rbp+57h+var_9C], 10h
0x18007bf56  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18007bf5a  xor     ecx, ecx; ClientBinding
0x18007bf5c  call    cs:__imp_RpcServerInqCallAttributesW
0x18007bf62  mov     edi, eax
0x18007bf64  test    eax, eax
0x18007bf66  jnz     loc_18007C064
0x18007bf6c  mov     r8d, [rbp+57h+dwProcessId]; dwProcessId
0x18007bf70  xor     edx, edx; bInheritHandle
0x18007bf72  mov     ecx, 400h; dwDesiredAccess
0x18007bf77  call    cs:__imp_OpenProcess
0x18007bf7d  mov     rdi, rax
0x18007bf80  mov     rcx, [rbx+70h]; hObject
0x18007bf84  lea     rdx, [rcx-1]
0x18007bf88  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18007bf8c  ja      short loc_18007BF94
0x18007bf8e  call    cs:__imp_CloseHandle
0x18007bf94  mov     [rbx+70h], rdi
0x18007bf98  mov     rcx, rdi; Process
0x18007bf9b  call    cs:__imp_GetProcessId
0x18007bfa1  mov     [rbx+80h], eax
0x18007bfa7  call    cs:__imp_CoImpersonateClient
0x18007bfad  test    eax, eax
0x18007bfaf  js      loc_18007C0B1
0x18007bfb5  mov     [rbp+57h+var_D0], 1
0x18007bfb9  cmp     byte ptr [rbx+84h], 0
0x18007bfc0  jnz     loc_18007C0CD
0x18007bfc6  movaps  xmm0, xmmword ptr [rsi]
0x18007bfc9  movdqu  xmmword ptr [rbx+88h], xmm0
0x18007bfd1  lea     rdx, [rbx+0A8h]; struct _LUID *
0x18007bfd8  call    ?GetLogonSessionId@CPrinterExtensionServer@Driver@Print@@AEAAXPEAU_LUID@@@Z; Print::Driver::CPrinterExtensionServer::GetLogonSessionId(_LUID *)
0x18007bfdd  lea     rcx, [rbx+28h]
0x18007bfe1  mov     rax, [rcx]
0x18007bfe4  mov     rax, [rax+18h]
0x18007bfe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007bfed  mov     ebx, eax
0x18007bfef  test    eax, eax
0x18007bff1  js      short loc_18007C017
0x18007bff3  call    cs:__imp_CoRevertToSelf
0x18007bff9  test    eax, eax
0x18007bffb  jns     short loc_18007BFFF
0x18007bffd  int     2Ch; Windows NT - assertion failure
0x18007bfff  mov     rcx, [rbp+57h+var_30]
0x18007c003  xor     rcx, rsp; StackCookie
0x18007c006  call    __security_check_cookie
0x18007c00b  add     rsp, 0D8h
0x18007c012  pop     rdi
0x18007c013  pop     rsi
0x18007c014  pop     rbx
0x18007c015  pop     rbp
0x18007c016  retn
0x18007c017  lea     rax, WPP_GLOBAL_Control
0x18007c01e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c025  cmp     rcx, rax
0x18007c028  jz      short loc_18007C048
0x18007c02a  test    byte ptr [rcx+44h], 1
0x18007c02e  jz      short loc_18007C048
0x18007c030  mov     edx, 0Dh
0x18007c035  mov     r9d, ebx
0x18007c038  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007c03f  mov     rcx, [rcx+38h]
0x18007c043  call    WPP_SF_d
0x18007c048  mov     edx, ebx; int
0x18007c04a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007c04e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007c053  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007c05a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c05e  call    _CxxThrowException_0
0x18007c064  lea     rax, WPP_GLOBAL_Control
0x18007c06b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c072  cmp     rcx, rax
0x18007c075  jz      short loc_18007C095
0x18007c077  test    byte ptr [rcx+44h], 1
0x18007c07b  jz      short loc_18007C095
0x18007c07d  mov     edx, 0Bh
0x18007c082  mov     r9d, edi
0x18007c085  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007c08c  mov     rcx, [rcx+38h]
0x18007c090  call    WPP_SF_d
0x18007c095  mov     edx, edi; int
0x18007c097  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007c09b  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007c0a0  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007c0a7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c0ab  call    _CxxThrowException_0
0x18007c0b1  mov     edx, eax; int
0x18007c0b3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007c0b7  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007c0bc  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007c0c3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c0c7  call    _CxxThrowException_0
0x18007c0cd  lea     rax, WPP_GLOBAL_Control
0x18007c0d4  mov     ebx, 8000000Eh
0x18007c0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c0e0  cmp     rcx, rax
0x18007c0e3  jz      short loc_18007C103
0x18007c0e5  test    byte ptr [rcx+44h], 1
0x18007c0e9  jz      short loc_18007C103
0x18007c0eb  mov     edx, 0Ch
0x18007c0f0  mov     r9d, ebx
0x18007c0f3  lea     r8, WPP_4d8140841c7e336675fe9606cbcc23fc_Traceguids
0x18007c0fa  mov     rcx, [rcx+38h]
0x18007c0fe  call    WPP_SF_d
0x18007c103  mov     edx, ebx; int
0x18007c105  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18007c109  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18007c10e  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18007c115  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18007c119  call    _CxxThrowException_0
```
