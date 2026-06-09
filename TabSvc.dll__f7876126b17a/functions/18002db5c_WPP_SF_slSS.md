# WPP_SF_slSS

- ea: `0x18002db5c`
- end: `0x18002dc34`
- name: `WPP_SF_slSS`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180016620`

## callees

- `0x18002db5c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18002dc28`
- `ntdll!EtwTraceMessage` at `0x18002dc28`

## string_xrefs

- `0x18002dc13`: `PENSERVICE_CPenProcess::Init`

## pseudocode

```c
__int64 __fastcall WPP_SF_slSS(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char a5, __int64 a6, __int64 a7)
{
  __int64 v7; // rdx
  __int64 v8; // rax

  v7 = -1;
  if ( a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a7 + 2 * v8) );
  }
  if ( a6 )
  {
    do
      ++v7;
    while ( *(_WORD *)(a6 + 2 * v7) );
  }
  return EtwTraceMessage(a1, 43, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids);
}

```

## disassembly

```asm
0x18002db5c  push    rbx
0x18002db5e  sub     rsp, 70h
0x18002db62  mov     r8, [rsp+78h+arg_30]
0x18002db6a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002db6e  xor     r9d, r9d
0x18002db71  mov     r10, rcx
0x18002db74  mov     r11d, 0Ah
0x18002db7a  test    r8, r8
0x18002db7d  jz      short loc_18002DB96
0x18002db7f  mov     rax, rdx
0x18002db82  inc     rax
0x18002db85  cmp     [r8+rax*2], r9w
0x18002db8a  jnz     short loc_18002DB82
0x18002db8c  lea     rcx, ds:2[rax*2]
0x18002db94  jmp     short loc_18002DB99
0x18002db96  mov     rcx, r11
0x18002db99  mov     rax, [rsp+78h+arg_28]
0x18002dba1  lea     rbx, aNull_0; "NULL"
0x18002dba8  test    r8, r8
0x18002dbab  cmovz   r8, rbx
0x18002dbaf  test    rax, rax
0x18002dbb2  jz      short loc_18002DBC8
0x18002dbb4  inc     rdx
0x18002dbb7  cmp     [rax+rdx*2], r9w
0x18002dbbc  jnz     short loc_18002DBB4
0x18002dbbe  lea     rdx, ds:2[rdx*2]
0x18002dbc6  jmp     short loc_18002DBCB
0x18002dbc8  mov     rdx, r11
0x18002dbcb  mov     [rsp+78h+var_18], r9
0x18002dbd0  test    rax, rax
0x18002dbd3  mov     [rsp+78h+var_20], rcx
0x18002dbd8  mov     r9d, r11d
0x18002dbdb  mov     [rsp+78h+var_28], r8
0x18002dbe0  cmovz   rax, rbx
0x18002dbe4  mov     [rsp+78h+var_30], rdx
0x18002dbe9  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002dbf0  mov     [rsp+78h+var_38], rax
0x18002dbf5  mov     edx, 2Bh ; '+'
0x18002dbfa  mov     [rsp+78h+var_40], 4
0x18002dc03  lea     rax, [rsp+78h+arg_20]
0x18002dc0b  mov     [rsp+78h+var_48], rax
0x18002dc10  mov     rcx, r10
0x18002dc13  lea     rax, aPenserviceCpen_1; "PENSERVICE_CPenProcess::Init"
0x18002dc1a  mov     [rsp+78h+var_50], 1Dh
0x18002dc23  mov     [rsp+78h+var_58], rax
0x18002dc28  call    cs:__imp_EtwTraceMessage
0x18002dc2e  add     rsp, 70h
0x18002dc32  pop     rbx
0x18002dc33  retn
```
