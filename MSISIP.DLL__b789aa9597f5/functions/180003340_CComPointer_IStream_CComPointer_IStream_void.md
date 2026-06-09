# CComPointer<IStream>::~CComPointer<IStream>(void)

- ea: `0x180003340`
- end: `0x180003367`
- name: `??1?$CComPointer@UIStream@@@@QEAA@XZ`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f20`
- `0x1800022b0`
- `0x180003a70`
- `0x180005a30`
- `0x180008da8`
- `0x18000ba20`
- `0x18000d410`
- `0x18000d430`
- `0x18000d450`
- `0x18000d470`
- `0x18000d490`
- `0x18000d4b0`
- `0x18000d4d0`

## callees

- `0x180003340`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CComPointer<IStream>::~CComPointer<IStream>(__int64 *a1)
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
0x180003340  sub     rsp, 38h
0x180003344  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000334d  mov     rcx, [rcx]
0x180003350  test    rcx, rcx
0x180003353  jz      short loc_180003362
0x180003355  mov     rax, [rcx]
0x180003358  mov     rax, [rax+10h]
0x18000335c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003361  nop
0x180003362  add     rsp, 38h
0x180003366  retn
```
