# ATL::CComPtr<IRendezvousSession>::operator=(IRendezvousSession *)

- ea: `0x140011460`
- end: `0x14001148c`
- name: `??4?$CComPtr@UIRendezvousSession@@@ATL@@QEAAPEAUIRendezvousSession@@PEAU2@@Z`
- size: `44`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400055b8`
- `0x1400056e4`
- `0x1400114c4`

## callees

- `0x140011460`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IRendezvousSession>::operator=(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140011460  push    rbx
0x140011462  sub     rsp, 20h
0x140011466  mov     rbx, rcx
0x140011469  mov     rcx, [rcx]
0x14001146c  test    rcx, rcx
0x14001146f  jz      short loc_140011484
0x140011471  mov     rax, [rcx]
0x140011474  mov     rax, [rax+10h]
0x140011478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001147d  mov     qword ptr [rbx], 0
0x140011484  xor     eax, eax
0x140011486  add     rsp, 20h
0x14001148a  pop     rbx
0x14001148b  retn
```
