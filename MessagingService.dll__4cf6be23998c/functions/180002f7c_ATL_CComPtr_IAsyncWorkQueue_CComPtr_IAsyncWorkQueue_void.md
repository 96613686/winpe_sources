# ATL::CComPtr<IAsyncWorkQueue>::~CComPtr<IAsyncWorkQueue>(void)

- ea: `0x180002f7c`
- end: `0x180002f9a`
- name: `??1?$CComPtr@UIAsyncWorkQueue@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000aeae`
- `0x18000aee4`
- `0x18000aef6`
- `0x18000af2c`
- `0x18000af50`

## callees

- `0x180002f7c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IAsyncWorkQueue>::~CComPtr<IAsyncWorkQueue>(__int64 *a1)
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
0x180002f7c  sub     rsp, 28h
0x180002f80  mov     rcx, [rcx]
0x180002f83  test    rcx, rcx
0x180002f86  jz      short loc_180002F95
0x180002f88  mov     rax, [rcx]
0x180002f8b  mov     rax, [rax+10h]
0x180002f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f94  nop
0x180002f95  add     rsp, 28h
0x180002f99  retn
```
