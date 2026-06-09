# NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)

- ea: `0x180001cdc`
- end: `0x180001d1b`
- name: `?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z`
- size: `63`
- prototype: `void __fastcall(const char *, unsigned int, const char *, int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085e0`
- `0x180008780`
- `0x180008fe0`
- `0x180009c70`
- `0x180009d10`
- `0x180009df0`
- `0x180009e70`
- `0x18000a1b0`

## callees

- `0x180001cdc`
- `0x180001e18`

## pseudocode

```c
void __fastcall NtlmTraceErrorWithStatusViaWpp(const char *a1, int a2, const char *a3, char a4)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sdsD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, (_DWORD)a3, (_DWORD)a1, a2, (__int64)a3, a4);
}

```

## disassembly

```asm
0x180001cdc  sub     rsp, 48h
0x180001ce0  mov     rax, rcx
0x180001ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cea  lea     r10, WPP_GLOBAL_Control
0x180001cf1  cmp     rcx, r10
0x180001cf4  jz      short loc_180001D16
0x180001cf6  test    byte ptr [rcx+1Ch], 1
0x180001cfa  jz      short loc_180001D16
0x180001cfc  mov     rcx, [rcx+10h]
0x180001d00  mov     [rsp+48h+var_18], r9d
0x180001d05  mov     r9, rax
0x180001d08  mov     [rsp+48h+var_20], r8
0x180001d0d  mov     [rsp+48h+var_28], edx
0x180001d11  call    WPP_SF_sdsD
0x180001d16  add     rsp, 48h
0x180001d1a  retn
```
