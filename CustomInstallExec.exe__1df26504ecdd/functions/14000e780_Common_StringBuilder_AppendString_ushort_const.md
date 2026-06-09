# Common::StringBuilder::AppendString(ushort const *)

- ea: `0x14000e780`
- end: `0x14000e7ef`
- name: `?AppendString@StringBuilder@Common@@QEAAJPEBG@Z`
- size: `111`
- prototype: `int __fastcall(Common::StringBuilder *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140008ec8`
- `0x140009310`

## callees

- `0x14000b854`
- `0x14000e6ac`
- `0x14000e780`
- `0x14000e8c4`

## string_xrefs

- `0x14000e7b6`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
int __fastcall Common::StringBuilder::AppendString(Common::StringBuilder *this, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int **v4; // r11
  int v5; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  v8 = 0;
  v3 = StringCchLengthW(a2, 0x3FFFFFFFu, &v8);
  v5 = v3;
  if ( v3 >= 0 )
    return Common::StringBuilder::InsertChars((Common::StringBuilder *)v4, *v4[1], a2, v8);
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x35,
    (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
    (const char *)(unsigned int)v3);
  return v5;
}

```

## disassembly

```asm
0x14000e780  mov     [rsp+arg_0], rbx
0x14000e785  push    rdi; int
0x14000e786  sub     rsp, 20h
0x14000e78a  mov     rdi, rdx
0x14000e78d  mov     [rsp+28h+arg_10], 0
0x14000e796  mov     r11, rcx
0x14000e799  lea     r8, [rsp+28h+arg_10]; unsigned __int64 *
0x14000e79e  mov     rcx, rdi; unsigned __int16 *
0x14000e7a1  mov     edx, 3FFFFFFFh; unsigned __int64
0x14000e7a6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14000e7ab  mov     ebx, eax
0x14000e7ad  test    eax, eax
0x14000e7af  jns     short loc_14000E7CE
0x14000e7b1  mov     rcx, [rsp+28h]; this
0x14000e7b6  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\string"...
0x14000e7bd  mov     r9d, eax; char *
0x14000e7c0  mov     edx, 35h ; '5'; void *
0x14000e7c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e7ca  mov     eax, ebx
0x14000e7cc  jmp     short loc_14000E7E4
0x14000e7ce  mov     rdx, [r11+8]
0x14000e7d2  mov     r8, rdi; unsigned __int16 *
0x14000e7d5  mov     r9d, dword ptr [rsp+28h+arg_10]; unsigned int
0x14000e7da  mov     rcx, r11; this
0x14000e7dd  mov     edx, [rdx]; unsigned int
0x14000e7df  call    ?InsertChars@StringBuilder@Common@@QEAAJKPEBGK@Z; Common::StringBuilder::InsertChars(ulong,ushort const *,ulong)
0x14000e7e4  mov     rbx, [rsp+28h+arg_0]
0x14000e7e9  add     rsp, 20h
0x14000e7ed  pop     rdi
0x14000e7ee  retn
```
