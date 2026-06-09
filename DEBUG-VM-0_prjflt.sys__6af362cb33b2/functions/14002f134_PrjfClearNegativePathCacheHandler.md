# PrjfClearNegativePathCacheHandler

- ea: `0x14002f134`
- end: `0x14002f1fe`
- name: `PrjfClearNegativePathCacheHandler`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140031a00`

## callees

- `0x140003e6c`
- `0x140006834`
- `0x14000d008`
- `0x140021f8c`
- `0x14002f134`

## pseudocode

```c
__int64 __fastcall PrjfClearNegativePathCacheHandler(__int64 a1, __int64 a2, ULONG *a3)
{
  __int64 UnionContextByVirtualizationInstanceInfo; // rax
  int v5; // edx
  int v6; // r8d
  char *v7; // rbx
  unsigned int v8; // edi

  UnionContextByVirtualizationInstanceInfo = PrjfGetUnionContextByVirtualizationInstanceInfo(a2, a1);
  v7 = (char *)UnionContextByVirtualizationInstanceInfo;
  if ( UnionContextByVirtualizationInstanceInfo )
  {
    v8 = 0;
    if ( (*(_DWORD *)(UnionContextByVirtualizationInstanceInfo + 56) & 1) != 0 )
      PrjfClearNegativePathCache(UnionContextByVirtualizationInstanceInfo, a3);
    PrjfReleaseUnionContext(v7);
  }
  else
  {
    v8 = -1073689084;
    if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        526,
        v5,
        v6,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        14,
        212,
        (__int64)WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        102);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14002f134  mov     [rsp+arg_0], rbx
0x14002f139  mov     [rsp+arg_8], rsi
0x14002f13e  push    rdi
0x14002f13f  sub     rsp, 50h
0x14002f143  mov     rax, rdx
0x14002f146  mov     rsi, r8
0x14002f149  mov     rdx, rcx
0x14002f14c  mov     rcx, rax
0x14002f14f  call    PrjfGetUnionContextByVirtualizationInstanceInfo
0x14002f154  mov     rbx, rax
0x14002f157  test    rax, rax
0x14002f15a  jnz     short loc_14002F1CE
0x14002f15c  mov     edi, 0C000CE04h
0x14002f161  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002f167  lea     rax, WPP_RECORDER_INITIALIZED
0x14002f16e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002f175  setnz   r8b
0x14002f179  and     dl, 40h
0x14002f17c  jnz     short loc_14002F183
0x14002f17e  test    r8b, r8b
0x14002f181  jz      short loc_14002F1EB
0x14002f183  mov     r9, cs:WPP_GLOBAL_Control
0x14002f18a  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002f191  mov     [rsp+58h+var_10], 1966h
0x14002f199  mov     ecx, 20Eh
0x14002f19e  mov     [rsp+58h+var_18], rax
0x14002f1a3  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x14002f1aa  mov     [rsp+58h+var_20], rax
0x14002f1af  mov     r9, [r9+40h]
0x14002f1b3  mov     [rsp+58h+var_28], 0D4h
0x14002f1ba  mov     [rsp+58h+var_30], 0Eh
0x14002f1c2  mov     [rsp+58h+var_38], 2
0x14002f1c7  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002f1cc  jmp     short loc_14002F1EB
0x14002f1ce  mov     ecx, [rax+38h]
0x14002f1d1  xor     edi, edi
0x14002f1d3  test    cl, 1
0x14002f1d6  jz      short loc_14002F1E3
0x14002f1d8  mov     rdx, rsi
0x14002f1db  mov     rcx, rbx
0x14002f1de  call    PrjfClearNegativePathCache
0x14002f1e3  mov     rcx, rbx; P
0x14002f1e6  call    PrjfReleaseUnionContext
0x14002f1eb  mov     rbx, [rsp+58h+arg_0]
0x14002f1f0  mov     eax, edi
0x14002f1f2  mov     rsi, [rsp+58h+arg_8]
0x14002f1f7  add     rsp, 50h
0x14002f1fb  pop     rdi
0x14002f1fc  retn
```
