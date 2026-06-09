# LogAdapter::Impl::TracingSink::WriteUtf8NullTerminated(unsigned __int64,uchar const * const,bool)

- ea: `0x1400075d0`
- end: `0x140007663`
- name: `?WriteUtf8NullTerminated@TracingSink@Impl@LogAdapter@@UEAAX_KQEBE_N@Z`
- size: `147`
- prototype: `void __fastcall(LogAdapter::Impl::TracingSink *this, unsigned __int64, const unsigned __int8 *const)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140002c2e`
- `0x140002cf8`
- `0x1400075d0`
- `0x14002acf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007603`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000763c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007603`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000763c`

## pseudocode

```c
void __fastcall LogAdapter::Impl::TracingSink::WriteUtf8NullTerminated(
        LogAdapter::Impl::TracingSink *this,
        unsigned __int64 a2,
        const unsigned __int8 *const a3)
{
  __int64 v3; // rax
  size_t v4; // rsi
  size_t v6; // rdi
  char *v8; // rcx

  v3 = *((_QWORD *)this + 1);
  v4 = 4095 - v3;
  v6 = 4095 - v3;
  if ( a2 < 4095 - v3 )
    v6 = a2;
  if ( v6 )
  {
    v8 = (char *)this + v3 + 16;
    if ( !v8 )
    {
LABEL_5:
      *(_DWORD *)_o__errno() = 22;
LABEL_12:
      invalid_parameter_noinfo();
      goto LABEL_13;
    }
    if ( a3 && v4 >= v6 )
    {
      memcpy_0(v8, a3, v6);
    }
    else
    {
      memset_0(v8, 0, 4095 - v3);
      if ( !a3 )
        goto LABEL_5;
      if ( v4 < v6 )
      {
        *(_DWORD *)_o__errno() = 34;
        goto LABEL_12;
      }
    }
  }
LABEL_13:
  *((_QWORD *)this + 1) += v6;
  *((_BYTE *)this + *((_QWORD *)this + 1) + 16) = 0;
}

```

## disassembly

```asm
0x1400075d0  push    rbx
0x1400075d2  push    rbp
0x1400075d3  push    rsi
0x1400075d4  push    rdi
0x1400075d5  sub     rsp, 28h
0x1400075d9  mov     rax, [rcx+8]
0x1400075dd  mov     esi, 0FFFh
0x1400075e2  sub     rsi, rax
0x1400075e5  mov     rbp, r8
0x1400075e8  cmp     rdx, rsi
0x1400075eb  mov     rdi, rsi
0x1400075ee  mov     rbx, rcx
0x1400075f1  cmovb   rdi, rdx
0x1400075f5  test    rdi, rdi
0x1400075f8  jz      short loc_14000764D
0x1400075fa  add     rcx, 10h
0x1400075fe  add     rcx, rax; void *
0x140007601  jnz     short loc_140007611
0x140007603  call    cs:__imp__o__errno
0x140007609  mov     dword ptr [rax], 16h
0x14000760f  jmp     short loc_140007648
0x140007611  test    rbp, rbp
0x140007614  jz      short loc_140007628
0x140007616  cmp     rsi, rdi
0x140007619  jb      short loc_140007628
0x14000761b  mov     r8, rdi; Size
0x14000761e  mov     rdx, rbp; Src
0x140007621  call    memcpy_0
0x140007626  jmp     short loc_14000764D
0x140007628  mov     r8, rsi; Size
0x14000762b  xor     edx, edx; Val
0x14000762d  call    memset_0
0x140007632  test    rbp, rbp
0x140007635  jz      short loc_140007603
0x140007637  cmp     rsi, rdi
0x14000763a  jnb     short loc_14000764D
0x14000763c  call    cs:__imp__o__errno
0x140007642  mov     dword ptr [rax], 22h ; '"'
0x140007648  call    _invalid_parameter_noinfo
0x14000764d  add     [rbx+8], rdi
0x140007651  mov     rax, [rbx+8]
0x140007655  mov     byte ptr [rax+rbx+10h], 0
0x14000765a  add     rsp, 28h
0x14000765e  pop     rdi
0x14000765f  pop     rsi
0x140007660  pop     rbp
0x140007661  pop     rbx
0x140007662  retn
```
