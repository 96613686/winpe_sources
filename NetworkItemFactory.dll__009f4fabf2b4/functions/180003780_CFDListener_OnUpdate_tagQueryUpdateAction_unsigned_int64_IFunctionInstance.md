# CFDListener::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)

- ea: `0x180003780`
- end: `0x1800037ef`
- name: `?OnUpdate@CFDListener@@UEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z`
- size: `111`
- prototype: `int(CFDListener *__hidden this, enum tagQueryUpdateAction, unsigned __int64, struct IFunctionInstance *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003780`
- `0x1800037f8`
- `0x1800076c8`

## pseudocode

```c
__int64 __fastcall CFDListener::OnUpdate(
        CNetworkItemFactory **this,
        enum tagQueryUpdateAction a2,
        __int64 a3,
        struct IFunctionInstance *a4)
{
  unsigned int v5; // edi
  volatile signed __int32 *v6; // rcx
  signed __int32 v9; // r10d
  __int64 v10; // r8
  signed __int32 v11; // edx

  v5 = 0;
  v6 = (volatile signed __int32 *)this + 3;
  v9 = *v6;
  if ( (*v6 & 0xFFFF8000) != 0 || (v10 = (unsigned int)(v9 + 1), v9 != _InterlockedCompareExchange(v6, v10, v9)) )
    CReaderWriterLock3::_LockSpin(v6, 2);
  if ( *((_DWORD *)this + 8) )
    v5 = CNetworkItemFactory::OnUpdate(this[3], a2, v10, a4);
  do
    v11 = *((_DWORD *)this + 3);
  while ( v11 != _InterlockedCompareExchange((volatile signed __int32 *)this + 3, v11 - 1, v11) );
  return v5;
}

```

## disassembly

```asm
0x180003780  push    rbx
0x180003782  push    rbp
0x180003783  push    rsi
0x180003784  push    rdi
0x180003785  sub     rsp, 28h
0x180003789  mov     rbx, rcx
0x18000378c  xor     edi, edi
0x18000378e  add     rcx, 0Ch
0x180003792  mov     rsi, r9
0x180003795  mov     ebp, edx
0x180003797  mov     r10d, [rcx]
0x18000379a  test    r10d, 0FFFF8000h
0x1800037a1  jnz     short loc_1800037B4
0x1800037a3  lea     r8d, [r10+1]
0x1800037a7  mov     eax, r10d
0x1800037aa  lock cmpxchg [rcx], r8d
0x1800037af  cmp     r10d, eax
0x1800037b2  jz      short loc_1800037BE
0x1800037b4  mov     edx, 2
0x1800037b9  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x1800037be  cmp     [rbx+20h], edi
0x1800037c1  jz      short loc_1800037D3
0x1800037c3  mov     rcx, [rbx+18h]; this
0x1800037c7  mov     r9, rsi; struct IFunctionInstance *
0x1800037ca  mov     edx, ebp; enum tagQueryUpdateAction
0x1800037cc  call    ?OnUpdate@CNetworkItemFactory@@QEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z; CNetworkItemFactory::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)
0x1800037d1  mov     edi, eax
0x1800037d3  mov     edx, [rbx+0Ch]
0x1800037d6  mov     eax, edx
0x1800037d8  lea     ecx, [rdx-1]
0x1800037db  lock cmpxchg [rbx+0Ch], ecx
0x1800037e0  cmp     edx, eax
0x1800037e2  jnz     short loc_1800037D3
0x1800037e4  mov     eax, edi
0x1800037e6  add     rsp, 28h
0x1800037ea  pop     rdi
0x1800037eb  pop     rsi
0x1800037ec  pop     rbp
0x1800037ed  pop     rbx
0x1800037ee  retn
```
