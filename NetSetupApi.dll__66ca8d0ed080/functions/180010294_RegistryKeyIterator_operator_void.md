# RegistryKeyIterator::operator*(void)

- ea: `0x180010294`
- end: `0x1800102df`
- name: `??DRegistryKeyIterator@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ`
- size: `75`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006af8`

## callees

- `0x1800079b4`

## pseudocode

```c
__int64 __fastcall RegistryKeyIterator::operator*(__int64 a1, __int64 a2)
{
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)a2 = 0;
  RegistryKey::GetSubKeyByIndex(*(_QWORD *)a1, *(unsigned int *)(a1 + 8), a2);
  return a2;
}

```

## disassembly

```asm
0x180010294  mov     [rsp+arg_8], rdx
0x180010299  push    rbx
0x18001029a  sub     rsp, 30h
0x18001029e  mov     [rsp+38h+var_10], 0FFFFFFFFFFFFFFFEh
0x1800102a7  mov     rbx, rdx
0x1800102aa  xor     eax, eax
0x1800102ac  mov     [rsp+38h+var_18], eax
0x1800102b0  mov     qword ptr [rdx+18h], 7
0x1800102b8  mov     [rdx+10h], rax
0x1800102bc  mov     [rdx], ax
0x1800102bf  mov     [rsp+38h+var_18], 1
0x1800102c7  mov     r8, rdx
0x1800102ca  mov     edx, [rcx+8]
0x1800102cd  mov     rcx, [rcx]
0x1800102d0  call    ?GetSubKeyByIndex@RegistryKey@@QEBA_NKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; RegistryKey::GetSubKeyByIndex(ulong,std::wstring &)
0x1800102d5  mov     rax, rbx
0x1800102d8  add     rsp, 30h
0x1800102dc  pop     rbx
0x1800102dd  retn
```
