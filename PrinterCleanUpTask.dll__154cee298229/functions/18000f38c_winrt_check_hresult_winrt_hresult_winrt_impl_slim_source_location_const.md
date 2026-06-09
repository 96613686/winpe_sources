# winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)

- ea: `0x18000f38c`
- end: `0x18000f3ab`
- name: `?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z`
- size: `31`
- prototype: `int *__fastcall(int *, int, __int64)`
- caller_count: `46`
- callee_count: `2`
- tags: ``

## callers

- `0x180007708`
- `0x180008a2c`
- `0x180008c20`
- `0x180008c80`
- `0x180009710`
- `0x1800097d8`
- `0x18000b0b4`
- `0x18000b2a8`
- `0x18000ba9c`
- `0x18000bb00`
- `0x18000becc`
- `0x18000c09c`
- `0x18000c120`
- `0x18000c344`
- `0x18000ca54`
- `0x18000cb54`
- `0x18000d1c0`
- `0x18000d22c`
- `0x18000d2e8`
- `0x18000da60`
- `0x18000db1c`
- `0x18000dfa4`
- `0x18000e8e4`
- `0x18000ea04`
- `0x18000ea58`
- `0x18000eb14`
- `0x18000ef84`
- `0x180010d48`
- `0x180010db4`
- `0x180010f38`
- `0x180010fb8`
- `0x180011060`
- `0x180011e4c`
- `0x1800123dc`
- `0x18001247c`
- `0x1800125a8`
- `0x180012bf0`
- `0x180012cac`
- `0x180013764`
- `0x1800144e0`
- `0x180014638`
- `0x1800146f4`
- `0x1800149f4`
- `0x180015a3c`
- `0x180015b60`
- `0x180015cd4`

## callees

- `0x18000f38c`
- `0x18001000c`

## pseudocode

```c
int *__fastcall winrt::check_hresult(int *a1, int a2, __int64 a3)
{
  if ( a2 < 0 )
    winrt::throw_hresult((unsigned int)a2, a3);
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x18000f38c  sub     rsp, 28h
0x18000f390  mov     eax, edx
0x18000f392  test    edx, edx
0x18000f394  js      short loc_18000F3A0
0x18000f396  mov     [rcx], edx
0x18000f398  mov     rax, rcx
0x18000f39b  add     rsp, 28h
0x18000f39f  retn
0x18000f3a0  mov     rdx, r8
0x18000f3a3  mov     ecx, eax
0x18000f3a5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
