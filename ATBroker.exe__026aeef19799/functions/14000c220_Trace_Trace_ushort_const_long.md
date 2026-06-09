# _Trace::_Trace(ushort const *,long *)

- ea: `0x14000c220`
- end: `0x14000c26a`
- name: `??0_Trace@@QEAA@PEBGPEAJ@Z`
- size: `74`
- prototype: `_Trace *__fastcall(_Trace *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d498`
- `0x14000ea38`
- `0x14000f9c0`
- `0x14000fd08`
- `0x140010e44`

## callees

- `0x14000abd8`
- `0x14000c220`

## pseudocode

```c
_Trace *__fastcall _Trace::_Trace(_Trace *this, const unsigned __int16 *a2, int *a3)
{
  *(_QWORD *)this = a3;
  *((_QWORD *)this + 1) = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4fe2a7da30c630366b37eac893510770_Traceguids, a2);
  return this;
}

```

## disassembly

```asm
0x14000c220  push    rbx
0x14000c222  sub     rsp, 20h
0x14000c226  mov     r9, rdx
0x14000c229  mov     [rcx], r8
0x14000c22c  mov     rbx, rcx
0x14000c22f  mov     [rcx+8], rdx
0x14000c233  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c23a  lea     rax, WPP_GLOBAL_Control
0x14000c241  cmp     rcx, rax
0x14000c244  jz      short loc_14000C261
0x14000c246  test    byte ptr [rcx+1Ch], 40h
0x14000c24a  jz      short loc_14000C261
0x14000c24c  mov     rcx, [rcx+10h]
0x14000c250  lea     r8, WPP_4fe2a7da30c630366b37eac893510770_Traceguids
0x14000c257  mov     edx, 0Ah
0x14000c25c  call    WPP_SF_S
0x14000c261  mov     rax, rbx
0x14000c264  add     rsp, 20h
0x14000c268  pop     rbx
0x14000c269  retn
```
