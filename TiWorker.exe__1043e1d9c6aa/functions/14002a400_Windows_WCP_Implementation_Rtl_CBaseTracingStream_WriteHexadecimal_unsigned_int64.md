# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(unsigned __int64)

- ea: `0x14002a400`
- end: `0x14002a469`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAX_K@Z`
- size: `105`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140002310`
- `0x140002e10`
- `0x14002a400`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        __int64 a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[24]; // [rsp+30h] [rbp-28h] BYREF

  v3 = snprintf_s(Buffer, 0x11u, 0xFFFFFFFFFFFFFFFFuLL, "%016I64x", a2);
  if ( v3 <= 0x11 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x14002a400  push    rbx
0x14002a402  sub     rsp, 50h
0x14002a406  mov     rax, cs:__security_cookie
0x14002a40d  xor     rax, rsp
0x14002a410  mov     [rsp+58h+var_10], rax
0x14002a415  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002a419  mov     [rsp+58h+var_38], rdx
0x14002a41e  mov     rbx, rcx
0x14002a421  lea     r9, a016i64x; "%016I64x"
0x14002a428  lea     rcx, [rsp+58h+Buffer]; Buffer
0x14002a42d  lea     edx, [r8+12h]; BufferCount
0x14002a431  call    _snprintf_s
0x14002a436  movsxd  rdx, eax
0x14002a439  cmp     rdx, 11h
0x14002a43d  ja      short loc_14002A456
0x14002a43f  mov     rax, [rbx]
0x14002a442  lea     r8, [rsp+58h+Buffer]
0x14002a447  mov     rcx, rbx
0x14002a44a  mov     rax, [rax+118h]
0x14002a451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a456  mov     rcx, [rsp+58h+var_10]
0x14002a45b  xor     rcx, rsp; StackCookie
0x14002a45e  call    __security_check_cookie
0x14002a463  add     rsp, 50h
0x14002a467  pop     rbx
0x14002a468  retn
```
