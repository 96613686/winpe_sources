# CServiceManager::CServiceManager(ushort const *,ulong,ushort const *)

- ea: `0x180020e48`
- end: `0x180020fa7`
- name: `??0CServiceManager@@QEAA@PEBGK0@Z`
- size: `351`
- prototype: `CServiceManager *(CServiceManager *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180033950`
- `0x1800429c0`

## callees

- `0x180020e48`
- `0x1800284d0`
- `0x18003104c`
- `0x180041778`
- `0x1800417d4`
- `0x180041d1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020f35`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180020f40`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180020f40`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180020f2c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180020f2c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180020ed4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180020ed4`

## pseudocode

```c
CServiceManager *__fastcall CServiceManager::CServiceManager(
        CServiceManager *this,
        const unsigned __int16 *a2,
        DWORD a3,
        const unsigned __int16 *a4)
{
  FwPolicy2 *v7; // rcx
  SC_HANDLE v8; // rax
  SC_HANDLE v9; // rdi
  DWORD LastError; // esi
  const unsigned __int16 *pExceptionObject; // [rsp+68h] [rbp+20h] BYREF

  pExceptionObject = a4;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f638107a045a363b0e191b757df6914a_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 4) != 0 )
      WPP_SF_SS(
        *((_QWORD *)v7 + 2),
        14,
        (unsigned int)WPP_f638107a045a363b0e191b757df6914a_Traceguids,
        (_DWORD)a2,
        (__int64)&Format);
  }
  v8 = OpenSCManagerW(0, 0, 1u);
  v9 = v8;
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f638107a045a363b0e191b757df6914a_Traceguids);
    CServiceManagerException::CServiceManagerException((CServiceManagerException *)&pExceptionObject);
    throw (CServiceManagerException *)&pExceptionObject;
  }
  *(_QWORD *)this = OpenServiceW(v8, a2, a3);
  LastError = GetLastError();
  CloseServiceHandle(v9);
  if ( !*(_QWORD *)this )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_f638107a045a363b0e191b757df6914a_Traceguids);
    CServiceManagerException::CServiceManagerException((CServiceManagerException *)&pExceptionObject, LastError);
    throw (CServiceManagerException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180020e48  mov     [rsp+arg_0], rbx
0x180020e4d  mov     [rsp+arg_8], rbp
0x180020e52  mov     [rsp+pExceptionObject], r9
0x180020e57  push    rsi
0x180020e58  push    rdi
0x180020e59  push    r14
0x180020e5b  sub     rsp, 30h
0x180020e5f  mov     ebp, r8d
0x180020e62  mov     rsi, rdx
0x180020e65  mov     rbx, rcx
0x180020e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e6f  lea     r14, WPP_GLOBAL_Control
0x180020e76  cmp     rcx, r14
0x180020e79  jz      short loc_180020ECC
0x180020e7b  test    byte ptr [rcx+1Ch], 8
0x180020e7f  jz      short loc_180020E9D
0x180020e81  mov     rcx, [rcx+10h]
0x180020e85  lea     r8, WPP_f638107a045a363b0e191b757df6914a_Traceguids
0x180020e8c  mov     edx, 0Dh
0x180020e91  call    WPP_SF_
0x180020e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e9d  cmp     rcx, r14
0x180020ea0  jz      short loc_180020ECC
0x180020ea2  test    byte ptr [rcx+1Ch], 4
0x180020ea6  jz      short loc_180020ECC
0x180020ea8  mov     rcx, [rcx+10h]
0x180020eac  lea     rax, Format
0x180020eb3  mov     edx, 0Eh
0x180020eb8  mov     [rsp+48h+var_28], rax
0x180020ebd  mov     r9, rsi
0x180020ec0  lea     r8, WPP_f638107a045a363b0e191b757df6914a_Traceguids
0x180020ec7  call    WPP_SF_SS
0x180020ecc  xor     edx, edx; lpDatabaseName
0x180020ece  xor     ecx, ecx; lpMachineName
0x180020ed0  lea     r8d, [rdx+1]; dwDesiredAccess
0x180020ed4  call    cs:__imp_OpenSCManagerW
0x180020eda  mov     rdi, rax
0x180020edd  test    rax, rax
0x180020ee0  jnz     short loc_180020F23
0x180020ee2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ee9  cmp     rcx, r14
0x180020eec  jz      short loc_180020F07
0x180020eee  test    byte ptr [rcx+1Ch], 1
0x180020ef2  jz      short loc_180020F07
0x180020ef4  mov     rcx, [rcx+10h]
0x180020ef8  lea     edx, [rax+0Fh]
0x180020efb  lea     r8, WPP_f638107a045a363b0e191b757df6914a_Traceguids
0x180020f02  call    WPP_SF_
0x180020f07  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180020f0c  call    ??0CServiceManagerException@@QEAA@XZ; CServiceManagerException::CServiceManagerException(void)
0x180020f11  lea     rdx, _TI1?AVCServiceManagerException@@; pThrowInfo
0x180020f18  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180020f1d  call    _CxxThrowException_0
0x180020f23  mov     r8d, ebp; dwDesiredAccess
0x180020f26  mov     rdx, rsi; lpServiceName
0x180020f29  mov     rcx, rdi; hSCManager
0x180020f2c  call    cs:__imp_OpenServiceW
0x180020f32  mov     [rbx], rax
0x180020f35  call    cs:__imp_GetLastError
0x180020f3b  mov     rcx, rdi; hSCObject
0x180020f3e  mov     esi, eax
0x180020f40  call    cs:__imp_CloseServiceHandle
0x180020f46  cmp     qword ptr [rbx], 0
0x180020f4a  jnz     short loc_180020F91
0x180020f4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f53  cmp     rcx, r14
0x180020f56  jz      short loc_180020F73
0x180020f58  test    byte ptr [rcx+1Ch], 1
0x180020f5c  jz      short loc_180020F73
0x180020f5e  mov     rcx, [rcx+10h]
0x180020f62  lea     r8, WPP_f638107a045a363b0e191b757df6914a_Traceguids
0x180020f69  mov     edx, 10h
0x180020f6e  call    WPP_SF_
0x180020f73  mov     edx, esi; unsigned int
0x180020f75  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180020f7a  call    ??0CServiceManagerException@@QEAA@K@Z; CServiceManagerException::CServiceManagerException(ulong)
0x180020f7f  lea     rdx, _TI1?AVCServiceManagerException@@; pThrowInfo
0x180020f86  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180020f8b  call    _CxxThrowException_0
0x180020f91  mov     rbp, [rsp+48h+arg_8]
0x180020f96  mov     rax, rbx
0x180020f99  mov     rbx, [rsp+48h+arg_0]
0x180020f9e  add     rsp, 30h
0x180020fa2  pop     r14
0x180020fa4  pop     rdi
0x180020fa5  pop     rsi
0x180020fa6  retn
```
