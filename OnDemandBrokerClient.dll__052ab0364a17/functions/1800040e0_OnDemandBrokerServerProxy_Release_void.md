# OnDemandBrokerServerProxy::Release(void)

- ea: `0x1800040e0`
- end: `0x180004111`
- name: `?Release@OnDemandBrokerServerProxy@@UEAAKXZ`
- size: `49`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800040e0`
- `0x18000437c`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::Release(OnDemandBrokerServerProxy *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
  {
    *(_QWORD *)this = &OnDemandBrokerServerProxy::`vftable';
    operator delete(this);
  }
  return v1;
}

```

## disassembly

```asm
0x1800040e0  push    rbx
0x1800040e2  sub     rsp, 20h
0x1800040e6  mov     ebx, 0FFFFFFFFh
0x1800040eb  lock xadd [rcx+8], ebx
0x1800040f0  sub     ebx, 1
0x1800040f3  jnz     short loc_180004109
0x1800040f5  test    rcx, rcx
0x1800040f8  jz      short loc_180004109
0x1800040fa  lea     rax, ??_7OnDemandBrokerServerProxy@@6B@; const OnDemandBrokerServerProxy::`vftable'
0x180004101  mov     [rcx], rax
0x180004104  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004109  mov     eax, ebx
0x18000410b  add     rsp, 20h
0x18000410f  pop     rbx
0x180004110  retn
```
