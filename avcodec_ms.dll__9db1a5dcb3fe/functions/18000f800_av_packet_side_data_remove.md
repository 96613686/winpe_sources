# av_packet_side_data_remove

- ea: `0x18000f800`
- end: `0x18000f896`
- name: `av_packet_side_data_remove`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18000f800`
- `0x18002277c`

## pseudocode

```c
__int64 __fastcall av_packet_side_data_remove(__int64 a1, int *a2, int a3)
{
  int v3; // r9d
  int v6; // r14d
  int v7; // r10d
  __int64 result; // rax
  _DWORD *v9; // rcx
  __int64 v10; // rbx

  v3 = *a2;
  v6 = *a2 - 1;
  v7 = v6;
  result = v6;
  if ( v6 >= 0 )
  {
    v9 = (_DWORD *)(a1 + 16 + 24LL * v6);
    while ( *v9 != a3 )
    {
      --v7;
      v9 -= 6;
      if ( --result < 0 )
        goto LABEL_7;
    }
    v10 = 3LL * v7;
    result = av_free(*(_QWORD *)(a1 + 24LL * v7));
    v3 = v6;
    *(_OWORD *)(a1 + 8 * v10) = *(_OWORD *)(a1 + 24LL * v6);
    *(_QWORD *)(a1 + 8 * v10 + 16) = *(_QWORD *)(a1 + 24LL * v6 + 16);
  }
LABEL_7:
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x18000f800  mov     rax, rsp
0x18000f803  mov     [rax+8], rbx
0x18000f807  mov     [rax+10h], rbp
0x18000f80b  mov     [rax+18h], rsi
0x18000f80f  mov     [rax+20h], rdi
0x18000f813  push    r14
0x18000f815  sub     rsp, 20h
0x18000f819  mov     r9d, [rdx]
0x18000f81c  mov     rsi, rdx
0x18000f81f  mov     rdi, rcx
0x18000f822  lea     r14d, [r9-1]
0x18000f826  movsxd  r10, r14d
0x18000f829  mov     rax, r10
0x18000f82c  test    r14d, r14d
0x18000f82f  js      short loc_18000F878
0x18000f831  add     rcx, 10h
0x18000f835  lea     rbp, [r10+r10*2]
0x18000f839  lea     rcx, [rcx+rbp*8]
0x18000f83d  cmp     [rcx], r8d
0x18000f840  jz      short loc_18000F851
0x18000f842  dec     r10d
0x18000f845  sub     rcx, 18h
0x18000f849  sub     rax, 1
0x18000f84d  jns     short loc_18000F83D
0x18000f84f  jmp     short loc_18000F878
0x18000f851  movsxd  rax, r10d
0x18000f854  lea     rbx, [rax+rax*2]
0x18000f858  mov     rcx, [rdi+rbx*8]
0x18000f85c  call    av_free
0x18000f861  movups  xmm0, xmmword ptr [rdi+rbp*8]
0x18000f865  mov     r9d, r14d
0x18000f868  movups  xmmword ptr [rdi+rbx*8], xmm0
0x18000f86c  movsd   xmm1, qword ptr [rdi+rbp*8+10h]
0x18000f872  movsd   qword ptr [rdi+rbx*8+10h], xmm1
0x18000f878  mov     rbx, [rsp+28h+arg_0]
0x18000f87d  mov     rbp, [rsp+28h+arg_8]
0x18000f882  mov     rdi, [rsp+28h+arg_18]
0x18000f887  mov     [rsi], r9d
0x18000f88a  mov     rsi, [rsp+28h+arg_10]
0x18000f88f  add     rsp, 20h
0x18000f893  pop     r14
0x18000f895  retn
```
