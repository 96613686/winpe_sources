# ResolveServices(SERVICES_MANAGER *)

- ea: `0x18002e468`
- end: `0x18002e551`
- name: `?ResolveServices@@YAJPEAVSERVICES_MANAGER@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(struct SERVICES_MANAGER *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180025170`

## callees

- `0x18002cedc`
- `0x18002e468`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e493`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002e485`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18002e485`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002e4c3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002e4f4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002e4c3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18002e4f4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e4db`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e50b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e514`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e4db`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e50b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002e514`

## pseudocode

```c
signed int __fastcall ResolveServices(struct SERVICES_MANAGER *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  signed int result; // eax
  unsigned int v5; // edi
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rax
  __int64 v8; // rcx
  __int64 i; // rbx
  unsigned __int16 *v10[2]; // [rsp+20h] [rbp-38h]

  *(_OWORD *)v10 = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = 0;
    v6 = OpenServiceW(v2, L"IISADMIN", 0xF01FFu);
    if ( v6 )
    {
      v10[0] = L"IISADMIN";
      v5 = 1;
      CloseServiceHandle(v6);
    }
    v7 = OpenServiceW(v3, L"WAS", 0xF01FFu);
    if ( v7 )
    {
      v8 = v5++;
      v10[v8] = L"WAS";
      CloseServiceHandle(v7);
    }
    CloseServiceHandle(v3);
    if ( *(_DWORD *)this )
    {
      return -2147467259;
    }
    else
    {
      result = 0;
      for ( i = 0; (unsigned int)i < v5; i = (unsigned int)(i + 1) )
      {
        result = SERVICES_MANAGER::InsertServiceName(this, v10[i]);
        if ( result < 0 )
          break;
        ++*(_DWORD *)this;
      }
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002e468  push    rbx
0x18002e46a  push    rsi
0x18002e46b  push    rdi
0x18002e46c  push    r14
0x18002e46e  sub     rsp, 38h
0x18002e472  xor     edx, edx; lpDatabaseName
0x18002e474  mov     rsi, rcx
0x18002e477  xorps   xmm0, xmm0
0x18002e47a  xor     ecx, ecx; lpMachineName
0x18002e47c  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18002e481  lea     r8d, [rdx+1]; dwDesiredAccess
0x18002e485  call    cs:__imp_OpenSCManagerW
0x18002e48b  mov     rbx, rax
0x18002e48e  test    rax, rax
0x18002e491  jnz     short loc_18002E4AE
0x18002e493  call    cs:__imp_GetLastError
0x18002e499  test    eax, eax
0x18002e49b  jle     loc_18002E547
0x18002e4a1  movzx   eax, ax
0x18002e4a4  or      eax, 80070000h
0x18002e4a9  jmp     loc_18002E547
0x18002e4ae  lea     r14, ServiceName; "IISADMIN"
0x18002e4b5  mov     r8d, 0F01FFh; dwDesiredAccess
0x18002e4bb  mov     rdx, r14; lpServiceName
0x18002e4be  mov     rcx, rbx; hSCManager
0x18002e4c1  xor     edi, edi
0x18002e4c3  call    cs:__imp_OpenServiceW
0x18002e4c9  test    rax, rax
0x18002e4cc  jz      short loc_18002E4E1
0x18002e4ce  mov     rcx, rax; hSCObject
0x18002e4d1  mov     [rsp+58h+var_38], r14
0x18002e4d6  mov     edi, 1
0x18002e4db  call    cs:__imp_CloseServiceHandle
0x18002e4e1  lea     r14, aWas; "WAS"
0x18002e4e8  mov     r8d, 0F01FFh; dwDesiredAccess
0x18002e4ee  mov     rdx, r14; lpServiceName
0x18002e4f1  mov     rcx, rbx; hSCManager
0x18002e4f4  call    cs:__imp_OpenServiceW
0x18002e4fa  test    rax, rax
0x18002e4fd  jz      short loc_18002E511
0x18002e4ff  mov     ecx, edi
0x18002e501  inc     edi
0x18002e503  mov     [rsp+rcx*8+58h+var_38], r14
0x18002e508  mov     rcx, rax; hSCObject
0x18002e50b  call    cs:__imp_CloseServiceHandle
0x18002e511  mov     rcx, rbx; hSCObject
0x18002e514  call    cs:__imp_CloseServiceHandle
0x18002e51a  cmp     dword ptr [rsi], 0
0x18002e51d  jz      short loc_18002E526
0x18002e51f  mov     eax, 80004005h
0x18002e524  jmp     short loc_18002E547
0x18002e526  xor     eax, eax
0x18002e528  xor     ebx, ebx
0x18002e52a  test    edi, edi
0x18002e52c  jz      short loc_18002E547
0x18002e52e  mov     rdx, [rsp+rbx*8+58h+var_38]; unsigned __int16 *
0x18002e533  mov     rcx, rsi; this
0x18002e536  call    ?InsertServiceName@SERVICES_MANAGER@@AEAAJPEAG@Z; SERVICES_MANAGER::InsertServiceName(ushort *)
0x18002e53b  test    eax, eax
0x18002e53d  js      short loc_18002E547
0x18002e53f  inc     dword ptr [rsi]
0x18002e541  inc     ebx
0x18002e543  cmp     ebx, edi
0x18002e545  jb      short loc_18002E52E
0x18002e547  add     rsp, 38h
0x18002e54b  pop     r14
0x18002e54d  pop     rdi
0x18002e54e  pop     rsi
0x18002e54f  pop     rbx
0x18002e550  retn
```
