# CSubCommand::Release(void)

- ea: `0x18000b1e0`
- end: `0x18000b21d`
- name: `?Release@CSubCommand@@UEAAKXZ`
- size: `61`
- prototype: `__int64 __fastcall(CSubCommand *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000453c`
- `0x180006b74`
- `0x18000b1e0`

## pseudocode

```c
__int64 __fastcall CSubCommand::Release(CSubCommand *this)
{
  unsigned __int32 v2; // edi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 2);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000b1e0  mov     [rsp+arg_0], rbx
0x18000b1e5  push    rdi
0x18000b1e6  sub     rsp, 20h
0x18000b1ea  mov     rbx, rcx
0x18000b1ed  or      edi, 0FFFFFFFFh
0x18000b1f0  lock xadd [rcx+8], edi
0x18000b1f5  sub     edi, 1
0x18000b1f8  jnz     short loc_18000B210
0x18000b1fa  test    rcx, rcx
0x18000b1fd  jz      short loc_18000B210
0x18000b1ff  add     rcx, 10h
0x18000b203  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b208  mov     rcx, rbx; Block
0x18000b20b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b210  mov     rbx, [rsp+28h+arg_0]
0x18000b215  mov     eax, edi
0x18000b217  add     rsp, 20h
0x18000b21b  pop     rdi
0x18000b21c  retn
```
