# Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(uint)

- ea: `0x14002a320`
- end: `0x14002a388`
- name: `?WriteHexadecimal@CBaseTracingStream@Rtl@Implementation@WCP@Windows@@UEAAXI@Z`
- size: `104`
- prototype: `void __fastcall(Windows::WCP::Implementation::Rtl::CBaseTracingStream *this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140002310`
- `0x140002e10`
- `0x14002a320`
- `0x14002b010`

## pseudocode

```c
void __fastcall Windows::WCP::Implementation::Rtl::CBaseTracingStream::WriteHexadecimal(
        Windows::WCP::Implementation::Rtl::CBaseTracingStream *this,
        int a2)
{
  unsigned __int64 v3; // rdx
  char Buffer[16]; // [rsp+30h] [rbp-28h] BYREF

  v3 = snprintf_s(Buffer, 9u, 0xFFFFFFFFFFFFFFFFuLL, "%08x", a2);
  if ( v3 <= 9 )
    (*(void (__fastcall **)(Windows::WCP::Implementation::Rtl::CBaseTracingStream *, unsigned __int64, char *))(*(_QWORD *)this + 280LL))(
      this,
      v3,
      Buffer);
}

```

## disassembly

```asm
0x14002a320  push    rbx
0x14002a322  sub     rsp, 50h
0x14002a326  mov     rax, cs:__security_cookie
0x14002a32d  xor     rax, rsp
0x14002a330  mov     [rsp+58h+var_18], rax
0x14002a335  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002a339  mov     [rsp+58h+var_38], edx
0x14002a33d  mov     rbx, rcx
0x14002a340  lea     r9, a08x; "%08x"
0x14002a347  lea     rcx, [rsp+58h+Buffer]; Buffer
0x14002a34c  lea     edx, [r8+0Ah]; BufferCount
0x14002a350  call    _snprintf_s
0x14002a355  movsxd  rdx, eax
0x14002a358  cmp     rdx, 9
0x14002a35c  ja      short loc_14002A375
0x14002a35e  mov     rax, [rbx]
0x14002a361  lea     r8, [rsp+58h+Buffer]
0x14002a366  mov     rcx, rbx
0x14002a369  mov     rax, [rax+118h]
0x14002a370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a375  mov     rcx, [rsp+58h+var_18]
0x14002a37a  xor     rcx, rsp; StackCookie
0x14002a37d  call    __security_check_cookie
0x14002a382  add     rsp, 50h
0x14002a386  pop     rbx
0x14002a387  retn
```
