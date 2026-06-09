# LocalMapStringRemoveNode

- ea: `0x180002998`
- end: `0x180002aab`
- name: `LocalMapStringRemoveNode`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`

## callees

- `0x180002998`
- `0x1800135cc`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002a70`
- `KERNEL32!GetProcessHeap` at `0x180002a84`
- `KERNEL32!GetProcessHeap` at `0x180002a70`
- `KERNEL32!GetProcessHeap` at `0x180002a84`
- `KERNEL32!HeapFree` at `0x180002a7e`
- `KERNEL32!HeapFree` at `0x180002a92`
- `KERNEL32!HeapFree` at `0x180002a7e`
- `KERNEL32!HeapFree` at `0x180002a92`

## pseudocode

```c
BOOL __fastcall LocalMapStringRemoveNode(__int64 a1, void **a2)
{
  _QWORD *v4; // rdx
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rcx
  void (__fastcall *v8)(void *); // rax
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax
  BOOL result; // eax

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v4 = a2[3];
  if ( v4 )
  {
    v5 = a2[4];
    if ( v5 )
    {
      v4 = (_QWORD *)v5[3];
      if ( v4 )
      {
        while ( v4[3] )
          v4 = (_QWORD *)v4[3];
        *(_QWORD *)(v4[2] + 24LL) = v4[4];
        v7 = v4[4];
        if ( v7 )
          *(_QWORD *)(v7 + 16) = v4[2];
        v4[4] = a2[4];
        *((_QWORD *)a2[4] + 2) = v4;
      }
      else
      {
        v4 = a2[4];
      }
      v4[3] = a2[3];
      *((_QWORD *)a2[3] + 2) = v4;
    }
  }
  else
  {
    v4 = a2[4];
    if ( !v4 )
      goto LABEL_13;
  }
  v4[2] = a2[2];
LABEL_13:
  v6 = a2[2];
  if ( v6 )
  {
    if ( a2 == (void **)v6[3] )
      v6[3] = v4;
    else
      v6[4] = v4;
  }
  else
  {
    *(_QWORD *)(a1 + 8) = v4;
  }
  v8 = *(void (__fastcall **)(void *))(a1 + 16);
  if ( v8 )
    v8(a2[1]);
  v9 = *a2;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v9);
  v11 = GetProcessHeap();
  result = HeapFree(v11, 0, a2);
  --*(_DWORD *)(a1 + 4);
  return result;
}

```

## disassembly

```asm
0x180002998  mov     [rsp+arg_0], rbx
0x18000299d  mov     [rsp+arg_8], rsi
0x1800029a2  push    rdi
0x1800029a3  sub     rsp, 20h
0x1800029a7  mov     rdi, rdx
0x1800029aa  mov     rsi, rcx
0x1800029ad  test    rcx, rcx
0x1800029b0  jnz     short loc_1800029B7
0x1800029b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800029b7  test    rdi, rdi
0x1800029ba  jnz     short loc_1800029C1
0x1800029bc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800029c1  mov     rdx, [rdi+18h]
0x1800029c5  test    rdx, rdx
0x1800029c8  jnz     short loc_1800029D5
0x1800029ca  mov     rdx, [rdi+20h]
0x1800029ce  test    rdx, rdx
0x1800029d1  jz      short loc_180002A02
0x1800029d3  jmp     short loc_1800029FA
0x1800029d5  mov     rax, [rdi+20h]
0x1800029d9  test    rax, rax
0x1800029dc  jz      short loc_1800029FA
0x1800029de  mov     rdx, [rax+18h]
0x1800029e2  test    rdx, rdx
0x1800029e5  jnz     short loc_180002A15
0x1800029e7  mov     rdx, rax
0x1800029ea  mov     rax, [rdi+18h]
0x1800029ee  mov     [rdx+18h], rax
0x1800029f2  mov     rax, [rdi+18h]
0x1800029f6  mov     [rax+10h], rdx
0x1800029fa  mov     rax, [rdi+10h]
0x1800029fe  mov     [rdx+10h], rax
0x180002a02  mov     rax, [rdi+10h]
0x180002a06  test    rax, rax
0x180002a09  jnz     short loc_180002A4B
0x180002a0b  mov     [rsi+8], rdx
0x180002a0f  jmp     short loc_180002A5B
0x180002a11  mov     rdx, [rdx+18h]
0x180002a15  cmp     qword ptr [rdx+18h], 0
0x180002a1a  jnz     short loc_180002A11
0x180002a1c  mov     rcx, [rdx+10h]
0x180002a20  mov     rax, [rdx+20h]
0x180002a24  mov     [rcx+18h], rax
0x180002a28  mov     rcx, [rdx+20h]
0x180002a2c  test    rcx, rcx
0x180002a2f  jz      short loc_180002A39
0x180002a31  mov     rax, [rdx+10h]
0x180002a35  mov     [rcx+10h], rax
0x180002a39  mov     rax, [rdi+20h]
0x180002a3d  mov     [rdx+20h], rax
0x180002a41  mov     rax, [rdi+20h]
0x180002a45  mov     [rax+10h], rdx
0x180002a49  jmp     short loc_1800029EA
0x180002a4b  cmp     rdi, [rax+18h]
0x180002a4f  jnz     short loc_180002A57
0x180002a51  mov     [rax+18h], rdx
0x180002a55  jmp     short loc_180002A5B
0x180002a57  mov     [rax+20h], rdx
0x180002a5b  mov     rax, [rsi+10h]
0x180002a5f  test    rax, rax
0x180002a62  jz      short loc_180002A6D
0x180002a64  mov     rcx, [rdi+8]
0x180002a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6d  mov     rbx, [rdi]
0x180002a70  call    cs:__imp_GetProcessHeap
0x180002a76  mov     r8, rbx; lpMem
0x180002a79  xor     edx, edx; dwFlags
0x180002a7b  mov     rcx, rax; hHeap
0x180002a7e  call    cs:__imp_HeapFree
0x180002a84  call    cs:__imp_GetProcessHeap
0x180002a8a  mov     r8, rdi; lpMem
0x180002a8d  xor     edx, edx; dwFlags
0x180002a8f  mov     rcx, rax; hHeap
0x180002a92  call    cs:__imp_HeapFree
0x180002a98  dec     dword ptr [rsi+4]
0x180002a9b  mov     rsi, [rsp+28h+arg_8]
0x180002aa0  mov     rbx, [rsp+28h+arg_0]
0x180002aa5  add     rsp, 20h
0x180002aa9  pop     rdi
0x180002aaa  retn
```
