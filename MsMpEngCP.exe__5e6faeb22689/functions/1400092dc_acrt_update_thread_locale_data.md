# __acrt_update_thread_locale_data

- ea: `0x1400092dc`
- end: `0x14000934a`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000a3d4`
- `0x14000a408`

## callees

- `0x140005a20`
- `0x140005fe8`
- `0x1400081e8`
- `0x140008248`
- `0x1400092dc`
- `0x14000934c`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 *v1; // rdi
  __int64 v2; // rbx

  v0 = sub_140005FE8();
  v1 = (__int64 *)(v0 + 144);
  if ( (*(_DWORD *)(v0 + 936) & dword_140019840) == 0 || (v2 = *v1) == 0 )
  {
    sub_1400081E8(4);
    v2 = updatetlocinfoEx_nolock(v1, qword_14001AB58);
    sub_140008248(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x1400092dc  mov     [rsp+arg_0], rbx
0x1400092e1  push    rdi
0x1400092e2  sub     rsp, 20h
0x1400092e6  call    sub_140005FE8
0x1400092eb  lea     rdi, [rax+90h]
0x1400092f2  mov     ecx, [rax+3A8h]
0x1400092f8  mov     eax, cs:dword_140019840
0x1400092fe  test    eax, ecx
0x140009300  jz      short loc_14000930A
0x140009302  mov     rbx, [rdi]
0x140009305  test    rbx, rbx
0x140009308  jnz     short loc_140009336
0x14000930a  mov     ecx, 4
0x14000930f  call    sub_1400081E8
0x140009314  nop
0x140009315  mov     rdx, cs:qword_14001AB58
0x14000931c  mov     rcx, rdi
0x14000931f  call    _updatetlocinfoEx_nolock
0x140009324  mov     rbx, rax
0x140009327  mov     ecx, 4
0x14000932c  call    sub_140008248
0x140009331  test    rbx, rbx
0x140009334  jz      short loc_140009344
0x140009336  mov     rax, rbx
0x140009339  mov     rbx, [rsp+28h+arg_0]
0x14000933e  add     rsp, 20h
0x140009342  pop     rdi
0x140009343  retn
0x140009344  call    abort
0x14000df5c  push    rbp; Microsoft VisualC 64bit universal runtime
0x14000df5e  sub     rsp, 20h
0x14000df62  mov     rbp, rdx
0x14000df65  mov     ecx, 4
0x14000df6a  add     rsp, 20h
0x14000df6e  pop     rbp
0x14000df6f  jmp     sub_140008248
```
