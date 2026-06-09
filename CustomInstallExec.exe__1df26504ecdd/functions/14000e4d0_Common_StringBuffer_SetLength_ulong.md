# Common::StringBuffer::SetLength(ulong)

- ea: `0x14000e4d0`
- end: `0x14000e544`
- name: `?SetLength@StringBuffer@Common@@QEAAJK@Z`
- size: `116`
- prototype: `__int64 __fastcall(Common::StringBuffer *this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009310`
- `0x14000e54c`
- `0x14000e940`

## callees

- `0x14000b854`
- `0x14000e3ec`
- `0x14000e4d0`

## string_xrefs

- `0x14000e50a`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetLength(Common::StringBuffer *this, unsigned int a2)
{
  __int64 v3; // rbx
  int v4; // eax
  unsigned int v5; // esi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = a2;
  if ( a2 <= ((*((_DWORD *)this + 4) - 1) & (unsigned int)-(*((_DWORD *)this + 4) != 0))
    || (v4 = Common::StringBuffer::SetCapacity((void **)this, a2), v5 = v4, v4 >= 0) )
  {
    *(_DWORD *)this = v3;
    if ( (_DWORD)v3 )
      *(_WORD *)(*((_QWORD *)this + 1) + 2 * v3) = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v4);
    return v5;
  }
}

```

## disassembly

```asm
0x14000e4d0  mov     [rsp+arg_0], rbx
0x14000e4d5  mov     [rsp+arg_8], rsi
0x14000e4da  push    rdi; int
0x14000e4db  sub     rsp, 20h
0x14000e4df  mov     eax, [rcx+10h]
0x14000e4e2  mov     rdi, rcx
0x14000e4e5  mov     ebx, edx
0x14000e4e7  lea     r8d, [rax-1]
0x14000e4eb  neg     eax
0x14000e4ed  sbb     r9d, r9d
0x14000e4f0  and     r9d, r8d
0x14000e4f3  cmp     edx, r9d
0x14000e4f6  jbe     short loc_14000E522
0x14000e4f8  mov     edx, ebx; unsigned int
0x14000e4fa  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x14000e4ff  mov     esi, eax
0x14000e501  test    eax, eax
0x14000e503  jns     short loc_14000E522
0x14000e505  mov     rcx, [rsp+28h]; this
0x14000e50a  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e511  mov     r9d, eax; char *
0x14000e514  mov     edx, 20Ch; void *
0x14000e519  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e51e  mov     eax, esi
0x14000e520  jmp     short loc_14000E534
0x14000e522  mov     [rdi], ebx
0x14000e524  test    ebx, ebx
0x14000e526  jz      short loc_14000E532
0x14000e528  mov     rcx, [rdi+8]
0x14000e52c  xor     eax, eax
0x14000e52e  mov     [rcx+rbx*2], ax
0x14000e532  xor     eax, eax
0x14000e534  mov     rbx, [rsp+28h+arg_0]
0x14000e539  mov     rsi, [rsp+28h+arg_8]
0x14000e53e  add     rsp, 20h
0x14000e542  pop     rdi
0x14000e543  retn
```
