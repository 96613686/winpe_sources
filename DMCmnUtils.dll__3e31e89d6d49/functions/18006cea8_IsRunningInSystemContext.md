# IsRunningInSystemContext

- ea: `0x18006cea8`
- end: `0x18006cf0a`
- name: `IsRunningInSystemContext`
- size: `98`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180061610`
- `0x180069ef0`
- `0x18006a150`
- `0x18006a730`
- `0x18006a860`
- `0x18006a990`
- `0x18006a9a0`
- `0x18006a9d0`

## callees

- `0x180007270`
- `0x18006cea8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006cee2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006cee2`

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
0x18006cea8  push    rbx
0x18006ceaa  sub     rsp, 40h
0x18006ceae  mov     rax, cs:__security_cookie
0x18006ceb5  xor     rax, rsp
0x18006ceb8  mov     [rsp+48h+var_18], rax
0x18006cebd  mov     rbx, rcx
0x18006cec0  mov     [rsp+48h+SidToCheck], 101h
0x18006cec8  mov     r8, rcx; IsMember
0x18006cecb  mov     [rsp+48h+var_24], 5000000h
0x18006ced3  xor     ecx, ecx; TokenHandle
0x18006ced5  mov     [rsp+48h+var_20], 12h
0x18006cedd  lea     rdx, [rsp+48h+SidToCheck]; SidToCheck
0x18006cee2  call    cs:__imp_CheckTokenMembership
0x18006cee9  nop     dword ptr [rax+rax+00h]
0x18006ceee  test    eax, eax
0x18006cef0  jnz     short loc_18006CEF4
0x18006cef2  mov     [rbx], eax
0x18006cef4  xor     eax, eax
0x18006cef6  mov     rcx, [rsp+48h+var_18]
0x18006cefb  xor     rcx, rsp; StackCookie
0x18006cefe  call    __security_check_cookie
0x18006cf03  add     rsp, 40h
0x18006cf07  pop     rbx
0x18006cf08  retn
```
