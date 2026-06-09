# std::_Func_class<std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(void)

- ea: `0x14000878c`
- end: `0x1400087be`
- name: `??1?$_Func_class@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBU__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001@@_NU_Nil@2@U42@U42@U42@U42@@std@@QEAA@XZ`
- size: `50`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400124b8`
- `0x140012514`
- `0x14001258b`
- `0x14001259d`

## callees

- `0x14000878c`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall std::_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::~_Func_class<std::map<std::wstring const,std::wstring>,__MIDL___MIDL_itf_privatespellcheck_0000_0003_0001 const &,bool,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *(_QWORD *)(a1 + 24);
  if ( v3 )
  {
    LOBYTE(a2) = v3 != a1;
    result = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 32LL))(v3, a2);
    *(_QWORD *)(a1 + 24) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000878c  push    rbx
0x14000878e  sub     rsp, 20h
0x140008792  mov     rbx, rcx
0x140008795  mov     rcx, [rcx+18h]
0x140008799  test    rcx, rcx
0x14000879c  jz      short loc_1400087B8
0x14000879e  mov     rax, [rcx]
0x1400087a1  cmp     rcx, rbx
0x1400087a4  setnz   dl
0x1400087a7  mov     rax, [rax+20h]
0x1400087ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087b0  mov     qword ptr [rbx+18h], 0
0x1400087b8  add     rsp, 20h
0x1400087bc  pop     rbx
0x1400087bd  retn
```
