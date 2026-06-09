# WPP_SF_sdqd

- ea: `0x180004cb0`
- end: `0x180004d52`
- name: `WPP_SF_sdqd`
- size: `162`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002650`
- `0x180003c90`
- `0x180003e30`
- `0x180003f50`
- `0x180004390`
- `0x1800044a0`
- `0x180004b80`

## callees

- `0x180004cb0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180004d47`
- `ntdll!EtwTraceMessage` at `0x180004d47`

## pseudocode

```c
__int64 __fastcall WPP_SF_sdqd(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
{
  __int64 v4; // rax

  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
  }
  if ( !a4 )
    a4 = "NULL";
  return EtwTraceMessage(a1, 43, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids, a2, a4);
}

```

## disassembly

```asm
0x180004cb0  sub     rsp, 78h
0x180004cb4  test    r9, r9
0x180004cb7  jz      short loc_180004CCF
0x180004cb9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004cc0  inc     rax
0x180004cc3  cmp     byte ptr [r9+rax], 0
0x180004cc8  jnz     short loc_180004CC0
0x180004cca  inc     rax
0x180004ccd  jmp     short loc_180004CD4
0x180004ccf  mov     eax, 5
0x180004cd4  mov     [rsp+78h+var_18], 0
0x180004cdd  lea     r8, aNull; "NULL"
0x180004ce4  mov     [rsp+78h+var_20], 4
0x180004ced  test    r9, r9
0x180004cf0  cmovz   r9, r8
0x180004cf4  lea     r8, [rsp+78h+arg_30]
0x180004cfc  mov     [rsp+78h+var_28], r8
0x180004d01  lea     r8, [rsp+78h+arg_28]
0x180004d09  mov     [rsp+78h+var_30], 8
0x180004d12  mov     [rsp+78h+var_38], r8
0x180004d17  lea     r8, [rsp+78h+arg_20]
0x180004d1f  mov     [rsp+78h+var_40], 4
0x180004d28  mov     [rsp+78h+var_48], r8
0x180004d2d  lea     r8, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids
0x180004d34  mov     [rsp+78h+var_50], rax
0x180004d39  mov     [rsp+78h+var_58], r9
0x180004d3e  movzx   r9d, dx
0x180004d42  mov     edx, 2Bh ; '+'
0x180004d47  call    cs:__imp_EtwTraceMessage
0x180004d4d  add     rsp, 78h
0x180004d51  retn
```
