# WPP_SF_sSdS

- ea: `0x18002d9e0`
- end: `0x18002dab6`
- name: `WPP_SF_sSdS`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180015660`

## callees

- `0x18002d9e0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18002daaa`
- `ntdll!EtwTraceMessage` at `0x18002daaa`

## string_xrefs

- `0x18002da81`: `PENSERVICE_CPenProcess::EnsureRunning`

## pseudocode

```c
__int64 __fastcall WPP_SF_sSdS(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, char a6, __int64 a7)
{
  __int64 v7; // rax
  __int64 v8; // rdx

  v7 = -1;
  if ( a7 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(a7 + 2 * v8) );
  }
  if ( a5 )
  {
    do
      ++v7;
    while ( *(_WORD *)(a5 + 2 * v7) );
  }
  return EtwTraceMessage(a1, 43, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids);
}

```

## disassembly

```asm
0x18002d9e0  push    rbx
0x18002d9e2  sub     rsp, 70h
0x18002d9e6  mov     r8, [rsp+78h+arg_30]
0x18002d9ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d9f2  xor     ebx, ebx
0x18002d9f4  mov     r10, rcx
0x18002d9f7  mov     r9d, 0Ah
0x18002d9fd  test    r8, r8
0x18002da00  jz      short loc_18002DA19
0x18002da02  mov     rdx, rax
0x18002da05  inc     rdx
0x18002da08  cmp     [r8+rdx*2], bx
0x18002da0d  jnz     short loc_18002DA05
0x18002da0f  lea     rdx, ds:2[rdx*2]
0x18002da17  jmp     short loc_18002DA1C
0x18002da19  mov     rdx, r9
0x18002da1c  mov     rcx, [rsp+78h+arg_20]
0x18002da24  lea     r11, aNull_0; "NULL"
0x18002da2b  test    r8, r8
0x18002da2e  cmovz   r8, r11
0x18002da32  test    rcx, rcx
0x18002da35  jz      short loc_18002DA4B
0x18002da37  inc     rax
0x18002da3a  cmp     [rcx+rax*2], bx
0x18002da3e  jnz     short loc_18002DA37
0x18002da40  lea     r9, ds:2[rax*2]
0x18002da48  test    rcx, rcx
0x18002da4b  mov     [rsp+78h+var_18], rbx
0x18002da50  lea     rax, [rsp+78h+arg_28]
0x18002da58  mov     [rsp+78h+var_20], rdx
0x18002da5d  cmovz   rcx, r11
0x18002da61  mov     [rsp+78h+var_28], r8
0x18002da66  mov     r11d, 18h
0x18002da6c  mov     [rsp+78h+var_30], 4
0x18002da75  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002da7c  mov     [rsp+78h+var_38], rax
0x18002da81  lea     rax, aPenserviceCpen_0; "PENSERVICE_CPenProcess::EnsureRunning"
0x18002da88  mov     [rsp+78h+var_40], r9
0x18002da8d  mov     r9d, r11d
0x18002da90  mov     [rsp+78h+var_48], rcx
0x18002da95  lea     edx, [r11+13h]
0x18002da99  mov     [rsp+78h+var_50], 26h ; '&'
0x18002daa2  mov     rcx, r10
0x18002daa5  mov     [rsp+78h+var_58], rax
0x18002daaa  call    cs:__imp_EtwTraceMessage
0x18002dab0  add     rsp, 70h
0x18002dab4  pop     rbx
0x18002dab5  retn
```
