# av_timecode_init_from_components

- ea: `0x180052370`
- end: `0x180052453`
- name: `av_timecode_init_from_components`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180052460`

## callees

- `0x180052370`
- `0x1800527e0`
- `0x18007b020`

## pseudocode

```c
__int64 __fastcall av_timecode_init_from_components(
        __m128i *a1,
        __int64 a2,
        __int32 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        __int64 a8)
{
  __int64 v12; // rax
  __int64 result; // rax
  int v14; // r8d
  int v15; // ecx
  bool v16; // zf
  int v17; // [rsp+3Ch] [rbp+14h]

  v17 = HIDWORD(a2);
  sub_18007B020(a1, 0, 0x14u);
  a1->m128i_i32[1] = a3;
  a1->m128i_i64[1] = a2;
  if ( v17 && (_DWORD)a2 )
    v12 = ((int)a2 + v17 / 2LL) / v17;
  else
    LODWORD(v12) = -1;
  a1[1].m128i_i32[0] = v12;
  result = sub_1800527E0(a8, a1);
  if ( (int)result >= 0 )
  {
    v14 = a5 + 60 * a4;
    v15 = a1[1].m128i_i32[0] * (a6 + 60 * v14);
    v16 = (a1->m128i_i8[4] & 1) == 0;
    a1->m128i_i32[0] = v15 + a7;
    if ( !v16 )
      a1->m128i_i32[0] = a7 + v15 - 2 * a1[1].m128i_i32[0] / 0x1Eu * (v14 - v14 / 10);
    return 0;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x180052370  mov     rax, rsp
0x180052373  mov     [rax+8], rbx
0x180052377  mov     [rax+18h], rbp
0x18005237b  mov     [rax+20h], rsi
0x18005237f  mov     [rax+10h], rdx
0x180052383  push    rdi
0x180052384  sub     rsp, 20h
0x180052388  mov     rbx, rdx
0x18005238b  mov     edi, r8d
0x18005238e  xor     edx, edx
0x180052390  mov     ebp, r9d
0x180052393  mov     rsi, rcx
0x180052396  lea     r8d, [rdx+14h]
0x18005239a  call    sub_18007B020
0x18005239f  movsxd  rax, [rsp+28h+arg_C]
0x1800523a4  mov     [rsi+4], edi
0x1800523a7  mov     [rsi+8], rbx
0x1800523ab  test    eax, eax
0x1800523ad  jz      short loc_1800523CB
0x1800523af  test    ebx, ebx
0x1800523b1  jz      short loc_1800523CB
0x1800523b3  mov     r8, rax
0x1800523b6  movsxd  rcx, ebx
0x1800523b9  cqo
0x1800523bb  sub     rax, rdx
0x1800523be  sar     rax, 1
0x1800523c1  add     rax, rcx
0x1800523c4  cqo
0x1800523c6  idiv    r8
0x1800523c9  jmp     short loc_1800523CE
0x1800523cb  or      eax, 0FFFFFFFFh
0x1800523ce  mov     rcx, [rsp+28h+arg_38]
0x1800523d3  mov     rdx, rsi
0x1800523d6  mov     [rsi+10h], eax
0x1800523d9  call    sub_1800527E0
0x1800523de  test    eax, eax
0x1800523e0  jns     short loc_1800523E7
0x1800523e2  lfence
0x1800523e5  jmp     short loc_18005243E
0x1800523e7  mov     r9d, [rsp+28h+arg_30]
0x1800523ec  imul    r8d, ebp, 3Ch ; '<'
0x1800523f0  add     r8d, [rsp+28h+arg_20]
0x1800523f5  imul    ecx, r8d, 3Ch ; '<'
0x1800523f9  add     ecx, [rsp+28h+arg_28]
0x1800523fd  imul    ecx, [rsi+10h]
0x180052401  test    byte ptr [rsi+4], 1
0x180052405  lea     eax, [rcx+r9]
0x180052409  mov     [rsi], eax
0x18005240b  jz      short loc_18005243C
0x18005240d  mov     eax, 66666667h
0x180052412  imul    r8d
0x180052415  sar     edx, 2
0x180052418  mov     eax, edx
0x18005241a  shr     eax, 1Fh
0x18005241d  add     edx, eax
0x18005241f  mov     eax, 88888889h
0x180052424  sub     r8d, edx
0x180052427  mul     dword ptr [rsi+10h]
0x18005242a  shr     edx, 4
0x18005242d  imul    r8d, edx
0x180052431  add     r8d, r8d
0x180052434  sub     ecx, r8d
0x180052437  add     ecx, r9d
0x18005243a  mov     [rsi], ecx
0x18005243c  xor     eax, eax
0x18005243e  mov     rbx, [rsp+28h+arg_0]
0x180052443  mov     rbp, [rsp+28h+arg_10]
0x180052448  mov     rsi, [rsp+28h+arg_18]
0x18005244d  add     rsp, 20h
0x180052451  pop     rdi
0x180052452  retn
```
