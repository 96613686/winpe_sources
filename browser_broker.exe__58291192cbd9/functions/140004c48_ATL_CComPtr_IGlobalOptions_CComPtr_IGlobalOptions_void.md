# ATL::CComPtr<IGlobalOptions>::~CComPtr<IGlobalOptions>(void)

- ea: `0x140004c48`
- end: `0x140004c65`
- name: `??1?$CComPtr@UIGlobalOptions@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x140004c48`
- `0x140006010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IGlobalOptions>::~CComPtr<IGlobalOptions>(__int64 *a1)
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
0x140004c48  sub     rsp, 28h
0x140004c4c  mov     rcx, [rcx]
0x140004c4f  test    rcx, rcx
0x140004c52  jz      short loc_140004C60
0x140004c54  mov     rax, [rcx]
0x140004c57  mov     rax, [rax+10h]
0x140004c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c60  add     rsp, 28h
0x140004c64  retn
```
