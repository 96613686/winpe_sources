# CommonUtil::UtilIsFileExists(wchar_t const *)

- ea: `0x1400044d0`
- end: `0x14000453e`
- name: `?UtilIsFileExists@CommonUtil@@YAJPEB_W@Z`
- size: `110`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140003c50`

## callees

- `0x1400042f4`
- `0x1400044d0`
- `0x14001dac4`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilIsFileExists(const WCHAR *this, const wchar_t *a2, const wchar_t *a3)
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
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_bed851edf8673fd54b380593fb017a56_Traceguids, this);
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
0x1400044d0  push    rbx
0x1400044d2  sub     rsp, 20h
0x1400044d6  mov     rbx, rcx
0x1400044d9  mov     [rsp+28h+arg_8], 0
0x1400044e1  mov     rdx, rcx; unsigned int *
0x1400044e4  lea     rcx, [rsp+28h+arg_8]; this
0x1400044e9  call    ?HrGetFileAttributes@CommonUtil@@YAJPEAKPEB_W@Z; CommonUtil::HrGetFileAttributes(ulong *,wchar_t const *)
0x1400044ee  mov     edx, eax
0x1400044f0  shr     edx, 1Fh
0x1400044f3  test    dl, dl
0x1400044f5  jnz     short loc_140004538
0x1400044f7  test    byte ptr [rsp+28h+arg_8], 10h
0x1400044fc  jz      short loc_140004536
0x1400044fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140004505  lea     rax, WPP_GLOBAL_Control
0x14000450c  cmp     rcx, rax
0x14000450f  jz      short loc_14000452F
0x140004511  test    byte ptr [rcx+1Ch], 1
0x140004515  jz      short loc_14000452F
0x140004517  mov     rcx, [rcx+10h]
0x14000451b  lea     r8, WPP_bed851edf8673fd54b380593fb017a56_Traceguids
0x140004522  mov     edx, 24h ; '$'
0x140004527  mov     r9, rbx
0x14000452a  call    WPP_SF_S
0x14000452f  mov     eax, 800700B7h
0x140004534  jmp     short loc_140004538
0x140004536  xor     eax, eax
0x140004538  add     rsp, 20h
0x14000453c  pop     rbx
0x14000453d  retn
```
