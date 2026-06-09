# ATL::CSecurityDescriptor::CloneSID(void * *,void *)

- ea: `0x18000a104`
- end: `0x18000a198`
- name: `?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(void **, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b8c4`
- `0x18000f93c`
- `0x18000fab4`

## callees

- `0x180009df4`
- `0x18000a104`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a179`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a179`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a146`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a146`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000a12f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000a12f`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a165`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000a165`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a13c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000a13c`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::CloneSID(void **a1, void *a2)
{
  DWORD LengthSid; // ebp
  void *v6; // rax
  unsigned int Error; // esi

  if ( !a1 )
    return 2147500035LL;
  if ( *a1 )
    return 2147942487LL;
  *a1 = 0;
  if ( !IsValidSid(a2) )
    return 2147942487LL;
  LengthSid = GetLengthSid(a2);
  v6 = malloc(LengthSid);
  *a1 = v6;
  if ( !v6 )
    return 2147942414LL;
  Error = 0;
  if ( !CopySid(LengthSid, v6, a2) )
  {
    Error = ATL::AtlHresultFromLastError();
    free(*a1);
    *a1 = 0;
  }
  return Error;
}

```

## disassembly

```asm
0x18000a104  push    rbx
0x18000a106  push    rbp
0x18000a107  push    rsi
0x18000a108  push    rdi
0x18000a109  sub     rsp, 28h
0x18000a10d  mov     rdi, rdx
0x18000a110  mov     rbx, rcx
0x18000a113  test    rcx, rcx
0x18000a116  jnz     short loc_18000A11F
0x18000a118  mov     eax, 80004003h
0x18000a11d  jmp     short loc_18000A18F
0x18000a11f  cmp     qword ptr [rcx], 0
0x18000a123  jnz     short loc_18000A18A
0x18000a125  mov     qword ptr [rcx], 0
0x18000a12c  mov     rcx, rdi; pSid
0x18000a12f  call    cs:__imp_IsValidSid
0x18000a135  test    eax, eax
0x18000a137  jz      short loc_18000A18A
0x18000a139  mov     rcx, rdi; pSid
0x18000a13c  call    cs:__imp_GetLengthSid
0x18000a142  mov     ecx, eax; Size
0x18000a144  mov     ebp, eax
0x18000a146  call    cs:__imp_malloc
0x18000a14c  mov     [rbx], rax
0x18000a14f  test    rax, rax
0x18000a152  jnz     short loc_18000A15B
0x18000a154  mov     eax, 8007000Eh
0x18000a159  jmp     short loc_18000A18F
0x18000a15b  mov     r8, rdi; pSourceSid
0x18000a15e  mov     rdx, rax; pDestinationSid
0x18000a161  mov     ecx, ebp; nDestinationSidLength
0x18000a163  xor     esi, esi
0x18000a165  call    cs:__imp_CopySid
0x18000a16b  test    eax, eax
0x18000a16d  jnz     short loc_18000A186
0x18000a16f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000a174  mov     rcx, [rbx]; Block
0x18000a177  mov     esi, eax
0x18000a179  call    cs:__imp_free
0x18000a17f  mov     qword ptr [rbx], 0
0x18000a186  mov     eax, esi
0x18000a188  jmp     short loc_18000A18F
0x18000a18a  mov     eax, 80070057h
0x18000a18f  add     rsp, 28h
0x18000a193  pop     rdi
0x18000a194  pop     rsi
0x18000a195  pop     rbp
0x18000a196  pop     rbx
0x18000a197  retn
```
