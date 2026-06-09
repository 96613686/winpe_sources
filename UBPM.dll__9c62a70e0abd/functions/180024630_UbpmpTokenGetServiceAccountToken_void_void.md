# UbpmpTokenGetServiceAccountToken(void *,void * *)

- ea: `0x180024630`
- end: `0x180024731`
- name: `?UbpmpTokenGetServiceAccountToken@@YAKPEAXPEAPEAX@Z`
- size: `257`
- prototype: `unsigned int __fastcall(void *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x180023b50`

## callees

- `0x18000fbf0`
- `0x180024630`
- `0x180024740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002468b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002468b`
- `api-ms-win-service-private-l1-2-0!GetServiceProcessToken` at `0x1800246cc`
- `api-ms-win-service-private-l1-2-0!GetServiceProcessToken` at `0x1800246cc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180024677`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180024677`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024700`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024714`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024700`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180024714`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800246a9`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800246a9`

## pseudocode

```c
__int64 __fastcall UbpmpTokenGetServiceAccountToken(void *a1, void **a2)
{
  SC_HANDLE v2; // rsi
  SC_HANDLE v4; // rdi
  __int64 v5; // rdx
  DWORD AccountNamesFromSid; // ebx
  __int64 v7; // r8
  __int64 v8; // r9
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rax
  LPCWSTR lpServiceName; // [rsp+60h] [rbp+18h] BYREF
  void *v13; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  v13 = 0;
  lpServiceName = 0;
  v4 = 0;
  AccountNamesFromSid = UbpmUtilsGetAccountNamesFromSid((_DWORD)a1, 5, 0, (unsigned int)&lpServiceName, 0);
  if ( !AccountNamesFromSid )
  {
    v9 = OpenSCManagerW(0, 0, 1u);
    v2 = v9;
    if ( v9 && (v10 = OpenServiceW(v9, lpServiceName, 0xF01FFu), (v4 = v10) != 0) )
    {
      AccountNamesFromSid = GetServiceProcessToken(g_ScheduleServiceHandle, v10, &v13);
      if ( !AccountNamesFromSid )
        *a2 = v13;
    }
    else
    {
      AccountNamesFromSid = GetLastError();
    }
  }
  if ( lpServiceName )
    UBPM_MIDL_user_free(lpServiceName, v5, v7, v8);
  if ( v2 )
    CloseServiceHandle(v2);
  if ( v4 )
    CloseServiceHandle(v4);
  return AccountNamesFromSid;
}

```

## disassembly

```asm
0x180024630  mov     rax, rsp
0x180024633  mov     [rax+8], rbx
0x180024637  push    rsi
0x180024638  push    rdi
0x180024639  push    r14
0x18002463b  sub     rsp, 30h
0x18002463f  xor     esi, esi
0x180024641  mov     qword ptr [rax+20h], 0
0x180024649  mov     r14, rdx
0x18002464c  mov     qword ptr [rax+18h], 0
0x180024654  lea     r9, [rax+18h]
0x180024658  mov     [rax-28h], rsi
0x18002465c  xor     r8d, r8d
0x18002465f  xor     edi, edi
0x180024661  lea     edx, [rsi+5]
0x180024664  call    UbpmUtilsGetAccountNamesFromSid
0x180024669  mov     ebx, eax
0x18002466b  test    eax, eax
0x18002466d  jnz     short loc_1800246E6
0x18002466f  xor     edx, edx; lpDatabaseName
0x180024671  lea     r8d, [rsi+1]; dwDesiredAccess
0x180024675  xor     ecx, ecx; lpMachineName
0x180024677  call    cs:__imp_OpenSCManagerW
0x18002467e  nop     dword ptr [rax+rax+00h]
0x180024683  mov     rsi, rax
0x180024686  test    rax, rax
0x180024689  jnz     short loc_18002469B
0x18002468b  call    cs:__imp_GetLastError
0x180024692  nop     dword ptr [rax+rax+00h]
0x180024697  mov     ebx, eax
0x180024699  jmp     short loc_1800246E6
0x18002469b  mov     rdx, [rsp+48h+lpServiceName]; lpServiceName
0x1800246a0  mov     r8d, 0F01FFh; dwDesiredAccess
0x1800246a6  mov     rcx, rax; hSCManager
0x1800246a9  call    cs:__imp_OpenServiceW
0x1800246b0  nop     dword ptr [rax+rax+00h]
0x1800246b5  mov     rdi, rax
0x1800246b8  test    rax, rax
0x1800246bb  jz      short loc_18002468B
0x1800246bd  mov     rcx, cs:g_ScheduleServiceHandle
0x1800246c4  lea     r8, [rsp+48h+arg_18]
0x1800246c9  mov     rdx, rax
0x1800246cc  call    cs:__imp_GetServiceProcessToken
0x1800246d3  nop     dword ptr [rax+rax+00h]
0x1800246d8  mov     ebx, eax
0x1800246da  test    eax, eax
0x1800246dc  jnz     short loc_1800246E6
0x1800246de  mov     rax, [rsp+48h+arg_18]
0x1800246e3  mov     [r14], rax
0x1800246e6  cmp     [rsp+48h+lpServiceName], 0
0x1800246ec  jz      short loc_1800246F8
0x1800246ee  mov     rcx, [rsp+48h+lpServiceName]
0x1800246f3  call    UBPM_MIDL_user_free
0x1800246f8  test    rsi, rsi
0x1800246fb  jz      short loc_18002470C
0x1800246fd  mov     rcx, rsi; hSCObject
0x180024700  call    cs:__imp_CloseServiceHandle
0x180024707  nop     dword ptr [rax+rax+00h]
0x18002470c  test    rdi, rdi
0x18002470f  jz      short loc_180024720
0x180024711  mov     rcx, rdi; hSCObject
0x180024714  call    cs:__imp_CloseServiceHandle
0x18002471b  nop     dword ptr [rax+rax+00h]
0x180024720  mov     eax, ebx
0x180024722  mov     rbx, [rsp+48h+arg_0]
0x180024727  add     rsp, 30h
0x18002472b  pop     r14
0x18002472d  pop     rdi
0x18002472e  pop     rsi
0x18002472f  retn
```
