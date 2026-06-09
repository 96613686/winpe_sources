# WPP_SF_sdq

- ea: `0x18000b800`
- end: `0x18000b88d`
- name: `WPP_SF_sdq`
- size: `141`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003c90`
- `0x180003e30`
- `0x1800044a0`
- `0x180004b80`

## callees

- `0x18000b800`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b882`
- `ntdll!EtwTraceMessage` at `0x18000b882`

## pseudocode

```c
__int64 __fastcall WPP_SF_sdq(__int64 a1, __int64 a2, __int64 a3, const char *a4)
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
  return EtwTraceMessage(a1, 43, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids, 14, a4);
}

```

## disassembly

```asm
0x18000b800  sub     rsp, 68h
0x18000b804  test    r9, r9
0x18000b807  jz      short loc_18000B81C
0x18000b809  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b80d  inc     rax
0x18000b810  cmp     byte ptr [r9+rax], 0
0x18000b815  jnz     short loc_18000B80D
0x18000b817  inc     rax
0x18000b81a  jmp     short loc_18000B821
0x18000b81c  mov     eax, 5
0x18000b821  mov     [rsp+68h+var_18], 0
0x18000b82a  lea     rdx, aNull; "NULL"
0x18000b831  mov     [rsp+68h+var_20], 8
0x18000b83a  test    r9, r9
0x18000b83d  mov     r8d, 0Eh
0x18000b843  cmovz   r9, rdx
0x18000b847  lea     rdx, [rsp+68h+arg_28]
0x18000b84f  mov     [rsp+68h+var_28], rdx
0x18000b854  lea     rdx, [rsp+68h+arg_20]
0x18000b85c  mov     [rsp+68h+var_30], 4
0x18000b865  mov     [rsp+68h+var_38], rdx
0x18000b86a  mov     [rsp+68h+var_40], rax
0x18000b86f  mov     [rsp+68h+var_48], r9
0x18000b874  mov     r9d, r8d
0x18000b877  lea     r8, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids
0x18000b87e  lea     edx, [r9+1Dh]
0x18000b882  call    cs:__imp_EtwTraceMessage
0x18000b888  add     rsp, 68h
0x18000b88c  retn
```
