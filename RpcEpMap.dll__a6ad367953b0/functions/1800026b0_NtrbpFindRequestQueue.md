# NtrbpFindRequestQueue

- ea: `0x1800026b0`
- end: `0x18000270e`
- name: `NtrbpFindRequestQueue`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001384`
- `0x1800013f8`
- `0x180002520`

## callees

- `0x1800026b0`
- `0x18000b010`

## pseudocode

```c
__int128 *__fastcall NtrbpFindRequestQueue(__int64 a1)
{
  __int128 *v1; // rbx
  __int128 *v3; // rdi

  v1 = (__int128 *)NtrbRequestQueueListHead;
  while ( v1 != &NtrbRequestQueueListHead && v1 )
  {
    v3 = v1;
    v1 = *(__int128 **)v1;
    if ( (unsigned int)((__int64 (__fastcall *)(__int64, _QWORD))NtrbUserCompareRequestIds)(a1, *((_QWORD *)v3 + 2)) )
      return v3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800026b0  mov     [rsp+arg_0], rbx
0x1800026b5  mov     [rsp+arg_8], rsi
0x1800026ba  push    rdi
0x1800026bb  sub     rsp, 20h
0x1800026bf  mov     rbx, qword ptr cs:NtrbRequestQueueListHead
0x1800026c6  mov     rsi, rcx
0x1800026c9  lea     rax, NtrbRequestQueueListHead
0x1800026d0  cmp     rbx, rax
0x1800026d3  jnz     short loc_1800026EA
0x1800026d5  xor     edi, edi
0x1800026d7  mov     rbx, [rsp+28h+arg_0]
0x1800026dc  mov     rax, rdi
0x1800026df  mov     rsi, [rsp+28h+arg_8]
0x1800026e4  add     rsp, 20h
0x1800026e8  pop     rdi
0x1800026e9  retn
0x1800026ea  test    rbx, rbx
0x1800026ed  jz      short loc_1800026D5
0x1800026ef  mov     rax, cs:NtrbUserCompareRequestIds
0x1800026f6  mov     rdi, rbx
0x1800026f9  mov     rbx, [rbx]
0x1800026fc  mov     rcx, rsi
0x1800026ff  mov     rdx, [rdi+10h]
0x180002703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002708  test    eax, eax
0x18000270a  jz      short loc_1800026C9
0x18000270c  jmp     short loc_1800026D7
```
