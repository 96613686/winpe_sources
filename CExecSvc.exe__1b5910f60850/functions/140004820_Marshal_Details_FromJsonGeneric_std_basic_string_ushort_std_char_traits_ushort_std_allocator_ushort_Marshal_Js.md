# Marshal::Details::FromJsonGeneric<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,>(Marshal::JsonParser &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)

- ea: `0x140004820`
- end: `0x14000488e`
- name: `??$FromJsonGeneric@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVUnmarshalContext@1@U?$integral_constant@_N$00@4@@Z`
- size: `110`
- prototype: `char __fastcall(__int64, void **, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400048f0`
- `0x140004e30`
- `0x140004e60`

## callees

- `0x140002ed8`
- `0x140004820`
- `0x140006790`
- `0x14000b4ac`
- `0x14000b8c8`

## pseudocode

```c
char __fastcall Marshal::Details::FromJsonGeneric<std::wstring,>(__int64 a1, void **a2, __int64 a3)
{
  __int64 v5; // rax
  const void *v6; // rdx
  char result; // al
  int pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+24h] [rbp-14h] BYREF
  __int64 v10; // [rsp+28h] [rbp-10h]

  try
  {
    v10 = a3;
    if ( (unsigned int)Marshal::JsonParser::PeekValueType() != 1 )
    {
      pExceptionObject = 7;
      throw (Marshal::UnmarshalError *)&pExceptionObject;
    }
    v5 = Marshal::JsonParser::ParseString(a1);
    if ( *(_QWORD *)(v5 + 24) <= 7u )
      v6 = (const void *)v5;
    else
      v6 = *(const void **)v5;
    std::wstring::_Assign<unsigned short>(a2, v6, *(_QWORD *)(v5 + 16));
    result = 1;
  }
  catch ( Marshal::UnmarshalError v9 )
  {
    Marshal::UnmarshalContext::ReportError(v10, v9);
    return 0;
  }
  v10 = a3;
}

```

## disassembly

```asm
0x140004820  mov     [rsp+arg_18], rbx
0x140004825  push    rdi
0x140004826  sub     rsp, 30h
0x14000482a  mov     rdi, rdx
0x14000482d  mov     rbx, rcx
0x140004830  mov     [rsp+38h+var_10], r8
0x140004835  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14000483a  cmp     eax, 1
0x14000483d  jnz     short loc_140004873
0x14000483f  mov     rcx, rbx
0x140004842  call    ?ParseString@JsonParser@Marshal@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Marshal::JsonParser::ParseString(void)
0x140004847  cmp     qword ptr [rax+18h], 7
0x14000484c  jbe     short loc_140004853
0x14000484e  mov     rdx, [rax]
0x140004851  jmp     short loc_140004856
0x140004853  mov     rdx, rax
0x140004856  mov     r8, [rax+10h]
0x14000485a  mov     rcx, rdi
0x14000485d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x140004862  mov     al, 1
0x140004864  jmp     short loc_140004868
0x140004866  xor     al, al
0x140004868  mov     rbx, [rsp+38h+arg_18]
0x14000486d  add     rsp, 30h
0x140004871  pop     rdi
0x140004872  retn
0x140004873  mov     [rsp+38h+pExceptionObject], 7
0x14000487b  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x140004882  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x140004887  call    _CxxThrowException_0
```
