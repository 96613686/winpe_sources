# CommonUtil::UtilIsFileExists(ushort const *)

- ea: `0x14000d9e8`
- end: `0x14000da51`
- name: `?UtilIsFileExists@CommonUtil@@YAJPEBG@Z`
- size: `105`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140005fdc`

## callees

- `0x14000cfa0`
- `0x14000d6f8`
- `0x14000d9e8`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilIsFileExists(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 result; // rax
  int v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  result = CommonUtil::HrGetFileAttributes((CommonUtil *)&v5, this, a3);
  if ( (int)result >= 0 )
  {
    if ( (v5 & 0x10) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, this);
      return 2147942583LL;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d9e8  push    rbx
0x14000d9ea  sub     rsp, 20h
0x14000d9ee  mov     rbx, rcx
0x14000d9f1  mov     [rsp+28h+arg_8], 0
0x14000d9f9  mov     rdx, rcx; unsigned int *
0x14000d9fc  lea     rcx, [rsp+28h+arg_8]; this
0x14000da01  call    ?HrGetFileAttributes@CommonUtil@@YAJPEAKPEBG@Z; CommonUtil::HrGetFileAttributes(ulong *,ushort const *)
0x14000da06  test    eax, eax
0x14000da08  js      short loc_14000DA4B
0x14000da0a  test    byte ptr [rsp+28h+arg_8], 10h
0x14000da0f  jz      short loc_14000DA49
0x14000da11  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da18  lea     rax, WPP_GLOBAL_Control
0x14000da1f  cmp     rcx, rax
0x14000da22  jz      short loc_14000DA42
0x14000da24  test    byte ptr [rcx+1Ch], 1
0x14000da28  jz      short loc_14000DA42
0x14000da2a  mov     rcx, [rcx+10h]
0x14000da2e  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000da35  mov     edx, 38h ; '8'
0x14000da3a  mov     r9, rbx
0x14000da3d  call    WPP_SF_S
0x14000da42  mov     eax, 800700B7h
0x14000da47  jmp     short loc_14000DA4B
0x14000da49  xor     eax, eax
0x14000da4b  add     rsp, 20h
0x14000da4f  pop     rbx
0x14000da50  retn
```
