# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_LBLOB const *)

- ea: `0x1400297f0`
- end: `0x140029911`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_LBLOB@@@Z`
- size: `289`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LBLOB *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400297f0`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LBLOB *a2)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v3; // rdi
  void (__fastcall *v4)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  __int64 *v5; // rdx
  unsigned __int64 v6; // rsi
  __int64 v7; // rbx
  __int64 v8; // rbp
  __int64 v9; // rbx
  __int64 v10; // rdx

  v3 = this;
  v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this
                                                                                                 + 200LL);
  if ( a2 )
  {
    v6 = *(_QWORD *)a2;
    v7 = *((_QWORD *)a2 + 1);
    v4(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HL__0GM__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
      v3,
      *(_QWORD *)a2);
    if ( v6 != v7 )
    {
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
        v3,
        ___LiteralObject__2U__BaseLiteralBuffer__04U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CA__0GN__0GM__0DK__0A_____0A__00_01_02_03_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
        v3,
        *((_QWORD *)a2 + 1));
    }
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CA__0GC__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    if ( v6 <= 0x80 )
    {
      v8 = v6;
      if ( !v6 )
      {
LABEL_12:
        v5 = ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
        this = v3;
        v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL);
        goto LABEL_13;
      }
    }
    else
    {
      v8 = 128;
    }
    v9 = 0;
    do
    {
      v10 = *((_QWORD *)a2 + 2);
      LOBYTE(v10) = *(_BYTE *)(v9 + v10);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
        v3,
        v10);
      ++v9;
    }
    while ( v9 != v8 );
    if ( v6 > 0x80 )
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
        v3,
        ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CO__0CO__0CO__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    goto LABEL_12;
  }
  v5 = ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0GO__0HF__0GM__0GM__0CJ__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
LABEL_13:
  v4(this, v5);
}

```

## disassembly

```asm
0x1400297f0  push    rbx
0x1400297f2  push    rbp
0x1400297f3  push    rsi
0x1400297f4  push    rdi
0x1400297f5  push    r14
0x1400297f7  push    r15
0x1400297f9  sub     rsp, 28h
0x1400297fd  mov     rax, [rcx]
0x140029800  mov     r14, rdx
0x140029803  mov     rdi, rcx
0x140029806  mov     rax, [rax+0C8h]
0x14002980d  test    rdx, rdx
0x140029810  jnz     short loc_14002981E
0x140029812  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029819  jmp     loc_140029900
0x14002981e  mov     rsi, [rdx]
0x140029821  mov     rbx, [rdx+8]
0x140029825  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HL@@0GM@@0DK@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002982c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029831  mov     rax, [rdi]
0x140029834  mov     rcx, rdi
0x140029837  mov     rdx, [r14]
0x14002983a  mov     rax, [rax+178h]
0x140029841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029846  cmp     rsi, rbx
0x140029849  jz      short loc_14002987A
0x14002984b  mov     rax, [rdi]
0x14002984e  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$04U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CA@@0GN@@0GM@@0DK@@0A@@@@$0A@$00$01$02$03@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029855  mov     rcx, rdi
0x140029858  mov     rax, [rax+0C8h]
0x14002985f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029864  mov     rax, [rdi]
0x140029867  mov     rcx, rdi
0x14002986a  mov     rdx, [r14+8]
0x14002986e  mov     rax, [rax+178h]
0x140029875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002987a  mov     rax, [rdi]
0x14002987d  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CA@@0GC@@0DK@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029884  mov     rcx, rdi
0x140029887  mov     rax, [rax+0C8h]
0x14002988e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029893  mov     r15d, 80h
0x140029899  cmp     rsi, r15
0x14002989c  jbe     short loc_1400298A3
0x14002989e  mov     ebp, r15d
0x1400298a1  jmp     short loc_1400298AB
0x1400298a3  mov     rbp, rsi
0x1400298a6  test    rsi, rsi
0x1400298a9  jz      short loc_1400298EC
0x1400298ab  xor     ebx, ebx
0x1400298ad  mov     rax, [rdi]
0x1400298b0  mov     rcx, rdi
0x1400298b3  mov     rdx, [r14+10h]
0x1400298b7  mov     rax, [rax+180h]
0x1400298be  mov     dl, [rbx+rdx]
0x1400298c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400298c6  inc     rbx
0x1400298c9  cmp     rbx, rbp
0x1400298cc  jnz     short loc_1400298AD
0x1400298ce  cmp     rsi, r15
0x1400298d1  jbe     short loc_1400298EC
0x1400298d3  mov     rax, [rdi]
0x1400298d6  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CO@@0CO@@0CO@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1400298dd  mov     rcx, rdi
0x1400298e0  mov     rax, [rax+0C8h]
0x1400298e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400298ec  mov     rax, [rdi]
0x1400298ef  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1400298f6  mov     rcx, rdi
0x1400298f9  mov     rax, [rax+0C8h]
0x140029900  add     rsp, 28h
0x140029904  pop     r15
0x140029906  pop     r14
0x140029908  pop     rdi
0x140029909  pop     rsi
0x14002990a  pop     rbp
0x14002990b  pop     rbx
0x14002990c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
