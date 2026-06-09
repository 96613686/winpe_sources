# _BitsHelper::CreateDownloadJob_::_1_::dtor$0

- ea: `0x140018b33`
- end: `0x140018b5c`
- name: `_BitsHelper::CreateDownloadJob_::_1_::dtor$0`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140005c14`
- `0x140018b33`

## pseudocode

```c
__int64 __fastcall BitsHelper::CreateDownloadJob_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 56) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 56) &= ~1u;
    return std::wstring::~wstring(a2 + 176);
  }
  return result;
}

```

## disassembly

```asm
0x140018b33  push    rbp
0x140018b35  sub     rsp, 20h
0x140018b39  mov     rbp, rdx
0x140018b3c  mov     eax, [rbp+38h]
0x140018b3f  and     eax, 1
0x140018b42  test    eax, eax
0x140018b44  jz      short loc_140018B56
0x140018b46  and     dword ptr [rbp+38h], 0FFFFFFFEh
0x140018b4a  lea     rcx, [rbp+0B0h]
0x140018b51  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b56  add     rsp, 20h
0x140018b5a  pop     rbp
0x140018b5b  retn
```
