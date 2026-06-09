# Marshal::Details::FromJsonVoid<vmstd::optional<bool>,Marshal::ModifierList<>>(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &)

- ea: `0x140004cf0`
- end: `0x140004d4e`
- name: `??$FromJsonVoid@U?$optional@_N@vmstd@@U?$ModifierList@$$V@Marshal@@@Details@Marshal@@YA_NAEAVJsonParser@1@PEAXAEBVUnmarshalContext@1@@Z`
- size: `94`
- prototype: `char __fastcall(Marshal::JsonParser *this, _BYTE *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x140004894`
- `0x140004cf0`
- `0x14000af70`
- `0x14000b8c8`

## pseudocode

```c
char __fastcall Marshal::Details::FromJsonVoid<vmstd::optional<bool>,Marshal::ModifierList<>>(
        Marshal::JsonParser *this,
        _BYTE *a2,
        __int64 a3)
{
  _BYTE *v4; // rbx
  char result; // al

  v4 = a2 + 1;
  if ( (unsigned int)Marshal::JsonParser::PeekValueType() == 5 )
  {
    Marshal::JsonParser::ParseNull(this);
    result = 1;
    *v4 = 0;
    *a2 = 0;
  }
  else
  {
    if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 8) == 0 || !*v4 )
    {
      *a2 = 0;
      *v4 = 1;
    }
    return Marshal::Details::FromJsonGeneric<bool,>(this, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x140004cf0  push    rbx
0x140004cf2  push    rbp
0x140004cf3  push    rsi
0x140004cf4  push    rdi
0x140004cf5  sub     rsp, 28h
0x140004cf9  mov     rbp, r8
0x140004cfc  lea     rbx, [rdx+1]
0x140004d00  mov     rdi, rdx
0x140004d03  mov     rsi, rcx
0x140004d06  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x140004d0b  cmp     eax, 5
0x140004d0e  jnz     short loc_140004D22
0x140004d10  mov     rcx, rsi; this
0x140004d13  call    ?ParseNull@JsonParser@Marshal@@QEAAXXZ; Marshal::JsonParser::ParseNull(void)
0x140004d18  mov     al, 1
0x140004d1a  mov     byte ptr [rbx], 0
0x140004d1d  mov     byte ptr [rdi], 0
0x140004d20  jmp     short loc_140004D45
0x140004d22  mov     rax, [rbp+8]
0x140004d26  test    byte ptr [rax+18h], 8
0x140004d2a  jz      short loc_140004D31
0x140004d2c  cmp     byte ptr [rbx], 0
0x140004d2f  jnz     short loc_140004D37
0x140004d31  mov     byte ptr [rdi], 0
0x140004d34  mov     byte ptr [rbx], 1
0x140004d37  mov     r8, rbp
0x140004d3a  mov     rdx, rdi
0x140004d3d  mov     rcx, rsi; this
0x140004d40  call    ??$FromJsonGeneric@_N$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEA_NAEBVUnmarshalContext@1@U?$integral_constant@_N$00@std@@@Z; Marshal::Details::FromJsonGeneric<bool,>(Marshal::JsonParser &,bool *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)
0x140004d45  add     rsp, 28h
0x140004d49  pop     rdi
0x140004d4a  pop     rsi
0x140004d4b  pop     rbp
0x140004d4c  pop     rbx
0x140004d4d  retn
```
