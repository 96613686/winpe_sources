# Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(void)

- ea: `0x140007bc0`
- end: `0x140007be8`
- name: `??1?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e80a`

## callees

- `0x140007bc0`
- `0x14000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(_QWORD *a1)
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
0x140007bc0  sub     rsp, 28h
0x140007bc4  mov     rax, rcx
0x140007bc7  mov     rcx, [rcx]
0x140007bca  test    rcx, rcx
0x140007bcd  jz      short loc_140007BE3
0x140007bcf  mov     qword ptr [rax], 0
0x140007bd6  mov     rax, [rcx]
0x140007bd9  mov     rax, [rax+10h]
0x140007bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007be2  nop
0x140007be3  add     rsp, 28h
0x140007be7  retn
```
