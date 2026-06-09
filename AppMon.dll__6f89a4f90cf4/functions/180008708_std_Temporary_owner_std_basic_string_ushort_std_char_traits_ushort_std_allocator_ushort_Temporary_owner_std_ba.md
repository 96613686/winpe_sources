# std::_Temporary_owner<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>::~_Temporary_owner<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(void)

- ea: `0x180008708`
- end: `0x180008723`
- name: `??1?$_Temporary_owner@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008c1c`
- `0x18000f6fb`

## callees

- `0x180008708`
- `0x180009424`

## pseudocode

```c
__int64 __fastcall std::_Temporary_owner<std::wstring>::~_Temporary_owner<std::wstring>(void **a1)
{
  void *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return std::wstring::`scalar deleting destructor'(v1);
  return result;
}

```

## disassembly

```asm
0x180008708  sub     rsp, 28h
0x18000870c  mov     rcx, [rcx]; void *
0x18000870f  test    rcx, rcx
0x180008712  jz      short loc_18000871E
0x180008714  mov     edx, 1
0x180008719  call    ??_G?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x18000871e  add     rsp, 28h
0x180008722  retn
```
