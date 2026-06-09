# _GetSidString_::_1_::dtor$0

- ea: `0x180012205`
- end: `0x18001222b`
- name: `_GetSidString_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006b04`
- `0x180012205`

## pseudocode

```c
__int64 __fastcall GetSidString_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::~HandleT<LocalAllocStringBufferTraits>(*(_QWORD *)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x180012205  push    rbp
0x180012207  sub     rsp, 20h
0x18001220b  mov     rbp, rdx
0x18001220e  mov     eax, [rbp+20h]
0x180012211  and     eax, 1
0x180012214  test    eax, eax
0x180012216  jz      short loc_180012225
0x180012218  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18001221c  mov     rcx, [rbp+40h]
0x180012220  call    ??1?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@QEAA@XZ
0x180012225  add     rsp, 20h
0x180012229  pop     rbp
0x18001222a  retn
```
