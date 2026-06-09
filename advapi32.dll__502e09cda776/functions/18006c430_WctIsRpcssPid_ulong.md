# WctIsRpcssPid(ulong)

- ea: `0x18006c430`
- end: `0x18006c5e5`
- name: `?WctIsRpcssPid@@YAHK@Z`
- size: `437`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18003fddc`

## callees

- `0x18003fb18`
- `0x18003fcdc`
- `0x18003fd04`
- `0x18004165c`
- `0x18006c430`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18006c4c2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18006c4c2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18006c49c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18006c49c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006c584`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006c593`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006c584`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18006c593`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18006c4ee`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18006c565`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18006c4ee`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18006c565`
- `KERNEL32!GetLastError` at `0x18006c4fe`
- `KERNEL32!GetLastError` at `0x18006c4fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WctIsRpcssPid(int a1)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rsi
  SC_HANDLE v6; // rdi
  DWORD v7; // eax
  BYTE *v8; // r14
  DWORD cbBufSize; // [rsp+70h] [rbp+40h] BYREF
  BYTE *v11; // [rsp+78h] [rbp+48h] BYREF
  __int64 v12; // [rsp+80h] [rbp+50h] BYREF

  cbBufSize = 0;
  v11 = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  if ( a1 )
  {
    v4 = OpenSCManagerW(0, 0, 1u);
    v5 = v4;
    if ( !v4 )
    {
LABEL_17:
      v2 = WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    v6 = OpenServiceW(v4, L"RPCSS", 4u);
    if ( !v6 )
    {
LABEL_16:
      CloseServiceHandle(v5);
      goto LABEL_17;
    }
    if ( QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, 0, 0, &cbBufSize) )
    {
      v7 = 4096;
      cbBufSize = 4096;
    }
    else
    {
      if ( GetLastError() != 122 )
      {
LABEL_15:
        CloseServiceHandle(v6);
        goto LABEL_16;
      }
      v7 = cbBufSize;
    }
    v8 = (BYTE *)operator new(v7, (const struct std::nothrow_t *)&std::nothrow);
    v11 = 0;
    utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v11);
    v12 = 0;
    v11 = v8;
    utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v12);
    if ( v8 && QueryServiceStatusEx(v6, SC_STATUS_PROCESS_INFO, v8, cbBufSize, &cbBufSize) && a1 == *((_DWORD *)v8 + 7) )
      v3 = 1;
    goto LABEL_15;
  }
LABEL_18:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 4) != 0 )
    WPP_SF_d(v2[2], 37, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v3);
  utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v11);
  return v3;
}

```

## disassembly

```asm
0x18006c430  push    rbp
0x18006c432  push    rbx
0x18006c433  push    rsi
0x18006c434  push    rdi
0x18006c435  push    r13
0x18006c437  push    r14
0x18006c439  push    r15
0x18006c43b  mov     rbp, rsp
0x18006c43e  sub     rsp, 30h
0x18006c442  mov     r15d, ecx
0x18006c445  mov     [rbp+cbBufSize], 0
0x18006c44c  mov     [rbp+arg_8], 0
0x18006c454  lea     r13, WPP_GLOBAL_Control
0x18006c45b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c462  cmp     rcx, r13
0x18006c465  jz      short loc_18006C489
0x18006c467  test    byte ptr [rcx+1Ch], 4
0x18006c46b  jz      short loc_18006C489
0x18006c46d  mov     edx, 24h ; '$'
0x18006c472  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006c479  mov     rcx, [rcx+10h]
0x18006c47d  call    WPP_SF_
0x18006c482  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c489  xor     ebx, ebx
0x18006c48b  test    r15d, r15d
0x18006c48e  jz      loc_18006C5A6
0x18006c494  xor     edx, edx; lpDatabaseName
0x18006c496  xor     ecx, ecx; lpMachineName
0x18006c498  lea     r8d, [rbx+1]; dwDesiredAccess
0x18006c49c  call    cs:__imp_OpenSCManagerW
0x18006c4a3  nop     dword ptr [rax+rax+00h]
0x18006c4a8  mov     rsi, rax
0x18006c4ab  test    rax, rax
0x18006c4ae  jz      loc_18006C59F
0x18006c4b4  lea     r8d, [rbx+4]; dwDesiredAccess
0x18006c4b8  lea     rdx, aRpcss; "RPCSS"
0x18006c4bf  mov     rcx, rax; hSCManager
0x18006c4c2  call    cs:__imp_OpenServiceW
0x18006c4c9  nop     dword ptr [rax+rax+00h]
0x18006c4ce  mov     rdi, rax
0x18006c4d1  test    rax, rax
0x18006c4d4  jz      loc_18006C590
0x18006c4da  lea     rax, [rbp+cbBufSize]
0x18006c4de  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18006c4e3  xor     r9d, r9d; cbBufSize
0x18006c4e6  xor     r8d, r8d; lpBuffer
0x18006c4e9  xor     edx, edx; InfoLevel
0x18006c4eb  mov     rcx, rdi; hService
0x18006c4ee  call    cs:__imp_QueryServiceStatusEx
0x18006c4f5  nop     dword ptr [rax+rax+00h]
0x18006c4fa  test    eax, eax
0x18006c4fc  jnz     short loc_18006C514
0x18006c4fe  call    cs:__imp_GetLastError
0x18006c505  nop     dword ptr [rax+rax+00h]
0x18006c50a  cmp     eax, 7Ah ; 'z'
0x18006c50d  jnz     short loc_18006C581
0x18006c50f  mov     eax, [rbp+cbBufSize]
0x18006c512  jmp     short loc_18006C51C
0x18006c514  mov     eax, 1000h
0x18006c519  mov     [rbp+cbBufSize], eax
0x18006c51c  mov     ecx, eax; unsigned __int64
0x18006c51e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006c525  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006c52a  mov     r14, rax
0x18006c52d  mov     [rbp+arg_8], rbx
0x18006c531  lea     rcx, [rbp+arg_8]
0x18006c535  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18006c53a  mov     [rbp+arg_10], rbx
0x18006c53e  mov     [rbp+arg_8], r14
0x18006c542  lea     rcx, [rbp+arg_10]
0x18006c546  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18006c54b  test    r14, r14
0x18006c54e  jz      short loc_18006C581
0x18006c550  lea     rax, [rbp+cbBufSize]
0x18006c554  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18006c559  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x18006c55d  mov     r8, r14; lpBuffer
0x18006c560  xor     edx, edx; InfoLevel
0x18006c562  mov     rcx, rdi; hService
0x18006c565  call    cs:__imp_QueryServiceStatusEx
0x18006c56c  nop     dword ptr [rax+rax+00h]
0x18006c571  test    eax, eax
0x18006c573  jz      short loc_18006C581
0x18006c575  cmp     r15d, [r14+1Ch]
0x18006c579  mov     eax, 1
0x18006c57e  cmovz   ebx, eax
0x18006c581  mov     rcx, rdi; hSCObject
0x18006c584  call    cs:__imp_CloseServiceHandle
0x18006c58b  nop     dword ptr [rax+rax+00h]
0x18006c590  mov     rcx, rsi; hSCObject
0x18006c593  call    cs:__imp_CloseServiceHandle
0x18006c59a  nop     dword ptr [rax+rax+00h]
0x18006c59f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c5a6  cmp     rcx, r13
0x18006c5a9  jz      short loc_18006C5CA
0x18006c5ab  test    byte ptr [rcx+1Ch], 4
0x18006c5af  jz      short loc_18006C5CA
0x18006c5b1  mov     edx, 25h ; '%'
0x18006c5b6  mov     r9d, ebx
0x18006c5b9  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006c5c0  mov     rcx, [rcx+10h]
0x18006c5c4  call    WPP_SF_d
0x18006c5c9  nop
0x18006c5ca  lea     rcx, [rbp+arg_8]
0x18006c5ce  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18006c5d3  mov     eax, ebx
0x18006c5d5  add     rsp, 30h
0x18006c5d9  pop     r15
0x18006c5db  pop     r14
0x18006c5dd  pop     r13
0x18006c5df  pop     rdi
0x18006c5e0  pop     rsi
0x18006c5e1  pop     rbx
0x18006c5e2  pop     rbp
0x18006c5e3  retn
```
