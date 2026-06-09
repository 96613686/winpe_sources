# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18000502c`
- end: `0x180005079`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004f94`
- `0x1800064e8`

## callees

- `0x18000502c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000505f`
- `ntdll!EtwEventWriteTransfer` at `0x18000505f`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    *(_QWORD *)a5 = v5;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(*a1, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x18000502c  sub     rsp, 38h
0x180005030  mov     r8, [rcx+8]
0x180005034  mov     rax, [rsp+38h+arg_20]
0x180005039  test    r8, r8
0x18000503c  jnz     short loc_18000506A
0x18000503e  mov     [rax], r8
0x180005041  xor     r10d, r10d
0x180005044  mov     [rax+8], r8d
0x180005048  xor     r8d, r8d
0x18000504b  mov     [rsp+38h+var_10], rax
0x180005050  mov     [rax+0Ch], r10d
0x180005054  mov     rcx, [rcx]
0x180005057  mov     [rsp+38h+var_18], r9d
0x18000505c  xor     r9d, r9d
0x18000505f  call    cs:__imp_EtwEventWriteTransfer
0x180005065  add     rsp, 38h
0x180005069  retn
0x18000506a  mov     [rax], r8
0x18000506d  mov     r10d, 2
0x180005073  movzx   r8d, word ptr [r8]
0x180005077  jmp     short loc_180005044
```
