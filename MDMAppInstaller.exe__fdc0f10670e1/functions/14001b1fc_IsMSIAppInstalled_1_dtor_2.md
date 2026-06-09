# _IsMSIAppInstalled_::_1_::dtor$2

- ea: `0x14001b1fc`
- end: `0x14001b222`
- name: `_IsMSIAppInstalled_::_1_::dtor$2`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140003c10`
- `0x14001b1fc`

## pseudocode

```c
__int64 __fastcall IsMSIAppInstalled_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    return std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(a2 + 120, a2);
  }
  return result;
}

```

## disassembly

```asm
0x14001b1fc  push    rbp
0x14001b1fe  sub     rsp, 20h
0x14001b202  mov     rbp, rdx
0x14001b205  mov     eax, [rbp+30h]
0x14001b208  and     eax, 1
0x14001b20b  test    eax, eax
0x14001b20d  jz      short loc_14001B21C
0x14001b20f  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x14001b213  lea     rcx, [rbp+78h]
0x14001b217  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x14001b21c  add     rsp, 20h
0x14001b220  pop     rbp
0x14001b221  retn
```
