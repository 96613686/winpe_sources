# ATL::CComPtr<IUsoSession>::~CComPtr<IUsoSession>(void)

- ea: `0x140005d18`
- end: `0x140005d36`
- name: `??1?$CComPtr@UIUsoSession@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400074d4`
- `0x1400074e6`

## callees

- `0x140005d18`
- `0x140008010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IUsoSession>::~CComPtr<IUsoSession>(__int64 *a1)
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
0x140005d18  sub     rsp, 28h
0x140005d1c  mov     rcx, [rcx]
0x140005d1f  test    rcx, rcx
0x140005d22  jz      short loc_140005D31
0x140005d24  mov     rax, [rcx]
0x140005d27  mov     rax, [rax+10h]
0x140005d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d30  nop
0x140005d31  add     rsp, 28h
0x140005d35  retn
```
