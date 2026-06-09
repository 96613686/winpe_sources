# CommonUtil::UtilIsFileExists(ushort const *)

- ea: `0x180007148`
- end: `0x1800071a5`
- name: `?UtilIsFileExists@CommonUtil@@YAJPEBG@Z`
- size: `93`
- prototype: `int __fastcall(CommonUtil *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800057f4`
- `0x180007304`

## callees

- `0x18000682c`
- `0x180006d84`
- `0x180007148`

## pseudocode

```c
int __fastcall CommonUtil::UtilIsFileExists(CommonUtil *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int result; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  result = CommonUtil::HrGetFileAttributes((CommonUtil *)&v7, (unsigned int *)this, a3);
  if ( result >= 0 )
  {
    if ( (v7 & 0x10) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, this);
      return -2147024713;
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
0x180007148  push    rbx
0x18000714a  sub     rsp, 20h
0x18000714e  mov     rbx, rcx
0x180007151  mov     [rsp+28h+arg_8], 0
0x180007159  mov     rdx, rcx; unsigned int *
0x18000715c  lea     rcx, [rsp+28h+arg_8]; this
0x180007161  call    ?HrGetFileAttributes@CommonUtil@@YAJPEAKPEBG@Z; CommonUtil::HrGetFileAttributes(ulong *,ushort const *)
0x180007166  test    eax, eax
0x180007168  js      short loc_18000719F
0x18000716a  test    byte ptr [rsp+28h+arg_8], 10h
0x18000716f  jz      short loc_18000719D
0x180007171  mov     rcx, cs:WPP_GLOBAL_Control
0x180007178  lea     rax, WPP_GLOBAL_Control
0x18000717f  cmp     rcx, rax
0x180007182  jz      short loc_180007196
0x180007184  test    byte ptr [rcx+1Ch], 1
0x180007188  jz      short loc_180007196
0x18000718a  mov     rcx, [rcx+10h]
0x18000718e  mov     r9, rbx
0x180007191  call    WPP_SF_S
0x180007196  mov     eax, 800700B7h
0x18000719b  jmp     short loc_18000719F
0x18000719d  xor     eax, eax
0x18000719f  add     rsp, 20h
0x1800071a3  pop     rbx
0x1800071a4  retn
```
