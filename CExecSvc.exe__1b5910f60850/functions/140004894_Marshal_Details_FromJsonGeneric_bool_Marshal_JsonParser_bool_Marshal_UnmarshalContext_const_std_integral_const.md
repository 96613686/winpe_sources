# Marshal::Details::FromJsonGeneric<bool,>(Marshal::JsonParser &,bool *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)

- ea: `0x140004894`
- end: `0x1400048e9`
- name: `??$FromJsonGeneric@_N$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEA_NAEBVUnmarshalContext@1@U?$integral_constant@_N$00@std@@@Z`
- size: `85`
- prototype: `char __fastcall(Marshal::JsonParser *this, _BYTE *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004cf0`
- `0x140005000`

## callees

- `0x140002ed8`
- `0x140004894`
- `0x14000adb4`
- `0x14000b8c8`

## pseudocode

```c
char __fastcall Marshal::Details::FromJsonGeneric<bool,>(Marshal::JsonParser *this, _BYTE *a2, __int64 a3)
{
  char result; // al
  int pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v7; // [rsp+24h] [rbp-14h] BYREF

  try
  {
    if ( (unsigned int)Marshal::JsonParser::PeekValueType() != 4 )
    {
      pExceptionObject = 9;
      throw (Marshal::UnmarshalError *)&pExceptionObject;
    }
    *a2 = Marshal::JsonParser::ParseBoolean(this);
    result = 1;
  }
  catch ( Marshal::UnmarshalError v7 )
  {
    Marshal::UnmarshalContext::ReportError(a3, v7);
    return 0;
  }
  if ( (unsigned int)Marshal::JsonParser::PeekValueType() != 4 )
  {
    pExceptionObject = 9;
    throw (Marshal::UnmarshalError *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x140004894  mov     [rsp+arg_0], rbx
0x140004899  mov     [rsp+arg_10], r8
0x14000489e  push    rdi
0x14000489f  sub     rsp, 30h
0x1400048a3  mov     rdi, rdx
0x1400048a6  mov     rbx, rcx
0x1400048a9  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x1400048ae  cmp     eax, 4
0x1400048b1  jnz     short loc_1400048CE
0x1400048b3  mov     rcx, rbx; this
0x1400048b6  call    ?ParseBoolean@JsonParser@Marshal@@QEAA_NXZ; Marshal::JsonParser::ParseBoolean(void)
0x1400048bb  mov     [rdi], al
0x1400048bd  mov     al, 1
0x1400048bf  jmp     short loc_1400048C3
0x1400048c1  xor     al, al
0x1400048c3  mov     rbx, [rsp+38h+arg_0]
0x1400048c8  add     rsp, 30h
0x1400048cc  pop     rdi
0x1400048cd  retn
0x1400048ce  mov     [rsp+38h+pExceptionObject], 9
0x1400048d6  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x1400048dd  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x1400048e2  call    _CxxThrowException_0
```
