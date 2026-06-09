# WPP_SF_sdd

- ea: `0x18000b774`
- end: `0x18000b7fa`
- name: `WPP_SF_sdd`
- size: `134`
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

- `0x18000b774`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b7ef`
- `ntdll!EtwTraceMessage` at `0x18000b7ef`

## pseudocode

```c
__int64 __fastcall WPP_SF_sdd(__int64 a1, unsigned __int16 a2, __int64 a3, const char *a4)
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
0x18000b774  sub     rsp, 68h
0x18000b778  test    r9, r9
0x18000b77b  jz      short loc_18000B790
0x18000b77d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b781  inc     rax
0x18000b784  cmp     byte ptr [r9+rax], 0
0x18000b789  jnz     short loc_18000B781
0x18000b78b  inc     rax
0x18000b78e  jmp     short loc_18000B795
0x18000b790  mov     eax, 5
0x18000b795  mov     [rsp+68h+var_18], 0
0x18000b79e  lea     r8, aNull; "NULL"
0x18000b7a5  mov     r10d, 4
0x18000b7ab  test    r9, r9
0x18000b7ae  mov     [rsp+68h+var_20], r10
0x18000b7b3  cmovz   r9, r8
0x18000b7b7  lea     r8, [rsp+68h+arg_28]
0x18000b7bf  mov     [rsp+68h+var_28], r8
0x18000b7c4  lea     r8, [rsp+68h+arg_20]
0x18000b7cc  mov     [rsp+68h+var_30], r10
0x18000b7d1  mov     [rsp+68h+var_38], r8
0x18000b7d6  lea     r8, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids
0x18000b7dd  mov     [rsp+68h+var_40], rax
0x18000b7e2  mov     [rsp+68h+var_48], r9
0x18000b7e7  movzx   r9d, dx
0x18000b7eb  lea     edx, [r10+27h]
0x18000b7ef  call    cs:__imp_EtwTraceMessage
0x18000b7f5  add     rsp, 68h
0x18000b7f9  retn
```
