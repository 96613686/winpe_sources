# _ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$0

- ea: `0x18000ea64`
- end: `0x18000ea8a`
- name: `_ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000627c`
- `0x18000ea64`

## pseudocode

```c
__int64 __fastcall ComUtils::GitComLockableWrapper_ITabletContextP_::GetComObject_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return ATL::CComPtr<ITabletContextP>::~CComPtr<ITabletContextP>(*(__int64 **)(a2 + 104));
  }
  return result;
}

```

## disassembly

```asm
0x18000ea64  push    rbp
0x18000ea66  sub     rsp, 20h
0x18000ea6a  mov     rbp, rdx
0x18000ea6d  mov     eax, [rbp+30h]
0x18000ea70  and     eax, 1
0x18000ea73  test    eax, eax
0x18000ea75  jz      short loc_18000EA84
0x18000ea77  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000ea7b  mov     rcx, [rbp+68h]
0x18000ea7f  call    ??1?$CComPtr@UITabletContextP@@@ATL@@QEAA@XZ
0x18000ea84  add     rsp, 20h
0x18000ea88  pop     rbp
0x18000ea89  retn
```
