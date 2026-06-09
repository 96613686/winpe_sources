# CRegistrySearch::~CRegistrySearch(void)

- ea: `0x140011cf0`
- end: `0x140011d10`
- name: `??1CRegistrySearch@@QEAA@XZ`
- size: `32`
- prototype: `void __fastcall(const unsigned __int16 **this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000ff40`
- `0x140014400`

## pseudocode

```c
void __fastcall CRegistrySearch::~CRegistrySearch(const unsigned __int16 **this)
{
  CHPtrArray::~CHPtrArray((CHPtrArray *)(this + 2));
  CHString::~CHString(this + 1);
}

```

## disassembly

```asm
0x140011cf0  push    rbx
0x140011cf2  sub     rsp, 20h
0x140011cf6  mov     rbx, rcx
0x140011cf9  add     rcx, 10h; this
0x140011cfd  call    ??1CHPtrArray@@QEAA@XZ; CHPtrArray::~CHPtrArray(void)
0x140011d02  lea     rcx, [rbx+8]; this
0x140011d06  add     rsp, 20h
0x140011d0a  pop     rbx
0x140011d0b  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
