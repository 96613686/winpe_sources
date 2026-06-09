# NtlmTraceInfoViaWpp(char const *,ulong,char const *)

- ea: `0x140036080`
- end: `0x1400360c5`
- name: `?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z`
- size: `69`
- prototype: `void __fastcall(const char *, unsigned int, const char *)`
- caller_count: `21`
- callee_count: `2`
- tags: ``

## callers

- `0x140033a60`
- `0x140034180`
- `0x140034270`
- `0x140034360`
- `0x140034700`
- `0x1400348a0`
- `0x140034a40`
- `0x140034c60`
- `0x1400350e0`
- `0x1400352c0`
- `0x1400353e0`
- `0x140035610`
- `0x140035770`
- `0x140035980`
- `0x140035ad0`
- `0x140035c80`
- `0x140035e30`
- `0x140035ec0`
- `0x140035fc0`
- `0x14003623c`
- `0x140036330`

## callees

- `0x140036080`
- `0x1400360cc`

## pseudocode

```c
void __fastcall NtlmTraceInfoViaWpp(const char *a1, char a2, const char *a3)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_sds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)"NtlmSuccess",
      (_DWORD)a1,
      a2,
      (__int64)"NtlmSuccess");
}

```

## disassembly

```asm
0x140036080  sub     rsp, 38h
0x140036084  mov     eax, edx
0x140036086  mov     r9, rcx
0x140036089  mov     rcx, cs:WPP_GLOBAL_Control
0x140036090  lea     rdx, WPP_GLOBAL_Control
0x140036097  cmp     rcx, rdx
0x14003609a  jz      short loc_1400360C0
0x14003609c  test    byte ptr [rcx+1Ch], 4
0x1400360a0  jz      short loc_1400360C0
0x1400360a2  mov     rcx, [rcx+10h]
0x1400360a6  lea     r8, aNtlmsuccess; "NtlmSuccess"
0x1400360ad  mov     [rsp+38h+var_10], r8
0x1400360b2  mov     edx, 0Eh
0x1400360b7  mov     [rsp+38h+var_18], eax
0x1400360bb  call    WPP_SF_sds
0x1400360c0  add     rsp, 38h
0x1400360c4  retn
```
