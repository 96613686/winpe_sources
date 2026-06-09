# Common::StringBuffer::SetCapacity(ulong)

- ea: `0x14000e3ec`
- end: `0x14000e4c8`
- name: `?SetCapacity@StringBuffer@Common@@QEAAJK@Z`
- size: `220`
- prototype: `__int64 __fastcall(void **this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000e4d0`
- `0x14000e54c`
- `0x14000e940`

## callees

- `0x140003644`
- `0x140006c24`
- `0x14000e2c8`
- `0x14000e3ec`

## string_xrefs

- `0x14000e407`: `onecore\base\appmodel\common\widestring.cpp`
- `0x14000e47f`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetCapacity(void **this, unsigned int a2)
{
  __int64 v2; // rdi
  void *v5; // rcx
  int v6; // eax
  unsigned int v7; // ebp
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = a2;
  if ( a2 > 0x3FFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070503LL);
    return 2147943683LL;
  }
  if ( a2 )
  {
    if ( a2 + 1 != *((_DWORD *)this + 4) )
    {
      v6 = Common::EnsureBufferCapacity(this[1]);
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C4,
          (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v6);
        return v7;
      }
      this[1] = 0;
      *((_DWORD *)this + 4) = v2 + 1;
      if ( *(_DWORD *)this <= (unsigned int)v2 )
      {
        if ( *(_DWORD *)this < (unsigned int)v2 && !*(_DWORD *)this )
          MEMORY[0] = 0;
      }
      else
      {
        *(_DWORD *)this = v2;
        *(_WORD *)(2 * v2) = 0;
      }
    }
  }
  else
  {
    v5 = this[1];
    if ( v5 )
    {
      operator delete(v5);
      this[1] = 0;
      *(_DWORD *)this = 0;
    }
    *((_DWORD *)this + 4) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e3ec  push    rbx
0x14000e3ee  push    rbp
0x14000e3ef  push    rsi
0x14000e3f0  push    rdi
0x14000e3f1  sub     rsp, 28h
0x14000e3f5  mov     edi, edx
0x14000e3f7  mov     rbx, rcx
0x14000e3fa  cmp     edx, 3FFFFFFFh
0x14000e400  jbe     short loc_14000E427
0x14000e402  mov     rcx, [rsp+48h]; this
0x14000e407  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e40e  mov     ebx, 80070503h
0x14000e413  mov     edx, 1A9h; void *
0x14000e418  mov     r9d, ebx; char *
0x14000e41b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e420  mov     eax, ebx
0x14000e422  jmp     loc_14000E4BF
0x14000e427  test    edx, edx
0x14000e429  jnz     short loc_14000E450
0x14000e42b  mov     rcx, [rcx+8]; void *
0x14000e42f  test    rcx, rcx
0x14000e432  jz      short loc_14000E447
0x14000e434  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e439  mov     qword ptr [rbx+8], 0
0x14000e441  mov     dword ptr [rbx], 0
0x14000e447  mov     dword ptr [rbx+10h], 0
0x14000e44e  jmp     short loc_14000E4BD
0x14000e450  mov     edx, [rcx+10h]
0x14000e453  lea     esi, [rdi+1]
0x14000e456  cmp     esi, edx
0x14000e458  jz      short loc_14000E4BD
0x14000e45a  mov     rcx, [rcx+8]; void *
0x14000e45e  lea     r9, [rsp+48h+arg_10]
0x14000e463  mov     r8d, esi
0x14000e466  mov     [rsp+48h+arg_10], 0
0x14000e46f  call    Common__EnsureBufferCapacity
0x14000e474  mov     ebp, eax
0x14000e476  test    eax, eax
0x14000e478  jns     short loc_14000E497
0x14000e47a  mov     rcx, [rsp+48h]; this
0x14000e47f  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e486  mov     r9d, eax; char *
0x14000e489  mov     edx, 1C4h; void *
0x14000e48e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e493  mov     eax, ebp
0x14000e495  jmp     short loc_14000E4BF
0x14000e497  mov     rdx, [rsp+48h+arg_10]
0x14000e49c  mov     [rbx+8], rdx
0x14000e4a0  mov     [rbx+10h], esi
0x14000e4a3  cmp     [rbx], edi
0x14000e4a5  jbe     short loc_14000E4B1
0x14000e4a7  xor     eax, eax
0x14000e4a9  mov     [rbx], edi
0x14000e4ab  mov     [rdx+rdi*2], ax
0x14000e4af  jmp     short loc_14000E4BD
0x14000e4b1  jnb     short loc_14000E4BD
0x14000e4b3  cmp     dword ptr [rbx], 0
0x14000e4b6  jnz     short loc_14000E4BD
0x14000e4b8  xor     eax, eax
0x14000e4ba  mov     [rdx], ax
0x14000e4bd  xor     eax, eax
0x14000e4bf  add     rsp, 28h
0x14000e4c3  pop     rdi
0x14000e4c4  pop     rsi
0x14000e4c5  pop     rbp
0x14000e4c6  pop     rbx
0x14000e4c7  retn
```
