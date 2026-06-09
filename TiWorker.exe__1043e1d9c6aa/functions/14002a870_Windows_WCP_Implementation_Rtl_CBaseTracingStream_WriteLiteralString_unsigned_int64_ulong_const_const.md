# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(unsigned __int64,ulong const * const)

- ea: `0x14002a870`
- end: `0x14002a97d`
- name: `?WriteLiteralString@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_KQEBK@Z`
- size: `269`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int64, const unsigned int *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002310`
- `0x14002a870`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteLiteralString(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int64 a2,
        const unsigned int *const a3)
{
  unsigned __int64 v6; // rbx
  unsigned __int64 i; // rsi
  unsigned int v8; // ebp
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
      if ( v8 >= 0x80 )
      {
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, _BYTE *))(*(_QWORD *)this + 280LL))(
          this,
          v6,
          v9);
        v6 = 0;
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, __int64 *))(*(_QWORD *)this + 200LL))(
          this,
          ___LiteralObject__2U__BaseLiteralBuffer__02U_LUTF8_STRING__D_Details_RtlStringLiterals__3E0FM__0HF__0A_____0A__00_01_Details_RtlStringLiterals__3U_LUTF8_STRING__B);
        (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, _QWORD))(*(_QWORD *)this + 400LL))(
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
0x14002a870  test    rdx, rdx
0x14002a873  jz      locret_14002A97C
0x14002a879  mov     [rsp+arg_8], rbx
0x14002a87e  push    rbp
0x14002a87f  push    rsi
0x14002a880  push    rdi
0x14002a881  push    r14
0x14002a883  push    r15
0x14002a885  sub     rsp, 50h
0x14002a889  mov     rax, cs:__security_cookie
0x14002a890  xor     rax, rsp
0x14002a893  mov     [rsp+78h+var_38], rax
0x14002a898  mov     r14, r8
0x14002a89b  mov     r15, rdx
0x14002a89e  mov     rdi, rcx
0x14002a8a1  test    r8, r8
0x14002a8a4  jz      loc_14002A95C
0x14002a8aa  xor     ebx, ebx
0x14002a8ac  xor     esi, esi
0x14002a8ae  mov     ebp, [r14+rsi*4]
0x14002a8b2  cmp     rbx, 20h ; ' '
0x14002a8b6  jb      short loc_14002A8D6
0x14002a8b8  mov     rax, [rdi]
0x14002a8bb  lea     r8, [rsp+78h+var_58]
0x14002a8c0  mov     edx, 20h ; ' '
0x14002a8c5  mov     rcx, rdi
0x14002a8c8  mov     rax, [rax+118h]
0x14002a8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a8d4  xor     ebx, ebx
0x14002a8d6  cmp     ebp, 80h
0x14002a8dc  jnb     short loc_14002A8E8
0x14002a8de  mov     [rsp+rbx+78h+var_58], bpl
0x14002a8e3  inc     rbx
0x14002a8e6  jmp     short loc_14002A931
0x14002a8e8  mov     rax, [rdi]
0x14002a8eb  lea     r8, [rsp+78h+var_58]
0x14002a8f0  mov     rdx, rbx
0x14002a8f3  mov     rcx, rdi
0x14002a8f6  mov     rax, [rax+118h]
0x14002a8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a902  mov     rax, [rdi]
0x14002a905  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$02U_LUTF8_STRING@@D@Details@RtlStringLiterals@@3E0FM@@0HF@@0A@@@@$0A@$00$01@Details@RtlStringLiterals@@3U_LUTF8_STRING@@B
0x14002a90c  mov     rcx, rdi
0x14002a90f  xor     ebx, ebx
0x14002a911  mov     rax, [rax+0C8h]
0x14002a918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a91d  mov     rax, [rdi]
0x14002a920  mov     edx, ebp
0x14002a922  mov     rcx, rdi
0x14002a925  mov     rax, [rax+190h]
0x14002a92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a931  inc     rsi
0x14002a934  cmp     rsi, r15
0x14002a937  jb      loc_14002A8AE
0x14002a93d  test    rbx, rbx
0x14002a940  jz      short loc_14002A95C
0x14002a942  mov     rax, [rdi]
0x14002a945  lea     r8, [rsp+78h+var_58]
0x14002a94a  mov     rdx, rbx
0x14002a94d  mov     rcx, rdi
0x14002a950  mov     rax, [rax+118h]
0x14002a957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a95c  mov     rcx, [rsp+78h+var_38]
0x14002a961  xor     rcx, rsp; StackCookie
0x14002a964  call    __security_check_cookie
0x14002a969  mov     rbx, [rsp+78h+arg_8]
0x14002a971  add     rsp, 50h
0x14002a975  pop     r15
0x14002a977  pop     r14
0x14002a979  pop     rdi
0x14002a97a  pop     rsi
0x14002a97b  pop     rbp
0x14002a97c  retn
```
