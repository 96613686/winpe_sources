# Common::StringBufferBuilder::SetLength(ulong)

- ea: `0x14000e940`
- end: `0x14000e9f0`
- name: `?SetLength@StringBufferBuilder@Common@@UEAAJK@Z`
- size: `176`
- prototype: `__int64 __fastcall(Common::StringBufferBuilder *this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000b854`
- `0x14000e3ec`
- `0x14000e4d0`
- `0x14000e940`

## string_xrefs

- `0x14000e998`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x14000e9c6`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBufferBuilder::SetLength(Common::StringBufferBuilder *this, unsigned int a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // r9d
  unsigned int v6; // r9d
  int v7; // eax
  unsigned int v8; // edi
  int v10; // eax
  unsigned int v11; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = a2;
  v4 = *((_QWORD *)this + 2);
  v5 = *(_DWORD *)(v4 + 16) != 0 ? *(_DWORD *)(v4 + 16) - 1 : 0;
  if ( a2 <= v5 )
    goto LABEL_8;
  if ( v5 <= 0x7FFFFFFF )
  {
    v6 = 2 * v5;
    if ( v6 >= a2 && v6 <= 0x3FFFFFFF )
      a2 = v6;
  }
  v7 = Common::StringBuffer::SetCapacity((void **)v4, a2);
  v8 = v7;
  if ( v7 >= 0 )
  {
LABEL_8:
    v10 = Common::StringBuffer::SetLength(*((Common::StringBuffer **)this + 2), v3);
    v11 = v10;
    if ( v10 >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x13C,
        (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)(unsigned int)v10);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13A,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v7);
    return v8;
  }
}

```

## disassembly

```asm
0x14000e940  mov     [rsp+arg_0], rbx
0x14000e945  mov     [rsp+arg_8], rsi
0x14000e94a  push    rdi; int
0x14000e94b  sub     rsp, 20h
0x14000e94f  mov     rsi, rcx
0x14000e952  mov     ebx, edx
0x14000e954  mov     rcx, [rcx+10h]; this
0x14000e958  mov     eax, [rcx+10h]
0x14000e95b  lea     r8d, [rax-1]
0x14000e95f  neg     eax
0x14000e961  sbb     r9d, r9d
0x14000e964  and     r9d, r8d
0x14000e967  cmp     edx, r9d
0x14000e96a  jbe     short loc_14000E9B0
0x14000e96c  cmp     r9d, 7FFFFFFFh
0x14000e973  ja      short loc_14000E988
0x14000e975  add     r9d, r9d
0x14000e978  cmp     r9d, edx
0x14000e97b  jb      short loc_14000E988
0x14000e97d  cmp     r9d, 3FFFFFFFh
0x14000e984  cmovbe  edx, r9d; unsigned int
0x14000e988  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x14000e98d  mov     edi, eax
0x14000e98f  test    eax, eax
0x14000e991  jns     short loc_14000E9B0
0x14000e993  mov     rcx, [rsp+28h]; this
0x14000e998  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\string"...
0x14000e99f  mov     r9d, eax; char *
0x14000e9a2  mov     edx, 13Ah; void *
0x14000e9a7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e9ac  mov     eax, edi
0x14000e9ae  jmp     short loc_14000E9E0
0x14000e9b0  mov     rcx, [rsi+10h]; this
0x14000e9b4  mov     edx, ebx; unsigned int
0x14000e9b6  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x14000e9bb  mov     ebx, eax
0x14000e9bd  test    eax, eax
0x14000e9bf  jns     short loc_14000E9DE
0x14000e9c1  mov     rcx, [rsp+28h]; this
0x14000e9c6  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\string"...
0x14000e9cd  mov     r9d, eax; char *
0x14000e9d0  mov     edx, 13Ch; void *
0x14000e9d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e9da  mov     eax, ebx
0x14000e9dc  jmp     short loc_14000E9E0
0x14000e9de  xor     eax, eax
0x14000e9e0  mov     rbx, [rsp+28h+arg_0]
0x14000e9e5  mov     rsi, [rsp+28h+arg_8]
0x14000e9ea  add     rsp, 20h
0x14000e9ee  pop     rdi
0x14000e9ef  retn
```
