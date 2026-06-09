# Sharp::Util::ComHelper::StringToComBstr(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400080e4`
- end: `0x14000811a`
- name: `?StringToComBstr@ComHelper@Util@Sharp@@YA?AVCComBSTR@ATL@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `54`
- prototype: `ATL::CComBSTR *__fastcall(ATL::CComBSTR *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007edc`

## callees

- `0x140007de4`
- `0x1400080e4`

## pseudocode

```c
ATL::CComBSTR *__fastcall Sharp::Util::ComHelper::StringToComBstr(ATL::CComBSTR *a1, const unsigned __int16 *a2)
{
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(const unsigned __int16 **)a2;
  ATL::CComBSTR::CComBSTR(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x1400080e4  mov     [rsp+arg_0], rcx
0x1400080e9  push    rbx
0x1400080ea  sub     rsp, 30h
0x1400080ee  mov     rbx, rcx
0x1400080f1  mov     [rsp+38h+var_18], 0
0x1400080f9  cmp     qword ptr [rdx+18h], 8
0x1400080fe  jb      short loc_140008103
0x140008100  mov     rdx, [rdx]; unsigned __int16 *
0x140008103  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140008108  mov     [rsp+38h+var_18], 1
0x140008110  mov     rax, rbx
0x140008113  add     rsp, 30h
0x140008117  pop     rbx
0x140008118  retn
```
