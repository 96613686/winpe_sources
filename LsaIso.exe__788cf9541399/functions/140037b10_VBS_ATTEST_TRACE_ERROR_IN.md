# VBS_ATTEST_TRACE_ERROR_IN

- ea: `0x140037b10`
- end: `0x140037b48`
- name: `VBS_ATTEST_TRACE_ERROR_IN`
- size: `56`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x14000e510`
- `0x14000e830`
- `0x14000f0d0`
- `0x1400123a4`
- `0x1400124e8`
- `0x14001260c`
- `0x140012864`
- `0x140012aac`
- `0x140012be0`
- `0x140012d24`
- `0x140012de0`
- `0x140012ee8`
- `0x140013124`
- `0x140013700`
- `0x140037bec`
- `0x140037e90`
- `0x140037edc`
- `0x140038074`
- `0x140038160`
- `0x1400384e0`

## callees

- `0x140037b10`
- `0x140037b50`

## pseudocode

```c
PVOID *__fastcall VBS_ATTEST_TRACE_ERROR_IN(int a1, __int64 a2, int a3)
{
  PVOID *result; // rax

  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    return (PVOID *)WPP_SF_Dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3);
  return result;
}

```

## disassembly

```asm
0x140037b10  sub     rsp, 38h
0x140037b14  mov     r9d, ecx
0x140037b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140037b1e  lea     rax, WPP_GLOBAL_Control
0x140037b25  cmp     rcx, rax
0x140037b28  jz      short loc_140037B43
0x140037b2a  test    byte ptr [rcx+1Ch], 1
0x140037b2e  jz      short loc_140037B43
0x140037b30  mov     rcx, [rcx+10h]
0x140037b34  mov     [rsp+38h+var_10], r8d
0x140037b39  mov     [rsp+38h+var_18], rdx
0x140037b3e  call    WPP_SF_Dsd
0x140037b43  add     rsp, 38h
0x140037b47  retn
```
