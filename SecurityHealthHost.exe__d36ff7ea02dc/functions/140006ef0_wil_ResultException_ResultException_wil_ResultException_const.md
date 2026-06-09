# wil::ResultException::ResultException(wil::ResultException const &)

- ea: `0x140006ef0`
- end: `0x140006ffe`
- name: `??0ResultException@wil@@QEAA@AEBV01@@Z`
- size: `270`
- prototype: `wil::ResultException *__fastcall(wil::ResultException *this, const struct wil::ResultException *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140006ef0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140006f18`
- `api-ms-win-crt-private-l1-1-0!__std_exception_copy` at `0x140006f18`

## pseudocode

```c
wil::ResultException *__fastcall wil::ResultException::ResultException(
        wil::ResultException *this,
        const struct wil::ResultException *a2)
{
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rcx

  *(_QWORD *)this = &std::exception::`vftable';
  *(_OWORD *)((char *)this + 8) = 0;
  __std_exception_copy((char *)a2 + 8);
  *(_QWORD *)this = &wil::ResultException::`vftable';
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)a2 + 24);
  *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)a2 + 40);
  *(_OWORD *)((char *)this + 56) = *(_OWORD *)((char *)a2 + 56);
  *(_OWORD *)((char *)this + 72) = *(_OWORD *)((char *)a2 + 72);
  *(_OWORD *)((char *)this + 88) = *(_OWORD *)((char *)a2 + 88);
  *(_OWORD *)((char *)this + 104) = *(_OWORD *)((char *)a2 + 104);
  *(_OWORD *)((char *)this + 120) = *(_OWORD *)((char *)a2 + 120);
  *(_OWORD *)((char *)this + 136) = *(_OWORD *)((char *)a2 + 136);
  *(_OWORD *)((char *)this + 152) = *(_OWORD *)((char *)a2 + 152);
  *((_QWORD *)this + 21) = *((_QWORD *)a2 + 21);
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  v4 = (volatile signed __int32 *)*((_QWORD *)a2 + 22);
  if ( v4 )
  {
    *((_QWORD *)this + 23) = *((_QWORD *)a2 + 23);
    *((_QWORD *)this + 22) = v4;
    _InterlockedIncrement(v4);
  }
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 0;
  v5 = (volatile signed __int32 *)*((_QWORD *)a2 + 24);
  if ( v5 )
  {
    *((_QWORD *)this + 25) = *((_QWORD *)a2 + 25);
    *((_QWORD *)this + 24) = v5;
    _InterlockedIncrement(v5);
  }
  return this;
}

```

## disassembly

```asm
0x140006ef0  mov     [rsp+arg_0], rbx
0x140006ef5  push    rdi
0x140006ef6  sub     rsp, 20h
0x140006efa  mov     rdi, rdx
0x140006efd  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x140006f04  mov     [rcx], rax
0x140006f07  lea     rdx, [rcx+8]
0x140006f0b  mov     rbx, rcx
0x140006f0e  xorps   xmm0, xmm0
0x140006f11  movups  xmmword ptr [rdx], xmm0
0x140006f14  lea     rcx, [rdi+8]
0x140006f18  call    cs:__imp___std_exception_copy
0x140006f1e  lea     rax, ??_7ResultException@wil@@6B@; const wil::ResultException::`vftable'
0x140006f25  xor     edx, edx
0x140006f27  mov     [rbx], rax
0x140006f2a  movups  xmm0, xmmword ptr [rdi+18h]
0x140006f2e  movups  xmmword ptr [rbx+18h], xmm0
0x140006f32  movups  xmm1, xmmword ptr [rdi+28h]
0x140006f36  movups  xmmword ptr [rbx+28h], xmm1
0x140006f3a  movups  xmm0, xmmword ptr [rdi+38h]
0x140006f3e  movups  xmmword ptr [rbx+38h], xmm0
0x140006f42  movups  xmm1, xmmword ptr [rdi+48h]
0x140006f46  movups  xmmword ptr [rbx+48h], xmm1
0x140006f4a  movups  xmm0, xmmword ptr [rdi+58h]
0x140006f4e  movups  xmmword ptr [rbx+58h], xmm0
0x140006f52  movups  xmm1, xmmword ptr [rdi+68h]
0x140006f56  movups  xmmword ptr [rbx+68h], xmm1
0x140006f5a  movups  xmm0, xmmword ptr [rdi+78h]
0x140006f5e  movups  xmmword ptr [rbx+78h], xmm0
0x140006f62  movups  xmm1, xmmword ptr [rdi+88h]
0x140006f69  movups  xmmword ptr [rbx+88h], xmm1
0x140006f70  movups  xmm0, xmmword ptr [rdi+98h]
0x140006f77  movups  xmmword ptr [rbx+98h], xmm0
0x140006f7e  mov     rax, [rdi+0A8h]
0x140006f85  mov     [rbx+0A8h], rax
0x140006f8c  mov     [rbx+0B0h], rdx
0x140006f93  mov     [rbx+0B8h], rdx
0x140006f9a  mov     rcx, [rdi+0B0h]
0x140006fa1  test    rcx, rcx
0x140006fa4  jz      short loc_140006FBE
0x140006fa6  mov     rax, [rdi+0B8h]
0x140006fad  mov     [rbx+0B8h], rax
0x140006fb4  mov     [rbx+0B0h], rcx
0x140006fbb  lock inc dword ptr [rcx]
0x140006fbe  mov     [rbx+0C0h], rdx
0x140006fc5  mov     [rbx+0C8h], rdx
0x140006fcc  mov     rcx, [rdi+0C0h]
0x140006fd3  test    rcx, rcx
0x140006fd6  jz      short loc_140006FF0
0x140006fd8  mov     rax, [rdi+0C8h]
0x140006fdf  mov     [rbx+0C8h], rax
0x140006fe6  mov     [rbx+0C0h], rcx
0x140006fed  lock inc dword ptr [rcx]
0x140006ff0  mov     rax, rbx
0x140006ff3  mov     rbx, [rsp+28h+arg_0]
0x140006ff8  add     rsp, 20h
0x140006ffc  pop     rdi
0x140006ffd  retn
```
