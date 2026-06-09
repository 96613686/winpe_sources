# _PolicyModel::CFileHash::GetXmlName_::_1_::dtor$0

- ea: `0x140014880`
- end: `0x1400148a6`
- name: `_PolicyModel::CFileHash::GetXmlName_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007e2c`
- `0x140014880`

## pseudocode

```c
__int64 __fastcall PolicyModel::CFileHash::GetXmlName_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 72), a2);
  }
  return result;
}

```

## disassembly

```asm
0x140014880  push    rbp
0x140014882  sub     rsp, 20h
0x140014886  mov     rbp, rdx
0x140014889  mov     eax, [rbp+20h]
0x14001488c  and     eax, 1
0x14001488f  test    eax, eax
0x140014891  jz      short loc_1400148A0
0x140014893  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x140014897  mov     rcx, [rbp+48h]
0x14001489b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400148a0  add     rsp, 20h
0x1400148a4  pop     rbp
0x1400148a5  retn
```
