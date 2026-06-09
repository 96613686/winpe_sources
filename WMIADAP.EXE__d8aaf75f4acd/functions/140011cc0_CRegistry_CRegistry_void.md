# CRegistry::~CRegistry(void)

- ea: `0x140011cc0`
- end: `0x140011ce8`
- name: `??1CRegistry@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000f91c`
- `0x140012f60`
- `0x140013510`
- `0x140015f29`
- `0x140015f3b`
- `0x14001629a`
- `0x14001631a`

## callees

- `0x14000ff40`
- `0x140011cc0`
- `0x140012040`

## pseudocode

```c
void __fastcall CRegistry::~CRegistry(CRegistry *this)
{
  CRegistry *v1; // rbx

  try
  {
    v1 = this;
    CRegistry::Close(this);
  }
  catch ( CHeap_Exception )
  {
    v1 = this;
  }
  v1 = this;
}

```

## disassembly

```asm
0x140011cc0  mov     [rsp+arg_0], rcx
0x140011cc5  push    rbx
0x140011cc6  sub     rsp, 20h
0x140011cca  mov     rbx, rcx
0x140011ccd  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x140011cd2  nop
0x140011cd3  jmp     short loc_140011CDA
0x140011cd5  mov     rbx, [rsp+28h+arg_0]
0x140011cda  lea     rcx, [rbx+18h]; this
0x140011cde  add     rsp, 20h
0x140011ce2  pop     rbx
0x140011ce3  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
