# std::tr1::shared_ptr<IRegistryKey>::_Resetp<RegistryKey>(RegistryKey *)

- ea: `0x1800200c8`
- end: `0x180020128`
- name: `??$_Resetp@VRegistryKey@@@?$shared_ptr@VIRegistryKey@@@tr1@std@@AEAAXPEAVRegistryKey@@@Z`
- size: `96`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180020040`
- `0x1800219d0`

## callees

- `0x180011a64`
- `0x1800200c8`
- `0x180021098`

## pseudocode

```c
__int64 __fastcall std::tr1::shared_ptr<IRegistryKey>::_Resetp<RegistryKey>(__int64 a1, __int64 a2)
{
  _DWORD *v4; // rax
  __int64 result; // rax

  try
  {
    v4 = operator new(0x18u);
    if ( v4 )
    {
      v4[2] = 1;
      v4[3] = 1;
      *(_QWORD *)v4 = &std::tr1::_Ref_count<RegistryKey>::`vftable';
      *((_QWORD *)v4 + 2) = a2;
    }
    result = std::tr1::_Ptr_base<IRegistryMultiStringValue>::_Reset0(a1, a2, v4);
  }
  catch ( ... )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 96LL))(a2, 1);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1800200c8  mov     [rsp+arg_8], rdx
0x1800200cd  push    rdi
0x1800200ce  sub     rsp, 30h
0x1800200d2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800200db  mov     [rsp+38h+arg_0], rbx
0x1800200e0  mov     rbx, rdx
0x1800200e3  mov     rdi, rcx
0x1800200e6  mov     ecx, 18h; Size
0x1800200eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800200f0  test    rax, rax
0x1800200f3  jz      short loc_18002010E
0x1800200f5  mov     ecx, 1
0x1800200fa  mov     [rax+8], ecx
0x1800200fd  mov     [rax+0Ch], ecx
0x180020100  lea     rcx, ??_7?$_Ref_count@VRegistryKey@@@tr1@std@@6B@; const std::tr1::_Ref_count<RegistryKey>::`vftable'
0x180020107  mov     [rax], rcx
0x18002010a  mov     [rax+10h], rbx
0x18002010e  mov     r8, rax
0x180020111  mov     rdx, rbx
0x180020114  mov     rcx, rdi
0x180020117  call    ?_Reset0@?$_Ptr_base@VIRegistryMultiStringValue@@@tr1@std@@QEAAXPEAVIRegistryMultiStringValue@@PEAV_Ref_count_base@23@@Z; std::tr1::_Ptr_base<IRegistryMultiStringValue>::_Reset0(IRegistryMultiStringValue *,std::tr1::_Ref_count_base *)
0x18002011c  nop
0x18002011d  mov     rbx, [rsp+38h+arg_0]
0x180020122  add     rsp, 30h
0x180020126  pop     rdi
0x180020127  retn
```
