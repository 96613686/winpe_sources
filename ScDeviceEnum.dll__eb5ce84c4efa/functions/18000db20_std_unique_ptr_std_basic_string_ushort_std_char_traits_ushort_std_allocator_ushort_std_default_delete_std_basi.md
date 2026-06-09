# std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::_Delete(void)

- ea: `0x18000db20`
- end: `0x18000db4a`
- name: `?_Delete@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ`
- size: `42`
- prototype: `void __fastcall(_QWORD *, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000c954`
- `0x18000ca98`
- `0x18000db7c`
- `0x180010150`
- `0x180010dd0`
- `0x1800118c0`

## callees

- `0x180009840`
- `0x18000db20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000db3e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000db3e`

## pseudocode

```c
void __fastcall std::unique_ptr<std::wstring>::_Delete(_QWORD *a1, __int64 a2)
{
  void *v2; // rbx

  v2 = (void *)*a1;
  if ( *a1 )
  {
    LOBYTE(a2) = 1;
    std::wstring::_Tidy(*a1, a2, 0);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x18000db20  push    rbx
0x18000db22  sub     rsp, 20h
0x18000db26  mov     rbx, [rcx]
0x18000db29  test    rbx, rbx
0x18000db2c  jz      short loc_18000DB44
0x18000db2e  xor     r8d, r8d
0x18000db31  mov     dl, 1
0x18000db33  mov     rcx, rbx
0x18000db36  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000db3b  mov     rcx, rbx
0x18000db3e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000db44  add     rsp, 20h
0x18000db48  pop     rbx
0x18000db49  retn
```
