# Marshal::Details::FromJsonVoid<std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,Marshal::ModifierList<>>(Marshal::JsonParser &,void *,Marshal::UnmarshalContext const &)

- ea: `0x140004e60`
- end: `0x140004ff4`
- name: `??$FromJsonVoid@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@U?$ModifierList@$$V@Marshal@@@Details@Marshal@@YA_NAEAVJsonParser@1@PEAXAEBVUnmarshalContext@1@@Z`
- size: `404`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x140004820`
- `0x140004e60`
- `0x140006db4`
- `0x1400077b8`
- `0x140008160`
- `0x140008fec`
- `0x14000a714`
- `0x14000b8c8`
- `0x14000bc7c`

## pseudocode

```c
char __fastcall Marshal::Details::FromJsonVoid<std::vector<std::wstring>,Marshal::ModifierList<>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rsi
  void **v9; // rdx
  unsigned __int64 v10; // rcx
  void **v11; // rbp
  void **j; // rdi
  __int64 v13; // rax
  bool v15; // si
  char i; // al
  __int64 v17; // rdx
  __int64 v18; // rdx

  if ( (unsigned int)Marshal::JsonParser::PeekValueType() == 2 )
  {
    LOBYTE(v7) = 93;
    LOBYTE(v6) = 91;
    v15 = 1;
    for ( i = Marshal::JsonParser::BeginAggregate(a1, v6, v7, 7); i; i = Marshal::JsonParser::NextElement(a1, v18, 8) )
    {
      v17 = *(_QWORD *)(a2 + 8);
      if ( v17 == *(_QWORD *)(a2 + 16) )
      {
        std::vector<std::wstring>::_Emplace_reallocate<>(a2);
      }
      else
      {
        *(_OWORD *)v17 = 0;
        *(_QWORD *)(v17 + 16) = 0;
        *(_QWORD *)(v17 + 24) = 7;
        *(_WORD *)v17 = 0;
        *(_QWORD *)(a2 + 8) += 32LL;
      }
      if ( !Marshal::Details::FromJsonGeneric<std::wstring,>(a1, (void **)(*(_QWORD *)(a2 + 8) - 32LL), a3) )
      {
        std::wstring::~wstring(*(_QWORD *)(a2 + 8) - 32LL);
        *(_QWORD *)(a2 + 8) -= 32LL;
        v15 = (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 4) == 0;
      }
      LOBYTE(v18) = 93;
    }
    return v15;
  }
  else if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 1) != 0 )
  {
    v8 = *(_QWORD *)(a2 + 8);
    v9 = *(void ***)a2;
    v10 = (v8 - *(_QWORD *)a2) >> 5;
    if ( v10 <= 1 )
    {
      if ( !v10 )
      {
        if ( (__int64)(*(_QWORD *)(a2 + 16) - (_QWORD)v9) >> 5 )
        {
          v13 = 1;
          do
          {
            *(_OWORD *)v8 = 0;
            *(_QWORD *)(v8 + 16) = 0;
            *(_QWORD *)(v8 + 24) = 7;
            *(_WORD *)v8 = 0;
            v8 += 32;
            --v13;
          }
          while ( v13 );
          *(_QWORD *)(a2 + 8) = v8;
        }
        else
        {
          std::vector<std::wstring>::_Resize_reallocate<std::_Value_init_tag>(a2);
        }
      }
    }
    else
    {
      v11 = v9 + 4;
      for ( j = v9 + 4; j != (void **)v8; j += 4 )
        std::wstring::~wstring(j);
      *(_QWORD *)(a2 + 8) = v11;
    }
    return Marshal::Details::FromJsonGeneric<std::wstring,>(a1, *(void ***)a2, a3);
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
0x140004e60  mov     [rsp+arg_18], rbx
0x140004e65  push    rbp
0x140004e66  push    rsi
0x140004e67  push    rdi
0x140004e68  push    r14
0x140004e6a  push    r15
0x140004e6c  sub     rsp, 20h
0x140004e70  mov     r14, r8
0x140004e73  mov     rbx, rdx
0x140004e76  mov     r15, rcx
0x140004e79  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x140004e7e  cmp     eax, 2
0x140004e81  jz      loc_140004F45
0x140004e87  mov     rax, [r14+8]
0x140004e8b  test    byte ptr [rax+18h], 1
0x140004e8f  jz      loc_140004F31
0x140004e95  mov     rsi, [rbx+8]
0x140004e99  mov     rdx, [rbx]
0x140004e9c  mov     rcx, rsi
0x140004e9f  sub     rcx, rdx
0x140004ea2  sar     rcx, 5
0x140004ea6  cmp     rcx, 1
0x140004eaa  jbe     short loc_140004ECF
0x140004eac  lea     rbp, [rdx+20h]
0x140004eb0  mov     rdi, rbp
0x140004eb3  cmp     rbp, rsi
0x140004eb6  jz      short loc_140004EC9
0x140004eb8  mov     rcx, rdi
0x140004ebb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004ec0  add     rdi, 20h ; ' '
0x140004ec4  cmp     rdi, rsi
0x140004ec7  jnz     short loc_140004EB8
0x140004ec9  mov     [rbx+8], rbp
0x140004ecd  jmp     short loc_140004F1B
0x140004ecf  jnb     short loc_140004F1B
0x140004ed1  mov     rax, [rbx+10h]
0x140004ed5  sub     rax, rdx
0x140004ed8  sar     rax, 5
0x140004edc  cmp     rax, 1
0x140004ee0  jnb     short loc_140004EEC
0x140004ee2  mov     rcx, rbx
0x140004ee5  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<std::wstring>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140004eea  jmp     short loc_140004F1B
0x140004eec  mov     eax, 1
0x140004ef1  sub     rax, rcx
0x140004ef4  jz      short loc_140004F17
0x140004ef6  xor     edi, edi
0x140004ef8  xorps   xmm0, xmm0
0x140004efb  movups  xmmword ptr [rsi], xmm0
0x140004efe  mov     [rsi+10h], rdi
0x140004f02  mov     qword ptr [rsi+18h], 7
0x140004f0a  mov     [rsi], di
0x140004f0d  add     rsi, 20h ; ' '
0x140004f11  sub     rax, 1
0x140004f15  jnz     short loc_140004EF8
0x140004f17  mov     [rbx+8], rsi
0x140004f1b  mov     rdx, [rbx]
0x140004f1e  mov     r8, r14
0x140004f21  mov     rcx, r15
0x140004f24  call    ??$FromJsonGeneric@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVUnmarshalContext@1@U?$integral_constant@_N$00@4@@Z; Marshal::Details::FromJsonGeneric<std::wstring,>(Marshal::JsonParser &,std::wstring *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)
0x140004f29  mov     dil, al
0x140004f2c  jmp     loc_140004FE0
0x140004f31  mov     edx, 6
0x140004f36  mov     rcx, r14
0x140004f39  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x140004f3e  xor     edi, edi
0x140004f40  jmp     loc_140004FE0
0x140004f45  mov     r9d, 7
0x140004f4b  mov     r8b, 5Dh ; ']'
0x140004f4e  mov     dl, 5Bh ; '['
0x140004f50  mov     rcx, r15
0x140004f53  mov     sil, 1
0x140004f56  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x140004f5b  xor     edi, edi
0x140004f5d  jmp     short loc_140004FD9
0x140004f5f  mov     rdx, [rbx+8]
0x140004f63  cmp     rdx, [rbx+10h]
0x140004f67  jz      short loc_140004F85
0x140004f69  xorps   xmm0, xmm0
0x140004f6c  movups  xmmword ptr [rdx], xmm0
0x140004f6f  mov     [rdx+10h], rdi
0x140004f73  mov     qword ptr [rdx+18h], 7
0x140004f7b  mov     [rdx], di
0x140004f7e  add     qword ptr [rbx+8], 20h ; ' '
0x140004f83  jmp     short loc_140004F8D
0x140004f85  mov     rcx, rbx
0x140004f88  call    ??$_Emplace_reallocate@$$V@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<>(std::wstring * const)
0x140004f8d  mov     rdx, [rbx+8]
0x140004f91  mov     r8, r14
0x140004f94  sub     rdx, 20h ; ' '
0x140004f98  mov     rcx, r15
0x140004f9b  call    ??$FromJsonGeneric@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVUnmarshalContext@1@U?$integral_constant@_N$00@4@@Z; Marshal::Details::FromJsonGeneric<std::wstring,>(Marshal::JsonParser &,std::wstring *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)
0x140004fa0  test    al, al
0x140004fa2  jnz     short loc_140004FC9
0x140004fa4  mov     rcx, [rbx+8]
0x140004fa8  sub     rcx, 20h ; ' '
0x140004fac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004fb1  add     qword ptr [rbx+8], 0FFFFFFFFFFFFFFE0h
0x140004fb6  mov     rax, [r14+8]
0x140004fba  mov     sil, [rax+18h]
0x140004fbe  shr     sil, 2
0x140004fc2  not     sil
0x140004fc5  and     sil, 1
0x140004fc9  mov     r8d, 8
0x140004fcf  mov     dl, 5Dh ; ']'
0x140004fd1  mov     rcx, r15
0x140004fd4  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x140004fd9  test    al, al
0x140004fdb  jnz     short loc_140004F5F
0x140004fdd  mov     dil, sil
0x140004fe0  mov     rbx, [rsp+48h+arg_18]
0x140004fe5  mov     al, dil
0x140004fe8  add     rsp, 20h
0x140004fec  pop     r15
0x140004fee  pop     r14
0x140004ff0  pop     rdi
0x140004ff1  pop     rsi
0x140004ff2  pop     rbp
0x140004ff3  retn
```
