# UbpmUtilsIsServiceSid(void *)

- ea: `0x1800245a8`
- end: `0x180024629`
- name: `?UbpmUtilsIsServiceSid@@YAEPEAX@Z`
- size: `129`
- prototype: `unsigned __int8 __fastcall(PSID pSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180023b50`

## callees

- `0x1800245a8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024606`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180024606`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800245b1`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800245b1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800245eb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800245eb`

## pseudocode

```c
bool __fastcall UbpmUtilsIsServiceSid(PSID pSid)
{
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  int v3; // ecx
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax

  SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
  if ( !SidIdentifierAuthority )
    return 0;
  v3 = *(_DWORD *)SidIdentifierAuthority->Value;
  if ( !*(_DWORD *)SidIdentifierAuthority->Value )
    v3 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - 1280;
  return !v3
      && (SidSubAuthorityCount = GetSidSubAuthorityCount(pSid)) != 0
      && *SidSubAuthorityCount == 6
      && (SidSubAuthority = GetSidSubAuthority(pSid, 0)) != 0
      && *SidSubAuthority == 80;
}

```

## disassembly

```asm
0x1800245a8  push    rbx
0x1800245aa  sub     rsp, 20h
0x1800245ae  mov     rbx, rcx
0x1800245b1  call    cs:__imp_GetSidIdentifierAuthority
0x1800245b8  nop     dword ptr [rax+rax+00h]
0x1800245bd  test    rax, rax
0x1800245c0  jz      short loc_180024620
0x1800245c2  mov     ecx, [rax]
0x1800245c4  mov     [rsp+28h+arg_8], 0
0x1800245cc  mov     [rsp+28h+arg_C], 500h
0x1800245d3  sub     ecx, [rsp+28h+arg_8]
0x1800245d7  jnz     short loc_1800245E4
0x1800245d9  movzx   ecx, word ptr [rax+4]
0x1800245dd  movzx   eax, [rsp+28h+arg_C]
0x1800245e2  sub     ecx, eax
0x1800245e4  test    ecx, ecx
0x1800245e6  jnz     short loc_180024620
0x1800245e8  mov     rcx, rbx; pSid
0x1800245eb  call    cs:__imp_GetSidSubAuthorityCount
0x1800245f2  nop     dword ptr [rax+rax+00h]
0x1800245f7  test    rax, rax
0x1800245fa  jz      short loc_180024620
0x1800245fc  cmp     byte ptr [rax], 6
0x1800245ff  jnz     short loc_180024620
0x180024601  xor     edx, edx; nSubAuthority
0x180024603  mov     rcx, rbx; pSid
0x180024606  call    cs:__imp_GetSidSubAuthority
0x18002460d  nop     dword ptr [rax+rax+00h]
0x180024612  test    rax, rax
0x180024615  jz      short loc_180024620
0x180024617  cmp     dword ptr [rax], 50h ; 'P'
0x18002461a  jnz     short loc_180024620
0x18002461c  mov     al, 1
0x18002461e  jmp     short loc_180024622
0x180024620  xor     al, al
0x180024622  add     rsp, 20h
0x180024626  pop     rbx
0x180024627  retn
```
