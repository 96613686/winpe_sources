# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(ulong)

- ea: `0x14002a390`
- end: `0x14002a3f8`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXK@Z`
- size: `104`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140002310`
- `0x140002e10`
- `0x14002a390`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = snprintf_s(Buffer, 9u, 0xFFFFFFFFFFFFFFFFuLL, "%08lx", a2);
  if ( v3 <= 9 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x14002a390  push    rbx
0x14002a392  sub     rsp, 50h
0x14002a396  mov     rax, cs:__security_cookie
0x14002a39d  xor     rax, rsp
0x14002a3a0  mov     [rsp+58h+var_18], rax
0x14002a3a5  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002a3a9  mov     [rsp+58h+var_38], edx
0x14002a3ad  mov     rbx, rcx
0x14002a3b0  lea     r9, a08lx; "%08lx"
0x14002a3b7  lea     rcx, [rsp+58h+Buffer]; Buffer
0x14002a3bc  lea     edx, [r8+0Ah]; BufferCount
0x14002a3c0  call    _snprintf_s
0x14002a3c5  movsxd  rdx, eax
0x14002a3c8  cmp     rdx, 9
0x14002a3cc  ja      short loc_14002A3E5
0x14002a3ce  mov     rax, [rbx]
0x14002a3d1  lea     r8, [rsp+58h+Buffer]
0x14002a3d6  mov     rcx, rbx
0x14002a3d9  mov     rax, [rax+118h]
0x14002a3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a3e5  mov     rcx, [rsp+58h+var_18]
0x14002a3ea  xor     rcx, rsp; StackCookie
0x14002a3ed  call    __security_check_cookie
0x14002a3f2  add     rsp, 50h
0x14002a3f6  pop     rbx
0x14002a3f7  retn
```
