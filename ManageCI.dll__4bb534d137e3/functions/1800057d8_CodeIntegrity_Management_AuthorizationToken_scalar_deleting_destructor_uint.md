# CodeIntegrity::Management::AuthorizationToken::`scalar deleting destructor'(uint)

- ea: `0x1800057d8`
- end: `0x18000580c`
- name: `??_GAuthorizationToken@Management@CodeIntegrity@@QEAAPEAXI@Z`
- size: `52`
- prototype: `void **__fastcall(void **this, char)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000529c`
- `0x18000fa80`
- `0x18001c044`

## callees

- `0x180002ea4`
- `0x180005494`
- `0x1800057d8`

## pseudocode

```c
void **__fastcall CodeIntegrity::Management::AuthorizationToken::`scalar deleting destructor'(void **this, char a2)
{
  CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800057d8  mov     [rsp+arg_0], rbx
0x1800057dd  push    rdi
0x1800057de  sub     rsp, 20h
0x1800057e2  mov     ebx, edx
0x1800057e4  mov     rdi, rcx
0x1800057e7  call    ??1AuthorizationToken@Management@CodeIntegrity@@QEAA@XZ; CodeIntegrity::Management::AuthorizationToken::~AuthorizationToken(void)
0x1800057ec  test    bl, 1
0x1800057ef  jz      short loc_1800057FE
0x1800057f1  mov     edx, 0E8h; unsigned __int64
0x1800057f6  mov     rcx, rdi; void *
0x1800057f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800057fe  mov     rbx, [rsp+28h+arg_0]
0x180005803  mov     rax, rdi
0x180005806  add     rsp, 20h
0x18000580a  pop     rdi
0x18000580b  retn
```
