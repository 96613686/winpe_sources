# WPP_SF_sSSS

- ea: `0x18002d8cc`
- end: `0x18002d9d7`
- name: `WPP_SF_sSSS`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x18002c3c4`

## callees

- `0x18002d8cc`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18002d9bf`
- `ntdll!EtwTraceMessage` at `0x18002d9bf`

## string_xrefs

- `0x18002d9a6`: `PENSERVICE_CPenProcess::CreateProcessW`

## pseudocode

```c
__int64 __fastcall WPP_SF_sSSS(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rax

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
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a6 + 2 * v9) );
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
0x18002d8cc  mov     [rsp+arg_0], rbx
0x18002d8d1  mov     [rsp+arg_8], rsi
0x18002d8d6  push    rdi
0x18002d8d7  sub     rsp, 70h
0x18002d8db  mov     r8, [rsp+78h+arg_30]
0x18002d8e3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002d8e7  xor     edi, edi
0x18002d8e9  mov     rbx, rcx
0x18002d8ec  mov     r9d, 0Ah
0x18002d8f2  test    r8, r8
0x18002d8f5  jz      short loc_18002D90E
0x18002d8f7  mov     rax, rdx
0x18002d8fa  inc     rax
0x18002d8fd  cmp     [r8+rax*2], di
0x18002d902  jnz     short loc_18002D8FA
0x18002d904  lea     r11, ds:2[rax*2]
0x18002d90c  jmp     short loc_18002D911
0x18002d90e  mov     r11, r9
0x18002d911  mov     rcx, [rsp+78h+arg_28]
0x18002d919  lea     rsi, aNull_0; "NULL"
0x18002d920  test    r8, r8
0x18002d923  cmovz   r8, rsi
0x18002d927  test    rcx, rcx
0x18002d92a  jz      short loc_18002D942
0x18002d92c  mov     rax, rdx
0x18002d92f  inc     rax
0x18002d932  cmp     [rcx+rax*2], di
0x18002d936  jnz     short loc_18002D92F
0x18002d938  lea     r10, ds:2[rax*2]
0x18002d940  jmp     short loc_18002D945
0x18002d942  mov     r10, r9
0x18002d945  mov     rax, [rsp+78h+arg_20]
0x18002d94d  test    rcx, rcx
0x18002d950  cmovz   rcx, rsi
0x18002d954  test    rax, rax
0x18002d957  jz      short loc_18002D96D
0x18002d959  inc     rdx
0x18002d95c  cmp     [rax+rdx*2], di
0x18002d960  jnz     short loc_18002D959
0x18002d962  lea     r9, ds:2[rdx*2]
0x18002d96a  test    rax, rax
0x18002d96d  mov     [rsp+78h+var_18], rdi
0x18002d972  mov     edx, 10h
0x18002d977  mov     [rsp+78h+var_20], r11
0x18002d97c  cmovz   rax, rsi
0x18002d980  mov     [rsp+78h+var_28], r8
0x18002d985  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002d98c  mov     [rsp+78h+var_30], r10
0x18002d991  mov     [rsp+78h+var_38], rcx
0x18002d996  mov     rcx, rbx
0x18002d999  mov     [rsp+78h+var_40], r9
0x18002d99e  mov     r9d, edx
0x18002d9a1  mov     [rsp+78h+var_48], rax
0x18002d9a6  lea     rax, aPenserviceCpen_5; "PENSERVICE_CPenProcess::CreateProcessW"
0x18002d9ad  mov     [rsp+78h+var_50], 27h ; '''
0x18002d9b6  mov     [rsp+78h+var_58], rax
0x18002d9bb  lea     edx, [r9+1Bh]
0x18002d9bf  call    cs:__imp_EtwTraceMessage
0x18002d9c5  lea     r11, [rsp+78h+var_8]
0x18002d9ca  mov     rbx, [r11+10h]
0x18002d9ce  mov     rsi, [r11+18h]
0x18002d9d2  mov     rsp, r11
0x18002d9d5  pop     rdi
0x18002d9d6  retn
```
