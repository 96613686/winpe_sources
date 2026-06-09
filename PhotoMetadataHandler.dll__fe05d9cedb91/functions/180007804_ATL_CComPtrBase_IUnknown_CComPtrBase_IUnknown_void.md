# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180007804`
- end: `0x180007822`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006860`
- `0x18000d5b4`
- `0x18000e84c`
- `0x18000ee6c`
- `0x180010520`
- `0x180010830`
- `0x180013c88`
- `0x180013e70`
- `0x1800156d0`
- `0x18001833c`
- `0x18001a658`
- `0x18001ad6c`
- `0x18001ae18`
- `0x18001b5e0`
- `0x18001b884`
- `0x18001b95c`
- `0x18001bc9c`
- `0x18001bf8c`
- `0x18001c690`
- `0x18001d2a8`
- `0x18001d38c`
- `0x18001d46c`
- `0x18001d678`
- `0x18001d850`
- `0x18001da50`
- `0x18001dc58`
- `0x18001e434`
- `0x18001f724`
- `0x180020f20`

## callees

- `0x180007804`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
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
0x180007804  sub     rsp, 28h
0x180007808  mov     rcx, [rcx]
0x18000780b  test    rcx, rcx
0x18000780e  jz      short loc_18000781D
0x180007810  mov     rax, [rcx]
0x180007813  mov     rax, [rax+10h]
0x180007817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000781c  nop
0x18000781d  add     rsp, 28h
0x180007821  retn
```
