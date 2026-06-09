# Marshal::Details::FromJsonGeneric<ushort,>(Marshal::JsonParser &,ushort *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)

- ea: `0x140004748`
- end: `0x140004818`
- name: `??$FromJsonGeneric@G$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEAGAEBVUnmarshalContext@1@U?$integral_constant@_N$00@std@@@Z`
- size: `208`
- prototype: `char __fastcall(__int64, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140004ce0`

## callees

- `0x140002ed8`
- `0x140004748`
- `0x14000b040`
- `0x14000b8c8`
- `0x14000bc7c`

## pseudocode

```c
char __fastcall Marshal::Details::FromJsonGeneric<unsigned short,>(__int64 a1, _WORD *a2, __int64 a3)
{
  __int64 v6; // rax
  char result; // al
  int pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  int v9; // [rsp+24h] [rbp-24h] BYREF
  int v10; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v11; // [rsp+2Ch] [rbp-1Ch] BYREF
  __int64 v12; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+38h] [rbp-10h]

  try
  {
    if ( (unsigned int)Marshal::JsonParser::PeekValueType() )
    {
      pExceptionObject = 2;
      throw (Marshal::UnmarshalError *)&pExceptionObject;
    }
    Marshal::JsonParser::ParseNumber(a1, &v12);
    if ( v13 )
    {
      if ( v13 != 1 )
      {
        v9 = 2;
        throw (Marshal::UnmarshalError *)&v9;
      }
      v6 = v12;
      if ( v12 < 0 )
      {
        v10 = 2;
        throw (Marshal::UnmarshalError *)&v10;
      }
    }
    else
    {
      v6 = v12;
    }
    if ( (unsigned __int16)v6 == v6 )
    {
      *a2 = v6;
      result = 1;
    }
    else
    {
      Marshal::UnmarshalContext::ReportError(a3, 4);
      result = 0;
    }
  }
  catch ( Marshal::UnmarshalError v11 )
  {
    Marshal::UnmarshalContext::ReportError(a3, v11);
    return 0;
  }
  if ( (unsigned int)Marshal::JsonParser::PeekValueType() )
  {
    pExceptionObject = 2;
    throw (Marshal::UnmarshalError *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x140004748  mov     [rsp+arg_0], rbx
0x14000474d  mov     [rsp+arg_8], rsi
0x140004752  mov     [rsp+arg_10], r8
0x140004757  push    rdi
0x140004758  sub     rsp, 40h
0x14000475c  mov     rdi, r8
0x14000475f  mov     rsi, rdx
0x140004762  mov     rbx, rcx
0x140004765  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14000476a  test    eax, eax
0x14000476c  jnz     short loc_1400047CB
0x14000476e  lea     rdx, [rsp+48h+var_18]
0x140004773  mov     rcx, rbx
0x140004776  call    ?ParseNumber@JsonParser@Marshal@@QEAA?AUNumber@12@XZ; Marshal::JsonParser::ParseNumber(void)
0x14000477b  mov     ecx, [rsp+48h+var_10]
0x14000477f  test    ecx, ecx
0x140004781  jz      short loc_140004794
0x140004783  cmp     ecx, 1
0x140004786  jnz     short loc_1400047E4
0x140004788  mov     rax, [rsp+48h+var_18]
0x14000478d  test    rax, rax
0x140004790  js      short loc_1400047FD
0x140004792  jmp     short loc_140004799
0x140004794  mov     rax, [rsp+48h+var_18]
0x140004799  movzx   ecx, ax
0x14000479c  cmp     rcx, rax
0x14000479f  jz      short loc_1400047B2
0x1400047a1  mov     edx, 4
0x1400047a6  mov     rcx, rdi
0x1400047a9  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x1400047ae  xor     al, al
0x1400047b0  jmp     short loc_1400047B7
0x1400047b2  mov     [rsi], cx
0x1400047b5  mov     al, 1
0x1400047b7  jmp     short loc_1400047BB
0x1400047b9  xor     al, al
0x1400047bb  mov     rbx, [rsp+48h+arg_0]
0x1400047c0  mov     rsi, [rsp+48h+arg_8]
0x1400047c5  add     rsp, 40h
0x1400047c9  pop     rdi
0x1400047ca  retn
0x1400047cb  mov     [rsp+48h+pExceptionObject], 2
0x1400047d3  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x1400047da  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400047df  call    _CxxThrowException_0
0x1400047e4  mov     [rsp+48h+var_24], 2
0x1400047ec  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x1400047f3  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x1400047f8  call    _CxxThrowException_0
0x1400047fd  mov     [rsp+48h+var_20], 2
0x140004805  lea     rdx, _TI1?AW4UnmarshalError@Marshal@@; pThrowInfo
0x14000480c  lea     rcx, [rsp+48h+var_20]; pExceptionObject
0x140004811  call    _CxxThrowException_0
```
