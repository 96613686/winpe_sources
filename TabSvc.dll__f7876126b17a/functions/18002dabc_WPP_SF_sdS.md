# WPP_SF_sdS

- ea: `0x18002dabc`
- end: `0x18002db54`
- name: `WPP_SF_sdS`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180015660`

## callees

- `0x18002dabc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18002db49`
- `ntdll!EtwTraceMessage` at `0x18002db49`

## string_xrefs

- `0x18002db30`: `PENSERVICE_CPenProcess::EnsureRunning`

## pseudocode

```c
__int64 __fastcall WPP_SF_sdS(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, __int64 a6)
{
  __int64 v6; // rax

  if ( a6 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_WORD *)(a6 + 2 * v6) );
  }
  return EtwTraceMessage(a1, 43, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids);
}

```

## disassembly

```asm
0x18002dabc  sub     rsp, 68h
0x18002dac0  mov     rdx, [rsp+68h+arg_28]
0x18002dac8  xor     r9d, r9d
0x18002dacb  test    rdx, rdx
0x18002dace  jz      short loc_18002DAE8
0x18002dad0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002dad4  inc     rax
0x18002dad7  cmp     [rdx+rax*2], r9w
0x18002dadc  jnz     short loc_18002DAD4
0x18002dade  lea     rax, ds:2[rax*2]
0x18002dae6  jmp     short loc_18002DAED
0x18002dae8  mov     eax, 0Ah
0x18002daed  mov     [rsp+68h+var_18], r9
0x18002daf2  lea     r8, aNull_0; "NULL"
0x18002daf9  mov     [rsp+68h+var_20], rax
0x18002dafe  test    rdx, rdx
0x18002db01  lea     rax, [rsp+68h+arg_20]
0x18002db09  cmovz   rdx, r8
0x18002db0d  mov     r8d, 1Eh
0x18002db13  mov     [rsp+68h+var_28], rdx
0x18002db18  mov     r9d, r8d
0x18002db1b  mov     [rsp+68h+var_30], 4
0x18002db24  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002db2b  mov     [rsp+68h+var_38], rax
0x18002db30  lea     rax, aPenserviceCpen_0; "PENSERVICE_CPenProcess::EnsureRunning"
0x18002db37  mov     [rsp+68h+var_40], 26h ; '&'
0x18002db40  lea     edx, [r9+0Dh]
0x18002db44  mov     [rsp+68h+var_48], rax
0x18002db49  call    cs:__imp_EtwTraceMessage
0x18002db4f  add     rsp, 68h
0x18002db53  retn
```
