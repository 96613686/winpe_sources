# CRdpSessionAgentProxy::`vector deleting destructor'(uint)

- ea: `0x1400035a0`
- end: `0x1400035d0`
- name: `??_ECRdpSessionAgentProxy@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CRdpSessionAgentProxy *__fastcall(CRdpSessionAgentProxy *this, char)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x140003590`

## callees

- `0x1400034c8`
- `0x1400035a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400035bc`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400035bc`

## pseudocode

```c
CRdpSessionAgentProxy *__fastcall CRdpSessionAgentProxy::`vector deleting destructor'(
        CRdpSessionAgentProxy *this,
        char a2)
{
  CRdpSessionAgentProxy::~CRdpSessionAgentProxy(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1400035a0  mov     [rsp+arg_0], rbx
0x1400035a5  push    rdi
0x1400035a6  sub     rsp, 20h
0x1400035aa  mov     ebx, edx
0x1400035ac  mov     rdi, rcx
0x1400035af  call    ??1CRdpSessionAgentProxy@@UEAA@XZ; CRdpSessionAgentProxy::~CRdpSessionAgentProxy(void)
0x1400035b4  test    bl, 1
0x1400035b7  jz      short loc_1400035C2
0x1400035b9  mov     rcx, rdi
0x1400035bc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400035c2  mov     rbx, [rsp+28h+arg_0]
0x1400035c7  mov     rax, rdi
0x1400035ca  add     rsp, 20h
0x1400035ce  pop     rdi
0x1400035cf  retn
```
