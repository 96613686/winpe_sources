# WPP_SF_SD

- ea: `0x18000fbfc`
- end: `0x18000fc6c`
- name: `WPP_SF_SD`
- size: `112`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, const wchar_t *)`
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003f40`
- `0x180004120`
- `0x18000536c`
- `0x180005edc`
- `0x180005fbc`
- `0x18000e0d8`
- `0x18000fef0`
- `0x1800102e8`
- `0x180010548`
- `0x180010798`
- `0x180010bfc`
- `0x180010c9c`

## callees

- `0x18000fbfc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000fc61`
- `ntdll!EtwTraceMessage` at `0x18000fc61`

## pseudocode

```c
__int64 __fastcall WPP_SF_SD(__int64 a1, unsigned __int16 a2, __int64 a3, const wchar_t *a4)
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
    a4 = L"NULL";
  return EtwTraceMessage(a1, 43, a3, a2, a4);
}

```

## disassembly

```asm
0x18000fbfc  sub     rsp, 58h
0x18000fc00  xor     r11d, r11d
0x18000fc03  test    r9, r9
0x18000fc06  jz      short loc_18000FC20
0x18000fc08  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fc0c  inc     rax
0x18000fc0f  cmp     [r9+rax*2], r11w
0x18000fc14  jnz     short loc_18000FC0C
0x18000fc16  lea     rax, ds:2[rax*2]
0x18000fc1e  jmp     short loc_18000FC25
0x18000fc20  mov     eax, 0Ah
0x18000fc25  mov     [rsp+58h+var_18], r11
0x18000fc2a  lea     r10, aNull_0; "NULL"
0x18000fc31  test    r9, r9
0x18000fc34  mov     [rsp+58h+var_20], 4
0x18000fc3d  cmovz   r9, r10
0x18000fc41  lea     r10, [rsp+58h+arg_20]
0x18000fc49  mov     [rsp+58h+var_28], r10
0x18000fc4e  mov     [rsp+58h+var_30], rax
0x18000fc53  mov     [rsp+58h+var_38], r9
0x18000fc58  movzx   r9d, dx
0x18000fc5c  mov     edx, 2Bh ; '+'
0x18000fc61  call    cs:__imp_EtwTraceMessage
0x18000fc67  add     rsp, 58h
0x18000fc6b  retn
```
