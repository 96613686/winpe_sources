# WriteFileView::TryAllocIfNecessary(void)

- ea: `0x1800357e0`
- end: `0x18003587d`
- name: `?TryAllocIfNecessary@WriteFileView@@QEAAKXZ`
- size: `157`
- prototype: `unsigned int __fastcall(WriteFileView *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180032794`
- `0x180032bb8`
- `0x180033258`
- `0x180035320`

## callees

- `0x180023548`
- `0x18003529c`
- `0x1800357e0`

## pseudocode

```c
__int64 __fastcall WriteFileView::TryAllocIfNecessary(WriteFileView *this)
{
  unsigned int v2; // edi
  __int64 v4; // rcx

  if ( *((_QWORD *)this + 7) )
    return 0;
  v2 = FileView::TryAllocMemory((WriteFileView *)((char *)this + 8));
  if ( !v2 )
  {
    v4 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 7) = v4;
    *((_QWORD *)this + 42) = this;
    *((_QWORD *)this + 9) = v4 + 128;
    *((_QWORD *)this + 44) = v4 + 384;
    *((_QWORD *)this + 61) = this;
    return 0;
  }
  if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_e8d0195a3cc637ab3689c79b5b31cbb7_Traceguids, v2);
  }
  return v2;
}

```

## disassembly

```asm
0x1800357e0  mov     [rsp+arg_0], rbx
0x1800357e5  push    rdi
0x1800357e6  sub     rsp, 20h
0x1800357ea  cmp     qword ptr [rcx+38h], 0
0x1800357ef  mov     rbx, rcx
0x1800357f2  jnz     short loc_180035870
0x1800357f4  add     rcx, 8; this
0x1800357f8  call    ?TryAllocMemory@FileView@@QEAAKXZ; FileView::TryAllocMemory(void)
0x1800357fd  mov     edi, eax
0x1800357ff  test    eax, eax
0x180035801  jz      short loc_180035841
0x180035803  mov     rcx, cs:WPP_GLOBAL_Control
0x18003580a  lea     rax, WPP_GLOBAL_Control
0x180035811  cmp     rcx, rax
0x180035814  jz      short loc_18003583D
0x180035816  test    dword ptr [rcx+1Ch], 200h
0x18003581d  jz      short loc_18003583D
0x18003581f  cmp     byte ptr [rcx+19h], 2
0x180035823  jb      short loc_18003583D
0x180035825  mov     rcx, [rcx+10h]
0x180035829  lea     r8, WPP_e8d0195a3cc637ab3689c79b5b31cbb7_Traceguids
0x180035830  mov     edx, 0Bh
0x180035835  mov     r9d, edi
0x180035838  call    WPP_SF_D
0x18003583d  mov     eax, edi
0x18003583f  jmp     short loc_180035872
0x180035841  mov     rcx, [rbx+18h]
0x180035845  mov     [rbx+38h], rcx
0x180035849  mov     [rbx+150h], rbx
0x180035850  lea     rax, [rcx+80h]
0x180035857  mov     [rbx+48h], rax
0x18003585b  lea     rax, [rcx+180h]
0x180035862  mov     [rbx+160h], rax
0x180035869  mov     [rbx+1E8h], rbx
0x180035870  xor     eax, eax
0x180035872  mov     rbx, [rsp+28h+arg_0]
0x180035877  add     rsp, 20h
0x18003587b  pop     rdi
0x18003587c  retn
```
