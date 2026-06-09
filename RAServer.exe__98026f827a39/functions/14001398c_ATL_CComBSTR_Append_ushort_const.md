# ATL::CComBSTR::Append(ushort const *)

- ea: `0x14001398c`
- end: `0x1400139ad`
- name: `?Append@CComBSTR@ATL@@QEAAJPEBG@Z`
- size: `33`
- prototype: `int __fastcall(ATL::CComBSTR *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140013a88`
- `0x140013ef8`
- `0x140014ccc`

## callees

- `0x14000c1f0`
- `0x1400139b4`

## pseudocode

```c
int __fastcall ATL::CComBSTR::Append(ATL::CComBSTR *this, const unsigned __int16 *a2)
{
  int v2; // eax
  const unsigned __int16 *v3; // rcx
  ATL::CComBSTR *v4; // r10

  v2 = ocslen(a2);
  return ATL::CComBSTR::Append(v4, v3, v2);
}

```

## disassembly

```asm
0x14001398c  sub     rsp, 28h
0x140013990  mov     r10, rcx
0x140013993  mov     rcx, rdx; unsigned __int16 *
0x140013996  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x14001399b  mov     rdx, rcx; unsigned __int16 *
0x14001399e  mov     r8d, eax; int
0x1400139a1  mov     rcx, r10; this
0x1400139a4  add     rsp, 28h
0x1400139a8  jmp     ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
```
