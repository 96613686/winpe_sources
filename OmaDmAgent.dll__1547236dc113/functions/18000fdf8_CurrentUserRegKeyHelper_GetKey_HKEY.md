# CurrentUserRegKeyHelper::GetKey(HKEY__ * &)

- ea: `0x18000fdf8`
- end: `0x18000fe46`
- name: `?GetKey@CurrentUserRegKeyHelper@@QEAAJAEAPEAUHKEY__@@@Z`
- size: `78`
- prototype: `__int64 __fastcall(PHKEY phkResult, HKEY *)`
- caller_count: `13`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000c734`
- `0x18000e524`
- `0x18000ea88`
- `0x18000fa44`
- `0x180011160`
- `0x180011398`
- `0x180011574`
- `0x18001180c`
- `0x180011a44`
- `0x180011bfc`
- `0x180011e54`
- `0x180012050`
- `0x180012338`

## callees

- `0x18000fdf8`

## import_xrefs

- `ADVAPI32!RegOpenCurrentUser` at `0x18000fe16`
- `ADVAPI32!RegOpenCurrentUser` at `0x18000fe16`

## pseudocode

```c
LSTATUS __fastcall CurrentUserRegKeyHelper::GetKey(PHKEY phkResult, HKEY *a2)
{
  LSTATUS result; // eax

  if ( *phkResult || (result = RegOpenCurrentUser(0xF003Fu, phkResult)) == 0 )
  {
    *a2 = *phkResult;
    return 0;
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18000fdf8  mov     [rsp+arg_0], rbx
0x18000fdfd  push    rdi
0x18000fdfe  sub     rsp, 20h
0x18000fe02  cmp     qword ptr [rcx], 0
0x18000fe06  mov     rdi, rdx
0x18000fe09  mov     rbx, rcx
0x18000fe0c  jnz     short loc_18000FE32
0x18000fe0e  mov     rdx, rcx; phkResult
0x18000fe11  mov     ecx, 0F003Fh; samDesired
0x18000fe16  call    cs:__imp_RegOpenCurrentUser
0x18000fe1d  nop     dword ptr [rax+rax+00h]
0x18000fe22  test    eax, eax
0x18000fe24  jz      short loc_18000FE32
0x18000fe26  jle     short loc_18000FE3A
0x18000fe28  movzx   eax, ax
0x18000fe2b  or      eax, 80070000h
0x18000fe30  jmp     short loc_18000FE3A
0x18000fe32  mov     rax, [rbx]
0x18000fe35  mov     [rdi], rax
0x18000fe38  xor     eax, eax
0x18000fe3a  mov     rbx, [rsp+28h+arg_0]
0x18000fe3f  add     rsp, 20h
0x18000fe43  pop     rdi
0x18000fe44  retn
```
