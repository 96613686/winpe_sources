# ATL::CComPtr<IMFSample>::~CComPtr<IMFSample>(void)

- ea: `0x18001b31c`
- end: `0x18001b33a`
- name: `??1?$CComPtr@UIMFSample@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022f88`
- `0x180022fc5`
- `0x180022fd7`
- `0x180022fe9`
- `0x180022ffb`

## callees

- `0x18001b31c`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IMFSample>::~CComPtr<IMFSample>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18001b31c  sub     rsp, 28h
0x18001b320  mov     rcx, [rcx]
0x18001b323  test    rcx, rcx
0x18001b326  jz      short loc_18001B335
0x18001b328  mov     rax, [rcx]
0x18001b32b  mov     rax, [rax+10h]
0x18001b32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b334  nop
0x18001b335  add     rsp, 28h
0x18001b339  retn
```
