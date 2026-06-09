# WctIsRpcssPid(ulong)

- ea: `0x18005fb78`
- end: `0x18005fd02`
- name: `?WctIsRpcssPid@@YAHK@Z`
- size: `394`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18003b80c`

## callees

- `0x18003b57c`
- `0x18003b728`
- `0x18003b748`
- `0x18003d048`
- `0x18005fb78`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005fc04`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005fc04`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005fbe4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18005fbe4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005fcae`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005fcb7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005fcae`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18005fcb7`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005fc2a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005fc95`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005fc2a`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18005fc95`
- `KERNEL32!GetLastError` at `0x18005fc34`
- `KERNEL32!GetLastError` at `0x18005fc34`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
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
    WPP_SF_d(v2[2], 37, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v3);
  utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(&v11);
  return v3;
}

```

## disassembly

```asm
0x18005fb78  push    rbp
0x18005fb7a  push    rbx
0x18005fb7b  push    rsi
0x18005fb7c  push    rdi
0x18005fb7d  push    r13
0x18005fb7f  push    r14
0x18005fb81  push    r15
0x18005fb83  mov     rbp, rsp
0x18005fb86  sub     rsp, 30h
0x18005fb8a  mov     r15d, ecx
0x18005fb8d  mov     [rbp+cbBufSize], 0
0x18005fb94  mov     [rbp+arg_8], 0
0x18005fb9c  lea     r13, WPP_GLOBAL_Control
0x18005fba3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fbaa  cmp     rcx, r13
0x18005fbad  jz      short loc_18005FBD1
0x18005fbaf  test    byte ptr [rcx+1Ch], 4
0x18005fbb3  jz      short loc_18005FBD1
0x18005fbb5  mov     edx, 24h ; '$'
0x18005fbba  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005fbc1  mov     rcx, [rcx+10h]
0x18005fbc5  call    WPP_SF_
0x18005fbca  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fbd1  xor     ebx, ebx
0x18005fbd3  test    r15d, r15d
0x18005fbd6  jz      loc_18005FCC4
0x18005fbdc  xor     edx, edx; lpDatabaseName
0x18005fbde  xor     ecx, ecx; lpMachineName
0x18005fbe0  lea     r8d, [rbx+1]; dwDesiredAccess
0x18005fbe4  call    cs:__imp_OpenSCManagerW
0x18005fbea  mov     rsi, rax
0x18005fbed  test    rax, rax
0x18005fbf0  jz      loc_18005FCBD
0x18005fbf6  lea     r8d, [rbx+4]; dwDesiredAccess
0x18005fbfa  lea     rdx, aRpcss; "RPCSS"
0x18005fc01  mov     rcx, rax; hSCManager
0x18005fc04  call    cs:__imp_OpenServiceW
0x18005fc0a  mov     rdi, rax
0x18005fc0d  test    rax, rax
0x18005fc10  jz      loc_18005FCB4
0x18005fc16  lea     rax, [rbp+cbBufSize]
0x18005fc1a  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005fc1f  xor     r9d, r9d; cbBufSize
0x18005fc22  xor     r8d, r8d; lpBuffer
0x18005fc25  xor     edx, edx; InfoLevel
0x18005fc27  mov     rcx, rdi; hService
0x18005fc2a  call    cs:__imp_QueryServiceStatusEx
0x18005fc30  test    eax, eax
0x18005fc32  jnz     short loc_18005FC44
0x18005fc34  call    cs:__imp_GetLastError
0x18005fc3a  cmp     eax, 7Ah ; 'z'
0x18005fc3d  jnz     short loc_18005FCAB
0x18005fc3f  mov     eax, [rbp+cbBufSize]
0x18005fc42  jmp     short loc_18005FC4C
0x18005fc44  mov     eax, 1000h
0x18005fc49  mov     [rbp+cbBufSize], eax
0x18005fc4c  mov     ecx, eax; unsigned __int64
0x18005fc4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005fc55  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005fc5a  mov     r14, rax
0x18005fc5d  mov     [rbp+arg_8], rbx
0x18005fc61  lea     rcx, [rbp+arg_8]
0x18005fc65  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18005fc6a  mov     [rbp+arg_10], rbx
0x18005fc6e  mov     [rbp+arg_8], r14
0x18005fc72  lea     rcx, [rbp+arg_10]
0x18005fc76  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18005fc7b  test    r14, r14
0x18005fc7e  jz      short loc_18005FCAB
0x18005fc80  lea     rax, [rbp+cbBufSize]
0x18005fc84  mov     [rsp+30h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18005fc89  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x18005fc8d  mov     r8, r14; lpBuffer
0x18005fc90  xor     edx, edx; InfoLevel
0x18005fc92  mov     rcx, rdi; hService
0x18005fc95  call    cs:__imp_QueryServiceStatusEx
0x18005fc9b  test    eax, eax
0x18005fc9d  jz      short loc_18005FCAB
0x18005fc9f  cmp     r15d, [r14+1Ch]
0x18005fca3  mov     eax, 1
0x18005fca8  cmovz   ebx, eax
0x18005fcab  mov     rcx, rdi; hSCObject
0x18005fcae  call    cs:__imp_CloseServiceHandle
0x18005fcb4  mov     rcx, rsi; hSCObject
0x18005fcb7  call    cs:__imp_CloseServiceHandle
0x18005fcbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fcc4  cmp     rcx, r13
0x18005fcc7  jz      short loc_18005FCE8
0x18005fcc9  test    byte ptr [rcx+1Ch], 4
0x18005fccd  jz      short loc_18005FCE8
0x18005fccf  mov     edx, 25h ; '%'
0x18005fcd4  mov     r9d, ebx
0x18005fcd7  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005fcde  mov     rcx, [rcx+10h]
0x18005fce2  call    WPP_SF_d
0x18005fce7  nop
0x18005fce8  lea     rcx, [rbp+arg_8]
0x18005fcec  call    ??1?$unique_ptr@U_OBJECT_NAME_INFORMATION@@U?$generic_delete@U_OBJECT_NAME_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>::~unique_ptr<_OBJECT_NAME_INFORMATION,tlx::generic_delete<_OBJECT_NAME_INFORMATION,tlx::operator_delete_deallocate>>(void)
0x18005fcf1  mov     eax, ebx
0x18005fcf3  add     rsp, 30h
0x18005fcf7  pop     r15
0x18005fcf9  pop     r14
0x18005fcfb  pop     r13
0x18005fcfd  pop     rdi
0x18005fcfe  pop     rsi
0x18005fcff  pop     rbx
0x18005fd00  pop     rbp
0x18005fd01  retn
```
