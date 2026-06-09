# softgrid::shared::revert_to_self::revert_to_self(void)

- ea: `0x14003e4dc`
- end: `0x14003e554`
- name: `??0revert_to_self@shared@softgrid@@QEAA@XZ`
- size: `120`
- prototype: `softgrid::shared::revert_to_self *__fastcall(softgrid::shared::revert_to_self *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003e9d8`
- `0x140045a4c`
- `0x1400639cc`
- `0x1400640a4`

## callees

- `0x14003e4dc`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x14003e50c`
- `ADVAPI32!OpenThreadToken` at `0x14003e50c`
- `ADVAPI32!SetThreadToken` at `0x14003e538`
- `ADVAPI32!SetThreadToken` at `0x14003e538`
- `KERNEL32!CloseHandle` at `0x14003e545`
- `KERNEL32!CloseHandle` at `0x14003e545`
- `KERNEL32!GetCurrentThread` at `0x14003e4f7`
- `KERNEL32!GetCurrentThread` at `0x14003e4f7`
- `KERNEL32!GetLastError` at `0x14003e516`
- `KERNEL32!GetLastError` at `0x14003e516`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
softgrid::shared::revert_to_self *__fastcall softgrid::shared::revert_to_self::revert_to_self(
        softgrid::shared::revert_to_self *this)
{
  HANDLE *v1; // rdi
  HANDLE CurrentThread; // rax

  v1 = (HANDLE *)((char *)this + 8);
  *(_BYTE *)this = 0;
  *((_QWORD *)this + 1) = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, v1) )
  {
    if ( !SetThreadToken(0, 0) )
    {
      CloseHandle(*v1);
      *v1 = 0;
      return this;
    }
    goto LABEL_3;
  }
  if ( GetLastError() == 1008 )
LABEL_3:
    *(_BYTE *)this = 1;
  return this;
}

```

## disassembly

```asm
0x14003e4dc  mov     [rsp+arg_0], rbx
0x14003e4e1  push    rdi
0x14003e4e2  sub     rsp, 20h
0x14003e4e6  lea     rdi, [rcx+8]
0x14003e4ea  mov     byte ptr [rcx], 0
0x14003e4ed  mov     qword ptr [rdi], 0
0x14003e4f4  mov     rbx, rcx
0x14003e4f7  call    cs:__imp_GetCurrentThread
0x14003e4fd  mov     edx, 4; DesiredAccess
0x14003e502  mov     r9, rdi; TokenHandle
0x14003e505  mov     rcx, rax; ThreadHandle
0x14003e508  lea     r8d, [rdx-3]; OpenAsSelf
0x14003e50c  call    cs:__imp_OpenThreadToken
0x14003e512  test    eax, eax
0x14003e514  jnz     short loc_14003E534
0x14003e516  call    cs:__imp_GetLastError
0x14003e51c  cmp     eax, 3F0h
0x14003e521  jnz     short loc_14003E526
0x14003e523  mov     byte ptr [rbx], 1
0x14003e526  mov     rax, rbx
0x14003e529  mov     rbx, [rsp+28h+arg_0]
0x14003e52e  add     rsp, 20h
0x14003e532  pop     rdi
0x14003e533  retn
0x14003e534  xor     edx, edx; Token
0x14003e536  xor     ecx, ecx; Thread
0x14003e538  call    cs:__imp_SetThreadToken
0x14003e53e  test    eax, eax
0x14003e540  jnz     short loc_14003E523
0x14003e542  mov     rcx, [rdi]; hObject
0x14003e545  call    cs:__imp_CloseHandle
0x14003e54b  mov     qword ptr [rdi], 0
0x14003e552  jmp     short loc_14003E526
```
