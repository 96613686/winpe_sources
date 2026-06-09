# Microsoft::WRL::SimpleClassFactory<CEditionUpgradeBroker,0>::`vector deleting destructor'(uint)

- ea: `0x180008540`
- end: `0x180008568`
- name: `??_E?$SimpleClassFactory@VCEditionUpgradeBroker@@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001cb0`
- `0x180008540`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::SimpleClassFactory<CEditionUpgradeBroker,0>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[3] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180008540  push    rbx
0x180008542  sub     rsp, 20h
0x180008546  mov     dword ptr [rcx+0Ch], 0C0000001h
0x18000854d  mov     rbx, rcx
0x180008550  test    dl, 1
0x180008553  jz      short loc_18000855F
0x180008555  mov     edx, 18h; unsigned __int64
0x18000855a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000855f  mov     rax, rbx
0x180008562  add     rsp, 20h
0x180008566  pop     rbx
0x180008567  retn
```
