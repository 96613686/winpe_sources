# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_LUNICODE_STRING const *)

- ea: `0x140029920`
- end: `0x140029a6c`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_LUNICODE_STRING@@@Z`
- size: `332`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _LUNICODE_STRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140029920`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _LUNICODE_STRING *a2)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v3; // rbx
  void (__fastcall *v4)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  __int64 *v5; // rdx
  unsigned __int64 v6; // rsi
  bool v7; // zf

  v3 = this;
  v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this
                                                                                                 + 200LL);
  if ( a2 )
  {
    v6 = *(_QWORD *)a2;
    if ( *((_QWORD *)a2 + 1) == *(_QWORD *)a2 )
    {
      v4(
        this,
        ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FL__0GM__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64))(*(_QWORD *)v3 + 376LL))(
        v3,
        v6 >> 1);
      v7 = (v6 & 1) == 0;
    }
    else
    {
      v4(
        this,
        ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FL__0GM__0DK__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
        v3,
        *(_QWORD *)a2 >> 1);
      if ( (*(_BYTE *)a2 & 1) != 0 )
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
          v3,
          ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CB__0CB__0CB__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
        v3,
        ___LiteralObject__2U__BaseLiteralBuffer__04U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CA__0GN__0GM__0DK__0A_____0A__00_01_02_03_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 376LL))(
        v3,
        *((_QWORD *)a2 + 1) >> 1);
      v7 = (*((_BYTE *)a2 + 8) & 1) == 0;
    }
    if ( !v7 )
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
        v3,
        ___LiteralObject__2U__BaseLiteralBuffer__03U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CB__0CB__0CB__0A_____0A__00_01_02_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FN__0CH__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD, _QWORD))(*(_QWORD *)v3 + 288LL))(
      v3,
      *(_QWORD *)a2 >> 1,
      *((_QWORD *)a2 + 2));
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CH__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
    this = v3;
    v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL);
  }
  else
  {
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0GO__0HF__0GM__0GM__0CJ__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
  }
  v4(this, v5);
}

```

## disassembly

```asm
0x140029920  mov     [rsp+arg_0], rbx
0x140029925  mov     [rsp+arg_8], rsi
0x14002992a  push    rdi
0x14002992b  sub     rsp, 20h
0x14002992f  mov     rax, [rcx]
0x140029932  mov     rdi, rdx
0x140029935  mov     rbx, rcx
0x140029938  mov     rax, [rax+0C8h]
0x14002993f  test    rdx, rdx
0x140029942  jnz     short loc_140029950
0x140029944  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002994b  jmp     loc_140029A58
0x140029950  mov     rsi, [rdx]
0x140029953  cmp     [rdx+8], rsi
0x140029957  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FL@@0GM@@0DK@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002995e  jnz     short loc_140029983
0x140029960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029965  mov     rax, [rbx]
0x140029968  mov     rdx, rsi
0x14002996b  shr     rdx, 1
0x14002996e  mov     rcx, rbx
0x140029971  mov     rax, [rax+178h]
0x140029978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002997d  test    sil, 1
0x140029981  jmp     short loc_1400299F4
0x140029983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029988  mov     rax, [rbx]
0x14002998b  mov     rcx, rbx
0x14002998e  mov     rdx, [rdi]
0x140029991  shr     rdx, 1
0x140029994  mov     rax, [rax+178h]
0x14002999b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400299a0  test    byte ptr [rdi], 1
0x1400299a3  jz      short loc_1400299BE
0x1400299a5  mov     rax, [rbx]
0x1400299a8  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CB@@0CB@@0CB@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1400299af  mov     rcx, rbx
0x1400299b2  mov     rax, [rax+0C8h]
0x1400299b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400299be  mov     rax, [rbx]
0x1400299c1  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$04U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CA@@0GN@@0GM@@0DK@@0A@@@@$0A@$00$01$02$03@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1400299c8  mov     rcx, rbx
0x1400299cb  mov     rax, [rax+0C8h]
0x1400299d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400299d7  mov     rax, [rbx]
0x1400299da  mov     rcx, rbx
0x1400299dd  mov     rdx, [rdi+8]
0x1400299e1  shr     rdx, 1
0x1400299e4  mov     rax, [rax+178h]
0x1400299eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400299f0  test    byte ptr [rdi+8], 1
0x1400299f4  jz      short loc_140029A0F
0x1400299f6  mov     rax, [rbx]
0x1400299f9  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$03U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CB@@0CB@@0CB@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029a00  mov     rcx, rbx
0x140029a03  mov     rax, [rax+0C8h]
0x140029a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029a0f  mov     rax, [rbx]
0x140029a12  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FN@@0CH@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029a19  mov     rcx, rbx
0x140029a1c  mov     rax, [rax+0C8h]
0x140029a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029a28  mov     rax, [rbx]
0x140029a2b  mov     rcx, rbx
0x140029a2e  mov     rdx, [rdi]
0x140029a31  mov     r8, [rdi+10h]
0x140029a35  shr     rdx, 1
0x140029a38  mov     rax, [rax+120h]
0x140029a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029a44  mov     rax, [rbx]
0x140029a47  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CH@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029a4e  mov     rcx, rbx
0x140029a51  mov     rax, [rax+0C8h]
0x140029a58  mov     rbx, [rsp+28h+arg_0]
0x140029a5d  mov     rsi, [rsp+28h+arg_8]
0x140029a62  add     rsp, 20h
0x140029a66  pop     rdi
0x140029a67  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
