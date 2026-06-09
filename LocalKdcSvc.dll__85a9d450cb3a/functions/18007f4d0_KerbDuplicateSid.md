# KerbDuplicateSid

- ea: `0x18007f4d0`
- end: `0x18007f53a`
- name: `KerbDuplicateSid`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002e6c4`
- `0x1800464f4`
- `0x18007d950`

## callees

- `0x1800038f0`
- `0x18005a060`
- `0x18007f4d0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18007f4fc`
- `ntdll!RtlLengthSid` at `0x18007f4fc`
- `ntdll!RtlValidSid` at `0x18007f4e8`
- `ntdll!RtlValidSid` at `0x18007f4e8`

## pseudocode

```c
__int64 __fastcall KerbDuplicateSid(_QWORD *a1, void *a2)
{
  size_t v5; // rdi
  void *v6; // rax

  if ( !RtlValidSid(a2) )
    return 3221225485LL;
  v5 = RtlLengthSid(a2);
  v6 = MIDL_user_allocate(v5);
  *a1 = v6;
  if ( !v6 )
    return 3221225626LL;
  memcpy_0(v6, a2, v5);
  return 0;
}

```

## disassembly

```asm
0x18007f4d0  mov     [rsp+arg_0], rbx
0x18007f4d5  mov     [rsp+arg_8], rsi
0x18007f4da  push    rdi
0x18007f4db  sub     rsp, 20h
0x18007f4df  mov     rsi, rcx
0x18007f4e2  mov     rbx, rdx
0x18007f4e5  mov     rcx, rdx; Sid
0x18007f4e8  call    cs:__imp_RtlValidSid
0x18007f4ee  test    al, al
0x18007f4f0  jnz     short loc_18007F4F9
0x18007f4f2  mov     eax, 0C000000Dh
0x18007f4f7  jmp     short loc_18007F52A
0x18007f4f9  mov     rcx, rbx; Sid
0x18007f4fc  call    cs:__imp_RtlLengthSid
0x18007f502  mov     ecx, eax; size
0x18007f504  mov     edi, eax
0x18007f506  call    MIDL_user_allocate
0x18007f50b  mov     [rsi], rax
0x18007f50e  test    rax, rax
0x18007f511  jnz     short loc_18007F51A
0x18007f513  mov     eax, 0C000009Ah
0x18007f518  jmp     short loc_18007F52A
0x18007f51a  mov     r8, rdi; Size
0x18007f51d  mov     rdx, rbx; Src
0x18007f520  mov     rcx, rax; void *
0x18007f523  call    memcpy_0
0x18007f528  xor     eax, eax
0x18007f52a  mov     rbx, [rsp+28h+arg_0]
0x18007f52f  mov     rsi, [rsp+28h+arg_8]
0x18007f534  add     rsp, 20h
0x18007f538  pop     rdi
0x18007f539  retn
```
