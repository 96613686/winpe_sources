# ATL::CComPtr<ISpellCheckProvider>::~CComPtr<ISpellCheckProvider>(void)

- ea: `0x1400085f0`
- end: `0x14000860e`
- name: `??1?$CComPtr@UISpellCheckProvider@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001248c`
- `0x1400124a2`

## callees

- `0x1400085f0`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ISpellCheckProvider>::~CComPtr<ISpellCheckProvider>(__int64 *a1)
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
0x1400085f0  sub     rsp, 28h
0x1400085f4  mov     rcx, [rcx]
0x1400085f7  test    rcx, rcx
0x1400085fa  jz      short loc_140008609
0x1400085fc  mov     rax, [rcx]
0x1400085ff  mov     rax, [rax+10h]
0x140008603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008608  nop
0x140008609  add     rsp, 28h
0x14000860d  retn
```
