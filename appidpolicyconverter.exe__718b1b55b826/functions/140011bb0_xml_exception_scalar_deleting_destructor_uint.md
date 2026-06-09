# xml_exception::`scalar deleting destructor'(uint)

- ea: `0x140011bb0`
- end: `0x140011bdf`
- name: `??_Gxml_exception@@UEAAPEAXI@Z`
- size: `47`
- prototype: `xml_exception *__fastcall(xml_exception *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x14000157c`
- `0x140011b08`
- `0x140011bb0`

## pseudocode

```c
xml_exception *__fastcall xml_exception::`scalar deleting destructor'(xml_exception *this, char a2)
{
  xml_exception::~xml_exception(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140011bb0  mov     [rsp+arg_0], rbx
0x140011bb5  push    rdi
0x140011bb6  sub     rsp, 20h
0x140011bba  mov     ebx, edx
0x140011bbc  mov     rdi, rcx
0x140011bbf  call    ??1xml_exception@@UEAA@XZ; xml_exception::~xml_exception(void)
0x140011bc4  test    bl, 1
0x140011bc7  jz      short loc_140011BD1
0x140011bc9  mov     rcx, rdi; Block
0x140011bcc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011bd1  mov     rbx, [rsp+28h+arg_0]
0x140011bd6  mov     rax, rdi
0x140011bd9  add     rsp, 20h
0x140011bdd  pop     rdi
0x140011bde  retn
```
