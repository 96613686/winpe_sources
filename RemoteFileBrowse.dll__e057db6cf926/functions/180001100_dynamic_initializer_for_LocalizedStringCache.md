# _dynamic_initializer_for__LocalizedStringCache__

- ea: `0x180001100`
- end: `0x180001136`
- name: `_dynamic_initializer_for__LocalizedStringCache__`
- size: `54`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000208c`
- `0x18000248c`

## pseudocode

```c
int dynamic_initializer_for__LocalizedStringCache__()
{
  _QWORD *v0; // rax

  v0 = operator new(0x48u);
  *v0 = v0;
  v0[1] = v0;
  v0[2] = v0;
  *((_WORD *)v0 + 12) = 257;
  LocalizedStringCache = (__int64)v0;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__LocalizedStringCache__);
}

```

## disassembly

```asm
0x180001100  sub     rsp, 28h
0x180001104  mov     ecx, 48h ; 'H'; Size
0x180001109  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000110e  lea     rcx, _dynamic_atexit_destructor_for__LocalizedStringCache__
0x180001115  mov     [rax], rax
0x180001118  mov     [rax+8], rax
0x18000111c  mov     [rax+10h], rax
0x180001120  mov     word ptr [rax+18h], 101h
0x180001126  mov     cs:?LocalizedStringCache@@3V?$map@HV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@@std@@A, rax; std::map<int,std::wstring> LocalizedStringCache
0x18000112d  add     rsp, 28h
0x180001131  jmp     atexit
```
