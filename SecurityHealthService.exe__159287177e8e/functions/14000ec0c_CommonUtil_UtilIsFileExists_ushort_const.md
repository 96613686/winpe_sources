# CommonUtil::UtilIsFileExists(ushort const *)

- ea: `0x14000ec0c`
- end: `0x14000ec75`
- name: `?UtilIsFileExists@CommonUtil@@YAJPEBG@Z`
- size: `105`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140007538`
- `0x14000ed24`

## callees

- `0x140005394`
- `0x14000e780`
- `0x14000ec0c`

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
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, this);
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
0x14000ec0c  push    rbx
0x14000ec0e  sub     rsp, 20h
0x14000ec12  mov     rbx, rcx
0x14000ec15  mov     [rsp+28h+arg_8], 0
0x14000ec1d  mov     rdx, rcx; unsigned int *
0x14000ec20  lea     rcx, [rsp+28h+arg_8]; this
0x14000ec25  call    ?HrGetFileAttributes@CommonUtil@@YAJPEAKPEBG@Z; CommonUtil::HrGetFileAttributes(ulong *,ushort const *)
0x14000ec2a  test    eax, eax
0x14000ec2c  js      short loc_14000EC6F
0x14000ec2e  test    byte ptr [rsp+28h+arg_8], 10h
0x14000ec33  jz      short loc_14000EC6D
0x14000ec35  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec3c  lea     rax, WPP_GLOBAL_Control
0x14000ec43  cmp     rcx, rax
0x14000ec46  jz      short loc_14000EC66
0x14000ec48  test    byte ptr [rcx+1Ch], 1
0x14000ec4c  jz      short loc_14000EC66
0x14000ec4e  mov     rcx, [rcx+10h]
0x14000ec52  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000ec59  mov     edx, 38h ; '8'
0x14000ec5e  mov     r9, rbx
0x14000ec61  call    WPP_SF_S
0x14000ec66  mov     eax, 800700B7h
0x14000ec6b  jmp     short loc_14000EC6F
0x14000ec6d  xor     eax, eax
0x14000ec6f  add     rsp, 20h
0x14000ec73  pop     rbx
0x14000ec74  retn
```
