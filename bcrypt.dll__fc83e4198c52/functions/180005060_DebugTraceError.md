# DebugTraceError

- ea: `0x180005060`
- end: `0x18000509f`
- name: `DebugTraceError`
- size: `63`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `80`
- callee_count: `2`
- tags: ``

## callers

- `0x180001590`
- `0x180004230`
- `0x180004390`
- `0x1800049a0`
- `0x180004e60`
- `0x1800050b0`
- `0x180005280`
- `0x180005470`
- `0x180005bc0`
- `0x180005f50`
- `0x180006020`
- `0x1800066f0`
- `0x180006da0`
- `0x1800070d0`
- `0x1800078e0`
- `0x180007b50`
- `0x180007d60`
- `0x180008890`
- `0x1800090a0`
- `0x180009454`
- `0x180009570`
- `0x180009764`
- `0x180009ba0`
- `0x18000a070`
- `0x18000a230`
- `0x18000a3e8`
- `0x18000abd8`
- `0x18000acc0`
- `0x18000b1d0`
- `0x18000b680`
- `0x18000b824`
- `0x18000bac0`
- `0x18000bba0`
- `0x18000c1e0`
- `0x18000ce50`
- `0x18000d030`
- `0x18000dac4`
- `0x18000df40`
- `0x18000e190`
- `0x18000e270`
- `0x18000e368`
- `0x18000e628`
- `0x18000e910`
- `0x18000edac`
- `0x18000f1fc`
- `0x18000f6a8`
- `0x1800101c0`
- `0x180012318`
- `0x180012a70`
- `0x180012cc4`

## callees

- `0x180005060`
- `0x180007a7c`

## pseudocode

```c
__int64 __fastcall DebugTraceError(unsigned int a1, int a2, __int64 a3, char a4)
{
  __int64 result; // rax

  result = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return WPP_SF_sDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a2, a1, a3, a4);
  return result;
}

```

## disassembly

```asm
0x180005060  sub     rsp, 48h
0x180005064  mov     eax, ecx
0x180005066  mov     rcx, cs:WPP_GLOBAL_Control
0x18000506d  lea     r10, WPP_GLOBAL_Control
0x180005074  cmp     rcx, r10
0x180005077  jz      short loc_180005099
0x180005079  test    byte ptr [rcx+1Ch], 1
0x18000507d  jz      short loc_180005099
0x18000507f  mov     rcx, [rcx+10h]
0x180005083  mov     [rsp+48h+var_18], r9d
0x180005088  mov     r9, rdx
0x18000508b  mov     [rsp+48h+var_20], r8
0x180005090  mov     [rsp+48h+var_28], eax
0x180005094  call    WPP_SF_sDsd
0x180005099  add     rsp, 48h
0x18000509d  retn
```
