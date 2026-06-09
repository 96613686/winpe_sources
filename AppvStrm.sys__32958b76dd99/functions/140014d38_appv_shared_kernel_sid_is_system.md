# appv::shared::kernel::sid_is_system

- ea: `0x140014d38`
- end: `0x140014dc3`
- name: `appv::shared::kernel::sid_is_system`
- size: `139`
- prototype: `bool __fastcall(PSID Sid2)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x140014560`
- `0x140014760`

## callees

- `0x140014d38`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x140014d5e`
- `ntoskrnl!RtlEqualSid` at `0x140014d82`
- `ntoskrnl!RtlEqualSid` at `0x140014da6`
- `ntoskrnl!RtlEqualSid` at `0x140014d5e`
- `ntoskrnl!RtlEqualSid` at `0x140014d82`
- `ntoskrnl!RtlEqualSid` at `0x140014da6`
- `ntoskrnl!SeExports` at `0x140014d4a`
- `ntoskrnl!SeExports` at `0x140014d6e`
- `ntoskrnl!SeExports` at `0x140014d92`

## pseudocode

```c
bool __fastcall appv::shared::kernel::sid_is_system(PSID Sid2)
{
  if ( !Sid2 )
    return 0;
  return RtlEqualSid(SeExports->SeLocalSystemSid, Sid2)
      || RtlEqualSid(SeExports->SeLocalServiceSid, Sid2)
      || RtlEqualSid(SeExports->SeNetworkServiceSid, Sid2);
}

```

## disassembly

```asm
0x140014d38  push    rbx
0x140014d3a  sub     rsp, 20h
0x140014d3e  mov     rbx, rcx
0x140014d41  test    rcx, rcx
0x140014d44  jnz     short loc_140014D4A
0x140014d46  xor     al, al
0x140014d48  jmp     short loc_140014DBC
0x140014d4a  mov     rax, cs:__imp_SeExports
0x140014d51  mov     rdx, rbx; Sid2
0x140014d54  mov     rcx, [rax]
0x140014d57  mov     rcx, [rcx+108h]; Sid1
0x140014d5e  call    cs:__imp_RtlEqualSid
0x140014d65  nop     dword ptr [rax+rax+00h]
0x140014d6a  test    al, al
0x140014d6c  jnz     short loc_140014DBA
0x140014d6e  mov     rax, cs:__imp_SeExports
0x140014d75  mov     rdx, rbx; Sid2
0x140014d78  mov     rcx, [rax]
0x140014d7b  mov     rcx, [rcx+180h]; Sid1
0x140014d82  call    cs:__imp_RtlEqualSid
0x140014d89  nop     dword ptr [rax+rax+00h]
0x140014d8e  test    al, al
0x140014d90  jnz     short loc_140014DBA
0x140014d92  mov     rax, cs:__imp_SeExports
0x140014d99  mov     rdx, rbx; Sid2
0x140014d9c  mov     rcx, [rax]
0x140014d9f  mov     rcx, [rcx+188h]; Sid1
0x140014da6  call    cs:__imp_RtlEqualSid
0x140014dad  nop     dword ptr [rax+rax+00h]
0x140014db2  test    al, al
0x140014db4  jnz     short loc_140014DBA
0x140014db6  xor     eax, eax
0x140014db8  jmp     short loc_140014DBC
0x140014dba  mov     al, 1
0x140014dbc  add     rsp, 20h
0x140014dc0  pop     rbx
0x140014dc1  retn
```
