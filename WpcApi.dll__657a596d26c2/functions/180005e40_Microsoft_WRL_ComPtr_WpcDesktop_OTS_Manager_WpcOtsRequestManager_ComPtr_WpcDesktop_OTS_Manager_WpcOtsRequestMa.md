# Microsoft::WRL::ComPtr<WpcDesktop::OTS::Manager::WpcOtsRequestManager>::~ComPtr<WpcDesktop::OTS::Manager::WpcOtsRequestManager>(void)

- ea: `0x180005e40`
- end: `0x180005e68`
- name: `??1?$ComPtr@VWpcOtsRequestManager@Manager@OTS@WpcDesktop@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002954b`
- `0x18002956f`
- `0x1800296a3`

## callees

- `0x180005e40`
- `0x18002c010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<WpcDesktop::OTS::Manager::WpcOtsRequestManager>::~ComPtr<WpcDesktop::OTS::Manager::WpcOtsRequestManager>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180005e40  sub     rsp, 28h
0x180005e44  mov     rax, rcx
0x180005e47  mov     rcx, [rcx]
0x180005e4a  test    rcx, rcx
0x180005e4d  jz      short loc_180005E63
0x180005e4f  mov     qword ptr [rax], 0
0x180005e56  mov     rax, [rcx]
0x180005e59  mov     rax, [rax+10h]
0x180005e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e62  nop
0x180005e63  add     rsp, 28h
0x180005e67  retn
```
