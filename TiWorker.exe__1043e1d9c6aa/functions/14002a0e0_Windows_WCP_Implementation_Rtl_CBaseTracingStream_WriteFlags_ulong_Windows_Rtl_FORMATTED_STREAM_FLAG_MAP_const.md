# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteFlags(ulong,Windows::Rtl::_FORMATTED_STREAM_FLAG_MAP const *)

- ea: `0x14002a0e0`
- end: `0x14002a212`
- name: `?WriteFlags@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXKPEBU_FORMATTED_STREAM_FLAG_MAP@25@@Z`
- size: `306`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned int, const struct Windows::Rtl::_FORMATTED_STREAM_FLAG_MAP *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14002a0e0`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteFlags(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned int a2,
        const struct Windows::Rtl::_FORMATTED_STREAM_FLAG_MAP *a3)
{
  char v3; // r13
  unsigned __int64 v6; // r15
  char v7; // bp
  __int64 v8; // r12
  unsigned __int64 v9; // rsi
  void (__fastcall *v10)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  void (__fastcall *v11)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax

  v3 = 0;
  if ( !a3 )
    goto LABEL_12;
  v6 = *(_QWORD *)a3;
  v7 = 0;
  v8 = *((_QWORD *)a3 + 1);
  v9 = 0;
  if ( !*(_QWORD *)a3 )
    goto LABEL_12;
  do
  {
    if ( (a2 & *(_DWORD *)(v8 + 16 * v9)) == *(_DWORD *)(v8 + 16 * v9) )
    {
      v10 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL);
      if ( v7 )
      {
        v10(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HM__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      }
      else
      {
        v10(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
        v3 = 1;
        v7 = 1;
      }
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 224LL))(
        this,
        *(_QWORD *)(v8 + 16 * v9 + 8));
      a2 &= ~*(_DWORD *)(v8 + 16 * v9);
    }
    ++v9;
  }
  while ( v9 < v6 );
  if ( !v7 )
    goto LABEL_12;
  if ( a2 )
  {
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HM__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
LABEL_12:
    v11 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL);
    if ( a2 )
    {
      v11(
        this,
        ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0DA__0HI__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 400LL))(
        this,
        a2);
    }
    else
    {
      v11(
        this,
        ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0DA__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    }
  }
  if ( v3 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CJ__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
}

```

## disassembly

```asm
0x14002a0e0  push    rbx
0x14002a0e2  push    rbp
0x14002a0e3  push    rsi
0x14002a0e4  push    rdi
0x14002a0e5  push    r12
0x14002a0e7  push    r13
0x14002a0e9  push    r14
0x14002a0eb  push    r15
0x14002a0ed  sub     rsp, 28h
0x14002a0f1  xor     r13b, r13b
0x14002a0f4  mov     edi, edx
0x14002a0f6  mov     rbx, rcx
0x14002a0f9  test    r8, r8
0x14002a0fc  jz      loc_14002A1A4
0x14002a102  mov     r15, [r8]
0x14002a105  xor     bpl, bpl
0x14002a108  mov     r12, [r8+8]
0x14002a10c  xor     esi, esi
0x14002a10e  test    r15, r15
0x14002a111  jz      loc_14002A1A4
0x14002a117  mov     r14, rsi
0x14002a11a  add     r14, r14
0x14002a11d  mov     eax, [r12+r14*8]
0x14002a121  and     eax, edi
0x14002a123  cmp     eax, [r12+r14*8]
0x14002a127  jnz     short loc_14002A17A
0x14002a129  mov     rax, [rbx]
0x14002a12c  mov     rcx, rbx
0x14002a12f  mov     rax, [rax+0C8h]
0x14002a136  test    bpl, bpl
0x14002a139  jnz     short loc_14002A14F
0x14002a13b  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002a142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a147  mov     r13b, 1
0x14002a14a  mov     bpl, r13b
0x14002a14d  jmp     short loc_14002A15B
0x14002a14f  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HM@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002a156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a15b  mov     rax, [rbx]
0x14002a15e  mov     rcx, rbx
0x14002a161  mov     rdx, [r12+r14*8+8]
0x14002a166  mov     rax, [rax+0E0h]
0x14002a16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a172  mov     eax, [r12+r14*8]
0x14002a176  not     eax
0x14002a178  and     edi, eax
0x14002a17a  inc     rsi
0x14002a17d  cmp     rsi, r15
0x14002a180  jb      short loc_14002A117
0x14002a182  test    bpl, bpl
0x14002a185  jz      short loc_14002A1A4
0x14002a187  test    edi, edi
0x14002a189  jz      short loc_14002A1E3
0x14002a18b  mov     rax, [rbx]
0x14002a18e  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HM@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002a195  mov     rcx, rbx
0x14002a198  mov     rax, [rax+0C8h]
0x14002a19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a1a4  mov     rax, [rbx]
0x14002a1a7  mov     rcx, rbx
0x14002a1aa  mov     rax, [rax+0C8h]
0x14002a1b1  test    edi, edi
0x14002a1b3  jnz     short loc_14002A1C3
0x14002a1b5  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0DA@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002a1bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a1c1  jmp     short loc_14002A1E3
0x14002a1c3  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0DA@@0HI@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002a1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a1cf  mov     rax, [rbx]
0x14002a1d2  mov     edx, edi
0x14002a1d4  mov     rcx, rbx
0x14002a1d7  mov     rax, [rax+190h]
0x14002a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a1e3  test    r13b, r13b
0x14002a1e6  jz      short loc_14002A201
0x14002a1e8  mov     rax, [rbx]
0x14002a1eb  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CJ@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002a1f2  mov     rcx, rbx
0x14002a1f5  mov     rax, [rax+0C8h]
0x14002a1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a201  add     rsp, 28h
0x14002a205  pop     r15
0x14002a207  pop     r14
0x14002a209  pop     r13
0x14002a20b  pop     r12
0x14002a20d  pop     rdi
0x14002a20e  pop     rsi
0x14002a20f  pop     rbp
0x14002a210  pop     rbx
0x14002a211  retn
```
