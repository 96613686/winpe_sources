# Windows::Globalization::Spelling::CHostSpellCheckProvider::ComprehensiveCheck(ushort const *,IEnumSpellingError * *)

- ea: `0x140009900`
- end: `0x140009925`
- name: `?ComprehensiveCheck@CHostSpellCheckProvider@Spelling@Globalization@Windows@@UEAAJPEBGPEAPEAUIEnumSpellingError@@@Z`
- size: `37`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling::CHostSpellCheckProvider *__hidden this, const unsigned __int16 *, struct IEnumSpellingError **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140009900`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostSpellCheckProvider::ComprehensiveCheck(
        Windows::Globalization::Spelling::CHostSpellCheckProvider *this,
        const unsigned __int16 *a2,
        struct IEnumSpellingError **a3)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 6);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IEnumSpellingError **))(*(_QWORD *)v4 + 24LL))(
             v4,
             a2,
             a3);
  else
    return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, struct IEnumSpellingError **))(**((_QWORD **)this + 5) + 32LL))(
             *((_QWORD *)this + 5),
             a2,
             a3);
}

```

## disassembly

```asm
0x140009900  mov     rax, rcx
0x140009903  mov     rcx, [rcx+30h]
0x140009907  test    rcx, rcx
0x14000990a  jz      short loc_140009915
0x14000990c  mov     rax, [rcx]
0x14000990f  mov     rax, [rax+18h]
0x140009913  jmp     short loc_140009920
0x140009915  mov     rcx, [rax+28h]
0x140009919  mov     rax, [rcx]
0x14000991c  mov     rax, [rax+20h]
0x140009920  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
