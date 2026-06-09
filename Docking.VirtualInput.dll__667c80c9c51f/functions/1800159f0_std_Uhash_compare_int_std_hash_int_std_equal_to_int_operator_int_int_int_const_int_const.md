# std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int,int>(int const &,int const &)

- ea: `0x1800159f0`
- end: `0x180015a4c`
- name: `??$?RHH@?$_Uhash_compare@HU?$hash@H@std@@U?$equal_to@H@2@@std@@QEBA_NAEBH0@Z`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015ce0`
- `0x180018bd0`

## callees

- `0x18000b810`
- `0x1800159f0`
- `0x18001705c`

## pseudocode

```c
_BOOL8 __fastcall std::_Uhash_compare<int,std::hash<int>,std::equal_to<int>>::operator()<int,int>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // [rsp+28h] [rbp-10h]

  v4 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a1);
  return (unsigned __int8)std::equal_to<int>::operator()(v4, a2, a3) == 0;
}

```

## disassembly

```asm
0x1800159f0  mov     [rsp+arg_10], r8
0x1800159f5  mov     [rsp+arg_8], rdx
0x1800159fa  mov     [rsp+arg_0], rcx
0x1800159ff  sub     rsp, 38h
0x180015a03  mov     rax, [rsp+38h+arg_0]
0x180015a08  mov     rcx, rax
0x180015a0b  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180015a10  mov     [rsp+38h+var_10], rax
0x180015a15  mov     r8, [rsp+38h+arg_10]
0x180015a1a  mov     rdx, [rsp+38h+arg_8]
0x180015a1f  mov     rcx, [rsp+38h+var_10]
0x180015a24  call    ??R?$equal_to@H@std@@QEBA_NAEBH0@Z; std::equal_to<int>::operator()(int const &,int const &)
0x180015a29  movzx   eax, al
0x180015a2c  test    eax, eax
0x180015a2e  jnz     short loc_180015A3A
0x180015a30  mov     [rsp+38h+var_18], 1
0x180015a38  jmp     short loc_180015A42
0x180015a3a  mov     [rsp+38h+var_18], 0
0x180015a42  movzx   eax, byte ptr [rsp+38h+var_18]
0x180015a47  add     rsp, 38h
0x180015a4b  retn
```
