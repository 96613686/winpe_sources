# NtlmTraceInfoViaWpp(char const *,ulong,char const *)

- ea: `0x180001d24`
- end: `0x180001d62`
- name: `?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z`
- size: `62`
- prototype: `void __fastcall(const char *, unsigned int, const char *)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085e0`
- `0x180008780`
- `0x180008a90`
- `0x180008fe0`
- `0x1800093e0`
- `0x1800094f0`
- `0x180009c70`
- `0x180009d10`
- `0x180009df0`
- `0x180009e70`
- `0x18000a480`

## callees

- `0x180001d24`
- `0x180001d68`

## pseudocode

```c
void __fastcall NtlmTraceInfoViaWpp(const char *a1, char a2, const char *a3)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_sds(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, (_DWORD)a3, (_DWORD)a1, a2, (__int64)a3);
}

```

## disassembly

```asm
0x180001d24  sub     rsp, 38h
0x180001d28  mov     eax, edx
0x180001d2a  mov     r9, rcx
0x180001d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d34  lea     rdx, WPP_GLOBAL_Control
0x180001d3b  cmp     rcx, rdx
0x180001d3e  jz      short loc_180001D5D
0x180001d40  test    byte ptr [rcx+1Ch], 4
0x180001d44  jz      short loc_180001D5D
0x180001d46  mov     rcx, [rcx+10h]
0x180001d4a  mov     edx, 0Eh
0x180001d4f  mov     [rsp+38h+var_10], r8
0x180001d54  mov     [rsp+38h+var_18], eax
0x180001d58  call    WPP_SF_sds
0x180001d5d  add     rsp, 38h
0x180001d61  retn
```
