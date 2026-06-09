# IsRunningInSystemContext

- ea: `0x180014fe8`
- end: `0x18001504a`
- name: `IsRunningInSystemContext`
- size: `98`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012a58`
- `0x180012b80`

## callees

- `0x180001c60`
- `0x180014fe8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180015022`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180015022`

## pseudocode

```c
__int64 __fastcall IsRunningInSystemContext(PBOOL IsMember)
{
  _DWORD SidToCheck[4]; // [rsp+20h] [rbp-28h] BYREF

  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  if ( !CheckTokenMembership(0, SidToCheck, IsMember) )
    *IsMember = 0;
  return 0;
}

```

## disassembly

```asm
0x180014fe8  push    rbx
0x180014fea  sub     rsp, 40h
0x180014fee  mov     rax, cs:__security_cookie
0x180014ff5  xor     rax, rsp
0x180014ff8  mov     [rsp+48h+var_18], rax
0x180014ffd  mov     rbx, rcx
0x180015000  mov     [rsp+48h+SidToCheck], 101h
0x180015008  mov     r8, rcx; IsMember
0x18001500b  mov     [rsp+48h+var_24], 5000000h
0x180015013  xor     ecx, ecx; TokenHandle
0x180015015  mov     [rsp+48h+var_20], 12h
0x18001501d  lea     rdx, [rsp+48h+SidToCheck]; SidToCheck
0x180015022  call    cs:__imp_CheckTokenMembership
0x180015029  nop     dword ptr [rax+rax+00h]
0x18001502e  test    eax, eax
0x180015030  jnz     short loc_180015034
0x180015032  mov     [rbx], eax
0x180015034  xor     eax, eax
0x180015036  mov     rcx, [rsp+48h+var_18]
0x18001503b  xor     rcx, rsp; StackCookie
0x18001503e  call    __security_check_cookie
0x180015043  add     rsp, 40h
0x180015047  pop     rbx
0x180015048  retn
```
