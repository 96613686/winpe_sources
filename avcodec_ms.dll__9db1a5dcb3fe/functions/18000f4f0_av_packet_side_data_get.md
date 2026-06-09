# av_packet_side_data_get

- ea: `0x18000f4f0`
- end: `0x18000f524`
- name: `av_packet_side_data_get`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000a670`

## callees

- `0x18000f4f0`

## pseudocode

```c
__int64 __fastcall av_packet_side_data_get(__int64 a1, int a2, int a3)
{
  int v3; // eax
  __int64 v5; // rcx
  __int64 v6; // r9
  _DWORD *i; // rdx

  v3 = 0;
  v5 = a2;
  if ( a2 <= 0 )
    return 0;
  v6 = 0;
  for ( i = (_DWORD *)(a1 + 16); *i != a3; i += 6 )
  {
    ++v3;
    if ( ++v6 >= v5 )
      return 0;
  }
  return a1 + 24LL * v3;
}

```

## disassembly

```asm
0x18000f4f0  xor     eax, eax
0x18000f4f2  mov     r10, rcx
0x18000f4f5  movsxd  rcx, edx
0x18000f4f8  test    edx, edx
0x18000f4fa  jle     short loc_18000F516
0x18000f4fc  mov     r9d, eax
0x18000f4ff  lea     rdx, [r10+10h]
0x18000f503  cmp     [rdx], r8d
0x18000f506  jz      short loc_18000F519
0x18000f508  inc     eax
0x18000f50a  inc     r9
0x18000f50d  add     rdx, 18h
0x18000f511  cmp     r9, rcx
0x18000f514  jl      short loc_18000F503
0x18000f516  xor     eax, eax
0x18000f518  retn
0x18000f519  cdqe
0x18000f51b  lea     rcx, [rax+rax*2]
0x18000f51f  lea     rax, [r10+rcx*8]
0x18000f523  retn
```
