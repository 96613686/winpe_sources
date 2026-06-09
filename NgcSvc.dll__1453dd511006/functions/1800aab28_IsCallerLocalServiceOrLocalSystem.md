# IsCallerLocalServiceOrLocalSystem

- ea: `0x1800aab28`
- end: `0x1800aabb9`
- name: `IsCallerLocalServiceOrLocalSystem`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18006d340`

## callees

- `0x180024e90`
- `0x180025120`
- `0x1800aab28`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aaba6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800aaba6`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800aab6c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800aab7c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800aab6c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x1800aab7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aab93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aab93`

## pseudocode

```c
__int64 __fastcall IsCallerLocalServiceOrLocalSystem(void *a1)
{
  unsigned int v1; // edi
  int UserSid; // eax
  PSID *v3; // rbx
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp+18h]

  v1 = 0;
  hMem = 0;
  hObject = 0;
  if ( GetCallerToken(a1, 1, &hObject) >= 0 )
  {
    UserSid = GetUserSid(hObject);
    v3 = (PSID *)hMem;
    if ( UserSid >= 0 && (IsWellKnownSid(*(PSID *)hMem, WinLocalSystemSid) || IsWellKnownSid(*v3, WinLocalServiceSid)) )
      v1 = 1;
    if ( v3 )
      LocalFree(v3);
  }
  if ( hObject )
    CloseHandle(hObject);
  return v1;
}

```

## disassembly

```asm
0x1800aab28  mov     rax, rsp
0x1800aab2b  mov     [rax+8], rbx
0x1800aab2f  push    rdi
0x1800aab30  sub     rsp, 20h
0x1800aab34  xor     edi, edi
0x1800aab36  lea     r8, [rax+10h]
0x1800aab3a  mov     [rax+18h], rdi
0x1800aab3e  mov     [rax+10h], rdi
0x1800aab42  lea     edx, [rdi+1]
0x1800aab45  call    GetCallerToken
0x1800aab4a  test    eax, eax
0x1800aab4c  js      short loc_1800AAB99
0x1800aab4e  mov     rcx, [rsp+28h+hObject]; TokenHandle
0x1800aab53  lea     rdx, [rsp+28h+hMem]
0x1800aab58  call    GetUserSid
0x1800aab5d  mov     rbx, [rsp+28h+hMem]
0x1800aab62  test    eax, eax
0x1800aab64  js      short loc_1800AAB8B
0x1800aab66  mov     rcx, [rbx]; pSid
0x1800aab69  lea     edx, [rdi+16h]; WellKnownSidType
0x1800aab6c  call    cs:__imp_IsWellKnownSid
0x1800aab72  test    eax, eax
0x1800aab74  jnz     short loc_1800AAB86
0x1800aab76  mov     rcx, [rbx]; pSid
0x1800aab79  lea     edx, [rdi+17h]; WellKnownSidType
0x1800aab7c  call    cs:__imp_IsWellKnownSid
0x1800aab82  test    eax, eax
0x1800aab84  jz      short loc_1800AAB8B
0x1800aab86  mov     edi, 1
0x1800aab8b  test    rbx, rbx
0x1800aab8e  jz      short loc_1800AAB99
0x1800aab90  mov     rcx, rbx; hMem
0x1800aab93  call    cs:__imp_LocalFree
0x1800aab99  cmp     [rsp+28h+hObject], 0
0x1800aab9f  jz      short loc_1800AABAC
0x1800aaba1  mov     rcx, [rsp+28h+hObject]; hObject
0x1800aaba6  call    cs:__imp_CloseHandle
0x1800aabac  mov     rbx, [rsp+28h+arg_0]
0x1800aabb1  mov     eax, edi
0x1800aabb3  add     rsp, 20h
0x1800aabb7  pop     rdi
0x1800aabb8  retn
```
