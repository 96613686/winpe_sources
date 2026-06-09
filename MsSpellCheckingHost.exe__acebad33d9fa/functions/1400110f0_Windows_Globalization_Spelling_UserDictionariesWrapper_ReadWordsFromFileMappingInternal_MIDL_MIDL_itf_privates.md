# Windows::Globalization::Spelling::UserDictionariesWrapper::ReadWordsFromFileMappingInternal(__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool)

- ea: `0x1400110f0`
- end: `0x140011107`
- name: `?ReadWordsFromFileMappingInternal@UserDictionariesWrapper@Spelling@Globalization@Windows@@SA?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_N@Z`
- size: `23`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140010d08`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::UserDictionariesWrapper::ReadWordsFromFileMappingInternal(
        __int64 a1)
{
  Windows::Globalization::Spelling::ReadWordsFromFileMapping();
  return a1;
}

```

## disassembly

```asm
0x1400110f0  push    rbx
0x1400110f2  sub     rsp, 30h
0x1400110f6  mov     rbx, rcx
0x1400110f9  call    Windows__Globalization__Spelling__ReadWordsFromFileMapping
0x1400110fe  mov     rax, rbx
0x140011101  add     rsp, 30h
0x140011105  pop     rbx
0x140011106  retn
```
