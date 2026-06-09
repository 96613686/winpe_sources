# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(uchar)

- ea: `0x14002a220`
- end: `0x14002a28b`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXE@Z`
- size: `107`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140002310`
- `0x140002e10`
- `0x14002a220`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        unsigned __int8 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[8]; // [rsp+30h] [rbp-18h] BYREF

  v3 = snprintf_s(Buffer, 3u, 0xFFFFFFFFFFFFFFFFuLL, "%02x", a2);
  if ( v3 <= 3 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x14002a220  push    rbx
0x14002a222  sub     rsp, 40h
0x14002a226  mov     rax, cs:__security_cookie
0x14002a22d  xor     rax, rsp
0x14002a230  mov     [rsp+48h+var_10], rax
0x14002a235  movzx   eax, dl
0x14002a238  lea     r9, a02x; "%02x"
0x14002a23f  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002a243  mov     [rsp+48h+var_28], eax
0x14002a247  mov     rbx, rcx
0x14002a24a  lea     rcx, [rsp+48h+Buffer]; Buffer
0x14002a24f  lea     edx, [r8+4]; BufferCount
0x14002a253  call    _snprintf_s
0x14002a258  movsxd  rdx, eax
0x14002a25b  cmp     rdx, 3
0x14002a25f  ja      short loc_14002A278
0x14002a261  mov     rax, [rbx]
0x14002a264  lea     r8, [rsp+48h+Buffer]
0x14002a269  mov     rcx, rbx
0x14002a26c  mov     rax, [rax+118h]
0x14002a273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a278  mov     rcx, [rsp+48h+var_10]
0x14002a27d  xor     rcx, rsp; StackCookie
0x14002a280  call    __security_check_cookie
0x14002a285  add     rsp, 40h
0x14002a289  pop     rbx
0x14002a28a  retn
```
