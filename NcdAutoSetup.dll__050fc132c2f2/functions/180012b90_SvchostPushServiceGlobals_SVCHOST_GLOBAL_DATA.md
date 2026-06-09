# SvchostPushServiceGlobals(_SVCHOST_GLOBAL_DATA *)

- ea: `0x180012b90`
- end: `0x180012c26`
- name: `?SvchostPushServiceGlobals@@YAXPEAU_SVCHOST_GLOBAL_DATA@@@Z`
- size: `150`
- prototype: `void __fastcall(struct _SVCHOST_GLOBAL_DATA *, __int64, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000a644`
- `0x180012b90`
- `0x1800130b8`
- `0x180013138`

## string_xrefs

- `0x180012bd0`: `SvchostPushServiceGlobals`
- `0x180012be8`: `SvchostPushServiceGlobals`

## pseudocode

```c
void __fastcall SvchostPushServiceGlobals(struct _SVCHOST_GLOBAL_DATA *a1, __int64 a2, int a3)
{
  int v4; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
  IncThreadCount("SvchostPushServiceGlobals", 25, a3);
  g_SvchostGlobals = a1;
  DecThreadCount("SvchostPushServiceGlobals", 27, v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_3f50365df99735211a88e8fb382b12e7_Traceguids);
}

```

## disassembly

```asm
0x180012b90  mov     [rsp+arg_0], rbx
0x180012b95  push    rdi
0x180012b96  sub     rsp, 20h
0x180012b9a  mov     rbx, rcx
0x180012b9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ba4  lea     rdi, WPP_GLOBAL_Control
0x180012bab  cmp     rcx, rdi
0x180012bae  jz      short loc_180012BCB
0x180012bb0  test    byte ptr [rcx+1Ch], 20h
0x180012bb4  jz      short loc_180012BCB
0x180012bb6  mov     rcx, [rcx+10h]
0x180012bba  lea     r8, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x180012bc1  mov     edx, 29h ; ')'
0x180012bc6  call    WPP_SF_
0x180012bcb  mov     edx, 119h; unsigned int
0x180012bd0  lea     rcx, aSvchostpushser_0; "SvchostPushServiceGlobals"
0x180012bd7  call    ?IncThreadCount@@YAXPEBDK@Z; IncThreadCount(char const *,ulong)
0x180012bdc  mov     edx, 11Bh; unsigned int
0x180012be1  mov     cs:?g_SvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, rbx; _SVCHOST_GLOBAL_DATA * g_SvchostGlobals
0x180012be8  lea     rcx, aSvchostpushser_0; "SvchostPushServiceGlobals"
0x180012bef  call    ?DecThreadCount@@YAXPEBDK@Z; DecThreadCount(char const *,ulong)
0x180012bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bfb  cmp     rcx, rdi
0x180012bfe  jz      short loc_180012C1B
0x180012c00  test    byte ptr [rcx+1Ch], 20h
0x180012c04  jz      short loc_180012C1B
0x180012c06  mov     rcx, [rcx+10h]
0x180012c0a  lea     r8, WPP_3f50365df99735211a88e8fb382b12e7_Traceguids
0x180012c11  mov     edx, 2Ah ; '*'
0x180012c16  call    WPP_SF_
0x180012c1b  mov     rbx, [rsp+28h+arg_0]
0x180012c20  add     rsp, 20h
0x180012c24  pop     rdi
0x180012c25  retn
```
