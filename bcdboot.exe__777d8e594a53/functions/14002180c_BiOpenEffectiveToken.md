# BiOpenEffectiveToken

- ea: `0x14002180c`
- end: `0x140021880`
- name: `BiOpenEffectiveToken`
- size: `116`
- prototype: `int __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400216fc`

## callees

- `0x14002180c`

## import_xrefs

- `ntdll!NtOpenProcessTokenEx` at `0x140021874`
- `ntdll!NtOpenProcessTokenEx` at `0x140021874`
- `ntdll!NtOpenThreadTokenEx` at `0x14002183b`
- `ntdll!NtOpenThreadTokenEx` at `0x14002185b`
- `ntdll!NtOpenThreadTokenEx` at `0x14002183b`
- `ntdll!NtOpenThreadTokenEx` at `0x14002185b`

## pseudocode

```c
int __fastcall BiOpenEffectiveToken(PHANDLE TokenHandle)
{
  int result; // eax

  if ( !NtCurrentTeb()->IsImpersonating )
    return NtOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, 0x200u, TokenHandle);
  result = NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 1u, 0x200u, TokenHandle);
  if ( result < 0 )
    return NtOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, 0x200u, TokenHandle);
  return result;
}

```

## disassembly

```asm
0x14002180c  push    rbx
0x14002180e  sub     rsp, 30h
0x140021812  mov     eax, gs:179Ch
0x14002181a  mov     rbx, rcx
0x14002181d  mov     edx, 28h ; '('; DesiredAccess
0x140021822  test    eax, eax
0x140021824  jz      short loc_140021867
0x140021826  mov     [rsp+38h+TokenHandle], rcx; TokenHandle
0x14002182b  mov     r9d, 200h; HandleAttributes
0x140021831  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140021838  mov     r8b, 1; OpenAsSelf
0x14002183b  call    cs:__imp_NtOpenThreadTokenEx
0x140021841  test    eax, eax
0x140021843  jns     short loc_14002187A
0x140021845  xor     r8d, r8d; OpenAsSelf
0x140021848  mov     [rsp+38h+TokenHandle], rbx; TokenHandle
0x14002184d  mov     r9d, 200h; HandleAttributes
0x140021853  lea     edx, [r8+28h]; DesiredAccess
0x140021857  lea     rcx, [r8-2]; ThreadHandle
0x14002185b  call    cs:__imp_NtOpenThreadTokenEx
0x140021861  add     rsp, 30h
0x140021865  pop     rbx
0x140021866  retn
0x140021867  mov     r9, rbx; TokenHandle
0x14002186a  mov     r8d, 200h; HandleAttributes
0x140021870  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140021874  call    cs:__imp_NtOpenProcessTokenEx
0x14002187a  add     rsp, 30h
0x14002187e  pop     rbx
0x14002187f  retn
```
