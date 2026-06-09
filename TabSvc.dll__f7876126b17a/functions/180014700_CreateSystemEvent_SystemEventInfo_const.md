# CreateSystemEvent(SystemEventInfo const *)

- ea: `0x180014700`
- end: `0x180014774`
- name: `?CreateSystemEvent@@YAPEAXPEBUSystemEventInfo@@@Z`
- size: `116`
- prototype: `HANDLE __fastcall(LPCWSTR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025bbc`

## callees

- `0x180014700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014752`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014752`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014760`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014723`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180014723`

## pseudocode

```c
HANDLE __fastcall CreateSystemEvent(LPCWSTR *a1)
{
  HANDLE v1; // rbx
  const WCHAR *v3; // r9
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+20h] [rbp-28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a1[1], 1u, &SecurityDescriptor, 0) )
  {
    v3 = *a1;
    EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&EventAttributes.nLength = 24;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    v1 = CreateEventW(&EventAttributes, 0, 0, v3);
    LocalFree(SecurityDescriptor);
  }
  return v1;
}

```

## disassembly

```asm
0x180014700  mov     [rsp+arg_8], rbx
0x180014705  push    rdi
0x180014706  sub     rsp, 40h
0x18001470a  xor     ebx, ebx
0x18001470c  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180014711  mov     rdi, rcx
0x180014714  mov     [rsp+48h+SecurityDescriptor], rbx
0x180014719  mov     rcx, [rcx+8]; StringSecurityDescriptor
0x18001471d  xor     r9d, r9d; SecurityDescriptorSize
0x180014720  lea     edx, [rbx+1]; StringSDRevision
0x180014723  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180014729  test    eax, eax
0x18001472b  jz      short loc_180014766
0x18001472d  mov     rax, [rsp+48h+SecurityDescriptor]
0x180014732  lea     rcx, [rsp+48h+EventAttributes]; lpEventAttributes
0x180014737  mov     r9, [rdi]; lpName
0x18001473a  xor     r8d, r8d; bInitialState
0x18001473d  xor     edx, edx; bManualReset
0x18001473f  mov     [rsp+48h+EventAttributes.lpSecurityDescriptor], rax
0x180014744  mov     qword ptr [rsp+48h+EventAttributes.nLength], 18h
0x18001474d  mov     qword ptr [rsp+48h+EventAttributes.bInheritHandle], rbx
0x180014752  call    cs:__imp_CreateEventW
0x180014758  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x18001475d  mov     rbx, rax
0x180014760  call    cs:__imp_LocalFree
0x180014766  mov     rax, rbx
0x180014769  mov     rbx, [rsp+48h+arg_8]
0x18001476e  add     rsp, 40h
0x180014772  pop     rdi
0x180014773  retn
```
