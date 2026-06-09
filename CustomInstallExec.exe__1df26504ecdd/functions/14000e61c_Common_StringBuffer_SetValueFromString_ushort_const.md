# Common::StringBuffer::SetValueFromString(ushort const *)

- ea: `0x14000e61c`
- end: `0x14000e6a3`
- name: `?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z`
- size: `135`
- prototype: `__int64 __fastcall(Common::StringBuffer *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140009918`
- `0x140009cd8`
- `0x14000a8a8`

## callees

- `0x14000b854`
- `0x14000e54c`
- `0x14000e61c`
- `0x14000e6ac`

## string_xrefs

- `0x14000e670`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetValueFromString(Common::StringBuffer *this, const unsigned __int16 *a2)
{
  _WORD *v4; // rcx
  int v6; // eax
  Common::StringBuffer *v7; // r11
  unsigned int v8; // edi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v10 = 0;
    v6 = StringCchLengthW(a2, 0x3FFFFFFEu, &v10);
    v8 = v6;
    if ( v6 >= 0 )
    {
      return Common::StringBuffer::SetValue(v7, a2, v10);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v6);
      return v8;
    }
  }
  else
  {
    v4 = (_WORD *)*((_QWORD *)this + 1);
    if ( v4 )
      *v4 = 0;
    *(_DWORD *)this = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x14000e61c  mov     [rsp+arg_0], rbx
0x14000e621  push    rdi; int
0x14000e622  sub     rsp, 20h
0x14000e626  mov     rbx, rdx
0x14000e629  mov     r11, rcx
0x14000e62c  test    rdx, rdx
0x14000e62f  jnz     short loc_14000E64A
0x14000e631  mov     rcx, [rcx+8]
0x14000e635  test    rcx, rcx
0x14000e638  jz      short loc_14000E63F
0x14000e63a  xor     eax, eax
0x14000e63c  mov     [rcx], ax
0x14000e63f  mov     dword ptr [r11], 0
0x14000e646  xor     eax, eax
0x14000e648  jmp     short loc_14000E698
0x14000e64a  lea     r8, [rsp+28h+arg_8]; unsigned __int64 *
0x14000e64f  mov     [rsp+28h+arg_8], 0
0x14000e658  mov     edx, 3FFFFFFEh; unsigned __int64
0x14000e65d  mov     rcx, rbx; unsigned __int16 *
0x14000e660  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14000e665  mov     edi, eax
0x14000e667  test    eax, eax
0x14000e669  jns     short loc_14000E688
0x14000e66b  mov     rcx, [rsp+28h]; this
0x14000e670  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e677  mov     r9d, eax; char *
0x14000e67a  mov     edx, 249h; void *
0x14000e67f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e684  mov     eax, edi
0x14000e686  jmp     short loc_14000E698
0x14000e688  mov     r8d, dword ptr [rsp+28h+arg_8]; unsigned int
0x14000e68d  mov     rdx, rbx; Src
0x14000e690  mov     rcx, r11; this
0x14000e693  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x14000e698  mov     rbx, [rsp+28h+arg_0]
0x14000e69d  add     rsp, 20h
0x14000e6a1  pop     rdi
0x14000e6a2  retn
```
