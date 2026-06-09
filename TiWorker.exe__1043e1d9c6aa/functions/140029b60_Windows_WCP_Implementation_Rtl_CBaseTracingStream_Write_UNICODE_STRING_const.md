# Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(_UNICODE_STRING const *)

- ea: `0x140029b60`
- end: `0x140029bd9`
- name: `?Write@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXPEBU_UNICODE_STRING@@@Z`
- size: `121`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, const struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140002310`
- `0x140029b60`
- `0x14002ab0c`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::Write(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        const struct _UNICODE_STRING *a2)
{
  __int128 v3; // [rsp+20h] [rbp-28h] BYREF
  __int64 v4; // [rsp+30h] [rbp-18h]

  if ( a2 )
  {
    v4 = 0;
    v3 = 0;
    RtlInitLUnicodeStringFromUnicodeString(a2, &v3);
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int128 *))(*(_QWORD *)this + 144LL))(
      this,
      &v3);
  }
  else
  {
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
      this,
      ___LiteralObject__2U__BaseLiteralBuffer__06U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0CI__0GO__0HF__0GM__0GM__0CJ__0A_____0A__00_01_02_03_04_05_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
  }
}

```

## disassembly

```asm
0x140029b60  push    rbx
0x140029b62  sub     rsp, 40h
0x140029b66  mov     rax, cs:__security_cookie
0x140029b6d  xor     rax, rsp
0x140029b70  mov     [rsp+48h+var_10], rax
0x140029b75  mov     rax, rdx
0x140029b78  mov     rbx, rcx
0x140029b7b  test    rdx, rdx
0x140029b7e  jnz     short loc_140029B93
0x140029b80  mov     rax, [rcx]
0x140029b83  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$06U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0CI@@0GO@@0HF@@0GM@@0GM@@0CJ@@0A@@@@$0A@$00$01$02$03$04$05@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x140029b8a  mov     rax, [rax+0C8h]
0x140029b91  jmp     short loc_140029BC1
0x140029b93  xor     ecx, ecx
0x140029b95  lea     rdx, [rsp+48h+var_28]
0x140029b9a  mov     [rsp+48h+var_18], rcx
0x140029b9f  xorps   xmm0, xmm0
0x140029ba2  mov     rcx, rax
0x140029ba5  movups  [rsp+48h+var_28], xmm0
0x140029baa  call    RtlInitLUnicodeStringFromUnicodeString
0x140029baf  mov     rax, [rbx]
0x140029bb2  lea     rdx, [rsp+48h+var_28]
0x140029bb7  mov     rcx, rbx
0x140029bba  mov     rax, [rax+90h]
0x140029bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029bc6  mov     rcx, [rsp+48h+var_10]
0x140029bcb  xor     rcx, rsp; StackCookie
0x140029bce  call    __security_check_cookie
0x140029bd3  add     rsp, 40h
0x140029bd7  pop     rbx
0x140029bd8  retn
```
