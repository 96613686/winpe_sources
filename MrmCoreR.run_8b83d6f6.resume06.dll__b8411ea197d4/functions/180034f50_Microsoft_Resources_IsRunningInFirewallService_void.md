# Microsoft::Resources::IsRunningInFirewallService(void)

- ea: `0x180034f50`
- end: `0x180034fb6`
- name: `?IsRunningInFirewallService@Resources@Microsoft@@YA_NXZ`
- size: `102`
- prototype: `bool __fastcall(Microsoft::Resources *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180034650`

## callees

- `0x180034f50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034fa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034fa8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180034f6d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180034f6d`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180034f91`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x180034f91`

## pseudocode

```c
bool __fastcall Microsoft::Resources::IsRunningInFirewallService(Microsoft::Resources *this)
{
  bool v1; // bl
  int v3; // [rsp+30h] [rbp+8h] BYREF
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  Sid = 0;
  v1 = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-3088073201-1464728630-1879813800-1107566885-823218052", &Sid) )
  {
    v3 = 0;
    if ( (unsigned int)CheckTokenMembershipEx(0, Sid, 1, &v3) )
      v1 = v3 == 1;
    LocalFree(Sid);
  }
  return v1;
}

```

## disassembly

```asm
0x180034f50  push    rbx
0x180034f52  sub     rsp, 20h
0x180034f56  lea     rdx, [rsp+28h+Sid]; Sid
0x180034f5b  mov     [rsp+28h+Sid], 0
0x180034f64  lea     rcx, StringSid; "S-1-5-80-3088073201-1464728630-18798138"...
0x180034f6b  xor     bl, bl
0x180034f6d  call    cs:__imp_ConvertStringSidToSidW
0x180034f73  test    eax, eax
0x180034f75  jz      short loc_180034FAE
0x180034f77  mov     rdx, [rsp+28h+Sid]
0x180034f7c  lea     r9, [rsp+28h+arg_0]
0x180034f81  mov     r8d, 1
0x180034f87  mov     [rsp+28h+arg_0], 0
0x180034f8f  xor     ecx, ecx
0x180034f91  call    cs:__imp_CheckTokenMembershipEx
0x180034f97  test    eax, eax
0x180034f99  jz      short loc_180034FA3
0x180034f9b  cmp     [rsp+28h+arg_0], 1
0x180034fa0  setz    bl
0x180034fa3  mov     rcx, [rsp+28h+Sid]; hMem
0x180034fa8  call    cs:__imp_LocalFree
0x180034fae  mov     al, bl
0x180034fb0  add     rsp, 20h
0x180034fb4  pop     rbx
0x180034fb5  retn
```
