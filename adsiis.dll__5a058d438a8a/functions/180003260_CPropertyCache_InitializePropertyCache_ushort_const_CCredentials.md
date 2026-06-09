# CPropertyCache::InitializePropertyCache(ushort const *,CCredentials &)

- ea: `0x180003260`
- end: `0x180003292`
- name: `?InitializePropertyCache@CPropertyCache@@QEAAJPEBGAEAVCCredentials@@@Z`
- size: `50`
- prototype: `int(CPropertyCache *__hidden this, const unsigned __int16 *, struct CCredentials *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d98`
- `0x18000549c`

## callees

- `0x1800195b8`
- `0x18001beb8`

## pseudocode

```c
__int64 __fastcall CPropertyCache::InitializePropertyCache(
        CPropertyCache *this,
        const unsigned __int16 *a2,
        struct CCredentials *a3)
{
  CCredentials::operator=((CPropertyCache *)((char *)this + 48), a3);
  return ADsAllocString(a2, (char *)this + 80);
}

```

## disassembly

```asm
0x180003260  mov     [rsp+arg_0], rbx
0x180003265  push    rdi
0x180003266  sub     rsp, 20h
0x18000326a  mov     rdi, rdx
0x18000326d  mov     rbx, rcx
0x180003270  add     rcx, 30h ; '0'; this
0x180003274  mov     rdx, r8; struct CCredentials *
0x180003277  call    ??4CCredentials@@QEAAXAEBV0@@Z; CCredentials::operator=(CCredentials const &)
0x18000327c  lea     rdx, [rbx+50h]
0x180003280  mov     rcx, rdi
0x180003283  mov     rbx, [rsp+28h+arg_0]
0x180003288  add     rsp, 20h
0x18000328c  pop     rdi
0x18000328d  jmp     ADsAllocString
```
