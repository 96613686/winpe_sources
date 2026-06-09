# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_GUID const *)

- ea: `0x140029640`
- end: `0x1400297e6`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_GUID@@@Z`
- size: `422`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140029640`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _GUID *a2)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v3; // rbx
  void (__fastcall *v4)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *); // rax
  __int64 *v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx

  v3 = this;
  v4 = *(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this
                                                                                                 + 200LL);
  if ( a2 )
  {
    v4(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HL__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 400LL))(
      v3,
      a2->Data1);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 392LL))(
      v3,
      a2->Data2);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)v3 + 392LL))(
      v3,
      a2->Data3);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    LOBYTE(v6) = a2->Data4[0];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v6);
    LOBYTE(v7) = a2->Data4[1];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v7);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)v3 + 200LL))(
      v3,
      ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
    LOBYTE(v8) = a2->Data4[2];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v8);
    LOBYTE(v9) = a2->Data4[3];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v9);
    LOBYTE(v10) = a2->Data4[4];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v10);
    LOBYTE(v11) = a2->Data4[5];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v11);
    LOBYTE(v12) = a2->Data4[6];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v12);
    LOBYTE(v13) = a2->Data4[7];
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64))(*(_QWORD *)v3 + 384LL))(
      v3,
      v13);
    v5 = ___LiteralObject__2U__BaseLiteralBuffer__01U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0HN__0A_____0A__00_Details_RtlStringLiterals__3U_LUTF8_STRING__B;
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
0x140029640  mov     [rsp+arg_0], rbx
0x140029645  push    rdi
0x140029646  sub     rsp, 20h
0x14002964a  mov     rax, [rcx]
0x14002964d  mov     rdi, rdx
0x140029650  mov     rbx, rcx
0x140029653  mov     rax, [rax+0C8h]
0x14002965a  test    rdx, rdx
0x14002965d  jnz     short loc_14002966B
0x14002965f  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029666  jmp     loc_1400297D7
0x14002966b  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HL@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029677  mov     rax, [rbx]
0x14002967a  mov     rcx, rbx
0x14002967d  mov     edx, [rdi]
0x14002967f  mov     rax, [rax+190h]
0x140029686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002968b  mov     rax, [rbx]
0x14002968e  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029695  mov     rcx, rbx
0x140029698  mov     rax, [rax+0C8h]
0x14002969f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400296a4  mov     rax, [rbx]
0x1400296a7  mov     rcx, rbx
0x1400296aa  movzx   edx, word ptr [rdi+4]
0x1400296ae  mov     rax, [rax+188h]
0x1400296b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400296ba  mov     rax, [rbx]
0x1400296bd  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1400296c4  mov     rcx, rbx
0x1400296c7  mov     rax, [rax+0C8h]
0x1400296ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400296d3  mov     rax, [rbx]
0x1400296d6  mov     rcx, rbx
0x1400296d9  movzx   edx, word ptr [rdi+6]
0x1400296dd  mov     rax, [rax+188h]
0x1400296e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400296e9  mov     rax, [rbx]
0x1400296ec  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1400296f3  mov     rcx, rbx
0x1400296f6  mov     rax, [rax+0C8h]
0x1400296fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029702  mov     rax, [rbx]
0x140029705  mov     rcx, rbx
0x140029708  mov     dl, [rdi+8]
0x14002970b  mov     rax, [rax+180h]
0x140029712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029717  mov     rax, [rbx]
0x14002971a  mov     rcx, rbx
0x14002971d  mov     dl, [rdi+9]
0x140029720  mov     rax, [rax+180h]
0x140029727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002972c  mov     rax, [rbx]
0x14002972f  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029736  mov     rcx, rbx
0x140029739  mov     rax, [rax+0C8h]
0x140029740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029745  mov     rax, [rbx]
0x140029748  mov     rcx, rbx
0x14002974b  mov     dl, [rdi+0Ah]
0x14002974e  mov     rax, [rax+180h]
0x140029755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002975a  mov     rax, [rbx]
0x14002975d  mov     rcx, rbx
0x140029760  mov     dl, [rdi+0Bh]
0x140029763  mov     rax, [rax+180h]
0x14002976a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002976f  mov     rax, [rbx]
0x140029772  mov     rcx, rbx
0x140029775  mov     dl, [rdi+0Ch]
0x140029778  mov     rax, [rax+180h]
0x14002977f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029784  mov     rax, [rbx]
0x140029787  mov     rcx, rbx
0x14002978a  mov     dl, [rdi+0Dh]
0x14002978d  mov     rax, [rax+180h]
0x140029794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029799  mov     rax, [rbx]
0x14002979c  mov     rcx, rbx
0x14002979f  mov     dl, [rdi+0Eh]
0x1400297a2  mov     rax, [rax+180h]
0x1400297a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400297ae  mov     rax, [rbx]
0x1400297b1  mov     rcx, rbx
0x1400297b4  mov     dl, [rdi+0Fh]
0x1400297b7  mov     rax, [rax+180h]
0x1400297be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400297c3  mov     rax, [rbx]
0x1400297c6  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$01U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0HN@@0A@@@@$0A@$00@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x1400297cd  mov     rcx, rbx
0x1400297d0  mov     rax, [rax+0C8h]
0x1400297d7  mov     rbx, [rsp+28h+arg_0]
0x1400297dc  add     rsp, 20h
0x1400297e0  pop     rdi
0x1400297e1  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
