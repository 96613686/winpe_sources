# _ComUtils::GitComLockableWrapper_IUnknown_::GetComObject_::_1_::dtor$0

- ea: `0x18000f19f`
- end: `0x18000f1c5`
- name: `_ComUtils::GitComLockableWrapper_IUnknown_::GetComObject_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c474`
- `0x18000f19f`

## pseudocode

```c
__int64 __fastcall ComUtils::GitComLockableWrapper_IUnknown_::GetComObject_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return ATL::CComPtr<IUnknown>::~CComPtr<IUnknown>(*(__int64 **)(a2 + 104));
  }
  return result;
}

```

## disassembly

```asm
0x18000f19f  push    rbp
0x18000f1a1  sub     rsp, 20h
0x18000f1a5  mov     rbp, rdx
0x18000f1a8  mov     eax, [rbp+30h]
0x18000f1ab  and     eax, 1
0x18000f1ae  test    eax, eax
0x18000f1b0  jz      short loc_18000F1BF
0x18000f1b2  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000f1b6  mov     rcx, [rbp+68h]
0x18000f1ba  call    ??1?$CComPtr@UIUnknown@@@ATL@@QEAA@XZ
0x18000f1bf  add     rsp, 20h
0x18000f1c3  pop     rbp
0x18000f1c4  retn
```
