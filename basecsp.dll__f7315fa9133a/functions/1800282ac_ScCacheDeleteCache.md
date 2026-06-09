# ScCacheDeleteCache

- ea: `0x1800282ac`
- end: `0x180028356`
- name: `ScCacheDeleteCache`
- size: `170`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d2b0`
- `0x18001d1fc`
- `0x18001ed64`

## callees

- `0x180019650`
- `0x1800196ac`
- `0x18001c96c`
- `0x1800280a4`
- `0x1800282ac`

## pseudocode

```c
__int64 __fastcall ScCacheDeleteCache(struct _RTL_CRITICAL_SECTION *a1)
{
  __int64 v2; // rcx

  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  I_ServerCacheCleanup(a1);
  WppTraceIndent(v2, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800282ac  mov     [rsp+arg_0], rbx
0x1800282b1  push    rdi
0x1800282b2  sub     rsp, 30h
0x1800282b6  xor     edx, edx
0x1800282b8  mov     rbx, rcx
0x1800282bb  call    WppTraceIndent
0x1800282c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282c7  lea     rdi, WPP_GLOBAL_Control
0x1800282ce  cmp     rcx, rdi
0x1800282d1  jz      short loc_1800282FB
0x1800282d3  test    byte ptr [rcx+1Ch], 2
0x1800282d7  jz      short loc_1800282FB
0x1800282d9  cmp     byte ptr [rcx+19h], 5
0x1800282dd  jb      short loc_1800282FB
0x1800282df  mov     r9, cs:WPP_pszIndent
0x1800282e6  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800282ed  mov     rcx, [rcx+10h]
0x1800282f1  mov     edx, 12h
0x1800282f6  call    WPP_SF_s
0x1800282fb  mov     rcx, rbx
0x1800282fe  call    I_ServerCacheCleanup
0x180028303  mov     edx, 1
0x180028308  call    WppTraceIndent
0x18002830d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028314  cmp     rcx, rdi
0x180028317  jz      short loc_180028349
0x180028319  test    byte ptr [rcx+1Ch], 2
0x18002831d  jz      short loc_180028349
0x18002831f  cmp     byte ptr [rcx+19h], 5
0x180028323  jb      short loc_180028349
0x180028325  mov     r9, cs:WPP_pszIndent
0x18002832c  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028333  mov     rcx, [rcx+10h]
0x180028337  mov     edx, 13h
0x18002833c  mov     [rsp+38h+var_18], 0
0x180028344  call    WPP_SF_sD
0x180028349  mov     rbx, [rsp+38h+arg_0]
0x18002834e  xor     eax, eax
0x180028350  add     rsp, 30h
0x180028354  pop     rdi
0x180028355  retn
```
