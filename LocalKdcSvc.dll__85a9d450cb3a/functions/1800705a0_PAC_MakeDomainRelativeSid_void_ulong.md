# PAC_MakeDomainRelativeSid(void *,ulong)

- ea: `0x1800705a0`
- end: `0x180070618`
- name: `?PAC_MakeDomainRelativeSid@@YAPEAXPEAXK@Z`
- size: `120`
- prototype: `void *__fastcall(PSID SourceSid, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180040ebc`
- `0x1800464f4`
- `0x18006e830`
- `0x18006f000`

## callees

- `0x18005a060`
- `0x18005a090`
- `0x1800705a0`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180070601`
- `ntdll!RtlSubAuthoritySid` at `0x180070601`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800705b1`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800705f4`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800705b1`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800705f4`
- `ntdll!RtlCopySid` at `0x1800705e0`
- `ntdll!RtlCopySid` at `0x1800705e0`
- `ntdll!RtlLengthRequiredSid` at `0x1800705bd`
- `ntdll!RtlLengthRequiredSid` at `0x1800705bd`

## pseudocode

```c
void *__fastcall PAC_MakeDomainRelativeSid(PSID SourceSid, ULONG a2)
{
  ULONG v4; // ebp
  ULONG v5; // esi
  void *v6; // rax
  void *v7; // rbx
  PUCHAR v9; // rax

  v4 = *RtlSubAuthorityCountSid(SourceSid);
  v5 = RtlLengthRequiredSid(v4 + 1);
  v6 = MIDL_user_allocate(v5);
  v7 = v6;
  if ( !v6 )
    return 0;
  if ( RtlCopySid(v5, v6, SourceSid) < 0 )
  {
    MIDL_user_free(v7);
    return 0;
  }
  v9 = RtlSubAuthorityCountSid(v7);
  ++*v9;
  *RtlSubAuthoritySid(v7, v4) = a2;
  return v7;
}

```

## disassembly

```asm
0x1800705a0  push    rbx
0x1800705a2  push    rbp
0x1800705a3  push    rsi
0x1800705a4  push    rdi
0x1800705a5  push    r14
0x1800705a7  sub     rsp, 20h
0x1800705ab  mov     r14d, edx
0x1800705ae  mov     rdi, rcx
0x1800705b1  call    cs:__imp_RtlSubAuthorityCountSid
0x1800705b7  movzx   ebp, byte ptr [rax]
0x1800705ba  lea     ecx, [rbp+1]; SubAuthorityCount
0x1800705bd  call    cs:__imp_RtlLengthRequiredSid
0x1800705c3  mov     ecx, eax; size
0x1800705c5  mov     esi, eax
0x1800705c7  call    MIDL_user_allocate
0x1800705cc  mov     rbx, rax
0x1800705cf  test    rax, rax
0x1800705d2  jnz     short loc_1800705D8
0x1800705d4  xor     eax, eax
0x1800705d6  jmp     short loc_18007060D
0x1800705d8  mov     r8, rdi; SourceSid
0x1800705db  mov     rdx, rbx; DestinationSid
0x1800705de  mov     ecx, esi; DestinationSidLength
0x1800705e0  call    cs:__imp_RtlCopySid
0x1800705e6  mov     rcx, rbx; Sid
0x1800705e9  test    eax, eax
0x1800705eb  jns     short loc_1800705F4
0x1800705ed  call    MIDL_user_free
0x1800705f2  jmp     short loc_1800705D4
0x1800705f4  call    cs:__imp_RtlSubAuthorityCountSid
0x1800705fa  mov     edx, ebp; SubAuthority
0x1800705fc  mov     rcx, rbx; Sid
0x1800705ff  inc     byte ptr [rax]
0x180070601  call    cs:__imp_RtlSubAuthoritySid
0x180070607  mov     [rax], r14d
0x18007060a  mov     rax, rbx
0x18007060d  add     rsp, 20h
0x180070611  pop     r14
0x180070613  pop     rdi
0x180070614  pop     rsi
0x180070615  pop     rbp
0x180070616  pop     rbx
0x180070617  retn
```
