# CServiceManager::CServiceManager(ushort const *,ulong,ushort const *)

- ea: `0x180022620`
- end: `0x180022798`
- name: `??0CServiceManager@@QEAA@PEBGK0@Z`
- size: `376`
- prototype: `CServiceManager *(CServiceManager *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180035f40`
- `0x180045d94`

## callees

- `0x180022620`
- `0x18002a200`
- `0x18003336c`
- `0x180044a60`
- `0x180044ac0`
- `0x18004504c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022719`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002272a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002272a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002270a`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002270a`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800226ac`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800226ac`

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
0x180022620  mov     [rsp+arg_0], rbx
0x180022625  mov     [rsp+arg_8], rbp
0x18002262a  mov     [rsp+pExceptionObject], r9
0x18002262f  push    rsi
0x180022630  push    rdi
0x180022631  push    r14
0x180022633  sub     rsp, 30h
0x180022637  mov     ebp, r8d
0x18002263a  mov     rsi, rdx
0x18002263d  mov     rbx, rcx
0x180022640  mov     rcx, cs:WPP_GLOBAL_Control
0x180022647  lea     r14, WPP_GLOBAL_Control
0x18002264e  cmp     rcx, r14
0x180022651  jz      short loc_1800226A4
0x180022653  test    byte ptr [rcx+1Ch], 8
0x180022657  jz      short loc_180022675
0x180022659  mov     rcx, [rcx+10h]
0x18002265d  lea     r8, WPP_f638107a045a363b0e191b757df6914a_Traceguids
0x180022664  mov     edx, 0Dh
0x180022669  call    WPP_SF_
0x18002266e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022675  cmp     rcx, r14
0x180022678  jz      short loc_1800226A4
0x18002267a  test    byte ptr [rcx+1Ch], 4
0x18002267e  jz      short loc_1800226A4
0x180022680  mov     rcx, [rcx+10h]
0x180022684  lea     rax, Format
0x18002268b  mov     edx, 0Eh
0x180022690  mov     [rsp+48h+var_28], rax
0x180022695  mov     r9, rsi
0x180022698  lea     r8, WPP_f638107a045a363b0e191b757df6914a_Traceguids
0x18002269f  call    WPP_SF_SS
0x1800226a4  xor     edx, edx; lpDatabaseName
0x1800226a6  xor     ecx, ecx; lpMachineName
0x1800226a8  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800226ac  call    cs:__imp_OpenSCManagerW
0x1800226b3  nop     dword ptr [rax+rax+00h]
0x1800226b8  mov     rdi, rax
0x1800226bb  test    rax, rax
0x1800226be  jnz     short loc_180022701
0x1800226c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800226c7  cmp     rcx, r14
0x1800226ca  jz      short loc_1800226E5
0x1800226cc  test    byte ptr [rcx+1Ch], 1
0x1800226d0  jz      short loc_1800226E5
0x1800226d2  mov     rcx, [rcx+10h]
0x1800226d6  lea     edx, [rax+0Fh]
0x1800226d9  lea     r8, WPP_f638107a045a363b0e191b757df6914a_Traceguids
0x1800226e0  call    WPP_SF_
0x1800226e5  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800226ea  call    ??0CServiceManagerException@@QEAA@XZ; CServiceManagerException::CServiceManagerException(void)
0x1800226ef  lea     rdx, _TI1?AVCServiceManagerException@@; pThrowInfo
0x1800226f6  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800226fb  call    _CxxThrowException_0
0x180022701  mov     r8d, ebp; dwDesiredAccess
0x180022704  mov     rdx, rsi; lpServiceName
0x180022707  mov     rcx, rdi; hSCManager
0x18002270a  call    cs:__imp_OpenServiceW
0x180022711  nop     dword ptr [rax+rax+00h]
0x180022716  mov     [rbx], rax
0x180022719  call    cs:__imp_GetLastError
0x180022720  nop     dword ptr [rax+rax+00h]
0x180022725  mov     rcx, rdi; hSCObject
0x180022728  mov     esi, eax
0x18002272a  call    cs:__imp_CloseServiceHandle
0x180022731  nop     dword ptr [rax+rax+00h]
0x180022736  cmp     qword ptr [rbx], 0
0x18002273a  jnz     short loc_180022781
0x18002273c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022743  cmp     rcx, r14
0x180022746  jz      short loc_180022763
0x180022748  test    byte ptr [rcx+1Ch], 1
0x18002274c  jz      short loc_180022763
0x18002274e  mov     rcx, [rcx+10h]
0x180022752  lea     r8, WPP_f638107a045a363b0e191b757df6914a_Traceguids
0x180022759  mov     edx, 10h
0x18002275e  call    WPP_SF_
0x180022763  mov     edx, esi; unsigned int
0x180022765  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18002276a  call    ??0CServiceManagerException@@QEAA@K@Z; CServiceManagerException::CServiceManagerException(ulong)
0x18002276f  lea     rdx, _TI1?AVCServiceManagerException@@; pThrowInfo
0x180022776  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18002277b  call    _CxxThrowException_0
0x180022781  mov     rbp, [rsp+48h+arg_8]
0x180022786  mov     rax, rbx
0x180022789  mov     rbx, [rsp+48h+arg_0]
0x18002278e  add     rsp, 30h
0x180022792  pop     r14
0x180022794  pop     rdi
0x180022795  pop     rsi
0x180022796  retn
```
