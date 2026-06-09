# av_packet_get_side_data

- ea: `0x18000f010`
- end: `0x18000f071`
- name: `av_packet_get_side_data`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180007c38`
- `0x180007d18`

## callees

- `0x18000f010`

## pseudocode

```c
__int64 __fastcall av_packet_get_side_data(__int64 a1, int a2, _QWORD *a3)
{
  int v3; // eax
  __int64 v5; // r11
  __int64 v6; // r10
  __int64 v7; // rbx
  _DWORD *v8; // rcx

  v3 = 0;
  if ( *(int *)(a1 + 56) <= 0 )
  {
LABEL_5:
    if ( a3 )
      *a3 = 0;
    return 0;
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 48);
    v6 = 0;
    v7 = *(int *)(a1 + 56);
    v8 = (_DWORD *)(v5 + 16);
    while ( *v8 != a2 )
    {
      ++v3;
      ++v6;
      v8 += 6;
      if ( v6 >= v7 )
        goto LABEL_5;
    }
    if ( a3 )
      *a3 = *(_QWORD *)(v5 + 24LL * v3 + 8);
    return *(_QWORD *)(*(_QWORD *)(a1 + 48) + 24LL * v3);
  }
}

```

## disassembly

```asm
0x18000f010  mov     [rsp+arg_0], rbx
0x18000f015  xor     eax, eax
0x18000f017  mov     r9, rcx
0x18000f01a  cmp     [rcx+38h], eax
0x18000f01d  jle     short loc_18000F040
0x18000f01f  mov     r11, [rcx+30h]
0x18000f023  xor     r10d, r10d
0x18000f026  movsxd  rbx, dword ptr [rcx+38h]
0x18000f02a  lea     rcx, [r11+10h]
0x18000f02e  cmp     [rcx], edx
0x18000f030  jz      short loc_18000F054
0x18000f032  inc     eax
0x18000f034  inc     r10
0x18000f037  add     rcx, 18h
0x18000f03b  cmp     r10, rbx
0x18000f03e  jl      short loc_18000F02E
0x18000f040  test    r8, r8
0x18000f043  jz      short loc_18000F04C
0x18000f045  mov     qword ptr [r8], 0
0x18000f04c  xor     eax, eax
0x18000f04e  mov     rbx, [rsp+arg_0]
0x18000f053  retn
0x18000f054  cdqe
0x18000f056  lea     rcx, [rax+rax*2]
0x18000f05a  test    r8, r8
0x18000f05d  jz      short loc_18000F067
0x18000f05f  mov     rax, [r11+rcx*8+8]
0x18000f064  mov     [r8], rax
0x18000f067  mov     rax, [r9+30h]
0x18000f06b  mov     rax, [rax+rcx*8]
0x18000f06f  jmp     short loc_18000F04E
```
