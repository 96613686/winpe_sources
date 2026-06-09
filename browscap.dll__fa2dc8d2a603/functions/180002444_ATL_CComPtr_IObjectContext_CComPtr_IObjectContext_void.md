# ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>(void)

- ea: `0x180002444`
- end: `0x180002462`
- name: `??1?$CComPtr@UIObjectContext@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bbe5`
- `0x18000bbf7`
- `0x18000bc09`
- `0x18000bd45`
- `0x18000beba`

## callees

- `0x180002444`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IObjectContext>::~CComPtr<IObjectContext>(__int64 *a1)
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
0x180002444  sub     rsp, 28h
0x180002448  mov     rcx, [rcx]
0x18000244b  test    rcx, rcx
0x18000244e  jz      short loc_18000245D
0x180002450  mov     rax, [rcx]
0x180002453  mov     rax, [rax+10h]
0x180002457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000245c  nop
0x18000245d  add     rsp, 28h
0x180002461  retn
```
