# Marshal::Details::ToJsonVoid<ushort,>(Marshal::JsonWriter &,void const *,Marshal::MarshalContext const &)

- ea: `0x1400064c0`
- end: `0x14000650f`
- name: `??$ToJsonVoid@G$$V@Details@Marshal@@YA_NAEAVJsonWriter@1@PEBXAEBVMarshalContext@1@@Z`
- size: `79`
- prototype: `char __fastcall(void **, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x140002310`
- `0x140004550`
- `0x14000894c`

## pseudocode

```c
char __fastcall Marshal::Details::ToJsonVoid<unsigned short,>(void **a1, unsigned __int16 *a2)
{
  _BYTE v4[64]; // [rsp+20h] [rbp-58h] BYREF

  Marshal::Details::FormatString<32>(v4, L"%llu", *a2);
  std::wstring::operator+=(*a1, v4);
  return 1;
}

```

## disassembly

```asm
0x1400064c0  push    rbx
0x1400064c2  sub     rsp, 70h
0x1400064c6  mov     rax, cs:__security_cookie
0x1400064cd  xor     rax, rsp
0x1400064d0  mov     [rsp+78h+var_18], rax
0x1400064d5  movzx   r8d, word ptr [rdx]
0x1400064d9  mov     rbx, rcx
0x1400064dc  lea     rdx, aLlu; "%llu"
0x1400064e3  lea     rcx, [rsp+78h+var_58]
0x1400064e8  call    ??$FormatString@$0CA@@Details@Marshal@@YAXAEAY0CA@GPEBGZZ; Marshal::Details::FormatString<32>(ushort (&)[32],ushort const *,...)
0x1400064ed  mov     rcx, [rbx]; Src
0x1400064f0  lea     rdx, [rsp+78h+var_58]; void *
0x1400064f5  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x1400064fa  mov     al, 1
0x1400064fc  mov     rcx, [rsp+78h+var_18]
0x140006501  xor     rcx, rsp; StackCookie
0x140006504  call    __security_check_cookie
0x140006509  add     rsp, 70h
0x14000650d  pop     rbx
0x14000650e  retn
```
