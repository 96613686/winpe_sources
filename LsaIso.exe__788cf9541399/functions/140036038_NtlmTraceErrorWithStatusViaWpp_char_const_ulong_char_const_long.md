# NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)

- ea: `0x140036038`
- end: `0x140036077`
- name: `?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z`
- size: `63`
- prototype: `void __fastcall(const char *, unsigned int, const char *, int)`
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

- `0x140036038`
- `0x14003617c`

## pseudocode

```c
void __fastcall NtlmTraceErrorWithStatusViaWpp(const char *a1, int a2, const char *a3, char a4)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sdsD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, (_DWORD)a3, (_DWORD)a1, a2, (__int64)a3, a4);
}

```

## disassembly

```asm
0x140036038  sub     rsp, 48h
0x14003603c  mov     rax, rcx
0x14003603f  mov     rcx, cs:WPP_GLOBAL_Control
0x140036046  lea     r10, WPP_GLOBAL_Control
0x14003604d  cmp     rcx, r10
0x140036050  jz      short loc_140036072
0x140036052  test    byte ptr [rcx+1Ch], 1
0x140036056  jz      short loc_140036072
0x140036058  mov     rcx, [rcx+10h]
0x14003605c  mov     [rsp+48h+var_18], r9d
0x140036061  mov     r9, rax
0x140036064  mov     [rsp+48h+var_20], r8
0x140036069  mov     [rsp+48h+var_28], edx
0x14003606d  call    WPP_SF_sdsD
0x140036072  add     rsp, 48h
0x140036076  retn
```
