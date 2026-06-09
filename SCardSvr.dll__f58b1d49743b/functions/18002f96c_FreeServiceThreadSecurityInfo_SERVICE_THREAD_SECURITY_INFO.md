# FreeServiceThreadSecurityInfo(_SERVICE_THREAD_SECURITY_INFO * *)

- ea: `0x18002f96c`
- end: `0x18002f9fe`
- name: `?FreeServiceThreadSecurityInfo@@YAKPEAPEAU_SERVICE_THREAD_SECURITY_INFO@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(void ***)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800186d0`
- `0x1800188fc`
- `0x18002f64c`

## callees

- `0x18002f96c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f9e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002f9e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002f9d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f9c8`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f984`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f99a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f9b1`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f984`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f99a`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18002f9b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FreeServiceThreadSecurityInfo(void ***a1)
{
  void **v1; // rbx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  HANDLE ProcessHeap; // rax
  __int64 result; // rax

  v1 = *a1;
  v3 = **a1;
  if ( v3 )
  {
    FreeSid(v3);
    *v1 = 0;
  }
  v4 = v1[1];
  if ( v4 )
  {
    FreeSid(v4);
    v1[1] = 0;
  }
  v5 = v1[2];
  if ( v5 )
  {
    FreeSid(v5);
    v1[2] = 0;
  }
  v6 = v1[3];
  if ( v6 )
  {
    LocalFree(v6);
    v1[3] = 0;
  }
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v1);
  result = 0;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x18002f96c  mov     [rsp+arg_0], rbx
0x18002f971  push    rdi
0x18002f972  sub     rsp, 20h
0x18002f976  mov     rbx, [rcx]
0x18002f979  mov     rdi, rcx
0x18002f97c  mov     rcx, [rbx]; pSid
0x18002f97f  test    rcx, rcx
0x18002f982  jz      short loc_18002F991
0x18002f984  call    cs:__imp_FreeSid
0x18002f98a  mov     qword ptr [rbx], 0
0x18002f991  mov     rcx, [rbx+8]; pSid
0x18002f995  test    rcx, rcx
0x18002f998  jz      short loc_18002F9A8
0x18002f99a  call    cs:__imp_FreeSid
0x18002f9a0  mov     qword ptr [rbx+8], 0
0x18002f9a8  mov     rcx, [rbx+10h]; pSid
0x18002f9ac  test    rcx, rcx
0x18002f9af  jz      short loc_18002F9BF
0x18002f9b1  call    cs:__imp_FreeSid
0x18002f9b7  mov     qword ptr [rbx+10h], 0
0x18002f9bf  mov     rcx, [rbx+18h]; hMem
0x18002f9c3  test    rcx, rcx
0x18002f9c6  jz      short loc_18002F9D6
0x18002f9c8  call    cs:__imp_LocalFree
0x18002f9ce  mov     qword ptr [rbx+18h], 0
0x18002f9d6  call    cs:__imp_GetProcessHeap
0x18002f9dc  mov     r8, rbx; lpMem
0x18002f9df  xor     edx, edx; dwFlags
0x18002f9e1  mov     rcx, rax; hHeap
0x18002f9e4  call    cs:__imp_HeapFree
0x18002f9ea  mov     rbx, [rsp+28h+arg_0]
0x18002f9ef  xor     eax, eax
0x18002f9f1  mov     qword ptr [rdi], 0
0x18002f9f8  add     rsp, 20h
0x18002f9fc  pop     rdi
0x18002f9fd  retn
```
