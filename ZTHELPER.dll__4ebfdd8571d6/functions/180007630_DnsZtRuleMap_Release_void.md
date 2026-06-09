# DnsZtRuleMap::Release(void)

- ea: `0x180007630`
- end: `0x18000766c`
- name: `?Release@DnsZtRuleMap@@QEAAKXZ`
- size: `60`
- prototype: `__int64 __fastcall(DnsZtRuleMap *this)`
- caller_count: `8`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003e00`
- `0x1800073e8`
- `0x180007414`
- `0x180007b64`
- `0x1800111cc`
- `0x180011490`
- `0x180011548`
- `0x180011858`

## callees

- `0x180001518`
- `0x180007490`
- `0x180007630`

## pseudocode

```c
__int64 __fastcall DnsZtRuleMap::Release(DnsZtRuleMap *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v2 && this )
  {
    CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Dispose();
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180007630  mov     [rsp+arg_0], rbx
0x180007635  push    rdi
0x180007636  sub     rsp, 20h
0x18000763a  mov     rbx, rcx
0x18000763d  or      edi, 0FFFFFFFFh
0x180007640  lock xadd [rcx+10h], edi
0x180007645  sub     edi, 1
0x180007648  jnz     short loc_18000765F
0x18000764a  test    rcx, rcx
0x18000764d  jz      short loc_18000765F
0x18000764f  call    ?Dispose@?$CWxRefMap@VDnsZtRuleMap@@VDnsZtRuleNode@@@@QEAAXXZ; CWxRefMap<DnsZtRuleMap,DnsZtRuleNode>::Dispose(void)
0x180007654  lea     edx, [rdi+18h]; unsigned __int64
0x180007657  mov     rcx, rbx; void *
0x18000765a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000765f  mov     rbx, [rsp+28h+arg_0]
0x180007664  mov     eax, edi
0x180007666  add     rsp, 20h
0x18000766a  pop     rdi
0x18000766b  retn
```
