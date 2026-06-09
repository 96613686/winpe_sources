# Windows::Internal::DialogBlocking::HookMgr::CreateStopEvent(void)

- ea: `0x180008da8`
- end: `0x180008ec0`
- name: `?CreateStopEvent@HookMgr@DialogBlocking@Internal@Windows@@AEAA_NXZ`
- size: `280`
- prototype: `char __fastcall(Windows::Internal::DialogBlocking::HookMgr *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180008b04`

## callees

- `0x180007d1c`
- `0x180008da8`
- `0x18000954c`
- `0x18000ab20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008e70`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008e21`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180008e21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008e5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e41`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008ddb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180008ddb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008e4d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008e97`

## pseudocode

```c
char __fastcall Windows::Internal::DialogBlocking::HookMgr::CreateStopEvent(
        Windows::Internal::DialogBlocking::HookMgr *this)
{
  char v2; // bl
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  void **v6; // rsi
  HANDLE v7; // r15
  void *v8; // rdi
  DWORD LastError; // r14d
  __int64 v10; // r8
  const char *v11; // r9
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR lpName[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+98h] [rbp+40h] BYREF

  SecurityDescriptor = 0;
  v2 = 1;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GA;;;WD)(D;;WOWD;;;WD)",
          1u,
          &SecurityDescriptor,
          0) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v3, v4, v5);
  *(_QWORD *)&EventAttributes.nLength = 24;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
  Windows::Internal::DialogBlocking::Consts::ShutdownEventName(lpName, *(unsigned int *)this);
  v6 = (void **)*((_QWORD *)this + 1);
  v7 = CreateEventExW(&EventAttributes, lpName[0], 1u, 0x1F0003u);
  if ( v7 )
  {
    GetLastError();
    v8 = *v6;
    if ( *v6 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
      SetLastError(LastError);
    }
    *v6 = v7;
  }
  else
  {
    v2 = 0;
  }
  if ( lpName[0] )
  {
    CoTaskMemFree((LPVOID)lpName[0]);
    lpName[0] = 0;
  }
  lpName[1] = 0;
  lpName[2] = 0;
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x180008da8  push    rbp
0x180008daa  push    rbx
0x180008dab  push    rsi
0x180008dac  push    rdi
0x180008dad  push    r14
0x180008daf  push    r15
0x180008db1  mov     rbp, rsp
0x180008db4  sub     rsp, 58h
0x180008db8  mov     rsi, rcx
0x180008dbb  mov     [rbp+SecurityDescriptor], 0
0x180008dc3  mov     rdi, [rbp+30h]
0x180008dc7  xor     r9d, r9d; SecurityDescriptorSize
0x180008dca  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180008dce  lea     ebx, [r9+1]
0x180008dd2  mov     edx, ebx; StringSDRevision
0x180008dd4  lea     rcx, aDAGaWdDWowdWd; "D:(A;;GA;;;WD)(D;;WOWD;;;WD)"
0x180008ddb  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180008de1  test    eax, eax
0x180008de3  jz      loc_180008EB7
0x180008de9  mov     qword ptr [rbp+EventAttributes.nLength], 18h
0x180008df1  mov     qword ptr [rbp+EventAttributes.bInheritHandle], 0
0x180008df9  mov     rax, [rbp+SecurityDescriptor]
0x180008dfd  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x180008e01  mov     edx, [rsi]
0x180008e03  lea     rcx, [rbp+lpName]
0x180008e07  call    ?ShutdownEventName@Consts@DialogBlocking@Internal@Windows@@SA?AV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@34@K@Z; Windows::Internal::DialogBlocking::Consts::ShutdownEventName(ulong)
0x180008e0c  mov     rsi, [rsi+8]
0x180008e10  mov     r9d, 1F0003h; dwDesiredAccess
0x180008e16  mov     r8d, ebx; dwFlags
0x180008e19  mov     rdx, [rbp+lpName]; lpName
0x180008e1d  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x180008e21  call    cs:__imp_CreateEventExW
0x180008e27  mov     r15, rax
0x180008e2a  test    rax, rax
0x180008e2d  jnz     short loc_180008E33
0x180008e2f  xor     bl, bl
0x180008e31  jmp     short loc_180008E67
0x180008e33  call    cs:__imp_GetLastError
0x180008e39  mov     rdi, [rsi]
0x180008e3c  test    rdi, rdi
0x180008e3f  jz      short loc_180008E64
0x180008e41  call    cs:__imp_GetLastError
0x180008e47  mov     r14d, eax
0x180008e4a  mov     rcx, rdi; hObject
0x180008e4d  call    cs:__imp_CloseHandle
0x180008e53  mov     rcx, [rbp+30h]; this
0x180008e57  test    eax, eax
0x180008e59  jz      short loc_180008EAC
0x180008e5b  mov     ecx, r14d; dwErrCode
0x180008e5e  call    cs:__imp_SetLastError
0x180008e64  mov     [rsi], r15
0x180008e67  mov     rcx, [rbp+lpName]; pv
0x180008e6b  test    rcx, rcx
0x180008e6e  jz      short loc_180008E7E
0x180008e70  call    cs:__imp_CoTaskMemFree
0x180008e76  mov     [rbp+lpName], 0
0x180008e7e  mov     [rbp+var_18], 0
0x180008e86  mov     [rbp+var_10], 0
0x180008e8e  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180008e92  test    rcx, rcx
0x180008e95  jz      short loc_180008E9D
0x180008e97  call    cs:__imp_LocalFree
0x180008e9d  mov     al, bl
0x180008e9f  add     rsp, 58h
0x180008ea3  pop     r15
0x180008ea5  pop     r14
0x180008ea7  pop     rdi
0x180008ea8  pop     rsi
0x180008ea9  pop     rbx
0x180008eaa  pop     rbp
0x180008eab  retn
0x180008eac  mov     edx, 0A0Bh; void *
0x180008eb1  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180008eb7  mov     rcx, rdi; this
0x180008eba  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
