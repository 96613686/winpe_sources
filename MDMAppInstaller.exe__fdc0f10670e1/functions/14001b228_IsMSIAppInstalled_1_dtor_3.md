# _IsMSIAppInstalled_::_1_::dtor$3

- ea: `0x14001b228`
- end: `0x14001b251`
- name: `_IsMSIAppInstalled_::_1_::dtor$3`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140003c10`
- `0x14001b228`

## pseudocode

```c
__int64 __fastcall IsMSIAppInstalled_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 48) & 2;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 48) &= ~2u;
    return std::pair<std::wstring,unsigned long>::~pair<std::wstring,unsigned long>(a2 + 152, a2);
  }
  return result;
}

```

## disassembly

```asm
0x14001b228  push    rbp
0x14001b22a  sub     rsp, 20h
0x14001b22e  mov     rbp, rdx
0x14001b231  mov     eax, [rbp+30h]
0x14001b234  and     eax, 2
0x14001b237  test    eax, eax
0x14001b239  jz      short loc_14001B24B
0x14001b23b  and     dword ptr [rbp+30h], 0FFFFFFFDh
0x14001b23f  lea     rcx, [rbp+98h]
0x14001b246  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@QEAA@XZ; std::pair<std::wstring,ulong>::~pair<std::wstring,ulong>(void)
0x14001b24b  add     rsp, 20h
0x14001b24f  pop     rbp
0x14001b250  retn
```
