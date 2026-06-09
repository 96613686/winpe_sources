# CIEAdminBrokerObject::Release(void)

- ea: `0x405ba0`
- end: `0x405bd5`
- name: `?Release@CIEAdminBrokerObject@@UAGKXZ`
- size: `53`
- prototype: `int __stdcall(CIEAdminBrokerObject *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x4061c0`
- `0x4061d0`

## callees

- `0x402712`
- `0x405a14`
- `0x405ba0`

## pseudocode

```c
int __stdcall CIEAdminBrokerObject::Release(CIEAdminBrokerObject *this)
{
  int v1; // edi

  v1 = *((_DWORD *)this + 3) - 1;
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) )
  {
    v1 = 0;
    if ( this )
    {
      CIEAdminBrokerObject::~CIEAdminBrokerObject(this);
      operator delete(this);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x405ba0  mov     edi, edi
0x405ba2  push    ebp
0x405ba3  mov     ebp, esp
0x405ba5  push    esi
0x405ba6  mov     esi, [ebp+lpMem]
0x405ba9  or      eax, 0FFFFFFFFh
0x405bac  push    edi
0x405bad  lea     ecx, [esi+0Ch]
0x405bb0  mov     edi, [ecx]
0x405bb2  dec     edi
0x405bb3  lock xadd [ecx], eax
0x405bb7  jnz     short loc_405BCD
0x405bb9  xor     edi, edi
0x405bbb  test    esi, esi
0x405bbd  jz      short loc_405BCD
0x405bbf  mov     ecx, esi; this
0x405bc1  call    ??1CIEAdminBrokerObject@@QAE@XZ; CIEAdminBrokerObject::~CIEAdminBrokerObject(void)
0x405bc6  push    esi; lpMem
0x405bc7  call    ??3@YAXPAX@Z; operator delete(void *)
0x405bcc  pop     ecx
0x405bcd  mov     eax, edi
0x405bcf  pop     edi
0x405bd0  pop     esi
0x405bd1  pop     ebp
0x405bd2  retn    4
```
