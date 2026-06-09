# CreateDropWrapper(IDataObject *,IDataObject * *)

- ea: `0x1800c3fe0`
- end: `0x1800c4099`
- name: `?CreateDropWrapper@@YAJPEAUIDataObject@@PEAPEAU1@@Z`
- size: `185`
- prototype: `HRESULT __fastcall(IDataObject *pDataObject, IDataObject **ppWrappedDataObject)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800233b0`

## callees

- `0x1800901fc`
- `0x180091d44`
- `0x1800c3fe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c400d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c400d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c4020`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c4020`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4081`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4054`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4081`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800c4039`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800c4039`

## pseudocode

```c
__int64 __fastcall CreateDropWrapper(IDataObject *pDataObject, IDataObject **ppWrappedDataObject)
{
  HANDLE CurrentProcess; // rax
  int Error; // ebx
  void *hPrimaryToken; // [rsp+48h] [rbp+10h] BYREF
  void *hImpersonationToken; // [rsp+50h] [rbp+18h] BYREF

  *ppWrappedDataObject = 0;
  hImpersonationToken = 0;
  hPrimaryToken = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0xEu, &hPrimaryToken)
    || (Error = 0, !DuplicateToken(hPrimaryToken, SecurityImpersonation, &hImpersonationToken)) )
  {
    Error = ResultFromKnownLastError();
  }
  if ( hPrimaryToken )
    CloseHandle(hPrimaryToken);
  if ( Error >= 0 )
    Error = CBrokeredClipDataObject::Create(pDataObject, 0, 0, &hImpersonationToken, ppWrappedDataObject);
  if ( hImpersonationToken )
    CloseHandle(hImpersonationToken);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800c3fe0  mov     rax, rsp
0x1800c3fe3  mov     [rax+8], rbx
0x1800c3fe7  mov     [rax+20h], rsi
0x1800c3feb  push    rdi
0x1800c3fec  sub     rsp, 30h
0x1800c3ff0  mov     rdi, ppWrappedDataObject
0x1800c3ff3  mov     qword ptr [ppWrappedDataObject], 0
0x1800c3ffa  mov     rsi, pDataObject
0x1800c3ffd  mov     qword ptr [rax+18h], 0
0x1800c4005  mov     qword ptr [rax+10h], 0
0x1800c400d  call    cs:__imp_GetCurrentProcess
0x1800c4013  lea     r8, [rsp+38h+hPrimaryToken]; TokenHandle
0x1800c4018  mov     edx, 0Eh; DesiredAccess
0x1800c401d  mov     pDataObject, rax; ProcessHandle
0x1800c4020  call    cs:__imp_OpenProcessToken
0x1800c4026  test    eax, eax
0x1800c4028  jz      short loc_1800C4043
0x1800c402a  mov     pDataObject, [rsp+38h+hPrimaryToken]; ExistingTokenHandle
0x1800c402f  lea     r8, [rsp+38h+hImpersonationToken]; DuplicateTokenHandle
0x1800c4034  xor     ebx, ebx
0x1800c4036  lea     edx, [rbx+2]; ImpersonationLevel
0x1800c4039  call    cs:__imp_DuplicateToken
0x1800c403f  test    eax, eax
0x1800c4041  jnz     short loc_1800C404A
0x1800c4043  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c4048  mov     ebx, eax
0x1800c404a  mov     pDataObject, [rsp+38h+hPrimaryToken]; hObject
0x1800c404f  test    pDataObject, pDataObject
0x1800c4052  jz      short loc_1800C405A
0x1800c4054  call    cs:__imp_CloseHandle
0x1800c405a  test    ebx, ebx
0x1800c405c  js      short loc_1800C4077
0x1800c405e  lea     r9, [rsp+38h+hImpersonationToken]; phObjectOwnerToken
0x1800c4063  mov     [rsp+38h+ppDataObj], rdi; ppDataObj
0x1800c4068  xor     r8d, r8d; fOwnerIsPlmManaged
0x1800c406b  xor     edx, edx; dwSourceProcessId
0x1800c406d  mov     pDataObject, rsi; pInnerDataObject
0x1800c4070  call    ?Create@CBrokeredClipDataObject@@SAJPEAUIDataObject@@K_NPEAPEAXPEAPEAU2@@Z; CBrokeredClipDataObject::Create(IDataObject *,ulong,bool,void * *,IDataObject * *)
0x1800c4075  mov     ebx, eax
0x1800c4077  mov     pDataObject, [rsp+38h+hImpersonationToken]; hObject
0x1800c407c  test    pDataObject, pDataObject
0x1800c407f  jz      short loc_1800C4087
0x1800c4081  call    cs:__imp_CloseHandle
0x1800c4087  mov     rsi, [rsp+38h+arg_18]
0x1800c408c  mov     eax, ebx
0x1800c408e  mov     rbx, [rsp+38h+arg_0]
0x1800c4093  add     rsp, 30h
0x1800c4097  pop     rdi
0x1800c4098  retn
```
