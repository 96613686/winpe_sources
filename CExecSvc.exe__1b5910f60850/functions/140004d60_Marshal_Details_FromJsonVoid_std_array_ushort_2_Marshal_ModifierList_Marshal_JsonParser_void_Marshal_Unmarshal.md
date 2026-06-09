# Marshal::Details::FromJsonVoid<std::array<ushort,2>,Marshal::ModifierList<>>(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &)

- ea: `0x140004d60`
- end: `0x140004e1f`
- name: `??$FromJsonVoid@V?$array@G$01@std@@U?$ModifierList@$$V@Marshal@@@Details@Marshal@@YA_NAEAVJsonParser@1@PEAXAEBVUnmarshalContext@1@@Z`
- size: `191`
- prototype: `char __fastcall(__int64, _WORD *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140004ce0`
- `0x140004d60`
- `0x140008fec`
- `0x14000a714`
- `0x14000b8c8`
- `0x14000bc7c`

## pseudocode

```c
char __fastcall Marshal::Details::FromJsonVoid<std::array<unsigned short,2>,Marshal::ModifierList<>>(
        __int64 a1,
        _WORD *a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  char v8; // bl
  char v9; // si
  __int64 v10; // rbp
  char v11; // al
  __int64 v12; // rdx

  if ( (unsigned int)Marshal::JsonParser::PeekValueType() == 2 )
  {
    LOBYTE(v7) = 93;
    LOBYTE(v6) = 91;
    v9 = 1;
    v8 = 0;
    if ( (unsigned __int8)Marshal::JsonParser::BeginAggregate(a1, v6, v7, 7) )
    {
      v10 = 0;
      while ( 1 )
      {
        v11 = Marshal::Details::FromJsonVoid<unsigned short,>(a1, &a2[v10], a3);
        LOBYTE(v12) = 93;
        v9 = v11 != 0 ? v9 : 0;
        if ( !(unsigned __int8)Marshal::JsonParser::NextElement(a1, v12, 8) )
          break;
        if ( (unsigned __int64)++v10 >= 2 )
        {
          Marshal::UnmarshalContext::ReportError(a3, 19);
          return v8;
        }
      }
    }
    return v9;
  }
  else if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 1) != 0 )
  {
    return Marshal::Details::FromJsonVoid<unsigned short,>(a1, a2, a3);
  }
  else
  {
    Marshal::UnmarshalContext::ReportError(a3, 6);
    return 0;
  }
}

```

## disassembly

```asm
0x140004d60  push    rbx
0x140004d62  push    rbp
0x140004d63  push    rsi
0x140004d64  push    rdi
0x140004d65  push    r14
0x140004d67  push    r15
0x140004d69  sub     rsp, 28h
0x140004d6d  mov     rdi, r8
0x140004d70  mov     r15, rdx
0x140004d73  mov     r14, rcx
0x140004d76  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x140004d7b  cmp     eax, 2
0x140004d7e  jz      short loc_140004DAD
0x140004d80  mov     rax, [rdi+8]
0x140004d84  test    byte ptr [rax+18h], 1
0x140004d88  jz      short loc_140004D9C
0x140004d8a  mov     r8, rdi
0x140004d8d  mov     rdx, r15
0x140004d90  mov     rcx, r14
0x140004d93  call    ??$FromJsonVoid@G$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEAXAEBVUnmarshalContext@1@@Z; Marshal::Details::FromJsonVoid<ushort,>(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &)
0x140004d98  mov     bl, al
0x140004d9a  jmp     short loc_140004E10
0x140004d9c  mov     edx, 6
0x140004da1  mov     rcx, rdi
0x140004da4  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x140004da9  xor     ebx, ebx
0x140004dab  jmp     short loc_140004E10
0x140004dad  mov     r9d, 7
0x140004db3  mov     r8b, 5Dh ; ']'
0x140004db6  mov     dl, 5Bh ; '['
0x140004db8  mov     rcx, r14
0x140004dbb  mov     sil, 1
0x140004dbe  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x140004dc3  xor     ebx, ebx
0x140004dc5  test    al, al
0x140004dc7  jz      short loc_140004E0D
0x140004dc9  mov     ebp, ebx
0x140004dcb  lea     rdx, [r15+rbp*2]
0x140004dcf  mov     r8, rdi
0x140004dd2  mov     rcx, r14
0x140004dd5  call    ??$FromJsonVoid@G$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEAXAEBVUnmarshalContext@1@@Z; Marshal::Details::FromJsonVoid<ushort,>(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &)
0x140004dda  neg     al
0x140004ddc  mov     r8d, 8
0x140004de2  mov     dl, 5Dh ; ']'
0x140004de4  sbb     cl, cl
0x140004de6  and     sil, cl
0x140004de9  mov     rcx, r14
0x140004dec  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x140004df1  test    al, al
0x140004df3  jz      short loc_140004E0D
0x140004df5  inc     rbp
0x140004df8  cmp     rbp, 2
0x140004dfc  jb      short loc_140004DCB
0x140004dfe  mov     edx, 13h
0x140004e03  mov     rcx, rdi
0x140004e06  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x140004e0b  jmp     short loc_140004E10
0x140004e0d  mov     bl, sil
0x140004e10  mov     al, bl
0x140004e12  add     rsp, 28h
0x140004e16  pop     r15
0x140004e18  pop     r14
0x140004e1a  pop     rdi
0x140004e1b  pop     rsi
0x140004e1c  pop     rbp
0x140004e1d  pop     rbx
0x140004e1e  retn
```
