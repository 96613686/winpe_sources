# CCredentials::operator=(CCredentials const &)

- ea: `0x1800195b8`
- end: `0x1800195f5`
- name: `??4CCredentials@@QEAAXAEBV0@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CCredentials *this, struct CCredentials *)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x180001ed0`
- `0x180002710`
- `0x180002b00`
- `0x180003260`
- `0x180003bb8`
- `0x180004360`
- `0x18000816c`
- `0x1800094f8`
- `0x180009624`
- `0x18000ce28`
- `0x18000d638`

## callees

- `0x1800195b8`
- `0x180019648`
- `0x18001969c`
- `0x1800197b4`

## pseudocode

```c
__int64 __fastcall CCredentials::operator=(CCredentials *this, struct CCredentials *a2)
{
  __int64 result; // rax

  if ( a2 != this )
  {
    CCredentials::FreeUserName((unsigned __int16 **)this);
    CCredentials::FreePassword((unsigned __int16 **)this + 1, (unsigned int *)this + 5);
    return CCredentials::Initialize(this, a2);
  }
  return result;
}

```

## disassembly

```asm
0x1800195b8  cmp     rdx, rcx
0x1800195bb  jz      short locret_1800195F4
0x1800195bd  mov     [rsp+arg_0], rbx
0x1800195c2  push    rdi
0x1800195c3  sub     rsp, 20h
0x1800195c7  mov     rdi, rdx
0x1800195ca  mov     rbx, rcx
0x1800195cd  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x1800195d2  lea     rdx, [rbx+14h]; unsigned int *
0x1800195d6  lea     rcx, [rbx+8]; unsigned __int16 **
0x1800195da  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x1800195df  mov     rdx, rdi; struct CCredentials *
0x1800195e2  mov     rcx, rbx; this
0x1800195e5  call    ?Initialize@CCredentials@@AEAAJAEBV1@@Z; CCredentials::Initialize(CCredentials const &)
0x1800195ea  mov     rbx, [rsp+28h+arg_0]
0x1800195ef  add     rsp, 20h
0x1800195f3  pop     rdi
0x1800195f4  retn
```
