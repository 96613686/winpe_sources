# NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)

- ea: `0x180011500`
- end: `0x180011517`
- name: `?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z`
- size: `23`
- prototype: `struct Property __fastcall(NetSetup2::ActiveObject *this, const struct _NETSETUPPROPKEY *, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180006af8`
- `0x18000e90c`
- `0x18000edd0`
- `0x18000f4a0`

## callees

- `0x180011520`

## pseudocode

```c
struct Property __fastcall NetSetup2::ActiveObject::GetProperty(
        NetSetup2::ActiveObject *this,
        const struct _NETSETUPPROPKEY *a2,
        unsigned int a3)
{
  NetSetup2::ActiveObject::GetProperty(this, a2, a3);
  return (struct Property)a2;
}

```

## disassembly

```asm
0x180011500  push    rbx
0x180011502  sub     rsp, 30h
0x180011506  mov     rbx, rdx
0x180011509  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18001150e  mov     rax, rbx
0x180011511  add     rsp, 30h
0x180011515  pop     rbx
0x180011516  retn
```
