# utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)

- ea: `0x140008d3c`
- end: `0x140008ddd`
- name: `??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z`
- size: `161`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000cc0c`
- `0x14000cfc4`
- `0x14000d5b8`

## callees

- `0x1400023d0`
- `0x1400023f4`
- `0x140008d3c`

## pseudocode

```c
__int64 __fastcall utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(
        __int64 a1,
        __int64 a2)
{
  _OWORD *v2; // rbp
  _OWORD *v3; // rsi
  __int128 v4; // xmm6
  __int64 v5; // rbx
  _OWORD *v6; // r15
  __int64 result; // rax

  v2 = *(_OWORD **)a2;
  v3 = (_OWORD *)(a2 + 16);
  v4 = *(_OWORD *)(a2 + 16);
  v5 = *(_QWORD *)(a2 + 8);
  v6 = (_OWORD *)(a1 + 16);
  *(_QWORD *)a2 = a2 + 16;
  *(_WORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 8) = a2 + 16;
  if ( *(_QWORD *)a1 != a1 + 16 )
    operator delete(*(void **)a1, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 == v3 )
  {
    v2 = v6;
    v5 = a1 + 2 * (((v5 - a2 - 16) >> 1) + 8);
  }
  *(_QWORD *)a1 = v2;
  result = a1;
  *(_QWORD *)(a1 + 8) = v5;
  *v6 = v4;
  return result;
}

```

## disassembly

```asm
0x140008d3c  push    rbx
0x140008d3e  push    rbp
0x140008d3f  push    rsi
0x140008d40  push    rdi
0x140008d41  push    r14
0x140008d43  push    r15
0x140008d45  sub     rsp, 48h
0x140008d49  movaps  [rsp+78h+var_48], xmm6
0x140008d4e  mov     rax, cs:__security_cookie
0x140008d55  xor     rax, rsp
0x140008d58  mov     [rsp+78h+var_58], rax
0x140008d5d  mov     rbp, [rdx]
0x140008d60  lea     rsi, [rdx+10h]
0x140008d64  movups  xmm6, xmmword ptr [rsi]
0x140008d67  mov     rbx, [rdx+8]
0x140008d6b  lea     r15, [rcx+10h]
0x140008d6f  xor     eax, eax
0x140008d71  mov     [rdx], rsi
0x140008d74  mov     [rsi], ax
0x140008d77  mov     r14, rdx
0x140008d7a  mov     [rdx+8], rsi
0x140008d7e  mov     rdi, rcx
0x140008d81  cmp     [rcx], r15
0x140008d84  jz      short loc_140008D95
0x140008d86  mov     rcx, [rcx]; void *
0x140008d89  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140008d90  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140008d95  cmp     rbp, rsi
0x140008d98  jnz     short loc_140008DAF
0x140008d9a  sub     rbx, r14
0x140008d9d  mov     rbp, r15
0x140008da0  sub     rbx, 10h
0x140008da4  sar     rbx, 1
0x140008da7  add     rbx, 8
0x140008dab  lea     rbx, [rdi+rbx*2]
0x140008daf  mov     [rdi], rbp
0x140008db2  mov     rax, rdi
0x140008db5  mov     [rdi+8], rbx
0x140008db9  movdqu  xmmword ptr [r15], xmm6
0x140008dbe  mov     rcx, [rsp+78h+var_58]
0x140008dc3  xor     rcx, rsp; StackCookie
0x140008dc6  call    __security_check_cookie
0x140008dcb  movaps  xmm6, [rsp+78h+var_48]
0x140008dd0  add     rsp, 48h
0x140008dd4  pop     r15
0x140008dd6  pop     r14
0x140008dd8  pop     rdi
0x140008dd9  pop     rsi
0x140008dda  pop     rbp
0x140008ddb  pop     rbx
0x140008ddc  retn
```
