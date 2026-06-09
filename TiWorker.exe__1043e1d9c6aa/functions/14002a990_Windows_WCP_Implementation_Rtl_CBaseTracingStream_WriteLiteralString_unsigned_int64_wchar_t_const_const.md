# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(unsigned __int64,wchar_t const * const)

- ea: `0x14002a990`
- end: `0x14002aaa1`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEB_W@Z`
- size: `273`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int64, const wchar_t *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002310`
- `0x14002a990`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int64 a2,
        const wchar_t *const a3)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 i; // rsi
  wchar_t v8; // bp
  _BYTE v9[32]; // [rsp+20h] [rbp-58h] BYREF

  if ( a2 && a3 )
  {
    v6 = 0;
    for ( i = 0; i < a2; ++i )
    {
      v8 = a3[i];
      if ( v6 >= 0x20 )
      {
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64, _BYTE *))(*(_QWORD *)this + 280LL))(
          this,
          32,
          v9);
        v6 = 0;
      }
      if ( v8 >= 0x80u )
      {
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, _BYTE *))(*(_QWORD *)this + 280LL))(
          this,
          v6,
          v9);
        v6 = 0;
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FM__0HF__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 392LL))(
          this,
          v8);
      }
      else
      {
        v9[v6++] = v8;
      }
    }
    if ( v6 )
      (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, _BYTE *))(*(_QWORD *)this + 280LL))(
        this,
        v6,
        v9);
  }
}

```

## disassembly

```asm
0x14002a990  test    rdx, rdx
0x14002a993  jz      locret_14002AAA0
0x14002a999  mov     [rsp+arg_8], rbx
0x14002a99e  push    rbp
0x14002a99f  push    rsi
0x14002a9a0  push    rdi
0x14002a9a1  push    r14
0x14002a9a3  push    r15
0x14002a9a5  sub     rsp, 50h
0x14002a9a9  mov     rax, cs:__security_cookie
0x14002a9b0  xor     rax, rsp
0x14002a9b3  mov     [rsp+78h+var_38], rax
0x14002a9b8  mov     r14, r8
0x14002a9bb  mov     r15, rdx
0x14002a9be  mov     rdi, rcx
0x14002a9c1  test    r8, r8
0x14002a9c4  jz      loc_14002AA80
0x14002a9ca  xor     ebx, ebx
0x14002a9cc  xor     esi, esi
0x14002a9ce  movzx   ebp, word ptr [r14+rsi*2]
0x14002a9d3  cmp     rbx, 20h ; ' '
0x14002a9d7  jb      short loc_14002A9F7
0x14002a9d9  mov     rax, [rdi]
0x14002a9dc  lea     r8, [rsp+78h+var_58]
0x14002a9e1  mov     edx, 20h ; ' '
0x14002a9e6  mov     rcx, rdi
0x14002a9e9  mov     rax, [rax+118h]
0x14002a9f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a9f5  xor     ebx, ebx
0x14002a9f7  mov     eax, 80h
0x14002a9fc  cmp     bp, ax
0x14002a9ff  jnb     short loc_14002AA0B
0x14002aa01  mov     [rsp+rbx+78h+var_58], bpl
0x14002aa06  inc     rbx
0x14002aa09  jmp     short loc_14002AA55
0x14002aa0b  mov     rax, [rdi]
0x14002aa0e  lea     r8, [rsp+78h+var_58]
0x14002aa13  mov     rdx, rbx
0x14002aa16  mov     rcx, rdi
0x14002aa19  mov     rax, [rax+118h]
0x14002aa20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa25  mov     rax, [rdi]
0x14002aa28  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FM@@0HF@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002aa2f  mov     rcx, rdi
0x14002aa32  xor     ebx, ebx
0x14002aa34  mov     rax, [rax+0C8h]
0x14002aa3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa40  mov     rax, [rdi]
0x14002aa43  movzx   edx, bp
0x14002aa46  mov     rcx, rdi
0x14002aa49  mov     rax, [rax+188h]
0x14002aa50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa55  inc     rsi
0x14002aa58  cmp     rsi, r15
0x14002aa5b  jb      loc_14002A9CE
0x14002aa61  test    rbx, rbx
0x14002aa64  jz      short loc_14002AA80
0x14002aa66  mov     rax, [rdi]
0x14002aa69  lea     r8, [rsp+78h+var_58]
0x14002aa6e  mov     rdx, rbx
0x14002aa71  mov     rcx, rdi
0x14002aa74  mov     rax, [rax+118h]
0x14002aa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002aa80  mov     rcx, [rsp+78h+var_38]
0x14002aa85  xor     rcx, rsp; StackCookie
0x14002aa88  call    __security_check_cookie
0x14002aa8d  mov     rbx, [rsp+78h+arg_8]
0x14002aa95  add     rsp, 50h
0x14002aa99  pop     r15
0x14002aa9b  pop     r14
0x14002aa9d  pop     rdi
0x14002aa9e  pop     rsi
0x14002aa9f  pop     rbp
0x14002aaa0  retn
```
