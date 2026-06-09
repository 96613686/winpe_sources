# HandleSendReceiveServer::SecurityCreateSecurityDescriptor(void * *)

- ea: `0x140019488`
- end: `0x1400194ef`
- name: `?SecurityCreateSecurityDescriptor@HandleSendReceiveServer@@AEAAJPEAPEAX@Z`
- size: `103`
- prototype: `__int64 __fastcall(HandleSendReceiveServer *__hidden this, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018908`

## callees

- `0x140019488`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400194db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400194db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400194c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1400194c1`

## pseudocode

```c
signed int __fastcall HandleSendReceiveServer::SecurityCreateSecurityDescriptor(
        HandleSendReceiveServer *this,
        void **a2)
{
  signed int result; // eax
  ULONG v4; // [rsp+30h] [rbp+8h] BYREF
  int v5; // [rsp+34h] [rbp+Ch]
  PSECURITY_DESCRIPTOR v6; // [rsp+38h] [rbp+10h] BYREF

  v5 = HIDWORD(this);
  *a2 = 0;
  v6 = 0;
  v4 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;0x1;;;WD)(A;;0x1;;;S-1-15-2-1)(A;;0x1;;;S-1-15-3-1024-1692970155-4054893335-185714091-3362601943-35265931"
          "81-1159816984-2199008581-497492991)",
         1u,
         &v6,
         &v4) )
  {
    *a2 = v6;
    return 0;
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
0x140019488  mov     rax, rsp
0x14001948b  mov     [rax+8], rcx
0x14001948f  push    rbx
0x140019490  sub     rsp, 20h
0x140019494  mov     rbx, rdx
0x140019497  mov     qword ptr [rdx], 0
0x14001949e  mov     edx, 1; StringSDRevision
0x1400194a3  mov     qword ptr [rax+10h], 0
0x1400194ab  lea     r9, [rax+8]; SecurityDescriptorSize
0x1400194af  mov     dword ptr [rax+8], 0
0x1400194b6  lea     r8, [rax+10h]; SecurityDescriptor
0x1400194ba  lea     rcx, StringSecurityDescriptor; "D:(A;;0x1;;;WD)(A;;0x1;;;S-1-15-2-1)(A;"...
0x1400194c1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1400194c7  test    eax, eax
0x1400194c9  jz      short loc_1400194DB
0x1400194cb  mov     rax, [rsp+28h+arg_8]
0x1400194d0  mov     [rbx], rax
0x1400194d3  xor     eax, eax
0x1400194d5  add     rsp, 20h
0x1400194d9  pop     rbx
0x1400194da  retn
0x1400194db  call    cs:__imp_GetLastError
0x1400194e1  test    eax, eax
0x1400194e3  jle     short loc_1400194D5
0x1400194e5  movzx   eax, ax
0x1400194e8  or      eax, 80070000h
0x1400194ed  jmp     short loc_1400194D5
```
