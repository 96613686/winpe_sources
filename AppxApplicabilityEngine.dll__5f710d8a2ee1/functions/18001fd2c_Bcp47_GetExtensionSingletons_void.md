# Bcp47::GetExtensionSingletons(void)

- ea: `0x18001fd2c`
- end: `0x18001fd60`
- name: `?GetExtensionSingletons@Bcp47@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001ffc4`

## callees

- `0x18000d8f8`
- `0x18001fa7c`
- `0x18001fd2c`

## pseudocode

```c
__int64 __fastcall Bcp47::GetExtensionSingletons(__int64 a1, __int64 a2, __int64 a3)
{
  if ( (*(_BYTE *)(a1 + 32) & 0x60) != 0 )
    Bcp47::GetExtensionSingletons(a2, a1, a3);
  else
    std::wstring::wstring(a2, &qword_18002C640);
  return a2;
}

```

## disassembly

```asm
0x18001fd2c  push    rbx
0x18001fd2e  sub     rsp, 30h
0x18001fd32  test    byte ptr [rcx+20h], 60h
0x18001fd36  mov     rbx, rdx
0x18001fd39  jz      short loc_18001FD48
0x18001fd3b  mov     rdx, rcx
0x18001fd3e  mov     rcx, rbx
0x18001fd41  call    ?GetExtensionSingletons@Bcp47@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVCLanguage@Internal@Windows@@@Z; Bcp47::GetExtensionSingletons(Windows::Internal::CLanguage const &)
0x18001fd46  jmp     short loc_18001FD57
0x18001fd48  lea     rdx, qword_18002C640
0x18001fd4f  mov     rcx, rbx
0x18001fd52  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001fd57  mov     rax, rbx
0x18001fd5a  add     rsp, 30h
0x18001fd5e  pop     rbx
0x18001fd5f  retn
```
