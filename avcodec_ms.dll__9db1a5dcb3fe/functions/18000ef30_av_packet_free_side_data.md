# av_packet_free_side_data

- ea: `0x18000ef30`
- end: `0x18000ef84`
- name: `av_packet_free_side_data`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000edf0`
- `0x18000f940`

## callees

- `0x18000ef30`
- `0x18002271c`

## pseudocode

```c
__int64 __fastcall av_packet_free_side_data(__int64 a1)
{
  int i; // edi
  __int64 result; // rax

  for ( i = 0; i < *(_DWORD *)(a1 + 56); ++i )
    av_freep(*(_QWORD *)(a1 + 48) + 24LL * i);
  result = av_freep(a1 + 48);
  *(_DWORD *)(a1 + 56) = 0;
  return result;
}

```

## disassembly

```asm
0x18000ef30  mov     [rsp+arg_0], rbx
0x18000ef35  mov     [rsp+arg_8], rsi
0x18000ef3a  push    rdi
0x18000ef3b  sub     rsp, 20h
0x18000ef3f  xor     edi, edi
0x18000ef41  mov     rbx, rcx
0x18000ef44  cmp     [rcx+38h], edi
0x18000ef47  jle     short loc_18000EF64
0x18000ef49  movsxd  rax, edi
0x18000ef4c  lea     rdx, [rax+rax*2]
0x18000ef50  mov     rax, [rbx+30h]
0x18000ef54  lea     rcx, [rax+rdx*8]
0x18000ef58  call    av_freep
0x18000ef5d  inc     edi
0x18000ef5f  cmp     edi, [rbx+38h]
0x18000ef62  jl      short loc_18000EF49
0x18000ef64  lea     rcx, [rbx+30h]
0x18000ef68  call    av_freep
0x18000ef6d  mov     rsi, [rsp+28h+arg_8]
0x18000ef72  mov     dword ptr [rbx+38h], 0
0x18000ef79  mov     rbx, [rsp+28h+arg_0]
0x18000ef7e  add     rsp, 20h
0x18000ef82  pop     rdi
0x18000ef83  retn
```
