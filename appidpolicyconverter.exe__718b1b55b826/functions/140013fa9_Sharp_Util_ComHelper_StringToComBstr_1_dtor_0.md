# _Sharp::Util::ComHelper::StringToComBstr_::_1_::dtor$0

- ea: `0x140013fa9`
- end: `0x140013fcf`
- name: `_Sharp::Util::ComHelper::StringToComBstr_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002290`
- `0x140013fa9`

## pseudocode

```c
void __fastcall Sharp::Util::ComHelper::StringToComBstr_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    ATL::CComBSTR::~CComBSTR(*(BSTR **)(a2 + 64));
  }
}

```

## disassembly

```asm
0x140013fa9  push    rbp
0x140013fab  sub     rsp, 20h
0x140013faf  mov     rbp, rdx
0x140013fb2  mov     eax, [rbp+20h]
0x140013fb5  and     eax, 1
0x140013fb8  test    eax, eax
0x140013fba  jz      short loc_140013FC9
0x140013fbc  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x140013fc0  mov     rcx, [rbp+40h]; this
0x140013fc4  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x140013fc9  add     rsp, 20h
0x140013fcd  pop     rbp
0x140013fce  retn
```
