# Common::StringBuilder::InsertChars(ulong,ushort const *,ulong)

- ea: `0x14000e8c4`
- end: `0x14000e92c`
- name: `?InsertChars@StringBuilder@Common@@QEAAJKPEBGK@Z`
- size: `104`
- prototype: `__int64 __fastcall(Common::StringBuilder *this, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e780`

## callees

- `0x140003f74`
- `0x14000b854`
- `0x14000e7f8`
- `0x14000e8c4`

## string_xrefs

- `0x14000e8ed`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuilder::InsertChars(
        Common::StringBuilder *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v5; // rdi
  __int64 v6; // rsi
  int v8; // eax
  unsigned int v9; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = a4;
  v6 = a2;
  v8 = Common::StringBuilder::Insert(this, a2, a4);
  v9 = v8;
  if ( v8 >= 0 )
  {
    memcpy_0((void *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 2 * v6), a3, 2 * v5);
    return 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x79,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v8);
    return v9;
  }
}

```

## disassembly

```asm
0x14000e8c4  push    rbx
0x14000e8c6  push    rbp
0x14000e8c7  push    rsi
0x14000e8c8  push    rdi
0x14000e8c9  push    r14; int
0x14000e8cb  sub     rsp, 20h
0x14000e8cf  mov     r14, r8
0x14000e8d2  mov     edi, r9d
0x14000e8d5  mov     r8d, r9d; unsigned int
0x14000e8d8  mov     esi, edx
0x14000e8da  mov     rbp, rcx
0x14000e8dd  call    ?Insert@StringBuilder@Common@@QEAAJKK@Z; Common::StringBuilder::Insert(ulong,ulong)
0x14000e8e2  mov     ebx, eax
0x14000e8e4  test    eax, eax
0x14000e8e6  jns     short loc_14000E905
0x14000e8e8  mov     rcx, [rsp+48h]; this
0x14000e8ed  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\string"...
0x14000e8f4  mov     r9d, eax; char *
0x14000e8f7  mov     edx, 79h ; 'y'; void *
0x14000e8fc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e901  mov     eax, ebx
0x14000e903  jmp     short loc_14000E921
0x14000e905  mov     rax, [rbp+8]
0x14000e909  mov     r8, rdi
0x14000e90c  add     r8, r8; Size
0x14000e90f  mov     rdx, r14; Src
0x14000e912  mov     rcx, [rax+8]
0x14000e916  lea     rcx, [rcx+rsi*2]; void *
0x14000e91a  call    memcpy_0
0x14000e91f  xor     eax, eax
0x14000e921  add     rsp, 20h
0x14000e925  pop     r14
0x14000e927  pop     rdi
0x14000e928  pop     rsi
0x14000e929  pop     rbp
0x14000e92a  pop     rbx
0x14000e92b  retn
```
