# av_packet_shrink_side_data

- ea: `0x18000f430`
- end: `0x18000f479`
- name: `av_packet_shrink_side_data`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000f430`

## pseudocode

```c
__int64 __fastcall av_packet_shrink_side_data(__int64 a1, int a2, unsigned __int64 a3)
{
  int v3; // eax
  __int64 v4; // r9
  __int64 v5; // r10
  __int64 v6; // r11
  _DWORD *i; // rcx

  v3 = 0;
  if ( *(int *)(a1 + 56) <= 0 )
    return 4294967294LL;
  v4 = *(_QWORD *)(a1 + 48);
  v5 = 0;
  v6 = *(int *)(a1 + 56);
  for ( i = (_DWORD *)(v4 + 16); *i != a2; i += 6 )
  {
    ++v3;
    if ( ++v5 >= v6 )
      return 4294967294LL;
  }
  if ( a3 > *(_QWORD *)(v4 + 24LL * v3 + 8) )
    return 4294967284LL;
  *(_QWORD *)(v4 + 24LL * v3 + 8) = a3;
  return 0;
}

```

## disassembly

```asm
0x18000f430  xor     eax, eax
0x18000f432  cmp     [rcx+38h], eax
0x18000f435  jle     short loc_18000F458
0x18000f437  mov     r9, [rcx+30h]
0x18000f43b  mov     r10d, eax
0x18000f43e  movsxd  r11, dword ptr [rcx+38h]
0x18000f442  lea     rcx, [r9+10h]
0x18000f446  cmp     [rcx], edx
0x18000f448  jz      short loc_18000F45E
0x18000f44a  inc     eax
0x18000f44c  inc     r10
0x18000f44f  add     rcx, 18h
0x18000f453  cmp     r10, r11
0x18000f456  jl      short loc_18000F446
0x18000f458  mov     eax, 0FFFFFFFEh
0x18000f45d  retn
0x18000f45e  cdqe
0x18000f460  lea     rcx, [rax+rax*2]
0x18000f464  cmp     r8, [r9+rcx*8+8]
0x18000f469  jbe     short loc_18000F471
0x18000f46b  mov     eax, 0FFFFFFF4h
0x18000f470  retn
0x18000f471  mov     [r9+rcx*8+8], r8
0x18000f476  xor     eax, eax
0x18000f478  retn
```
