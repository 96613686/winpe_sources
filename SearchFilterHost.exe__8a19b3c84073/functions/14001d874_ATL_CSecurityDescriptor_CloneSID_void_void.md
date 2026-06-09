# ATL::CSecurityDescriptor::CloneSID(void * *,void *)

- ea: `0x14001d874`
- end: `0x14001d908`
- name: `?CloneSID@CSecurityDescriptor@ATL@@SAJPEAPEAXPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(void **, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020ff8`
- `0x140023e90`
- `0x140023f30`

## callees

- `0x14001d4e8`
- `0x14001d874`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d8e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001d8e9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d8b6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001d8b6`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001d8d5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x14001d8d5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001d8ac`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001d8ac`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14001d89f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14001d89f`

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
    Error = ResultFromLastError();
    free(*a1);
    *a1 = 0;
  }
  return Error;
}

```

## disassembly

```asm
0x14001d874  push    rbx
0x14001d876  push    rbp
0x14001d877  push    rsi
0x14001d878  push    rdi
0x14001d879  sub     rsp, 28h
0x14001d87d  mov     rdi, rdx
0x14001d880  mov     rbx, rcx
0x14001d883  test    rcx, rcx
0x14001d886  jnz     short loc_14001D88F
0x14001d888  mov     eax, 80004003h
0x14001d88d  jmp     short loc_14001D8FF
0x14001d88f  cmp     qword ptr [rcx], 0
0x14001d893  jnz     short loc_14001D8FA
0x14001d895  mov     qword ptr [rcx], 0
0x14001d89c  mov     rcx, rdi; pSid
0x14001d89f  call    cs:__imp_IsValidSid
0x14001d8a5  test    eax, eax
0x14001d8a7  jz      short loc_14001D8FA
0x14001d8a9  mov     rcx, rdi; pSid
0x14001d8ac  call    cs:__imp_GetLengthSid
0x14001d8b2  mov     ecx, eax; Size
0x14001d8b4  mov     ebp, eax
0x14001d8b6  call    cs:__imp_malloc
0x14001d8bc  mov     [rbx], rax
0x14001d8bf  test    rax, rax
0x14001d8c2  jnz     short loc_14001D8CB
0x14001d8c4  mov     eax, 8007000Eh
0x14001d8c9  jmp     short loc_14001D8FF
0x14001d8cb  mov     r8, rdi; pSourceSid
0x14001d8ce  mov     rdx, rax; pDestinationSid
0x14001d8d1  mov     ecx, ebp; nDestinationSidLength
0x14001d8d3  xor     esi, esi
0x14001d8d5  call    cs:__imp_CopySid
0x14001d8db  test    eax, eax
0x14001d8dd  jnz     short loc_14001D8F6
0x14001d8df  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001d8e4  mov     rcx, [rbx]; Block
0x14001d8e7  mov     esi, eax
0x14001d8e9  call    cs:__imp_free
0x14001d8ef  mov     qword ptr [rbx], 0
0x14001d8f6  mov     eax, esi
0x14001d8f8  jmp     short loc_14001D8FF
0x14001d8fa  mov     eax, 80070057h
0x14001d8ff  add     rsp, 28h
0x14001d903  pop     rdi
0x14001d904  pop     rsi
0x14001d905  pop     rbp
0x14001d906  pop     rbx
0x14001d907  retn
```
