# Common::StringBuilder::Insert(ulong,ulong)

- ea: `0x14000e7f8`
- end: `0x14000e8bb`
- name: `?Insert@StringBuilder@Common@@QEAAJKK@Z`
- size: `195`
- prototype: `__int64 __fastcall(Common::StringBuilder *this, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e8c4`

## callees

- `0x140003f80`
- `0x14000b854`
- `0x14000e7f8`
- `0x14000f010`

## string_xrefs

- `0x14000e82c`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x14000e872`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuilder::Insert(Common::StringBuilder *this, unsigned int a2, int a3)
{
  __int64 v4; // rdi
  unsigned int v6; // ebx
  int v8; // eax
  unsigned int v9; // ebp
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a2;
  v6 = **((_DWORD **)this + 1);
  if ( a2 > v6 )
    return 2147942487LL;
  if ( v6 <= ~a3 )
  {
    if ( v6 + a3 <= 0x3FFFFFFF )
    {
      v8 = (**(__int64 (__fastcall ***)(Common::StringBuilder *))this)(this);
      v9 = v8;
      if ( v8 >= 0 )
      {
        if ( (_DWORD)v4 != v6 )
          memmove_0(
            (void *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 2LL * (unsigned int)(v4 + a3)),
            (const void *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 2 * v4),
            2LL * (v6 - (unsigned int)v4));
        return 0;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x10D,
          (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
          (const char *)(unsigned int)v8);
        return v9;
      }
    }
    else
    {
      return 2147943683LL;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x107,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)0x80070216LL);
    return 2147942934LL;
  }
}

```

## disassembly

```asm
0x14000e7f8  push    rbx
0x14000e7fa  push    rbp
0x14000e7fb  push    rsi
0x14000e7fc  push    rdi
0x14000e7fd  push    r14; int
0x14000e7ff  sub     rsp, 20h
0x14000e803  mov     rax, [rcx+8]
0x14000e807  mov     esi, r8d
0x14000e80a  mov     edi, edx
0x14000e80c  mov     r14, rcx
0x14000e80f  mov     ebx, [rax]
0x14000e811  cmp     edx, ebx
0x14000e813  jbe     short loc_14000E81F
0x14000e815  mov     eax, 80070057h
0x14000e81a  jmp     loc_14000E8B0
0x14000e81f  mov     eax, esi
0x14000e821  not     eax
0x14000e823  cmp     ebx, eax
0x14000e825  jbe     short loc_14000E849
0x14000e827  mov     rcx, [rsp+48h]; this
0x14000e82c  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\string"...
0x14000e833  mov     ebx, 80070216h
0x14000e838  mov     edx, 107h; void *
0x14000e83d  mov     r9d, ebx; char *
0x14000e840  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e845  mov     eax, ebx
0x14000e847  jmp     short loc_14000E8B0
0x14000e849  lea     edx, [rbx+r8]
0x14000e84d  cmp     edx, 3FFFFFFFh
0x14000e853  jbe     short loc_14000E85C
0x14000e855  mov     eax, 80070503h
0x14000e85a  jmp     short loc_14000E8B0
0x14000e85c  mov     rax, [rcx]
0x14000e85f  mov     rax, [rax]
0x14000e862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e867  mov     ebp, eax
0x14000e869  test    eax, eax
0x14000e86b  jns     short loc_14000E88A
0x14000e86d  mov     rcx, [rsp+48h]; this
0x14000e872  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\string"...
0x14000e879  mov     r9d, eax; char *
0x14000e87c  mov     edx, 10Dh; void *
0x14000e881  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e886  mov     eax, ebp
0x14000e888  jmp     short loc_14000E8B0
0x14000e88a  cmp     edi, ebx
0x14000e88c  jz      short loc_14000E8AE
0x14000e88e  mov     rax, [r14+8]
0x14000e892  sub     ebx, edi
0x14000e894  mov     r8d, ebx
0x14000e897  add     r8, r8; Size
0x14000e89a  mov     r9, [rax+8]
0x14000e89e  lea     eax, [rdi+rsi]
0x14000e8a1  lea     rdx, [r9+rdi*2]; Src
0x14000e8a5  lea     rcx, [r9+rax*2]; void *
0x14000e8a9  call    memmove_0
0x14000e8ae  xor     eax, eax
0x14000e8b0  add     rsp, 20h
0x14000e8b4  pop     r14
0x14000e8b6  pop     rdi
0x14000e8b7  pop     rsi
0x14000e8b8  pop     rbp
0x14000e8b9  pop     rbx
0x14000e8ba  retn
```
