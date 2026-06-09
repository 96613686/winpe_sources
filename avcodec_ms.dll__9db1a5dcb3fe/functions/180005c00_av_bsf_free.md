# av_bsf_free

- ea: `0x180005c00`
- end: `0x180005c91`
- name: `av_bsf_free`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x1800050a4`
- `0x180005960`
- `0x180005ac0`
- `0x180005ee0`
- `0x1800060b4`
- `0x180007164`

## callees

- `0x180005c00`
- `0x180006470`
- `0x18000ef00`
- `0x18002271c`
- `0x180022746`
- `0x180024140`

## pseudocode

```c
void __fastcall av_bsf_free(_QWORD *a1)
{
  __int64 v1; // rbx
  void (__fastcall *v3)(_QWORD); // rax

  if ( a1 )
  {
    v1 = *a1;
    if ( *a1 )
    {
      if ( *(_QWORD *)(v1 + 16) )
      {
        v3 = *(void (__fastcall **)(_QWORD))(*(_QWORD *)(v1 + 8) + 48LL);
        if ( v3 )
          v3(*a1);
        if ( *(_QWORD *)(*(_QWORD *)(v1 + 8) + 16LL) )
          av_opt_free(*(_QWORD *)(v1 + 16));
        av_freep(v1 + 16);
      }
      av_packet_free(v1 + 56);
      avcodec_parameters_free(v1 + 24);
      avcodec_parameters_free(v1 + 32);
      av_freep((__int64)a1);
    }
  }
}

```

## disassembly

```asm
0x180005c00  test    rcx, rcx
0x180005c03  jz      locret_180005C90
0x180005c09  mov     [rsp+arg_0], rbx
0x180005c0e  mov     [rsp+arg_8], rsi
0x180005c13  push    rdi
0x180005c14  sub     rsp, 20h
0x180005c18  mov     rbx, [rcx]
0x180005c1b  mov     rdi, rcx
0x180005c1e  test    rbx, rbx
0x180005c21  jz      short loc_180005C81
0x180005c23  lea     rsi, [rbx+10h]
0x180005c27  cmp     qword ptr [rsi], 0
0x180005c2b  jz      short loc_180005C5E
0x180005c2d  mov     rax, [rbx+8]
0x180005c31  mov     rax, [rax+30h]
0x180005c35  test    rax, rax
0x180005c38  jz      short loc_180005C43
0x180005c3a  mov     rcx, rbx
0x180005c3d  call    cs:__guard_dispatch_icall_fptr
0x180005c43  mov     rax, [rbx+8]
0x180005c47  cmp     qword ptr [rax+10h], 0
0x180005c4c  jz      short loc_180005C56
0x180005c4e  mov     rcx, [rsi]
0x180005c51  call    av_opt_free
0x180005c56  mov     rcx, rsi
0x180005c59  call    av_freep
0x180005c5e  lea     rcx, [rbx+38h]
0x180005c62  call    av_packet_free
0x180005c67  lea     rcx, [rbx+18h]
0x180005c6b  call    avcodec_parameters_free
0x180005c70  lea     rcx, [rbx+20h]
0x180005c74  call    avcodec_parameters_free
0x180005c79  mov     rcx, rdi
0x180005c7c  call    av_freep
0x180005c81  mov     rbx, [rsp+28h+arg_0]
0x180005c86  mov     rsi, [rsp+28h+arg_8]
0x180005c8b  add     rsp, 20h
0x180005c8f  pop     rdi
0x180005c90  retn
```
