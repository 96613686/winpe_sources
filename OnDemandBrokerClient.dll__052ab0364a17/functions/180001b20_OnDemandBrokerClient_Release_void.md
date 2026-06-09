# OnDemandBrokerClient::Release(void)

- ea: `0x180001b20`
- end: `0x180001b5d`
- name: `?Release@OnDemandBrokerClient@@UEAAKXZ`
- size: `61`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800060a0`
- `0x1800060b0`

## callees

- `0x180001b20`
- `0x180001b70`
- `0x18000437c`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::Release(OnDemandBrokerClient *this)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 16);
  if ( !v2 && this )
  {
    OnDemandBrokerClient::~OnDemandBrokerClient(this);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180001b20  mov     [rsp+arg_0], rbx
0x180001b25  push    rdi
0x180001b26  sub     rsp, 20h
0x180001b2a  mov     rdi, rcx
0x180001b2d  mov     ebx, 0FFFFFFFFh
0x180001b32  lock xadd [rcx+40h], ebx
0x180001b37  sub     ebx, 1
0x180001b3a  jz      short loc_180001B49
0x180001b3c  mov     eax, ebx
0x180001b3e  mov     rbx, [rsp+28h+arg_0]
0x180001b43  add     rsp, 20h
0x180001b47  pop     rdi
0x180001b48  retn
0x180001b49  test    rdi, rdi
0x180001b4c  jz      short loc_180001B3C
0x180001b4e  call    ??1OnDemandBrokerClient@@AEAA@XZ; OnDemandBrokerClient::~OnDemandBrokerClient(void)
0x180001b53  mov     rcx, rdi; Block
0x180001b56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001b5b  jmp     short loc_180001B3C
```
